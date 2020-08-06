---
title: Erstellen von Skripts für die Replikation | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- scripts [SQL Server replication], replication objects
- merge replication scripting [SQL Server replication]
- replication [SQL Server], scripting
- snapshot replication [SQL Server], scripting
- scripts [SQL Server replication]
- transactional replication, scripting
ms.assetid: e50fac44-54c0-470c-a4ea-9c111fa4322b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2e865e2664a399bca4738c1fc157bef176f35e96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608516"
---
# <a name="scripting-replication"></a><span data-ttu-id="d5f3b-102">Erstellen von Skripts für die Replikation</span><span class="sxs-lookup"><span data-stu-id="d5f3b-102">Scripting Replication</span></span>
  <span data-ttu-id="d5f3b-103">Für die Replikationskomponenten in einer Topologie sollten im Rahmen des Plans zur Wiederherstellung im Notfall Skripts erstellt werden; diese können dann auch zur Automatisierung sich wiederholender Tasks verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-103">All replication components in a topology should be scripted as part of a disaster recovery plan, and scripts can also be used to automate repetitive tasks.</span></span> <span data-ttu-id="d5f3b-104">Skripts enthalten die gespeicherten Transact-SQL-Systemprozeduren, die zum Implementieren der Replikationskomponenten im Skript, wie z. B. der Veröffentlichungen oder Abonnements, benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-104">A script contains the Transact-SQL system stored procedures necessary to implement the replication component(s) scripted, such as a publication or subscription.</span></span> <span data-ttu-id="d5f3b-105">Skripts können in einem Assistenten (z. B. dem Assistenten für neue Veröffentlichungen) oder nach dem Erstellen einer Komponente in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-105">Scripts can be created in a wizard (such as the New Publication Wizard) or in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] after you create a component.</span></span> <span data-ttu-id="d5f3b-106">Sie können das Skript mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder **sqlcmd**anzeigen, ändern oder ausführen.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-106">You can view, modify, and run the script using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or **sqlcmd**.</span></span> <span data-ttu-id="d5f3b-107">Skripts können mit Sicherungsdateien gespeichert und dann verwendet werden, wenn eine Replikationstopologie erneut konfiguriert werden muss.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-107">Scripts can be stored with backup files to be used in case a replication topology must be reconfigured.</span></span>  
  
 <span data-ttu-id="d5f3b-108">Wenn die Eigenschaften einer Komponente geändert werden, muss das Skript für diese Komponente neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-108">A component should be re-scripted if any property changes are made.</span></span> <span data-ttu-id="d5f3b-109">Wenn Sie bei einer Transaktionsreplikation benutzerdefinierte gespeicherte Prozeduren verwenden, sollte zusammen mit den Skripts eine Kopie aller dieser Prozeduren gespeichert werden. Nach Änderungen an der Prozedur sollte die Kopie dann aktualisiert werden (zu Prozedurupdates kommt es in der Regel nach Schemaänderungen oder wenn sich die Anwendungsanforderungen ändern).</span><span class="sxs-lookup"><span data-stu-id="d5f3b-109">If you use custom stored procedures with transactional replication, a copy of each procedure should be stored with the scripts; the copy should be updated if the procedure changes (procedures are typically updated due to schema changes or changing application requirements).</span></span> <span data-ttu-id="d5f3b-110">Weitere Informationen zu benutzerdefinierten Prozeduren finden Sie unter [Angeben der Weitergabemethode für Änderungen bei Transaktionsartikeln](transactional/transactional-articles-specify-how-changes-are-propagated.md).</span><span class="sxs-lookup"><span data-stu-id="d5f3b-110">For more information about custom procedures, see [Specify How Changes Are Propagated for Transactional Articles](transactional/transactional-articles-specify-how-changes-are-propagated.md).</span></span>  
  
 <span data-ttu-id="d5f3b-111">Bei Mergeveröffentlichungen, die parametrisierte Filter verwenden, enthalten Veröffentlichungsskripts die Aufrufe von gespeicherten Prozeduren zum Erstellen von Datenpartitionen.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-111">For merge publications that use parameterized filters, publication scripts contain the stored procedure calls to create data partitions.</span></span> <span data-ttu-id="d5f3b-112">Die Skripts stellen einen Verweis für die erstellten Partitionen bereit und ermöglichen das erneute Erstellen von Partitionen, falls dies erforderlich wird.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-112">The script provides a reference for the partitions created and a way in which to re-create one or more partitions if necessary.</span></span>  
  
