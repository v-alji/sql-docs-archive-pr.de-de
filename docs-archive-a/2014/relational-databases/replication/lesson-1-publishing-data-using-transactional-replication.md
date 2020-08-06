---
title: 'Lektion 1: Veröffentlichen von Daten mithilfe der Transaktionsreplikation | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 9c55aa3c-4664-41fc-943f-e817c31aad5e
author: rothja
ms.author: jroth
ms.openlocfilehash: ce20f4ed8863ede34c8709d2b77bf032e7d14a97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696713"
---
# <a name="lesson-1-publishing-data-using-transactional-replication"></a><span data-ttu-id="a6eee-102">Lektion 1: Veröffentlichen von Daten mithilfe der Transaktionsreplikation</span><span class="sxs-lookup"><span data-stu-id="a6eee-102">Lesson 1: Publishing Data Using Transactional Replication</span></span>
  <span data-ttu-id="a6eee-103"> In dieser Lektion erstellen Sie mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] eine Transaktionsveröffentlichung, um eine gefilterte Teilmenge der **Product**-Tabelle in der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]-Beispieldatenbank zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="a6eee-103">In this lesson, you will create a transactional publication using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to publish a filtered subset of the **Product** table in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="a6eee-104">Außerdem fügen Sie der Veröffentlichungszugriffsliste (Publication Access List, PAL) die vom Verteilungs-Agent verwendete SQL Server-Anmeldung hinzu.</span><span class="sxs-lookup"><span data-stu-id="a6eee-104">You will also add the SQL Server login used by the Distribution Agent to the publication access list (PAL).</span></span> <span data-ttu-id="a6eee-105">Bevor Sie dieses Tutorial starten, sollten Sie das vorherige Tutorial ( [Vorbereiten des Servers für die Replikation](tutorial-preparing-the-server-for-replication.md)) abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="a6eee-105">Before starting this tutorial, you should have completed the previous tutorial, [Preparing the Server for Replication](tutorial-preparing-the-server-for-replication.md).</span></span>  
  
### <a name="to-create-a-publication-and-define-articles"></a><span data-ttu-id="a6eee-106">So erstellen Sie eine Veröffentlichung und definieren Artikel</span><span class="sxs-lookup"><span data-stu-id="a6eee-106">To create a publication and define articles</span></span>  
  
1.  <span data-ttu-id="a6eee-107">Stellen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Verbindung mit dem Verleger her, und erweitern Sie dann den Serverknoten.</span><span class="sxs-lookup"><span data-stu-id="a6eee-107">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="a6eee-108">Erweitern Sie den Ordner **Replikation** und klicken Sie mit der rechten Maustaste auf den Ordner **Lokale Veröffentlichungen** . Klicken Sie anschließend auf **Neue Veröffentlichung**.</span><span class="sxs-lookup"><span data-stu-id="a6eee-108">Expand the **Replication** folder, right-click the **Local Publications** folder, and click **New Publication**.</span></span>  
  
     <span data-ttu-id="a6eee-109">Der Assistent für neue Veröffentlichung wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="a6eee-109">The Publication Configuration Wizard launches.</span></span>  
  
3.  <span data-ttu-id="a6eee-110">Wählen Sie auf der Seite Veröffentlichungsdatenbank [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]aus, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a6eee-110">On the Publication Database page, select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="a6eee-111">Wählen Sie auf der Seite Veröffentlichungstyp **Transaktionsveröffentlichung**aus, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a6eee-111">On the Publication Type page, select **Transactional publication**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="a6eee-112">Erweitern Sie auf der Seite Artikel den Knoten **Tabellen** , aktivieren Sie das Kontrollkästchen **Product** , erweitern Sie anschließend **Product** und deaktivieren Sie die Kontrollkästchen **ListPrice** und **StandardCost** .</span><span class="sxs-lookup"><span data-stu-id="a6eee-112">On the Articles page, expand the **Tables** node, select the **Product** check box, then expand **Product** and clear the **ListPrice** and **StandardCost** check boxes.</span></span> <span data-ttu-id="a6eee-113">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a6eee-113">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="a6eee-114">Klicken Sie auf der Seite Tabellenzeilen filtern auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a6eee-114">On the Filter Table Rows page, click **Add**.</span></span>  
  
