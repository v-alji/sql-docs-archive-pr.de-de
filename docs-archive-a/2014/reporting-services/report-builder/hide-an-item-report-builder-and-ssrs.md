---
title: Ausblenden eines Elements (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.shared.visibility.f1
- "10503"
ms.assetid: 9d78f8de-959b-456f-8947-687fa6e2ba91
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 56e834204698369687528c622cf6167a492766f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615836"
---
# <a name="hide-an-item-report-builder-and-ssrs"></a><span data-ttu-id="1e3f5-102">Ausblenden eines Elements (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="1e3f5-102">Hide an Item (Report Builder and SSRS)</span></span>
  <span data-ttu-id="1e3f5-103">Legen Sie die Sichtbarkeit eines Berichtselements fest, wenn Sie ein Element basierend auf einem Berichtsparameter oder einem anderen von Ihnen angegebenen Ausdruck bedingt ausblenden möchten.</span><span class="sxs-lookup"><span data-stu-id="1e3f5-103">Set the visibility of a report item when you want to conditionally hide an item based on a report parameter or some other expression that you specify.</span></span>

 <span data-ttu-id="1e3f5-104">Sie können auch einen Bericht entwerfen, der dem Benutzer ermöglicht, die Sichtbarkeit von Berichtselementen durch Klicken auf Textfelder im Bericht ein- und auszublenden. Beispielsweise kann dies bei einem Drilldownbericht hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="1e3f5-104">You can also design a report to allow the user to toggle the visibility of report items based on clicking text boxes in the report, for example, for a drilldown report.</span></span> <span data-ttu-id="1e3f5-105">Weitere Informationen finden Sie unter [Hinzufügen einer Erweiterungs- oder Reduzieraktion zu einem Element &#40;Berichts-Generator und SSRS&#41;](../report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1e3f5-105">For more information, see [Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](../report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md).</span></span>

 <span data-ttu-id="1e3f5-106">In den folgenden Verfahren wird beschrieben, wie ein Berichtselement in einem gerenderten Bericht basierend auf einer Konstante oder einem Ausdruck ein- oder ausgeblendet wird.</span><span class="sxs-lookup"><span data-stu-id="1e3f5-106">The following procedures describe how to show or hide a report item in a rendered report based on a constant or an expression.</span></span>

> [!NOTE]
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]

### <a name="to-hide-a-report-item"></a><span data-ttu-id="1e3f5-107">So blenden Sie ein Berichtselement aus</span><span class="sxs-lookup"><span data-stu-id="1e3f5-107">To hide a report item</span></span>

1.  <span data-ttu-id="1e3f5-108">Klicken Sie in der Berichtsentwurfsansicht mit der rechten Maustaste auf das Berichtselement, und öffnen Sie die Seite **Eigenschaften** des Elements.</span><span class="sxs-lookup"><span data-stu-id="1e3f5-108">In report design view, right-click the report item and open its **Properties** page.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="1e3f5-109">Klicken Sie im Datenbereich, um eine ganze Tabelle oder Matrix auszuwählen. Klicken Sie mit der rechten Maustaste auf einen Zeilen-, Spalten- oder Eckziehpunkt, und klicken Sie anschließend auf **Tablix-Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="1e3f5-109">To select an entire table or matrix data region, click in the data region to select it, right-click a row, column, or corner handle, and then click **Tablix Properties**.</span></span>

2.  <span data-ttu-id="1e3f5-110">Klicken Sie auf **Transparenz.**</span><span class="sxs-lookup"><span data-stu-id="1e3f5-110">Click **Visibility.**</span></span>

3.  <span data-ttu-id="1e3f5-111">Geben Sie unter **Bei erstmaliger Ausführung des Berichts**an, ob das Element ausgeblendet werden soll, wenn der Bericht erstmals angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="1e3f5-111">In **When the report is initially run**, specify whether to hide the item when you first view the report:</span></span>

    -   <span data-ttu-id="1e3f5-112">Um das Element anzuzeigen, klicken Sie auf **Anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="1e3f5-112">To display the item, click **Show**.</span></span>

    -   <span data-ttu-id="1e3f5-113">Um das Element auszublenden, klicken Sie auf **Ausblenden**.</span><span class="sxs-lookup"><span data-stu-id="1e3f5-113">To hide the item, click **Hide**.</span></span>

    -   <span data-ttu-id="1e3f5-114">Klicken Sie auf **Je nach Ausdruck einblenden/ausblenden**, um einen Ausdruck anzugeben, der zur Laufzeit ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="1e3f5-114">To specify an expression that is evaluated at run-time, click **Show or hide based on an expression**.</span></span> <span data-ttu-id="1e3f5-115">Geben Sie den Ausdruck ein, oder klicken Sie auf die Ausdrucksschaltfläche (**fx**), um den Ausdruck im Dialogfeld **Ausdruck** zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1e3f5-115">Type the expression or click the expression (**fx**) button to create the expression in the **Expression** dialog box.</span></span>

        > [!NOTE]
        >  <span data-ttu-id="1e3f5-116">Wenn Sie einen Ausdruck für die Sichtbarkeit angeben, legen Sie die Hidden-Eigenschaft des Berichtselements wie im folgenden Bild dargestellt fest.</span><span class="sxs-lookup"><span data-stu-id="1e3f5-116">When you specify an expression for visibility, you are setting the Hidden property of the report item, as shown in the following image.</span></span> <span data-ttu-id="1e3f5-117">Der ausgewertete Ausdruck zeigt das Berichtselement an, wenn der Wert False lautet, und blendet das Berichtselement aus, wenn der Wert True lautet.</span><span class="sxs-lookup"><span data-stu-id="1e3f5-117">The evaluated expression shows the report item when the value is False, and hides the report item when the value is True.</span></span> 
        > <span data-ttu-id="1e3f5-118">![Properties_Visibility-Dialogfeld und Eigenschaft „Hidden“](../media/hiddenproperty-propertiesvisibility.png "Properties_Visibility-Dialogfeld und Eigenschaft „Hidden“")</span><span class="sxs-lookup"><span data-stu-id="1e3f5-118">![Properties_Visibility dialog and Hidden property](../media/hiddenproperty-propertiesvisibility.png "Properties_Visibility dialog and Hidden property")</span></span>

4.  <span data-ttu-id="1e3f5-119">Klicken Sie zweimal auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1e3f5-119">Click **OK** twice.</span></span>

### <a name="to-hide-static-rows-in-a-table-matrix-or-list"></a><span data-ttu-id="1e3f5-120">So blenden Sie statische Zeilen in einer Tabelle, Matrix oder Liste aus</span><span class="sxs-lookup"><span data-stu-id="1e3f5-120">To hide static rows in a table, matrix, or list</span></span>

1.  <span data-ttu-id="1e3f5-121">Klicken Sie in der Berichtsentwurfsansicht auf die Tabelle, Matrix oder Liste, um die Zeilen- und Spaltenziehpunkte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1e3f5-121">In report design view, click the table, matrix, or list to display the row and column handles.</span></span>

2.  <span data-ttu-id="1e3f5-122">Klicken Sie mit der rechten Maustaste auf den Zeilenziehpunkt, und klicken Sie anschließend auf **Sichtbarkeit anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="1e3f5-122">Right-click the row handle, and then click **Row Visibility**.</span></span> <span data-ttu-id="1e3f5-123">Das Dialogfeld **Sichtbarkeit anzeigen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1e3f5-123">The **Row Visibility** dialog box opens.</span></span>

3.  <span data-ttu-id="1e3f5-124">Um die Sichtbarkeit festzulegen, führen Sie die Schritte 3 und 4 der ersten Prozedur aus.</span><span class="sxs-lookup"><span data-stu-id="1e3f5-124">To set the visibility, follow steps 3 and 4 in the first procedure.</span></span>

### <a name="to-hide-static-columns-in-a-table-matrix-or-list"></a><span data-ttu-id="1e3f5-125">So blenden Sie statische Spalten in einer Tabelle, Matrix oder Liste aus</span><span class="sxs-lookup"><span data-stu-id="1e3f5-125">To hide static columns in a table, matrix, or list</span></span>

1.  <span data-ttu-id="1e3f5-126">Wählen Sie in der Entwurfsansicht die Tabelle, Matrix oder Liste, um die Zeilen- und Spaltenziehpunkte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1e3f5-126">In Design view, select the table, matrix, or list to display the row and column handles.</span></span>

2.  <span data-ttu-id="1e3f5-127">Klicken Sie mit der rechten Maustaste auf den Spaltenziehpunkt, und klicken Sie anschließend auf **Spaltensichtbarkeit**.</span><span class="sxs-lookup"><span data-stu-id="1e3f5-127">Right-click the column handle, and then click **Column Visibility**.</span></span>

3.  <span data-ttu-id="1e3f5-128">Führen Sie im Dialogfeld **Spaltensichtbarkeit** die Schritte 3 und 4 der ersten Prozedur aus.</span><span class="sxs-lookup"><span data-stu-id="1e3f5-128">In the **Column Visibility** dialog box, follow steps 3 and 4 in the first procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e3f5-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1e3f5-129">See Also</span></span>
 <span data-ttu-id="1e3f5-130">[Drilldown-Aktion &#40;Berichts-Generator und SSRS&#41;](../report-design/drilldown-action-report-builder-and-ssrs.md) [Hinzufügen einer Erweiterungs-oder Reduzier Aktion zu einem Element &#40;Berichts-Generator und SSRS&#41;](../report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) [Ausdrucks Beispiele &#40;Berichts-Generator und SSRS&#41;](../report-design/expression-examples-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="1e3f5-130">[Drilldown Action &#40;Report Builder and SSRS&#41;](../report-design/drilldown-action-report-builder-and-ssrs.md) [Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](../report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md) [Expression Examples &#40;Report Builder and SSRS&#41;](../report-design/expression-examples-report-builder-and-ssrs.md)</span></span>


