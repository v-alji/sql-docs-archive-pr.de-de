---
title: Quellen-Editor für SAP BW (Seite „Spalten“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: c2ec8bb7-be9b-4783-ad88-32512de784b0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ba605360d01abc520cedfbc457dd89319ed83c52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722930"
---
# <a name="sap-bw-source-editor-columns-page"></a><span data-ttu-id="76be1-102">Quellen-Editor für SAP BW (Seite Spalten)</span><span class="sxs-lookup"><span data-stu-id="76be1-102">SAP BW Source Editor (Columns Page)</span></span>
  <span data-ttu-id="76be1-103">Auf der Seite **Spalten** im **Quellen-Editor für SAP BW** können Sie jeder externen Spalte (Quellspalte) eine Ausgabespalte zuordnen.</span><span class="sxs-lookup"><span data-stu-id="76be1-103">Use the **Columns** page of the **SAP BW Source Editor** to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="76be1-104">Weitere Informationen zur SAP BW-Quellkomponente von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW finden Sie unter [SAP BW-Quelle](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="76be1-104">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="76be1-105">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="76be1-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="76be1-106">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="76be1-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="76be1-107">Das Extrahieren von Daten aus SAP NetWeaver BW erfordert zusätzliche SAP-Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="76be1-107">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="76be1-108">Stimmen Sie diese Anforderungen mit SAP ab.</span><span class="sxs-lookup"><span data-stu-id="76be1-108">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="76be1-109">**So öffnen Sie die Seite "Spalten"**</span><span class="sxs-lookup"><span data-stu-id="76be1-109">**To open the Columns page**</span></span>  
  
1.  <span data-ttu-id="76be1-110">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket, in dem die SAP BW-Quelle enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="76be1-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="76be1-111">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf die SAP BW-Quelle.</span><span class="sxs-lookup"><span data-stu-id="76be1-111">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="76be1-112">Klicken Sie im **Quellen-Editor für SAP BW**auf **Spalten** , um die Seite **Spalten** des Editors zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="76be1-112">In the **SAP BW Source Editor**, click **Columns** to open the **Columns** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="76be1-113">Tastatur</span><span class="sxs-lookup"><span data-stu-id="76be1-113">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="76be1-114">Wenn Sie nicht alle Werte kennen, die zur Konfiguration der Quelle erforderlich sind, müssen Sie ggf. Ihren SAP-Administrator um Unterstützung bitten.</span><span class="sxs-lookup"><span data-stu-id="76be1-114">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="76be1-115">**Verfügbare externe Spalten**</span><span class="sxs-lookup"><span data-stu-id="76be1-115">**Available External Columns**</span></span>  
 <span data-ttu-id="76be1-116">Zeigen Sie die Liste der verfügbaren externen Spalten in der Datenquelle an, und wählen Sie dann die Spalten aus, die in den Datenfluss aufgenommen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="76be1-116">View the list of available external columns in the data source, and then select the columns to be included in the data flow.</span></span>  
  
 <span data-ttu-id="76be1-117">Um eine Spalte in den Datenfluss einzuschließen, aktivieren Sie das Kontrollkästchen, das dieser Spalte entspricht.</span><span class="sxs-lookup"><span data-stu-id="76be1-117">To include a column in the data flow, select the check box that corresponds to that column.</span></span> <span data-ttu-id="76be1-118">Die Spalten werden in der Reihenfolge ausgegeben, in der Sie die Kontrollkästchen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="76be1-118">The order in which you select the check boxes determines the order in which columns will be output.</span></span> <span data-ttu-id="76be1-119">Das heißt, das erste aktivierte Kontrollkästchen entspricht der ersten Ausgabespalte, das zweite Kontrollkästchen der zweiten Ausgabespalte usw.</span><span class="sxs-lookup"><span data-stu-id="76be1-119">That is, the first check box that you select will be the first output column, the second check box will be the second output columns, and so on.</span></span>  
  
 <span data-ttu-id="76be1-120">**Externe Spalte**</span><span class="sxs-lookup"><span data-stu-id="76be1-120">**External Column**</span></span>  
 <span data-ttu-id="76be1-121">Zeigt die ausgewählten externen Spalten (Quellspalten) an.</span><span class="sxs-lookup"><span data-stu-id="76be1-121">View the selected external (source) columns.</span></span> <span data-ttu-id="76be1-122">Die ausgewählten Spalten werden in der Reihenfolge angezeigt, in der beim Konfigurieren von Downstreamkomponenten auch die entsprechenden Ausgabespalten angezeigt werden, die Daten aus dieser Quelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="76be1-122">The selected columns appear in the order in which you will see their corresponding output columns when you configure downstream components that consume data from this source.</span></span>  
  
 <span data-ttu-id="76be1-123">Um die Reihenfolge der Spalten in der Liste **Verfügbare externe Spalten** zu ändern, deaktivieren Sie die Kontrollkästchen für alle Spalten.</span><span class="sxs-lookup"><span data-stu-id="76be1-123">To change the order of the columns, in the **Available External Columns** list, clear the check boxes for all columns.</span></span> <span data-ttu-id="76be1-124">Wählen Sie anschließend Spalten in der Reihenfolge aus, in der sie angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="76be1-124">Then, select the columns in the order that you want them to appear.</span></span>  
  
 <span data-ttu-id="76be1-125">**Ausgabespalte**</span><span class="sxs-lookup"><span data-stu-id="76be1-125">**Output Column**</span></span>  
 <span data-ttu-id="76be1-126">Geben Sie für jede Ausgabespalte einen eindeutigen Namen an.</span><span class="sxs-lookup"><span data-stu-id="76be1-126">Provide a unique name for each output column.</span></span> <span data-ttu-id="76be1-127">Der Standardname ist der Name der ausgewählten externen Spalte (Quellspalte).</span><span class="sxs-lookup"><span data-stu-id="76be1-127">The default is the name of the selected external (source) column.</span></span> <span data-ttu-id="76be1-128">Sie können jedoch einen eindeutigen, beschreibenden Namen eingeben.</span><span class="sxs-lookup"><span data-stu-id="76be1-128">However, you can enter any unique, descriptive name.</span></span> [!INCLUDE[ssIS](../../includes/ssis-md.md)] <span data-ttu-id="76be1-129">-Designer die **Ausgabespalte** -Namen für die Spalten an.</span><span class="sxs-lookup"><span data-stu-id="76be1-129">Designer will display the **Output Column** names for the columns when you configure downstream components that consume data from this source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76be1-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76be1-130">See Also</span></span>  
 <span data-ttu-id="76be1-131">[Quellen-Editor für SAP BW &#40;Seite „Verbindungs-Manager“&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="76be1-131">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="76be1-132">[Quellen-Editor für SAP BW &#40;Seite „Fehlerausgabe“&#41;](sap-bw-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="76be1-132">[SAP BW Source Editor &#40;Error Output Page&#41;](sap-bw-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="76be1-133">[Quellen-Editor für SAP BW &#40;Seite „Erweitert“&#41;](sap-bw-source-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="76be1-133">[SAP BW Source Editor &#40;Advanced Page&#41;](sap-bw-source-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="76be1-134">F1-Hilfe zu Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="76be1-134">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
