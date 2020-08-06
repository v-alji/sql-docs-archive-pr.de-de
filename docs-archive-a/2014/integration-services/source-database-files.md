---
title: Quelldaten Bank Dateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferdatabasetask.sourcedbfiles.f1
ms.assetid: 7dc6bfeb-37c1-45e8-a705-a87564922265
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 31f0c0e0c633ead0c093bdc8e1f20c9b8f23cc28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726022"
---
# <a name="source-database-files"></a><span data-ttu-id="9fe4c-102">Quelldatenbankdateien</span><span class="sxs-lookup"><span data-stu-id="9fe4c-102">Source database files</span></span>
  <span data-ttu-id="9fe4c-103">Verwenden Sie das Dialogfeld **Quelldatenbankdateien** , um die Namen und Speicherorte der Datenbankdateien auf dem Quellserver anzuzeigen, oder um für den Task "Datenbanken übertragen" eine Dateifreigabe auf dem Netzwerk anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9fe4c-103">Use the **Source Database Files** dialog box to view the database file names and locations on the source server, or to specify a network file share location for the Transfer Database task.</span></span> <span data-ttu-id="9fe4c-104">Weitere Informationen zu diesem Task finden Sie unter [Datenbanken übertragen (Task)](control-flow/transfer-database-task.md).</span><span class="sxs-lookup"><span data-stu-id="9fe4c-104">For more information about this task, see [Transfer Database Task](control-flow/transfer-database-task.md).</span></span>  
  
 <span data-ttu-id="9fe4c-105">Um dieses Dialogfeld mit den Datenbankdateinamen und -speicherorten des Quellservers aufzufüllen, geben Sie zuerst auf der Seite **Datenbanken** des Dialogfelds **Editor für den Task 'Datenbanken übertragen'** die Parameter **SourceConnection** und **SourceDatabaseName** an.</span><span class="sxs-lookup"><span data-stu-id="9fe4c-105">To populate this dialog box with the database file names and locations on the source server, specify the **SourceConnection** and **SourceDatabaseName** first in the **Databases** page of the **Transfer Database Task Editor** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9fe4c-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="9fe4c-106">Options</span></span>  
 <span data-ttu-id="9fe4c-107">**Quelldatei**</span><span class="sxs-lookup"><span data-stu-id="9fe4c-107">**Source File**</span></span>  
 <span data-ttu-id="9fe4c-108">Die Namen der zu übertragenden Datenbankdateien auf dem Quellserver.</span><span class="sxs-lookup"><span data-stu-id="9fe4c-108">Database file names on the source server that will be transferred.</span></span> <span data-ttu-id="9fe4c-109">**Quelldatei** ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="9fe4c-109">**Source File** is read only.</span></span>  
  
 <span data-ttu-id="9fe4c-110">**Quellordner**</span><span class="sxs-lookup"><span data-stu-id="9fe4c-110">**Source Folder**</span></span>  
 <span data-ttu-id="9fe4c-111">Der Ordner auf dem Quellserver, in dem sich die zu übertragenden Datenbankdateien befinden.</span><span class="sxs-lookup"><span data-stu-id="9fe4c-111">Folder on the source server where the database files to be transferred reside.</span></span> <span data-ttu-id="9fe4c-112">**Quellordner** ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="9fe4c-112">**Source Folder** is read only.</span></span>  
  
 <span data-ttu-id="9fe4c-113">**Netzwerkdateifreigabe**</span><span class="sxs-lookup"><span data-stu-id="9fe4c-113">**Network File Share**</span></span>  
 <span data-ttu-id="9fe4c-114">Der auf dem Netzwerk freigegebene Ordner auf dem Quellserver, aus dem die Datenbankdateien übertragen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9fe4c-114">Network shared folder on the source server from where the database files will be transferred.</span></span> <span data-ttu-id="9fe4c-115">Verwenden Sie **Netzwerkdateifreigabe** , wenn Sie eine Datenbank im Offlinemodus übertragen, indem Sie auf der Seite **Datenbanken** des Dialogfelds **Editor für den Task 'Datenbanken übertragen'** als **Methode** **DatabaseOffline** angeben.</span><span class="sxs-lookup"><span data-stu-id="9fe4c-115">Use **Network File Share** when you transfer a database in offline mode by specifying **DatabaseOffline** for **Method** in the **Databases** page of the **Transfer Database Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="9fe4c-116">Geben Sie den Speicherort der Netzwerkdateifreigabe ein, oder klicken Sie auf die Schaltfläche zum Durchsuchen **(…)** , um zu dieser Netzwerkdateifreigabe zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="9fe4c-116">Enter the network file share location, or click the browse button **(...)** to locate the network file share location.</span></span>  
  
 <span data-ttu-id="9fe4c-117">Beim Übertragen einer Datenbank im Offlinemodus werden die Datenbankdateien zunächst in den als **Netzwerkdateifreigabe** angegebenen Speicherort auf dem Quellserver kopiert, bevor sie auf den Zielserver übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="9fe4c-117">When you transfer a database in offline mode, the database files are copied to the **Network file share** location on the source server before they are transferred to the destination server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fe4c-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9fe4c-118">See Also</span></span>  
 <span data-ttu-id="9fe4c-119">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="9fe4c-119">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="9fe4c-120">[Editor für den Task Datenbanken übertragen &#40;Seite Allgemein&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="9fe4c-120">[Transfer Database Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="9fe4c-121">Editor für den Task Datenbanken übertragen &#40;Seite Datenbanken&#41;</span><span class="sxs-lookup"><span data-stu-id="9fe4c-121">Transfer Database Task Editor &#40;Databases Page&#41;</span></span>](../../2014/integration-services/transfer-database-task-editor-databases-page.md)  
  
  