## <a name="example-of-automating-a-task-with-scripts"></a><span data-ttu-id="d5f3b-113">Beispiel für das Automatisieren einer Aufgabe durch Skripts</span><span class="sxs-lookup"><span data-stu-id="d5f3b-113">Example of Automating a Task with Scripts</span></span>  
 <span data-ttu-id="d5f3b-114">[!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)]implementiert die Mergereplikation, um Daten an die Außendienstmitarbeiter zu verteilen.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-114">Consider [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)], which implements merge replication to distribute data to its remote sales force.</span></span> <span data-ttu-id="d5f3b-115">Ein Vertriebsmitarbeiter lädt mithilfe von Pullabonnements alle Informationen zu den Kunden in seinem Vertriebsgebiet herunter.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-115">A sales representative downloads all the data that pertains to the customers in her territory using pull subscriptions.</span></span> <span data-ttu-id="d5f3b-116">Im Offlinebetrieb kann er die Daten aktualisieren und neue Kunden und Bestellungen eingeben.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-116">When working offline, the sales representative updates data and enters new customers and orders.</span></span> <span data-ttu-id="d5f3b-117">Da [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] über mehr als 50 Vertriebsmitarbeiter in verschiedenen Gebieten verfügt, wäre das Erstellen der verschiedenen Abonnements auf den einzelnen Abonnenten mit dem Assistenten für neue Abonnements recht zeitaufwendig.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-117">Because [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] has more than fifty sales representatives in different territories, it would be time-consuming to create the different subscriptions at each Subscriber with the New Subscription Wizard.</span></span> <span data-ttu-id="d5f3b-118">Stattdessen kann der Replikationsadministrator die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="d5f3b-118">Instead, the replication administrator can follow these steps:</span></span>  
  
1.  <span data-ttu-id="d5f3b-119">Einrichten der notwendigen Mergeveröffentlichungen mit Partitionen nach Vertriebsmitarbeiter oder Vertriebsgebiet</span><span class="sxs-lookup"><span data-stu-id="d5f3b-119">Set up the necessary merge publications with partitions based on the sales representative or their territory.</span></span>  
  
2.  <span data-ttu-id="d5f3b-120">Erstellen eines Pullabonnements für einen Abonnenten</span><span class="sxs-lookup"><span data-stu-id="d5f3b-120">Create a pull subscription for one Subscriber.</span></span>  
  
3.  <span data-ttu-id="d5f3b-121">Generieren eines Skripts auf der Grundlage dieses Pullabonnements</span><span class="sxs-lookup"><span data-stu-id="d5f3b-121">Generate a script based on that pull subscription.</span></span>  
  
4.  <span data-ttu-id="d5f3b-122">Ändern des Skripts durch Ändern von Werten, wie z. B. des Namens des Abonnenten</span><span class="sxs-lookup"><span data-stu-id="d5f3b-122">Modify the script, changing such values as the name of the Subscriber.</span></span>  
  
5.  <span data-ttu-id="d5f3b-123">Ausführen des Skripts auf mehreren Abonnenten zum Generieren der erforderlichen Pullabonnements</span><span class="sxs-lookup"><span data-stu-id="d5f3b-123">Run the script at multiple Subscribers to generate the required pull subscriptions.</span></span>  
  
