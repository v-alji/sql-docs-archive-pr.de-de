---
title: Festlegen des Gebietsschemas für einen Bericht oder ein Textfeld (Reporting Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- locales [Reporting Services]
ms.assetid: df115b01-184b-47f0-b5ec-0ad965ff9bee
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bb2b0cbd6e4216138520834216358ee455729386
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609639"
---
# <a name="set-the-locale-for-a-report-or-text-box-reporting-services"></a><span data-ttu-id="097b8-102">Festlegen des Gebietsschemas für einen Bericht oder ein Textfeld (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="097b8-102">Set the Locale for a Report or Text Box (Reporting Services)</span></span>
  <span data-ttu-id="097b8-103">Die **Language** -Eigenschaft eines Berichts oder eines Textfelds enthält das Gebietsschema, das die Standardformate zur Anzeige von Berichtsdaten festlegt, die je nach Land unterschiedlich sind, z. B. bei Datums-, Währungs- oder Zahlwerten.</span><span class="sxs-lookup"><span data-stu-id="097b8-103">The **Language** property on a report or a text box contains the locale setting, which determines the default formats for displaying report data that differ by language and region, for example, date, currency, or number values.</span></span> <span data-ttu-id="097b8-104">Die **Language** -Eigenschaft eines Textfelds hat Vorrang vor der **Language** -Eigenschaft des Berichts.</span><span class="sxs-lookup"><span data-stu-id="097b8-104">The **Language** property on a text box overrides the **Language** property on the report.</span></span> <span data-ttu-id="097b8-105">Wenn für **Language**kein Wert angegeben wird, verwendet Reporting Services das Gebietsschema des Betriebssystems auf dem Berichtsserver für veröffentlichte Berichte oder auf dem Computer zur Berichterstellung für die Berichtsvorschau.</span><span class="sxs-lookup"><span data-stu-id="097b8-105">If no value is specified for **Language**, Reporting Services uses the locale of the operating system on the report server for published reports or of the report authoring computer for report preview.</span></span>  
  
 <span data-ttu-id="097b8-106">Bei HTML-Berichten können Sie den Standardwert der **Language** -Eigenschaft überschreiben und die über den HTTP-Header des Browser-Clients angegebene Sprache verwenden, indem Sie das eingebettete Feld „User!Language“ in einem Ausdruck für die **Language** -Eigenschaft eines Berichts bzw. eines Textfelds verwenden.</span><span class="sxs-lookup"><span data-stu-id="097b8-106">For HTML reports, you can override the default **Language** value and use the language specified by the HTTP header of the browser client by using the built-in field User!Language in an expression for the **Language** property of a report or a text box.</span></span>  
  
 <span data-ttu-id="097b8-107">Außerdem können Sie die **Language** -Eigenschaft für einen Bericht in einer URL angeben.</span><span class="sxs-lookup"><span data-stu-id="097b8-107">You can also specify the **Language** property for a report in a URL.</span></span> <span data-ttu-id="097b8-108">Weitere Informationen finden Sie unter [Festlegen der Sprache für Berichtsparameter in einer URL](../set-the-language-for-report-parameters-in-a-url.md).</span><span class="sxs-lookup"><span data-stu-id="097b8-108">For more information, see [Set the Language for Report Parameters in a URL](../set-the-language-for-report-parameters-in-a-url.md).</span></span>  
  
### <a name="to-set-the-locale-for-a-report"></a><span data-ttu-id="097b8-109">So legen Sie das Gebietsschema für einen Bericht fest</span><span class="sxs-lookup"><span data-stu-id="097b8-109">To set the locale for a report</span></span>  
  
1.  <span data-ttu-id="097b8-110">Klicken Sie in der Entwurfssicht auf eine Stelle außerhalb der Berichts-Entwurfsoberfläche, um den Bericht auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="097b8-110">In Design view, click outside the report design surface to select the report.</span></span>  
  
2.  <span data-ttu-id="097b8-111">Geben Sie im Eigenschaftenbereich für die **Language** -Eigenschaft die Sprache ein, die Sie für den Bericht verwenden möchten, oder wählen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="097b8-111">In the Properties pane, for the **Language** property, type or select the language that you want to use for the report.</span></span>  
  
### <a name="to-set-the-locale-for-a-text-box"></a><span data-ttu-id="097b8-112">So legen Sie das Gebietsschema für ein Textfeld fest</span><span class="sxs-lookup"><span data-stu-id="097b8-112">To set the locale for a text box</span></span>  
  
1.  <span data-ttu-id="097b8-113">Wählen Sie in der Entwurfssicht das Textfeld aus, für das die Gebietsschemaeinstellungen übernommen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="097b8-113">In Design view, select the text box to which you want to apply the locale settings.</span></span>  
  
2.  <span data-ttu-id="097b8-114">Führen Sie im Eigenschaftenbereich folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="097b8-114">In the Properties pane, do the following:</span></span>  
  
    -   <span data-ttu-id="097b8-115">Geben Sie für die **Calendar** -Eigenschaft den Kalender ein, der für Datumsangaben verwendet werden soll, oder wählen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="097b8-115">For the **Calendar** property, type or select the calendar that you want to use for dates.</span></span>  
  
    -   <span data-ttu-id="097b8-116">Geben Sie für die **Direction** -Eigenschaft die Schreibrichtung für den Text ein, oder wählen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="097b8-116">For the **Direction** property, type or select the direction in which the text is written.</span></span>  
  
    -   <span data-ttu-id="097b8-117">Geben Sie für die **Language** -Eigenschaft die Sprache ein, die für das Textfeld verwendet werden soll, oder wählen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="097b8-117">For the **Language** property, type or select the language that you want to use for the text box.</span></span> <span data-ttu-id="097b8-118">Dieser Wert überschreibt die **Language** -Eigenschaft des Berichts.</span><span class="sxs-lookup"><span data-stu-id="097b8-118">This value overrides the **Language** property for the Report.</span></span>  
  
    -   <span data-ttu-id="097b8-119">Geben Sie für die **NumeralLanguage** -Eigenschaft das Format für Zahlen im Textfeld ein, oder wählen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="097b8-119">For the **NumeralLanguage** property, type or select the format to use for numbers in the text box.</span></span>  
  
    -   <span data-ttu-id="097b8-120">Geben Sie für die **NumeralVariant** -Eigenschaft die zu verwendende Variante für das Zahlenformat im Textfeld ein, oder wählen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="097b8-120">For the **NumeralVariant** property, type or select the variant of the format to use for numbers in the text box.</span></span>  
  
    -   <span data-ttu-id="097b8-121">Wählen Sie für die **UnicodeBiDi** -Eigenschaft den bidirektionalen Einbettungsgrad aus, der für das Textfeld verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="097b8-121">For the **UnicodeBiDi** property, select the level of bidirectional embedding to use in the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="097b8-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="097b8-122">See Also</span></span>  
 [<span data-ttu-id="097b8-123">Ausdrucksverwendungen in Berichten &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="097b8-123">Expression Uses in Reports &#40;Report Builder and SSRS&#41;</span></span>](expression-uses-in-reports-report-builder-and-ssrs.md)  
  
  
