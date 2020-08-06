---
title: 'Lektion 3: Konfigurieren der Verteilung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: f248984a-0b59-4c2f-a56d-31f8dafe72b5
author: rothja
ms.author: jroth
ms.openlocfilehash: 52b284b6186e599b7afe73bd37ab0a8348ec38da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723697"
---
# <a name="lesson-3-configuring-distribution"></a><span data-ttu-id="39654-102">Lektion 3: Konfigurieren der Verteilung</span><span class="sxs-lookup"><span data-stu-id="39654-102">Lesson 3: Configuring Distribution</span></span>
  <span data-ttu-id="39654-103">In dieser Lektion konfigurieren Sie die Verteilung auf dem Verleger und legen die erforderlichen Berechtigungen für die Verteilungs- und Veröffentlichungsdatenbanken fest.</span><span class="sxs-lookup"><span data-stu-id="39654-103">In this lesson, you will configure distribution at the Publisher and set the required permissions on the publication and distribution databases.</span></span> <span data-ttu-id="39654-104">Wenn der Verteiler bereits konfiguriert wurde, müssen die Veröffentlichung und die Verteilung erst deaktiviert werden, bevor Sie mit dieser Lektion beginnen.</span><span class="sxs-lookup"><span data-stu-id="39654-104">If you have already configured the Distributor, you must first disable publishing and distribution before you begin this lesson.</span></span> <span data-ttu-id="39654-105">Führen Sie diese Lektion nicht aus, wenn Sie eine vorhandene Replikationstopologie beibehalten müssen.</span><span class="sxs-lookup"><span data-stu-id="39654-105">Do not do this if you must retain an existing replication topology.</span></span>  
  
 <span data-ttu-id="39654-106">Das Konfigurieren eines Verlegers mit einem Remoteverteiler wird in diesem Lernprogramm nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="39654-106">Configuring a Publisher with a remote Distributor is outside the scope of this tutorial.</span></span>  
  
### <a name="configuring-distribution-at-the-publisher"></a><span data-ttu-id="39654-107">Konfigurieren der Verteilung auf dem Verleger</span><span class="sxs-lookup"><span data-stu-id="39654-107">Configuring distribution at the Publisher</span></span>  
  
