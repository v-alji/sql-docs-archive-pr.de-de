---
title: 'Lektion 3: Synchronisieren des Abonnements für die Mergeveröffentlichung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 49008384-2c55-4080-a890-9bceb40e4d6d
author: rothja
ms.author: jroth
ms.openlocfilehash: bf0256c69d69d1236869fa83285bf4dbf5c462da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723694"
---
# <a name="lesson-3-synchronizing-the-subscription-to-the-merge-publication"></a><span data-ttu-id="f5043-102">Lektion 3: Synchronisieren des Abonnements für die Mergeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="f5043-102">Lesson 3: Synchronizing the Subscription to the Merge Publication</span></span>
  <span data-ttu-id="f5043-103">In dieser Lektion starten Sie den Merge-Agent, um das Abonnement mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="f5043-103">In this lesson, you will start the Merge Agent to initialize the subscription using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="f5043-104">Mithilfe dieser Prozedur können Sie außerdem eine Synchronisierung mit dem Verleger ausführen.</span><span class="sxs-lookup"><span data-stu-id="f5043-104">You also use this procedure to synchronize with the Publisher.</span></span> <span data-ttu-id="f5043-105">Diese Lektion setzt voraus, dass Sie die vorherige Lektion abgeschlossen haben: [Lektion 2: Erstellen eines Abonnements für die Mergeveröffentlichung](lesson-2-creating-a-subscription-to-the-merge-publication.md).</span><span class="sxs-lookup"><span data-stu-id="f5043-105">This lesson requires that you have completed the previous lesson, [Lesson 2: Creating a Subscription to the Merge Publication](lesson-2-creating-a-subscription-to-the-merge-publication.md).</span></span>  
  
### <a name="to-start-synchronization-and-initialize-the-subscription"></a><span data-ttu-id="f5043-106">So starten Sie die Synchronisierung und initialisieren das Abonnement</span><span class="sxs-lookup"><span data-stu-id="f5043-106">To start synchronization and initialize the subscription</span></span>  
  
1.  <span data-ttu-id="f5043-107">Stellen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Verbindung mit dem Abonnenten her, und erweitern Sie dann den Serverknoten sowie den Ordner **Replikation** .</span><span class="sxs-lookup"><span data-stu-id="f5043-107">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="f5043-108">Klicken Sie im Ordner **Lokale Abonnements** mit der rechten Maustaste auf das Abonnement in der Datenbank **SalesOrdersReplica** , und klicken Sie anschließend auf **Synchronisierungsstatus anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="f5043-108">In the **Local Subscriptions** folder, right-click the subscription in the **SalesOrdersReplica** database, and then click **View Synchronization Status**.</span></span>  
  
3.  <span data-ttu-id="f5043-109">Klicken Sie auf **Start** , um das Abonnement zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="f5043-109">Click **Start** to initialize the subscription.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f5043-110">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f5043-110">Next Steps</span></span>  
 <span data-ttu-id="f5043-111">Sie haben den Merge-Agent erfolgreich ausgeführt, um die Synchronisierung zu starten und das Abonnement zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="f5043-111">You have successfully run the Merge Agent to start synchronization and initialize the subscription.</span></span> <span data-ttu-id="f5043-112">Sie können auch Daten in der **SalesOrderHeader** -Tabelle oder der **SalesOrderDetail** -Tabelle auf dem Verleger oder dem Abonnenten einfügen, aktualisieren oder löschen, diese Schrittfolge wiederholen, wenn eine Netzwerkverbindung verfügbar ist, um Daten zwischen dem Verleger und dem Abonnenten zu synchronisieren, und anschließend können Sie die **SalesOrderHeader** -Tabelle oder die **SalesOrderDetail** -Tabelle auf dem anderen Server abfragen, um die replizierten Änderungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f5043-112">You can also insert, update, or delete data in the **SalesOrderHeader** or **SalesOrderDetail** tables at the Publisher or Subscriber, repeat this procedure when network connectivity is available to synchronize data between the Publisher and the Subscriber, and then query the **SalesOrderHeader** or **SalesOrderDetail** tables at the other server to view the replicated changes.</span></span>  
  
 <span data-ttu-id="f5043-113">Damit ist das Lernprogramm zum Replizieren von Daten mit mobilen Clients abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f5043-113">This completes the Replicating Data with Mobile Clients tutorial.</span></span> <span data-ttu-id="f5043-114">Ein ähnliches Lernprogramm für Transaktionsreplikationen finden Sie unter [Tutorial: Replicating Data Between Continuously Connected Servers](tutorial-replicating-data-between-continuously-connected-servers.md).</span><span class="sxs-lookup"><span data-stu-id="f5043-114">For a similar tutorial that uses transactional replication, see [Tutorial: Replicating Data Between Continuously Connected Servers](tutorial-replicating-data-between-continuously-connected-servers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5043-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f5043-115">See Also</span></span>  
 <span data-ttu-id="f5043-116">[Initialisieren eines Abonnements mit einer Momentaufnahme](initialize-a-subscription-with-a-snapshot.md) </span><span class="sxs-lookup"><span data-stu-id="f5043-116">[Initialize a Subscription with a Snapshot](initialize-a-subscription-with-a-snapshot.md) </span></span>  
 <span data-ttu-id="f5043-117">[Synchronisieren von Daten](synchronize-data.md) </span><span class="sxs-lookup"><span data-stu-id="f5043-117">[Synchronize Data](synchronize-data.md) </span></span>  
 [<span data-ttu-id="f5043-118">Synchronisieren eines Pullabonnements</span><span class="sxs-lookup"><span data-stu-id="f5043-118">Synchronize a Pull Subscription</span></span>](synchronize-a-pull-subscription.md)  
  
  
