---
title: Transformations-Editor für Fuzzysuche (Registerkarte Spalten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzylookuptransformation.columns.f1
helpviewer_keywords:
- Fuzzy Lookup Transformation Editor
ms.assetid: aaf45327-79e9-4760-9b4d-546ace91b5b4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f9294022b52536940916a381d7b811437eaa5814
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696986"
---
# <a name="fuzzy-lookup-transformation-editor-columns-tab"></a><span data-ttu-id="25675-102">Transformations-Editor für Fuzzysuche (Registerkarte Spalten)</span><span class="sxs-lookup"><span data-stu-id="25675-102">Fuzzy Lookup Transformation Editor (Columns Tab)</span></span>
  <span data-ttu-id="25675-103">Auf der Registerkarte **Spalten** des Dialogfelds **Transformations-Editor für Fuzzysuche** können Sie die Eigenschaften für die Eingabe- und Ausgabespalten festlegen.</span><span class="sxs-lookup"><span data-stu-id="25675-103">Use the **Columns** tab of the **Fuzzy Lookup Transformation Editor** dialog box to set properties for input and output columns.</span></span>  
  
 <span data-ttu-id="25675-104">Weitere Informationen zur Transformation für Fuzzysuche finden Sie unter [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="25675-104">To learn more about the Fuzzy Lookup transformation, see [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="25675-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="25675-105">Options</span></span>  
 <span data-ttu-id="25675-106">**Verfügbare Eingabespalten**</span><span class="sxs-lookup"><span data-stu-id="25675-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="25675-107">Um Eingabespalten mit verfügbaren Suchspalten zu verbinden, ziehen Sie diese auf die Suchspalten.</span><span class="sxs-lookup"><span data-stu-id="25675-107">Drag input columns to connect them to available lookup columns.</span></span> <span data-ttu-id="25675-108">Diese Spalten müssen übereinstimmende, unterstützte Datentypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="25675-108">These columns must have matching, supported data types.</span></span> <span data-ttu-id="25675-109">Wählen Sie eine Zuordnungszeile aus, und klicken Sie mit der rechten Maustaste darauf, um die Zuordnungen im Dialogfeld [Beziehungen erstellen](data-flow/transformations/create-relationships.md) zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="25675-109">Select a mapping line and right-click to edit the mappings in the [Create Relationships](data-flow/transformations/create-relationships.md) dialog box.</span></span>  
  
 <span data-ttu-id="25675-110">**Name**</span><span class="sxs-lookup"><span data-stu-id="25675-110">**Name**</span></span>  
 <span data-ttu-id="25675-111">Zeigen Sie die Namen der verfügbaren Eingabespalten an.</span><span class="sxs-lookup"><span data-stu-id="25675-111">View the names of the available input columns.</span></span>  
  
 <span data-ttu-id="25675-112">**Pass-Through**</span><span class="sxs-lookup"><span data-stu-id="25675-112">**Pass Through**</span></span>  
 <span data-ttu-id="25675-113">Geben Sie an, ob die Eingabespalten in der Ausgabe der Transformation eingeschlossen sein sollen.</span><span class="sxs-lookup"><span data-stu-id="25675-113">Specify whether to include the input columns in the output of the transformation.</span></span>  
  
 <span data-ttu-id="25675-114">**Verfügbare Suchspalten**</span><span class="sxs-lookup"><span data-stu-id="25675-114">**Available Lookup Columns**</span></span>  
 <span data-ttu-id="25675-115">Wählen Sie mithilfe der Kontrollkästchen die Spalten aus, für die die Fuzzysuchvorgänge ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="25675-115">Use the check boxes to select columns on which to perform fuzzy lookup operations.</span></span>  
  
 <span data-ttu-id="25675-116">**Suchspalte**</span><span class="sxs-lookup"><span data-stu-id="25675-116">**Lookup Column**</span></span>  
 <span data-ttu-id="25675-117">Wählen Sie Suchspalten aus der Liste der verfügbaren Spalten der Verweistabelle aus.</span><span class="sxs-lookup"><span data-stu-id="25675-117">Select lookup columns from the list of available reference table columns.</span></span> <span data-ttu-id="25675-118">Ihre Auswahl wird entsprechend in der Auswahl der Kontrollkästchen in der **Verfügbare Suchspalten** -Tabelle deutlich.</span><span class="sxs-lookup"><span data-stu-id="25675-118">Your selections are reflected in the check box selections in the **Available Lookup Columns** table.</span></span> <span data-ttu-id="25675-119">Durch das Auswählen einer Spalte in der **Verfügbare Suchspalten** -Tabelle wird eine Ausgabespalte erstellt, die den Spaltenwert der Verweistabelle für jede übereinstimmende Zeile enthält, die zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="25675-119">Selecting a column in the **Available Lookup Columns** table creates an output column that contains the reference table column value for each matching row returned.</span></span>  
  
 <span data-ttu-id="25675-120">**Ausgabealias**</span><span class="sxs-lookup"><span data-stu-id="25675-120">**Output Alias**</span></span>  
 <span data-ttu-id="25675-121">Geben Sie einen Alias für die Ausgabe der einzelnen Suchspalten ein.</span><span class="sxs-lookup"><span data-stu-id="25675-121">Type an alias for the output for each lookup column.</span></span> <span data-ttu-id="25675-122">Standardmäßig wird der Name der Suchspalte mit einem angefügten numerischen Indexwert verwendet. Sie können jedoch auch einen beschreibenden Namen angeben, sofern dieser eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="25675-122">The default is the name of the lookup column with a numeric index value appended; however, you can choose any unique, descriptive name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25675-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="25675-123">See Also</span></span>  
 <span data-ttu-id="25675-124">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="25675-124">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="25675-125">[Transformations-Editor für Fuzzysuche &#40;Registerkarte Verweis Tabelle&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-reference-table-tab.md) </span><span class="sxs-lookup"><span data-stu-id="25675-125">[Fuzzy Lookup Transformation Editor &#40;Reference Table Tab&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-reference-table-tab.md) </span></span>  
 [<span data-ttu-id="25675-126">Transformations-Editor für Fuzzysuche &#40;Registerkarte „Erweitert“&#41;</span><span class="sxs-lookup"><span data-stu-id="25675-126">Fuzzy Lookup Transformation Editor &#40;Advanced Tab&#41;</span></span>](../../2014/integration-services/fuzzy-lookup-transformation-editor-advanced-tab.md)  
  
  
