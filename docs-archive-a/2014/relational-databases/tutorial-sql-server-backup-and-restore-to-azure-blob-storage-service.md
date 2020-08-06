---
title: 'Tutorial: SQL Server-Sicherung und -Wiederherstellung mit dem Azure-BLOB-Speicherdienst | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 9e1d94ce-2c93-45d1-ae2a-2a7d1fa094c4
author: rothja
ms.author: jroth
ms.openlocfilehash: d15200968011cdb314829736512f39730782dc0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696701"
---
# <a name="tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service"></a><span data-ttu-id="5ca5e-102">Tutorial: SQL Server-Sicherung und -Wiederherstellung mit dem Azure Blob Storage-Dienst</span><span class="sxs-lookup"><span data-stu-id="5ca5e-102">Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service</span></span>
  <span data-ttu-id="5ca5e-103">Willkommen beim Tutorial zu den ersten Schritten mit SQL Server Sicherung und Wiederherstellung mit Azure BLOB Storage Dienst.</span><span class="sxs-lookup"><span data-stu-id="5ca5e-103">Welcome to the Getting Started with SQL Server Backup and Restore with Azure Blob Storage Service tutorial.</span></span> <span data-ttu-id="5ca5e-104">In diesem Tutorial erfahren Sie, wie Sie Sicherungen in den Azure-BLOB-Speicherdienst schreiben und daraus wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="5ca5e-104">This tutorial helps you understand how to write backups to and restore from the Azure Blob storage service.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="5ca5e-105">Lernziele</span><span class="sxs-lookup"><span data-stu-id="5ca5e-105">What You Will Learn</span></span>  
 <span data-ttu-id="5ca5e-106">In diesem Lernprogramm erfahren Sie, wie Sie ein Windows-Speicherkonto, einen BLOB-Container und Anmeldeinformationen für den Zugriff auf das Speicherkonto erstellen, eine Sicherung in den BLOB-Dienst schreiben und eine einfache Wiederherstellung ausführen.</span><span class="sxs-lookup"><span data-stu-id="5ca5e-106">This tutorial shows you how to create a Windows Storage account, a blob container, creating credentials to access the storage account, writing a backup to the blob service, and performing a simple restore.</span></span> <span data-ttu-id="5ca5e-107">Dieses Lernprogramm ist in vier Lektionen aufgeteilt:</span><span class="sxs-lookup"><span data-stu-id="5ca5e-107">This tutorial is divided into four lessons:</span></span>  
  
 [<span data-ttu-id="5ca5e-108">Lektion 1: Erstellen von Azure Storage Objekten</span><span class="sxs-lookup"><span data-stu-id="5ca5e-108">Lesson 1: Create Azure Storage Objects</span></span>](../tutorials/lesson-1-create-windows-azure-storage-objects.md)  
 <span data-ttu-id="5ca5e-109">In dieser Lektion erstellen Sie ein Azure-Speicherkonto und einen BLOB-Container.</span><span class="sxs-lookup"><span data-stu-id="5ca5e-109">In this lesson, you create an Azure storage account and a blob container.</span></span>  
  
 [<span data-ttu-id="5ca5e-110">Lektion 2: Erstellen von SQL Server-Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="5ca5e-110">Lesson 2: Create a SQL Server Credential</span></span>](../tutorials/lesson-2-create-a-sql-server-credential.md)  
 <span data-ttu-id="5ca5e-111">In dieser Lektion erstellen Sie Anmeldeinformationen, um die Sicherheitsinformationen für den Zugriff auf das Azure-Speicherkonto zu speichern.</span><span class="sxs-lookup"><span data-stu-id="5ca5e-111">In this lesson, you create a Credential to store security information used to access the Azure storage account.</span></span>  
  
 [<span data-ttu-id="5ca5e-112">Lektion 3: Schreiben einer vollständigen Datenbanksicherung in den Azure Blob Storage-Dienst</span><span class="sxs-lookup"><span data-stu-id="5ca5e-112">Lesson 3: Write a Full Database Backup to the Azure Blob Storage Service</span></span>](../tutorials/lesson-3-write-a-full-database-backup-to-the-windows-azure-blob-storage-service.md)  
 <span data-ttu-id="5ca5e-113">In dieser Lektion geben Sie eine T-SQL-Anweisung aus, um eine Sicherung der AdventureWorks2012-Datenbank in den Azure-BLOB-Speicherdienst zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="5ca5e-113">In this lesson, you issue a T-SQL statement to write a backup of the AdventureWorks2012 database to the Azure Blob storage service.</span></span>  
  
 [<span data-ttu-id="5ca5e-114">Lektion 4: Ausführen einer Wiederherstellung aus einer vollständigen Datenbanksicherung</span><span class="sxs-lookup"><span data-stu-id="5ca5e-114">Lesson 4: Perform a Restore From a Full Database Backup</span></span>](../tutorials/lesson-4-perform-a-restore-from-a-full-database-backup.md)  
 <span data-ttu-id="5ca5e-115">In dieser Lektion geben Sie eine T-SQL-Anweisung aus, um die in der vorherigen Lektion erstellte Datenbanksicherung wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="5ca5e-115">In this lesson, you issue a T-SQL statement to restore from the database backup you created in the previous lesson.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="5ca5e-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5ca5e-116">Requirements</span></span>  
 <span data-ttu-id="5ca5e-117">Um dieses Tutorial abzuschließen, müssen Sie mit den Sicherungs- und Wiederherstellungskonzepten in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] und der T-SQL-Syntax vertraut sein.</span><span class="sxs-lookup"><span data-stu-id="5ca5e-117">To complete this tutorial, you must be familiar with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backup and restore concepts and T-SQL syntax.</span></span> <span data-ttu-id="5ca5e-118">Damit Sie dieses Lernprogramm ausführen können, muss Ihr System die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="5ca5e-118">To use this tutorial, your system must meet the following requirements:</span></span>  
  
