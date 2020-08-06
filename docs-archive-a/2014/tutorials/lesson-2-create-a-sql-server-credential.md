---
title: 'Lektion 2: Erstellen eines SQL Server Anmelde Informationen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 64f8805c-1ddc-4c96-a47c-22917d12e1ab
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: e8b13c8d4d9e5937064cef5503ec64bfd6e4a2d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726385"
---
# <a name="lesson-2-create-a-sql-server-credential"></a><span data-ttu-id="ead00-102">Lektion 2: Erstellen von SQL Server-Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="ead00-102">Lesson 2: Create a SQL Server Credential</span></span>
  <span data-ttu-id="ead00-103">**Anmeldeinformationen:** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Anmeldeinformationen sind ein Objekt zum Speichern von Authentifizierungsinformationen, die für die Verbindung mit einer Ressource außerhalb von SQL Server erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ead00-103">**Credential:** A [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] credential is an object that is used to store authentication information required to connect to a resource outside of SQL Server.</span></span>  <span data-ttu-id="ead00-104">Hier werden [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] von Sicherungs-und Wiederherstellungs Prozessen Anmelde Informationen für die Authentifizierung beim Azure BLOB Storage-Dienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="ead00-104">Here, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backup and restore processes use credential to authenticate to the Azure Blob storage service.</span></span> <span data-ttu-id="ead00-105">In den Anmeldeinformationen werden der Name des Speicherkontos und der **Zugriffsschlüssel** des Speicherkontos gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ead00-105">The Credential stores the name of the storage account and the storage account **access key** values.</span></span> <span data-ttu-id="ead00-106">Sobald die Anmeldeinformationen erstellt wurden, müssen sie beim Ausgeben der BACKUP-/RESTORE-Anweisungen in der WITH CREDENTIAL-Option angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ead00-106">Once the credential is created, it must be specified in the WITH CREDENTIAL option when issuing the BACKUP/RESTORE statements.</span></span> <span data-ttu-id="ead00-107">Weitere Informationen zum Anzeigen, Kopieren oder erneuten Generieren von **access keys**für Speicherkonten finden Sie unter [Zugriffsschlüssel für Speicherkonten](https://msdn.microsoft.com/library/windowsazure/hh531566.aspx).</span><span class="sxs-lookup"><span data-stu-id="ead00-107">For more information about how to view, copy or regenerate storage account **access keys**, see [Storage Account Access Keys](https://msdn.microsoft.com/library/windowsazure/hh531566.aspx).</span></span>  
  
 <span data-ttu-id="ead00-108">Allgemeine Informationen zu Anmelde Informationen finden Sie unter [Anmelde](../relational-databases/security/authentication-access/credentials-database-engine.md)Informationen.</span><span class="sxs-lookup"><span data-stu-id="ead00-108">For general information about credentials, see [Credentials](../relational-databases/security/authentication-access/credentials-database-engine.md).</span></span>  
  
 <span data-ttu-id="ead00-109">Informationen zu anderen Beispielen, in denen Anmelde Informationen verwendet werden, finden Sie unter [Erstellen eines SQL Server-Agent Proxys](../ssms/agent/create-a-sql-server-agent-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="ead00-109">For information, on other examples where credentials are used, see [Create a SQL Server Agent Proxy](../ssms/agent/create-a-sql-server-agent-proxy.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ead00-110">Die Anforderungen für das Erstellen einer SQL Server Anmelde Informationen, die unten beschrieben werden, gelten speziell für SQL Server Sicherungs Prozesse ([SQL Server URL-Sicherung](../relational-databases/backup-restore/sql-server-backup-to-url.md)und [SQL Server verwaltete Sicherung in Azure](../relational-databases/backup-restore/sql-server-managed-backup-to-microsoft-azure.md)).</span><span class="sxs-lookup"><span data-stu-id="ead00-110">The requirements for creating a SQL Server credential described below are specific to SQL Server backup processes ([SQL Server Backup to URL](../relational-databases/backup-restore/sql-server-backup-to-url.md), and [SQL Server Managed  Backup to Azure](../relational-databases/backup-restore/sql-server-managed-backup-to-microsoft-azure.md)).</span></span> <span data-ttu-id="ead00-111">SQL Server verwendet beim Zugriff auf Azure-Speicher zum Schreiben oder Lesen von Sicherungen den Namen des Speicherkontos und Informationen zu den Zugriffsschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="ead00-111">SQL Server, when accessing Azure storage to write or read backups uses the storage account name and access key information.</span></span>  <span data-ttu-id="ead00-112">Weitere Informationen zum Erstellen von Anmeldeinformationen für das Speichern von Datenbankdateien in Azure-Speicher finden Sie unter [Lesson 3: Create a SQL Server Credential](../relational-databases/lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)</span><span class="sxs-lookup"><span data-stu-id="ead00-112">For more information on creating credentials for storing database files in Azure storage, see [Lesson 3: Create a SQL Server Credential](../relational-databases/lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)</span></span>  
  
## <a name="create-a-sql-server-credential"></a><span data-ttu-id="ead00-113">Erstellen von SQL Server-Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="ead00-113">Create a SQL Server Credential</span></span>  
 <span data-ttu-id="ead00-114">Führen Sie die folgenden Schritte aus, um SQL Server-Anmeldeinformationen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="ead00-114">To create a SQL Server Credential, use the following steps:</span></span>  
  
1.  <span data-ttu-id="ead00-115">Stellen Sie eine Verbindung mit SQL Server Management Studio her.</span><span class="sxs-lookup"><span data-stu-id="ead00-115">Connect to SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="ead00-116">Stellen Sie im Objekt-Explorer eine Verbindung mit der Instanz der Datenbank-Engine her, auf der die Datenbank AdventureWorks2012 installiert ist, oder verwenden Sie Ihre eigene Datenbank für dieses Lernprogramm.</span><span class="sxs-lookup"><span data-stu-id="ead00-116">In Object Explorer, connect to the instance of Database Engine that has AdventureWorks2012 database installed, or use your own database you plan to use for this tutorial.</span></span>  
  
3.  <span data-ttu-id="ead00-117">Klicken Sie auf der \*\*\*\* Standardsymbolleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="ead00-117">On the **Standard** tool bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="ead00-118">Kopieren Sie das folgende Beispiel in das Abfragefenster, und ändern Sie es nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="ead00-118">Copy and paste the following example into the query window, modify as needed.</span></span>  
  
    ```  
    CREATE CREDENTIAL mycredential   
    WITH IDENTITY= 'mystorageaccount' - this is the name of the storage account you specified when creating a storage account (See Lesson 1)   
    , SECRET = '<storage account access key>' - this should be either the Primary or Secondary Access Key for the storage account (See Lesson 1)  
  
    ```  
  
     <span data-ttu-id="ead00-119">![Zuordnen des Speicherkontos zu SQL-Anmeldeinformationen](../../2014/tutorials/media/backuptocloud-storage-credential-mapping.gif "Zuordnen des Speicherkontos zu SQL-Anmeldeinformationen")</span><span class="sxs-lookup"><span data-stu-id="ead00-119">![mapping storage account to sql credentials](../../2014/tutorials/media/backuptocloud-storage-credential-mapping.gif "mapping storage account to sql credentials")</span></span>  
  
5.  <span data-ttu-id="ead00-120">Prüfen Sie die T-SQL-Anweisung, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ead00-120">Verify the T-SQL statement and click **Execute**.</span></span>  
  
 <span data-ttu-id="ead00-121">Weitere Informationen zum Azure BLOB Storage-Dienst für Sicherungs Konzepte und-Anforderungen finden Sie unter [SQL Server sichern und Wiederherstellen mit Azure BLOB Storage Dienst](../relational-databases/backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="ead00-121">For more information about the Azure Blob storage service for backup concepts and requirements, see [SQL Server Backup and Restore with Azure Blob Storage Service](../relational-databases/backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
### <a name="next-lesson"></a><span data-ttu-id="ead00-122">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="ead00-122">Next Lesson</span></span>  
 <span data-ttu-id="ead00-123">[Lektion 3: Schreiben einer vollständigen Datenbanksicherung in den Azure BLOB Storage-Dienst](../../2014/tutorials/lesson-3-write-a-full-database-backup-to-the-windows-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="ead00-123">[Lesson 3: Write a Full Database Backup to the Azure Blob Storage Service](../../2014/tutorials/lesson-3-write-a-full-database-backup-to-the-windows-azure-blob-storage-service.md).</span></span>  
  
  
