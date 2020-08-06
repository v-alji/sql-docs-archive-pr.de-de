---
title: 'Tutorial: SQL Server von Datendateien in Azure Storage Service | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: e69be67d-da1c-41ae-8c9a-6b12c8c2fb61
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 21a0fc11706a0c5ee35cf71e1af69f2927adc9db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622504"
---
# <a name="tutorial-sql-server-data-files-in-azure-storage-service"></a><span data-ttu-id="c6d9b-102">Tutorial: SQL Server-Datendateien im Azure Storage-Dienst</span><span class="sxs-lookup"><span data-stu-id="c6d9b-102">Tutorial: SQL Server Data Files in Azure Storage service</span></span>
  <span data-ttu-id="c6d9b-103">Willkommen beim Tutorial SQL Server Datendateien in Azure Storage Dienst.</span><span class="sxs-lookup"><span data-stu-id="c6d9b-103">Welcome to the  SQL Server Data Files in Azure Storage Service tutorial.</span></span> <span data-ttu-id="c6d9b-104">Dieses Tutorial hilft Ihnen, zu verstehen, wie Sie SQL Server-Datendateien direkt im Azure Blob Storage-Dienst speichern.</span><span class="sxs-lookup"><span data-stu-id="c6d9b-104">This tutorial helps you understand how to store SQL Server data files in the Azure Blob storage service directly.</span></span>  
  
 <span data-ttu-id="c6d9b-105">Die Unterstützung der SQL Server Integration für den Azure BLOB Storage-Dienst ist eine SQL Server 2014-Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="c6d9b-105">SQL Server integration support for the Azure Blob storage service is a SQL Server 2014 enhancement.</span></span> <span data-ttu-id="c6d9b-106">Eine Übersicht über die Funktionen und Vorteile der Verwendung dieser Funktion finden Sie unter [SQL Server von Datendateien in Azure](databases/sql-server-data-files-in-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="c6d9b-106">For an overview of the functionality and benefits of using this functionality, see [SQL Server Data Files in Azure](databases/sql-server-data-files-in-microsoft-azure.md).</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="c6d9b-107">Lernziele</span><span class="sxs-lookup"><span data-stu-id="c6d9b-107">What you will learn</span></span>  
 <span data-ttu-id="c6d9b-108">In diesem Tutorial wird gezeigt, wie Sie SQL Server Datendateien in mehreren Lektionen in Azure Storage Dienst speichern.</span><span class="sxs-lookup"><span data-stu-id="c6d9b-108">This tutorial shows you how to store SQL Server Data Files in Azure Storage service in multiple lessons.</span></span> <span data-ttu-id="c6d9b-109">Jede Lektion behandelt eine bestimmte Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="c6d9b-109">Each lesson is focused on a specific task.</span></span> <span data-ttu-id="c6d9b-110">Zunächst erfahren Sie, wie Sie ein Speicherkonto und einen Container in Azure erstellen.</span><span class="sxs-lookup"><span data-stu-id="c6d9b-110">First, you will learn how to create a storage account and a container in Azure.</span></span> <span data-ttu-id="c6d9b-111">Anschließend erfahren Sie, wie Sie eine SQL Server Anmelde Informationen erstellen, damit Sie SQL Server in Azure Storage integrieren können.</span><span class="sxs-lookup"><span data-stu-id="c6d9b-111">Then, you will learn how to create a SQL Server credential to be able to integrate SQL Server with Azure Storage.</span></span> <span data-ttu-id="c6d9b-112">Anschließend erstellen Sie eine Datenbank direkt in Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="c6d9b-112">Then, you will create a database in Azure Storage directly.</span></span> <span data-ttu-id="c6d9b-113">Außerdem werden im Lernprogramm Verschlüsselungs-, Migrations- sowie Sicherungs- und Wiederherstellungsszenarien behandelt.</span><span class="sxs-lookup"><span data-stu-id="c6d9b-113">In addition, the tutorial will demonstrate encryption, migration, and backup and restore scenarios.</span></span>  
  
 <span data-ttu-id="c6d9b-114">Dieses Lernprogramm ist in neun Lektionen aufgeteilt:</span><span class="sxs-lookup"><span data-stu-id="c6d9b-114">This tutorial is divided into nine lessons:</span></span>  
  
 <span data-ttu-id="c6d9b-115">**[Lektion 1: Erstellen eines Azure Storage-Kontos und -Containers](../tutorials/lesson-1-create-windows-azure-storage-account-and-container.md)**</span><span class="sxs-lookup"><span data-stu-id="c6d9b-115">**[Lesson 1: Create Azure Storage Account and Container](../tutorials/lesson-1-create-windows-azure-storage-account-and-container.md)**</span></span>  
 <span data-ttu-id="c6d9b-116">In dieser Lektion erstellen Sie ein Azure Storage Konto und einen Container.</span><span class="sxs-lookup"><span data-stu-id="c6d9b-116">In this lesson, you create an Azure Storage account and a container.</span></span>  
  
 <span data-ttu-id="c6d9b-117">**[Lektion 2. Erstellen einer Richtlinie für einen Container und Generieren einer Shared Access Signature &#40;SAS-&#41; Schlüssel](lesson-1-create-stored-access-policy-and-shared-access-signature.md)**</span><span class="sxs-lookup"><span data-stu-id="c6d9b-117">**[Lesson 2. Create a policy on container and generate a Shared Access Signature &#40;SAS&#41; key](lesson-1-create-stored-access-policy-and-shared-access-signature.md)**</span></span>  
 <span data-ttu-id="c6d9b-118">In dieser Lektion erstellen Sie eine Richtlinie für den BLOB-Container und generieren zusätzlich eine SAS (Shared Access Signature, Signatur für gemeinsamen Zugriff).</span><span class="sxs-lookup"><span data-stu-id="c6d9b-118">In this lesson, you create a policy on the Blob container and also generate a shared access signature.</span></span>  
  
 <span data-ttu-id="c6d9b-119">**[Lektion 3: Erstellen von SQL Server-Anmeldeinformationen](lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)**</span><span class="sxs-lookup"><span data-stu-id="c6d9b-119">**[Lesson 3: Create a SQL Server Credential](lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)**</span></span>  
 <span data-ttu-id="c6d9b-120">In dieser Lektion erstellen Sie Anmeldeinformationen, um die Sicherheitsinformationen für den Zugriff auf das Azure-Speicherkonto zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c6d9b-120">In this lesson, you create a Credential to store security information used to access the Azure storage account.</span></span>  
  
 <span data-ttu-id="c6d9b-121">**[Lektion 4: Erstellen einer Datenbank in Azure Storage](../relational-databases/lesson-3-database-backup-to-url.md)**</span><span class="sxs-lookup"><span data-stu-id="c6d9b-121">**[Lesson 4: Create a database in Azure Storage](../relational-databases/lesson-3-database-backup-to-url.md)**</span></span>  
 <span data-ttu-id="c6d9b-122">In dieser Lektion erstellen Sie eine Datenbank in Azure Storage mithilfe der Option Create Database filename.</span><span class="sxs-lookup"><span data-stu-id="c6d9b-122">In this lesson, you create a database in Azure Storage using CREATE Database FILENAME option.</span></span>  
  
 <span data-ttu-id="c6d9b-123">**[Lektion 5. &#40;optional,&#41; Ihre Datenbank mithilfe von TDE zu verschlüsseln.](../relational-databases/lesson-4-restore-database-to-virtual-machine-from-url.md)**</span><span class="sxs-lookup"><span data-stu-id="c6d9b-123">**[Lesson 5. &#40;Optional&#41; Encrypt your database using TDE](../relational-databases/lesson-4-restore-database-to-virtual-machine-from-url.md)**</span></span>  
 <span data-ttu-id="c6d9b-124">In dieser Lektion verschlüsseln Sie die Datenbank mithilfe einer transparenten Datenverschlüsselung (TDE) und eines Serverzertifikats.</span><span class="sxs-lookup"><span data-stu-id="c6d9b-124">In this lesson, you encrypt your database by using a transparent data encryption (TDE) and a server certificate.</span></span>  
  
 <span data-ttu-id="c6d9b-125">**[Lektion 6: Migrieren einer Datenbank von einem lokalen Quellcomputer zu einem Zielcomputer in Azure](lesson-5-backup-database-using-file-snapshot-backup.md)**</span><span class="sxs-lookup"><span data-stu-id="c6d9b-125">**[Lesson 6: Migrate a database from a source machine on-premises to a destination machine in Azure](lesson-5-backup-database-using-file-snapshot-backup.md)**</span></span>  
 <span data-ttu-id="c6d9b-126">In dieser Lektion migrieren Sie eine Datenbank von einem lokalen Standort zu einem virtuellen Computer in Azure mithilfe der Option Create Database for Attach.</span><span class="sxs-lookup"><span data-stu-id="c6d9b-126">In this lesson, you migrate a database from on-premises to a virtual machine in Azure using CREATE DATABASE FOR ATTACH option.</span></span>  
  
 <span data-ttu-id="c6d9b-127">**[Lektion 7: Verschieben von Datendateien nach Azure Storage](../relational-databases/lesson-6-generate-activity-and-backup-log-using-file-snapshot-backup.md)**</span><span class="sxs-lookup"><span data-stu-id="c6d9b-127">**[Lesson 7: Move your data files to Azure Storage](../relational-databases/lesson-6-generate-activity-and-backup-log-using-file-snapshot-backup.md)**</span></span>  
 <span data-ttu-id="c6d9b-128">In dieser Lektion verschieben Sie die Datendateien mithilfe der ALTER DATABASE-Anweisung in Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="c6d9b-128">In this lesson, you move your data files to Azure Storage using ALTER DATABASE statement.</span></span>  
  
 <span data-ttu-id="c6d9b-129">**[Lektion 8. Wiederherstellen einer Datenbank auf Azure Storage](../relational-databases/lesson-7-restore-a-database-to-a-point-in-time.md)**</span><span class="sxs-lookup"><span data-stu-id="c6d9b-129">**[Lesson 8. Restore a database to Azure Storage](../relational-databases/lesson-7-restore-a-database-to-a-point-in-time.md)**</span></span>  
 <span data-ttu-id="c6d9b-130">In dieser Lektion stellen Sie eine Datenbank mithilfe der Move-Option RESTORE DATABASE auf Azure Storage wieder her.</span><span class="sxs-lookup"><span data-stu-id="c6d9b-130">In this lesson, you restore a database to Azure Storage using RESTORE Database MOVE option.</span></span>  
  
 <span data-ttu-id="c6d9b-131">**[Lektion 9. Wiederherstellen einer Datenbank aus Azure Storage](lesson-8-restore-as-new-database-from-log-backup.md)**</span><span class="sxs-lookup"><span data-stu-id="c6d9b-131">**[Lesson 9. Restore a database from Azure Storage](lesson-8-restore-as-new-database-from-log-backup.md)**</span></span>  
 <span data-ttu-id="c6d9b-132">In dieser Lektion stellen Sie eine Datenbank aus Azure Storage mithilfe der Option zum Verschieben von Datenbanken wieder her.</span><span class="sxs-lookup"><span data-stu-id="c6d9b-132">In this lesson, you restore a database from Azure Storage using RESTORE Database MOVE option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6d9b-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c6d9b-133">See Also</span></span>  
 [<span data-ttu-id="c6d9b-134">SQL Server-Datendateien in Azure</span><span class="sxs-lookup"><span data-stu-id="c6d9b-134">SQL Server Data Files in Azure</span></span>](databases/sql-server-data-files-in-microsoft-azure.md)  
  
  
