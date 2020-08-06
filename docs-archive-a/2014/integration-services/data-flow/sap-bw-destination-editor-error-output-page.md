---
title: Ziel-Editor für SAP BW (Seite Fehlerausgabe) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a543d811-0bd2-4890-a0d3-f5fdcd4524b8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9ffd58580865a71626252aa2d177530e41156537
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695902"
---
# <a name="sap-bw-destination-editor-error-output-page"></a><span data-ttu-id="4120c-102">Ziel-Editor für SAP BW (Seite Fehlerausgabe)</span><span class="sxs-lookup"><span data-stu-id="4120c-102">SAP BW Destination Editor (Error Output Page)</span></span>
  <span data-ttu-id="4120c-103">Auf der Seite **Fehlerausgabe** im **Ziel-Editor für SAP BW** geben Sie Optionen für die Fehlerbehandlung an.</span><span class="sxs-lookup"><span data-stu-id="4120c-103">Use the **Error Output** page of the **SAP BW Destination Editor** to specify error handling options.</span></span>  
  
 <span data-ttu-id="4120c-104">Weitere Informationen zum SAP BW-Ziel von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW finden Sie unter [SAP BW-Ziel](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="4120c-104">To learn more about the SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4120c-105">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="4120c-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="4120c-106">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="4120c-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="4120c-107">**So öffnen Sie die Seite "Fehlerausgabe"**</span><span class="sxs-lookup"><span data-stu-id="4120c-107">**To open the Error Output page**</span></span>  
  
1.  <span data-ttu-id="4120c-108">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket, in dem das SAP BW-Ziel enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="4120c-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="4120c-109">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf das SAP BW-Ziel.</span><span class="sxs-lookup"><span data-stu-id="4120c-109">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="4120c-110">Klicken Sie im **Ziel-Editor für SAP BW**auf **Fehlerausgabe** , um die Seite **Fehlerausgabe** des Editors zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4120c-110">In the **SAP BW Destination Editor**, click **Error Output** to open the **Error Output** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4120c-111">Tastatur</span><span class="sxs-lookup"><span data-stu-id="4120c-111">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4120c-112">Wenn Sie nicht alle Werte kennen, die zur Konfiguration des Ziels erforderlich sind, müssen Sie ggf. Ihren SAP-Administrator um Unterstützung bitten.</span><span class="sxs-lookup"><span data-stu-id="4120c-112">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="4120c-113">**Eingabe oder Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="4120c-113">**Input or Output**</span></span>  
 <span data-ttu-id="4120c-114">Zeigt den Namen der Eingabe an.</span><span class="sxs-lookup"><span data-stu-id="4120c-114">View the name of the input.</span></span>  
  
 <span data-ttu-id="4120c-115">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="4120c-115">**Column**</span></span>  
 <span data-ttu-id="4120c-116">Diese Option wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="4120c-116">This option is not used.</span></span>  
  
 <span data-ttu-id="4120c-117">**Fehler**</span><span class="sxs-lookup"><span data-stu-id="4120c-117">**Error**</span></span>  
 <span data-ttu-id="4120c-118">Gibt an, welche Aktion das Ziel bei einem Fehler ausführen soll: den Fehler ignorieren, die Zeile umleiten oder die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="4120c-118">Specify what the destination should do when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="4120c-119">**Abschneiden**</span><span class="sxs-lookup"><span data-stu-id="4120c-119">**Truncation**</span></span>  
 <span data-ttu-id="4120c-120">Diese Option wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="4120c-120">This option is not used.</span></span>  
  
 <span data-ttu-id="4120c-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="4120c-121">**Description**</span></span>  
 <span data-ttu-id="4120c-122">Zeigt die Beschreibung des Vorgangs an.</span><span class="sxs-lookup"><span data-stu-id="4120c-122">View the description of the operation.</span></span>  
  
 <span data-ttu-id="4120c-123">**Diesen Wert für ausgewählte Zellen festlegen**</span><span class="sxs-lookup"><span data-stu-id="4120c-123">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="4120c-124">Gibt an, wie das Ziel bei einem Fehler oder einer Kürzung mit den ausgewählten Zellen verfahren soll: den Fehler ignorieren, die Zeile umleiten oder die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="4120c-124">Specify what the destination should do to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="4120c-125">**Anwenden**</span><span class="sxs-lookup"><span data-stu-id="4120c-125">**Apply**</span></span>  
 <span data-ttu-id="4120c-126">Wendet die Fehlerbehandlungsoption auf die ausgewählten Zellen an.</span><span class="sxs-lookup"><span data-stu-id="4120c-126">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4120c-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4120c-127">See Also</span></span>  
 <span data-ttu-id="4120c-128">[Ziel-Editor für SAP BW &#40;Seite „Verbindungs-Manager“&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="4120c-128">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="4120c-129">[Ziel-Editor für SAP BW &#40;Seite „Zuordnungen“&#41;](sap-bw-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="4120c-129">[SAP BW Destination Editor &#40;Mappings Page&#41;](sap-bw-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="4120c-130">[Ziel-Editor für SAP BW &#40;Seite „Erweitert“&#41;](sap-bw-destination-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="4120c-130">[SAP BW Destination Editor &#40;Advanced Page&#41;](sap-bw-destination-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="4120c-131">F1-Hilfe zu Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="4120c-131">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
