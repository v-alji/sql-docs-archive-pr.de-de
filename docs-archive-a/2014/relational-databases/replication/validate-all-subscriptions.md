---
title: Alle Abonnements überprüfen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.validate.allsubscriptions.f1
helpviewer_keywords:
- Validate All Subscriptions dialog box
ms.assetid: 32e31469-36e4-42d9-a57a-12388bfd229d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 27a7a4f5e5c3c303d5a1cbe257c0a0e9b531e824
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620264"
---
# <a name="validate-all-subscriptions"></a><span data-ttu-id="90077-102">Alle Abonnements überprüfen</span><span class="sxs-lookup"><span data-stu-id="90077-102">Validate All Subscriptions</span></span>
  <span data-ttu-id="90077-103">Im Dialogfeld **Alle Abonnements überprüfen** können Sie angeben, dass alle Abonnements für eine Mergeveröffentlichung überprüft werden sollen, sobald der Merge-Agent für die einzelnen Abonnements das nächste Mal ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="90077-103">Use the **Validate All Subscriptions** dialog box to specify that all subscriptions to a merge publication should be validated the next time the Merge Agent for each subscription runs.</span></span> <span data-ttu-id="90077-104">Die Ergebnisse der Überprüfung werden im Replikationsmonitor angezeigt.</span><span class="sxs-lookup"><span data-stu-id="90077-104">The results of validation are displayed in Replication Monitor.</span></span> <span data-ttu-id="90077-105">Weitere Informationen finden Sie unter [Validate Data at the Subscriber](validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="90077-105">For more information, see [Validate Data at the Subscriber](validate-data-at-the-subscriber.md).</span></span>  
  
 <span data-ttu-id="90077-106">Wenn Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] mit der rechten Maustaste auf ein Abonnement klicken und dann auf **Abonnement überprüfen**klicken, können Sie auch ein einzelnes Abonnement überprüfen.</span><span class="sxs-lookup"><span data-stu-id="90077-106">It is also possible to validate a single subscription by right-clicking a subscription in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and clicking **Validate Subscription**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="90077-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="90077-107">Options</span></span>  
 <span data-ttu-id="90077-108">**Nur Zeilenanzahl überprüfen**</span><span class="sxs-lookup"><span data-stu-id="90077-108">**Verify the row counts only**</span></span>  
 <span data-ttu-id="90077-109">Wählen Sie diese Option aus, um zu überprüfen, ob die Anzahl der Zeilen in der Tabelle auf dem Abonnenten mit der Anzahl der Zeilen in der Tabelle auf dem Verleger übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="90077-109">Select to validate whether the table at the Subscriber has the same number of rows as the table at the Publisher.</span></span> <span data-ttu-id="90077-110">Mit dieser Methode wird nicht überprüft, ob die Inhalte der Zeilen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="90077-110">This method does not validate that the content of the rows matches.</span></span> <span data-ttu-id="90077-111">Die Überprüfung der Zeilenanzahl bietet einen Überprüfungsansatz, der kaum Ressourcen beansprucht und Sie Probleme bei den Daten erkennen lässt.</span><span class="sxs-lookup"><span data-stu-id="90077-111">Row count validation provides a lightweight approach to validation that can make you aware of issues with your data.</span></span>  
  
 <span data-ttu-id="90077-112">**Die Zeilenanzahl überprüfen und Prüfsummen vergleichen, um die Zeilendaten zu überprüfen**</span><span class="sxs-lookup"><span data-stu-id="90077-112">**Verify the row counts and compare checksums to verify the row data**</span></span>  
 <span data-ttu-id="90077-113">Zusätzlich zum Einbinden einer Reihe von Zeilen auf Verleger- und Abonnentenebene wird eine Prüfsumme aller Daten mit dem binären Prüfsummenalgorithmus berechnet.</span><span class="sxs-lookup"><span data-stu-id="90077-113">In addition to taking a count of rows at the Publisher and Subscriber, a checksum of all the data is calculated using the binary checksum algorithm.</span></span> <span data-ttu-id="90077-114">Ist die Zeilenanzahl fehlerhaft, wird die Berechnung der Prüfsumme nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="90077-114">If the row count fails, the checksum is not performed.</span></span> <span data-ttu-id="90077-115">Diese Option gilt nicht für [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90077-115">This option is not valid for [!INCLUDE[ssEW](../../includes/ssew-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90077-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90077-116">See Also</span></span>  
 [<span data-ttu-id="90077-117">Überprüfen von replizierten Daten</span><span class="sxs-lookup"><span data-stu-id="90077-117">Validate Replicated Data</span></span>](validate-data-at-the-subscriber.md)  
  
  