## <a name="script-replication-objects"></a><span data-ttu-id="d5f3b-124">Skriptreplikationsobjekte</span><span class="sxs-lookup"><span data-stu-id="d5f3b-124">Script Replication Objects</span></span>  
 <span data-ttu-id="d5f3b-125">Skripts für Replikationsobjekte lassen sich über die Replikations-Assistenten bzw. den Ordner **Replikation** in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] erstellen.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-125">Script replication objects from the replication wizards or from the **Replication** folder in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="d5f3b-126">Wenn Sie die Skripterstellung über die Assistenten vornehmen, können Sie entweder Objekte erstellen und Skripts für sie erstellen oder nur Skripts für sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-126">If you script from the wizards, you can choose to create objects and script them, or you can choose only to script them.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d5f3b-127">Bei der Erstellung von Skripts für Kennwörter wird stets NULL angegeben.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-127">All passwords are scripted as NULL.</span></span> <span data-ttu-id="d5f3b-128">Benutzer sollten nach Möglichkeit dazu aufgefordert werden, Anmeldeinformationen zur Laufzeit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-128">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="d5f3b-129">Wenn Sie Anmeldeinformationen in einer Skriptdatei speichern, müssen Sie die Datei schützen, um unberechtigtem Zugriff vorzubeugen.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-129">If you store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
 <span data-ttu-id="d5f3b-130">Weitere Informationen zum Verwenden der Replikations-Assistenten finden Sie hier:</span><span class="sxs-lookup"><span data-stu-id="d5f3b-130">For more information about using the replication wizards, see:</span></span>  
  
-   [<span data-ttu-id="d5f3b-131">Konfigurieren der Veröffentlichung und der Verteilung</span><span class="sxs-lookup"><span data-stu-id="d5f3b-131">Configure Publishing and Distribution</span></span>](configure-publishing-and-distribution.md)  
  
-   [<span data-ttu-id="d5f3b-132">Erstellen einer Veröffentlichung</span><span class="sxs-lookup"><span data-stu-id="d5f3b-132">Create a Publication</span></span>](publish/create-a-publication.md)  
  
-   [<span data-ttu-id="d5f3b-133">Erstellen eines Pushabonnements</span><span class="sxs-lookup"><span data-stu-id="d5f3b-133">Create a Push Subscription</span></span>](create-a-push-subscription.md)  
  
-   [<span data-ttu-id="d5f3b-134">Erstellen eines Pullabonnements</span><span class="sxs-lookup"><span data-stu-id="d5f3b-134">Create a Pull Subscription</span></span>](create-a-pull-subscription.md)  
  
#### <a name="to-script-an-object-from-a-replication-wizard"></a><span data-ttu-id="d5f3b-135">So erstellen Sie ein Skript für ein Objekt vom Replikations-Assistenten aus</span><span class="sxs-lookup"><span data-stu-id="d5f3b-135">To script an object from a replication wizard</span></span>  
  
1.  <span data-ttu-id="d5f3b-136">Aktivieren Sie auf der Seite **Aktionen des Assistenten** das entsprechende Kontrollkästchen für den Assistenten:</span><span class="sxs-lookup"><span data-stu-id="d5f3b-136">On the **Wizard Actions** page of a wizard, select the check box appropriate for the wizard:</span></span>  
  
    -   <span data-ttu-id="d5f3b-137">**Skriptdatei mit Schritten zur Veröffentlichungserstellung generieren**</span><span class="sxs-lookup"><span data-stu-id="d5f3b-137">**Generate a script file with steps to create a publication**</span></span>  
  
    -   <span data-ttu-id="d5f3b-138">**Skriptdatei mit Schritten zur Abonnentenerstellung generieren**</span><span class="sxs-lookup"><span data-stu-id="d5f3b-138">**Generate a script file with steps to create the subscription(s)**</span></span>  
  
    -   <span data-ttu-id="d5f3b-139">**Skriptdatei mit Schritten zur Verteilungskonfiguration generieren**</span><span class="sxs-lookup"><span data-stu-id="d5f3b-139">**Generate a script file with steps to configure distribution**</span></span>  
  
2.  <span data-ttu-id="d5f3b-140">Geben Sie Optionen auf der Seite **Skriptdatei** an.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-140">Specify options on the **Script File Properties** page.</span></span>  
  
