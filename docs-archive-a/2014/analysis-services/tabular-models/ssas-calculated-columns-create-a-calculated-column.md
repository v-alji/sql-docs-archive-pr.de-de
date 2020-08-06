---
title: Erstellen einer berechneten Spalte (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.as.daxref.CreataCalculatedColumn.f1
ms.assetid: 59440510-2d76-41dc-9b55-edc15259f9da
author: minewiskan
ms.author: owend
ms.openlocfilehash: cdb56ffb2b42aa8225b7eff76b11315ea511fd81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694714"
---
# <a name="create-a-calculated-column-ssas-tabular"></a><span data-ttu-id="3c328-102">Erstellen einer berechneten Spalte (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="3c328-102">Create a Calculated Column (SSAS Tabular)</span></span>
  <span data-ttu-id="3c328-103">Mithilfe berechneter Spalten können Sie dem Modell neue Daten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3c328-103">Calculated columns allow you to add new data to your model.</span></span> <span data-ttu-id="3c328-104">Anstatt Werte in die Spalte einfügen oder importieren zu müssen, erstellen Sie eine DAX-Formel, die die Zeilen Ebenen Werte der Spalte definiert.</span><span class="sxs-lookup"><span data-stu-id="3c328-104">Instead of pasting or importing values into the column, you create a DAX formula that defines the column's row level values.</span></span> <span data-ttu-id="3c328-105">Die Werte in den einzelnen Zeilen einer berechneten Spalte werden berechnet und aufgefüllt, wenn Sie eine gültige Formel erstellen und die EINGABETASTE drücken.</span><span class="sxs-lookup"><span data-stu-id="3c328-105">The values in each row of a calculated column are calculated and populated when you create a valid formula and then click ENTER.</span></span> <span data-ttu-id="3c328-106">Die berechnete Spalte kann anschließend wie jeder andere Datenspalte einer Berichterstellungs- oder Analyseanwendung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="3c328-106">The calculated column can then be added to a reporting or analysis application just as would any other column of data.</span></span> <span data-ttu-id="3c328-107">In diesem Thema wird beschrieben, wie eine neue berechnete Spalte mithilfe der DAX-Bearbeitungsleiste im Modell-Designer erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="3c328-107">This topic describes how to create a new calculated column by using the DAX formula bar in the model designer.</span></span>  
  
#### <a name="to-create-a-new-calculated-column"></a><span data-ttu-id="3c328-108">So erstellen Sie eine neue berechnete Spalte</span><span class="sxs-lookup"><span data-stu-id="3c328-108">To create a new calculated column</span></span>  
  
1.  <span data-ttu-id="3c328-109">Wählen Sie im Modell-Designer in der Datensicht die Tabelle aus, der Sie eine berechnete Spalte hinzufügen möchten, und klicken Sie dann auf das Menü **Spalte** und auf **Spalte hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3c328-109">In the model designer, in Data View, select the table to which you want to add a calculated column, then click the **Column** menu, and then click **Add Column**.</span></span>  
  
     <span data-ttu-id="3c328-110">In der leeren Spalte am äußersten rechten Rand wird**Spalte hinzufügen** hervorgehoben, und der Cursor wird in die Bearbeitungsleiste verschoben.</span><span class="sxs-lookup"><span data-stu-id="3c328-110">**Add Column** is highlighted over the empty rightmost column, and the cursor moves to the formula bar.</span></span>  
  
     <span data-ttu-id="3c328-111">Klicken Sie mit der rechten Maustaste auf eine vorhandene Spalte, und klicken Sie dann auf **Spalte einfügen**, um zwischen zwei vorhandenen Spalten eine neue Spalte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3c328-111">To create a new column between two existing columns, right-click an existing column, and then click **Insert Column**.</span></span>  
  
2.  <span data-ttu-id="3c328-112">Führen Sie in der Bearbeitungsleiste einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="3c328-112">In the formula bar, do one of the following:</span></span>  
  
    -   <span data-ttu-id="3c328-113">Geben Sie ein Gleichheitszeichen gefolgt von einer Formel ein.</span><span class="sxs-lookup"><span data-stu-id="3c328-113">Type an equal sign followed by a formula.</span></span>  
  
    -   <span data-ttu-id="3c328-114">Geben Sie ein Gleichheitszeichen gefolgt von einer DAX-Funktion, den Argumenten und Parametern ein, die von der Funktion benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="3c328-114">Type an equal sign, followed by a DAX function, followed by arguments and parameters as required by the function.</span></span>  
  
    -   <span data-ttu-id="3c328-115">Klicken Sie auf die Funktionsschaltfläche (**fx**), und wählen Sie dann im Dialogfeld **Funktion einfügen** eine Kategorie und eine Funktion aus. Klicken Sie abschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3c328-115">Click the function button (**fx**), then in the **Insert Function** dialog box, select a category and function, and then click **OK**.</span></span> <span data-ttu-id="3c328-116">Geben Sie in der Bearbeitungsleiste die übrigen Argumente und Parameter ein, die von der Funktion benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="3c328-116">In the formula bar, type the remaining arguments and parameters as required by the function.</span></span>  
  
3.  <span data-ttu-id="3c328-117">Drücken Sie die EINGABETASTE, um die Formel zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="3c328-117">Press ENTER to accept the formula.</span></span>  
  
     <span data-ttu-id="3c328-118">Die gesamte Spalte wird mit der Formel aufgefüllt, d. h., für jede Zeile wird ein Wert berechnet.</span><span class="sxs-lookup"><span data-stu-id="3c328-118">The entire column is populated with the formula, and a value is calculated for each row.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="3c328-119">Sie können AutoVervollständigen für DAX-Formeln auch mitten in einer vorhandenen Formel mit geschachtelten Funktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="3c328-119">You can use DAX Formula AutoComplete in the middle of an existing formula with nested functions.</span></span> <span data-ttu-id="3c328-120">Ausgehend vom Text unmittelbar vor der Einfügemarke werden Werte in der Dropdownliste angezeigt. Der Text nach der Einfügemarke bleibt unverändert.</span><span class="sxs-lookup"><span data-stu-id="3c328-120">The text immediately before the insertion point is used to display values in the drop-down list, and all of the text after the insertion point remains unchanged.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c328-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3c328-121">See Also</span></span>  
 <span data-ttu-id="3c328-122">[Berechnete Spalten &#40;tabellarischen SSAS-&#41;](ssas-calculated-columns.md) </span><span class="sxs-lookup"><span data-stu-id="3c328-122">[Calculated Columns &#40;SSAS Tabular&#41;](ssas-calculated-columns.md) </span></span>  
 [<span data-ttu-id="3c328-123">Measures &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="3c328-123">Measures &#40;SSAS Tabular&#41;</span></span>](measures-ssas-tabular.md)  
  
  
