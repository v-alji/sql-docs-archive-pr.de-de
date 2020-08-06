---
title: 'Lektion 1: Erstellen von Azure Storage Objekten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 74edd1fd-ab00-46f7-9e29-7ba3f1a446c5
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: d46c6d22ffd92dbf8035bff140960af8ef56122d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609598"
---
# <a name="lesson-1-create-azure-storage-objects"></a><span data-ttu-id="25c3d-102">Lektion 1: Erstellen von Azure Storage-Objekten</span><span class="sxs-lookup"><span data-stu-id="25c3d-102">Lesson 1: Create Azure Storage Objects</span></span>
  <span data-ttu-id="25c3d-103">Bevor Sie [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Sicherungen im Cloudspeicher erstellen, müssen Sie zunächst ein Speicherkonto und dann einen BLOB-Container erstellen.</span><span class="sxs-lookup"><span data-stu-id="25c3d-103">Before you can create [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backups on cloud storage, you must first create a storage account, and then a blob container.</span></span> <span data-ttu-id="25c3d-104">Lektion 1 führt Sie durch die Schritte zum Anmelden beim Azure-Verwaltungsportal und zum Erstellen eines Speicher Kontos und eines BLOB-Containers.</span><span class="sxs-lookup"><span data-stu-id="25c3d-104">Lesson 1 walks you through the steps of Logging into the Azure Management Portal, creating a storage account and a blob container.</span></span>  
  
## <a name="create-a-storage-account"></a><span data-ttu-id="25c3d-105">Erstellen eines Speicherkontos</span><span class="sxs-lookup"><span data-stu-id="25c3d-105">Create a storage Account</span></span>  
 <span data-ttu-id="25c3d-106">Führen Sie die folgenden Schritte aus, um ein Speicherkonto aus dem Azure-Verwaltungsportal zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="25c3d-106">To create a storage account from the Azure Management Portal, use the following steps:</span></span>  
  
1.  <span data-ttu-id="25c3d-107">Melden Sie sich unter Ihrem Konto beim Azure-Verwaltungsportal an.</span><span class="sxs-lookup"><span data-stu-id="25c3d-107">Log in to the Azure Management Portal using your account.</span></span> <span data-ttu-id="25c3d-108">Wenn Sie nicht über ein Azure-Konto verfügen, besuchen Sie die [Kostenlose Azure-Testversion für 3 Monate](https://go.microsoft.com/fwlink/?LinkId=271927).</span><span class="sxs-lookup"><span data-stu-id="25c3d-108">If you do not have an Azure account, [visit Azure 3-Month free trial](https://go.microsoft.com/fwlink/?LinkId=271927).</span></span>  
  
     <span data-ttu-id="25c3d-109">![Azure-Anmeldebildschirm](../../2014/tutorials/media/windowazurelogin-backuptocloud.gif "Azure-Anmeldebildschirm")</span><span class="sxs-lookup"><span data-stu-id="25c3d-109">![Azure Login Screen](../../2014/tutorials/media/windowazurelogin-backuptocloud.gif "Azure Login Screen")</span></span>  
  
2.  <span data-ttu-id="25c3d-110">Führen Sie die [hier](https://go.microsoft.com/fwlink/?LinkId=271926)beschriebenen schrittweisen Anweisungen aus, um ein Speicherkonto zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="25c3d-110">Use the step by step instructions detailed [here](https://go.microsoft.com/fwlink/?LinkId=271926), to create a storage account.</span></span>  
  
3.  <span data-ttu-id="25c3d-111">Navigieren Sie zu dem Speicherkonto, das Sie im vorherigen Schritt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="25c3d-111">Browse to the storage account you created in previous step.</span></span> <span data-ttu-id="25c3d-112">Klicken Sie unten in der Mitte der Webseite auf **Schlüssel verwalten**.</span><span class="sxs-lookup"><span data-stu-id="25c3d-112">From the bottom center of the web page, click **MANAGE KEYS**.</span></span> <span data-ttu-id="25c3d-113">Die Kontoinformationen werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="25c3d-113">The account information is displayed.</span></span> <span data-ttu-id="25c3d-114">Kopieren Sie den Speicherkontonamen und die Zugriffsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="25c3d-114">Copy the storage account name, and the Access Keys.</span></span> <span data-ttu-id="25c3d-115">Diese Informationen sind erforderlich, um gespeicherte SQL-Anmeldeinformation zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="25c3d-115">This information is required to create SQL Stored Credentials.</span></span> [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="25c3d-116">verwendet diese Informationen, um auf das Speicherkonto zuzugreifen und Sicherungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="25c3d-116">uses this information to access the storage account and create backups.</span></span>  
  
     <span data-ttu-id="25c3d-117">![Screenshot der Azure Storage Kontoschlüssel](../../2014/tutorials/media/manageaccesskeys-backuptocloud.gif "Screenshot der Azure Storage Kontoschlüssel")</span><span class="sxs-lookup"><span data-stu-id="25c3d-117">![Screen shot of Azure Storage Account Keys](../../2014/tutorials/media/manageaccesskeys-backuptocloud.gif "Screen shot of Azure Storage Account Keys")</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="25c3d-118">Sie können ein Speicherkonto mithilfe von REST-APIs auch programmgesteuert erstellen.</span><span class="sxs-lookup"><span data-stu-id="25c3d-118">You can also create a storage account programmatically using REST APIs.</span></span> <span data-ttu-id="25c3d-119">Weitere Informationen finden Sie unter [Erstellen eines Speicher Kontos](https://go.microsoft.com/fwlink/?LinkId=271928).</span><span class="sxs-lookup"><span data-stu-id="25c3d-119">For more information, see [Create Storage Account](https://go.microsoft.com/fwlink/?LinkId=271928).</span></span>  
  
### <a name="create-a-blob-container"></a><span data-ttu-id="25c3d-120">Erstellen eines BLOB-Containers</span><span class="sxs-lookup"><span data-stu-id="25c3d-120">Create a Blob Container</span></span>  
 <span data-ttu-id="25c3d-121">Ein Container stellt eine Gruppierung eines Blob-Satzes bereit.</span><span class="sxs-lookup"><span data-stu-id="25c3d-121">A container provides a grouping of a set of blobs.</span></span> <span data-ttu-id="25c3d-122">Alle BLOBs müssen sich in einem Container befinden.</span><span class="sxs-lookup"><span data-stu-id="25c3d-122">All blobs must be in a container.</span></span> <span data-ttu-id="25c3d-123">Die Anzahl der Container für ein Konto ist unbegrenzt, muss jedoch mindestens 1 betragen.</span><span class="sxs-lookup"><span data-stu-id="25c3d-123">An account can contain an unlimited number of containers, but must have at least one container.</span></span> <span data-ttu-id="25c3d-124">In einem Container kann eine unbegrenzte Anzahl von BLOBs gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="25c3d-124">A container can store an unlimited number of blobs.</span></span>  
  
 <span data-ttu-id="25c3d-125">Führen Sie die folgenden Schritte aus, um einen Container zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="25c3d-125">To create a Container, use the following steps:</span></span>  
  
1.  <span data-ttu-id="25c3d-126">Wählen Sie das Speicherkonto aus, klicken Sie auf die Registerkarte **Container** , und klicken Sie am unteren Bildschirmrand auf **Container hinzufügen** , um ein neues Dialogfeld zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="25c3d-126">Select the storage account, click the **CONTAINERS** tab and click **ADD CONTAINER** at the bottom of the screen which opens a new dialog box.</span></span>  
  
     <span data-ttu-id="25c3d-127">![Erstellen eines Containers im Verwaltungsportal](../../2014/tutorials/media/backuptocloud.gif "Erstellen eines Containers im Verwaltungsportal")</span><span class="sxs-lookup"><span data-stu-id="25c3d-127">![Creating a Container in the Management Portal](../../2014/tutorials/media/backuptocloud.gif "Creating a Container in the Management Portal")</span></span>  
  
2.  <span data-ttu-id="25c3d-128">Geben Sie den Namen für den Container ein.</span><span class="sxs-lookup"><span data-stu-id="25c3d-128">Enter the name for the container.</span></span> <span data-ttu-id="25c3d-129">Notieren Sie den eingegebenen Containernamen.</span><span class="sxs-lookup"><span data-stu-id="25c3d-129">Make a note of the container name you specified.</span></span> <span data-ttu-id="25c3d-130">Diese Informationen werden in der URL (Pfad der Sicherungsdatei) der T-SQL-Anweisungen in Lektion 3 und 4 verwendet.</span><span class="sxs-lookup"><span data-stu-id="25c3d-130">This information is used in the URL (path to backup file) in the T-SQL statements in lesson 3 and 4.</span></span>  
  
3.  <span data-ttu-id="25c3d-131">Wählen Sie privat als **Zugriffstyp**aus.</span><span class="sxs-lookup"><span data-stu-id="25c3d-131">Select Private for **Access Type**.</span></span> <span data-ttu-id="25c3d-132">Es wird empfohlen, zum Sichern der Sicherungsdateien private Container zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="25c3d-132">We recommend creating private containers for securing your backup files.</span></span>  
  
     <span data-ttu-id="25c3d-133">![Erstellen eines neuen BLOB-Containers](../../2014/tutorials/media/backuptocloud-newblobcontainer.gif "Erstellen eines neuen BLOB-Containers")</span><span class="sxs-lookup"><span data-stu-id="25c3d-133">![Creating a new blob container](../../2014/tutorials/media/backuptocloud-newblobcontainer.gif "Creating a new blob container")</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="25c3d-134">Sowohl Sicherungs- als auch Wiederherstellungsvorgänge in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] erfordern eine Authentifizierung beim Speicherkonto. Dies gilt auch, wenn Sie einen öffentlichen Container erstellen.</span><span class="sxs-lookup"><span data-stu-id="25c3d-134">Authentication to the storage account is required for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backup and restore even if you choose to create a public container.</span></span>  
    >   
    >  <span data-ttu-id="25c3d-135">Container können mithilfe der REST-APIs auch programmgesteuert erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="25c3d-135">You can also create a container programmatically using REST APIs.</span></span> <span data-ttu-id="25c3d-136">Weitere Informationen finden Sie unter [Create Container](https://go.microsoft.com/fwlink/?LinkId=271946).</span><span class="sxs-lookup"><span data-stu-id="25c3d-136">For more information, see [Create Container](https://go.microsoft.com/fwlink/?LinkId=271946).</span></span>  
  
### <a name="next-lesson"></a><span data-ttu-id="25c3d-137">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="25c3d-137">Next Lesson</span></span>  
 <span data-ttu-id="25c3d-138">[Lektion 2: Erstellen eines SQL Server](../../2014/tutorials/lesson-2-create-a-sql-server-credential.md)Anmelde Informationen.</span><span class="sxs-lookup"><span data-stu-id="25c3d-138">[Lesson 2: Create a SQL Server Credential](../../2014/tutorials/lesson-2-create-a-sql-server-credential.md).</span></span>  
  
  
