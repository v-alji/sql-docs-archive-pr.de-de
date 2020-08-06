---
title: 'Lektion 3: Erstellen eines SQL Server Anmelde Informationen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 29e57ebd-828f-4dff-b473-c10ab0b1c597
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 808438e544e3beb18b2e2afa9c399b5666277483
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723842"
---
# <a name="lesson-3-create-a-sql-server-credential"></a><span data-ttu-id="12cee-102">Lektion 3: Erstellen von SQL Server-Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="12cee-102">Lesson 3: Create a SQL Server Credential</span></span>
  <span data-ttu-id="12cee-103">In dieser Lektion erstellen Sie Anmelde Informationen zum Speichern der Sicherheitsinformationen, die für den Zugriff auf das Azure-Speicherkonto verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="12cee-103">In this lesson, you will create a credential to store security information used to access the Azure storage account.</span></span>  
  
 <span data-ttu-id="12cee-104">SQL Server-Anmeldeinformationen sind ein Objekt zum Speichern von Authentifizierungsinformationen, die für die Verbindung mit einer Ressource außerhalb von SQL Server erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="12cee-104">A SQL Server credential is an object that is used to store authentication information required to connect to a resource outside of SQL Server.</span></span> <span data-ttu-id="12cee-105">In den Anmeldeinformationen werden der URI-Pfad des Speichercontainers und die Shared Access Signature-Schlüsselwerte gespeichert.</span><span class="sxs-lookup"><span data-stu-id="12cee-105">The credential stores the URI path of the storage container and the shared access signature key values.</span></span> <span data-ttu-id="12cee-106">Für jeden Speichercontainer, der von einer Daten- oder Protokolldatei verwendet wird, müssen Sie SQL Server-Anmeldeinformationen erstellen, deren Namen mit dem Containerpfad übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="12cee-106">For each storage container used by a data or log file, you must create a SQL Server Credential whose name matches the container path.</span></span>  
  
 <span data-ttu-id="12cee-107">Allgemeine Informationen zu Anmelde Informationen finden Sie unter [Anmelde Informationen &#40;Datenbank-Engine&#41;](security/authentication-access/credentials-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="12cee-107">For general information about credentials, see [Credentials &#40;Database Engine&#41;](security/authentication-access/credentials-database-engine.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="12cee-108">Die Anforderungen zum Erstellen einer SQL Server Anmelde Informationen, die unten beschrieben werden, gelten speziell für das Feature [SQL Server Datendateien in Azure](databases/sql-server-data-files-in-microsoft-azure.md) .</span><span class="sxs-lookup"><span data-stu-id="12cee-108">The requirements for creating a SQL Server credential described below are specific to the [SQL Server Data Files in Azure](databases/sql-server-data-files-in-microsoft-azure.md) feature.</span></span> <span data-ttu-id="12cee-109">Informationen zum Erstellen von Anmelde Informationen für Sicherungs Prozesse in Azure Storage finden Sie unter [Lektion 2: Erstellen eines SQL Server](../tutorials/lesson-2-create-a-sql-server-credential.md)Anmelde Informationen.</span><span class="sxs-lookup"><span data-stu-id="12cee-109">For information on creating credentials for backup processes in Azure storage, see [Lesson 2: Create a SQL Server Credential](../tutorials/lesson-2-create-a-sql-server-credential.md).</span></span>  
  
 <span data-ttu-id="12cee-110">Führen Sie die folgenden Schritte aus, um SQL Server-Anmeldeinformationen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="12cee-110">To create a SQL Server Credential, follow these steps:</span></span>  
  
1.  <span data-ttu-id="12cee-111">Stellen Sie eine Verbindung mit SQL Server Management Studio her.</span><span class="sxs-lookup"><span data-stu-id="12cee-111">Connect to SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="12cee-112">Stellen Sie im Objekt-Explorer eine Verbindung mit der Instanz der installierten Datenbank-Engine her.</span><span class="sxs-lookup"><span data-stu-id="12cee-112">In Object Explorer, connect to the instance of Database Engine installed.</span></span>  
  
3.  <span data-ttu-id="12cee-113">Klicken Sie auf der Standardsymbolleiste auf "Neue Abfrage".</span><span class="sxs-lookup"><span data-stu-id="12cee-113">On the Standard tool bar, click New Query.</span></span>  
  
4.  <span data-ttu-id="12cee-114">Kopieren Sie das folgende Beispiel in das Abfragefenster, und ändern Sie es nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="12cee-114">Copy and paste the following example into the query window, modify as needed.</span></span> <span data-ttu-id="12cee-115">Mit der folgenden Anweisung wird eine SQL Server Anmelde Informationen erstellt, um das freigegebene Zugriffs Zertifikat Ihres Speicher Containers zu speichern.</span><span class="sxs-lookup"><span data-stu-id="12cee-115">The following statement will create a SQL Server Credential to store your storage container's Shared Access Certificate.</span></span>  
  
    ```sql  
  
    USE master  
    CREATE CREDENTIAL credentialname - this name should match the container path and it must start with https.   
       WITH IDENTITY='SHARED ACCESS SIGNATURE', -- this is a mandatory string and do not change it.   
       SECRET = 'sharedaccesssignature' -- this is the shared access signature key that you obtained in Lesson 2.   
    GO  
  
    ```  
  
     <span data-ttu-id="12cee-116">Ausführliche Informationen finden Sie unter [Create Credential &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) in SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="12cee-116">For detailed information, see [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) in SQL Server Books Online.</span></span>  
  
5.  <span data-ttu-id="12cee-117">Um alle verfügbaren Anmeldeinformationen anzuzeigen, können Sie im Abfragefenster die folgende Anweisung ausführen:</span><span class="sxs-lookup"><span data-stu-id="12cee-117">To see all available credentials, you can run the following statement in the query window:</span></span>  
  
    ```sql  
    SELECT * from sys.credentials  
    ```  
  
     <span data-ttu-id="12cee-118">Weitere Informationen zu sys. Anmelde Informationen finden Sie unter [sys. Anmelde Informationen &#40;Transact-SQL-&#41;](/sql/relational-databases/system-catalog-views/sys-credentials-transact-sql) in SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="12cee-118">For more information on sys.credentials, see [sys.credentials &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-credentials-transact-sql) in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="12cee-119">**Nächste Lektion:**</span><span class="sxs-lookup"><span data-stu-id="12cee-119">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="12cee-120">Lektion 4: Erstellen einer Datenbank in Azure Storage</span><span class="sxs-lookup"><span data-stu-id="12cee-120">Lesson 4: Create a database in Azure Storage</span></span>](lesson-3-database-backup-to-url.md)  
  
  
