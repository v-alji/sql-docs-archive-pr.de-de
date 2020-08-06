---
title: Transformations-Editor für Suche (Seite ' Fehlerausgabe ') | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.erroroutput.f1
ms.assetid: 15d53bb0-8be1-46fb-b459-04a397e75fac
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9cd78f40a0072f7f0c5c923cdd51431873402f3e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618100"
---
# <a name="lookup-transformation-editor-error-output-page"></a><span data-ttu-id="eb0e4-102">Transformations-Editor für Suche (Seite 'Fehlerausgabe')</span><span class="sxs-lookup"><span data-stu-id="eb0e4-102">Lookup Transformation Editor (Error Output Page)</span></span>
  <span data-ttu-id="eb0e4-103">Auf der Seite **Fehlerausgabe** des Dialogfelds **Transformations-Editor für Suche** geben Sie Optionen für die Fehlerbehandlung an.</span><span class="sxs-lookup"><span data-stu-id="eb0e4-103">Use the **Error Output** page of the **Lookup Transformation Editor** dialog box to specify error handling options.</span></span>  
  
 <span data-ttu-id="eb0e4-104">Weitere Informationen zur Transformation für Suche finden Sie unter [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="eb0e4-104">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="eb0e4-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="eb0e4-105">Options</span></span>  
 <span data-ttu-id="eb0e4-106">**Eingabe/Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="eb0e4-106">**Input/Output**</span></span>  
 <span data-ttu-id="eb0e4-107">Zeigt den Namen der Eingabe an.</span><span class="sxs-lookup"><span data-stu-id="eb0e4-107">View the name of the input.</span></span>  
  
 <span data-ttu-id="eb0e4-108">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="eb0e4-108">**Column**</span></span>  
 <span data-ttu-id="eb0e4-109">Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="eb0e4-109">Not used.</span></span>  
  
 <span data-ttu-id="eb0e4-110">**Fehler**</span><span class="sxs-lookup"><span data-stu-id="eb0e4-110">**Error**</span></span>  
 <span data-ttu-id="eb0e4-111">Geben Sie an, welche Art von Fehler auftreten soll, wenn Zeilen ohne übereinstimmende Einträge im Verweisdataset behandelt werden:</span><span class="sxs-lookup"><span data-stu-id="eb0e4-111">Specify what type of error should occur when handling rows without matching entries in the reference dataset:</span></span>  
  
-   <span data-ttu-id="eb0e4-112">Den Fehler ignorieren und die Zeilen an eine Ausgabe weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="eb0e4-112">Ignore the failure and direct the rows to an output.</span></span>  
  
-   <span data-ttu-id="eb0e4-113">Die Zeilen an eine Fehlerausgabe weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="eb0e4-113">Redirect the rows to an error output.</span></span>  
  
-   <span data-ttu-id="eb0e4-114">Die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="eb0e4-114">Fail the component.</span></span>  
  
 <span data-ttu-id="eb0e4-115">Diese Option ist nicht verfügbar, wenn Sie in der Liste **Angeben, wie Zeilen ohne übereinstimmende Einträge behandelt werden sollen** den Eintrag **Zeilen an Ausgabe nicht übereinstimmender Einträge umleiten** auswählen.</span><span class="sxs-lookup"><span data-stu-id="eb0e4-115">This option is not available when you select **Redirect rows to no match output** in the **Specify how to handle rows with no matching entries** list.</span></span> <span data-ttu-id="eb0e4-116">Diese Liste befindet sich auf der Seite **Allgemein** des Dialogfelds **Transformations-Editor für Suche** .</span><span class="sxs-lookup"><span data-stu-id="eb0e4-116">This list is on the **General** page of the **Lookup Transformation Editor** dialog box.</span></span>  
  
 <span data-ttu-id="eb0e4-117">**Verwandte Themen:** [Fehlerbehandlung in Daten](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="eb0e4-117">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="eb0e4-118">**Abschneiden**</span><span class="sxs-lookup"><span data-stu-id="eb0e4-118">**Truncation**</span></span>  
 <span data-ttu-id="eb0e4-119">Geben Sie an, was geschehen soll, wenn Daten abgeschnitten werden:</span><span class="sxs-lookup"><span data-stu-id="eb0e4-119">Specify what should happen when data truncation occurs:</span></span>  
  
-   <span data-ttu-id="eb0e4-120">Den Fehler ignorieren.</span><span class="sxs-lookup"><span data-stu-id="eb0e4-120">Ignore the failure.</span></span>  
  
-   <span data-ttu-id="eb0e4-121">Die Zeile umleiten.</span><span class="sxs-lookup"><span data-stu-id="eb0e4-121">Redirect the row.</span></span>  
  
-   <span data-ttu-id="eb0e4-122">Die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="eb0e4-122">Fail the component.</span></span>  
  
 <span data-ttu-id="eb0e4-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="eb0e4-123">**Description**</span></span>  
 <span data-ttu-id="eb0e4-124">Zeigt die Beschreibung des Vorgangs an.</span><span class="sxs-lookup"><span data-stu-id="eb0e4-124">View the description of the operation.</span></span>  
  
 <span data-ttu-id="eb0e4-125">**Diesen Wert für ausgewählte Zellen festlegen**</span><span class="sxs-lookup"><span data-stu-id="eb0e4-125">**Set selected cells to this value**</span></span>  
 <span data-ttu-id="eb0e4-126">Geben Sie an, was bei einem Fehler oder beim Abschneiden von Daten mit allen ausgewählten Zellen geschehen soll:</span><span class="sxs-lookup"><span data-stu-id="eb0e4-126">Specify what should happen to all the selected cells when an error or truncation occurs:</span></span>  
  
-   <span data-ttu-id="eb0e4-127">Den Fehler ignorieren.</span><span class="sxs-lookup"><span data-stu-id="eb0e4-127">Ignore the failure.</span></span>  
  
-   <span data-ttu-id="eb0e4-128">Die Zeile umleiten.</span><span class="sxs-lookup"><span data-stu-id="eb0e4-128">Redirect the row.</span></span>  
  
-   <span data-ttu-id="eb0e4-129">Die Komponente mit einem Fehler abbrechen.</span><span class="sxs-lookup"><span data-stu-id="eb0e4-129">Fail the component.</span></span>  
  
 <span data-ttu-id="eb0e4-130">**Anwenden**</span><span class="sxs-lookup"><span data-stu-id="eb0e4-130">**Apply**</span></span>  
 <span data-ttu-id="eb0e4-131">Wendet die Fehlerbehandlungsoption auf die ausgewählten Zellen an.</span><span class="sxs-lookup"><span data-stu-id="eb0e4-131">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb0e4-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb0e4-132">See Also</span></span>  
 [<span data-ttu-id="eb0e4-133">Fehler- und Meldungsreferenz von Integration Services</span><span class="sxs-lookup"><span data-stu-id="eb0e4-133">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
