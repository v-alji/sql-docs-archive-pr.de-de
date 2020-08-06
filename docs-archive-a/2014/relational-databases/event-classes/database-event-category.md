---
title: Datenbank (Ereigniskategorie) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- event classes [SQL Server], Database event category
- Database event category [SQL Server]
- SQL Server event classes, Database event category
ms.assetid: b61af738-f144-4992-b0b2-d44cb7240991
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2860e1434611393c941a639280343f736073c709
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619837"
---
# <a name="database-event-category"></a><span data-ttu-id="51ff1-102">Datenbank (Ereigniskategorie)</span><span class="sxs-lookup"><span data-stu-id="51ff1-102">Database Event Category</span></span>
  <span data-ttu-id="51ff1-103">Die **Datenbank** -Ereigniskategorie enthält Ereignisklassen zum Überwachen von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="51ff1-103">The **Database** event category contains event classes to monitor the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="51ff1-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="51ff1-104">In This Section</span></span>  
  
|<span data-ttu-id="51ff1-105">Thema</span><span class="sxs-lookup"><span data-stu-id="51ff1-105">Topic</span></span>|<span data-ttu-id="51ff1-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="51ff1-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="51ff1-107">Data File Auto Grow-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="51ff1-107">Data File Auto Grow Event Class</span></span>](data-file-auto-grow-event-class.md)|<span data-ttu-id="51ff1-108">Zeigt an, dass die Datendatei automatisch vergrößert wurde.</span><span class="sxs-lookup"><span data-stu-id="51ff1-108">Indicates that the data file grew automatically.</span></span> <span data-ttu-id="51ff1-109">Dieses Ereignis wird nicht ausgelöst, wenn die Datendatei explizit mit ALTER DATABASE vergrößert wird.</span><span class="sxs-lookup"><span data-stu-id="51ff1-109">This event is not triggered if the data file is grown explicitly through ALTER DATABASE.</span></span>|  
|[<span data-ttu-id="51ff1-110">Data File Auto Shrink-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="51ff1-110">Data File Auto Shrink Event Class</span></span>](data-file-auto-shrink-event-class.md)|<span data-ttu-id="51ff1-111">Zeigt an, dass die Datendatei verkleinert wurde.</span><span class="sxs-lookup"><span data-stu-id="51ff1-111">Indicates that the data file has been shrunk.</span></span>|  
|[<span data-ttu-id="51ff1-112">Database Mirroring:Connection-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="51ff1-112">Database Mirroring Connection Event Class</span></span>](database-mirroring-connection-event-class.md)|<span data-ttu-id="51ff1-113">Ein Ereignis, das den Status einer Transportverbindung für die Datenbankspiegelung meldet.</span><span class="sxs-lookup"><span data-stu-id="51ff1-113">An event generated to report the status of a transport connection for database mirroring.</span></span>|  
|[<span data-ttu-id="51ff1-114">Database Mirroring State Change-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="51ff1-114">Database Mirroring State Change Event Class</span></span>](database-mirroring-state-change-event-class.md)|<span data-ttu-id="51ff1-115">Zeigt an, wenn sich der Status einer gespiegelten Datenbank ändert.</span><span class="sxs-lookup"><span data-stu-id="51ff1-115">Indicates when the state of a mirrored database changes.</span></span>|  
|[<span data-ttu-id="51ff1-116">Database Suspect Data Page-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="51ff1-116">Database Suspect Data Page Event Class</span></span>](database-suspect-data-page-event-class.md)|<span data-ttu-id="51ff1-117">Gibt an, wenn der Tabelle **suspect_pages** in der **msdb** -Datenbank eine Seite hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="51ff1-117">Indicates when a page is added to the **suspect_pages** table in the **msdb** database.</span></span>|  
|[<span data-ttu-id="51ff1-118">Log File Auto Grow-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="51ff1-118">Log File Auto Grow Event Class</span></span>](log-file-auto-grow-event-class.md)|<span data-ttu-id="51ff1-119">Zeigt an, dass die Protokolldatei automatisch vergrößert wurde.</span><span class="sxs-lookup"><span data-stu-id="51ff1-119">Indicates that the log file grew automatically.</span></span> <span data-ttu-id="51ff1-120">Dieses Ereignis wird nicht ausgelöst, wenn die Protokolldatei explizit mit ALTER DATABASE vergrößert wird.</span><span class="sxs-lookup"><span data-stu-id="51ff1-120">This event is not triggered if the log file is grown explicitly through ALTER DATABASE.</span></span>|  
|[<span data-ttu-id="51ff1-121">Log File Auto Shrink-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="51ff1-121">Log File Auto Shrink Event Class</span></span>](log-file-auto-shrink-event-class.md)|<span data-ttu-id="51ff1-122">Zeigt an, dass die Protokolldatei automatisch vergrößert wurde.</span><span class="sxs-lookup"><span data-stu-id="51ff1-122">Indicates that the log file grew automatically.</span></span> <span data-ttu-id="51ff1-123">Dieses Ereignis wird nicht ausgelöst, wenn die Protokolldatei explizit mit ALTER DATABASE verkleinert wird.</span><span class="sxs-lookup"><span data-stu-id="51ff1-123">This event is not triggered if the log file shrinks explicitly through ALTER DATABASE.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="51ff1-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="51ff1-124">See Also</span></span>  
 [<span data-ttu-id="51ff1-125">Erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="51ff1-125">Extended Events</span></span>](../extended-events/extended-events.md)  
  
  
