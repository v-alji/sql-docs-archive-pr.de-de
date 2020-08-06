---
title: Ziel-Editor für SAP BW (Seite „Erweitert“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 862957db-bbc6-4dda-bc0e-591457f1baa7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0c5ca943b804ad39cc391cb1cf7f06e056ddbe56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618816"
---
# <a name="sap-bw-destination-editor-advanced-page"></a><span data-ttu-id="d3d38-102">Ziel-Editor für SAP BW (Seite Erweitert)</span><span class="sxs-lookup"><span data-stu-id="d3d38-102">SAP BW Destination Editor (Advanced Page)</span></span>
  <span data-ttu-id="d3d38-103">Auf der Seite **Erweitert** im **Ziel-Editor für SAP BW** legen Sie erweiterte Einstellungen wie Paketgröße und Timoutinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="d3d38-103">Use the **Advanced** page of the **SAP BW Destination Editor** to set advanced settings such as package size and time-out information.</span></span>  
  
 <span data-ttu-id="d3d38-104">Weitere Informationen zum SAP BW-Ziel von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW finden Sie unter [SAP BW-Ziel](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="d3d38-104">To learn more about the SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d3d38-105">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="d3d38-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="d3d38-106">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="d3d38-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="d3d38-107">**So öffnen Sie die Seite "Erweitert"**</span><span class="sxs-lookup"><span data-stu-id="d3d38-107">**To open the Advanced page**</span></span>  
  
1.  <span data-ttu-id="d3d38-108">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket, in dem das SAP BW-Ziel enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="d3d38-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="d3d38-109">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf das SAP BW-Ziel.</span><span class="sxs-lookup"><span data-stu-id="d3d38-109">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="d3d38-110">Klicken Sie im **Ziel-Editor für SAP BW**auf **Erweitert** , um die Seite **Erweitert** des Editors zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d3d38-110">In the **SAP BW Destination Editor**, click **Advanced** to open the **Advanced** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d3d38-111">Tastatur</span><span class="sxs-lookup"><span data-stu-id="d3d38-111">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d3d38-112">Wenn Sie nicht alle Werte kennen, die zur Konfiguration des Ziels erforderlich sind, müssen Sie ggf. Ihren SAP-Administrator um Unterstützung bitten.</span><span class="sxs-lookup"><span data-stu-id="d3d38-112">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="d3d38-113">**Paketgröße**</span><span class="sxs-lookup"><span data-stu-id="d3d38-113">**Package size**</span></span>  
 <span data-ttu-id="d3d38-114">Geben Sie an, wie viele Datenzeilen auf einmal übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="d3d38-114">Specify how many rows of data will be transferred at a time.</span></span> <span data-ttu-id="d3d38-115">Der optimale Wert für diesen Parameter hängt vom SAP NetWeaver BW-System und ggf. zusätzlichen Schritten zur Verarbeitung der Daten ab.</span><span class="sxs-lookup"><span data-stu-id="d3d38-115">The optimal value for this parameter depends on the SAP Netweaver BW system and on additional processing of the data that might occur.</span></span> <span data-ttu-id="d3d38-116">In der Regel liefern Werte zwischen 2.000 und 20.000 die beste Leistung.</span><span class="sxs-lookup"><span data-stu-id="d3d38-116">Typically, values between 2000 and 20000 offer the best performance.</span></span>  
  
 <span data-ttu-id="d3d38-117">**Prozesskette auslösen**</span><span class="sxs-lookup"><span data-stu-id="d3d38-117">**Trigger process chain**</span></span>  
 <span data-ttu-id="d3d38-118">(Optional) Geben Sie den Namen einer Prozesskette an, die ausgelöst wird, nachdem die Daten vollständig geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="d3d38-118">(Optional) Specify the name of a process chain to be triggered after the loading of data is completed.</span></span>  
  
 <span data-ttu-id="d3d38-119">**Timeout beim Warten auf InfoPackage**</span><span class="sxs-lookup"><span data-stu-id="d3d38-119">**Timeout for waiting InfoPackage**</span></span>  
 <span data-ttu-id="d3d38-120">Geben Sie die maximale Anzahl von Sekunden an, die das Ziel wartet, bis das InfoPackage erstellt ist.</span><span class="sxs-lookup"><span data-stu-id="d3d38-120">Specify the maximum number of seconds that the destination should wait for the InfoPackage to finish.</span></span>  
  
 <span data-ttu-id="d3d38-121">**Warten, bis Datenübertragung abgeschlossen ist**</span><span class="sxs-lookup"><span data-stu-id="d3d38-121">**Wait for data transfer to finish**</span></span>  
 <span data-ttu-id="d3d38-122">Geben Sie an, ob das Ziel warten soll, bis das SAP NetWeaver BW-System die Daten vollständig geladen hat.</span><span class="sxs-lookup"><span data-stu-id="d3d38-122">Specify whether the destination should wait until the SAP Netweaver BW system has finished loading the data.</span></span>  
  
 <span data-ttu-id="d3d38-123">**InfoPackage nicht starten (nur warten)**</span><span class="sxs-lookup"><span data-stu-id="d3d38-123">**No InfoPackage Start (Only Wait)**</span></span>  
 <span data-ttu-id="d3d38-124">Geben Sie an, dass vom Ziel kein InfoPackage ausgelöst, sondern nur auf eine Benachrichtigung gewartet wird, dass das SAP NetWeaver BW-System mit dem Laden der Daten begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="d3d38-124">Specify that the destination does not trigger an InfoPackage, but just waits for notification that the SAP Netweaver BW system has started loading the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3d38-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d3d38-125">See Also</span></span>  
 <span data-ttu-id="d3d38-126">[Ziel-Editor für SAP BW &#40;Seite „Verbindungs-Manager“&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="d3d38-126">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="d3d38-127">[Ziel-Editor für SAP BW &#40;Seite „Zuordnungen“&#41;](sap-bw-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="d3d38-127">[SAP BW Destination Editor &#40;Mappings Page&#41;](sap-bw-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="d3d38-128">[Ziel-Editor für SAP BW &#40;Seite „Fehlerausgabe“&#41;](sap-bw-destination-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="d3d38-128">[SAP BW Destination Editor &#40;Error Output Page&#41;](sap-bw-destination-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="d3d38-129">F1-Hilfe zu Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="d3d38-129">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
