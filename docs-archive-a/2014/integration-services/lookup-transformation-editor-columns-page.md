---
title: Transformations-Editor für Suche (Seite ' Spalten ') | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.columns.f1
helpviewer_keywords:
- Lookup Transformation Editor
ms.assetid: 690ffef5-fd59-4e95-a27d-4fcf0d6b1c0b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b768076d8acbcaef8cbff21783a7697020e027eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618104"
---
# <a name="lookup-transformation-editor-columns-page"></a><span data-ttu-id="099a3-102">Transformations-Editor für Suche (Seite 'Spalten')</span><span class="sxs-lookup"><span data-stu-id="099a3-102">Lookup Transformation Editor (Columns Page)</span></span>
  <span data-ttu-id="099a3-103">Auf der Seite **Spalten** des Dialogfelds **Transformations-Editor für Suche** können Sie den Join zwischen der Quell- und der Verweistabelle angeben sowie Suchspalten aus der Verweistabelle auswählen.</span><span class="sxs-lookup"><span data-stu-id="099a3-103">Use the **Columns** page of the **Lookup Transformation Editor** dialog box to specify the join between the source table and the reference table, and to select lookup columns from the reference table.</span></span>  
  
 <span data-ttu-id="099a3-104">Weitere Informationen zur Transformation für Suche finden Sie unter [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="099a3-104">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="099a3-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="099a3-105">Options</span></span>  
 <span data-ttu-id="099a3-106">**Verfügbare Eingabespalten**</span><span class="sxs-lookup"><span data-stu-id="099a3-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="099a3-107">Zeigt die Liste der verfügbaren Eingabespalten an.</span><span class="sxs-lookup"><span data-stu-id="099a3-107">View the list of available input columns.</span></span> <span data-ttu-id="099a3-108">Die Eingabespalten sind die Spalten im Datenfluss aus einer verbundenen Quelle.</span><span class="sxs-lookup"><span data-stu-id="099a3-108">The input columns are the columns in the data flow from a connected source.</span></span> <span data-ttu-id="099a3-109">Die Datentypen der Eingabe- und Suchspalte müssen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="099a3-109">The input columns and lookup column must have matching data types.</span></span>  
  
 <span data-ttu-id="099a3-110">Mithilfe eines Drag-und-Drop-Vorgangs können Sie verfügbare Eingabespalten bestimmten Suchspalten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="099a3-110">Use a drag-and-drop operation to map available input columns to lookup columns.</span></span>  
  
 <span data-ttu-id="099a3-111">Sie können auch mithilfe der Tastatur Eingabespalten bestimmten Suchspalten zuordnen. Dazu heben Sie eine Spalte in der Tabelle **Verfügbare Eingabespalten** hervor, drücken die Anwendungstaste und klicken dann auf **Zuordnungen bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="099a3-111">You can also map input columns to lookup columns using the keyboard, by highlighting a column in the **Available Input Columns** table, pressing the Application key, and then clicking **Edit Mappings**.</span></span>  
  
 <span data-ttu-id="099a3-112">**Verfügbare Suchspalten**</span><span class="sxs-lookup"><span data-stu-id="099a3-112">**Available Lookup Columns**</span></span>  
 <span data-ttu-id="099a3-113">Zeigt die Liste der Suchspalten an.</span><span class="sxs-lookup"><span data-stu-id="099a3-113">View the list of lookup columns.</span></span> <span data-ttu-id="099a3-114">Die Suchspalten sind Spalten in der Verweistabelle, in denen nach Werten gesucht werden soll, die mit den Eingabespalten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="099a3-114">The lookup columns are columns in the reference table in which you want to look up values that match the input columns.</span></span>  
  
 <span data-ttu-id="099a3-115">Mithilfe eines Drag-und-Drop-Vorgangs können Sie verfügbare Suchspalten bestimmten Eingabespalten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="099a3-115">Use a drag-and-drop operation to map available lookup columns to input columns.</span></span>  
  
 <span data-ttu-id="099a3-116">Wählen Sie mithilfe der Kontrollkästchen die Suchspalten in der Verweistabelle aus, für die die Suchvorgänge ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="099a3-116">Use the check boxes to select lookup columns in the reference table on which to perform lookup operations.</span></span>  
  
 <span data-ttu-id="099a3-117">Sie können auch mithilfe der Tastatur Suchspalten bestimmten Eingabespalten zuordnen. Dazu heben Sie eine Spalte in der Tabelle **Verfügbare Suchspalten** hervor, drücken die Anwendungstaste und klicken dann auf **Zuordnungen bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="099a3-117">You can also map lookup columns to input columns using the keyboard, by highlighting a column in the **Available Lookup Columns** table, pressing the Application key, and then clicking **Edit Mappings**.</span></span>  
  
 <span data-ttu-id="099a3-118">**Suchspalte**</span><span class="sxs-lookup"><span data-stu-id="099a3-118">**Lookup Column**</span></span>  
 <span data-ttu-id="099a3-119">Zeigt die Liste der ausgewählten Suchspalten an.</span><span class="sxs-lookup"><span data-stu-id="099a3-119">View the selected lookup columns.</span></span> <span data-ttu-id="099a3-120">Die Auswahl wird entsprechend in der Auswahl der Kontrollkästchen in der Tabelle **Verfügbare Suchspalten** deutlich.</span><span class="sxs-lookup"><span data-stu-id="099a3-120">The selections are reflected in the check box selections in the **Available Lookup Columns** table.</span></span>  
  
 <span data-ttu-id="099a3-121">**Suchvorgang**</span><span class="sxs-lookup"><span data-stu-id="099a3-121">**Lookup Operation**</span></span>  
 <span data-ttu-id="099a3-122">Wählen Sie in der Liste einen Suchvorgang aus, der für die Suchspalte ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="099a3-122">Select a lookup operation from the list to perform on the lookup column.</span></span>  
  
 <span data-ttu-id="099a3-123">**Ausgabealias**</span><span class="sxs-lookup"><span data-stu-id="099a3-123">**Output Alias**</span></span>  
 <span data-ttu-id="099a3-124">Geben Sie einen Alias für die Ausgabe der einzelnen Suchspalten ein.</span><span class="sxs-lookup"><span data-stu-id="099a3-124">Type an alias for the output for each lookup column.</span></span> <span data-ttu-id="099a3-125">Standardmäßig wird der Name der Suchspalte verwendet. Sie können jedoch auch einen beschreibenden Namen angeben, sofern dieser eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="099a3-125">The default is the name of the lookup column; however, you can select any unique, descriptive name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="099a3-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="099a3-126">See Also</span></span>  
 <span data-ttu-id="099a3-127">[Transformations-Editor für Suche &#40;Seite "Allgemein"&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="099a3-127">[Lookup Transformation Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="099a3-128">[Transformations-Editor für Suche &#40;Verbindungs Seite&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span><span class="sxs-lookup"><span data-stu-id="099a3-128">[Lookup Transformation Editor &#40;Connection Page&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span></span>  
 <span data-ttu-id="099a3-129">[Transformations-Editor für Suche &#40;Seite "Erweitert"&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="099a3-129">[Lookup Transformation Editor &#40;Advanced Page&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span></span>  
 <span data-ttu-id="099a3-130">[Transformations-Editor für Suche &#40;Seite "Fehlerausgabe"&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="099a3-130">[Lookup Transformation Editor &#40;Error Output Page&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="099a3-131">Transformation für Fuzzysuche</span><span class="sxs-lookup"><span data-stu-id="099a3-131">Fuzzy Lookup Transformation</span></span>](data-flow/transformations/fuzzy-lookup-transformation.md)  
  
  
