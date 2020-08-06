---
title: Cursor-Ereigniskategorie | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Cursors event category [SQL Server]
- event classes [SQL Server], Cursors event category
- SQL Server event classes, Cursors event category
ms.assetid: 752e0695-b464-4720-93be-5b9b53b7ab21
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3b31ff8ccb9c662a2f0ea54adc9cd2d466103be2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699555"
---
# <a name="cursors-event-category"></a><span data-ttu-id="f5e1c-102">Cursor-Ereigniskategorie</span><span class="sxs-lookup"><span data-stu-id="f5e1c-102">Cursors Event Category</span></span>
  <span data-ttu-id="f5e1c-103">Die Ereigniskategorie **Cursors** enthält Ereignisklassen, die zum Überwachen des Verhaltens von Cursor verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f5e1c-103">The **Cursors** event category contains event classes that are used to monitor the behavior of cursors.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f5e1c-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f5e1c-104">In This Section</span></span>  
  
|<span data-ttu-id="f5e1c-105">Thema</span><span class="sxs-lookup"><span data-stu-id="f5e1c-105">Topic</span></span>|<span data-ttu-id="f5e1c-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f5e1c-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="f5e1c-107">CursorClose-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="f5e1c-107">CursorClose Event Class</span></span>](cursorclose-event-class.md)|<span data-ttu-id="f5e1c-108">Beschreibt Ereignisse, die bei API-Cursorn (Application Programming Interface, Anwendungsprogrammierschnittstelle) das Schließen des Cursors bewirken.</span><span class="sxs-lookup"><span data-stu-id="f5e1c-108">Describes cursor close events that occur in application programming interface (API) cursors.</span></span>|  
|[<span data-ttu-id="f5e1c-109">CursorExecute (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="f5e1c-109">CursorExecute Event Class</span></span>](cursorexecute-event-class.md)|<span data-ttu-id="f5e1c-110">Beschreibt Ereignisse, die bei API-Cursorn das Ausführen des Cursors bewirken.</span><span class="sxs-lookup"><span data-stu-id="f5e1c-110">Describes cursor execute events that occur in API cursors.</span></span>|  
|[<span data-ttu-id="f5e1c-111">CursorImplicitConversion (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="f5e1c-111">CursorImplicitConversion Event Class</span></span>](cursorimplicitconversion-event-class.md)|<span data-ttu-id="f5e1c-112">Beschreibt Ereignisse, die bei API- oder [!INCLUDE[tsql](../../includes/tsql-md.md)] -Cursorn eine implizite Cursorkonvertierung bewirken.</span><span class="sxs-lookup"><span data-stu-id="f5e1c-112">Describes cursor implicit conversion events that occur in API or [!INCLUDE[tsql](../../includes/tsql-md.md)] cursors.</span></span>|  
|[<span data-ttu-id="f5e1c-113">CursorOpen-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="f5e1c-113">CursorOpen Event Class</span></span>](cursoropen-event-class.md)|<span data-ttu-id="f5e1c-114">Beschreibt Ereignisse, die bei API-Cursorn das Öffnen des Cursors bewirken.</span><span class="sxs-lookup"><span data-stu-id="f5e1c-114">Describes cursor open events that occur in API cursors.</span></span>|  
|[<span data-ttu-id="f5e1c-115">CursorPrepare (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="f5e1c-115">CursorPrepare Event Class</span></span>](cursorprepare-event-class.md)|<span data-ttu-id="f5e1c-116">Beschreibt Ereignisse, die bei API-Cursorn das Vorbereiten des Cursors bewirken.</span><span class="sxs-lookup"><span data-stu-id="f5e1c-116">Describes cursor prepare events that occur in API cursors.</span></span>|  
|[<span data-ttu-id="f5e1c-117">CursorRecompile (Ereignisklasse)</span><span class="sxs-lookup"><span data-stu-id="f5e1c-117">CursorRecompile Event Class</span></span>](cursorrecompile-event-class.md)|<span data-ttu-id="f5e1c-118">Beschreibt Ereignisse, die bei API-Cursorn das erneute Kompilieren des Cursors bewirken.</span><span class="sxs-lookup"><span data-stu-id="f5e1c-118">Describes cursor recompile events that occur in API cursors.</span></span>|  
|[<span data-ttu-id="f5e1c-119">CursorUnprepare-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="f5e1c-119">CursorUnprepare Event Class</span></span>](cursorunprepare-event-class.md)|<span data-ttu-id="f5e1c-120">Beschreibt Ereignisse, die bei API-Cursorn die Aufhebung der Cursorvorbereitung bewirken.</span><span class="sxs-lookup"><span data-stu-id="f5e1c-120">Describes cursor unprepare events that occur in API cursors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5e1c-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f5e1c-121">See Also</span></span>  
 [<span data-ttu-id="f5e1c-122">Erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="f5e1c-122">Extended Events</span></span>](../extended-events/extended-events.md)  
  
  
