---
title: Ziel-Editor für SAP BW (Seite „Zuordnungen“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: dfa1f1d6-6b64-4331-bdc5-eaa8b7aa41a1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7c4c2803be3e2649f7425a2974dae8ac0a80fae7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695901"
---
# <a name="sap-bw-destination-editor-mappings-page"></a><span data-ttu-id="a133f-102">Ziel-Editor für SAP BW (Seite Zuordnungen)</span><span class="sxs-lookup"><span data-stu-id="a133f-102">SAP BW Destination Editor (Mappings Page)</span></span>
  <span data-ttu-id="a133f-103">Auf der Seite **Zuordnungen** im **Ziel-Editor für SAP BW** können Sie eine Zuordnung zwischen Eingabe- und Zielspalten vornehmen.</span><span class="sxs-lookup"><span data-stu-id="a133f-103">Use the **Mappings** page of the **SAP BW Destination Editor** to map input columns to destination columns.</span></span>  
  
 <span data-ttu-id="a133f-104">Weitere Informationen zum SAP BW-Ziel von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW finden Sie unter [SAP BW-Ziel](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="a133f-104">To learn more about the SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a133f-105">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="a133f-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="a133f-106">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="a133f-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="a133f-107">**So öffnen Sie die Seite "Zuordnungen"**</span><span class="sxs-lookup"><span data-stu-id="a133f-107">**To open the Mappings page**</span></span>  
  
1.  <span data-ttu-id="a133f-108">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket, in dem das SAP BW-Ziel enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="a133f-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="a133f-109">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf das SAP BW-Ziel.</span><span class="sxs-lookup"><span data-stu-id="a133f-109">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="a133f-110">Klicken Sie im **Ziel-Editor für SAP BW**auf **Zuordnungen** , um die Seite **Zuordnungen** des Editors zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a133f-110">In the **SAP BW Destination Editor**, click **Mappings** to open the **Mappings** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a133f-111">Tastatur</span><span class="sxs-lookup"><span data-stu-id="a133f-111">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a133f-112">Wenn Sie nicht alle Werte kennen, die zur Konfiguration des Ziels erforderlich sind, müssen Sie ggf. Ihren SAP-Administrator um Unterstützung bitten.</span><span class="sxs-lookup"><span data-stu-id="a133f-112">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="a133f-113">Die Seite **Zuordnungen** im **Ziel-Editor für SAP BW** besteht aus zwei Abschnitten:</span><span class="sxs-lookup"><span data-stu-id="a133f-113">The **Mappings** page of the **SAP BW Destination Editor consists** of two sections:</span></span>  
  
-   <span data-ttu-id="a133f-114">Der obere Abschnitt enthält die verfügbaren Eingabe- und Zielspalten. Dort können Sie Zuordnungen zwischen den beiden Spaltentypen erstellen.</span><span class="sxs-lookup"><span data-stu-id="a133f-114">The upper section shows the available input and destination columns and lets you create mappings between these two types of columns.</span></span>  
  
-   <span data-ttu-id="a133f-115">Der untere Abschnitt ist eine Tabelle, der Sie entnehmen können, welche Eingabespalten welchen Ausgabespalten zugeordnet wurden.</span><span class="sxs-lookup"><span data-stu-id="a133f-115">The lower section is a table that lists which input columns have been mapped to which output columns.</span></span>  
  
### <a name="upper-section-options"></a><span data-ttu-id="a133f-116">Optionen im oberen Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a133f-116">Upper Section Options</span></span>  
 <span data-ttu-id="a133f-117">Der obere Abschnitt enthält die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="a133f-117">The upper section has the following options:</span></span>  
  
 <span data-ttu-id="a133f-118">**Verfügbare Eingabespalten**</span><span class="sxs-lookup"><span data-stu-id="a133f-118">**Available Input Columns**</span></span>  
 <span data-ttu-id="a133f-119">Zeigt die Liste der verfügbaren Eingabespalten an.</span><span class="sxs-lookup"><span data-stu-id="a133f-119">View the list of available input columns.</span></span>  
  
 <span data-ttu-id="a133f-120">Um einer Zielspalte eine Eingabespalte zuzuordnen, ziehen Sie eine Spalte aus der Liste **Verfügbare Eingabespalten** auf eine Spalte in der Liste **Verfügbare Zielspalten** .</span><span class="sxs-lookup"><span data-stu-id="a133f-120">To map an input column to a destination column, drag a column from the **Available Input Columns** list and drop that column onto a column in the **Available Destination Columns** list.</span></span>  
  
 <span data-ttu-id="a133f-121">**Verfügbare Zielspalten**</span><span class="sxs-lookup"><span data-stu-id="a133f-121">**Available Destination Columns**</span></span>  
 <span data-ttu-id="a133f-122">Zeigt die Liste der verfügbaren Zielspalten an.</span><span class="sxs-lookup"><span data-stu-id="a133f-122">View the list of available destination columns.</span></span>  
  
 <span data-ttu-id="a133f-123">Um einer Zielspalte eine Eingabespalte zuzuordnen, ziehen Sie eine Spalte aus der Liste **Verfügbare Eingabespalten** auf eine Spalte in der Liste **Verfügbare Zielspalten** .</span><span class="sxs-lookup"><span data-stu-id="a133f-123">To map an input column to destination column, drag a column from the **Available Input Columns** list and drop that column onto a column in the **Available Destination Columns** list.</span></span>  
  
 <span data-ttu-id="a133f-124">Der obere Abschnitt enthält auch ein Kontextmenü, das Sie öffnen, indem Sie mit der rechten Maustaste auf den Hintergrund klicken.</span><span class="sxs-lookup"><span data-stu-id="a133f-124">The upper section also has a context menu that you can open by right-clicking on the background.</span></span> <span data-ttu-id="a133f-125">Das Kontextmenü enthält die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="a133f-125">This context menu contains the following options:</span></span>  
  
-   <span data-ttu-id="a133f-126">**Alle Zuordnungen auswählen**</span><span class="sxs-lookup"><span data-stu-id="a133f-126">**Select All Mappings**</span></span>  
  
-   <span data-ttu-id="a133f-127">**Ausgewählte Zuordnungen löschen**</span><span class="sxs-lookup"><span data-stu-id="a133f-127">**Delete Selected Mappings**</span></span>  
  
-   <span data-ttu-id="a133f-128">**Elemente nach übereinstimmenden Namen zuordnen**</span><span class="sxs-lookup"><span data-stu-id="a133f-128">**Map Items by Matching Names**</span></span>  
  
### <a name="lower-section-columns"></a><span data-ttu-id="a133f-129">Spalten im unteren Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a133f-129">Lower Section Columns</span></span>  
 <span data-ttu-id="a133f-130">Der untere Abschnitt enthält eine Tabelle der Zuordnungen und weist die folgenden Spalten auf:</span><span class="sxs-lookup"><span data-stu-id="a133f-130">The lower section is a table of the mappings, and has the following columns:</span></span>  
  
 <span data-ttu-id="a133f-131">**Eingabespalte**</span><span class="sxs-lookup"><span data-stu-id="a133f-131">**Input Column**</span></span>  
 <span data-ttu-id="a133f-132">Zeigt die ausgewählten Eingabespalten an.</span><span class="sxs-lookup"><span data-stu-id="a133f-132">View the input columns that you have selected.</span></span>  
  
 <span data-ttu-id="a133f-133">Um derselben Zielspalte eine andere Eingabespalte zuzuordnen, wählen Sie eine andere Eingabespalte aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="a133f-133">To map a different input column to the same destination column, select a different input column in the list.</span></span> <span data-ttu-id="a133f-134">Um eine Zuordnung zu entfernen, wählen Sie **\<ignore>** aus, um die Eingabespalte von der Ausgabe auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="a133f-134">To remove a mapping, select **\<ignore>** to exclude the input column from the output.</span></span>  
  
 <span data-ttu-id="a133f-135">**Zielspalte**</span><span class="sxs-lookup"><span data-stu-id="a133f-135">**Destination Column**</span></span>  
 <span data-ttu-id="a133f-136">Zeigt alle verfügbaren Zielspalten an, und zwar unabhängig davon, ob die Spalte zugeordnet ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="a133f-136">View each available destination column, regardless of whether that column is mapped or not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a133f-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a133f-137">See Also</span></span>  
 <span data-ttu-id="a133f-138">[Ziel-Editor für SAP BW &#40;Seite „Verbindungs-Manager“&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="a133f-138">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="a133f-139">[Ziel-Editor für SAP BW &#40;Seite „Fehlerausgabe“&#41;](sap-bw-destination-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="a133f-139">[SAP BW Destination Editor &#40;Error Output Page&#41;](sap-bw-destination-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="a133f-140">[Ziel-Editor für SAP BW &#40;Seite „Erweitert“&#41;](sap-bw-destination-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="a133f-140">[SAP BW Destination Editor &#40;Advanced Page&#41;](sap-bw-destination-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="a133f-141">F1-Hilfe zu Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="a133f-141">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
