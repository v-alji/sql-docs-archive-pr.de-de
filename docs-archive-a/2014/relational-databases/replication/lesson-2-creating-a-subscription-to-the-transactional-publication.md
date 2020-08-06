---
title: 'Lektion 2: Erstellen eines Abonnements für die Transaktionsveröffentlichung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 5995b7d2-7c06-46f5-b96c-2bee879bcda2
author: rothja
ms.author: jroth
ms.openlocfilehash: dbf40fa259302dffdd6c0b8e8717b7c35b0cf92d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609067"
---
# <a name="lesson-2-creating-a-subscription-to-the-transactional-publication"></a><span data-ttu-id="61173-102">Lektion 2: Erstellen eines Abonnements für die Transaktionsveröffentlichung</span><span class="sxs-lookup"><span data-stu-id="61173-102">Lesson 2: Creating a Subscription to the Transactional Publication</span></span>
  <span data-ttu-id="61173-103">In dieser Lektion erstellen Sie mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]ein Abonnement.</span><span class="sxs-lookup"><span data-stu-id="61173-103">In this lesson, you will create a subscription using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="61173-104">Für diese Lektion wird vorausgesetzt, dass Sie die vorherige Lektion abgeschlossen haben: [Lektion 1: Veröffentlichen von Daten mithilfe der Transaktionsreplikation](lesson-1-publishing-data-using-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="61173-104">This lesson requires that you have completed the previous lesson, [Lesson 1: Publishing Data Using Transactional Replication](lesson-1-publishing-data-using-transactional-replication.md).</span></span>  
  
### <a name="to-create-the-subscription"></a><span data-ttu-id="61173-105">So erstellen Sie das Abonnement</span><span class="sxs-lookup"><span data-stu-id="61173-105">To create the subscription</span></span>  
  
1.  <span data-ttu-id="61173-106">Stellen Sie in eine Verbindung mit dem Verleger her [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , erweitern Sie den Server Knoten, und erweitern Sie dann den Ordner **Replikation** .</span><span class="sxs-lookup"><span data-stu-id="61173-106">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="61173-107">Klicken Sie im Ordner **Lokale Veröffentlichungen** mit der rechten Maustaste auf die **AdvWorksProductTrans** -Veröffentlichung und anschließend auf **Neue Abonnements**.</span><span class="sxs-lookup"><span data-stu-id="61173-107">In the **Local Publications** folder, right-click the **AdvWorksProductTrans** publication, and then click **New Subscriptions**.</span></span>  
  
     <span data-ttu-id="61173-108">Der Assistent für neue Abonnements wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="61173-108">The New Subscription Wizard launches.</span></span>  
  
3.  <span data-ttu-id="61173-109">Wählen Sie auf der Seite Veröffentlichung die **AdvWorksProductTrans**-Veröffentlichung aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="61173-109">On the Publication page, select **AdvWorksProductTrans**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="61173-110">Wählen Sie auf der Seite Speicherort des Verteilungs-Agents die Option **Alle Agents auf dem Verteiler ausführen**aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="61173-110">On the Distribution Agent Location page, select **Run all agents at the Distributor**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="61173-111">Wenn der Name der Abonnenteninstanz auf der Seite Abonnenten nicht angezeigt wird, klicken Sie auf **Abonnent hinzufügen**, klicken Sie auf **SQL Server-Abonnenten hinzufügen**, geben Sie den Namen der Abonnenteninstanz im Dialogfeld **Verbindung mit Server herstellen** ein, und klicken Sie dann auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="61173-111">On the Subscribers page, if the name of the Subscriber instance is not displayed, click **Add Subscriber**, click **Add SQL Server Subscriber**, enter the Subscriber instance name in the **Connect to Server** dialog box, and then click **Connect**.</span></span>  
  
6.  <span data-ttu-id="61173-112">Wählen Sie auf der Seite Abonnenten den Instanznamen des Abonnenten Servers aus, und wählen Sie **\<New Database>** unter **Abonnement Datenbank**aus.</span><span class="sxs-lookup"><span data-stu-id="61173-112">On the Subscribers page, select the instance name of the Subscriber server, and select **\<New Database>** under **Subscription Database**.</span></span>  
  
7.  <span data-ttu-id="61173-113">Geben Sie im Dialogfeld **Neue Datenbank** den Namen **ProductReplica** in das Feld **Datenbankname** ein, klicken Sie auf **OK**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="61173-113">On the **New Database** dialog box, enter **ProductReplica** in the **Database name** box, click **OK**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="61173-114">Klicken Sie im Dialogfeld **Verteilungs-Agent Sicherheit** auf die Schaltfläche mit den Auslassungs Punkten (**...**), geben Sie \<_Machine_Name> im Feld **Prozess Konto** den Text _**\ repl_distribution** ein, geben Sie das Kennwort für dieses Konto ein, klicken Sie auf **OK**und dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="61173-114">In the **Distribution Agent Security** dialog box, click the ellipsis (**...**) button, enter \<_Machine_Name>_**\repl_distribution** in the **Process account** box, enter the password for this account, click **OK**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="61173-115">Klicken Sie auf **Fertig stellen** , um auf den verbleibenden Seiten die Standardwerte zu übernehmen und den Assistenten zu beenden.</span><span class="sxs-lookup"><span data-stu-id="61173-115">Click **Finish** to accept the default values on the remaining pages and complete the wizard.</span></span>  
  
### <a name="setting-database-permissions-at-the-subscriber"></a><span data-ttu-id="61173-116">Festlegen der Datenbankberechtigungen auf dem Abonnenten</span><span class="sxs-lookup"><span data-stu-id="61173-116">Setting database permissions at the Subscriber</span></span>  
  
1.  <span data-ttu-id="61173-117">Stellen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Verbindung mit dem Abonnenten her, erweitern Sie **Datenbanken**, **ProductReplica**und **Sicherheit**, klicken Sie mit der rechten Maustaste auf **Benutzer**, und wählen Sie anschließend **Neuer Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="61173-117">Connect to the Subscriber in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand **Databases**, **ProductReplica**, and **Security**, right-click **Users**, and then select **New User**.</span></span>  
  
2.  <span data-ttu-id="61173-118">Klicken Sie auf der Seite **Allgemein** in der Liste **Benutzertyp** auf **Windows-Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="61173-118">On the **General** page, in the **User type** list, select **Windows user**.</span></span>  
  
3.  <span data-ttu-id="61173-119">Wählen Sie das Feld **Benutzername** aus, **und klicken Sie**auf die Schaltfläche mit den Auslassungs Punkten (...). Geben Sie im Feld **Geben Sie die zu ausgewäfenden Objektnamen** ein den <Machine_Name>**\ repl_distribution**ein, klicken Sie auf **Namen überprüfen**</span><span class="sxs-lookup"><span data-stu-id="61173-119">Select the **User name** box and click the ellipsis (...) button, in the **Enter the object name to select** box type <Machine_Name>**\repl_distribution**, click **Check Names**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="61173-120">Wählen Sie auf der Seite **Mitgliedschaft** im Bereich **Mitgliedschaft in Datenbankrollen** die **db_owner**-Rolle aus, und klicken Sie anschließend auf **OK** , um den Benutzer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="61173-120">On the **Membership** page, in **Database role membership** area, select **db_owner**, and then click **OK** to create the user.</span></span>  
  
### <a name="to-view-the-synchronization-status-of-the-subscription"></a><span data-ttu-id="61173-121">So zeigen Sie den Synchronisierungsstatus des Abonnements an</span><span class="sxs-lookup"><span data-stu-id="61173-121">To view the synchronization status of the subscription</span></span>  
  
1.  <span data-ttu-id="61173-122">Stellen Sie in eine Verbindung mit dem Verleger her [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , erweitern Sie den Server Knoten, und erweitern Sie dann den Ordner **Replikation** .</span><span class="sxs-lookup"><span data-stu-id="61173-122">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the server node, and then expand the **Replication** folder.</span></span>  
  
2.  <span data-ttu-id="61173-123">Erweitern Sie im Ordner **Lokale Veröffentlichungen** die **AdvWorksProductTrans** -Veröffentlichung, klicken Sie mit der rechten Maustaste auf das Abonnement in der **ProductReplica** -Datenbank und anschließend auf **Synchronisierungsstatus anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="61173-123">In the **Local Publications** folder, expand the **AdvWorksProductTrans** publication, right-click the subscription in the **ProductReplica** database, and then click **View Synchronization Status**.</span></span>  
  
     <span data-ttu-id="61173-124">Der aktuelle Synchronisierungsstatus des Abonnements wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="61173-124">The current synchronization status of the subscription is displayed.</span></span>  
  
3.  <span data-ttu-id="61173-125">Wenn das Abonnement unter **AdvWorksProductTrans**nicht angezeigt wird, drücken Sie F5, um die Liste zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="61173-125">If the subscription is not visible under **AdvWorksProductTrans**, press F5 to refresh the list.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="61173-126">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="61173-126">Next Steps</span></span>  
 <span data-ttu-id="61173-127">Sie haben erfolgreich ein Abonnement für die Transaktionsveröffentlichung erstellt.</span><span class="sxs-lookup"><span data-stu-id="61173-127">You have successfully created a subscription to the transactional publication.</span></span> <span data-ttu-id="61173-128">Da der Verteilungs-Agent für dieses Abonnement ständig ausgeführt wird, wird das Abonnement initialisiert, wenn es erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="61173-128">Because the Distribution Agent for this subscription runs continuously, the subscription is initialized when it is created.</span></span> <span data-ttu-id="61173-129">Als Nächstes verwenden Sie Überwachungstoken, um zu überprüfen, ob die Änderungen auf dem Abonnenten repliziert werden, und um die Latenzzeit zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="61173-129">Next, you will use tracer tokens to verify that changes are being replicated to the Subscriber and to determine latency.</span></span> <span data-ttu-id="61173-130">Siehe [Lesson 3: Validating the Subscription and Measuring Latency](lesson-3-validating-the-subscription-and-measuring-latency.md).</span><span class="sxs-lookup"><span data-stu-id="61173-130">See [Lesson 3: Validating the Subscription and Measuring Latency](lesson-3-validating-the-subscription-and-measuring-latency.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61173-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="61173-131">See Also</span></span>  
 <span data-ttu-id="61173-132">[Initialisieren eines Abonnements mit einer Momentaufnahme](initialize-a-subscription-with-a-snapshot.md) </span><span class="sxs-lookup"><span data-stu-id="61173-132">[Initialize a Subscription with a Snapshot](initialize-a-subscription-with-a-snapshot.md) </span></span>  
 <span data-ttu-id="61173-133">[Create a Push Subscription](create-a-push-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="61173-133">[Create a Push Subscription](create-a-push-subscription.md) </span></span>  
 [<span data-ttu-id="61173-134">Abonnieren von Veröffentlichungen</span><span class="sxs-lookup"><span data-stu-id="61173-134">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
