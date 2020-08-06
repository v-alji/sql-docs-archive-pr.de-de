---
title: Funktion einfügen (Dialog Feld) (SSAS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- SQL12.ASVS.BIDTOOLSET.INSERTFUNCTIONDB.F1
ms.assetid: c4b36d8f-2328-45f7-8bd4-cc0111571e25
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0d92dd34e671dc026215d79e7eaed88bebfac15f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618400"
---
# <a name="insert-function-dialog-box-ssas"></a><span data-ttu-id="023c5-102">Funktion einfügen (Dialogfeld) (SSAS)</span><span class="sxs-lookup"><span data-stu-id="023c5-102">Insert Function Dialog Box (SSAS)</span></span>
  <span data-ttu-id="023c5-103">Im Dialogfeld **Funktion einfügen** können Sie Funktionen aus einer Liste auswählen, die beim Erstellen von Formeln verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="023c5-103">The **Insert Function** dialog box enables you to choose from a list of functions that can be used when building formulas.</span></span> <span data-ttu-id="023c5-104">Um das Dialogfeld über den Modell-Designer zu öffnen, klicken Sie auf der Bearbeitungsleiste über jeder Tabelle auf die Funktionsschaltfläche (**fx**).</span><span class="sxs-lookup"><span data-stu-id="023c5-104">To access this dialog box from the model designer, in the formula bar above each table, click the function (**fx**) button.</span></span> <span data-ttu-id="023c5-105">Weitere Informationen zum Auswählen von Funktionen für die Verwendung in Formeln finden Sie in der DAX-Einführung und im Thema zum Erstellen eine Formel.</span><span class="sxs-lookup"><span data-stu-id="023c5-105">For more information about choosing functions to use in formulas, see DAX Introduction and Build a Formula.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="023c5-106">Element</span><span class="sxs-lookup"><span data-stu-id="023c5-106">Item</span></span>|<span data-ttu-id="023c5-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="023c5-107">Description</span></span>|  
|<span data-ttu-id="023c5-108">**Kategorie auswählen**</span><span class="sxs-lookup"><span data-stu-id="023c5-108">**Select a category**</span></span>|<span data-ttu-id="023c5-109">Wenn Sie eine ungefähre Vorstellung haben, welche Art Funktion Sie benötigen, wählen Sie eine Kategorie aus der Liste. Alternativ wählen Sie **Alle** aus, um eine alphabetische Funktionsliste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="023c5-109">If you have a general idea which kind of function you need, choose a category from the list; or select **All** to view an alphabetical list of functions.</span></span>|  
|<span data-ttu-id="023c5-110">**Auswählen einer Funktion**</span><span class="sxs-lookup"><span data-stu-id="023c5-110">**Select a function**</span></span>|<span data-ttu-id="023c5-111">Zeigt eine Liste der Funktionen in der ausgewählten Kategorie an.</span><span class="sxs-lookup"><span data-stu-id="023c5-111">Displays a list of the functions in the selected category.</span></span>|  
|<span data-ttu-id="023c5-112">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="023c5-112">**Description**</span></span>|<span data-ttu-id="023c5-113">Zeigt zusammen mit allen erforderlichen oder optionalen Argumenten, z. B. Spaltennamen und Ausdrücken, eine Beschreibung der Wirkungsweise der Funktion an.</span><span class="sxs-lookup"><span data-stu-id="023c5-113">Displays a description of what the function does, together with any required or optional arguments, such as column names and expressions.</span></span>|  
  
## <a name="function-categories"></a><span data-ttu-id="023c5-114">Funktionskategorien</span><span class="sxs-lookup"><span data-stu-id="023c5-114">Function Categories</span></span>  
 <span data-ttu-id="023c5-115">Data Analysis Expressions (DAX) stellt im Dialogfeld **Funktion einfügen** die folgenden Funktionskategorietypen bereit.</span><span class="sxs-lookup"><span data-stu-id="023c5-115">Data Analysis Expressions (DAX) provides the following types of function categories in the **Insert Functions** dialog box.</span></span>  
  
 <span data-ttu-id="023c5-116">All</span><span class="sxs-lookup"><span data-stu-id="023c5-116">All</span></span>  
  
 <span data-ttu-id="023c5-117">Datum & Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="023c5-117">Date & Time</span></span>  
  
 <span data-ttu-id="023c5-118">Filter</span><span class="sxs-lookup"><span data-stu-id="023c5-118">Filter</span></span>  
  
 <span data-ttu-id="023c5-119">Logisch</span><span class="sxs-lookup"><span data-stu-id="023c5-119">Logical</span></span>  
  
 <span data-ttu-id="023c5-120">Math. & Trigonom.</span><span class="sxs-lookup"><span data-stu-id="023c5-120">Math & Trig</span></span>  
  
 <span data-ttu-id="023c5-121">Statistisch</span><span class="sxs-lookup"><span data-stu-id="023c5-121">Statistical</span></span>  
  
 <span data-ttu-id="023c5-122">Text</span><span class="sxs-lookup"><span data-stu-id="023c5-122">Text</span></span>  
  
## <a name="measures-and-formulas"></a><span data-ttu-id="023c5-123">Measures und Formeln</span><span class="sxs-lookup"><span data-stu-id="023c5-123">Measures and Formulas</span></span>  
 <span data-ttu-id="023c5-124">Das Dialogfeld **Funktion einfügen** ist nur verfügbar, wenn Sie eine Formel erstellen.</span><span class="sxs-lookup"><span data-stu-id="023c5-124">The **Insert Function** dialog box is available only when you are building a formula.</span></span> <span data-ttu-id="023c5-125">Sie können Berechnungen entweder in einer berechneten Spalte oder in einer PivotTable bzw. einem PivotChart erstellen.</span><span class="sxs-lookup"><span data-stu-id="023c5-125">You can create calculations either in a calculated column, or in a PivotTable or PivotChart.</span></span> <span data-ttu-id="023c5-126">Formeln, die Sie ausdrücklich zur Verwendung in einer PivotTable erstellen, werden auch als *Measures*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="023c5-126">Formulas that you build expressly for use in a PivotTable are also called *measures*.</span></span> <span data-ttu-id="023c5-127">Weitere Informationen finden Sie unter [Erstellen einer berechneten Spalte &#40;SSAS – tabellarisch&#41;](tabular-models/ssas-calculated-columns-create-a-calculated-column.md) und [Erstellen und Verwalten von Measures &#40;SSAS – tabellarisch&#41;](tabular-models/measures-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="023c5-127">For more information, see [Create a Calculated Column &#40;SSAS Tabular&#41;](tabular-models/ssas-calculated-columns-create-a-calculated-column.md) and [Create and Manage Measures &#40;SSAS Tabular&#41;](tabular-models/measures-ssas-tabular.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="023c5-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="023c5-128">See Also</span></span>  
 [<span data-ttu-id="023c5-129">Berechnungen &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="023c5-129">Calculations &#40;SSAS Tabular&#41;</span></span>](tabular-models/calculations-ssas-tabular.md)  
  
  
