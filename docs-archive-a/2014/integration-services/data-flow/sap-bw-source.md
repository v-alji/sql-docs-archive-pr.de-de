---
title: SAP BW-Quelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 749afb64-3567-4dc9-8431-783d650c25db
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d64af5e0d881e3b7dbbd2cc4e005aa3dbef3c43a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621117"
---
# <a name="sap-bw-source"></a><span data-ttu-id="78209-102">SAP BW-Quelle</span><span class="sxs-lookup"><span data-stu-id="78209-102">SAP BW Source</span></span>
  <span data-ttu-id="78209-103">Die SAP BW-Quelle ist die Quellkomponente von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="78209-103">The SAP BW source is the source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span> <span data-ttu-id="78209-104">Daher extrahiert die SAP BW-Quelle Daten aus einem SAP NetWeaver BW-System, Version 7, und macht diese Daten im Datenfluss in einem [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Paket verfügbar.</span><span class="sxs-lookup"><span data-stu-id="78209-104">Thus, the SAP BW source extracts data from an SAP Netweaver BW version 7 system and makes this data available to the data flow in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span>  
  
 <span data-ttu-id="78209-105">Diese Quelle weist eine Ausgabe und eine Fehlerausgabe auf.</span><span class="sxs-lookup"><span data-stu-id="78209-105">This source has one output and one error output.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="78209-106">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="78209-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="78209-107">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="78209-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="78209-108">Das Extrahieren von Daten aus SAP NetWeaver BW erfordert zusätzliche SAP-Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="78209-108">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="78209-109">Stimmen Sie diese Anforderungen mit SAP ab.</span><span class="sxs-lookup"><span data-stu-id="78209-109">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="78209-110">Führen Sie die folgenden Aufgaben aus, um die SAP BW-Quelle zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="78209-110">To use the SAP BW source, you have to do the following tasks:</span></span>  
  
-   [<span data-ttu-id="78209-111">Vorbereiten der SAP NetWeaver BW-Objekte</span><span class="sxs-lookup"><span data-stu-id="78209-111">Prepare the SAP Netweaver BW objects</span></span>](#bkmk_Prepare_Objects)  
  
-   [<span data-ttu-id="78209-112">Verbinden mit dem SAP NetWeaver BW-System</span><span class="sxs-lookup"><span data-stu-id="78209-112">Connect to the SAP Netweaver BW system</span></span>](#bkmk_Connect_Database)  
  
-   [<span data-ttu-id="78209-113">Konfigurieren der SAP BW-Quelle</span><span class="sxs-lookup"><span data-stu-id="78209-113">Configure the SAP BW source</span></span>](#bkmk_Configure_Source)  
  
##  <a name="preparing-the-sap-netweaver-bw-objects-that-the-source-requires"></a><a name="bkmk_Prepare_Objects"></a> <span data-ttu-id="78209-114">Vorbereiten der SAP NetWeaver BW-Objekte, die für die Quelle erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="78209-114">Preparing the SAP Netweaver BW Objects That the Source Requires</span></span>  
 <span data-ttu-id="78209-115">Die SAP BW-Quelle erfordert, dass sich bestimmte Objekte im SAP NetWeaver BW-System befinden, damit die Quelle funktionsfähig ist.</span><span class="sxs-lookup"><span data-stu-id="78209-115">The SAP BW source requires that certain objects are in the SAP Netweaver BW system before the source can function.</span></span> <span data-ttu-id="78209-116">Wenn diese Objekte noch nicht vorhanden sind, müssen Sie diese Schritte ausführen, um die Objekte im SAP NetWeaver BW-System zu erstellen und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="78209-116">If these objects do not already exist, you have to follow these steps to create and configure these objects in the SAP Netweaver BW system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="78209-117">Zusätzliche Informationen zu diesen Objekten und die Konfigurationsschritte finden Sie in der SAP NetWeaver BW-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="78209-117">For additional details about these objects and these configuration steps, see the SAP Netweaver BW documentation.</span></span>  
  
1.  <span data-ttu-id="78209-118">Melden Sie sich über die SAP GUI bei SAP NetWeaver BW an, geben Sie den Transaktionscode SM59 ein, und erstellen Sie ein RFC-Ziel:</span><span class="sxs-lookup"><span data-stu-id="78209-118">Log on to SAP Netweaver BW through the SAP GUI, enter transaction code SM59, and create an RFC destination:</span></span>  
  
    1.  <span data-ttu-id="78209-119">Wählen Sie für **Verbindungstyp**die Option **TCP/IP**aus.</span><span class="sxs-lookup"><span data-stu-id="78209-119">For **Connection Type**, select **TCP/IP**.</span></span>  
  
    2.  <span data-ttu-id="78209-120">Wählen Sie für **Activation Type**(Aktivierungstyp) die Option **Registered Server Program**(Registriertes Serverprogramm) aus.</span><span class="sxs-lookup"><span data-stu-id="78209-120">For **Activation Type**, select **Registered Server Program**.</span></span>  
  
    3.  <span data-ttu-id="78209-121">Wählen Sie für **Communication Type with Target System**(Kommunikationstyp mit Zielsystem) die Option **Non-Unicode (Inactive MDMP Settings)** (Nicht-Unicode (inaktive MDMP-Einstellungen)) aus.</span><span class="sxs-lookup"><span data-stu-id="78209-121">For **Communication Type with Target System**, select **Non-Unicode (Inactive MDMP Settings)**.</span></span>  
  
    4.  <span data-ttu-id="78209-122">Weisen Sie eine entsprechende Programm-ID zu.</span><span class="sxs-lookup"><span data-stu-id="78209-122">Assign an appropriate Program ID.</span></span>  
  
2.  <span data-ttu-id="78209-123">Erstellen Sie ein Open Hub-Ziel:</span><span class="sxs-lookup"><span data-stu-id="78209-123">Create an Open Hub Destination:</span></span>  
  
    1.  <span data-ttu-id="78209-124">Wechseln Sie zur Administrator-Workbench (Transaktionscode RSA1), und wählen Sie im linken Bereich die Option **Open Hub Destination**(Open Hub-Ziel) aus.</span><span class="sxs-lookup"><span data-stu-id="78209-124">Go to the Administrator Workbench (transaction code RSA1) and, in the left pane, select **Open Hub Destination**.</span></span>  
  
    2.  <span data-ttu-id="78209-125">Klicken Sie im mittleren Bereich mit der rechten Maustaste auf eine InfoArea, und wählen Sie anschließend **Create Open Hub Destination**(Open Hub-Ziel erstellen) aus.</span><span class="sxs-lookup"><span data-stu-id="78209-125">In the middle pane, right-click an InfoArea, and then select **"Create Open Hub Destination"**.</span></span>  
  
    3.  <span data-ttu-id="78209-126">Wählen Sie für **Destination Type**(Zieltyp) die Option **Third Party Tool**(Drittanbietertool) aus, und geben Sie das zuvor erstellte RFC-Ziel ein.</span><span class="sxs-lookup"><span data-stu-id="78209-126">For **Destination Type**, select **"Third Party Tool"**, and then enter the previously created RFC Destination.</span></span>  
  
    4.  <span data-ttu-id="78209-127">Speichern und aktivieren Sie das neue Open Hub-Ziel.</span><span class="sxs-lookup"><span data-stu-id="78209-127">Save and activate the new Open Hub Destination.</span></span>  
  
3.  <span data-ttu-id="78209-128">Erstellen Sie einen Datenübertragungsprozess (DTP):</span><span class="sxs-lookup"><span data-stu-id="78209-128">Create a Data Transfer Process (DTP):</span></span>  
  
    1.  <span data-ttu-id="78209-129">Klicken Sie im mittleren Bereich der InfoArea mit der rechten Maustaste auf das zuvor erstellte Ziel, und wählen Sie anschließend **Create data transfer process**(Datenübertragungsprozess erstellen) aus.</span><span class="sxs-lookup"><span data-stu-id="78209-129">In the middle pane of the InfoArea, right-click the previously created destination, and then select **"Create data transfer process"**.</span></span>  
  
    2.  <span data-ttu-id="78209-130">Konfigurieren, speichern, und aktivieren Sie den Datenübertragungsprozess.</span><span class="sxs-lookup"><span data-stu-id="78209-130">Configure, save, and activate the DTP.</span></span>  
  
    3.  <span data-ttu-id="78209-131">Klicken Sie im Menü auf **Goto**(Gehe zu) und dann auf **Settings for Batch Manager**(Einstellungen für Batch-Manager).</span><span class="sxs-lookup"><span data-stu-id="78209-131">On the menu, click **Goto**, and then click **Settings for Batch Manager**.</span></span>  
  
    4.  <span data-ttu-id="78209-132">Aktualisieren Sie den Wert für **Number of processes** (Anzahl von Prozessen) für die serielle Verarbeitung auf 1.</span><span class="sxs-lookup"><span data-stu-id="78209-132">Update **Number of processes** to 1 for serial processing.</span></span>  
  
4.  <span data-ttu-id="78209-133">Erstellen Sie eine Prozesskette:</span><span class="sxs-lookup"><span data-stu-id="78209-133">Create a process chain:</span></span>  
  
    1.  <span data-ttu-id="78209-134">Wählen Sie bei der Konfiguration der Prozesskette die Option **Start Using Metadata Chain or API** (Metadatenkette oder API verwenden) als **Scheduling Options** (Planungsoptionen) für **Start Process**(Prozess starten) aus, und fügen Sie dann den zuvor erstellten Datenübertragungsprozess als nachfolgenden Knoten hinzu.</span><span class="sxs-lookup"><span data-stu-id="78209-134">When configuring the process chain, select the **Start Using Metadata Chain or API** as the **Scheduling Options** of the **Start Process**, and then add the previously created DTP as the subsequent node.</span></span>  
  
    2.  <span data-ttu-id="78209-135">Speichern und aktivieren Sie die Prozesskette.</span><span class="sxs-lookup"><span data-stu-id="78209-135">Save and activate the process chain.</span></span>  
  
     <span data-ttu-id="78209-136">Die SAP BW-Quelle kann die Prozesskette aufrufen, um den Datenübertragungsprozess zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="78209-136">The SAP BW source can call the process chain to activate the data transfer process.</span></span>  
  
##  <a name="connecting-to-the-sap-netweaver-bw-system"></a><a name="bkmk_Connect_Database"></a> <span data-ttu-id="78209-137">Herstellen einer Verbindung mit dem SAP NetWeaver BW-System</span><span class="sxs-lookup"><span data-stu-id="78209-137">Connecting to the SAP Netweaver BW System</span></span>  
 <span data-ttu-id="78209-138">Um eine Verbindung mit dem SAP NetWeaver BW-System, Version 7, herzustellen, verwendet die SQL BW-Quelle den SAP BW-Verbindungs-Manager, der im Lieferumfang des [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW-Pakets enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="78209-138">To connect to the SAP Netweaver BW version 7 system, the SAP BW source uses the SAP BW connection manager that is part of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW package.</span></span> <span data-ttu-id="78209-139">Der SAP BW-Verbindungs-Manager ist der einzige [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Verbindungs-Manager, der von der SAP BW-Quelle verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="78209-139">The SAP BW connection manager is the only [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] connection manager that the SAP BW source can use.</span></span>  
  
 <span data-ttu-id="78209-140">Weitere Informationen zum SAP BW-Verbindungs-Manager finden Sie unter [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="78209-140">For more information about the SAP BW connection manager, see [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span></span>  
  
##  <a name="configuring-the-sap-bw-source"></a><a name="bkmk_Configure_Source"></a> <span data-ttu-id="78209-141">Konfigurieren der SAP BW-Quelle</span><span class="sxs-lookup"><span data-stu-id="78209-141">Configuring the SAP BW Source</span></span>  
 <span data-ttu-id="78209-142">Es gibt folgende Möglichkeiten, um die SAP BW-Quelle zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="78209-142">You can configure the SAP BW source in the following ways:</span></span>  
  
-   <span data-ttu-id="78209-143">Suchen Sie das OHS (Open Hub Service)-Ziel, das zum Extrahieren von Daten verwendet werden soll, und wählen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="78209-143">Look up and select the Open Hub Service (OHS) destination to use to extract data.</span></span>  
  
-   <span data-ttu-id="78209-144">Wählen Sie eine der folgenden Methoden zum Extrahieren von Daten aus:</span><span class="sxs-lookup"><span data-stu-id="78209-144">Select one of the following methods for extracting data:</span></span>  
  
    -   <span data-ttu-id="78209-145">Lösen Sie eine Prozesskette aus.</span><span class="sxs-lookup"><span data-stu-id="78209-145">Trigger a process chain.</span></span> <span data-ttu-id="78209-146">In diesem Fall wird der Extrahierungsprozess vom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket gestartet.</span><span class="sxs-lookup"><span data-stu-id="78209-146">In this case, the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package starts the extraction process.</span></span>  
  
    -   <span data-ttu-id="78209-147">Warten Sie auf die Benachrichtigung vom SAP NetWeaver BW-System, um mit der Extrahierung zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="78209-147">Wait for notification from the SAP Netweaver BW system to begin an extraction.</span></span> <span data-ttu-id="78209-148">In diesem Fall wird der Extrahierungsprozess vom SAP NetWeaver BW-System gestartet.</span><span class="sxs-lookup"><span data-stu-id="78209-148">In this case, the SAP Netweaver BW system starts the extraction process.</span></span>  
  
    -   <span data-ttu-id="78209-149">Rufen Sie die Daten ab, die einer bestimmten Anforderungs-ID zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="78209-149">Retrieve the data that is associated with a particular Request ID.</span></span> <span data-ttu-id="78209-150">In diesem Fall hat das SAP NetWeaver BW-System die Daten bereits in eine interne Tabelle extrahiert, und die Daten werden gerade vom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket gelesen.</span><span class="sxs-lookup"><span data-stu-id="78209-150">In this case, the SAP Netweaver BW system has already extracted the data to an internal table, and the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package just reads the data.</span></span>  
  
-   <span data-ttu-id="78209-151">Je nach der Methode, die Sie zum Extrahieren von Daten ausgewählt haben, stellen Sie die folgenden zusätzlichen Informationen bereit:</span><span class="sxs-lookup"><span data-stu-id="78209-151">Depending on the method selected for extracting data, provide the following additional information:</span></span>  
  
    -   <span data-ttu-id="78209-152">Geben Sie für die Option **P – Prozesskette auslösen** den Host- und den Dienstnamen des Gateways, die Programm-ID für das RFC-Ziel und den Namen der Prozesskette an.</span><span class="sxs-lookup"><span data-stu-id="78209-152">For the **P - Trigger Process Chain** option, provide the gateway host name, gateway service name, program ID for the RFC destination, and name of the process chain.</span></span>  
  
    -   <span data-ttu-id="78209-153">Geben Sie für die Option **W – Benachrichtigung abwarten** den Host- und den Servernamen des Gateways sowie die Programm-ID für das RFC-Ziel an.</span><span class="sxs-lookup"><span data-stu-id="78209-153">For the **W - Wait for Notify** option, provide the gateway host name, the gateway server name, and the program ID for the RFC destination.</span></span> <span data-ttu-id="78209-154">Sie können auch das Timeout (in Sekunden) angeben.</span><span class="sxs-lookup"><span data-stu-id="78209-154">You can also specify the timeout (in seconds).</span></span> <span data-ttu-id="78209-155">Das Timeout ist die maximale Zeit, die die Quelle auf eine Benachrichtigung wartet.</span><span class="sxs-lookup"><span data-stu-id="78209-155">The timeout is the maximum period of time that the source will wait to be notified.</span></span>  
  
    -   <span data-ttu-id="78209-156">Geben Sie für die Option **E – Nur extrahieren** die Anforderungs-ID an.</span><span class="sxs-lookup"><span data-stu-id="78209-156">For the **E - Extract Only** option, provide the Request ID.</span></span>  
  
-   <span data-ttu-id="78209-157">Geben Sie Regeln für die Zeichenfolgenkonvertierung an.</span><span class="sxs-lookup"><span data-stu-id="78209-157">Specify rules for string conversion.</span></span> <span data-ttu-id="78209-158">(Konvertieren Sie beispielsweise alle Zeichenfolgen abhängig davon, ob das SAP NetWeaver BW-System ein Unicode-System ist oder nicht, oder konvertieren Sie alle Zeichenfolgen in `varchar` oder `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="78209-158">(For example, convert all strings depending on whether the SAP Netweaver BW system is Unicode or not, or convert all strings to `varchar` or `nvarchar`).</span></span>  
  
-   <span data-ttu-id="78209-159">Verwenden Sie die ausgewählten Optionen, um die zu extrahierenden Daten in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="78209-159">Use the options that you have selected to preview the data to be extracted.</span></span>  
  
 <span data-ttu-id="78209-160">Sie können auch die Protokollierung von RFC-Funktionsaufrufen durch die Quelle aktivieren.</span><span class="sxs-lookup"><span data-stu-id="78209-160">You can also enable logging of RFC function calls by the source.</span></span> <span data-ttu-id="78209-161">(Diese Protokollierung wird separat von der optionalen Protokollierung ausgeführt, die Sie für [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Pakete aktivieren können.) Sie aktivieren die Protokollierung von RFC-Funktionsaufrufen bei der Konfiguration des SAP BW-Verbindungs-Managers, der von der Quelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="78209-161">(This logging is separate from the optional logging that you can enable on [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.) You enable logging of RFC function calls when you configure the SAP BW connection manager that the source will use.</span></span> <span data-ttu-id="78209-162">Weitere Informationen zur Konfiguration des SAP BW-Verbindungs-Managers finden Sie unter [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="78209-162">For more information about how to configure the SAP BW connection manager, see [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span></span>  
  
 <span data-ttu-id="78209-163">Wenn Sie nicht alle Werte kennen, die zur Konfiguration der Quelle erforderlich sind, müssen Sie ggf. Ihren SAP-Administrator um Unterstützung bitten.</span><span class="sxs-lookup"><span data-stu-id="78209-163">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="78209-164">Eine exemplarische Vorgehensweise, die zeigt, wie der SAP BW-Verbindungs-Manager sowie die zugehörige Quelle und das zugehörige Ziel konfiguriert und verwendet werden, finden Sie im Whitepaper [Verwenden von SQL Server 2008 Integration Services und SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span><span class="sxs-lookup"><span data-stu-id="78209-164">For a walkthrough that demonstrates how to configure and use the SAP BW connection manager, source, and destination, see the white paper, [Using SQL Server 2008 Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span></span> <span data-ttu-id="78209-165">In diesem Whitepaper wird auch erläutert, wie die erforderlichen Objekte in SAP BW konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="78209-165">This white paper also shows how to configure the required objects in SAP BW.</span></span>  
  
### <a name="using-the-ssis-designer-to-configure-the-source"></a><span data-ttu-id="78209-166">Konfigurieren der Quelle mit dem SSIS-Designer</span><span class="sxs-lookup"><span data-stu-id="78209-166">Using the SSIS Designer to Configure the Source</span></span>  
 <span data-ttu-id="78209-167">Um weitere Informationen zu den Eigenschaften der SAP BW-Quelle zu erhalten, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können, klicken Sie auf eines der folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="78209-167">For more information about the properties of the SAP BW source that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="78209-168">Quellen-Editor für SAP BW &#40;Seite Verbindungs-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="78209-168">SAP BW Source Editor &#40;Connection Manager Page&#41;</span></span>](sap-bw-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="78209-169">Quellen-Editor für SAP BW &#40;Seite Spalten&#41;</span><span class="sxs-lookup"><span data-stu-id="78209-169">SAP BW Source Editor &#40;Columns Page&#41;</span></span>](sap-bw-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="78209-170">Quellen-Editor für SAP BW &#40;Seite Fehlerausgabe&#41;</span><span class="sxs-lookup"><span data-stu-id="78209-170">SAP BW Source Editor &#40;Error Output Page&#41;</span></span>](sap-bw-source-editor-error-output-page.md)  
  
-   [<span data-ttu-id="78209-171">Quellen-Editor für SAP BW &#40;Seite Erweitert&#41;</span><span class="sxs-lookup"><span data-stu-id="78209-171">SAP BW Source Editor &#40;Advanced Page&#41;</span></span>](sap-bw-source-editor-advanced-page.md)  
  
 <span data-ttu-id="78209-172">Während Sie die SAP BW-Quelle konfigurieren, können Sie auch verschiedene Dialogfelder verwenden, um SAP NetWeaver BW-Objekte zu suchen oder die Quelldaten in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="78209-172">While you are configuring the SAP BW source, you can also use various dialog boxes to look up SAP Netweaver BW objects or to preview the source data.</span></span> <span data-ttu-id="78209-173">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu diesen Dialogfeldern zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="78209-173">For more information about these dialog boxes, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="78209-174">RFC-Ziel suchen</span><span class="sxs-lookup"><span data-stu-id="78209-174">Look Up RFC Destination</span></span>](look-up-rfc-destination.md)  
  
-   [<span data-ttu-id="78209-175">Prozesskette suchen</span><span class="sxs-lookup"><span data-stu-id="78209-175">Look Up Process Chain</span></span>](look-up-process-chain.md)  
  
-   [<span data-ttu-id="78209-176">Anforderungsprotokoll</span><span class="sxs-lookup"><span data-stu-id="78209-176">Request Log</span></span>](request-log.md)  
  
-   [<span data-ttu-id="78209-177">Vorschau</span><span class="sxs-lookup"><span data-stu-id="78209-177">Preview</span></span>](preview.md)  
  
## <a name="see-also"></a><span data-ttu-id="78209-178">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="78209-178">See Also</span></span>  
 [<span data-ttu-id="78209-179">Komponenten von Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="78209-179">Microsoft Connector 1.1 for SAP BW Components</span></span>](../microsoft-connector-for-sap-bw-components.md)  
  
  