7.  <span data-ttu-id="a6eee-115">Klicken Sie im Dialogfeld **Filter hinzufügen** auf die Spalte **SafetyStockLevel** , klicken Sie auf den Pfeil nach rechts, um der WHERE-Klausel der Filteranweisung die Spalte hinzuzufügen, und ändern Sie die WHERE-Klausel wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a6eee-115">In the **Add Filter** dialog box, click the **SafetyStockLevel** column, click the right arrow to add the column to the Filter statement WHERE clause of the filter query, and modify the WHERE clause as follows:</span></span>  
  
    ```  
    WHERE [SafetyStockLevel] < 500  
    ```  
  
8.  <span data-ttu-id="a6eee-116">Klicken Sie auf **OK**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a6eee-116">Click **OK**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="a6eee-117">Aktivieren Sie das Kontrollkästchen **Momentaufnahme sofort erstellen und zum Initialisieren von Abonnements verfügbar halten** und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a6eee-117">Select the **Create a snapshot immediately and keep the snapshot available to initialize subscriptions** check box, and click **Next**.</span></span>  
  
10. <span data-ttu-id="a6eee-118">Deaktivieren Sie auf der Seite „Agentsicherheit“ das Kontrollkästchen **Sicherheitseinstellungen des Momentaufnahme-Agents verwenden** .</span><span class="sxs-lookup"><span data-stu-id="a6eee-118">On the Agent Security page, clear **Use the security settings from the Snapshot Agent** check box.</span></span>  
  
11. <span data-ttu-id="a6eee-119">Klicken Sie für den Momentaufnahmen-Agent auf **Sicherheitseinstellungen** , geben Sie \<_Machine_Name> im Feld **Prozess Konto** die Angabe _**\ repl_snapshot** ein, geben Sie das Kennwort für dieses Konto an, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6eee-119">Click **Security Settings** for the Snapshot Agent, enter \<_Machine_Name>_**\repl_snapshot** in the **Process account** box, supply the password for this account, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="a6eee-120">Wiederholen Sie den vorherigen Schritt, um repl_logreader als Prozesskonto für den Protokolllese-Agenten festzulegen, und klicken Sie anschließend auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="a6eee-120">Repeat the previous step to set repl_logreader as the process account for the Log Reader Agent, and then click **Finish**.</span></span>  
  
13. <span data-ttu-id="a6eee-121">Geben Sie auf der Seite „Assistenten abschließen“ im Feld **Veröffentlichungsname** den Namen **AdvWorksProductTrans** ein und klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="a6eee-121">On the Complete the Wizard page, type **AdvWorksProductTrans** in the **Publication name** box, and click **Finish**.</span></span>  
  
14. <span data-ttu-id="a6eee-122">Klicken Sie auf **Schließen** , um den Assistenten zu beenden, nachdem die Veröffentlichung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="a6eee-122">After the publication is created, click **Close** to complete the wizard.</span></span>  
  
### <a name="to-view-the-status-of-snapshot-generation"></a><span data-ttu-id="a6eee-123">So zeigen Sie den Status der Momentaufnahmegenerierung an</span><span class="sxs-lookup"><span data-stu-id="a6eee-123">To view the status of snapshot generation</span></span>  
  
