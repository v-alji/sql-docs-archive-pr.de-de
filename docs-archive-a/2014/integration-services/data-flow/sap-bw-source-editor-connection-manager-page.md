---
title: Quellen-Editor für SAP BW (Seite „Verbindungs-Manager“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 2a6dc531-85ca-43c5-a65f-3ad3f7d537c4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8c6b1782daf8c00b3b3d3a7d13b5ffa00adeeba2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695898"
---
# <a name="sap-bw-source-editor-connection-manager-page"></a><span data-ttu-id="6efe8-102">Quellen-Editor für SAP BW (Seite Verbindungs-Manager)</span><span class="sxs-lookup"><span data-stu-id="6efe8-102">SAP BW Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="6efe8-103">Auf der Seite **Verbindungs-Manager** des Dialogfelds **Quellen-Editor für SAP BW** können Sie den SAP BW-Verbindungs-Manager für die SAP BW-Quelle auswählen.</span><span class="sxs-lookup"><span data-stu-id="6efe8-103">Use the **Connection Manager** page of the **SAP BW Source Editor** to select the SAP BW connection manager for the SAP BW source.</span></span> <span data-ttu-id="6efe8-104">Auf dieser Seite wählen Sie außerdem den Ausführungsmodus und die Parameter aus, mit denen Sie die Daten aus dem SAP NetWeaver BW-System extrahieren.</span><span class="sxs-lookup"><span data-stu-id="6efe8-104">On this page, you also select the execution mode and the parameters for extracting the data from the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="6efe8-105">Weitere Informationen zur SAP BW-Quellkomponente von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW finden Sie unter [SAP BW-Quelle](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="6efe8-105">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6efe8-106">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="6efe8-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="6efe8-107">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="6efe8-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6efe8-108">Das Extrahieren von Daten aus SAP NetWeaver BW erfordert zusätzliche SAP-Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="6efe8-108">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="6efe8-109">Stimmen Sie diese Anforderungen mit SAP ab.</span><span class="sxs-lookup"><span data-stu-id="6efe8-109">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="6efe8-110">**So öffnen Sie die Seite "Verbindungs-Manager"**</span><span class="sxs-lookup"><span data-stu-id="6efe8-110">**To open the Connection Manager page**</span></span>  
  
1.  <span data-ttu-id="6efe8-111">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket, in dem die SAP BW-Quelle enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="6efe8-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="6efe8-112">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf die SAP BW-Quelle.</span><span class="sxs-lookup"><span data-stu-id="6efe8-112">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="6efe8-113">Klicken Sie im **Quellen-Editor für SAP BW**auf **Verbindungs-Manager** , um die Seite **Verbindungs-Manager** des Editors zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6efe8-113">In the **SAP BW Source Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="6efe8-114">Statische Optionen</span><span class="sxs-lookup"><span data-stu-id="6efe8-114">Static Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6efe8-115">Wenn Sie nicht alle Werte kennen, die zur Konfiguration der Quelle erforderlich sind, müssen Sie ggf. Ihren SAP-Administrator um Unterstützung bitten.</span><span class="sxs-lookup"><span data-stu-id="6efe8-115">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="6efe8-116">**SAP BW-Verbindungs-Manager**</span><span class="sxs-lookup"><span data-stu-id="6efe8-116">**SAP BW connection manager**</span></span>  
 <span data-ttu-id="6efe8-117">Wählen Sie in der Liste einen vorhandenen Verbindungs-Manager aus, oder erstellen Sie eine neue Verbindung, indem Sie auf **Neu**klicken.</span><span class="sxs-lookup"><span data-stu-id="6efe8-117">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="6efe8-118">**Neu**</span><span class="sxs-lookup"><span data-stu-id="6efe8-118">**New**</span></span>  
 <span data-ttu-id="6efe8-119">Erstellen Sie mithilfe des Dialogfelds **SAP BW-Verbindungs-Manager** einen neuen Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="6efe8-119">Create a new connection manager by using the **SAP BW Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="6efe8-120">Weitere Informationen zu diesem Dialogfeld finden Sie unter [SAP BW Connection Manager Editor](../sap-bw-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="6efe8-120">For more information about this dialog box, see [SAP BW Connection Manager Editor](../sap-bw-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="6efe8-121">**OHS-Ziel**</span><span class="sxs-lookup"><span data-stu-id="6efe8-121">**OHS destination**</span></span>  
 <span data-ttu-id="6efe8-122">Wählen Sie das OHS (Open Hub Service)-Ziel aus, das zum Extrahieren von Daten aus der Quelle verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6efe8-122">Select the Open Hub Service (OHS) destination to use to extract data from the source.</span></span>  
  
 <span data-ttu-id="6efe8-123">**Ausführungsmodus**</span><span class="sxs-lookup"><span data-stu-id="6efe8-123">**Execution mode**</span></span>  
 <span data-ttu-id="6efe8-124">Gibt die Methode zum Extrahieren von Daten aus der Quelle an.</span><span class="sxs-lookup"><span data-stu-id="6efe8-124">Specify the method for extracting data from the source.</span></span>  
  
|<span data-ttu-id="6efe8-125">Option</span><span class="sxs-lookup"><span data-stu-id="6efe8-125">Option</span></span>|<span data-ttu-id="6efe8-126">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6efe8-126">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="6efe8-127">**P - Prozesskette auslösen**</span><span class="sxs-lookup"><span data-stu-id="6efe8-127">**P - Trigger Process Chain**</span></span>|<span data-ttu-id="6efe8-128">Lösen Sie eine Prozesskette aus.</span><span class="sxs-lookup"><span data-stu-id="6efe8-128">Trigger a process chain.</span></span> <span data-ttu-id="6efe8-129">In diesem Fall wird der Extrahierungsprozess vom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket gestartet.</span><span class="sxs-lookup"><span data-stu-id="6efe8-129">In this case, the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package starts the extraction process.</span></span>|  
|<span data-ttu-id="6efe8-130">**W - Benachrichtigung abwarten**</span><span class="sxs-lookup"><span data-stu-id="6efe8-130">**W - Wait for Notify**</span></span>|<span data-ttu-id="6efe8-131">Warten Sie auf die Benachrichtigung vom SAP NetWeaver BW-System, um mit dem Extrahieren von Daten zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="6efe8-131">Wait for notification from the SAP Netweaver BW system to begin extracting the data.</span></span> <span data-ttu-id="6efe8-132">In diesem Fall wird der Extrahierungsprozess vom SAP NetWeaver BW-System gestartet.</span><span class="sxs-lookup"><span data-stu-id="6efe8-132">In this case, the SAP Netweaver BW system starts the extraction process.</span></span>|  
|<span data-ttu-id="6efe8-133">**E - Nur extrahieren**</span><span class="sxs-lookup"><span data-stu-id="6efe8-133">**E - Extract Only**</span></span>|<span data-ttu-id="6efe8-134">Rufen Sie die Daten ab, die einer bestimmten Anforderungs-ID zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="6efe8-134">Retrieve the data that is associated with a particular Request ID.</span></span> <span data-ttu-id="6efe8-135">In diesem Fall hat das SAP NetWeaver BW-System die Daten bereits in eine interne Tabelle extrahiert, und die Daten werden gerade vom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket gelesen.</span><span class="sxs-lookup"><span data-stu-id="6efe8-135">In this case, the SAP Netweaver BW system has already extracted the data into an internal table, and the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package just reads the data.</span></span>|  
  
 <span data-ttu-id="6efe8-136">**Vorschau**</span><span class="sxs-lookup"><span data-stu-id="6efe8-136">**Preview**</span></span>  
 <span data-ttu-id="6efe8-137">Öffnen Sie das Dialogfeld **Vorschau** , in dem Sie eine Vorschau der Ergebnisse anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="6efe8-137">Open the **Preview** dialog box in which you can preview results.</span></span> <span data-ttu-id="6efe8-138">Weitere Informationen finden Sie unter [Preview](preview.md).</span><span class="sxs-lookup"><span data-stu-id="6efe8-138">For more information, see [Preview](preview.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6efe8-139">Die Daten werden tatsächlich mithilfe der Option **Vorschau** extrahiert, die im Quellen-Editor für SAP BW auf der Seite **Verbindungs-Manager** verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="6efe8-139">The **Preview** option, that is available on the **Connection Manager** page of the SAP BW Source Editor, actually extracts data.</span></span> <span data-ttu-id="6efe8-140">Wenn Sie SAP NetWeaver BW so konfiguriert haben, dass nur Daten extrahiert werden, die sich seit der letzten Extrahierung geändert haben, schließen Sie die in der Vorschau angezeigten Daten durch Auswahl von **Vorschau** aus der nachfolgenden Extrahierung aus.</span><span class="sxs-lookup"><span data-stu-id="6efe8-140">If you have configured SAP Netweaver BW to extract only data that has changed since the previous extraction, selecting **Preview** will exclude the previewed data from the next extraction.</span></span>  
  
 <span data-ttu-id="6efe8-141">Wenn Sie auf **Vorschau**klicken, wird gleichzeitig das Dialogfeld **Anforderungsprotokoll** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6efe8-141">When you click **Preview**, you also open the **Request Log** dialog box.</span></span> <span data-ttu-id="6efe8-142">Sie können dieses Dialogfeld verwenden, um die Ereignisse anzuzeigen, die protokolliert werden, während Beispieldaten vom SAP NetWeaver BW-System angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="6efe8-142">You can use this dialog box to view the events that are logged during the request that is made to the SAP Netweaver BW system for sample data.</span></span> <span data-ttu-id="6efe8-143">Weitere Informationen finden Sie unter [Request Log](request-log.md).</span><span class="sxs-lookup"><span data-stu-id="6efe8-143">For more information, see [Request Log](request-log.md).</span></span>  
  
## <a name="execution-mode-dynamic-options"></a><span data-ttu-id="6efe8-144">Optionen für den dynamischen Ausführungsmodus</span><span class="sxs-lookup"><span data-stu-id="6efe8-144">Execution Mode Dynamic Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6efe8-145">Wenn Sie nicht alle Werte kennen, die zur Konfiguration der Quelle erforderlich sind, müssen Sie ggf. Ihren SAP-Administrator um Unterstützung bitten.</span><span class="sxs-lookup"><span data-stu-id="6efe8-145">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
### <a name="execution-mode--p---trigger-process-chain"></a><span data-ttu-id="6efe8-146">Ausführungsmodus = P - Prozesskette auslösen</span><span class="sxs-lookup"><span data-stu-id="6efe8-146">Execution Mode = P - Trigger Process Chain</span></span>  
  
#### <a name="rfc-destination-options"></a><span data-ttu-id="6efe8-147">Optionen für "RFC-Ziel"</span><span class="sxs-lookup"><span data-stu-id="6efe8-147">RFC Destination Options</span></span>  
 <span data-ttu-id="6efe8-148">Diese Werte müssen nicht im Voraus bekannt sein und eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6efe8-148">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="6efe8-149">Verwenden Sie die Schaltfläche **Suchen** , um das entsprechende RFC-Ziel zu suchen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="6efe8-149">Use the **Look up** button to find and select the appropriate RFC destination.</span></span> <span data-ttu-id="6efe8-150">Nachdem Sie ein RFC-Ziel ausgewählt haben, werden die entsprechenden Werte für diese Optionen von der Komponente eingegeben.</span><span class="sxs-lookup"><span data-stu-id="6efe8-150">After you select an RFC destination, the component enters the appropriate values for these options.</span></span>  
  
 <span data-ttu-id="6efe8-151">**Gatewayhost**</span><span class="sxs-lookup"><span data-stu-id="6efe8-151">**Gateway host**</span></span>  
 <span data-ttu-id="6efe8-152">Geben Sie den Servernamen oder die IP-Adresse des Gatewayhosts ein.</span><span class="sxs-lookup"><span data-stu-id="6efe8-152">Enter the server name or IP address of the gateway host.</span></span> <span data-ttu-id="6efe8-153">Normalerweise ist der Name oder die IP-Adresse identisch mit dem SAP-Anwendungsserver.</span><span class="sxs-lookup"><span data-stu-id="6efe8-153">Usually, the name or IP address is the same as the SAP application server.</span></span>  
  
 <span data-ttu-id="6efe8-154">**Gatewaydienst**</span><span class="sxs-lookup"><span data-stu-id="6efe8-154">**Gateway service**</span></span>  
 <span data-ttu-id="6efe8-155">Geben Sie den Namen des Gatewaydiensts im Format `sapgwNN` ein, wobei `NN` der Systemnummer entspricht.</span><span class="sxs-lookup"><span data-stu-id="6efe8-155">Enter the name of the gateway service, in the format `sapgwNN`, where `NN` is the system number.</span></span>  
  
 <span data-ttu-id="6efe8-156">**Programm-ID**</span><span class="sxs-lookup"><span data-stu-id="6efe8-156">**Program ID**</span></span>  
 <span data-ttu-id="6efe8-157">Geben Sie die Programm-ID ein, die dem RFC-Ziel zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="6efe8-157">Enter the Program ID that is associated with the RFC destination.</span></span>  
  
 <span data-ttu-id="6efe8-158">**Suchen**</span><span class="sxs-lookup"><span data-stu-id="6efe8-158">**Look up**</span></span>  
 <span data-ttu-id="6efe8-159">Suchen Sie das RFC-Ziel mithilfe des Dialogfelds **RFC-Ziel suchen** .</span><span class="sxs-lookup"><span data-stu-id="6efe8-159">Look up the RFC destination by using the **Look Up RFC Destination** dialog box.</span></span> <span data-ttu-id="6efe8-160">Weitere Informationen zu diesem Dialogfeld finden Sie unter [Look Up RFC Destination](look-up-rfc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="6efe8-160">For more information about this dialog box, see [Look Up RFC Destination](look-up-rfc-destination.md).</span></span>  
  
#### <a name="process-chain-options"></a><span data-ttu-id="6efe8-161">Optionen für "Prozesskette"</span><span class="sxs-lookup"><span data-stu-id="6efe8-161">Process Chain Options</span></span>  
 <span data-ttu-id="6efe8-162">Diese Werte müssen nicht im Voraus bekannt sein und eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6efe8-162">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="6efe8-163">Verwenden Sie die Schaltfläche **Suchen** , um die entsprechende Prozesskette zu suchen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="6efe8-163">Use the **Look up** button to find and select the appropriate process chain.</span></span> <span data-ttu-id="6efe8-164">Nachdem Sie eine Prozesskette ausgewählt haben, wird der entsprechende Wert für die Option von der Komponente eingegeben.</span><span class="sxs-lookup"><span data-stu-id="6efe8-164">After you select a process chain, the component enters the appropriate value for the option.</span></span>  
  
 <span data-ttu-id="6efe8-165">**Prozesskette**</span><span class="sxs-lookup"><span data-stu-id="6efe8-165">**Process chain**</span></span>  
 <span data-ttu-id="6efe8-166">Geben Sie den Namen der Prozesskette ein, die von der Quelle ausgelöst werden soll.</span><span class="sxs-lookup"><span data-stu-id="6efe8-166">Enter the name of the process chain to be triggered by the source.</span></span>  
  
 <span data-ttu-id="6efe8-167">**Suchen**</span><span class="sxs-lookup"><span data-stu-id="6efe8-167">**Look up**</span></span>  
 <span data-ttu-id="6efe8-168">Suchen Sie die Prozesskette mithilfe des Dialogfelds **Prozesskette suchen** .</span><span class="sxs-lookup"><span data-stu-id="6efe8-168">Look up the process chain by using the **Look Up Process Chain** dialog box.</span></span> <span data-ttu-id="6efe8-169">Weitere Informationen zu diesem Dialogfeld finden Sie unter [Look Up Process Chain](look-up-process-chain.md).</span><span class="sxs-lookup"><span data-stu-id="6efe8-169">For more information about this dialog box, see [Look Up Process Chain](look-up-process-chain.md).</span></span>  
  
### <a name="execution-mode--w---wait-for-notify"></a><span data-ttu-id="6efe8-170">Ausführungsmodus = W - Benachrichtigung abwarten</span><span class="sxs-lookup"><span data-stu-id="6efe8-170">Execution Mode = W - Wait for Notify</span></span>  
  
#### <a name="rfc-destination-options"></a><span data-ttu-id="6efe8-171">Optionen für "RFC-Ziel"</span><span class="sxs-lookup"><span data-stu-id="6efe8-171">RFC Destination Options</span></span>  
 <span data-ttu-id="6efe8-172">Diese Werte müssen nicht im Voraus bekannt sein und eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6efe8-172">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="6efe8-173">Verwenden Sie die Schaltfläche **Suchen** , um das entsprechende RFC-Ziel zu suchen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="6efe8-173">Use the **Look up** button to find and select the appropriate RFC destination.</span></span> <span data-ttu-id="6efe8-174">Nachdem Sie ein RFC-Ziel ausgewählt haben, werden die entsprechenden Werte für die Optionen von der Komponente eingegeben.</span><span class="sxs-lookup"><span data-stu-id="6efe8-174">After you select an RFC destination, the component enters the appropriate values for the options.</span></span>  
  
 <span data-ttu-id="6efe8-175">**Gatewayhost**</span><span class="sxs-lookup"><span data-stu-id="6efe8-175">**Gateway host**</span></span>  
 <span data-ttu-id="6efe8-176">Geben Sie den Servernamen oder die IP-Adresse des Gatewayhosts ein.</span><span class="sxs-lookup"><span data-stu-id="6efe8-176">Enter the server name or IP address of the gateway host.</span></span> <span data-ttu-id="6efe8-177">Normalerweise ist der Name oder die IP-Adresse identisch mit dem SAP-Anwendungsserver.</span><span class="sxs-lookup"><span data-stu-id="6efe8-177">Usually, the name or IP address is the same as the SAP application server.</span></span>  
  
 <span data-ttu-id="6efe8-178">**Gatewaydienst**</span><span class="sxs-lookup"><span data-stu-id="6efe8-178">**Gateway service**</span></span>  
 <span data-ttu-id="6efe8-179">Geben Sie den Namen des Gatewaydiensts im Format `sapgwNN` ein, wobei `NN` der Systemnummer entspricht.</span><span class="sxs-lookup"><span data-stu-id="6efe8-179">Enter the name of the gateway service, in the format `sapgwNN`, where `NN` is the system number.</span></span>  
  
 <span data-ttu-id="6efe8-180">**Programm-ID**</span><span class="sxs-lookup"><span data-stu-id="6efe8-180">**Program ID**</span></span>  
 <span data-ttu-id="6efe8-181">Geben Sie die Programm-ID ein, die dem RFC-Ziel zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="6efe8-181">Enter the Program ID that is associated with the RFC destination.</span></span>  
  
 <span data-ttu-id="6efe8-182">**Suchen**</span><span class="sxs-lookup"><span data-stu-id="6efe8-182">**Look up**</span></span>  
 <span data-ttu-id="6efe8-183">Suchen Sie das RFC-Ziel mithilfe des Dialogfelds **RFC-Ziel suchen** .</span><span class="sxs-lookup"><span data-stu-id="6efe8-183">Look up the RFC destination by using the **Look Up RFC Destination** dialog box.</span></span> <span data-ttu-id="6efe8-184">Weitere Informationen zu diesem Dialogfeld finden Sie unter [Look Up RFC Destination](look-up-rfc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="6efe8-184">For more information about this dialog box, see [Look Up RFC Destination](look-up-rfc-destination.md).</span></span>  
  
### <a name="execution-mode--e---extract-only"></a><span data-ttu-id="6efe8-185">Ausführungsmodus = E - Nur extrahieren</span><span class="sxs-lookup"><span data-stu-id="6efe8-185">Execution Mode = E - Extract Only</span></span>  
 <span data-ttu-id="6efe8-186">**Anfrage-ID**</span><span class="sxs-lookup"><span data-stu-id="6efe8-186">**Request ID**</span></span>  
 <span data-ttu-id="6efe8-187">Geben Sie die Anforderungs-ID ein, die der Extrahierung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="6efe8-187">Enter the Request ID that is associated with the extraction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6efe8-188">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6efe8-188">See Also</span></span>  
 <span data-ttu-id="6efe8-189">[Quellen-Editor für SAP BW &#40;Seite Spalten&#41;](sap-bw-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="6efe8-189">[SAP BW Source Editor &#40;Columns Page&#41;](sap-bw-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="6efe8-190">[Quellen-Editor für SAP BW &#40;Seite „Fehlerausgabe“&#41;](sap-bw-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="6efe8-190">[SAP BW Source Editor &#40;Error Output Page&#41;](sap-bw-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="6efe8-191">[Quellen-Editor für SAP BW &#40;Seite „Erweitert“&#41;](sap-bw-source-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="6efe8-191">[SAP BW Source Editor &#40;Advanced Page&#41;](sap-bw-source-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="6efe8-192">F1-Hilfe zu Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="6efe8-192">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