1.  <span data-ttu-id="39654-108">Stellen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Verbindung mit dem Verleger her, und erweitern Sie dann den Serverknoten.</span><span class="sxs-lookup"><span data-stu-id="39654-108">Connect to the Publisher in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="39654-109">Klicken Sie mit der rechten Maustaste auf den Ordner **Replikation** , und klicken Sie anschließend auf **Verteilung konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="39654-109">Right-click the **Replication** folder and click **Configure Distribution**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="39654-110">Wenn Sie \*\*localhost[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anstelle des tatsächlichen Servernamens verwendet haben, um eine Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herzustellen, werden Sie in einer Warnmeldung darauf hingewiesen, dass \*\* nicht in der Lage ist, eine Verbindung mit dem Server **"localhost"** herzustellen.</span><span class="sxs-lookup"><span data-stu-id="39654-110">If you have connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using **localhost** rather than the actual server name you will be prompted with a warning that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is unable to connect to server **'localhost'**.</span></span> <span data-ttu-id="39654-111">Klicken Sie im Warnungs Dialogfeld auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="39654-111">Click **OK** on the warning dialog.</span></span> <span data-ttu-id="39654-112">Ändern Sie im Dialogfeld **Verbindung mit Server herstellen** die Angabe für **Servername** von **localhost** in den Namen des Servers.</span><span class="sxs-lookup"><span data-stu-id="39654-112">In the **Connect to Server** dialog change the **Server name** from **localhost** to the name of your server.</span></span> <span data-ttu-id="39654-113">Klicken Sie auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="39654-113">Click **Connect**.</span></span>  
  
     <span data-ttu-id="39654-114">Der Verteilungskonfigurations-Assistent wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="39654-114">The Distribution Configuration Wizard launches.</span></span>  
  
3.  <span data-ttu-id="39654-115">Wählen Sie auf der Seite **Verteiler** die Option **"** _\<ServerName>_ **" wird als eigener Verteiler fungieren. SQL Server erstellt eine Verteilungs Datenbank und ein Protokoll**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="39654-115">On the **Distributor** page, select **'**_\<ServerName>_**' will act as its own Distributor; SQL Server will create a distribution database and log**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="39654-116">Wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht ausgeführt wird, wählen Sie auf der Seite [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**Agent-Start** die Option **Ja**, den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent zum automatischen Starten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="39654-116">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not running, on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**Agent Start** page, select **Yes**, configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service to start automatically.</span></span> <span data-ttu-id="39654-117">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="39654-117">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="39654-118">Geben Sie **\\\\** \<_Machine_Name> im Textfeld **Momentaufnahme Ordner** _**\repldata** ein, wobei \<*Machine_Name> \* der Name des Verlegers ist, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="39654-118">Enter **\\\\**\<_Machine_Name>_**\repldata** in the **Snapshot folder** text box, where \<*Machine_Name>\* is the name of the Publisher, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="39654-119">Übernehmen Sie die Standardwerte auf den restlichen Seiten des Assistenten.</span><span class="sxs-lookup"><span data-stu-id="39654-119">Accept the default values on the remaining pages of the wizard.</span></span>  
  
7.  <span data-ttu-id="39654-120">Klicken Sie auf **Fertig stellen** , um die Verteilung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="39654-120">Click **Finish** to enable distribution.</span></span>  
  
### <a name="setting-database-permissions-at-the-publisher"></a><span data-ttu-id="39654-121">Festlegen der Datenbankberechtigungen auf dem Verleger</span><span class="sxs-lookup"><span data-stu-id="39654-121">Setting database permissions at the Publisher</span></span>  
  
1.  <span data-ttu-id="39654-122">Erweitern Sie in die Option [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **Sicherheit**, klicken Sie mit der rechten Maustaste auf **Anmeldungen**, und wählen Sie dann **neue Anmeldung**aus.</span><span class="sxs-lookup"><span data-stu-id="39654-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand **Security**, right-click **Logins**, and then select **New Login**.</span></span>  
  
2.  <span data-ttu-id="39654-123">Klicken Sie auf der Seite **Allgemein** auf **Suchen**, geben Sie \<_Machine_Name> _**\ repl_snapshot** in das Feld **Geben Sie die zu ausgewäfenden Objektnamen** ein ein, wobei \<*Machine_Name> \* der Name des lokalen Verleger Servers ist. Klicken Sie auf **Namen überprüfen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="39654-123">On the **General** page, click **Search**, enter \<_Machine_Name>_**\repl_snapshot** in the **Enter the object name to select** box, where \<*Machine_Name>\* is the name of the local Publisher server, click **Check Names**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="39654-124">Wählen Sie auf der Seite **Benutzer Zuordnung** in der Liste **Benutzer, die dieser Anmeldung zugeordnet** sind sowohl die **Verteilungs** -als auch die- [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="39654-124">On the **User Mapping** page, in the **Users mapped to this login** list select both the **distribution** and [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] databases.</span></span>  
  
     <span data-ttu-id="39654-125">Wählen Sie in der Liste **Daten bankrollen Mitgliedschaft** die `db_owner` Rolle für den Anmelde Namen für beide Datenbanken aus.</span><span class="sxs-lookup"><span data-stu-id="39654-125">In the **Database role membership** list select the `db_owner` role for the login for both databases.</span></span>  
  
4.  <span data-ttu-id="39654-126">Klicken Sie auf **OK** , um die Anmeldung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="39654-126">Click **OK** to create the login.</span></span>  
  
5.  <span data-ttu-id="39654-127">Wiederholen Sie die Schritte 1 bis 4, um eine Anmeldung für das lokale Konto repl_logreader zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="39654-127">Repeat steps 1-4 to create a login for the local repl_logreader account.</span></span> <span data-ttu-id="39654-128">Diese Anmeldung muss auch Benutzern zugeordnet werden, die Mitglieder der `db_owner` Fixed-Daten Bank Rolle in den Datenbanken **Distribution** und **AdventureWorks** sind.</span><span class="sxs-lookup"><span data-stu-id="39654-128">This login must also be mapped to users that are members of the `db_owner` fixed database role in the **distribution** and **AdventureWorks** databases.</span></span>  
  
6.  <span data-ttu-id="39654-129">Wiederholen Sie die Schritte 1 bis 4, um eine Anmeldung für das lokale Konto repl_distribution zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="39654-129">Repeat steps 1-4 to create a login for the local repl_distribution account.</span></span> <span data-ttu-id="39654-130">Diese Anmeldung muss einem Benutzer zugeordnet werden, der Mitglied der `db_owner` festgelegten Daten Bank Rolle in der **Verteilungs** Datenbank ist.</span><span class="sxs-lookup"><span data-stu-id="39654-130">This login must be mapped to a user that is a member of the `db_owner` fixed database role in the **distribution** database.</span></span>  
  
7.  <span data-ttu-id="39654-131">Wiederholen Sie die Schritte 1 bis 4, um eine Anmeldung für das lokale Konto repl_merge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="39654-131">Repeat steps 1-4 to create a login for the local repl_merge account.</span></span> <span data-ttu-id="39654-132">Diese Anmeldung muss Benutzerzuordnungen in den Datenbanken **distribution** und **AdventureWorks** haben.</span><span class="sxs-lookup"><span data-stu-id="39654-132">This login must have user mappings in the **distribution** and **AdventureWorks** databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39654-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="39654-133">See Also</span></span>  
 <span data-ttu-id="39654-134">[Verteilung konfigurieren](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="39654-134">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="39654-135">Sicherheitsmodell des Replikations-Agents</span><span class="sxs-lookup"><span data-stu-id="39654-135">Replication Agent Security Model</span></span>](security/replication-agent-security-model.md)  
  
  
