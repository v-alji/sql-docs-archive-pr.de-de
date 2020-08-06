---
title: Verweise auf Berichts- und Gruppenvariablenauflistungen (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10404"
- sql12.rtp.rptdesigner.categorygroupproperties.variables.f1
- "10083"
- sql12.rtp.rptdesigner.seriesgroupproperties.variables.f1
- sql12.rtp.rptdesigner.reportproperties.variables.f1
- sql12.rtp.rptdesigner.groupproperties.variables.f1
- "10292"
- "10412"
ms.assetid: 4be5b463-3ce2-483d-a3c6-dae752cb543e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 41dd652bf39721b13801131a5ec268495edf9d29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695410"
---
# <a name="report-and-group-variables-collections-references-report-builder-and-ssrs"></a><span data-ttu-id="b43df-102">Verweise auf Berichts- und Gruppenvariablenauflistungen (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="b43df-102">Report and Group Variables Collections References (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b43df-103">Bei komplexen Berechnungen, die in Ausdrücken eines Berichts mehrfach verwendet werden, empfiehlt sich das Erstellen einer Variable.</span><span class="sxs-lookup"><span data-stu-id="b43df-103">When you have a complex calculation that is used more than once in expressions in a report, you might want to create a variable.</span></span> <span data-ttu-id="b43df-104">Sie können eine Berichtsvariable oder eine Gruppenvariable erstellen.</span><span class="sxs-lookup"><span data-stu-id="b43df-104">You can create a report variable or a group variable.</span></span> <span data-ttu-id="b43df-105">Variablennamen müssen im Bericht eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="b43df-105">Variable names must be unique in a report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="report-variables"></a><span data-ttu-id="b43df-106">Berichtsvariablen</span><span class="sxs-lookup"><span data-stu-id="b43df-106">Report Variables</span></span>  
 <span data-ttu-id="b43df-107">Verwenden Sie eine Berichtsvariable zur Aufnahme eines Werts für zeitabhängige Berechnungen, wie Währungskurse oder Zeitstempel, oder für eine komplexe Berechnung, auf die mehrere Male verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b43df-107">Use a report variable to hold a value for time-dependent calculations, such as currency rates or time stamps, or for a complex calculation that is referenced multiple times.</span></span> <span data-ttu-id="b43df-108">Standardmäßig wird eine Berichtsvariable einmal berechnet und kann in Ausdrücken im gesamten Bericht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b43df-108">By default, a report variable is calculated once and can be used in expressions throughout a report.</span></span> <span data-ttu-id="b43df-109">Berichtsvariablen sind standardmäßig schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="b43df-109">Report variables are read-only by default.</span></span> <span data-ttu-id="b43df-110">Sie können die Standardeinstellung ändern, um für eine Berichtsvariable den Lese-/Schreibzugriff zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b43df-110">You can change the default to enable a report variable as read-write.</span></span> <span data-ttu-id="b43df-111">Der Wert in einer Berichtsvariable wird in der gesamten Sitzung beibehalten, bis der Bericht erneut verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="b43df-111">The value in a report variable is preserved throughout a session, until the report is processed again.</span></span>  
  
 <span data-ttu-id="b43df-112">Um eine Berichtsvariable hinzuzufügen, öffnen Sie das Dialogfeld **Berichtseigenschaften** , klicken Sie auf **Variablen**, und geben Sie einen Namen und einen Wert an.</span><span class="sxs-lookup"><span data-stu-id="b43df-112">To add a report variable, open the **ReportProperties** dialog box, click **Variables**, and provide a name and a value.</span></span> <span data-ttu-id="b43df-113">Bei Namen ist die Groß-/Kleinschreibung zu beachten. Sie beginnen mit einem Buchstaben und enthalten keine Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="b43df-113">Names are case-sensitive strings that begin with a letter and have no spaces.</span></span> <span data-ttu-id="b43df-114">Ein Name darf Buchstaben, Zahlen oder Unterstriche (_) enthalten.</span><span class="sxs-lookup"><span data-stu-id="b43df-114">A name can include letters, numbers, or underscores (_).</span></span>  
  
 <span data-ttu-id="b43df-115">Um auf die Variable in einem Ausdruck zu verweisen, verwenden Sie die globale Auflistungssyntax, z. B. `=Variables!CustomTimeStamp.Value`.</span><span class="sxs-lookup"><span data-stu-id="b43df-115">To refer to the variable in an expression, use the global collection syntax, for example, `=Variables!CustomTimeStamp.Value`.</span></span> <span data-ttu-id="b43df-116">Auf der Entwurfsoberfläche wird der Wert in einem Textfeld als `<<Expr>>`angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b43df-116">On the design surface, the value appears in a text box as `<<Expr>>`.</span></span>  
  
 <span data-ttu-id="b43df-117">Es gibt folgende Möglichkeiten für die Verwendung von Berichtsvariablen:</span><span class="sxs-lookup"><span data-stu-id="b43df-117">You can use report variables in the following ways:</span></span>  
  
-   <span data-ttu-id="b43df-118">**Nur Lesezugriff** Legen Sie einmalig einen Wert fest, um eine Konstante für die Berichtssitzung zu erstellen, z.B. einen Zeitstempel.</span><span class="sxs-lookup"><span data-stu-id="b43df-118">**Read-only use** Set a value once to create a constant for the report session, for example, to create a time stamp.</span></span>  
  
     <span data-ttu-id="b43df-119">Da Ausdrücke in Textfeldern bedarfsgesteuert ausgewertet werden, wenn ein Benutzer durch einen Bericht blättert, können dynamische Werte (z.B. ein Ausdruck, der `Now()` einschließt, eine Funktion, die die Tageszeit zurückgibt) unterschiedliche Werte zurückgeben, wenn Sie vor und mit der Schaltfläche **Zurück** zurückblättern.</span><span class="sxs-lookup"><span data-stu-id="b43df-119">Because expressions in text boxes are evaluated on-demand as a user pages through a report, dynamic values (for example, an expression that includes the `Now()` function, which returns the time of day) can return different values if you page forward and backward by using the **Back** button.</span></span> <span data-ttu-id="b43df-120">Durch Festlegen des Werts einer Berichtsvariablen auf den Ausdruck `=Now()`und anschließendes Hinzufügen der Variablen zum Ausdruck wird gewährleistet, dass während der Berichtsverarbeitung die gleiche Variable verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b43df-120">By setting a the value of a report variable to the expression `=Now()`, and then adding the variable to your expression, you ensure the same value is used throughout report processing.</span></span>  
  
-   <span data-ttu-id="b43df-121">**Lese-/Schreibzugriff** Legen Sie einmalig einen Wert fest, und serialisieren Sie diesen innerhalb einer Berichtssitzung.</span><span class="sxs-lookup"><span data-stu-id="b43df-121">**Read-write use** Set a value once and serialize the value within a report session.</span></span> <span data-ttu-id="b43df-122">Die Lese-/Schreiboption für Variablen bietet eine bessere Alternative als die Verwendung einer statischen Variable im Codeblock der Berichtsdefinition.</span><span class="sxs-lookup"><span data-stu-id="b43df-122">The read-write option for variables provides a better alternative than using a static variable in the Code block in the report definition.</span></span>  
  
     <span data-ttu-id="b43df-123">Wenn **Sie die Option Schreib** geschützt für eine Variable deaktivieren, wird die beschreibbare-Eigenschaft für die Variable auf festgelegt `true` .</span><span class="sxs-lookup"><span data-stu-id="b43df-123">When you clear the **Read-Only** option for a variable, the Writable property for the variable is set to `true`.</span></span> <span data-ttu-id="b43df-124">Verwenden Sie die SetValue-Methode, z.B. `=Variables!MyVariable.SetValue("123")`, um den Wert mit einem Ausdruck zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b43df-124">To update the value from an expression, use the SetValue method, for example, `=Variables!MyVariable.SetValue("123")`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b43df-125">Sie können nicht steuern, wann der Berichtsprozessor eine Variable initialisiert oder einen Ausdruck auswertet, der eine Variable aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="b43df-125">You cannot control when the report processor initializes a variable or evaluates an expression that updates a variable.</span></span> <span data-ttu-id="b43df-126">Der Reihenfolge der Ausführung für die Variableninitialisierung ist nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="b43df-126">The order of execution for variable initialization is undefined.</span></span>  
  
 <span data-ttu-id="b43df-127">Weitere Informationen zu Sitzungen finden Sie unter [Previewing Reports in Report Builder](../report-builder/previewing-reports-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="b43df-127">For more information about sessions, see [Previewing Reports in Report Builder](../report-builder/previewing-reports-in-report-builder.md).</span></span>  
  
## <a name="group-variables"></a><span data-ttu-id="b43df-128">Gruppenvariablen</span><span class="sxs-lookup"><span data-stu-id="b43df-128">Group Variables</span></span>  
 <span data-ttu-id="b43df-129">Verwenden Sie eine Gruppenvariable, um einen komplexen Ausdruck im Bereich einer Gruppe einmal zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="b43df-129">Use a group variable to calculate a complex expression once in the scope of a group.</span></span> <span data-ttu-id="b43df-130">Eine Gruppenvariable ist nur im Bereich der Gruppe und der untergeordneten Gruppen gültig.</span><span class="sxs-lookup"><span data-stu-id="b43df-130">A group variable is valid only in the scope of the group and its child groups.</span></span>  
  
 <span data-ttu-id="b43df-131">Angenommen, ein Datenbereich zeigt Bestandsdaten für Posten an, die verschiedenen Steuerkategorien angehören, und Sie möchten für jede Kategorie einen anderen Steuersatz anwenden.</span><span class="sxs-lookup"><span data-stu-id="b43df-131">For example, suppose a data region displays inventory data for items that are in different tax categories and you want to apply different tax rates for each category.</span></span> <span data-ttu-id="b43df-132">In diesem Fall gruppieren Sie die Daten in Kategorien und definieren für die übergeordnete Gruppe eine *Tax* -Variable.</span><span class="sxs-lookup"><span data-stu-id="b43df-132">You would group the data on Category and define a *Tax* variable on the parent group.</span></span> <span data-ttu-id="b43df-133">Anschließend definieren Sie eine Gruppenvariable für *ItemTax* für jede Steuerkategorie und weisen jeder der Kategorieuntergruppen die richtige Gruppenvariable zu.</span><span class="sxs-lookup"><span data-stu-id="b43df-133">Then you would define a group variable for *ItemTax* for each tax category and assign each of the different Category subgroups to the correct group variable.</span></span> <span data-ttu-id="b43df-134">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b43df-134">For example:</span></span>  
  
-   <span data-ttu-id="b43df-135">Definieren Sie für die übergeordnete Gruppe auf Grundlage von `[Category]`die Variable *Tax* mit einem Wert `[Tax]`.</span><span class="sxs-lookup"><span data-stu-id="b43df-135">For the parent group based on `[Category]`, define the variable *Tax* with a value `[Tax]`.</span></span> <span data-ttu-id="b43df-136">Angenommen, die Kategoriewerte lauten Nahrungsmittel und Kleidung.</span><span class="sxs-lookup"><span data-stu-id="b43df-136">Assume the category values are Food and Clothing.</span></span>  
  
-   <span data-ttu-id="b43df-137">Definieren Sie für die untergeordnete Gruppe auf Grundlage von `[Subcategory]`die Variable *ItemsTax* als `=Variables!Tax.Value * Sum(Fields!Price.Value)`.</span><span class="sxs-lookup"><span data-stu-id="b43df-137">For the child group based on `[Subcategory]`, define the variable *ItemsTax* as `=Variables!Tax.Value * Sum(Fields!Price.Value)`.</span></span> <span data-ttu-id="b43df-138">Angenommen, die Unterkategoriewerte für die Kategorie Nahrungsmittel sind Getränke und Brot.</span><span class="sxs-lookup"><span data-stu-id="b43df-138">Assume the subcategory values for the category Food are Beverages and Bread.</span></span> <span data-ttu-id="b43df-139">Die Unterkategoriewerte für Kleidung lauten Hemden und Hüte.</span><span class="sxs-lookup"><span data-stu-id="b43df-139">Assume the subcategory values for Clothing are Shirts and Hats.</span></span>  
  
-   <span data-ttu-id="b43df-140">Fügen Sie für ein Textfeld in einer Zeile der untergeordneten Gruppe den Ausdruck `=Variables!ItemsTax.Value`hinzu.</span><span class="sxs-lookup"><span data-stu-id="b43df-140">For a text box in a row in the child group, add the expression `=Variables!ItemsTax.Value`.</span></span>  
  
     <span data-ttu-id="b43df-141">Das Textfeld zeigt die gesamte Steuer für Getränke und Brot unter Verwendung des Steuersatzes für Nahrungsmittel und für Hemden und Hüte unter Verwendung des Steuersatzes für Kleidung an.</span><span class="sxs-lookup"><span data-stu-id="b43df-141">The text box displays the total tax for Beverages and Bread using the Food tax and for Shirts and Hats using the Clothing tax.</span></span>  
  
 <span data-ttu-id="b43df-142">Um eine Gruppenvariable hinzuzufügen, öffnen Sie das Dialogfeld **Tablix-Gruppeneigenschaften** , klicken Sie auf **Variablen**, und geben Sie einen Namen und einen Wert an.</span><span class="sxs-lookup"><span data-stu-id="b43df-142">To add a group variable, open the **Tablix Group Properties** dialog box, click **Variables**, and provide a name and a value.</span></span> <span data-ttu-id="b43df-143">Die Gruppenvariable wird einmal pro eindeutigen Gruppenwert berechnet.</span><span class="sxs-lookup"><span data-stu-id="b43df-143">The group variable is calculated once per unique group value.</span></span>  
  
 <span data-ttu-id="b43df-144">Um auf die Variable in einem Ausdruck zu verweisen, verwenden Sie die globale Auflistungssyntax, z. B. `=Variables!GroupDescription.Value`.</span><span class="sxs-lookup"><span data-stu-id="b43df-144">To refer to the variable in an expression, use the global collection syntax, for example, `=Variables!GroupDescription.Value`.</span></span> <span data-ttu-id="b43df-145">Auf der Entwurfsoberfläche wird der Wert in einem Textfeld als `<<Expr>>`angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b43df-145">On the design surface, the value appears in a text box as `<<Expr>>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b43df-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b43df-146">See Also</span></span>  
 <span data-ttu-id="b43df-147">[Filtern, Gruppieren und Sortieren von Daten &#40;Berichts-Generator und SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b43df-147">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b43df-148">[Integrierte Sammlungen in Ausdrücken &#40;Berichts-Generator und SSRS&#41;](built-in-collections-in-expressions-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="b43df-148">[Built-in Collections in Expressions &#40;Report Builder and SSRS&#41;](built-in-collections-in-expressions-report-builder.md) </span></span>  
 [<span data-ttu-id="b43df-149">Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b43df-149">Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](expression-examples-report-builder-and-ssrs.md)  
  
  