1.  <span data-ttu-id="a6eee-124">Stellen Sie in eine Verbindung mit dem Verleger her [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , erweitern Sie den Server Knoten, und erweitern Sie dann den Ordner **Replikation** .</span><span class="sxs-lookup"><span data-stu-id="a6eee-124">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="a6eee-125">Klicken Sie im Ordner **Lokale Veröffentlichungen** mit der rechten Maustaste auf **AdvWorksProductTrans**und anschließend auf **Status des Momentaufnahme-Agents anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="a6eee-125">In the **Local Publications** folder, right-click **AdvWorksProductTrans**, and then click **View Snapshot Agent Status**.</span></span>  
  
3.  <span data-ttu-id="a6eee-126">Der aktuelle Status des Auftrags des Momentaufnahme-Agents für die Veröffentlichung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a6eee-126">The current status of the Snapshot Agent job for the publication is displayed.</span></span> <span data-ttu-id="a6eee-127">Prüfen Sie, ob der Momentaufnahmeauftrag erfolgreich war, bevor Sie zur nächsten Lektion wechseln.</span><span class="sxs-lookup"><span data-stu-id="a6eee-127">Verify that the snapshot job has succeeded before you continue to the next lesson.</span></span>  
  
### <a name="to-add-the-distribution-agent-login-to-the-pal"></a><span data-ttu-id="a6eee-128">So fügen Sie der PAL die Anmeldung des Verteilungs-Agents hinzu</span><span class="sxs-lookup"><span data-stu-id="a6eee-128">To add the Distribution Agent login to the PAL</span></span>  
  
1.  <span data-ttu-id="a6eee-129">Stellen Sie in eine Verbindung mit dem Verleger her [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , erweitern Sie den Server Knoten, und erweitern Sie dann den Ordner **Replikation** .</span><span class="sxs-lookup"><span data-stu-id="a6eee-129">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="a6eee-130">Klicken Sie im Ordner **Lokale Veröffentlichungen** mit der rechten Maustaste auf **AdvWorksProductTrans**und anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="a6eee-130">In the **Local Publications** folder, right-click **AdvWorksProductTrans**, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="a6eee-131">Das Dialogfeld **Veröffentlichungseigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a6eee-131">The **Publication Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="a6eee-132">Wählen Sie die Seite **Veröffentlichungszugriffsliste** aus und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a6eee-132">Select the **Publication Access List** page, and click **Add**.</span></span>  
  
4.  <span data-ttu-id="a6eee-133">Wählen Sie im Dialogfeld **Veröffentlichungszugriff hinzufügen** die Anmeldung _<Computername>_**\repl_distribution** aus und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6eee-133">\In the **Add Publication Access** dialog box, select _<Machine_Name>_**\repl_distribution** and click **OK**.</span></span> <span data-ttu-id="a6eee-134">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6eee-134">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a6eee-135">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a6eee-135">Next Steps</span></span>  
 <span data-ttu-id="a6eee-136">Sie haben die Transaktionsveröffentlichung erfolgreich erstellt.</span><span class="sxs-lookup"><span data-stu-id="a6eee-136">You have successfully created the transactional publication.</span></span> <span data-ttu-id="a6eee-137">Als Nächstes abonnieren Sie diese Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="a6eee-137">Next, you will subscribe to this publication.</span></span> <span data-ttu-id="a6eee-138">Siehe [Lektion 2: Erstellen eines Abonnements für die Transaktionsveröffentlichung](lesson-2-creating-a-subscription-to-the-transactional-publication.md).</span><span class="sxs-lookup"><span data-stu-id="a6eee-138">See [Lesson 2: Creating a Subscription to the Transactional Publication](lesson-2-creating-a-subscription-to-the-transactional-publication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6eee-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a6eee-139">See Also</span></span>  
 <span data-ttu-id="a6eee-140">[Filtern von veröffentlichten Daten](publish/filter-published-data.md) </span><span class="sxs-lookup"><span data-stu-id="a6eee-140">[Filter Published Data](publish/filter-published-data.md) </span></span>  
 <span data-ttu-id="a6eee-141">[Define an Article](publish/define-an-article.md) </span><span class="sxs-lookup"><span data-stu-id="a6eee-141">[Define an Article](publish/define-an-article.md) </span></span>  
 [<span data-ttu-id="a6eee-142">Erstellen und Anwenden der Momentaufnahme</span><span class="sxs-lookup"><span data-stu-id="a6eee-142">Create and Apply the Snapshot</span></span>](create-and-apply-the-snapshot.md)  
  
  
