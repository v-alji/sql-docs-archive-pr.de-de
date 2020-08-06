---
title: Ziel Datenbankdateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferdatabasetask.destdbfiles.f1
ms.assetid: f6f90417-86fb-4b8c-a790-0b215c344ef6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0d0ab2c0ff39fc728afc17b59f0d4bae076e4022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621607"
---
# <a name="destination-database-files"></a><span data-ttu-id="4370c-102">Zieldatenbankdateien</span><span class="sxs-lookup"><span data-stu-id="4370c-102">Destination Database Files</span></span>
  <span data-ttu-id="4370c-103">Verwenden Sie das Dialogfeld **Zieldatenbankdateien** , um die Namen und Speicherorte der Datenbankdateien auf dem Zielserver anzuzeigen oder um für den Task "Datenbanken übertragen" eine Dateifreigabe auf dem Netzwerk anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4370c-103">Use the **Destination Database Files** dialog box to view or change the database file names and locations on the destination server, or to specify a network file location for the Transfer Database task.</span></span> <span data-ttu-id="4370c-104">Weitere Informationen zu diesem Task finden Sie unter [Datenbanken übertragen (Task)](control-flow/transfer-database-task.md).</span><span class="sxs-lookup"><span data-stu-id="4370c-104">For more information about this task, see [Transfer Database Task](control-flow/transfer-database-task.md).</span></span>  
  
 <span data-ttu-id="4370c-105">Um dieses Dialogfeld automatisch mit den Datenbankdateinamen und -speicherorten des Quellservers aufzufüllen, geben Sie zuerst auf der Seite **Datenbanken**des Dialogfelds **Editor für den Task 'Datenbanken übertragen'** die Parameter **SourceConnection** , **SourceDatabaseName** und **SourceDatabaseFiles** an.</span><span class="sxs-lookup"><span data-stu-id="4370c-105">To automatically populate this dialog box with the database file names and locations on the source server, specify the **SourceConnection**, **SourceDatabaseName**, and **SourceDatabaseFiles** first in the **Databases** page of the **Transfer Database Task Editor** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4370c-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="4370c-106">Options</span></span>  
 <span data-ttu-id="4370c-107">**Zieldatei**</span><span class="sxs-lookup"><span data-stu-id="4370c-107">**Destination File**</span></span>  
 <span data-ttu-id="4370c-108">Namen der übertragenen Datenbankdateien auf dem Zielserver.</span><span class="sxs-lookup"><span data-stu-id="4370c-108">Names of the transferred database files on the destination server.</span></span>  
  
 <span data-ttu-id="4370c-109">Geben Sie den Dateinamen ein, oder klicken Sie darauf, um ihn zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="4370c-109">Enter the file name, or click the file name to edit it.</span></span>  
  
 <span data-ttu-id="4370c-110">**Zielordner**</span><span class="sxs-lookup"><span data-stu-id="4370c-110">**Destination Folder**</span></span>  
 <span data-ttu-id="4370c-111">Der Ordner auf dem Zielserver, in den die Datenbankdateien übertragen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4370c-111">Folder on the destination server where the database files will be transferred to.</span></span>  
  
 <span data-ttu-id="4370c-112">Geben Sie den Ordnerpfad auf dem Zielserver ein, klicken Sie darauf, um ihn zu bearbeiten, oder klicken Sie auf die Schaltfläche zum Durchsuchen, um zu dem Ordner zu navigieren, in den Sie die Datenbankdateien übertragen wollen.</span><span class="sxs-lookup"><span data-stu-id="4370c-112">Enter the folder path, click the folder path to edit it, or click browse to locate the folder where you want to transfer the database files on the destination server.</span></span>  
  
 <span data-ttu-id="4370c-113">**Netzwerkdateifreigabe**</span><span class="sxs-lookup"><span data-stu-id="4370c-113">**Network File Share**</span></span>  
 <span data-ttu-id="4370c-114">Die Netzwerkdateifreigabe auf dem Zielserver, in die die Datenbankdateien übertragen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4370c-114">Network shared folder on the destination server where the database files will be transferred to.</span></span> <span data-ttu-id="4370c-115">Verwenden Sie **Netzwerkdateifreigabe** , wenn Sie eine Datenbank im Offlinemodus übertragen, indem Sie auf der Seite **Datenbanken** des Dialogfelds **Editor für den Task 'Datenbanken übertragen'** als **Methode** **DatabaseOffline** angeben.</span><span class="sxs-lookup"><span data-stu-id="4370c-115">Use **Network file share** when you transfer a database in offline mode by specifying **DatabaseOffline** for **Method** in the **Databases** page of the **Transfer Database Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="4370c-116">Geben Sie den Speicherort der Netzwerkdateifreigabe ein, oder klicken Sie auf die Schaltfläche zum Durchsuchen, um zu dieser Netzwerkdateifreigabe zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="4370c-116">Enter the network file share location, or click browse to locate the network file share location.</span></span>  
  
 <span data-ttu-id="4370c-117">Beim Übertragen einer Datenbank im Offlinemodus werden die Datenbankdateien zunächst in den als **Netzwerkdateifreigabe** angegebenen Speicherort kopiert, bevor sie in den als **Zielordner** gekennzeichneten Speicherort übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="4370c-117">When you transfer a database in offline mode, the database files are copied to the **Network file share** location before they are transferred to the **Destination folder** location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4370c-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4370c-118">See Also</span></span>  
 <span data-ttu-id="4370c-119">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="4370c-119">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="4370c-120">[Editor für den Task Datenbanken übertragen &#40;Seite Allgemein&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="4370c-120">[Transfer Database Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="4370c-121">Editor für den Task Datenbanken übertragen &#40;Seite Datenbanken&#41;</span><span class="sxs-lookup"><span data-stu-id="4370c-121">Transfer Database Task Editor &#40;Databases Page&#41;</span></span>](../../2014/integration-services/transfer-database-task-editor-databases-page.md)  
  
  
