---
title: Ziel-Editor für SAP BW (Seite „Verbindungs-Manager“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 04ae38f8-5287-45a3-826a-8aac5dd15a91
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0dd628f1a0fec09490e0d3720610d1232882ed92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695910"
---
# <a name="sap-bw-destination-editor-connection-manager-page"></a><span data-ttu-id="28672-102">Ziel-Editor für SAP BW (Seite Verbindungs-Manager)</span><span class="sxs-lookup"><span data-stu-id="28672-102">SAP BW Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="28672-103">Verwenden Sie die Seite **Verbindungs-Manager** im **Ziel-Editor für SAP BW** , um den SAP BW-Verbindungs-Manager auszuwählen, der vom SAP BW-Ziel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="28672-103">Use the **Connection Manager** page of the **SAP BW Destination Editor** to select the SAP BW connection manager that the SAP BW destination will use.</span></span> <span data-ttu-id="28672-104">Auf dieser Seite wählen Sie außerdem die Parameter aus, die zum Laden der Daten in das SAP NetWeaver BW-System verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="28672-104">On this page, you also select the parameters for loading the data into the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="28672-105">Weitere Informationen zum SAP BW-Ziel von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW finden Sie unter [SAP BW-Ziel](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="28672-105">To learn more about the SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="28672-106">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="28672-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="28672-107">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="28672-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="28672-108">**So öffnen Sie die Seite "Verbindungs-Manager"**</span><span class="sxs-lookup"><span data-stu-id="28672-108">**To open the Connection Manager page**</span></span>  
  
1.  <span data-ttu-id="28672-109">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket, in dem das SAP BW-Ziel enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="28672-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="28672-110">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf das SAP BW-Ziel.</span><span class="sxs-lookup"><span data-stu-id="28672-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="28672-111">Klicken Sie im **Ziel-Editor für SAP BW**auf **Verbindungs-Manager** , um die Seite **Verbindungs-Manager** des Editors zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="28672-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="28672-112">Tastatur</span><span class="sxs-lookup"><span data-stu-id="28672-112">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="28672-113">Wenn Sie nicht alle Werte kennen, die zur Konfiguration des Ziels erforderlich sind, müssen Sie ggf. Ihren SAP-Administrator um Unterstützung bitten.</span><span class="sxs-lookup"><span data-stu-id="28672-113">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="28672-114">**SAP BW-Verbindungs-Manager**</span><span class="sxs-lookup"><span data-stu-id="28672-114">**SAP BW connection manager**</span></span>  
 <span data-ttu-id="28672-115">Wählen Sie in der Liste einen vorhandenen Verbindungs-Manager aus, oder erstellen Sie eine neue Verbindung, indem Sie auf **Neu**klicken.</span><span class="sxs-lookup"><span data-stu-id="28672-115">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="28672-116">**Neu**</span><span class="sxs-lookup"><span data-stu-id="28672-116">**New**</span></span>  
 <span data-ttu-id="28672-117">Erstellen Sie mithilfe des Dialogfelds **SAP BW-Verbindungs-Manager** einen neuen Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="28672-117">Create a new connection manager by using the **SAP BW Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="28672-118">**Testladevorgang**</span><span class="sxs-lookup"><span data-stu-id="28672-118">**Test Load**</span></span>  
 <span data-ttu-id="28672-119">Führen Sie einen Testladevorgang aus, in dem die ausgewählten Einstellungen verwendet und 0 Zeilen geladen werden.</span><span class="sxs-lookup"><span data-stu-id="28672-119">Perform a test of the loading process that uses the settings that you have selected and loads zero rows.</span></span>  
  
### <a name="infopackageinfosource-options"></a><span data-ttu-id="28672-120">Optionen für "InfoPackage/InfoSource"</span><span class="sxs-lookup"><span data-stu-id="28672-120">InfoPackage/InfoSource Options</span></span>  
 <span data-ttu-id="28672-121">Diese Werte müssen nicht im Voraus bekannt sein und eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="28672-121">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="28672-122">Verwenden Sie die Schaltfläche **Suchen** , um das entsprechende InfoPackage zu suchen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="28672-122">Use the **Look up** button to find and select the appropriate InfoPackage.</span></span> <span data-ttu-id="28672-123">Nachdem Sie ein InfoPackage ausgewählt haben, werden die entsprechenden Werte für diese Optionen von der Komponente eingegeben.</span><span class="sxs-lookup"><span data-stu-id="28672-123">After you select an InfoPackage, the component enters the appropriate values for these options.</span></span>  
  
 <span data-ttu-id="28672-124">**InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="28672-124">**InfoPackage**</span></span>  
 <span data-ttu-id="28672-125">Geben Sie den Namen für das InfoPackage ein.</span><span class="sxs-lookup"><span data-stu-id="28672-125">Enter the name of the InfoPackage.</span></span>  
  
 <span data-ttu-id="28672-126">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="28672-126">**InfoSource**</span></span>  
 <span data-ttu-id="28672-127">Geben Sie den Namen für die InfoSource ein.</span><span class="sxs-lookup"><span data-stu-id="28672-127">Enter the name of the InfoSource.</span></span>  
  
 <span data-ttu-id="28672-128">**Typ**</span><span class="sxs-lookup"><span data-stu-id="28672-128">**Type**</span></span>  
 <span data-ttu-id="28672-129">Geben Sie das Einzelzeichen ein, durch das der InfoSource-Typ identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="28672-129">Enter the single-character that identifies the type of the InfoSource.</span></span> <span data-ttu-id="28672-130">In der folgenden Tabelle sind die zulässigen Einzelzeichenwerte aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="28672-130">The following table lists the acceptable single-character values.</span></span>  
  
|<span data-ttu-id="28672-131">value</span><span class="sxs-lookup"><span data-stu-id="28672-131">Value</span></span>|<span data-ttu-id="28672-132">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="28672-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="28672-133">**D**</span><span class="sxs-lookup"><span data-stu-id="28672-133">**D**</span></span>|<span data-ttu-id="28672-134">Transaktionsdaten</span><span class="sxs-lookup"><span data-stu-id="28672-134">Transaction data</span></span>|  
|<span data-ttu-id="28672-135">**M**</span><span class="sxs-lookup"><span data-stu-id="28672-135">**M**</span></span>|<span data-ttu-id="28672-136">Masterdaten</span><span class="sxs-lookup"><span data-stu-id="28672-136">Master data</span></span>|  
|<span data-ttu-id="28672-137">**T**</span><span class="sxs-lookup"><span data-stu-id="28672-137">**T**</span></span>|<span data-ttu-id="28672-138">Texte</span><span class="sxs-lookup"><span data-stu-id="28672-138">Texts</span></span>|  
|<span data-ttu-id="28672-139">**H**</span><span class="sxs-lookup"><span data-stu-id="28672-139">**H**</span></span>|<span data-ttu-id="28672-140">Hierarchiedaten</span><span class="sxs-lookup"><span data-stu-id="28672-140">Hierarchy data</span></span>|  
  
 <span data-ttu-id="28672-141">**Logisches System**</span><span class="sxs-lookup"><span data-stu-id="28672-141">**Logical system**</span></span>  
 <span data-ttu-id="28672-142">Geben Sie den Namen des logischen Systems ein, das dem InfoPackage zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="28672-142">Enter the name of the logical system that is associated with the InfoPackage.</span></span>  
  
 <span data-ttu-id="28672-143">**Suchen**</span><span class="sxs-lookup"><span data-stu-id="28672-143">**Look up**</span></span>  
 <span data-ttu-id="28672-144">Suchen Sie das InfoPackage mithilfe des Dialogfelds **InfoPackage suchen** .</span><span class="sxs-lookup"><span data-stu-id="28672-144">Look up the InfoPackage by using the **Look Up InfoPackage** dialog box.</span></span> <span data-ttu-id="28672-145">Weitere Informationen zu diesem Dialogfeld finden Sie unter [Look Up InfoPackage](look-up-infopackage.md).</span><span class="sxs-lookup"><span data-stu-id="28672-145">For more information about this dialog box, see [Look Up InfoPackage](look-up-infopackage.md).</span></span>  
  
### <a name="rfc-destination-options"></a><span data-ttu-id="28672-146">Optionen für "RFC-Ziel"</span><span class="sxs-lookup"><span data-stu-id="28672-146">RFC Destination Options</span></span>  
 <span data-ttu-id="28672-147">Diese Werte müssen nicht im Voraus bekannt sein und eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="28672-147">You do not have to know and enter these values in advance.</span></span> <span data-ttu-id="28672-148">Verwenden Sie die Schaltfläche **Suchen** , um das entsprechende RFC-Ziel zu suchen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="28672-148">Use the **Look up** button to find and select the appropriate RFC destination.</span></span> <span data-ttu-id="28672-149">Nachdem Sie ein RFC-Ziel ausgewählt haben, werden die entsprechenden Werte für diese Optionen von der Komponente eingegeben.</span><span class="sxs-lookup"><span data-stu-id="28672-149">After you select an RFC destination, the component enters the appropriate values for these options.</span></span>  
  
 <span data-ttu-id="28672-150">**Gatewayhost**</span><span class="sxs-lookup"><span data-stu-id="28672-150">**Gateway host**</span></span>  
 <span data-ttu-id="28672-151">Geben Sie den Servernamen oder die IP-Adresse des Gatewayhosts ein.</span><span class="sxs-lookup"><span data-stu-id="28672-151">Enter the server name or IP address of the gateway host.</span></span> <span data-ttu-id="28672-152">Normalerweise ist der Name oder die IP-Adresse identisch mit dem SAP-Anwendungsserver.</span><span class="sxs-lookup"><span data-stu-id="28672-152">Usually, the name or IP address is the same as the SAP application server.</span></span>  
  
 <span data-ttu-id="28672-153">**Gatewaydienst**</span><span class="sxs-lookup"><span data-stu-id="28672-153">**Gateway service**</span></span>  
 <span data-ttu-id="28672-154">Geben Sie den Namen des Gatewaydiensts im Format `sapgwNN` ein, wobei `NN` der Systemnummer entspricht.</span><span class="sxs-lookup"><span data-stu-id="28672-154">Enter the name of the gateway service, in the format `sapgwNN`, where `NN` is the system number.</span></span>  
  
 <span data-ttu-id="28672-155">**Programm-ID**</span><span class="sxs-lookup"><span data-stu-id="28672-155">**Program ID**</span></span>  
 <span data-ttu-id="28672-156">Geben Sie die Programm-ID ein, die dem RFC-Ziel zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="28672-156">Enter the Program ID that is associated with the RFC destination.</span></span>  
  
 <span data-ttu-id="28672-157">**Suchen**</span><span class="sxs-lookup"><span data-stu-id="28672-157">**Look up**</span></span>  
 <span data-ttu-id="28672-158">Suchen Sie das RFC-Ziel mithilfe des Dialogfelds **RFC-Ziel suchen** .</span><span class="sxs-lookup"><span data-stu-id="28672-158">Look up the RFC destination by using the **Look Up RFC Destination** dialog box.</span></span> <span data-ttu-id="28672-159">Weitere Informationen zu diesem Dialogfeld finden Sie unter [Look Up RFC Destination](look-up-rfc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="28672-159">For more information about this dialog box, see [Look Up RFC Destination](look-up-rfc-destination.md).</span></span>  
  
### <a name="create-sap-bw-objects-options"></a><span data-ttu-id="28672-160">Optionen für "SAP BW-Objekte erstellen"</span><span class="sxs-lookup"><span data-stu-id="28672-160">Create SAP BW Objects Options</span></span>  
 <span data-ttu-id="28672-161">**Objekttyp auswählen**</span><span class="sxs-lookup"><span data-stu-id="28672-161">**Select object type**</span></span>  
 <span data-ttu-id="28672-162">Wählen Sie den Typ des SAP NetWeaver BW-Objekts aus, das Sie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="28672-162">Select the type of SAP Netweaver BW object that you want to create.</span></span> <span data-ttu-id="28672-163">Wählen Sie einen der folgenden Typen aus:</span><span class="sxs-lookup"><span data-stu-id="28672-163">You can select one of the following types:</span></span>  
  
-   <span data-ttu-id="28672-164">InfoObject</span><span class="sxs-lookup"><span data-stu-id="28672-164">InfoObject</span></span>  
  
-   <span data-ttu-id="28672-165">InfoCube</span><span class="sxs-lookup"><span data-stu-id="28672-165">InfoCube</span></span>  
  
-   <span data-ttu-id="28672-166">InfoSource</span><span class="sxs-lookup"><span data-stu-id="28672-166">InfoSource</span></span>  
  
-   <span data-ttu-id="28672-167">InfoPackage</span><span class="sxs-lookup"><span data-stu-id="28672-167">InfoPackage</span></span>  
  
 <span data-ttu-id="28672-168">**Erstellen**</span><span class="sxs-lookup"><span data-stu-id="28672-168">**Create**</span></span>  
 <span data-ttu-id="28672-169">Erstellen Sie den ausgewählten SAP NetWeaver BW-Objekttyp.</span><span class="sxs-lookup"><span data-stu-id="28672-169">Create the selected type of SAP Netweaver BW object.</span></span>  
  
|<span data-ttu-id="28672-170">Objekttyp</span><span class="sxs-lookup"><span data-stu-id="28672-170">Object Type</span></span>|<span data-ttu-id="28672-171">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="28672-171">Result</span></span>|  
|-----------------|------------|  
|<span data-ttu-id="28672-172">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="28672-172">**InfoObject**</span></span>|<span data-ttu-id="28672-173">Erstellen Sie ein neues InfoObject mithilfe des Dialogfelds **Neues InfoObject erstellen** .</span><span class="sxs-lookup"><span data-stu-id="28672-173">Create a new InfoObject by using the **Create New InfoObject** dialog box.</span></span> <span data-ttu-id="28672-174">Weitere Informationen zu diesem Dialogfeld finden Sie unter [Create New InfoObject](create-new-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="28672-174">For more information about this dialog box, see [Create New InfoObject](create-new-infoobject.md).</span></span>|  
|<span data-ttu-id="28672-175">**InfoCube**</span><span class="sxs-lookup"><span data-stu-id="28672-175">**InfoCube**</span></span>|<span data-ttu-id="28672-176">Erstellen Sie einen neuen InfoCube mithilfe des Dialogfelds **InfoCube für Transaktionsdaten erstellen** .</span><span class="sxs-lookup"><span data-stu-id="28672-176">Create a new InfoCube by using the **Create InfoCube for Transaction Data** dialog box.</span></span> <span data-ttu-id="28672-177">Weitere Informationen zu diesem Dialogfeld finden Sie unter [Create InfoCube for Transaction Data](create-infocube-for-transaction-data.md).</span><span class="sxs-lookup"><span data-stu-id="28672-177">For more information about this dialog box, see [Create InfoCube for Transaction Data](create-infocube-for-transaction-data.md).</span></span>|  
|<span data-ttu-id="28672-178">**InfoSource**</span><span class="sxs-lookup"><span data-stu-id="28672-178">**InfoSource**</span></span>|<span data-ttu-id="28672-179">Erstellen Sie eine neue InfoSource, indem Sie erst das Dialogfeld **InfoSource erstellen** und dann das Dialogfeld **InfoSource für Transaktionsdaten erstellen** oder **InfoSource für Masterdaten erstellen** verwenden.</span><span class="sxs-lookup"><span data-stu-id="28672-179">Create a new InfoSource by using the **Create InfoSource** dialog box, and then by using the **Create InfoSource for Transaction Data** or the **Create InfoSource for Master Data** dialog box.</span></span> <span data-ttu-id="28672-180">Weitere Informationen zu diesen Dialogfeldern finden Sie unter [Create InfoSource](create-infosource.md), [Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md) und [Create InfoSource for Master Data](create-infosource-for-master-data.md).</span><span class="sxs-lookup"><span data-stu-id="28672-180">For more information about these dialog boxes, see [Create InfoSource](create-infosource.md), [Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md) and [Create InfoSource for Master Data](create-infosource-for-master-data.md).</span></span>|  
|<span data-ttu-id="28672-181">**InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="28672-181">**InfoPackage**</span></span>|<span data-ttu-id="28672-182">Erstellen Sie ein neues InfoPackage mithilfe des Dialogfelds **InfoPackage erstellen** .</span><span class="sxs-lookup"><span data-stu-id="28672-182">Create a new InfoPackage by using the **Create InfoPackage** dialog box.</span></span> <span data-ttu-id="28672-183">Weitere Informationen zu diesem Dialogfeld finden Sie unter [Create InfoPackage](create-infopackage.md).</span><span class="sxs-lookup"><span data-stu-id="28672-183">For more information about this dialog box, see [Create InfoPackage](create-infopackage.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28672-184">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="28672-184">See Also</span></span>  
 <span data-ttu-id="28672-185">[Ziel-Editor für SAP BW &#40;Seite „Zuordnungen“&#41;](sap-bw-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="28672-185">[SAP BW Destination Editor &#40;Mappings Page&#41;](sap-bw-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="28672-186">[Ziel-Editor für SAP BW &#40;Seite „Fehlerausgabe“&#41;](sap-bw-destination-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="28672-186">[SAP BW Destination Editor &#40;Error Output Page&#41;](sap-bw-destination-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="28672-187">[Ziel-Editor für SAP BW &#40;Seite „Erweitert“&#41;](sap-bw-destination-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="28672-187">[SAP BW Destination Editor &#40;Advanced Page&#41;](sap-bw-destination-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="28672-188">F1-Hilfe zu Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="28672-188">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
