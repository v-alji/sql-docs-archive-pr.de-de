---
title: Legen Sie fest, dass eine Instanz von SQL Server automatisch gestartet wird (SQL Server-Konfigurations-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/07/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- automatic SQL Server startup
- SQL Server, automatic startup
- starting SQL Server, automatically
ms.assetid: aa2b6bde-e76d-4fea-a560-54a63745d9b1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2fc21bd881c1588da47710c6d8437e31d3df2ab4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723065"
---
# <a name="set-an-instance-of-sql-server-to-start-automatically-sql-server-configuration-manager"></a><span data-ttu-id="496fd-102">Festlegen des automatischen Starts einer Instanz von SQL Server (SQL Server-Konfigurations-Manager)</span><span class="sxs-lookup"><span data-stu-id="496fd-102">Set an Instance of SQL Server to Start Automatically (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="496fd-103">In diesem Thema wird beschrieben, wie Sie in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe des SQL Server-Konfigurations-Managers festlegen können, dass eine Instanz von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] automatisch gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="496fd-103">This topic describes how to set an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to start automatically in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="496fd-104">Bei der Installation wird [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] normalerweise für den automatischen Start konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="496fd-104">During setup, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is normally configured to start automatically.</span></span> <span data-ttu-id="496fd-105">Diese Einstellung kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="496fd-105">If this was not done, you can change that setting at any time.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="496fd-106">Verwenden des SQL Server-Konfigurations-Managers</span><span class="sxs-lookup"><span data-stu-id="496fd-106">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-set-an-instance-of-sql-server-to-start-automatically"></a><span data-ttu-id="496fd-107">So legen Sie für eine Instanz von SQL Server den automatischen Start fest</span><span class="sxs-lookup"><span data-stu-id="496fd-107">To set an instance of SQL Server to start automatically</span></span>  
  
1.  <span data-ttu-id="496fd-108">Zeigen Sie im Menü **Start** auf **Alle Programme**, zeigen Sie auf [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], zeigen Sie auf **Konfigurationstools**, und klicken Sie dann auf **SQL Server-Konfigurations-Manager**.</span><span class="sxs-lookup"><span data-stu-id="496fd-108">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="496fd-109">Da der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager ein Snap-In für das [!INCLUDE[msCoName](../../includes/msconame-md.md)] -Verwaltungskonsolenprogramm und kein eigenständiges Programm ist, wird der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager in neueren Versionen von Windows nicht als Anwendung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="496fd-109">Because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager is a snap-in for the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console program and not a stand-alone program, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager does not appear as an application in newer versions of Windows.</span></span>  
    >   
    >  -   <span data-ttu-id="496fd-110">**Windows 10**:</span><span class="sxs-lookup"><span data-stu-id="496fd-110">**Windows 10**:</span></span>  
    >          <span data-ttu-id="496fd-111">Um Configuration Manager zu öffnen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , geben Sie auf der **Start Seite**SQLServerManager12. msc (für [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] ) ein.</span><span class="sxs-lookup"><span data-stu-id="496fd-111">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, on the **Start Page**, type SQLServerManager12.msc (for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]).</span></span> <span data-ttu-id="496fd-112">Ersetzen Sie für frühere Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 12 durch eine kleinere Zahl.</span><span class="sxs-lookup"><span data-stu-id="496fd-112">For previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replace 12 with a smaller number.</span></span> <span data-ttu-id="496fd-113">Durch Klicken auf SQLServerManager12.msc wird der Konfigurations-Manager geöffnet.</span><span class="sxs-lookup"><span data-stu-id="496fd-113">Clicking SQLServerManager12.msc opens the Configuration Manager.</span></span> <span data-ttu-id="496fd-114">Um die Configuration Manager an die Start Seite oder Task Leiste anzuheften, klicken Sie mit der rechten Maustaste auf SQLServerManager12. msc, und klicken Sie dann auf **Datei Speicherort öffnen**.</span><span class="sxs-lookup"><span data-stu-id="496fd-114">To pin the Configuration Manager to the Start Page or Task Bar, right-click SQLServerManager12.msc, and then click **Open file location**.</span></span> <span data-ttu-id="496fd-115">Klicken Sie im Windows-Datei-Explorer mit der rechten Maustaste auf SQLServerManager12. msc, und klicken Sie dann auf am **Anfang anheften** oder **an Taskleiste**anheften</span><span class="sxs-lookup"><span data-stu-id="496fd-115">In the Windows File Explorer, right-click SQLServerManager12.msc, and then click **Pin to Start** or **Pin to taskbar**.</span></span>  
    > -   <span data-ttu-id="496fd-116">**Windows 8**:</span><span class="sxs-lookup"><span data-stu-id="496fd-116">**Windows 8**:</span></span>  
    >          <span data-ttu-id="496fd-117">Um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager im Charm **Suchen** unter **apps**zu öffnen, geben Sie **SQLServerManager \<version> . msc** ein, z `SQLServerManager12.msc` . b., und drücken Sie dann die **Eingabe**Taste.</span><span class="sxs-lookup"><span data-stu-id="496fd-117">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the **Search** charm, under **Apps**, type **SQLServerManager\<version>.msc** such as `SQLServerManager12.msc`, and then press **Enter**.</span></span>  
  
2.  <span data-ttu-id="496fd-118">Erweitern Sie in **SQL Server-Konfigurations-Manager**den Ordner **Services**, und klicken Sie dann auf **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="496fd-118">In **SQL Server Configuration Manager**, expand **Services**, and then click **SQL Server**.</span></span>  
  
3.  <span data-ttu-id="496fd-119">Klicken Sie im Detailbereich mit der rechten Maustaste auf den Namen der Instanz, die automatisch gestartet werden soll, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="496fd-119">In the details pane, right-click the name of the instance you want to start automatically, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="496fd-120">Legen Sie im Dialogfeld **SQL Server \<***instancename***>-Eigenschaften** den **Startmodus** auf **Automatisch** fest.</span><span class="sxs-lookup"><span data-stu-id="496fd-120">In the **SQL Server \<***instancename***> Properties** dialog box, set **Start Mode** to **Automatic**.</span></span>  
  
5.  <span data-ttu-id="496fd-121">Klicken Sie auf **OK**, und schließen Sie dann den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager.</span><span class="sxs-lookup"><span data-stu-id="496fd-121">Click **OK**, and then close [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="496fd-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="496fd-122">See Also</span></span>  
 <span data-ttu-id="496fd-123">[Verhindern des automatischen Starts einer Instanz von SQL Server &#40;SQL Server-Konfigurations-Manager&#41;](scm-services-prevent-automatic-startup-of-an-instance.md) </span><span class="sxs-lookup"><span data-stu-id="496fd-123">[Prevent Automatic Startup of an Instance of SQL Server &#40;SQL Server Configuration Manager&#41;](scm-services-prevent-automatic-startup-of-an-instance.md) </span></span>  
 <span data-ttu-id="496fd-124">[Herstellen einer Verbindung mit einem anderen Computer (SQL Server-Konfigurations-Manager)](scm-services-connect-to-another-computer.md) </span><span class="sxs-lookup"><span data-stu-id="496fd-124">[Connect to Another Computer &#40;SQL Server Configuration Manager&#41;](scm-services-connect-to-another-computer.md) </span></span>  
 [<span data-ttu-id="496fd-125">Konfigurieren von WMI zum Anzeigen des Serverstatus in SQL Server-Tools</span><span class="sxs-lookup"><span data-stu-id="496fd-125">Configure WMI to Show Server Status in SQL Server Tools</span></span>](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md)  
  
  