-   <span data-ttu-id="5ca5e-119">Eine Instanz von [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] und die AdventureWorks2012-Datenbank sind installiert.</span><span class="sxs-lookup"><span data-stu-id="5ca5e-119">An instance of [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)], and AdventureWorks2012 database installed.</span></span>  
  
     <span data-ttu-id="5ca5e-120">Die SQL Server-Instanz kann lokal oder auf einem virtuellen Azure-Computer gespeichert sein.</span><span class="sxs-lookup"><span data-stu-id="5ca5e-120">The SQL Server instance can be on-premises or in an Azure Virtual Machine.</span></span>  
  
     <span data-ttu-id="5ca5e-121">Anstelle von AdventureWorks2012 können Sie eine Benutzerdatenbank verwenden und die T-SQL-Syntax entsprechend ändern.</span><span class="sxs-lookup"><span data-stu-id="5ca5e-121">You can use a user database in place of AdventureWorks2012, and modify the tsql syntax accordingly.</span></span>  
  
-   <span data-ttu-id="5ca5e-122">Das zum Ausgeben von BACKUP- oder RESTORE-Befehlen verwendete Benutzerkonto sollte Mitglied der Datenbankrolle **db_backup operator** sein und über Berechtigungen zum **Ändern beliebiger Anmeldeinformationen** verfügen.</span><span class="sxs-lookup"><span data-stu-id="5ca5e-122">The user account that is used to issue BACKUP or RESTORE commands should be in the **db_backup operator** database role with **Alter any credential** permissions.</span></span>  
  
### <a name="additional-reading"></a><span data-ttu-id="5ca5e-123">Weiterführende Lektüre</span><span class="sxs-lookup"><span data-stu-id="5ca5e-123">Additional Reading</span></span>  
 <span data-ttu-id="5ca5e-124">Die folgenden Themen werden empfohlen, um das Verständnis der Konzepte und bewährten Verfahren zu verbessern, die Sie bei [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Sicherungen im Azure-BLOB-Speicherdienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="5ca5e-124">Following are some recommended reading to understand the concepts, best practices when using Azure Blob storage service for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backups.</span></span>  
  
1.  [<span data-ttu-id="5ca5e-125">SQL Server-Sicherung und -Wiederherstellung mit dem Microsoft Azure Blob Storage Service</span><span class="sxs-lookup"><span data-stu-id="5ca5e-125">SQL Server Backup and Restore with Azure Blob Storage Service</span></span>](backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md)  
  
2.  [<span data-ttu-id="5ca5e-126">SQL Server-Sicherung über URLs – bewährte Methoden und Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="5ca5e-126">SQL Server Backup to URL Best Practices and Troubleshooting</span></span>](backup-restore/sql-server-backup-to-url-best-practices-and-troubleshooting.md)  
  
  
