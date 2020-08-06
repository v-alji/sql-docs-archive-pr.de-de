---
title: Skripterstellung für eine Sitzung für erweiterte Ereignisse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 80f9fdde-1f13-4292-a4fc-55da826be3b4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 11adc60ae7c7e0f8b8012d06f56c83874d3708ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616670"
---
# <a name="script-an-extended-event-session"></a><span data-ttu-id="4f8ea-102">Schreiben einer Sitzung für erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="4f8ea-102">Script an Extended Event Session</span></span>
  <span data-ttu-id="4f8ea-103">In diesem Thema wird beschrieben, wie ein Skript für eine Ereignissitzung geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="4f8ea-103">This topic describes how to script an event session.</span></span> <span data-ttu-id="4f8ea-104">Sie können die Ereignissitzung exportieren, ändern oder löschen, oder Sie können die Ereignissitzung wie folgt löschen und erstellen:</span><span class="sxs-lookup"><span data-stu-id="4f8ea-104">You can export, alter, or drop the event session, or drop and create the event session to the following:</span></span>  
  
-   <span data-ttu-id="4f8ea-105">**Neues Abfrage-Editor-Fenster**</span><span class="sxs-lookup"><span data-stu-id="4f8ea-105">**New Query Editor Window**</span></span>  
  
-   <span data-ttu-id="4f8ea-106">**Datei**</span><span class="sxs-lookup"><span data-stu-id="4f8ea-106">**File**</span></span>  
  
-   <span data-ttu-id="4f8ea-107">**Zwischenablage**</span><span class="sxs-lookup"><span data-stu-id="4f8ea-107">**Clipboard**</span></span>  
  
-   <span data-ttu-id="4f8ea-108">**Agent-Auftrag**</span><span class="sxs-lookup"><span data-stu-id="4f8ea-108">**Agent Job**</span></span>  
  
### <a name="to-script-an-existing-event-session"></a><span data-ttu-id="4f8ea-109">So schreiben Sie ein Skript für eine vorhandene Ereignissitzung</span><span class="sxs-lookup"><span data-stu-id="4f8ea-109">To script an existing event session</span></span>  
  
1.  <span data-ttu-id="4f8ea-110">Erweitern Sie im Objekt-Explorer den Knoten **Verwaltung** , und erweitern Sie dann **Erweiterte Ereignisse**.</span><span class="sxs-lookup"><span data-stu-id="4f8ea-110">In Object Explorer, expand the **Management** node, and then expand **Extended Events**.</span></span>  
  
2.  <span data-ttu-id="4f8ea-111">Klicken Sie mit der rechten Maustaste auf die Sitzung, für die Sie ein Skript schreiben möchten, zeigen Sie auf **Skript für Sitzung als**, zeigen Sie auf **CREATE in**, und wählen Sie dann aus, wo das Skript für die Sitzung geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="4f8ea-111">Right-click the session you want to script, point to **Script Session as**, point to **CREATE to**, and then select where you want to script the session.</span></span>  
  
### <a name="to-script-a-new-event-session"></a><span data-ttu-id="4f8ea-112">So schreiben Sie ein Skript für eine neue Ereignissitzung</span><span class="sxs-lookup"><span data-stu-id="4f8ea-112">To script a new event session</span></span>  
  
1.  <span data-ttu-id="4f8ea-113">Erweitern Sie im Objekt-Explorer den Knoten **Verwaltung** , und erweitern Sie dann **Erweiterte Ereignisse**.</span><span class="sxs-lookup"><span data-stu-id="4f8ea-113">In Object Explorer, expand the **Management** node, and then expand **Extended Events**.</span></span>  
  
2.  <span data-ttu-id="4f8ea-114">Klicken Sie mit der rechten Maustaste auf **Sitzungen**, und klicken Sie dann auf **Neue Sitzung**.</span><span class="sxs-lookup"><span data-stu-id="4f8ea-114">Right-click **Sessions**, and then click **New Session**.</span></span>  
  
3.  <span data-ttu-id="4f8ea-115">Erstellen Sie in der Benutzeroberfläche **Neue Sitzung** die Ereignissitzung, und wählen Sie aus der Dropdownliste **Skript** aus, wo das Skript für die Ereignissitzung geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="4f8ea-115">In the **New Session** UI, create the event session, and then select where you want to script the event session from the **Script** drop-down list.</span></span>  
  
### <a name="to-script-a-modified-event-session"></a><span data-ttu-id="4f8ea-116">So schreiben Sie ein Skript für eine geänderte Ereignissitzung</span><span class="sxs-lookup"><span data-stu-id="4f8ea-116">To script a modified event session</span></span>  
  
1.  <span data-ttu-id="4f8ea-117">Erweitern Sie im Objekt-Explorer den Knoten **Verwaltung** , und erweitern Sie dann **Erweiterte Ereignisse**.</span><span class="sxs-lookup"><span data-stu-id="4f8ea-117">In Object Explorer, expand the **Management** node, and then expand **Extended Events**.</span></span>  
  
2.  <span data-ttu-id="4f8ea-118">Klicken Sie mit der rechten Maustaste auf die Sitzung, den Sie ändern möchten, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="4f8ea-118">Right-click the session you want to modify, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="4f8ea-119">Ändern Sie die Ereignissitzung im Dialogfeld **Sitzungseigenschaften** , und wählen Sie aus der Dropdownliste **Skript** aus, wo das Skript für die geänderte Sitzung geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="4f8ea-119">In the **Session Properties** dialog box, modify the event session, and then select where you want to script the modified session from the **Script** drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f8ea-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4f8ea-120">See Also</span></span>  
 [<span data-ttu-id="4f8ea-121">Erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="4f8ea-121">Extended Events</span></span>](../relational-databases/extended-events/extended-events.md)  
  
  