3.  <span data-ttu-id="d5f3b-141">Schließen Sie den Assistenten ab.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-141">Complete the wizard.</span></span>  
  
#### <a name="to-script-an-object-from-management-studio"></a><span data-ttu-id="d5f3b-142">So erstellen Sie ein Skript für ein Objekt von Management Studio aus</span><span class="sxs-lookup"><span data-stu-id="d5f3b-142">To script an object from Management Studio</span></span>  
  
1.  <span data-ttu-id="d5f3b-143">Stellen Sie in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]eine Verbindung mit dem Verteiler, Verleger oder Abonnenten her, und erweitern Sie dann den Serverknoten.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-143">Connect to the Distributor, Publisher, or Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="d5f3b-144">Erweitern Sie den Ordner **Replikation** , und erweitern Sie dann den Ordner **Lokale Veröffentlichungen** oder **Lokale Abonnements** .</span><span class="sxs-lookup"><span data-stu-id="d5f3b-144">Expand the **Replication** folder, and then expand the **Local Publications** folder or the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="d5f3b-145">Klicken Sie mit der rechten Maustaste auf eine Veröffentlichung oder ein Abonnement, und klicken Sie dann auf **Skripts generieren**.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-145">Right-click a publication or subscription, and then click **Generate Scripts**.</span></span>  
  
4.  <span data-ttu-id="d5f3b-146">Geben Sie Optionen im Dialogfeld **SQL-Skript generieren – \<ReplicationObject>** an.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-146">Specify options in the **Generate SQL Script - \<ReplicationObject>** dialog box.</span></span>  
  
5.  <span data-ttu-id="d5f3b-147">Klicken Sie auf **Skript in Datei schreiben**.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-147">Click **Script to File**.</span></span>  
  
6.  <span data-ttu-id="d5f3b-148">Geben Sie im Dialogfeld **Speicherort der Skriptdatei** einen Dateinamen ein, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-148">Enter a file name in the **Script File Location** dialog box, and then click **Save**.</span></span> <span data-ttu-id="d5f3b-149">Daraufhin wird eine Statusmeldung eingeblendet.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-149">A status message is displayed.</span></span>  
  
7.  <span data-ttu-id="d5f3b-150">Klicken Sie auf **OK**und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-150">Click **OK**, and then click **Close**.</span></span>  
  
#### <a name="to-script-multiple-objects-from-management-studio"></a><span data-ttu-id="d5f3b-151">So erstellen Sie ein Skript für mehrere Objekte vom Management Studio aus</span><span class="sxs-lookup"><span data-stu-id="d5f3b-151">To script multiple objects from Management Studio</span></span>  
  
1.  <span data-ttu-id="d5f3b-152">Stellen Sie in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]eine Verbindung mit dem Verteiler, Verleger oder Abonnenten her, und erweitern Sie dann den Serverknoten.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-152">Connect to the Distributor, Publisher, or Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="d5f3b-153">Klicken Sie mit der rechten Maustaste auf den Ordner **Replikation** , und klicken Sie dann auf **Skripts generieren**.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-153">Right-click the **Replication** folder, and then click **Generate Scripts**.</span></span>  
  
3.  <span data-ttu-id="d5f3b-154">Geben Sie Optionen im Dialogfeld **SQL-Skript generieren** an.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-154">Specify options in the **Generate SQL Script** dialog box.</span></span>  
  
4.  <span data-ttu-id="d5f3b-155">Klicken Sie auf **Skript in Datei schreiben**.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-155">Click **Script to File**.</span></span>  
  
5.  <span data-ttu-id="d5f3b-156">Geben Sie im Dialogfeld **Speicherort der Skriptdatei** einen Dateinamen ein, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-156">Enter a file name in the **Script File Location** dialog box, and then click **Save**.</span></span> <span data-ttu-id="d5f3b-157">Daraufhin wird eine Statusmeldung eingeblendet.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-157">A status message is displayed.</span></span>  
  
6.  <span data-ttu-id="d5f3b-158">Klicken Sie auf **OK** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="d5f3b-158">Click **OK, and then** click **Close**.</span></span>  
  
  
