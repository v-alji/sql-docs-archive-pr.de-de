---
title: Verhindern des automatischen Starts einer Instanz von SQL Server (SQL Server-Konfigurations-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- automatic SQL Server startup
- SQL Server, stopping
- SQL Server, automatic startup
- canceling automatic startup
- stopping SQL Server
- preventing automatic startups [SQL Server]
ms.assetid: 782663cf-f3d7-4cc6-b621-21e4550f0322
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8f93f5abc749f589ab4208b3a4c9434ca63b8769
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618899"
---
# <a name="prevent-automatic-startup-of-an-instance-of-sql-server-sql-server-configuration-manager"></a><span data-ttu-id="cb92b-102">Verhindern des automatischen Starts einer Instanz von SQL Server (SQL Server-Konfigurations-Manager)</span><span class="sxs-lookup"><span data-stu-id="cb92b-102">Prevent Automatic Startup of an Instance of SQL Server (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="cb92b-103">In diesem Thema wird beschrieben, wie Sie in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe des SQL Server-Konfigurations-Managers verhindern können, dass eine Instanz von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] automatisch gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="cb92b-103">This topic describes how prevent an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from starting automatically in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cb92b-104">ist normalerweise für den automatischen Start konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="cb92b-104">is normally configured to start automatically.</span></span> <span data-ttu-id="cb92b-105">Sie können diese Einstellung ändern, indem Sie den Startmodus für die Instanz auf manuell festlegen.</span><span class="sxs-lookup"><span data-stu-id="cb92b-105">You can change that by setting the start mode for the instance to manual.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="cb92b-106">Verwenden des SQL Server-Konfigurations-Managers</span><span class="sxs-lookup"><span data-stu-id="cb92b-106">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-prevent-automatic-startup-of-an-instance-of-sql-server"></a><span data-ttu-id="cb92b-107">So verhindern Sie das automatische Starten einer Instanz von SQL Server</span><span class="sxs-lookup"><span data-stu-id="cb92b-107">To prevent automatic startup of an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="cb92b-108">Zeigen Sie im Menü **Start** auf **Alle Programme**, zeigen Sie auf [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], zeigen Sie auf **Konfigurationstools**, und klicken Sie dann auf **SQL Server-Konfigurations-Manager**.</span><span class="sxs-lookup"><span data-stu-id="cb92b-108">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="cb92b-109">Erweitern Sie im SQL Server-Konfigurations-Manager **Dienste**, und klicken Sie dann auf **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="cb92b-109">In SQL Server Configuration Manager, expand **Services**, and then click **SQL Server**.</span></span>  
  
3.  <span data-ttu-id="cb92b-110">Klicken Sie im Detailbereich mit der rechten Maustaste auf **MSSQLServer**, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="cb92b-110">In the details pane, right-click **MSSQLServer**, and then click **Properties.**</span></span>  
  
4.  <span data-ttu-id="cb92b-111">Legen Sie im Dialogfeld **SQL Server \<**_instancename_**> Eigenschaften** im Feld **Eigenschaften** den Wert für **Start Modus** auf **manuell**fest.</span><span class="sxs-lookup"><span data-stu-id="cb92b-111">In the **SQL Server \<**_instancename_**> Properties** dialog box, in the **Properties** box, set the value of **Start Mode** to **Manual**.</span></span>  
  
5.  <span data-ttu-id="cb92b-112">Klicken Sie auf **OK**, um das Dialogfeld **SQL Server \<**_instancename_**>-Eigenschaften** zu schließen, und schließen Sie dann den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Konfigurations-Manager.</span><span class="sxs-lookup"><span data-stu-id="cb92b-112">Click **OK** to close the **SQL Server \<**_instancename_**> Properties** dialog box, and then close [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb92b-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb92b-113">See Also</span></span>  
 [<span data-ttu-id="cb92b-114">Starten, Beenden, Anhalten, Fortsetzen und Neustarten der Datenbank-Engine, SQL Server-Agent oder des SQL Server-Browsers</span><span class="sxs-lookup"><span data-stu-id="cb92b-114">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](start-stop-pause-resume-restart-sql-server-services.md)  
  
  
