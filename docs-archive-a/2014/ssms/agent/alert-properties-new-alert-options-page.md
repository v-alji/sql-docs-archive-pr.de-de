---
title: 'Warnungs Eigenschaften: neue Warnung (Seite "Optionen") | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.alert.options.f1
ms.assetid: 6e4f41aa-832d-46ba-b6b5-cf1d3b15d33f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a1507372aa1516c2a88b8682faa77a7d57e58f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722226"
---
# <a name="alert-properties-new-alert-options-page"></a><span data-ttu-id="6afbb-102">Eigenschaften von Warnungen: Neue Warnung (Seite „Optionen“)</span><span class="sxs-lookup"><span data-stu-id="6afbb-102">Alert Properties: New Alert (Options Page)</span></span>
  <span data-ttu-id="6afbb-103">Mithilfe dieser Seite können Sie Optionen für-Agent-Warnungen anzeigen und ändern [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6afbb-103">Use this page to view and modify options for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6afbb-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="6afbb-104">Options</span></span>  
 <span data-ttu-id="6afbb-105">**E**</span><span class="sxs-lookup"><span data-stu-id="6afbb-105">**E-mail**</span></span>  
 <span data-ttu-id="6afbb-106">Schließt Fehlertext des Ereignisses ggf. in E-Mail-Benachrichtigungen ein.</span><span class="sxs-lookup"><span data-stu-id="6afbb-106">Include error text from the event, if any, in e-mail notifications.</span></span>  
  
 <span data-ttu-id="6afbb-107">**Pager**</span><span class="sxs-lookup"><span data-stu-id="6afbb-107">**Pager**</span></span>  
 <span data-ttu-id="6afbb-108">Schließt Fehlertext des Ereignisses ggf. in Pagerbenachrichtigungen ein.</span><span class="sxs-lookup"><span data-stu-id="6afbb-108">Include error text from the event, if any, in pager notifications.</span></span>  
  
 <span data-ttu-id="6afbb-109">**NET SEND**</span><span class="sxs-lookup"><span data-stu-id="6afbb-109">**Net send**</span></span>  
 <span data-ttu-id="6afbb-110">Schließt Fehlertext des Ereignisses ggf. in NET SEND-Benachrichtigungen ein.</span><span class="sxs-lookup"><span data-stu-id="6afbb-110">Include error text from the event, if any, in net send notifications.</span></span>  
  
 <span data-ttu-id="6afbb-111">**Zusätzlich zu sendende Warnbenachrichtigung**</span><span class="sxs-lookup"><span data-stu-id="6afbb-111">**Additional notification message to send**</span></span>  
 <span data-ttu-id="6afbb-112">Geben Sie hier zusätzlichen Text ein, der in die Benachrichtigungsmeldungen aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="6afbb-112">Type any additional text to include in notification messages.</span></span>  
  
 <span data-ttu-id="6afbb-113">**Antwortverzögerung**</span><span class="sxs-lookup"><span data-stu-id="6afbb-113">**Delay between responses**</span></span>  
 <span data-ttu-id="6afbb-114">Geben Sie eine Verzögerung für das wiederholte Auftreten des Ereignisses an.</span><span class="sxs-lookup"><span data-stu-id="6afbb-114">Specify a delay for repeated occurrences of the event.</span></span> <span data-ttu-id="6afbb-115">Einige Ereignisse können innerhalb einer kurzen Zeitspanne häufig auftreten.</span><span class="sxs-lookup"><span data-stu-id="6afbb-115">Some events may occur frequently during a short period of time.</span></span> <span data-ttu-id="6afbb-116">In diesem Fall könnte es sinnvoll sein, zwar über das Auftreten des Ereignisses informiert zu werden, nicht aber für jedes Auftreten eine Meldung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6afbb-116">In this case, you may want to know that the event has occurred, but you may not want a response for every event.</span></span> <span data-ttu-id="6afbb-117">Verwenden Sie diese Option, um ein Timeout anzugeben. Nachdem die Warnung auf ein Ereignis reagiert hat, wartet der-Agent mit einer Verzögerung auf [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die angegebene Verzögerung, bevor erneut reagiert wird, unabhängig davon, ob das Ereignis während der Verzögerung auftritt.</span><span class="sxs-lookup"><span data-stu-id="6afbb-117">Use this option to specify a time-out. With a delay, after the alert responds to an event, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent waits for the delay specified before responding again, regardless of whether the event occurs during the delay.</span></span>  
  
 <span data-ttu-id="6afbb-118">**Minuten**</span><span class="sxs-lookup"><span data-stu-id="6afbb-118">**Minutes**</span></span>  
 <span data-ttu-id="6afbb-119">Geben Sie eine Verzögerung in Minuten an.</span><span class="sxs-lookup"><span data-stu-id="6afbb-119">Specify a delay in minutes.</span></span> <span data-ttu-id="6afbb-120">Wenn bei jedem Auftreten des Ereignisses geantwortet werden soll, geben Sie 0 Minuten und 0 Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="6afbb-120">To respond every time the event occurs, specify 0 minutes and 0 seconds.</span></span>  
  
 <span data-ttu-id="6afbb-121">**Vorsprung**</span><span class="sxs-lookup"><span data-stu-id="6afbb-121">**Seconds**</span></span>  
 <span data-ttu-id="6afbb-122">Geben Sie eine Verzögerung in Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="6afbb-122">Specify a delay in seconds.</span></span> <span data-ttu-id="6afbb-123">Wenn bei jedem Auftreten des Ereignisses geantwortet werden soll, geben Sie 0 Minuten und 0 Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="6afbb-123">To respond every time the event occurs, specify 0 minutes and 0 seconds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6afbb-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6afbb-124">See Also</span></span>  
 [<span data-ttu-id="6afbb-125">Warnungen</span><span class="sxs-lookup"><span data-stu-id="6afbb-125">Alerts</span></span>](alerts.md)  
  
  
