---
title: Herstellen einer Verbindung mit einem anderen Computer (SQL Server-Konfigurations-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server], other computers
ms.assetid: c4c1e94f-4f5f-431e-8b5b-d5ff97baf723
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f3d478cebc1ca36ccb8f87b0355b7c8fe0a928cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622887"
---
# <a name="connect-to-another-computer-sql-server-configuration-manager"></a><span data-ttu-id="2d59b-102">Herstellen einer Verbindung mit einem anderen Computer (SQL Server-Konfigurations-Manager)</span><span class="sxs-lookup"><span data-stu-id="2d59b-102">Connect to Another Computer (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="2d59b-103">In diesem Thema wird beschrieben, wie Sie in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]eine Verbindung mit einem anderen Computer herstellen können.</span><span class="sxs-lookup"><span data-stu-id="2d59b-103">This topic describes how to connect to another computer in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="2d59b-104">Befolgen Sie die erste Prozedur, um die Computerverwaltung von Windows, MMC ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console) zu öffnen, stellen Sie eine Verbindung zu dem Computer her, und erweitern die Struktur "Dienste und Anwendungen".</span><span class="sxs-lookup"><span data-stu-id="2d59b-104">Follow the first procedure to open the Windows Computer Management [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console (mmc), connect to the computer, and expand the Services and Applications tree.</span></span> <span data-ttu-id="2d59b-105">Führen Sie das zweite Verfahren zum Erstellen einer Datei mit einem Link zum [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager auf einem Remotecomputer aus.</span><span class="sxs-lookup"><span data-stu-id="2d59b-105">Follow the second procedure to create a file with a link to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager on a remote computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2d59b-106">Bei einer Remoteverbindung können einige Aktionen nicht von Configuration Manager ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2d59b-106">Some actions cannot be performed by Configuration Manager when connecting remotely.</span></span>  
  
 <span data-ttu-id="2d59b-107">Zum Starten, Stoppen, Anhalten oder Fortsetzen von Diensten auf einem anderen Computer können Sie auch mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]eine Verbindung zu dem Server herstellen, mit der rechten Maustaste auf den Server oder den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent und anschließend auf die gewünschte Aktion klicken.</span><span class="sxs-lookup"><span data-stu-id="2d59b-107">To start, stop, pause, or resume services on another computer, you can also connect to the server with [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click the server or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent and then click the desired action.</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-connect-to-another-computer-with-windows-computer-management"></a><span data-ttu-id="2d59b-108">So stellen Sie eine Verbindung mit einem anderen Computer mit der Computerverwaltung von Windows her</span><span class="sxs-lookup"><span data-stu-id="2d59b-108">To connect to another computer with Windows Computer Management</span></span>  
  
1.  <span data-ttu-id="2d59b-109">Klicken Sie im Menü **Start** mit der rechten Maustaste auf **Arbeitsplatz**, und klicken Sie dann auf **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="2d59b-109">On the **Start** menu, right-click **My Computer**, and then click **Manage.**</span></span>  
  
2.  <span data-ttu-id="2d59b-110">Klicken Sie in **Computerverwaltung**mit der rechten Maustaste auf **Computerverwaltung (lokal)**, und klicken Sie dann auf **Verbindung mit anderem Computer herstellen**.</span><span class="sxs-lookup"><span data-stu-id="2d59b-110">In **Computer Management**, right-click **Computer Management (Local)**, and then click **Connect to another computer**.</span></span>  
  
3.  <span data-ttu-id="2d59b-111">Geben Sie im Dialogfeld **Computer auswählen** in das Textfeld **Anderen Computer** den Namen des Computers ein, den Sie verwalten möchten, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d59b-111">In the **Select Computer** dialog box, in the **Another computer** text box, type the name of the computer you want to manage, and then click **OK**.</span></span>  
  
     <span data-ttu-id="2d59b-112">Die Computerverwaltung zeigt die Dienste an, die auf dem Remotecomputer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2d59b-112">Computer Management displays the services running on the remote computer.</span></span> <span data-ttu-id="2d59b-113">Der Knoten der obersten Ebene wird in **Computerverwaltung** \<*remotecomputer*> geändert.</span><span class="sxs-lookup"><span data-stu-id="2d59b-113">The top-level node changes to **Computer Management** \<*remotecomputer*>.</span></span>  
  
4.  <span data-ttu-id="2d59b-114">Erweitern Sie in der Konsolenstruktur **Dienste und Anwendungen**, und erweitern Sie dann **SQL Server-Konfigurations-Manager** , um die Dienste des Remotecomputers zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="2d59b-114">In the console tree, expand **Services and Applications**, and then expand **SQL Server Configuration Manager** to manage the remote computer's services.</span></span>  
  
#### <a name="to-save-a-link-to-sql-server-configuration-manager-for-another-computer"></a><span data-ttu-id="2d59b-115">So sichern Sie einen Link zu SQL Server-Konfigurations-Manager für einen anderen Computer</span><span class="sxs-lookup"><span data-stu-id="2d59b-115">To save a link to SQL Server Configuration Manager for another computer</span></span>  
  
1.  <span data-ttu-id="2d59b-116">Klicken Sie im Menü **Start** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="2d59b-116">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="2d59b-117">Geben Sie im Feld **Öffnen** ein, `mmc -a` um die [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console im Autoren Modus zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2d59b-117">In the **Open** box, type `mmc -a` to open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console in author mode.</span></span>  
  
3.  <span data-ttu-id="2d59b-118">Klicken Sie im Menü **Datei** auf **Snap-In hinzufügen/entfernen**.</span><span class="sxs-lookup"><span data-stu-id="2d59b-118">On the **File** menu, click **Add/Remove Snap-in**.</span></span>  
  
4.  <span data-ttu-id="2d59b-119">Klicken Sie im Fenster **Snap-In hinzufügen/entfernen** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2d59b-119">In the **Add/Remove Snap-in** window, click **Add**.</span></span>  
  
5.  <span data-ttu-id="2d59b-120">Klicken Sie im Dialogfeld **Eigenständiges Snap-In hinzufügen** auf **Computerverwaltung** , und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2d59b-120">In the **Add Standalone Snap-in** window, click **Computer Management** and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="2d59b-121">Klicken Sie im Dialogfeld **Computerverwaltung** auf **Anderen Computer**, geben Sie den Namen des zu verwaltenden Remotecomputers ein, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="2d59b-121">In the **Computer Management** window, click **Another computer**, type the name of the remote computer you wish to manage, and then click **Finish**.</span></span>  
  
7.  <span data-ttu-id="2d59b-122">Klicken Sie im Dialogfeld **Eigenständiges Snap-In hinzufügen** auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="2d59b-122">In the **Add Standalone Snap-in** window, click **Close**.</span></span>  
  
8.  <span data-ttu-id="2d59b-123">Klicken Sie im Fenster **Snap-In hinzufügen/entfernen** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d59b-123">In the **Add/Remove Snap-in** window, click **OK**.</span></span>  
  
9. <span data-ttu-id="2d59b-124">Erweitern Sie **Computer Verwaltung ( ***\<computer name>*** )** und **Dienste und Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="2d59b-124">Expand **Computer Management (***\<computer name>***)**, and **Services and Applications**.</span></span>  
  
10. <span data-ttu-id="2d59b-125">Klicken Sie mit der rechten Maustaste auf **SQL Server-Konfigurations-Manager**, und klicken Sie dann auf **Neues Fenster**.</span><span class="sxs-lookup"><span data-stu-id="2d59b-125">Right-click **SQL Server Configuration Manager**, and then click **New Window from here**.</span></span>  
  
11. <span data-ttu-id="2d59b-126">Klicken Sie im Menü **Fenster** auf **Konsolenstamm**, um zum ersten Fenster zurückzuwechseln, und löschen Sie das Fenster.</span><span class="sxs-lookup"><span data-stu-id="2d59b-126">On the **Window** menu, click **Console Root**, to switch back to the first window, and delete the window.</span></span>  
  
12. <span data-ttu-id="2d59b-127">Klicken Sie im Menü **Datei** auf **Speichern**unter, und speichern Sie die Datei im gewünschten Ordner mit einem entsprechenden Namen mit der `.msc` Dateierweiterung.</span><span class="sxs-lookup"><span data-stu-id="2d59b-127">On the **File** menu, click **Save As**, and save the file in the desired folder, with an appropriate name with the `.msc` file extension.</span></span> <span data-ttu-id="2d59b-128">Schließen Sie das Fenster [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console.</span><span class="sxs-lookup"><span data-stu-id="2d59b-128">Close the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console.</span></span>  
  
13. <span data-ttu-id="2d59b-129">Doppelklicken Sie auf die Datei, um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager auf dem Zielcomputer zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2d59b-129">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager on the target computer, double-click the file.</span></span> <span data-ttu-id="2d59b-130">Speichern Sie gegebenenfalls einen Link zu der Datei auf dem Desktop oder im Menü **Start** .</span><span class="sxs-lookup"><span data-stu-id="2d59b-130">If desired, save a link to the file on the desktop or in the **Start** menu.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="2d59b-131">Wenn Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager auf einem Remotecomputer verwenden, ist der Computername nicht offensichtlich, und es ist möglich, versehentlich den falschen Computer zu stoppen oder zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2d59b-131">When using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager on a remote computer, the computer name is not obvious and it is possible to mistakenly stop or configure the wrong computer.</span></span> <span data-ttu-id="2d59b-132">Überprüfen Sie auf der Registerkarte **Dienst** das Feld **Hostname** , um den Computernamen zu überprüfen, bevor Sie einen Dienst ändern.</span><span class="sxs-lookup"><span data-stu-id="2d59b-132">On the **Service** tab, check the **Host Name** box to confirm the computer name before modifying a service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d59b-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d59b-133">See Also</span></span>  
 [<span data-ttu-id="2d59b-134">Konfigurieren von WMI zum Anzeigen des Serverstatus in SQL Server-Tools</span><span class="sxs-lookup"><span data-stu-id="2d59b-134">Configure WMI to Show Server Status in SQL Server Tools</span></span>](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md)  
  
  
