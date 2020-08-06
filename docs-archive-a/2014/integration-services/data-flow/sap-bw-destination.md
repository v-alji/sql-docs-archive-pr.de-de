---
title: SAP BW-Ziel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a612ed91-b89b-4173-a0b1-0bce381e1e28
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8a0d7c5b75da89e665dbe60bbd7e29ce74da67db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619980"
---
# <a name="sap-bw-destination"></a><span data-ttu-id="66814-102">SAP BW-Ziel</span><span class="sxs-lookup"><span data-stu-id="66814-102">SAP BW Destination</span></span>
  <span data-ttu-id="66814-103">Das SAP BW-Ziel ist die Zielkomponente von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="66814-103">The SAP BW destination is the destination component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span> <span data-ttu-id="66814-104">Folglich lädt das SAP BW-Ziel Daten aus dem Datenfluss in ein [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket im SAP NetWeaver BW-System, Version 7.</span><span class="sxs-lookup"><span data-stu-id="66814-104">Thus, the SAP BW destination loads data from the data flow in an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package into an SAP Netweaver BW version 7 system.</span></span>  
  
 <span data-ttu-id="66814-105">Das Ziel weist eine Eingabe und eine Fehlerausgabe auf.</span><span class="sxs-lookup"><span data-stu-id="66814-105">This destination has one input and one error output.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="66814-106">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="66814-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="66814-107">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="66814-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="66814-108">Führen Sie die folgenden Aufgaben aus, um das SAP BW-Ziel zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="66814-108">To use the SAP BW destination, you have to do the following tasks:</span></span>  
  
-   [<span data-ttu-id="66814-109">Vorbereiten der SAP NetWeaver BW-Objekte</span><span class="sxs-lookup"><span data-stu-id="66814-109">Prepare the SAP Netweaver BW objects</span></span>](#bkmk_Prepare_Objects)  
  
-   [<span data-ttu-id="66814-110">Verbinden mit dem SAP NetWeaver BW-System</span><span class="sxs-lookup"><span data-stu-id="66814-110">Connect to the SAP Netweaver BW system</span></span>](#bkmk_Connect_Database)  
  
-   [<span data-ttu-id="66814-111">Konfigurieren des SAP BW-Ziels</span><span class="sxs-lookup"><span data-stu-id="66814-111">Configure the SAP BW destination</span></span>](#bkmk_Configure_Destination)  
  
##  <a name="preparing-the-sap-netweaver-bw-objects-that-the-destination-requires"></a><a name="bkmk_Prepare_Objects"></a> <span data-ttu-id="66814-112">Vorbereiten der SAP NetWeaver BW-Objekte, die für das Ziel erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="66814-112">Preparing the SAP Netweaver BW Objects That the Destination Requires</span></span>  
 <span data-ttu-id="66814-113">Das SAP BW-Ziel erfordert, dass sich bestimmte Objekte im SAP NetWeaver BW-System befinden, damit das Ziel funktionsfähig ist.</span><span class="sxs-lookup"><span data-stu-id="66814-113">The SAP BW destination requires that certain objects are in the SAP Netweaver BW system before the destination can function.</span></span> <span data-ttu-id="66814-114">Wenn diese Objekte noch nicht vorhanden sind, müssen Sie diese Schritte ausführen, um die Objekte im SAP NetWeaver BW-System zu erstellen und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="66814-114">If these objects do not already exist, you have to follow these steps to create and configure these objects in the SAP Netweaver BW system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="66814-115">Zusätzliche Informationen zu diesen Objekten und die Konfigurationsschritte finden Sie in der SAP NetWeaver BW-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="66814-115">For additional details about these objects and these configuration steps, see the SAP Netweaver BW documentation.</span></span>  
  
1.  <span data-ttu-id="66814-116">Erstellen Sie ein neues Quellsystem:</span><span class="sxs-lookup"><span data-stu-id="66814-116">Create a new Source System:</span></span>  
  
    1.  <span data-ttu-id="66814-117">Wählen Sie den Typ **Third Party/Staging BAPIs**(Drittanbieter/Staging BAPIs) aus.</span><span class="sxs-lookup"><span data-stu-id="66814-117">Select the type, **"Third Party/Staging BAPIs"**.</span></span>  
  
    2.  <span data-ttu-id="66814-118">Wählen Sie für **Communication Type with Target System**(Kommunikationstyp mit Zielsystem) die Option **Non-Unicode (Inactive MDMP Settings)** (Nicht-Unicode (inaktive MDMP-Einstellungen)) aus.</span><span class="sxs-lookup"><span data-stu-id="66814-118">For **Communication Type with Target System**, select **Non-Unicode (Inactive MDMP Settings)**.</span></span>  
  
    3.  <span data-ttu-id="66814-119">Weisen Sie eine entsprechende Programm-ID zu.</span><span class="sxs-lookup"><span data-stu-id="66814-119">Assign an appropriate Program ID.</span></span>  
  
2.  <span data-ttu-id="66814-120">Weisen Sie einer InfoSource das Quellsystem zu.</span><span class="sxs-lookup"><span data-stu-id="66814-120">Assign the Source System to an InfoSource.</span></span>  
  
3.  <span data-ttu-id="66814-121">Erstellen Sie ein InfoPackage.</span><span class="sxs-lookup"><span data-stu-id="66814-121">Create an InfoPackage.</span></span>  
  
     <span data-ttu-id="66814-122">Das InfoPackage ist das wichtigste Objekt, das vom SAP BW-Ziel benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="66814-122">The InfoPackage is the most important object that is required by the SAP BW destination.</span></span>  
  
 <span data-ttu-id="66814-123">Sie können zusätzliche InfoObjects, InfoCubes, InfoSources und InfoPackages erstellen, die erforderlich sind, um den Ladevorgang der Daten in das SAP NetWeaver BW-System zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="66814-123">You can also create additional InfoObjects, InfoCubes, InfoSources, and InfoPackages that are required to support loading data into the SAP Netweaver BW system.</span></span>  
  
##  <a name="connecting-to-the-sap-netweaver-bw-system"></a><a name="bkmk_Connect_Database"></a> <span data-ttu-id="66814-124">Herstellen einer Verbindung mit dem SAP NetWeaver BW-System</span><span class="sxs-lookup"><span data-stu-id="66814-124">Connecting to the SAP Netweaver BW System</span></span>  
 <span data-ttu-id="66814-125">Um eine Verbindung mit dem SAP NetWeaver BW-System, Version 7, herzustellen, verwendet das SQL BW-Ziel den SAP BW-Verbindungs-Manager, der im Lieferumfang des [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW-Pakets enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="66814-125">To connect to the SAP Netweaver BW version 7 system, the SAP BW destination uses the SAP BW connection manager that is part of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW package.</span></span> <span data-ttu-id="66814-126">Der SAP BW-Verbindungs-Manager ist der einzige [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Verbindungs-Manager, der vom SAP BW-Ziel verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="66814-126">The SAP BW connection manager is the only [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] connection manager that the SAP BW destination can use.</span></span>  
  
 <span data-ttu-id="66814-127">Weitere Informationen zum SAP BW-Verbindungs-Manager finden Sie unter [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="66814-127">For more information about the SAP BW connection manager, see [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span></span>  
  
##  <a name="configuring-the-sap-bw-destination"></a><a name="bkmk_Configure_Destination"></a> <span data-ttu-id="66814-128">Konfigurieren des SAP BW-Ziels</span><span class="sxs-lookup"><span data-stu-id="66814-128">Configuring the SAP BW Destination</span></span>  
 <span data-ttu-id="66814-129">Es gibt folgende Möglichkeiten, um das SAP BW-Ziel zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="66814-129">You can configure the SAP BW destination in the following ways:</span></span>  
  
-   <span data-ttu-id="66814-130">Suchen Sie das InfoPackage, das zum Laden von Daten verwendet werden soll, und wählen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="66814-130">Look up and select the InfoPackage to use to load data.</span></span>  
  
-   <span data-ttu-id="66814-131">Ordnen Sie jede Spalte im Datenfluss dem entsprechenden InfoObject im InfoPackage zu.</span><span class="sxs-lookup"><span data-stu-id="66814-131">Map each column in the data flow to the appropriate InfoObject in the InfoPackage.</span></span>  
  
-   <span data-ttu-id="66814-132">Geben Sie an, wie viele Datenzeilen auf einmal übertragen werden, indem Sie die `PackageSize`-Eigenschaft konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="66814-132">Specify how many rows of data will be transferred at a time by configuring the `PackageSize` property.</span></span>  
  
-   <span data-ttu-id="66814-133">Warten Sie, bis das SAP NetWeaver BW-System den Datenladevorgang vollständig abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="66814-133">Choose to wait until the loading of data is completed by the SAP Netweaver BW system.</span></span>  
  
-   <span data-ttu-id="66814-134">Lösen Sie das InfoPackage nicht aus, sondern warten Sie auf die Benachrichtigung, dass das SAP NetWeaver BW-System den Datenladevorgang gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="66814-134">Choose not to trigger the InfoPackage, but to wait for notification that the SAP Netweaver BW system has started the loading of data.</span></span>  
  
-   <span data-ttu-id="66814-135">Optional können Sie eine weitere Prozesskette auslösen, nachdem der Datenladevorgang abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="66814-135">Optionally, trigger another process chain after the loading of data is completed.</span></span>  
  
-   <span data-ttu-id="66814-136">Optional können Sie die SAP NetWeaver BW-Objekte erstellen, die vom Ziel benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="66814-136">Optionally, create the SAP Netweaver BW objects that are required by the destination.</span></span> <span data-ttu-id="66814-137">Dazu gehören InfoObjects, InfoCubes, InfoSources und InfoPackages.</span><span class="sxs-lookup"><span data-stu-id="66814-137">This includes creating InfoObjects, InfoCubes, InfoSources, and InfoPackages.</span></span>  
  
-   <span data-ttu-id="66814-138">Testen Sie den Datenladevorgang anhand der ausgewählten Optionen.</span><span class="sxs-lookup"><span data-stu-id="66814-138">Test the loading of data with the options that you have selected.</span></span>  
  
 <span data-ttu-id="66814-139">Sie können auch die Protokollierung von RFC-Funktionsaufrufen durch das Ziel aktivieren.</span><span class="sxs-lookup"><span data-stu-id="66814-139">You can also enable logging of RFC function calls by the destination.</span></span> <span data-ttu-id="66814-140">(Diese Protokollierung wird separat von der optionalen Protokollierung ausgeführt, die Sie für [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Pakete aktivieren können.) Sie aktivieren die Protokollierung von RFC-Funktionsaufrufen bei der Konfiguration des SAP BW-Verbindungs-Managers, der vom Ziel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="66814-140">(This logging is separate from the optional logging that you can enable on [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.) You enable logging of RFC function calls when you configure the SAP BW connection manager that the destination will use.</span></span> <span data-ttu-id="66814-141">Weitere Informationen zur Konfiguration des SAP BW-Verbindungs-Managers finden Sie unter [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="66814-141">For more information about how to configure the SAP BW connection manager, see [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span></span>  
  
 <span data-ttu-id="66814-142">Wenn Sie nicht alle Werte kennen, die zur Konfiguration des Ziels erforderlich sind, müssen Sie ggf. Ihren SAP-Administrator um Unterstützung bitten.</span><span class="sxs-lookup"><span data-stu-id="66814-142">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="66814-143">Eine exemplarische Vorgehensweise, die zeigt, wie der SAP BW-Verbindungs-Manager sowie die zugehörige Quelle und das zugehörige Ziel konfiguriert und verwendet werden, finden Sie im Whitepaper [Verwenden von SQL Server 2008 Integration Services und SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span><span class="sxs-lookup"><span data-stu-id="66814-143">For a walkthrough that demonstrates how to configure and use the SAP BW connection manager, source, and destination, see the white paper, [Using SQL Server 2008 Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span></span> <span data-ttu-id="66814-144">In diesem Whitepaper wird auch erläutert, wie die erforderlichen Objekte in SAP BW konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="66814-144">This white paper also shows how to configure the required objects in SAP BW.</span></span>  
  
### <a name="using-the-ssis-designer-to-configure-the-destination"></a><span data-ttu-id="66814-145">Konfigurieren des Ziels mit dem SSIS-Designer</span><span class="sxs-lookup"><span data-stu-id="66814-145">Using the SSIS Designer to Configure the Destination</span></span>  
 <span data-ttu-id="66814-146">Um weitere Informationen zu den Eigenschaften des SAP BW-Ziels zu erhalten, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können, klicken Sie auf eines der folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="66814-146">For more information about the properties of the SAP BW destination that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="66814-147">Ziel-Editor für SAP BW &#40;Seite „Verbindungs-Manager“&#41;</span><span class="sxs-lookup"><span data-stu-id="66814-147">SAP BW Destination Editor &#40;Connection Manager Page&#41;</span></span>](sap-bw-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="66814-148">Ziel-Editor für SAP BW &#40;Seite „Zuordnungen“&#41;</span><span class="sxs-lookup"><span data-stu-id="66814-148">SAP BW Destination Editor &#40;Mappings Page&#41;</span></span>](sap-bw-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="66814-149">Ziel-Editor für SAP BW &#40;Seite „Fehlerausgabe“&#41;</span><span class="sxs-lookup"><span data-stu-id="66814-149">SAP BW Destination Editor &#40;Error Output Page&#41;</span></span>](sap-bw-destination-editor-error-output-page.md)  
  
-   [<span data-ttu-id="66814-150">Ziel-Editor für SAP BW &#40;Seite „Erweitert“&#41;</span><span class="sxs-lookup"><span data-stu-id="66814-150">SAP BW Destination Editor &#40;Advanced Page&#41;</span></span>](sap-bw-destination-editor-advanced-page.md)  
  
 <span data-ttu-id="66814-151">Während Sie das SAP BW-Ziel konfigurieren, können Sie auch verschiedene Dialogfelder verwenden, um SAP NetWeaver BW-Objekte zu suchen oder zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="66814-151">While you are configuring the SAP BW destination, you can also use various dialog boxes to look up or to create SAP Netweaver BW objects.</span></span> <span data-ttu-id="66814-152">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu diesen Dialogfeldern zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="66814-152">For more information about these dialog boxes, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="66814-153">InfoPackage suchen</span><span class="sxs-lookup"><span data-stu-id="66814-153">Look Up InfoPackage</span></span>](look-up-infopackage.md)  
  
-   [<span data-ttu-id="66814-154">Neues InfoObject erstellen</span><span class="sxs-lookup"><span data-stu-id="66814-154">Create New InfoObject</span></span>](create-new-infoobject.md)  
  
-   [<span data-ttu-id="66814-155">InfoCube für Transaktionsdaten erstellen</span><span class="sxs-lookup"><span data-stu-id="66814-155">Create InfoCube for Transaction Data</span></span>](create-infocube-for-transaction-data.md)  
  
-   [<span data-ttu-id="66814-156">InfoObject suchen</span><span class="sxs-lookup"><span data-stu-id="66814-156">Look Up InfoObject</span></span>](look-up-infoobject.md)  
  
-   [<span data-ttu-id="66814-157">InfoSource erstellen</span><span class="sxs-lookup"><span data-stu-id="66814-157">Create InfoSource</span></span>](create-infosource.md)  
  
-   [<span data-ttu-id="66814-158">InfoSource für Transaktionsdaten erstellen</span><span class="sxs-lookup"><span data-stu-id="66814-158">Create InfoSource for Transaction Data</span></span>](create-infosource-for-transaction-data.md)  
  
-   [<span data-ttu-id="66814-159">InfoSource für Masterdaten erstellen</span><span class="sxs-lookup"><span data-stu-id="66814-159">Create InfoSource for Master Data</span></span>](create-infosource-for-master-data.md)  
  
-   [<span data-ttu-id="66814-160">InfoPackage erstellen</span><span class="sxs-lookup"><span data-stu-id="66814-160">Create InfoPackage</span></span>](create-infopackage.md)  
  
## <a name="see-also"></a><span data-ttu-id="66814-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="66814-161">See Also</span></span>  
 [<span data-ttu-id="66814-162">Komponenten von Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="66814-162">Microsoft Connector 1.1 for SAP BW Components</span></span>](../microsoft-connector-for-sap-bw-components.md)  
  
  
