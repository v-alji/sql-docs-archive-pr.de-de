---
title: Starten und Beenden des Berichtsserverdiensts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- stopping Report Server service
- Report Server Windows service, starting
- Report Server service, starting
- starting Report Server service
ms.assetid: 6ec69ac3-27b0-472d-91e1-733af9078ed2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b751fd1a31830ffdc96cb296fa39d08e396c8c50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617628"
---
# <a name="start-and-stop-the-report-server-service"></a><span data-ttu-id="70bf6-102">Starten und Beenden des Berichtsserverdiensts</span><span class="sxs-lookup"><span data-stu-id="70bf6-102">Start and Stop the Report Server Service</span></span>
  <span data-ttu-id="70bf6-103">Der Berichtsserver wird als Windows-Dienst implementiert, der den Report Server-Webdienst, den Berichts-Manager und eine Hintergrundverarbeitungsanwendung umfasst.</span><span class="sxs-lookup"><span data-stu-id="70bf6-103">A report server is implemented as a Windows service that contains the Report Server Web service, Report Manager, and a background processing application.</span></span> <span data-ttu-id="70bf6-104">Der Dienst muss ausgeführt werden, damit Sie die Berichtsserverfunktionalitäten nutzen können.</span><span class="sxs-lookup"><span data-stu-id="70bf6-104">The service must be running if you want to use any report server functionality.</span></span> <span data-ttu-id="70bf6-105">Durch Beenden des Diensts werden alle Berichtsservervorgänge beendet.</span><span class="sxs-lookup"><span data-stu-id="70bf6-105">Stopping the service stops all report server operations.</span></span>  
  
 <span data-ttu-id="70bf6-106">Wenn der Dienst beendet ist, werden Anforderungen für die Verarbeitung von geplanten Berichts- und Abonnementverarbeitungen in die Warteschlange gestellt.</span><span class="sxs-lookup"><span data-stu-id="70bf6-106">While the service is stopped, requests for scheduled report and subscription processing that would have occurred had the service been running are added to the queue.</span></span> <span data-ttu-id="70bf6-107">Dies liegt daran, dass diese Ereignisse von vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent ausgeführten Aufträgen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="70bf6-107">This is because jobs that are run by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent create the events.</span></span> <span data-ttu-id="70bf6-108">Wenn Sie einen Backlog von Vorgängen vermeiden möchten, während der Dienst deaktiviert ist, sollten Sie erwägen, den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent ebenfalls zu beenden.</span><span class="sxs-lookup"><span data-stu-id="70bf6-108">If you want to avoid a backlog of operations while the service is off, consider stopping [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent as well.</span></span>  
  
 <span data-ttu-id="70bf6-109">Sie können den Berichtsserverdienst mit einer Vielzahl von Tools starten oder beenden, u.&nbsp;a. mit dem [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Konfigurationstool, dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager und dem Services-Tool von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="70bf6-109">You can use a variety of tools to start or stop the Report Server service, including the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, and the Services tool provided in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span></span>  
  
 <span data-ttu-id="70bf6-110">Wenn Sie über das Starten und Beenden des Diensts hinaus weitere Vorgänge durchführen möchten, z.&nbsp;B. Ändern des Dienstkontos, müssen Sie das [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Konfigurationstool verwenden.</span><span class="sxs-lookup"><span data-stu-id="70bf6-110">If you are doing more than starting or stopping the service, such as changing the service account, you must use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool.</span></span> <span data-ttu-id="70bf6-111">Wenn Sie zum Ändern des Dienstkontos andere Tools verwenden, kann dadurch Ihre [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Installation beschädigt werden.</span><span class="sxs-lookup"><span data-stu-id="70bf6-111">Using other tools to change the service account can break your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation.</span></span> <span data-ttu-id="70bf6-112">Weitere Informationen finden Sie unter [Konfigurieren des Berichtsserver-Dienstkontos &#40;SSRS-Konfigurations-Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="70bf6-112">For more information, see [Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md).</span></span>  
  
 <span data-ttu-id="70bf6-113">Der Dienst kann nicht angehalten und fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="70bf6-113">You cannot pause and resume the service.</span></span> <span data-ttu-id="70bf6-114">Es gibt keine Startparameter.</span><span class="sxs-lookup"><span data-stu-id="70bf6-114">There are no start parameters.</span></span> <span data-ttu-id="70bf6-115">Obwohl keine expliziten Abhängigkeiten vorhanden sind, muss der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent ausgeführt werden, wenn auf dem Berichtsserver Abonnements oder geplante Berichtsvorgänge unterstützt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="70bf6-115">Although there are no explicit dependencies, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be running if you support any subscriptions or scheduled report operations on the report server.</span></span>  
  
### <a name="to-start-or-stop-the-service-using-the-reporting-services-configuration-tool"></a><span data-ttu-id="70bf6-116">So starten oder beenden Sie den Dienst mit dem Reporting Services-Konfigurationstool</span><span class="sxs-lookup"><span data-stu-id="70bf6-116">To start or stop the service using the Reporting Services Configuration tool</span></span>  
  
1.  <span data-ttu-id="70bf6-117">Starten Sie das [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Konfigurationstool, und stellen Sie eine Verbindung mit dem Berichtsserver her.</span><span class="sxs-lookup"><span data-stu-id="70bf6-117">Start [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool and connect to the report server.</span></span>  
  
2.  <span data-ttu-id="70bf6-118">Klicken Sie auf der Seite Berichtsserverstatus auf **Beenden** oder auf **Starten**.</span><span class="sxs-lookup"><span data-stu-id="70bf6-118">On the Report Server Status page, click **Stop** or **Start**.</span></span>  
  
### <a name="to-start-or-stop-the-service-using-services-in-administrative-tools"></a><span data-ttu-id="70bf6-119">So starten oder beenden Sie den Dienst mit der Option Dienste unter Verwaltung</span><span class="sxs-lookup"><span data-stu-id="70bf6-119">To start or stop the service using Services in Administrative Tools</span></span>  
  
-   <span data-ttu-id="70bf6-120">Öffnen Sie unter „Verwaltung“ den Eintrag „Dienste“, klicken Sie mit der rechten Maustaste auf **SQL Server Reporting Services (MSSQLSERVER)**, und klicken Sie auf **Beenden** bzw. **Neu starten**.</span><span class="sxs-lookup"><span data-stu-id="70bf6-120">In Administrative Tools, open Services, right-click **SQL Server Reporting Services (MSSQLSERVER)**, and click **Stop** or **Restart**.</span></span>  
  
 <span data-ttu-id="70bf6-121">Wenn mehrere Instanzen ausgeführt werden oder der Berichtsserver als eine benannte Instanz ausgeführt wird, überprüfen Sie, ob der Instanzname in Klammern der Berichtsserverinstanz entspricht, die beendet oder neu gestartet werden soll.</span><span class="sxs-lookup"><span data-stu-id="70bf6-121">If you are running multiple instance or if the report server is running as a named instance, verify that the instance name in parentheses corresponds to the report server instance you want to stop or restart.</span></span>  
  
### <a name="to-start-or-stop-the-service-using-sql-server-configuration-manager"></a><span data-ttu-id="70bf6-122">So starten oder beenden Sie den Dienst mit dem SQL Server-Konfigurations-Manager</span><span class="sxs-lookup"><span data-stu-id="70bf6-122">To start or stop the service using SQL Server Configuration Manager</span></span>  
  
1.  <span data-ttu-id="70bf6-123">Starten Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager.</span><span class="sxs-lookup"><span data-stu-id="70bf6-123">Start [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
2.  <span data-ttu-id="70bf6-124">Wählen Sie „SQL Server-Dienste“ aus, klicken Sie mit der rechten Maustaste auf **SQL Server Reporting Services**, und klicken Sie auf **Beenden** oder **Neu starten**.</span><span class="sxs-lookup"><span data-stu-id="70bf6-124">Select SQL Server Services, right-click **SQL Server Reporting Services**, and click **Stop** or **Restart**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70bf6-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="70bf6-125">See Also</span></span>  
 [<span data-ttu-id="70bf6-126">Reporting Services-Konfigurations-Manager &#40;einheitlicher Modus&#41;</span><span class="sxs-lookup"><span data-stu-id="70bf6-126">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)  
  
  
