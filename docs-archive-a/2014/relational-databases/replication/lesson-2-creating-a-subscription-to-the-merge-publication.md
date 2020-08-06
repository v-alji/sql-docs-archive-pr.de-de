---
title: 'Lektion 2: Erstellen eines Abonnements für die Mergeveröffentlichung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 06722baa-9065-443e-b1d5-99036cf89074
author: rothja
ms.author: jroth
ms.openlocfilehash: 2ca4f9cdf9c40d80b428d65b4201be61c2ea3eae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619071"
---
# <a name="lesson-2-creating-a-subscription-to-the-merge-publication"></a><span data-ttu-id="a8c8d-102">Lektion 2: Erstellen eines Abonnements für die Mergeveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="a8c8d-102">Lesson 2: Creating a Subscription to the Merge Publication</span></span>
  <span data-ttu-id="a8c8d-103">In dieser Lektion erstellen Sie das Abonnement mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8c8d-103">In this lesson, you will create the subscription using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="a8c8d-104">Anschließend erstellen Sie Berechtigungen für die Abonnementdatenbank und generieren die gefilterte Datenmomentaufnahme für das neue Abonnement manuell.</span><span class="sxs-lookup"><span data-stu-id="a8c8d-104">You will then set permissions on the subscription database and manually generate the filtered data snapshot for the new subscription.</span></span> <span data-ttu-id="a8c8d-105">Für diese Lektion wird vorausgesetzt, dass Sie die vorherige Lektion abgeschlossen haben: [Lektion 1: Veröffentlichen von Daten mithilfe der Mergereplikation](lesson-1-publishing-data-using-merge-replication.md).</span><span class="sxs-lookup"><span data-stu-id="a8c8d-105">This lesson requires that you have completed the previous lesson, [Lesson 1: Publishing Data Using Merge Replication](lesson-1-publishing-data-using-merge-replication.md).</span></span>  
  
### <a name="to-create-the-subscription"></a><span data-ttu-id="a8c8d-106">So erstellen Sie das Abonnement</span><span class="sxs-lookup"><span data-stu-id="a8c8d-106">To create the subscription</span></span>  
  
1.  <span data-ttu-id="a8c8d-107">Stellen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Verbindung mit dem Abonnenten her, erweitern Sie den Serverknoten und den Ordner **Replikation** . Klicken Sie mit der rechten Maustaste auf den Ordner **Lokale Abonnements** , und klicken Sie anschließend auf **Neue Abonnements**.</span><span class="sxs-lookup"><span data-stu-id="a8c8d-107">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, expand the **Replication** folder, right-click the **Local Subscriptions** folder, and then click **New Subscriptions**.</span></span>  
  
     <span data-ttu-id="a8c8d-108">Der Assistent für neue Abonnements wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="a8c8d-108">The New Subscription Wizard launches.</span></span>  
  
2.  <span data-ttu-id="a8c8d-109">Klicken Sie auf der Seite **Veröffentlichung** in der Liste **Verleger** auf **SQL Server-Verleger suchen** .</span><span class="sxs-lookup"><span data-stu-id="a8c8d-109">On the **Publication** page, click **Find SQL Server Publisher** in the **Publisher** list.</span></span>  
  
3.  <span data-ttu-id="a8c8d-110">Geben Sie im Dialogfeld **Verbindung mit Server herstellen** im Feld **Servername** den Namen der Verlegerinstanz ein, und klicken Sie auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="a8c8d-110">In the **Connect to Server** dialog box, enter the name of the Publisher instance in the **Server name** box, and click **Connect**.</span></span>  
  
4.  <span data-ttu-id="a8c8d-111">Klicken Sie auf **AdvWorksSalesOrdersMerge**, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a8c8d-111">Click **AdvWorksSalesOrdersMerge**, and click **Next**.</span></span>  
  
5.  <span data-ttu-id="a8c8d-112">Klicken Sie auf der Seite Speicherort des Merge-Agents auf **Jeden Agent auf seinem Abonnenten ausführen**, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a8c8d-112">On the Merge Agent Location page, click **Run each agent at its Subscriber**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="a8c8d-113">Wählen Sie auf der Seite Abonnenten den Instanznamen des Abonnentenservers aus, und wählen Sie unter **Abonnementdatenbank**aus der Liste die Option **\<New Database>** aus.</span><span class="sxs-lookup"><span data-stu-id="a8c8d-113">On the Subscribers page, select the instance name of the Subscriber server, and under **Subscription Database**, select **\<New Database>** from the list.</span></span>  
  
