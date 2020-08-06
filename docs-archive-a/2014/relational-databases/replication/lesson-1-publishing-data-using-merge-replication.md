---
title: 'Lektion 1: Veröffentlichen von Daten mithilfe der Mergereplikation | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: c3c6e0b6-54cd-4b7d-8efb-2cefe14fcd7f
author: rothja
ms.author: jroth
ms.openlocfilehash: ba1d8829d84c02d1436013af80de4bf0979049e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721370"
---
# <a name="lesson-1-publishing-data-using-merge-replication"></a><span data-ttu-id="af738-102">Lektion 1: Veröffentlichen von Daten mithilfe der Mergereplikation</span><span class="sxs-lookup"><span data-stu-id="af738-102">Lesson 1: Publishing Data Using Merge Replication</span></span>
  <span data-ttu-id="af738-103">In dieser Lektion erstellen Sie mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] eine Mergeveröffentlichung, um eine Teilmenge der Tabellen **Employee**, **SalesOrderHeader**und **SalesOrderDetail** in der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Beispieldatenbank zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="af738-103">In this lesson, you will create a merge publication using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to publish a subset of the **Employee**, **SalesOrderHeader**, and **SalesOrderDetail** tables in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="af738-104">Diese Tabellen werden mit parametrisierten Zeilenfiltern gefiltert, sodass in den einzelnen Abonnements jeweils eine eindeutige Teilmenge der Daten enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="af738-104">These tables are filtered with parameterized row filters so that each subscription contains a unique partition of the data.</span></span> <span data-ttu-id="af738-105">Außerdem fügen Sie der Veröffentlichungszugriffsliste (Publication Access List, PAL) die vom Merge-Agent verwendete [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung hinzu.</span><span class="sxs-lookup"><span data-stu-id="af738-105">You will also add the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used by the Merge Agent to the publication access list (PAL).</span></span> <span data-ttu-id="af738-106">Für dieses Lernprogramm ist es erforderlich, dass Sie das vorherige Lernprogramm ( [Vorbereiten des Servers für die Replikation](tutorial-preparing-the-server-for-replication.md)) abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="af738-106">This tutorial requires that you have completed the previous tutorial, [Preparing the Server for Replication](tutorial-preparing-the-server-for-replication.md).</span></span>  
  
### <a name="to-create-a-publication-and-define-articles"></a><span data-ttu-id="af738-107">So erstellen Sie eine Veröffentlichung und definieren Artikel</span><span class="sxs-lookup"><span data-stu-id="af738-107">To create a publication and define articles</span></span>  
  
1.  <span data-ttu-id="af738-108">Stellen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Verbindung mit dem Verleger her, und erweitern Sie dann den Serverknoten.</span><span class="sxs-lookup"><span data-stu-id="af738-108">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="af738-109">Erweitern Sie den Ordner **Replikation** und klicken Sie mit der rechten Maustaste auf **Lokale Veröffentlichungen**. Klicken Sie anschließend auf **Neue Veröffentlichung**.</span><span class="sxs-lookup"><span data-stu-id="af738-109">Expand the **Replication** folder, right-click **Local Publications**, and click **New Publication**.</span></span>  
  
     <span data-ttu-id="af738-110">Der Assistent für neue Veröffentlichung wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="af738-110">The Publication Configuration Wizard launches.</span></span>  
  
3.  <span data-ttu-id="af738-111">Wählen Sie auf der Seite Veröffentlichungsdatenbank [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]aus, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="af738-111">On the Publication Database page, select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="af738-112">Wählen Sie auf der Seite **Veröffentlichungstyp**die Option **Mergeveröffentlichung**aus und klicken Sie anschließend auf Weiter.</span><span class="sxs-lookup"><span data-stu-id="af738-112">On the Publication Type page, select **Merge publication**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="af738-113">Stellen Sie auf der Seite „Abonnententypen“ sicher, dass [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] oder höher ausgewählt ist, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="af738-113">On the Subscriber Types page, ensure that only [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later is selected, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="af738-114">Erweitern Sie auf der Seite Artikel den Knoten **Tabellen** und wählen Sie **SalesOrderHeader** und **SalesOrderDetail**aus. Erweitern Sie anschließend **Employee**, wählen Sie **EmployeeID** oder **LoginID**aus und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="af738-114">On the Articles page, expand the **Tables** node, select **SalesOrderHeader** and **SalesOrderDetail**, then expand **Employee**, select **EmployeeID** or **LoginID**, and then click **Next**.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="af738-115">Zusätzliche erforderliche Spalten werden automatisch ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="af738-115">Additional required columns are automatically selected.</span></span> <span data-ttu-id="af738-116">Wählen Sie beliebige automatisch ausgewählte Spalten aus, und lesen Sie unter der Liste **Zu veröffentlichende Objekte** die Erklärung, warum die Spalte erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="af738-116">Select any of  the automatically selected columns and view the note below the **Objects to publish** list for an explanation why the column is required.</span></span>  
  
7.  <span data-ttu-id="af738-117">Klicken Sie auf der Seite Tabellenzeilen filtern auf **Hinzufügen** und klicken Sie anschließend auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="af738-117">On the Filter Table Rows page, click **Add** and then click **Add Filter**.</span></span>  
  
8.  <span data-ttu-id="af738-118">Wählen Sie im Dialogfeld **Filter hinzufügen** unter **Wählen Sie die zu filternde Tabelle aus** die Option **Employee (HumanResources)** aus. Klicken Sie auf die Spalte **LoginID** und anschließend auf den nach rechts weisenden Pfeil, um der WHERE-Klausel der Filterabfrage die Spalte hinzuzufügen, und ändern Sie die WHERE-Klausel wie folgt:</span><span class="sxs-lookup"><span data-stu-id="af738-118">In the **Add Filter** dialog box, select **Employee (HumanResources)** in **Select the table to filter**, click the **LoginID** column, click the right arrow to add the column to the WHERE clause of the filter query, and modify the WHERE clause as follows:</span></span>  
  
    ```  
    WHERE [LoginID] = HOST_NAME()  
    ```  
  
9. <span data-ttu-id="af738-119">Klicken Sie auf **Eine Zeile aus dieser Tabelle wird nur an ein Abonnement gesendet**und anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="af738-119">Click **A row from this table will go to only one subscription**, and click **OK**.</span></span>  
  
10. <span data-ttu-id="af738-120">Klicken Sie auf der Seite **Tabellenzeilen filtern** auf **Employee (Human Resources)**, klicken Sie auf **Hinzufügen** und anschließend auf **Join hinzufügen, um den ausgewählten Filter zu erweitern**.</span><span class="sxs-lookup"><span data-stu-id="af738-120">On the **Filter Table Rows** page, click **Employee (Human Resources)**, click **Add,** and then click **Add Join to Extend the Selected Filter**.</span></span>  
  
11. <span data-ttu-id="af738-121">Wählen Sie im Dialogfeld **Join hinzufügen** unter **Verknüpfte Tabelle** die Tabelle **Sales.SalesOrderHeader**aus, klicken Sie auf **Joinanweisung manuell schreiben**und vervollständigen Sie die Joinanweisung wie folgt:</span><span class="sxs-lookup"><span data-stu-id="af738-121">In the **Add Join** dialog box, select **Sales.SalesOrderHeader** under **Joined table**, click **Write the join statement manually**, and complete the join statement as follows:</span></span>  
  
    ```  
    ON Employee.EmployeeID = SalesOrderHeader.SalesPersonID  
    ```  
  
12. <span data-ttu-id="af738-122">Wählen Sie unter **Geben Sie Joinoptionen an**die Option **Eindeutiger Schlüssel**aus und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="af738-122">In **Specify join options**, select **Unique key**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="af738-123">Klicken Sie auf der Seite Tabellenzeilen filtern auf **SalesOrderHeader**, klicken Sie auf **Hinzufügen**und anschließend auf **Join hinzufügen, um den ausgewählten Filter zu erweitern**.</span><span class="sxs-lookup"><span data-stu-id="af738-123">On the Filter Table Rows page, click **SalesOrderHeader**, click **Add**, and then click **Add Join to Extend the Selected Filter**.</span></span>  
  
14. <span data-ttu-id="af738-124">Wählen Sie im Dialogfeld **Join hinzufügen** unter **Verknüpfte Tabelle** den Eintrag **Sales.SalesOrderDetail**aus.</span><span class="sxs-lookup"><span data-stu-id="af738-124">In the **Add Join** dialog box, select **Sales.SalesOrderDetail** under **Joined table**.</span></span>  
  
15. <span data-ttu-id="af738-125">Klicken Sie auf **Joinanweisung manuell schreiben**.</span><span class="sxs-lookup"><span data-stu-id="af738-125">Click **Write the join statement manually**.</span></span>  
  
16. <span data-ttu-id="af738-126">Wählen Sie in **Gefilterte Tabellenspalten**den Eintrag **BusinessEntityID**aus und klicken Sie anschließend auf die Pfeilschaltfläche, um den Spaltennamen in die Joinanweisung zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="af738-126">In **Filtered table columns**, select **BusinessEntityID**, then click the arrow button to copy the column name to the loin statement.</span></span>  
  
17. <span data-ttu-id="af738-127">Schließen Sie im Feld **Joinanweisung** die Joinanweisung wie folgt ab:</span><span class="sxs-lookup"><span data-stu-id="af738-127">In the **Join statement** box, complete the join statement as follows:</span></span>  
  
    ```  
    ON Employee.BusinessEntityID = SalesOrderHeader.SalesPersonID  
    ```  
  
18. <span data-ttu-id="af738-128">Wählen Sie unter **Geben Sie Joinoptionen an**die Option **Eindeutiger Schlüssel**aus und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="af738-128">In **Specify join options**, select **Unique key**, and then click **OK**.</span></span>  
  
19. <span data-ttu-id="af738-129">Klicken Sie auf der Seite **Tabellenzeilen filtern** auf **SalesOrderHeader (Sales)**, klicken Sie auf **Hinzufügen**und anschließend auf **Join hinzufügen, um den ausgewählten Filter zu erweitern**.</span><span class="sxs-lookup"><span data-stu-id="af738-129">On the **Filter Table Rows** page, click **SalesOrderHeader (Sales)**, click **Add**, and then click **Add Join to Extend the Selected Filter**.</span></span>  
  
20. <span data-ttu-id="af738-130">Wählen Sie im Dialogfeld **Join hinzufügen** unter **Verknüpfte Tabelle** die Tabelle **Sales.SalesOrderDetail**aus, klicken Sie auf **OK**und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="af738-130">In the **Add Join** dialog box, select **Sales.SalesOrderDetail** under **Joined table**, click **OK**, and then click **Next**.</span></span>  
  
21. <span data-ttu-id="af738-131">Wählen Sie **Momentaufnahme sofort erstellen**aus, deaktivieren Sie **Ausführung des Momentaufnahme-Agents zu folgenden Zeitpunkten planen**und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="af738-131">Select **Create a snapshot immediately**, clear **Schedule the snapshot agent to run at the following times**, and click **Next**.</span></span>  
  
22. <span data-ttu-id="af738-132">Klicken Sie auf der Seite Agentsicherheit auf **Sicherheitseinstellungen**, geben Sie \<_Machine_Name> im Feld **Prozess Konto** die Angabe _**\ repl_snapshot** ein, geben Sie das Kennwort für dieses Konto an, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="af738-132">On the Agent Security page, click **Security Settings**, type \<_Machine_Name>_**\repl_snapshot** in the **Process account** box, supply the password for this account, and then click **OK**.</span></span> <span data-ttu-id="af738-133">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="af738-133">Click **Finish**.</span></span>  
  
23. <span data-ttu-id="af738-134">Geben Sie auf der Seite „Assistenten abschließen“ im Feld **Veröffentlichungsname** den Namen **AdvWorksSalesOrdersMerge** ein und klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="af738-134">On the Complete the Wizard page, enter **AdvWorksSalesOrdersMerge** in the **Publication name** box and click **Finish**.</span></span>  
  
24. <span data-ttu-id="af738-135">Klicken Sie auf **Schließen**, nachdem die Veröffentlichung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="af738-135">After the publication is created, click **Close**.</span></span>  
  
### <a name="to-view-the-status-of-snapshot-generation"></a><span data-ttu-id="af738-136">So zeigen Sie den Status der Momentaufnahmegenerierung an</span><span class="sxs-lookup"><span data-stu-id="af738-136">To view the status of snapshot generation</span></span>  
  
1.  <span data-ttu-id="af738-137">Stellen Sie in eine Verbindung mit dem Verleger her [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , erweitern Sie den Server Knoten, und erweitern Sie dann den Ordner **Replikation** .</span><span class="sxs-lookup"><span data-stu-id="af738-137">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="af738-138">Klicken Sie im Ordner Lokale Veröffentlichungen mit der rechten Maustaste auf **AdvWorksSalesOrdersMerge**und anschließend auf **Status des Momentaufnahme-Agents anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="af738-138">In the Local Publications folder, right-click **AdvWorksSalesOrdersMerge**, and then click **View Snapshot Agent Status**.</span></span>  
  
3.  <span data-ttu-id="af738-139">Der aktuelle Status des Auftrags des Momentaufnahme-Agents für die Veröffentlichung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="af738-139">The current status of the Snapshot Agent job for the publication is displayed.</span></span> <span data-ttu-id="af738-140">Stellen Sie sicher, dass der Momentaufnahmeauftrag erfolgreich war, bevor Sie zur nächsten Lektion wechseln.</span><span class="sxs-lookup"><span data-stu-id="af738-140">Ensure that the snapshot job has succeeded before you continue to the next lesson.</span></span>  
  
### <a name="to-add-the-merge-agent-login-to-the-pal"></a><span data-ttu-id="af738-141">So fügen Sie der PAL die Anmeldung des Merge-Agents hinzu</span><span class="sxs-lookup"><span data-stu-id="af738-141">To add the Merge Agent login to the PAL</span></span>  
  
1.  <span data-ttu-id="af738-142">Stellen Sie in eine Verbindung mit dem Verleger her [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , erweitern Sie den Server Knoten, und erweitern Sie dann den Ordner **Replikation** .</span><span class="sxs-lookup"><span data-stu-id="af738-142">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="af738-143">Klicken Sie im Ordner Lokale Veröffentlichungen mit der rechten Maustaste auf **AdvWorksSalesOrdersMerge**und anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="af738-143">In the Local Publications folder, right-click **AdvWorksSalesOrdersMerge**, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="af738-144">Das Dialogfeld **Veröffentlichungseigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="af738-144">The **Publication Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="af738-145">Wählen Sie die Seite **Veröffentlichungszugriffsliste** aus und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="af738-145">Select the **Publication Access List** page, and click **Add**.</span></span>  
  
4.  <span data-ttu-id="af738-146">Wählen Sie im Dialogfeld „Veröffentlichungszugriff hinzufügen“ Folgendes aus: _<Computername>_**\repl_merge**. Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="af738-146">In the Add Publication Access dialog box, select _<Machine_Name>_**\repl_merge** and click **OK**.</span></span> <span data-ttu-id="af738-147">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="af738-147">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="af738-148">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="af738-148">Next Steps</span></span>  
 <span data-ttu-id="af738-149">Sie haben die Mergeveröffentlichung erfolgreich erstellt.</span><span class="sxs-lookup"><span data-stu-id="af738-149">You have successfully created the merge publication.</span></span> <span data-ttu-id="af738-150">Als Nächstes abonnieren Sie diese Veröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="af738-150">Next, you will subscribe to this publication.</span></span> <span data-ttu-id="af738-151">Siehe [Lektion 2: Erstellen eines Abonnements für die Mergeveröffentlichung](lesson-2-creating-a-subscription-to-the-merge-publication.md).</span><span class="sxs-lookup"><span data-stu-id="af738-151">See [Lesson 2: Creating a Subscription to the Merge Publication](lesson-2-creating-a-subscription-to-the-merge-publication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af738-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="af738-152">See Also</span></span>  
 <span data-ttu-id="af738-153">[Filtern von veröffentlichten Daten](publish/filter-published-data.md) </span><span class="sxs-lookup"><span data-stu-id="af738-153">[Filter Published Data](publish/filter-published-data.md) </span></span>  
 <span data-ttu-id="af738-154">[Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md) </span><span class="sxs-lookup"><span data-stu-id="af738-154">[Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md) </span></span>  
 [<span data-ttu-id="af738-155">Definieren eines Artikels</span><span class="sxs-lookup"><span data-stu-id="af738-155">Define an Article</span></span>](publish/define-an-article.md)  
  
  
