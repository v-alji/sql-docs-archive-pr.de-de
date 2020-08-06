---
title: Quellen-Editor für SAP BW (Seite „Fehlerausgabe“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b6e23b0c-949a-46d1-8424-4dc3d9035e79
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1a4ad2d02d3f5ec5c1a786019e18fa01665fdc0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695894"
---
# <a name="sap-bw-source-editor-error-output-page"></a><span data-ttu-id="01dfd-102">Quellen-Editor für SAP BW (Seite Fehlerausgabe)</span><span class="sxs-lookup"><span data-stu-id="01dfd-102">SAP BW Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="01dfd-103">Mithilfe der Seite **Fehlerausgabe** im **Quellen-Editor für SAP BW** können Sie Fehlerbehandlungsoptionen auswählen und Eigenschaften für Fehlerausgabespalten festlegen.</span><span class="sxs-lookup"><span data-stu-id="01dfd-103">Use the **Error Output** page of the **SAP BW Source Editor** to select error handling options and to set properties on error output columns.</span></span>  
  
 <span data-ttu-id="01dfd-104">Weitere Informationen zur SAP BW-Quellkomponente von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW finden Sie unter [SAP BW-Quelle](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="01dfd-104">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="01dfd-105">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="01dfd-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="01dfd-106">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="01dfd-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="01dfd-107">Das Extrahieren von Daten aus SAP NetWeaver BW erfordert zusätzliche SAP-Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="01dfd-107">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="01dfd-108">Stimmen Sie diese Anforderungen mit SAP ab.</span><span class="sxs-lookup"><span data-stu-id="01dfd-108">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="01dfd-109">**So öffnen Sie die Seite "Fehlerausgabe"**</span><span class="sxs-lookup"><span data-stu-id="01dfd-109">**To open the Error Output page**</span></span>  
  
1.  <span data-ttu-id="01dfd-110">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket, in dem die SAP BW-Quelle enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="01dfd-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="01dfd-111">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf die SAP BW-Quelle.</span><span class="sxs-lookup"><span data-stu-id="01dfd-111">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="01dfd-112">Klicken Sie im **Quellen-Editor für SAP BW**auf **Fehlerausgabe** , um die Seite **Fehlerausgabe** des Editors zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="01dfd-112">In the **SAP BW Source Editor**, click **Error Output** to open the **Error Output** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="01dfd-113">Tastatur</span><span class="sxs-lookup"><span data-stu-id="01dfd-113">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="01dfd-114">Wenn Sie nicht alle Werte kennen, die zur Konfiguration der Quelle erforderlich sind, müssen Sie ggf. Ihren SAP-Administrator um Unterstützung bitten.</span><span class="sxs-lookup"><span data-stu-id="01dfd-114">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="01dfd-115">**Eingabe oder Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="01dfd-115">**Input or Output**</span></span>  
 <span data-ttu-id="01dfd-116">Zeigt den Namen der Datenquelle an.</span><span class="sxs-lookup"><span data-stu-id="01dfd-116">View the name of the data source.</span></span>  
  
 <span data-ttu-id="01dfd-117">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="01dfd-117">**Column**</span></span>  
 <span data-ttu-id="01dfd-118">Zeigt die externen Spalten (Quellspalten) an, die im Dialogfeld **Quellen-Editor für SAP BW** auf der Seite **Spalten** ausgewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="01dfd-118">View the external (source) columns that you selected on the **Columns** page of the **SAP BW Source Editor** dialog box.</span></span> <span data-ttu-id="01dfd-119">Weitere Informationen zu diesem Dialogfeld finden Sie unter [Quellen-Editor für SAP BW &#40;Seite „Spalten“&#41;](sap-bw-source-editor-columns-page.md).</span><span class="sxs-lookup"><span data-stu-id="01dfd-119">For more information about this dialog box, see [SAP BW Source Editor &#40;Columns Page&#41;](sap-bw-source-editor-columns-page.md).</span></span>  
  
 <span data-ttu-id="01dfd-120">**Fehler**</span><span class="sxs-lookup"><span data-stu-id="01dfd-120">**Error**</span></span>  
 <span data-ttu-id="01dfd-121">Gibt an, wie die SAP BW-Quellkomponente bei einem Fehler vorgehen soll: den Fehler ignorieren, die Zeile umleiten oder die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="01dfd-121">Specify what the SAP BW source component should do when there is an error: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="01dfd-122">**Abschneiden**</span><span class="sxs-lookup"><span data-stu-id="01dfd-122">**Truncation**</span></span>  
 <span data-ttu-id="01dfd-123">Gibt an, wie die SAP BW-Quellkomponente bei einer Kürzung vorgehen soll: den Fehler ignorieren, die Zeile umleiten oder die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="01dfd-123">Specify what the SAP BW source component should do when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="01dfd-124">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="01dfd-124">**Description**</span></span>  
 <span data-ttu-id="01dfd-125">Zeigt die Beschreibung des Fehlers an.</span><span class="sxs-lookup"><span data-stu-id="01dfd-125">View the description of the error.</span></span>  
  
 <span data-ttu-id="01dfd-126">**Diesen Wert für ausgewählte Zellen festlegen**</span><span class="sxs-lookup"><span data-stu-id="01dfd-126">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="01dfd-127">Gibt an, wie die SAP BW-Quellkomponente im Falle eines Fehlers oder einer Kürzung vorgehen soll: den Fehler ignorieren, die Zeile umleiten oder die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="01dfd-127">Specify what the SAP BW source component should do to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="01dfd-128">**Anwenden**</span><span class="sxs-lookup"><span data-stu-id="01dfd-128">**Apply**</span></span>  
 <span data-ttu-id="01dfd-129">Wendet die Fehlerbehandlungsoption auf die ausgewählten Zellen an.</span><span class="sxs-lookup"><span data-stu-id="01dfd-129">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01dfd-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="01dfd-130">See Also</span></span>  
 <span data-ttu-id="01dfd-131">[Quellen-Editor für SAP BW &#40;Seite „Verbindungs-Manager“&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="01dfd-131">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="01dfd-132">[Quellen-Editor für SAP BW &#40;Seite Spalten&#41;](sap-bw-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="01dfd-132">[SAP BW Source Editor &#40;Columns Page&#41;](sap-bw-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="01dfd-133">[Quellen-Editor für SAP BW &#40;Seite „Erweitert“&#41;](sap-bw-source-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="01dfd-133">[SAP BW Source Editor &#40;Advanced Page&#41;](sap-bw-source-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="01dfd-134">F1-Hilfe zu Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="01dfd-134">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
