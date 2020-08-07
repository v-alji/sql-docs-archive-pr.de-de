---
title: Transformations-Editor für ausdrucksexextraktion (Registerkarte Erweitert) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.termextraction.advanced.f1
helpviewer_keywords:
- Term Extraction Transformation Editor
ms.assetid: 87118281-6e3c-499e-bac4-fa4c24bb12c6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f4be56f8ac2deeab49e43071a07894a466019287
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718469"
---
# <a name="term-extraction-transformation-editor-advanced-tab"></a><span data-ttu-id="bc377-102">Transformations-Editor für Ausdrucksextrahierung (Registerkarte Erweitert)</span><span class="sxs-lookup"><span data-stu-id="bc377-102">Term Extraction Transformation Editor (Advanced Tab)</span></span>
  <span data-ttu-id="bc377-103">Auf der Registerkarte **Erweitert** des Dialogfelds **Transformations-Editor für Ausdrucksextrahierung** können Sie Eigenschaften für die Extrahierung angeben, wie z. B. Häufigkeit, Länge und ob Wörter oder Ausdrücke extrahiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bc377-103">Use the **Advanced** tab of the **Term Extraction Transformation Editor** dialog box to specify properties for the extraction such as frequency, length, and whether to extract words or phrases.</span></span>  
  
 <span data-ttu-id="bc377-104">Weitere Informationen zur Transformation für Ausdrucksextrahierung finden Sie unter [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="bc377-104">To learn more about the Term Extraction transformation, see [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="bc377-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="bc377-105">Options</span></span>  
 <span data-ttu-id="bc377-106">**Nomen**</span><span class="sxs-lookup"><span data-stu-id="bc377-106">**Noun**</span></span>  
 <span data-ttu-id="bc377-107">Gibt an, dass durch die Transformation nur einzelne Nomen extrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="bc377-107">Specify that the transformation extracts individual nouns only.</span></span>  
  
 <span data-ttu-id="bc377-108">**Nominaler Ausdruck**</span><span class="sxs-lookup"><span data-stu-id="bc377-108">**Noun phrase**</span></span>  
 <span data-ttu-id="bc377-109">Gibt an, dass durch die Transformation nur nominale Ausdrücke extrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="bc377-109">Specify that the transformation extracts noun phrases only.</span></span>  
  
 <span data-ttu-id="bc377-110">**Nomen und nominaler Ausdruck**</span><span class="sxs-lookup"><span data-stu-id="bc377-110">**Noun and noun phrase**</span></span>  
 <span data-ttu-id="bc377-111">Gibt an, dass durch die Transformation sowohl Nomen als auch nominale Ausdrücke extrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="bc377-111">Specify that the transformation extracts both nouns and noun phrases.</span></span>  
  
 <span data-ttu-id="bc377-112">**Frequency**</span><span class="sxs-lookup"><span data-stu-id="bc377-112">**Frequency**</span></span>  
 <span data-ttu-id="bc377-113">Gibt an, dass es sich bei dem Ergebnis um die Häufigkeit des Begriffs handelt.</span><span class="sxs-lookup"><span data-stu-id="bc377-113">Specify that the score is the frequency of the term.</span></span>  
  
 <span data-ttu-id="bc377-114">**TFIDF**</span><span class="sxs-lookup"><span data-stu-id="bc377-114">**TFIDF**</span></span>  
 <span data-ttu-id="bc377-115">Gibt an, dass es sich bei dem Ergebnis um den TFIDF-Wert des Begriffs handelt.</span><span class="sxs-lookup"><span data-stu-id="bc377-115">Specify that the score is the TFIDF value of the term.</span></span> <span data-ttu-id="bc377-116">Das TFIDF-Ergebnis ist das Produkt von Ausdruckshäufigkeit und umgekehrter Dokumenthäufigkeit, definiert als: TFIDF des Ausdrucks T = (Häufigkeit von T) \* log((Anz. Zeilen in der Eingabe)/(Anz. Zeilen mit T))</span><span class="sxs-lookup"><span data-stu-id="bc377-116">The TFIDF score is the product of Term Frequency and Inverse Document Frequency, defined as: TFIDF of a Term T = (frequency of T) \* log( (#rows in Input) / (#rows having T) )</span></span>  
  
 <span data-ttu-id="bc377-117">**Schwellenwert für Häufigkeit**</span><span class="sxs-lookup"><span data-stu-id="bc377-117">**Frequency threshold**</span></span>  
 <span data-ttu-id="bc377-118">Gibt in Form eines Zahlenwertes an, wie oft ein Wort oder ein Ausdruck vorkommen muss, bevor die Extrahierung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="bc377-118">Specify the number of times a word or phrase must occur before extracting it.</span></span> <span data-ttu-id="bc377-119">Der Standardwert ist 2.</span><span class="sxs-lookup"><span data-stu-id="bc377-119">The default value is 2.</span></span>  
  
 <span data-ttu-id="bc377-120">**Maximale Ausdruckslänge**</span><span class="sxs-lookup"><span data-stu-id="bc377-120">**Maximum length of term**</span></span>  
 <span data-ttu-id="bc377-121">Gibt die maximale Länge des Ausdrucks in Worten an.</span><span class="sxs-lookup"><span data-stu-id="bc377-121">Specify the maximum length of a phrase in words.</span></span> <span data-ttu-id="bc377-122">Diese Option bezieht sich nur auf nominale Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="bc377-122">This option affects noun phrases only.</span></span> <span data-ttu-id="bc377-123">Der Standardwert ist 12.</span><span class="sxs-lookup"><span data-stu-id="bc377-123">The default value is 12.</span></span>  
  
 <span data-ttu-id="bc377-124">**Ausdrucksextrahierung mit Unterscheidung nach Groß-/Kleinschreibung verwenden**</span><span class="sxs-lookup"><span data-stu-id="bc377-124">**Use case-sensitive term extraction**</span></span>  
 <span data-ttu-id="bc377-125">Gibt an, ob bei der Extrahierung nach Groß-/Kleinschreibung unterschieden wird.</span><span class="sxs-lookup"><span data-stu-id="bc377-125">Specify whether to make the extraction case-sensitive.</span></span> <span data-ttu-id="bc377-126">Der Standardwert lautet `False`.</span><span class="sxs-lookup"><span data-stu-id="bc377-126">The default is `False`.</span></span>  
  
 <span data-ttu-id="bc377-127">**Konfigurieren der Fehlerausgabe**</span><span class="sxs-lookup"><span data-stu-id="bc377-127">**Configure Error Output**</span></span>  
 <span data-ttu-id="bc377-128">Geben Sie mit dem Dialogfeld [Fehlerausgabe konfigurieren](../../2014/integration-services/configure-error-output.md) die Fehlerbehandlung für Zeilen an, die Fehler verursachen.</span><span class="sxs-lookup"><span data-stu-id="bc377-128">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling for rows that cause errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc377-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bc377-129">See Also</span></span>  
 <span data-ttu-id="bc377-130">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="bc377-130">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="bc377-131">[Transformations-Editor für Ausdrucksextrahierung &#40;Registerkarten&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md) </span><span class="sxs-lookup"><span data-stu-id="bc377-131">[Term Extraction Transformation Editor &#40;Term Extraction Tab&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md) </span></span>  
 <span data-ttu-id="bc377-132">[Transformations-Editor für Ausdrucksextrahierung &#40;&#41;Register](../../2014/integration-services/term-extraction-transformation-editor-exclusion-tab.md) </span><span class="sxs-lookup"><span data-stu-id="bc377-132">[Term Extraction Transformation Editor &#40;Exclusion Tab&#41;](../../2014/integration-services/term-extraction-transformation-editor-exclusion-tab.md) </span></span>  
 [<span data-ttu-id="bc377-133">Transformation für Ausdruckssuche</span><span class="sxs-lookup"><span data-stu-id="bc377-133">Term Lookup Transformation</span></span>](data-flow/transformations/lookup-transformation.md)  
  
  