7.  <span data-ttu-id="a8c8d-114">Geben Sie im Dialogfeld **Neue Datenbank** den Namen **SalesOrdersReplica** in das Feld **Datenbankname** ein, klicken Sie auf **OK**, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a8c8d-114">In the **New Database** dialog box, enter **SalesOrdersReplica** in the **Database name** box, click **OK**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="a8c8d-115">Klicken Sie auf der Seite Merge-Agent Sicherheit auf die Schaltfläche mit den Auslassungs Punkten (**...**), geben Sie \<_Machine_Name> im Feld **Prozess Konto** den Text _**\ repl_merge** ein, geben Sie das Kennwort für dieses Konto **Next** ein, klicken Sie auf **OK**und dann erneut **auf weiter**.</span><span class="sxs-lookup"><span data-stu-id="a8c8d-115">On the Merge Agent Security page, click the ellipsis (**...**) button, enter \<_Machine_Name>_**\repl_merge** in the **Process account** box, supply the password for this account, click **OK**, click **Next**, and then click **Next** again.</span></span>  
  
9. <span data-ttu-id="a8c8d-116">Wählen Sie auf der Seite Abonnements initialisieren aus der Liste **Initialisierungszeitpunkt** die Option **Bei der ersten Synchronisierung** aus, klicken Sie auf **Weiter**, und klicken Sie erneut auf **Weiter** .</span><span class="sxs-lookup"><span data-stu-id="a8c8d-116">On the Initialize Subscriptions page, select **At first synchronization** from the **Initialize When** list, click **Next**, and then click **Next** again.</span></span>  
  
10. <span data-ttu-id="a8c8d-117">Geben Sie auf der Seite HOST_NAME Werte `adventure-works\pamela0` im Feld **HOST_NAME Wert** den Wert ein, und klicken Sie dann auf **Fertig**stellen.</span><span class="sxs-lookup"><span data-stu-id="a8c8d-117">On the HOST_NAME Values page, enter a value of `adventure-works\pamela0` in the **HOST_NAME Value** box, and then click **Finish**.</span></span>  
  
11. <span data-ttu-id="a8c8d-118">Klicken Sie erneut auf **Fertig stellen** , und klicken Sie nach dem Erstellen des Abonnements auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="a8c8d-118">Click **Finish** again, and after the subscription is created, click **Close**.</span></span>  
  
### <a name="setting-database-permissions-at-the-subscriber"></a><span data-ttu-id="a8c8d-119">Festlegen der Datenbankberechtigungen auf dem Abonnenten</span><span class="sxs-lookup"><span data-stu-id="a8c8d-119">Setting database permissions at the Subscriber</span></span>  
  
1.  <span data-ttu-id="a8c8d-120">Stellen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Verbindung mit dem Abonnenten her, erweitern Sie **Datenbanken**, **SalesOrdersReplica**und **Sicherheit**, klicken Sie mit der rechten Maustaste auf **Benutzer**, und wählen Sie anschließend **Neuer Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="a8c8d-120">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand **Databases**, **SalesOrdersReplica**, and **Security**, right-click **Users**, and then select **New User**.</span></span>  
  
2.  <span data-ttu-id="a8c8d-121">Geben Sie **General** auf der Seite Allgemein \<_Machine_Name> _ **\ repl_merge** in das Feld **Benutzername** ein, klicken Sie auf die Schaltfläche mit den Auslassungs Punkten (**...**), klicken Sie auf **Durchsuchen**, wählen \<_Machine_Name> Sie _ **\ repl_merge**aus, klicken Sie auf **OK**, und klicken Sie dann auf **Namen überprüfen** **OK**</span><span class="sxs-lookup"><span data-stu-id="a8c8d-121">On the **General** page, enter \<_Machine_Name>_**\repl_merge** in the **User name** box, click the ellipsis (**...**) button, click **Browse**, select \<_Machine_Name>_**\repl_merge**, click **OK**, click **Check Names**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="a8c8d-122">Wählen Sie unter **Mitgliedschaft in Datenbankrollen**die **db_owner**-Rolle aus, und klicken Sie anschließend auf **OK** , um den Benutzer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a8c8d-122">In **Database role membership**, select **db_owner**, and then click **OK** to create the user.</span></span>  
  
