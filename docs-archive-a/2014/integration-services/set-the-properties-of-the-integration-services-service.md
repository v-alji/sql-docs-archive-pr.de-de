---
title: Festlegen der Eigenschaften des Integration Services Dienstanbieter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services service, configuring
- Integration Services service, properties
ms.assetid: 3a8ad546-0f58-4b31-ab56-58d6313b1098
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 055eadd9a1d59c59dd40675b142eae480763f6f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726045"
---
# <a name="set-the-properties-of-the-integration-services-service"></a><span data-ttu-id="2170c-102">Festlegen der Eigenschaften des Integration Services-Diensts</span><span class="sxs-lookup"><span data-stu-id="2170c-102">Set the Properties of the Integration Services Service</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="2170c-103">In diesem Thema wird der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienst beschrieben, ein Windows-Dienst zur Verwaltung von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paketen.</span><span class="sxs-lookup"><span data-stu-id="2170c-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="2170c-104">unterstützt den Dienst für die Abwärtskompatibilität mit früheren Versionen von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2170c-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="2170c-105">Ab [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]können Sie Objekte, z. B. Pakete, auf dem Integration Services-Server verwalten.</span><span class="sxs-lookup"><span data-stu-id="2170c-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="2170c-106">Der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienst überwacht und verwaltet Pakete in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2170c-106">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages and monitors packages in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="2170c-107">Bei der erstmaligen Installation [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] von wird der-Dienst gestartet, und der Starttyp des Dienstanbieter wird auf automatisch festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2170c-107">When you first install [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service is started and the startup type of the service is set to automatic.</span></span>  
  
 <span data-ttu-id="2170c-108">Nach der Installation des [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Diensts können Sie die Eigenschaften des Dienstes entweder mit dem SQL Server-Konfigurations-Manager oder mit dem MMC-Snap-In „Dienste“ festlegen.</span><span class="sxs-lookup"><span data-stu-id="2170c-108">After the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service has been installed, you can set the properties of the service by using either SQL Server Configuration Manager or the Services MMC snap-in.</span></span>  
  
 <span data-ttu-id="2170c-109">Zur Konfiguration anderer wichtiger Funktionen des Dienstes, wie die Verzeichnisse für die Speicherung und Verwaltung von Paketen, müssen Sie die Konfigurationsdatei des Dienstes ändern.</span><span class="sxs-lookup"><span data-stu-id="2170c-109">To configure other important features of the service, including the locations where it stores and manages packages, you must modify the configuration file of the service.</span></span> <span data-ttu-id="2170c-110">Weitere Informationen finden Sie unter [Konfigurieren des Integration Services-Diensts &#40;SSIS-Dienst&#41;](service/integration-services-service-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="2170c-110">For more information, see [Configuring the Integration Services Service &#40;SSIS Service&#41;](service/integration-services-service-ssis-service.md).</span></span>  
  
### <a name="to-set-properties-of-the-integration-services-service-by-using-sql-server-configuration-manager"></a><span data-ttu-id="2170c-111">So legen Sie Eigenschaften des Integration Services-Dienstes mit dem SQL Server-Konfigurations-Manager fest</span><span class="sxs-lookup"><span data-stu-id="2170c-111">To set properties of the Integration Services service by using SQL Server Configuration Manager</span></span>  
  
1.  <span data-ttu-id="2170c-112">Zeigen Sie im Menü **Start** auf **Alle Programme**, **Microsoft SQL Server**, **Konfigurationstools**, und klicken Sie dann auf **SQL Server-Konfigurations-Manager**.</span><span class="sxs-lookup"><span data-stu-id="2170c-112">On the **Start** menu, point to **All Programs**, point to **Microsoft SQL Server**, point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="2170c-113">Suchen Sie im **SQL Server-Konfigurations-Manager** -Snap-In in der Diensteliste nach **SQL Server Integration Services** , klicken Sie mit der rechten Maustaste auf **SQL Server Integration Services**, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="2170c-113">In the **SQL Server Configuration Manager** snap-in, locate **SQL Server Integration Services** in the list of services, right-click **SQL Server Integration Services**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="2170c-114">Im Dialogfeld **Eigenschaften von SQL Server Integration Services** können Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="2170c-114">In the **SQL Server Integration Services Properties** dialog box you can do the following:</span></span>  
  
    -   <span data-ttu-id="2170c-115">Klicken Sie auf die Registerkarte **Anmelden** , um die Anmeldeinformationen, wie z. B. den Kontonamen, anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2170c-115">Click the **Log On** tab to view the logon information such as the account name.</span></span>  
  
    -   <span data-ttu-id="2170c-116">Klicken Sie auf die Registerkarte **Dienst** , um Informationen zum Dienst, wie z. B. den Namen des Hostcomputers, anzuzeigen und den Startmodus des [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienstes anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2170c-116">Click the **Service** tab to view information about the service such as the name of the host computer and to specify the start mode of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="2170c-117">Die Registerkarte **Erweitert** enthält keine Informationen zum [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienst.</span><span class="sxs-lookup"><span data-stu-id="2170c-117">The **Advanced** tab contains no information for [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span>  
  
4.  <span data-ttu-id="2170c-118">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2170c-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="2170c-119">Klicken Sie im Menü **Datei** auf **Beenden** , um das **SQL Server-Konfigurations-Manager** -Snap-In zu schließen.</span><span class="sxs-lookup"><span data-stu-id="2170c-119">On the **File** menu, click **Exit** to close the **SQL Server Configuration Manager** snap-in.</span></span>  
  
### <a name="to-set-properties-of-the-integration-services-service-by-using-services"></a><span data-ttu-id="2170c-120">So legen Sie die Eigenschaften des Integration Services-Diensts mit Diensten fest</span><span class="sxs-lookup"><span data-stu-id="2170c-120">To set properties of the Integration Services service by using Services</span></span>  
  
1.  <span data-ttu-id="2170c-121">Wenn Sie die klassische Ansicht verwenden, klicken Sie in der **Systemsteuerung**auf **Verwaltung**. Wenn Sie die Kategorieansicht verwenden, klicken Sie auf **Leistung und Wartung** und dann auf **Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="2170c-121">In **Control Panel**, if you are using Classic View, click **Administrative Tools**, or, if you are using Category View, click **Performance and Maintenance** and then click **Administrative Tools**.</span></span>  
  
2.  <span data-ttu-id="2170c-122">Klicken Sie auf **Dienste**.</span><span class="sxs-lookup"><span data-stu-id="2170c-122">Click **Services**.</span></span>  
  
3.  <span data-ttu-id="2170c-123">Suchen Sie im Snap-In **Dienste** in der Diensteliste **SQL Server Integration Services** , klicken Sie mit der rechten Maustaste auf **SQL Server Integration Services**, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="2170c-123">In the **Services** snap-in, locate **SQL Server Integration Services** in the list of services, right-click **SQL Server Integration Services**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="2170c-124">Im Dialogfeld **Eigenschaften von SQL Server Integration Services** können Sie folgende Schritte durchführen:</span><span class="sxs-lookup"><span data-stu-id="2170c-124">In the **SQL Server Integration Services Properties** dialog box, you can do the following:</span></span>  
  
    -   <span data-ttu-id="2170c-125">Klicken Sie auf die Registerkarte **Allgemein** . Um den Dienst zu aktivieren, wählen Sie entweder den manuellen oder automatischen Starttyp aus.</span><span class="sxs-lookup"><span data-stu-id="2170c-125">Click the **General** tab. To enable the service, select either the manual or automatic startup type.</span></span> <span data-ttu-id="2170c-126">Um den Dienst zu deaktivieren, wählen Sie im Feld **Starttyp** die Option "Deaktivieren" aus.</span><span class="sxs-lookup"><span data-stu-id="2170c-126">To disable the service, select Disable in the **Startup type** box.</span></span> <span data-ttu-id="2170c-127">Die Auswahl von "Deaktivieren" führt nicht zum Beenden des Dienstes, falls er gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2170c-127">Selecting Disable does not stop the service if it is currently running.</span></span>  
  
         <span data-ttu-id="2170c-128">Wenn der Dienst bereits aktiviert ist, können Sie auf **Beenden** klicken, um den Dienst zu beenden, oder Sie können auf **Starten** klicken, um den Dienst zu starten.</span><span class="sxs-lookup"><span data-stu-id="2170c-128">If the service is already enabled, you can click **Stop** to stop the service, or click **Start** to start the service.</span></span>  
  
    -   <span data-ttu-id="2170c-129">Klicken Sie auf die Registerkarte **Anmelden** , um die Anmeldeinformationen anzuzeigen oder zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="2170c-129">Click the **Log On** tab to view or edit the logon information.</span></span>  
  
    -   <span data-ttu-id="2170c-130">Klicken Sie auf die Registerkarte **Wiederherstellung** , um die Standardreaktionen des Computers bei Dienstfehlern anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2170c-130">Click the **Recovery** tab to view the default computer responses to service failure.</span></span> <span data-ttu-id="2170c-131">Diese Optionen können Sie entsprechend Ihrer Umgebung anpassen.</span><span class="sxs-lookup"><span data-stu-id="2170c-131">You can modify these options to suit your environment.</span></span>  
  
    -   <span data-ttu-id="2170c-132">Klicken Sie auf die **Abhängigkeiten** -Registerkarte, um eine Liste der abhängigen Dienste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2170c-132">Click the **Dependencies** tab to view a list of dependent services.</span></span> <span data-ttu-id="2170c-133">Der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienst weist keine Abhängigkeiten auf.</span><span class="sxs-lookup"><span data-stu-id="2170c-133">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service has no dependencies.</span></span>  
  
5.  <span data-ttu-id="2170c-134">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2170c-134">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="2170c-135">Wenn als Starttyp „Manuell“ oder „Automatisch“ ausgewählt wurde, können Sie optional mit der rechten Maustaste auf **SQL Server Integration Services** klicken und anschließend auf **Starten, Beenden oder Neu starten**klicken.</span><span class="sxs-lookup"><span data-stu-id="2170c-135">Optionally, if the startup type is Manual or Automatic, you can right-click **SQL Server Integration Services** and click **Start, Stop, or Restart**.</span></span>  
  
7.  <span data-ttu-id="2170c-136">Klicken Sie im Menü **Datei** auf **Beenden** , um das Snap-In **Dienste** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="2170c-136">On the **File** menu, click **Exit** to close the **Services** snap-in.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2170c-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2170c-137">See Also</span></span>  
 [<span data-ttu-id="2170c-138">Verwalten des Integration Services-Diensts</span><span class="sxs-lookup"><span data-stu-id="2170c-138">Manage the Integration Services Service</span></span>](../../2014/integration-services/manage-the-integration-services-service.md)  
  
  
