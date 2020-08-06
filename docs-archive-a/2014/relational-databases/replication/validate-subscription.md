---
title: Abonnement überprüfen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.validate.validateandresynch.f1
helpviewer_keywords:
- Validate Subscription dialog box
ms.assetid: 74bdf5e1-b886-4284-b5fb-332bf79ae083
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 010b5b2e9778ccf37133b0a84796373c012290f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615918"
---
# <a name="validate-subscription"></a><span data-ttu-id="41b0e-102">Abonnement überprüfen</span><span class="sxs-lookup"><span data-stu-id="41b0e-102">Validate Subscription</span></span>
  <span data-ttu-id="41b0e-103">Im Dialogfeld **Abonnements überprüfen** können Sie angeben, dass ein Abonnement für eine Mergeveröffentlichung überprüft werden soll, sobald der Merge-Agent für das Abonnement das nächste Mal ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="41b0e-103">Use the **Validate Subscription** dialog box to specify that a subscription to a merge publication should be validated the next time the Merge Agent for the subscription runs.</span></span> <span data-ttu-id="41b0e-104">Die Ergebnisse der Überprüfung werden im Replikationsmonitor angezeigt.</span><span class="sxs-lookup"><span data-stu-id="41b0e-104">The results of validation are displayed in Replication Monitor.</span></span> <span data-ttu-id="41b0e-105">Weitere Informationen finden Sie unter [Validate Data at the Subscriber](validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="41b0e-105">For more information, see [Validate Data at the Subscriber](validate-data-at-the-subscriber.md).</span></span>  
  
 <span data-ttu-id="41b0e-106">Wenn Sie in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] zunächst mit der rechten Maustaste auf eine Veröffentlichung und dann auf **Alle Abonnements überprüfen** klicken, können Sie auch alle Abonnements einer Mergeveröffentlichung überprüfen.</span><span class="sxs-lookup"><span data-stu-id="41b0e-106">It is also possible to validate all subscriptions to a merge publication by right-clicking a publication in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and clicking **Validate All Subscriptions**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="41b0e-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="41b0e-107">Options</span></span>  
 <span data-ttu-id="41b0e-108">**Datum der letzten versuchten Überprüfung**</span><span class="sxs-lookup"><span data-stu-id="41b0e-108">**Date of the last attempted validation**</span></span>  
 <span data-ttu-id="41b0e-109">Das Datum der letzten Merge-Agent-Sitzung, bei der Abonnements überprüft wurden. Der Erfolg der Überprüfung ist dabei nicht entscheidend.</span><span class="sxs-lookup"><span data-stu-id="41b0e-109">The date of the last Merge Agent session that included subscription validation, whether or not that validation was successful.</span></span>  
  
 <span data-ttu-id="41b0e-110">**Datum der letzten erfolgreichen Überprüfung**</span><span class="sxs-lookup"><span data-stu-id="41b0e-110">**Date of the last successful validation**</span></span>  
 <span data-ttu-id="41b0e-111">Das Datum der letzten Merge-Agent-Sitzung, bei der Abonnements erfolgreich überprüft wurden.</span><span class="sxs-lookup"><span data-stu-id="41b0e-111">The date of the last Merge Agent session that included a successful subscription validation.</span></span>  
  
 <span data-ttu-id="41b0e-112">**Dieses Abonnement überprüfen**</span><span class="sxs-lookup"><span data-stu-id="41b0e-112">**Validate this subscription**</span></span>  
 <span data-ttu-id="41b0e-113">Wählen Sie diese Option aus, um das Abonnement zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="41b0e-113">Select to validate the subscription.</span></span>  
  
 <span data-ttu-id="41b0e-114">**Optionen**</span><span class="sxs-lookup"><span data-stu-id="41b0e-114">**Options**</span></span>  
 <span data-ttu-id="41b0e-115">Klicken Sie auf diese Option, um auf das Dialogfeld **Optionen für die Abonnementüberprüfung** zuzugreifen, in dem Sie angeben können, ob die Zeilenanzahlüberprüfung oder die binäre Prüfsummenüberprüfung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="41b0e-115">Click to access the **Subscription Validation Options** dialog box, which allows you to specify whether to use row count validation or binary checksum validation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41b0e-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="41b0e-116">See Also</span></span>  
 [<span data-ttu-id="41b0e-117">Überprüfen von replizierten Daten</span><span class="sxs-lookup"><span data-stu-id="41b0e-117">Validate Replicated Data</span></span>](validate-data-at-the-subscriber.md)  
  
  
