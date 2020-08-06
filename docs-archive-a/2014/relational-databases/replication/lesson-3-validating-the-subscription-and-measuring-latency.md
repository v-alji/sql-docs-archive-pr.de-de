---
title: 'Lektion 3: Überprüfen des Abonnements und Messen der Latenzzeit | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 147f7b93-1804-4e0b-9e17-57a51d035b2a
author: rothja
ms.author: jroth
ms.openlocfilehash: e4893c054d25d131eb2f88f32291606b0b789af7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723693"
---
# <a name="lesson-3-validating-the-subscription-and-measuring-latency"></a><span data-ttu-id="4f862-102">Lektion 3: Überprüfen des Abonnements und Messen der Latenzzeit</span><span class="sxs-lookup"><span data-stu-id="4f862-102">Lesson 3: Validating the Subscription and Measuring Latency</span></span>
  <span data-ttu-id="4f862-103">In dieser Lektion verwenden Sie Überwachungstoken, um sicherzustellen, dass Änderungen auf dem Abonnenten repliziert werden, und um die Latenzzeit (die Zeit, nach der eine auf dem Verleger vorgenommene Änderung auf dem Abonnenten angezeigt wird) zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="4f862-103">In this lesson, you will use tracer tokens to verify that changes are being replicated to the Subscriber and to determine latency, the time it takes for a change made at the Publisher to appear to the Subscriber.</span></span> <span data-ttu-id="4f862-104">Diese Lektion setzt voraus, dass Sie die vorherige Lektion abgeschlossen haben: [Lektion 2: Erstellen eines Abonnements für die Transaktionsveröffentlichung](lesson-2-creating-a-subscription-to-the-transactional-publication.md).</span><span class="sxs-lookup"><span data-stu-id="4f862-104">This lesson requires that you have completed the previous lesson, [Lesson 2: Creating a Subscription to the Transactional Publication](lesson-2-creating-a-subscription-to-the-transactional-publication.md).</span></span>  
  
### <a name="to-insert-a-tracer-token-and-view-information-on-the-token"></a><span data-ttu-id="4f862-105">So fügen Sie ein Überwachungstoken ein und zeigen Informationen zum Token an</span><span class="sxs-lookup"><span data-stu-id="4f862-105">To insert a tracer token and view information on the token</span></span>  
  
1.  <span data-ttu-id="4f862-106">Stellen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Verbindung mit dem Verleger her, erweitern Sie den Serverknoten, klicken Sie mit der rechten Maustaste auf den Ordner **Replikation** , und klicken Sie anschließend auf **Replikationsmonitor starten**.</span><span class="sxs-lookup"><span data-stu-id="4f862-106">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, right-click the **Replication** folder, and then click **Launch Replication Monitor**.</span></span>  
  
     <span data-ttu-id="4f862-107">Der Replikationsmonitor wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="4f862-107">Replication Monitor launches.</span></span>  
  
2.  <span data-ttu-id="4f862-108">Erweitern Sie im linken Bereich eine Verlegergruppe, erweitern Sie die Verlegerinstanz, und klicken Sie dann auf die **AdvWorksProductTrans** -Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="4f862-108">Expand a Publisher group in the left pane, expand the Publisher instance, and then click the **AdvWorksProductTrans** publication.</span></span>  
  
3.  <span data-ttu-id="4f862-109">Klicken Sie auf die Registerkarte **Überwachungstoken** .</span><span class="sxs-lookup"><span data-stu-id="4f862-109">Click the **Tracer Tokens** tab.</span></span>  
  
4.  <span data-ttu-id="4f862-110">Klicken Sie auf **Überwachung einfügen**.</span><span class="sxs-lookup"><span data-stu-id="4f862-110">Click **Insert Tracer**.</span></span>  
  
5.  <span data-ttu-id="4f862-111">In den folgenden Spalten sehen Sie die für das Überwachungstoken benötigte Zeit: **Verleger zu Verteiler**, **Verteiler zu Abonnent**, **Gesamtlatenzzeit**.</span><span class="sxs-lookup"><span data-stu-id="4f862-111">View elapsed time for the tracer token in the following columns: **Publisher to Distributor**, **Distributor to Subscriber**, **Total Latency**.</span></span> <span data-ttu-id="4f862-112">Der Wert **Pending** gibt an, dass das Token einen bestimmten Punkt nicht erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="4f862-112">A value of **Pending** indicates that the token has not reached a given point.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4f862-113">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="4f862-113">Next Steps</span></span>  
 <span data-ttu-id="4f862-114">In dieser Lektion haben Sie mithilfe von Überwachungstoken erfolgreich überprüft, dass Datenänderungen vom Verleger zum Abonnenten repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="4f862-114">In this lesson, you successfully used tracer tokens to validate that data changes are being replicated from the Publisher to the Subscriber.</span></span> <span data-ttu-id="4f862-115">Zudem können Sie Daten in der **Product** -Tabelle auf dem Verleger einfügen, aktualisieren und löschen und die **Product** -Tabelle auf dem Abonnenten abfragen, um diese Änderungen anzuzeigen, nachdem sie repliziert wurden.</span><span class="sxs-lookup"><span data-stu-id="4f862-115">You can also insert, update, or delete data in the **Product** table at the Publisher and query the **Product** table at the Subscriber to view these changes after they are replicated.</span></span>  
  
 <span data-ttu-id="4f862-116">Damit ist das Lernprogramm Replizieren von Daten zwischen Servern mit kontinuierlicher Verbindung abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4f862-116">This completes the Replicating Data Between Continuously Connected Servers tutorial.</span></span> <span data-ttu-id="4f862-117">Ein ähnliches Lernprogramm zur Mergereplikation finden Sie unter [Tutorial: Replicating Data with Mobile Clients](tutorial-replicating-data-with-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="4f862-117">For a similar tutorial that uses merge replication, see [Tutorial: Replicating Data with Mobile Clients](tutorial-replicating-data-with-mobile-clients.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f862-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4f862-118">See Also</span></span>  
 [<span data-ttu-id="4f862-119">Messen der Latenzzeit und Überprüfen der Verbindungen bei Transaktionsreplikationen</span><span class="sxs-lookup"><span data-stu-id="4f862-119">Measure Latency and Validate Connections for Transactional Replication</span></span>](monitor/measure-latency-and-validate-connections-for-transactional-replication.md)  
  
  