### <a name="to-create-the-filtered-data-snapshot-for-the-subscription"></a><span data-ttu-id="a8c8d-123">So erstellen Sie die gefilterte Datenmomentaufnahme für das Abonnement</span><span class="sxs-lookup"><span data-stu-id="a8c8d-123">To create the filtered data snapshot for the subscription</span></span>  
  
1.  <span data-ttu-id="a8c8d-124">Stellen Sie in eine Verbindung mit dem Verleger her [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , erweitern Sie den Server Knoten, und erweitern Sie dann den Ordner **Replikation** .</span><span class="sxs-lookup"><span data-stu-id="a8c8d-124">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="a8c8d-125">Klicken Sie im Ordner **Lokale Veröffentlichungen** mit der rechten Maustaste auf die **AdvWorksSalesOrdersMerge** -Veröffentlichung, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="a8c8d-125">In the **Local Publications** folder, right-click the **AdvWorksSalesOrdersMerge** publication, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="a8c8d-126">Das Dialogfeld **Veröffentlichungseigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a8c8d-126">The **Publication Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="a8c8d-127">Wählen Sie die Seite **Datenpartitionen** aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a8c8d-127">Select the **Data Partitions** page, and click **Add**.</span></span>  
  
4.  <span data-ttu-id="a8c8d-128">Geben Sie im Dialogfeld **Daten Partition hinzufügen** `adventure-works\pamela0` im Feld **HOST_NAME Wert** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8c8d-128">In the **Add Data Partition** dialog box, type `adventure-works\pamela0` in the **HOST_NAME Value** box, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="a8c8d-129">Wählen Sie die neu hinzugefügte Partition aus, klicken Sie auf **Die ausgewählten Momentaufnahmen jetzt generieren**, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8c8d-129">Select the newly added partition, click **Generate the selected snapshots now**, and then click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a8c8d-130">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a8c8d-130">Next Steps</span></span>  
 <span data-ttu-id="a8c8d-131">Sie haben erfolgreich ein Abonnement für die Mergeveröffentlichung erstellt und die gefilterte Momentaufnahme für die Datenpartition des neuen Abonnements generiert, damit diese verfügbar ist, wenn das Abonnement initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="a8c8d-131">You have successfully created a subscription to the merge publication and generated the filtered snapshot for the new subscription's data partition so that it will be available when the subscription is initialized.</span></span> <span data-ttu-id="a8c8d-132">Als Nächstes gewähren Sie dem Merge-Agent Rechte für die Abonnementdatenbank und führen den Merge-Agent aus, um die Synchronisierung zu starten und das Abonnement zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="a8c8d-132">Next, you will grant rights to the Merge Agent on the subscription database and run the Merge Agent to start synchronization and initialize the subscription.</span></span> <span data-ttu-id="a8c8d-133">Weitere Informationen finden Sie unter [Lektion 3: Synchronisieren des Abonnements für die Mergeveröffentlichung](lesson-3-synchronizing-the-subscription-to-the-merge-publication.md).</span><span class="sxs-lookup"><span data-stu-id="a8c8d-133">See [Lesson 3: Synchronizing the Subscription to the Merge Publication](lesson-3-synchronizing-the-subscription-to-the-merge-publication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8c8d-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a8c8d-134">See Also</span></span>  
 <span data-ttu-id="a8c8d-135">[Abonnieren von Veröffentlichungen](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="a8c8d-135">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 <span data-ttu-id="a8c8d-136">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="a8c8d-136">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 [<span data-ttu-id="a8c8d-137">Momentaufnahmen für Mergeveröffentlichungen mit parametrisierten Filtern</span><span class="sxs-lookup"><span data-stu-id="a8c8d-137">Snapshots for Merge Publications with Parameterized Filters</span></span>](snapshots-for-merge-publications-with-parameterized-filters.md)  
  
  
