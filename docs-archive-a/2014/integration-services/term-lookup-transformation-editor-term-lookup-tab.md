---
title: Transformations-Editor für die Begriffs Suche (Registerkarte Begriffs Suche) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.termlookup.termlookup.f1
helpviewer_keywords:
- Term Lookup Transformation Editor
ms.assetid: 245d3466-d51f-4073-978a-694a8d9dfaec
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9bb8c0bd0477d9883640cc3e4d3cb25c2a3a8b27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622208"
---
# <a name="term-lookup-transformation-editor-term-lookup-tab"></a><span data-ttu-id="6ef97-102">Transformations-Editor für Ausdruckssuche (Registerkarte Ausdruckssuche)</span><span class="sxs-lookup"><span data-stu-id="6ef97-102">Term Lookup Transformation Editor (Term Lookup Tab)</span></span>
  <span data-ttu-id="6ef97-103">Mithilfe der Registerkarte **Ausdruckssuche** des Dialogfelds **Transformations-Editor für Ausdruckssuche** können Sie eine Eingabespalte einer Suchspalte in einer Verweistabelle zuordnen und einen Alias für jede Ausgabespalte bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6ef97-103">Use the **Term Lookup** tab of the **Term Lookup Transformation Editor** dialog box to map an input column to a lookup column in a reference table and to provide an alias for each output column.</span></span>  
  
 <span data-ttu-id="6ef97-104">Weitere Informationen zur Transformation für Ausdruckssuche finden Sie unter [Term Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="6ef97-104">To learn more about the Term Lookup transformation, see [Term Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="6ef97-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="6ef97-105">Options</span></span>  
 <span data-ttu-id="6ef97-106">**Verfügbare Eingabespalten**</span><span class="sxs-lookup"><span data-stu-id="6ef97-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="6ef97-107">Wählen Sie mithilfe der Kontrollkästchen die Eingabespalten aus, die unverändert an die Ausgabe weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6ef97-107">Using the check boxes, select input columns to pass through to the output unchanged.</span></span> <span data-ttu-id="6ef97-108">Ziehen Sie eine Eingabespalte auf die Liste **Verfügbare Verweisspalten** , um sie einer Suchspalte in der Verweistabelle zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="6ef97-108">Drag an input column to the **Available Reference Columns** list to map it to a lookup column in the reference table.</span></span> <span data-ttu-id="6ef97-109">Die Eingabe- und Suchspalten müssen übereinstimmende, unterstützte Datentypen haben, entweder DT_NTEXT oder DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="6ef97-109">The input and lookup columns must have matching, supported data types, either DT_NTEXT or DT_WSTR.</span></span> <span data-ttu-id="6ef97-110">Wählen Sie eine Zuordnungszeile aus, und klicken Sie mit der rechten Maustaste darauf, um die Zuordnungen im Dialogfeld [Beziehungen erstellen](data-flow/transformations/create-relationships.md) zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="6ef97-110">Select a mapping line and right-click to edit the mappings in the [Create Relationships](data-flow/transformations/create-relationships.md) dialog box.</span></span>  
  
 <span data-ttu-id="6ef97-111">**Verfügbare Verweisspalten**</span><span class="sxs-lookup"><span data-stu-id="6ef97-111">**Available Reference Columns**</span></span>  
 <span data-ttu-id="6ef97-112">Zeigen Sie die verfügbaren Spalten in der Verweistabelle an.</span><span class="sxs-lookup"><span data-stu-id="6ef97-112">View the available columns in the reference table.</span></span> <span data-ttu-id="6ef97-113">Wählen Sie die Spalte aus, die die Liste der Ausdrücke enthält, für die nach einer Übereinstimmung gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="6ef97-113">Choose the column that contains the list of terms to match.</span></span>  
  
 <span data-ttu-id="6ef97-114">**Pass-Through-Spalte**</span><span class="sxs-lookup"><span data-stu-id="6ef97-114">**Pass-Through Column**</span></span>  
 <span data-ttu-id="6ef97-115">Wählen Sie Spalten aus der Liste der verfügbaren Eingabespalten aus.</span><span class="sxs-lookup"><span data-stu-id="6ef97-115">Select from the list of available input columns.</span></span> <span data-ttu-id="6ef97-116">Ihre Auswahl wird entsprechend in der Auswahl der Kontrollkästchen in der **Verfügbare Eingabespalten** -Tabelle deutlich.</span><span class="sxs-lookup"><span data-stu-id="6ef97-116">Your selections are reflected in the check box selections in the **Available Input Columns** table.</span></span>  
  
 <span data-ttu-id="6ef97-117">**Alias der Ausgabespalte**</span><span class="sxs-lookup"><span data-stu-id="6ef97-117">**Output Column Alias**</span></span>  
 <span data-ttu-id="6ef97-118">Geben Sie einen Alias für jede Spalte ein.</span><span class="sxs-lookup"><span data-stu-id="6ef97-118">Type an alias for each output column.</span></span> <span data-ttu-id="6ef97-119">Standardmäßig wird der Name der Spalte verwendet. Sie können jedoch auch einen beschreibenden Namen angeben, sofern dieser eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="6ef97-119">The default is the name of the column; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="6ef97-120">**Konfigurieren der Fehlerausgabe**</span><span class="sxs-lookup"><span data-stu-id="6ef97-120">**Configure Error Output**</span></span>  
 <span data-ttu-id="6ef97-121">Auf der Registerkarte [Fehlerausgabe konfigurieren](../../2014/integration-services/configure-error-output.md) können Sie die Optionen zur Fehlerbehandlung von Zeilen angeben, die Fehler verursachen.</span><span class="sxs-lookup"><span data-stu-id="6ef97-121">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling options for rows that cause errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ef97-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6ef97-122">See Also</span></span>  
 <span data-ttu-id="6ef97-123">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="6ef97-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="6ef97-124">[Transformations-Editor für die Begriffs Suche &#40;Registerkarte "Verweis Tabelle"&#41;](../../2014/integration-services/term-lookup-transformation-editor-reference-table-tab.md) </span><span class="sxs-lookup"><span data-stu-id="6ef97-124">[Term Lookup Transformation Editor &#40;Reference Table Tab&#41;](../../2014/integration-services/term-lookup-transformation-editor-reference-table-tab.md) </span></span>  
 <span data-ttu-id="6ef97-125">[Transformations-Editor für die Begriffs Suche &#40;Registerkarte "Erweitert"&#41;](../../2014/integration-services/term-lookup-transformation-editor-advanced-tab.md) </span><span class="sxs-lookup"><span data-stu-id="6ef97-125">[Term Lookup Transformation Editor &#40;Advanced Tab&#41;](../../2014/integration-services/term-lookup-transformation-editor-advanced-tab.md) </span></span>  
 [<span data-ttu-id="6ef97-126">Transformation für Ausdrucksextrahierung</span><span class="sxs-lookup"><span data-stu-id="6ef97-126">Term Extraction Transformation</span></span>](data-flow/transformations/term-extraction-transformation.md)  
  
  
