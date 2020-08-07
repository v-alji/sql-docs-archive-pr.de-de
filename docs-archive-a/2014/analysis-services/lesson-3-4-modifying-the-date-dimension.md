---
title: Ändern der Date-Dimension | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 4689d780-4bf6-4cf8-8fde-eb3f15dd668a
author: minewiskan
ms.author: owend
ms.openlocfilehash: b4978e9fe3acd93ddfdca707d2c2353bf171ba12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619435"
---
# <a name="modifying-the-date-dimension"></a><span data-ttu-id="3d07b-102">Ändern der Date-Dimension</span><span class="sxs-lookup"><span data-stu-id="3d07b-102">Modifying the Date Dimension</span></span>
  <span data-ttu-id="3d07b-103">In den Aufgaben dieses Themas erstellen Sie eine benutzerdefinierte Hierarchie und ändern die Elementnamen, die für die Attribute Date, Month, Calendar Quarter und Calendar Semester angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3d07b-103">In the tasks in this topic, you create a user-defined hierarchy and change the member names that are displayed for the Date, Month, Calendar Quarter, and Calendar Semester attributes.</span></span> <span data-ttu-id="3d07b-104">Außerdem definieren Sie zusammengesetzte Schlüssel für Attribute, steuern die Sortierreihenfolge von Dimensionselementen und definieren Attributbeziehungen.</span><span class="sxs-lookup"><span data-stu-id="3d07b-104">You also define composite keys for attributes, control the sort order of dimension members, and define attribute relationships.</span></span>  
  
## <a name="adding-a-named-calculation"></a><span data-ttu-id="3d07b-105">Hinzufügen einer benannten Berechnung</span><span class="sxs-lookup"><span data-stu-id="3d07b-105">Adding a Named Calculation</span></span>  
 <span data-ttu-id="3d07b-106">Sie können eine benannte Berechnung, bei der es sich um einen SQL-Ausdruck handelt, der als eine berechnete Spalte dargestellt wird, zu einer Tabelle in einer Datenquellensicht hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3d07b-106">You can add a named calculation, which is a SQL expression that is represented as a calculated column, to a table in a data source view.</span></span> <span data-ttu-id="3d07b-107">Der Ausdruck wird als Spalte in der Tabelle angezeigt und verhält sich auch so.</span><span class="sxs-lookup"><span data-stu-id="3d07b-107">The expression appears and behaves as a column in the table.</span></span> <span data-ttu-id="3d07b-108">Mithilfe von benannten Berechnungen können Sie das relationale Schema vorhandener Tabellen in einer Datenquellensicht erweitern, ohne die Tabelle in der zugrunde liegenden Datenquelle zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3d07b-108">Named calculations enable you to extend the relational schema of existing tables in a data source view without modifying the table in the underlying data source.</span></span> <span data-ttu-id="3d07b-109">Weitere Informationen finden Sie unter [Definieren von benannten Berechnungen in einer Datenquellensicht &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)</span><span class="sxs-lookup"><span data-stu-id="3d07b-109">For more information, see [Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)</span></span>  
  
#### <a name="to-add-a-named-calculation"></a><span data-ttu-id="3d07b-110">So fügen Sie eine benannte Berechnung hinzu</span><span class="sxs-lookup"><span data-stu-id="3d07b-110">To add a named calculation</span></span>  
  
1.  <span data-ttu-id="3d07b-111">Um die Datenquellensicht **Adventure Works DW 2012** zu öffnen, doppelklicken Sie im Projektmappen-Explorer im Ordner **Datenquellensichten** auf diese Sicht.</span><span class="sxs-lookup"><span data-stu-id="3d07b-111">To open the **Adventure Works DW 2012** data source view, double-click it in the **Data Source Views** folder in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="3d07b-112">Klicken Sie im unteren Bereich des **Tabellen** Bereichs mit der rechten Maustaste auf `Date` , und klicken Sie dann auf **neue benannte Berechnung**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-112">Near the bottom of the **Tables** pane, right-click `Date`, and then click **New Named Calculation**.</span></span>  
  
3.  <span data-ttu-id="3d07b-113">Geben Sie im Dialogfeld **benannte Berechnung erstellen** `SimpleDate` im Feld **Spaltenname** ein, und geben Sie dann die folgende `DATENAME` Anweisung in das Feld **Ausdruck** ein (Sie können die Anweisung auch kopieren und Einfügen):</span><span class="sxs-lookup"><span data-stu-id="3d07b-113">In the **Create Named Calculation** dialog box, type `SimpleDate` in the **Column name** box, and then type or copy and paste the following `DATENAME` statement in the **Expression** box:</span></span>  
  
    ```  
    DATENAME(mm, FullDateAlternateKey) + ' ' +  
    DATENAME(dd, FullDateAlternateKey) + ', ' +  
    DATENAME(yy, FullDateAlternateKey)  
    ```  
  
     <span data-ttu-id="3d07b-114">Mithilfe dieser `DATENAME`-Anweisung werden Jahr-, Monats- und Tageswerte aus der FullDateAlternateKey-Spalte extrahiert.</span><span class="sxs-lookup"><span data-stu-id="3d07b-114">The `DATENAME` statement extracts the year, month, and day values from the FullDateAlternateKey column.</span></span> <span data-ttu-id="3d07b-115">Sie verwenden diese neue Spalte als angezeigten Namen für das FullDateAlternateKey-Attribut.</span><span class="sxs-lookup"><span data-stu-id="3d07b-115">You will use this new column as the displayed name for the FullDateAlternateKey attribute.</span></span>  
  
4.  <span data-ttu-id="3d07b-116">Klicken Sie auf **OK**, und erweitern Sie dann `Date` im Bereich **Tabellen** .</span><span class="sxs-lookup"><span data-stu-id="3d07b-116">Click **OK**, and then expand `Date` in the **Tables** pane.</span></span>  
  
     <span data-ttu-id="3d07b-117">Die `SimpleDate` benannte Berechnung wird in der Liste der Spalten in der Date-Tabelle mit einem Symbol angezeigt, das angibt, dass es sich um eine benannte Berechnung handelt.</span><span class="sxs-lookup"><span data-stu-id="3d07b-117">The `SimpleDate` named calculation appears in the list of columns in the Date table, with an icon that indicates that it is a named calculation.</span></span>  
  
5.  <span data-ttu-id="3d07b-118">Klicken Sie im Menü **File** (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="3d07b-118">On the **File** menu, click **Save All**.</span></span>  
  
6.  <span data-ttu-id="3d07b-119">Klicken Sie im Bereich **Tabellen** mit der rechten Maustaste auf `Date` , und klicken Sie dann auf **Daten durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-119">In the **Tables** pane, right-click `Date`, and then click **Explore Data**.</span></span>  
  
7.  <span data-ttu-id="3d07b-120">Scrollen Sie nach rechts, um die letzte Spalte in der Sicht **Explore Date Table** zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="3d07b-120">Scroll to the right to review the last column in the **Explore Date Table** view.</span></span>  
  
     <span data-ttu-id="3d07b-121">Beachten Sie, dass die `SimpleDate` Spalte in der Datenquellen Sicht angezeigt wird, wobei Daten aus verschiedenen Spalten aus der zugrunde liegenden Datenquelle ordnungsgemäß verkettet werden, ohne die ursprüngliche Datenquelle zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3d07b-121">Notice that the `SimpleDate` column appears in the data source view, correctly concatenating data from several columns from the underlying data source, without modifying the original data source.</span></span>  
  
8.  <span data-ttu-id="3d07b-122">Schließen Sie die Sicht **Explore Date Table** .</span><span class="sxs-lookup"><span data-stu-id="3d07b-122">Close the **Explore Date Table** view.</span></span>  
  
## <a name="using-the-named-calculation-for-member-names"></a><span data-ttu-id="3d07b-123">Verwenden der benannten Berechnung für Elementnamen</span><span class="sxs-lookup"><span data-stu-id="3d07b-123">Using the Named Calculation for Member Names</span></span>  
 <span data-ttu-id="3d07b-124">Nachdem Sie eine benannte Berechnung in der Datenquellensicht erstellt haben, können Sie diese als Eigenschaft eines Attributs verwenden.</span><span class="sxs-lookup"><span data-stu-id="3d07b-124">After you create a named calculation in the data source view, you can use the named calculation as a property of an attribute.</span></span>  
  
#### <a name="to-use-the-named-calculation-for-member-names"></a><span data-ttu-id="3d07b-125">So verwenden Sie die benannte Berechnung für Elementnamen</span><span class="sxs-lookup"><span data-stu-id="3d07b-125">To use the named calculation for member names</span></span>  
  
1.  <span data-ttu-id="3d07b-126">Öffnen Sie den **Dimensions-Designer** für die Date-Dimension in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3d07b-126">Open **Dimension Designer** for the Date dimension in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="3d07b-127">Doppelklicken Sie hierzu auf die `Date` Dimension im **Dimensionen** -Knoten **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-127">To do this, double-click the `Date` dimension in the **Dimensions** node of **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="3d07b-128">Klicken Sie im Bereich **Attribute** der Registerkarte **Dimensionsstruktur** auf das **Date Key** -Attribut.</span><span class="sxs-lookup"><span data-stu-id="3d07b-128">In the **Attributes** pane of the **Dimension Structure** tab, click the **Date Key** attribute.</span></span>  
  
3.  <span data-ttu-id="3d07b-129">Wenn das Eigenschaftenfenster nicht geöffnet ist, öffnen Sie es, und klicken Sie in der Titelleiste auf die Schaltfläche **Automatisch im Hintergrund** , damit es geöffnet bleibt.</span><span class="sxs-lookup"><span data-stu-id="3d07b-129">If the Properties window is not open, open the Properties window, and then click the **Auto Hide** button on the title bar so that it stays open.</span></span>  
  
4.  <span data-ttu-id="3d07b-130">Klicken Sie im unteren Bereich des Fensters auf das Eigenschafts Feld **namecolumzun** , und klicken Sie dann auf die Schaltfläche mit den Auslassungs Punkten (**...**), um das Dialogfeld **Namensspalte** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3d07b-130">Click the **NameColumn** property field near the bottom of the window, and then click the ellipsis browse (**...**) button to open the **Name Column** dialog box.</span></span>  
  
5.  <span data-ttu-id="3d07b-131">Wählen Sie `SimpleDate` unten in der Liste **Quell Spalte** die Option aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-131">Select `SimpleDate` at the bottom of the **Source column** list, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="3d07b-132">Klicken Sie im Menü **File** (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="3d07b-132">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="creating-a-hierarchy"></a><span data-ttu-id="3d07b-133">Erstellen einer Hierarchie</span><span class="sxs-lookup"><span data-stu-id="3d07b-133">Creating a Hierarchy</span></span>  
 <span data-ttu-id="3d07b-134">Sie können eine neue Hierarchie erstellen, indem Sie ein Attribut aus dem Bereich **Attribute** in den Bereich **Hierarchien** ziehen.</span><span class="sxs-lookup"><span data-stu-id="3d07b-134">You can create a new hierarchy by dragging an attribute from the **Attributes** pane to the **Hierarchies** pane.</span></span>  
  
#### <a name="to-create-a-hierarchy"></a><span data-ttu-id="3d07b-135">So erstellen Sie eine Hierarchie</span><span class="sxs-lookup"><span data-stu-id="3d07b-135">To create a hierarchy</span></span>  
  
1.  <span data-ttu-id="3d07b-136">Ziehen Sie im Dimensions-Designer für die Dimension auf der Registerkarte **Dimensions Struktur** `Date` das **Calendar Year** -Attribut aus dem Bereich **Attribute** in den Bereich **Hierarchien** .</span><span class="sxs-lookup"><span data-stu-id="3d07b-136">In **Dimension Structure** tab of the Dimension Designer for the `Date` dimension, drag the **Calendar Year** attribute from the **Attributes** pane into the **Hierarchies** pane.</span></span>  
  
2.  <span data-ttu-id="3d07b-137">Ziehen Sie das **Calendar Semester** -Attribut aus dem Bereich **Attribute** in die **\<new level>** -Zelle des Bereichs **Hierarchien** unterhalb der **Calendar Year** -Ebene.</span><span class="sxs-lookup"><span data-stu-id="3d07b-137">Drag the **Calendar Semester** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Calendar Year** level.</span></span>  
  
3.  <span data-ttu-id="3d07b-138">Ziehen Sie das **Calendar Quarter** -Attribut aus dem Bereich **Attribute** in die **\<new level>** -Zelle des Bereichs **Hierarchien** unterhalb der **Calendar Semester** -Ebene.</span><span class="sxs-lookup"><span data-stu-id="3d07b-138">Drag the **Calendar Quarter** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Calendar Semester** level.</span></span>  
  
4.  <span data-ttu-id="3d07b-139">Ziehen Sie das **English Month Name** -Attribut aus dem Bereich **Attribute** in die **\<new level>** -Zelle des Bereichs **Hierarchien** unterhalb der **Calendar Quarter** -Ebene.</span><span class="sxs-lookup"><span data-stu-id="3d07b-139">Drag the **English Month Name** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Calendar Quarter** level.</span></span>  
  
5.  <span data-ttu-id="3d07b-140">Ziehen Sie das **Date Key** -Attribut aus dem Bereich **Attribute** in die **\<new level>** -Zelle des Bereichs **Hierarchien** unterhalb der **English Month Name** -Ebene.</span><span class="sxs-lookup"><span data-stu-id="3d07b-140">Drag the **Date Key** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **English Month Name** level.</span></span>  
  
6.  <span data-ttu-id="3d07b-141">Klicken Sie im Bereich **Hierarchien** mit der rechten Maustaste auf die Titelleiste der **Hierarchie** Hierarchie, klicken Sie auf **Umbenennen**, und geben Sie dann ein `Calendar Date` .</span><span class="sxs-lookup"><span data-stu-id="3d07b-141">In the **Hierarchies** pane, right-click the title bar of the **Hierarchy** hierarchy, click **Rename**, and then type `Calendar Date`.</span></span>  
  
7.  <span data-ttu-id="3d07b-142">Benennen Sie mithilfe des Rechtsklick-Kontextmenüs in der- `Calendar Date` Hierarchie die **English Month Name** -Ebene in um `Calendar Month` , und benennen Sie dann die **Date Key** -Ebene in um `Date` .</span><span class="sxs-lookup"><span data-stu-id="3d07b-142">By using the right-click context menu, in the `Calendar Date` hierarchy, rename the **English Month Name** level to `Calendar Month`, and then rename the **Date Key** level to `Date`.</span></span>  
  
8.  <span data-ttu-id="3d07b-143">Löschen Sie das **Full Date Alternate Key** -Attribut aus dem Bereich **Attribute** , da Sie es nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="3d07b-143">Delete the **Full Date Alternate Key** attribute from the **Attributes** pane because you will not be using it.</span></span> <span data-ttu-id="3d07b-144">Klicken Sie im Bestätigungsfenster **Objekte löschen** auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="3d07b-144">Click **OK** in the **Delete Objects** confirmation window.</span></span>  
  
9. <span data-ttu-id="3d07b-145">Klicken Sie im Menü **File** (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="3d07b-145">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-attribute-relationships"></a><span data-ttu-id="3d07b-146">Definieren von Attributbeziehungen</span><span class="sxs-lookup"><span data-stu-id="3d07b-146">Defining Attribute Relationships</span></span>  
 <span data-ttu-id="3d07b-147">Sofern die zugrunde liegenden Daten dies unterstützen, sollten Sie auch Attributbeziehungen zwischen Attributen definieren.</span><span class="sxs-lookup"><span data-stu-id="3d07b-147">If the underlying data supports it, you should define attribute relationships between attributes.</span></span> <span data-ttu-id="3d07b-148">Durch Definieren von Attributbeziehungen wird die Dimensions-, Partitions- und Abfrageverarbeitung beschleunigt.</span><span class="sxs-lookup"><span data-stu-id="3d07b-148">Defining attribute relationships speeds up dimension, partition, and query processing.</span></span>  
  
#### <a name="to-define-attribute-relationships"></a><span data-ttu-id="3d07b-149">So definieren Sie Attributbeziehungen</span><span class="sxs-lookup"><span data-stu-id="3d07b-149">To define attribute relationships</span></span>  
  
1.  <span data-ttu-id="3d07b-150">Klicken Sie im **Dimensions-Designer** für die Dimension auf `Date` die Registerkarte **Attribut Beziehungen** .</span><span class="sxs-lookup"><span data-stu-id="3d07b-150">In the **Dimension Designer** for the `Date` dimension, click the **Attribute Relationships** tab.</span></span>  
  
2.  <span data-ttu-id="3d07b-151">Klicken Sie im Diagramm mit der rechten Maustaste auf das **English Month Name** -Attribut, und klicken Sie auf **Neue Attributbeziehung**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-151">In the diagram, right-click the **English Month Name** attribute, and then click **New Attribute Relationship**.</span></span>  
  
3.  <span data-ttu-id="3d07b-152">Im Dialogfeld **Attributbeziehung erstellen** lautet das **Quellattribut\*\*\*\*English Month Name**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-152">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **English Month Name**.</span></span> <span data-ttu-id="3d07b-153">Legen Sie den Wert für **Verknüpftes Attribut** auf **Calendar Quarter**fest.</span><span class="sxs-lookup"><span data-stu-id="3d07b-153">Set the **Related Attribute** to **Calendar Quarter**.</span></span>  
  
4.  <span data-ttu-id="3d07b-154">Stellen Sie in der Liste **Beziehungstyp** den Beziehungstyp auf **Fest**ein.</span><span class="sxs-lookup"><span data-stu-id="3d07b-154">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
     <span data-ttu-id="3d07b-155">Der Beziehungstyp ist **Fest** , da sich Beziehungen zwischen den Elementen nicht im Laufe der Zeit ändern.</span><span class="sxs-lookup"><span data-stu-id="3d07b-155">The relationship type is **Rigid** because relationships between the members will not change over time.</span></span>  
  
5.  <span data-ttu-id="3d07b-156">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-156">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="3d07b-157">Klicken Sie im Diagramm mit der rechten Maustaste auf das **Calendar Quarter** -Attribut, und klicken Sie auf **Neue Attributbeziehung**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-157">In the diagram, right-click the **Calendar Quarter** attribute, and then click **New Attribute Relationship**.</span></span>  
  
7.  <span data-ttu-id="3d07b-158">Im Dialogfeld **Attributbeziehung erstellen** lautet das **Quellattribut\*\*\*\*Calendar Quarter**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-158">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **Calendar Quarter**.</span></span> <span data-ttu-id="3d07b-159">Legen Sie den Wert für **Verknüpftes Attribut** auf **Calendar Semester**fest.</span><span class="sxs-lookup"><span data-stu-id="3d07b-159">Set the **Related Attribute** to **Calendar Semester**.</span></span>  
  
8.  <span data-ttu-id="3d07b-160">Stellen Sie in der Liste **Beziehungstyp** den Beziehungstyp auf **Fest**ein.</span><span class="sxs-lookup"><span data-stu-id="3d07b-160">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
9. <span data-ttu-id="3d07b-161">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-161">Click **OK**.</span></span>  
  
10. <span data-ttu-id="3d07b-162">Klicken Sie im Diagramm mit der rechten Maustaste auf das **Calendar Semester** -Attribut, und klicken Sie auf **Neue Attributbeziehung**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-162">In the diagram, right-click the **Calendar Semester** attribute, and then click **New Attribute Relationship**.</span></span>  
  
11. <span data-ttu-id="3d07b-163">Im Dialogfeld **Attributbeziehung erstellen** lautet das **Quellattribut\*\*\*\*Calendar Semester**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-163">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **Calendar Semester**.</span></span> <span data-ttu-id="3d07b-164">Legen Sie den Wert für **Verknüpftes Attribut** auf **Calendar Year**fest.</span><span class="sxs-lookup"><span data-stu-id="3d07b-164">Set the **Related Attribute** to **Calendar Year**.</span></span>  
  
12. <span data-ttu-id="3d07b-165">Stellen Sie in der Liste **Beziehungstyp** den Beziehungstyp auf **Fest**ein.</span><span class="sxs-lookup"><span data-stu-id="3d07b-165">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
13. <span data-ttu-id="3d07b-166">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-166">Click **OK**.</span></span>  
  
14. <span data-ttu-id="3d07b-167">Klicken Sie im Menü **File** (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="3d07b-167">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="providing-unique-dimension-member-names"></a><span data-ttu-id="3d07b-168">Angeben von eindeutigen Dimensionselementnamen</span><span class="sxs-lookup"><span data-stu-id="3d07b-168">Providing Unique Dimension Member Names</span></span>  
 <span data-ttu-id="3d07b-169">In dieser Aufgabe erstellen Sie benutzerfreundliche Namensspalten, die von den Attributen **EnglishMonthName**, **CalendarQuarter**und **CalendarSemester** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3d07b-169">In this task, you will create user-friendly name columns that will be used by the **EnglishMonthName**, **CalendarQuarter**, and **CalendarSemester** attributes.</span></span>  
  
#### <a name="to-provide-unique-dimension-member-names"></a><span data-ttu-id="3d07b-170">So stellen Sie eindeutige Dimensionselementnamen zur Verfügung</span><span class="sxs-lookup"><span data-stu-id="3d07b-170">To provide unique dimension member names</span></span>  
  
1.  <span data-ttu-id="3d07b-171">Um zur Datenquellen Sicht \*\* [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW 2012\*\* zu wechseln, doppelklicken Sie im Ordner **Datenquellen Sichten** in Projektmappen-Explorer auf die Datenquellen Sicht.</span><span class="sxs-lookup"><span data-stu-id="3d07b-171">To switch to the **[!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW 2012** data source view, double-click it in the **Data Source Views** folder in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="3d07b-172">Klicken Sie im Bereich **Tabellen** mit der rechten Maustaste auf `Date` , und klicken Sie dann auf **neue benannte Berechnung**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-172">In the **Tables** pane, right-click `Date`, and then click **New Named Calculation**.</span></span>  
  
3.  <span data-ttu-id="3d07b-173">Geben Sie im Dialogfeld **benannte Berechnung erstellen** `MonthName` im Feld **Spaltenname** ein, und geben Sie dann die folgende Anweisung in das Feld **Ausdruck** ein (Sie können die Anweisung auch kopieren und Einfügen):</span><span class="sxs-lookup"><span data-stu-id="3d07b-173">In the **Create Named Calculation** dialog box, type `MonthName` in the **Column name** box, and then type or copy and paste the following statement in the **Expression** box:</span></span>  
  
    ```  
    EnglishMonthName+' '+ CONVERT(CHAR (4), CalendarYear)  
    ```  
  
     <span data-ttu-id="3d07b-174">Mit dieser Anweisung werden der Monat und das Jahr für jeden Monat in der Tabelle zu einer neuen Spalte verknüpft.</span><span class="sxs-lookup"><span data-stu-id="3d07b-174">The statement concatenates the month and year for each month in the table into a new column.</span></span>  
  
4.  <span data-ttu-id="3d07b-175">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-175">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="3d07b-176">Klicken Sie im Bereich **Tabellen** mit der rechten Maustaste auf `Date` , und klicken Sie dann auf **neue benannte Berechnung**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-176">In the **Tables** pane, right-click `Date`, and then click **New Named Calculation**.</span></span>  
  
6.  <span data-ttu-id="3d07b-177">Geben Sie im Dialogfeld **benannte Berechnung erstellen** `CalendarQuarterDesc` in das Feld **Spaltenname** ein, und geben Sie dann das folgende SQL-Skript in das Feld **Ausdruck** ein (Sie können das Skript auch kopieren und Einfügen):</span><span class="sxs-lookup"><span data-stu-id="3d07b-177">In the **Create Named Calculation** dialog box, type `CalendarQuarterDesc` in the **Column name** box, and then type or copy and paste the following SQL script in the **Expression** box:</span></span>  
  
    ```  
    'Q' + CONVERT(CHAR (1), CalendarQuarter) +' '+ 'CY ' +  
    CONVERT(CHAR (4), CalendarYear)  
    ```  
  
     <span data-ttu-id="3d07b-178">Mit diesem SQL-Skript werden das Kalenderquartal und das Jahr für jedes Quartal in der Tabelle zu einer neuen Spalte verknüpft.</span><span class="sxs-lookup"><span data-stu-id="3d07b-178">This SQL script concatenates the calendar quarter and year for each quarter in the table into a new column.</span></span>  
  
7.  <span data-ttu-id="3d07b-179">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-179">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="3d07b-180">Klicken Sie im Bereich **Tabellen** mit der rechten Maustaste auf `Date` , und klicken Sie dann auf **neue benannte Berechnung**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-180">In the **Tables** pane, right-click `Date`, and then click **New Named Calculation**.</span></span>  
  
9. <span data-ttu-id="3d07b-181">Geben Sie im Dialogfeld **benannte Berechnung erstellen** `CalendarSemesterDesc` in das Feld **Spaltenname** ein, und geben Sie dann das folgende SQL-Skript in das Feld **Ausdruck** ein (Sie können das Skript auch kopieren und Einfügen):</span><span class="sxs-lookup"><span data-stu-id="3d07b-181">In the **Create Named Calculation** dialog box, type `CalendarSemesterDesc` in the **Column name** box, and then type or copy and paste the following SQL script in the **Expression** box:</span></span>  
  
    ```  
    CASE  
    WHEN CalendarSemester = 1 THEN 'H1' + ' ' + 'CY' + ' '   
           + CONVERT(CHAR(4), CalendarYear)  
    ELSE  
    'H2' + ' ' + 'CY' + ' ' + CONVERT(CHAR(4), CalendarYear)  
    END  
    ```  
  
     <span data-ttu-id="3d07b-182">Mit diesem SQL-Skript werden das Kalendersemester und das Jahr für jedes Semester in der Tabelle zu einer neuen Spalte verknüpft.</span><span class="sxs-lookup"><span data-stu-id="3d07b-182">This SQL script concatenates the calendar semester and year for each semester in the table into a new column.</span></span>  
  
10. <span data-ttu-id="3d07b-183">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-183">Click **OK.**</span></span>  
  
11. <span data-ttu-id="3d07b-184">Klicken Sie im Menü **File** (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="3d07b-184">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-composite-keycolumns-and-setting-the-name-column"></a><span data-ttu-id="3d07b-185">Definieren von zusammengesetzten KeyColumns und Festlegen der Namensspalte</span><span class="sxs-lookup"><span data-stu-id="3d07b-185">Defining Composite KeyColumns and Setting the Name Column</span></span>  
 <span data-ttu-id="3d07b-186">Die Eigenschaft **KeyColumns** enthält die Spalte bzw. Spalten, die den Schlüssel für das Attribut darstellen.</span><span class="sxs-lookup"><span data-stu-id="3d07b-186">The **KeyColumns** property contains the column or columns that represent the key for the attribute.</span></span> <span data-ttu-id="3d07b-187">In dieser Aufgabe definieren Sie zusammengesetzte Schlüsselspalten ( **KeyColumns**).</span><span class="sxs-lookup"><span data-stu-id="3d07b-187">In this task, you will define composite **KeyColumns**.</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-english-month-name-attribute"></a><span data-ttu-id="3d07b-188">So definieren Sie zusammengesetzte KeyColumns für das English Month Name-Attribut</span><span class="sxs-lookup"><span data-stu-id="3d07b-188">To define composite KeyColumns for the English Month Name attribute</span></span>  
  
1.  <span data-ttu-id="3d07b-189">Öffnen Sie die Registerkarte **Dimensionsstruktur** für die Date-Dimension.</span><span class="sxs-lookup"><span data-stu-id="3d07b-189">Open the **Dimension Structure** tab for the Date dimension.</span></span>  
  
2.  <span data-ttu-id="3d07b-190">Klicken Sie im Bereich **Attribute** auf das **English Month Name** -Attribut.</span><span class="sxs-lookup"><span data-stu-id="3d07b-190">In the **Attributes** pane, click the **English Month Name** attribute.</span></span>  
  
3.  <span data-ttu-id="3d07b-191">Klicken Sie im Fenster **Eigenschaften** auf das Feld **KeyColumns** und anschließend auf die Schaltfläche zum Durchsuchen (**...**).</span><span class="sxs-lookup"><span data-stu-id="3d07b-191">In the **Properties** window, click the **KeyColumns** field, and then click the browse (**...**) button.</span></span>  
  
4.  <span data-ttu-id="3d07b-192">Wählen Sie im Dialogfeld **Schlüssel Spalten** in der Liste **Verfügbare Spalten** die Spalte **CalendarYear**aus, und klicken Sie dann auf die **>** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="3d07b-192">In the **Key Columns** dialog box, in the **Available Columns** list, select the column **CalendarYear**, and then click the **>** button.</span></span>  
  
5.  <span data-ttu-id="3d07b-193">Die Spalten **EnglishMonthName** und **CalendarYear** werden jetzt in der Liste **Schlüsselspalten** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3d07b-193">The **EnglishMonthName** and **CalendarYear** columns are now displayed in the **Key Columns** list.</span></span>  
  
6.  <span data-ttu-id="3d07b-194">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-194">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="3d07b-195">Um die **NameColumn** -Eigenschaft des **EnglishMonthName** -Attributs festzulegen, klicken Sie in das Feld **NameColumn** des Eigenschaftenfensters und anschließend auf die Schaltfläche zum Durchsuchen (**...**).</span><span class="sxs-lookup"><span data-stu-id="3d07b-195">To set the **NameColumn** property of the **EnglishMonthName** attribute, click the **NameColumn** field in the Properties window, and then click the browse (**...**) button.</span></span>  
  
8.  <span data-ttu-id="3d07b-196">Wählen Sie im Dialogfeld **Namensspalte** in der Liste **Quell Spalte** die Option aus `MonthName` , und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-196">In the **Name Column** dialog box, in the **Source Column** list, select `MonthName`, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="3d07b-197">Klicken Sie im Menü **File** (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="3d07b-197">On the **File** menu, click **Save All**.</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-calendar-quarter-attribute"></a><span data-ttu-id="3d07b-198">So definieren Sie zusammengesetzte KeyColumns für das "Calendar Quarter"-Attribut</span><span class="sxs-lookup"><span data-stu-id="3d07b-198">To define composite KeyColumns for the Calendar Quarter attribute</span></span>  
  
1.  <span data-ttu-id="3d07b-199">Klicken Sie im Bereich **Attribute** auf das **Calendar Quarter** -Attribut.</span><span class="sxs-lookup"><span data-stu-id="3d07b-199">In the **Attributes** pane, click the **Calendar Quarter** attribute.</span></span>  
  
2.  <span data-ttu-id="3d07b-200">Klicken Sie im Fenster **Eigenschaften** auf das Feld **KeyColumns** und anschließend auf die Schaltfläche zum Durchsuchen (**...**).</span><span class="sxs-lookup"><span data-stu-id="3d07b-200">In the **Properties** window, click the **KeyColumns** field, and then click the browse (**...**) button.</span></span>  
  
3.  <span data-ttu-id="3d07b-201">Wählen Sie im Dialogfeld **Schlüssel Spalten** in der Liste **Verfügbare Spalten** die Spalte **CalendarYear**aus, und klicken Sie dann auf die **>** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="3d07b-201">In the **Key Columns** dialog box, in the **Available Columns** list, select the column **CalendarYear**, and then click the **>** button.</span></span>  
  
     <span data-ttu-id="3d07b-202">Die Spalten **CalendarQuarter** und **CalendarYear** werden jetzt in der Liste **Schlüsselspalten** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3d07b-202">The **CalendarQuarter** and **CalendarYear** columns are now displayed in the **Key Columns** list.</span></span>  
  
4.  <span data-ttu-id="3d07b-203">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-203">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="3d07b-204">Um die **NameColumn** -Eigenschaft des **Calendar Quarter** -Attributs festzulegen, klicken Sie in das Feld **NameColumn** des Eigenschaftenfensters und anschließend auf die Schaltfläche zum Durchsuchen (**...**).</span><span class="sxs-lookup"><span data-stu-id="3d07b-204">To set the **NameColumn** property of the **Calendar Quarter** attribute, click the **NameColumn** field in the Properties window, and then click the browse (**...**) button.</span></span>  
  
6.  <span data-ttu-id="3d07b-205">Wählen Sie im Dialogfeld **Namensspalte** in der Liste **Quell Spalte** die Option aus `CalendarQuarterDesc` , und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-205">In the **Name Column** dialog box, in the **Source Column** list, select `CalendarQuarterDesc`, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="3d07b-206">Klicken Sie im Menü **File** (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="3d07b-206">On the **File** menu, click **Save All**.</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-calendar-semester-attribute"></a><span data-ttu-id="3d07b-207">So definieren Sie zusammengesetzte KeyColumns für das "Calendar Semester"-Attribut</span><span class="sxs-lookup"><span data-stu-id="3d07b-207">To define composite KeyColumns for the Calendar Semester attribute</span></span>  
  
1.  <span data-ttu-id="3d07b-208">Klicken Sie im Bereich **Attribute** auf das **Calendar Semester** -Attribut.</span><span class="sxs-lookup"><span data-stu-id="3d07b-208">In the **Attributes** pane, click the **Calendar Semester** attribute.</span></span>  
  
2.  <span data-ttu-id="3d07b-209">Klicken Sie im Fenster **Eigenschaften** auf das Feld **KeyColumns** und anschließend auf die Schaltfläche zum Durchsuchen (**...**).</span><span class="sxs-lookup"><span data-stu-id="3d07b-209">In the **Properties** window, click the **KeyColumns** field, and then click the browse (**...**) button.</span></span>  
  
3.  <span data-ttu-id="3d07b-210">Wählen Sie im Dialogfeld **Schlüsselspalten** die Spalte **CalendarYear** in der Liste **Verfügbare Spalten**aus, und klicken Sie anschließend auf die Schaltfläche **>** .</span><span class="sxs-lookup"><span data-stu-id="3d07b-210">In the **Key Columns** dialog box, in the **Available Columns** list, select the column, **CalendarYear**, and then click the **>** button.</span></span>  
  
     <span data-ttu-id="3d07b-211">Die Spalten **CalendarSemester** und **CalendarYear** werden jetzt in der Liste **Schlüsselspalten** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3d07b-211">The **CalendarSemester** and **CalendarYear** columns are now displayed in the **Key Columns** list.</span></span>  
  
4.  <span data-ttu-id="3d07b-212">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-212">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="3d07b-213">Um die **NameColumn** -Eigenschaft des **Calendar Semester** -Attributs festzulegen, klicken Sie in das Feld **NameColumn** des Eigenschaftenfensters und anschließend auf die Schaltfläche zum Durchsuchen (**...**).</span><span class="sxs-lookup"><span data-stu-id="3d07b-213">To set the **NameColumn** property of the **Calendar Semester** attribute, click the **NameColumn** field in the property window, and then click the browse (**...**) button.</span></span>  
  
6.  <span data-ttu-id="3d07b-214">Wählen Sie im Dialogfeld **Namensspalte** in der Liste **Quell Spalte** die Option aus `CalendarSemesterDesc` , und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-214">In the **Name Column** dialog box, in the **Source Column** list, select `CalendarSemesterDesc`, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="3d07b-215">Klicken Sie im Menü **File** (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="3d07b-215">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="deploying-and-viewing-the-changes"></a><span data-ttu-id="3d07b-216">Bereitstellen und Anzeigen der Änderungen</span><span class="sxs-lookup"><span data-stu-id="3d07b-216">Deploying and Viewing the Changes</span></span>  
 <span data-ttu-id="3d07b-217">Nach dem Ändern von Attributen und Hierarchien müssen Sie die Änderungen bereitstellen und die verknüpften Objekte neu verarbeiten, bevor Sie die Änderungen anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="3d07b-217">After you have changed attributes and hierarchies, you must deploy the changes and reprocess the related objects before you can view the changes.</span></span>  
  
#### <a name="to-deploy-and-view-the-changes"></a><span data-ttu-id="3d07b-218">So stellen Sie Änderungen bereit und zeigen sie an</span><span class="sxs-lookup"><span data-stu-id="3d07b-218">To deploy and view the changes</span></span>  
  
1.  <span data-ttu-id="3d07b-219">Klicken Sie im Menü **Erstellen** von [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf **Analysis Services Tutorial bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-219">On the **Build** menu of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="3d07b-220">Nachdem Sie die Meldung **Bereitstellung erfolgreich abgeschlossen** erhalten haben, klicken Sie im **Dimensions-Designer** für die Dimension auf die Registerkarte **Browser** `Date` , und klicken Sie dann auf der Symbolleiste des Designers auf die Schaltfläche Verbindung wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="3d07b-220">After you have received the **Deployment Completed Successfully** message, click the **Browser** tab of **Dimension Designer** for the `Date` dimension, and then click the Reconnect button on the toolbar of the designer.</span></span>  
  
3.  <span data-ttu-id="3d07b-221">Wählen Sie aus der Liste **Hierarchie\*\*\*\*Calendar Quarter** aus.</span><span class="sxs-lookup"><span data-stu-id="3d07b-221">Select **Calendar Quarter** from the **Hierarchy** list.</span></span> <span data-ttu-id="3d07b-222">Überprüfen Sie die Elemente in der **Calendar Quarter** -Attributhierarchie.</span><span class="sxs-lookup"><span data-stu-id="3d07b-222">Review the members in the **Calendar Quarter** attribute hierarchy.</span></span>  
  
     <span data-ttu-id="3d07b-223">Beachten Sie, dass die Namen der Elemente der Attributhierarchie **Calendar Quarter** eindeutiger und einfacher zu verwenden sind, da Sie eine benannte Berechnung erstellt haben, um sie als Namen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3d07b-223">Notice that the names of the members of the **Calendar Quarter** attribute hierarchy are clearer and easier to use because you created a named calculation to use as the name.</span></span> <span data-ttu-id="3d07b-224">Elemente sind jetzt für jedes Quartal pro Jahr in der Hierarchie des **Calendar Quarter** -Attributs vorhanden.</span><span class="sxs-lookup"><span data-stu-id="3d07b-224">Members now exist in the **Calendar Quarter** attribute hierarchy for each quarter in each year.</span></span> <span data-ttu-id="3d07b-225">Die Elemente werden nicht in chronologischer Reihenfolge sortiert.</span><span class="sxs-lookup"><span data-stu-id="3d07b-225">The members are not sorted in chronological order.</span></span> <span data-ttu-id="3d07b-226">Stattdessen sind sie nach Quartal und dann nach Jahr sortiert.</span><span class="sxs-lookup"><span data-stu-id="3d07b-226">Instead they are sorted by quarter and then by year.</span></span> <span data-ttu-id="3d07b-227">In der nächsten Aufgabe in diesem Thema ändern Sie dieses Verhalten, um die Elemente dieser Attributhierarchie nach Jahr und dann nach Quartal zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="3d07b-227">In the next task in this topic, you will modify this behavior to sort the members of this attribute hierarchy by year and then by quarter.</span></span>  
  
4.  <span data-ttu-id="3d07b-228">Überprüfen Sie die Elemente der Attributhierarchien **English Month Name** - und **Calendar Semester** .</span><span class="sxs-lookup"><span data-stu-id="3d07b-228">Review the members of the **English Month Name** and **Calendar Semester** attribute hierarchies.</span></span>  
  
     <span data-ttu-id="3d07b-229">Beachten Sie, dass die Elemente dieser Hierarchien ebenfalls nicht in chronologischer Reihenfolge sortiert sind.</span><span class="sxs-lookup"><span data-stu-id="3d07b-229">Notice that the members of these hierarchies are also not sorted in chronological order.</span></span> <span data-ttu-id="3d07b-230">Stattdessen sind sie nach Monat beziehungsweise Semester und dann nach Jahr sortiert.</span><span class="sxs-lookup"><span data-stu-id="3d07b-230">Instead, they are sorted by month or semester, respectively, and then by year.</span></span> <span data-ttu-id="3d07b-231">In der nächsten Aufgabe in diesem Thema ändern Sie dieses Verhalten, um die Sortierreihenfolge zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3d07b-231">In the next task in this topic, you will modify this behavior to change this sort order.</span></span>  
  
## <a name="changing-the-sort-order-by-modifying-composite-key-member-order"></a><span data-ttu-id="3d07b-232">Ändern der Sortierreihenfolge durch Ändern der Elementreihenfolge zusammengesetzter Schlüssel</span><span class="sxs-lookup"><span data-stu-id="3d07b-232">Changing the Sort Order by Modifying Composite Key Member Order</span></span>  
 <span data-ttu-id="3d07b-233">In dieser Aufgabe ändern Sie die Sortierreihenfolge, indem Sie die Reihenfolge der Schlüssel, aus denen der zusammengesetzte Schlüssel besteht, ändern.</span><span class="sxs-lookup"><span data-stu-id="3d07b-233">In this task, you will change the sort order by changing the order of the keys that make up the composite key.</span></span>  
  
#### <a name="to-modify-the-composite-key-member-order"></a><span data-ttu-id="3d07b-234">So ändern Sie die Elementreihenfolge zusammengesetzter Schlüssel</span><span class="sxs-lookup"><span data-stu-id="3d07b-234">To modify the composite key member order</span></span>  
  
1.  <span data-ttu-id="3d07b-235">Öffnen Sie die Registerkarte **Dimensions Struktur** des Dimensions-Designers für die `Date` Dimension, und wählen Sie dann im Bereich **Attribute** die Option **Calendar Semester** aus.</span><span class="sxs-lookup"><span data-stu-id="3d07b-235">Open the **Dimension Structure** tab of Dimension Designer for the `Date` dimension, and then select **Calendar Semester** in the **Attributes** pane.</span></span>  
  
2.  <span data-ttu-id="3d07b-236">Überprüfen Sie im Eigenschaftenfenster den Wert für die **OrderBy** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3d07b-236">In the Properties window, review the value for the **OrderBy** property.</span></span> <span data-ttu-id="3d07b-237">Er wird auf **Schlüssel**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3d07b-237">It is set to **Key**.</span></span>  
  
     <span data-ttu-id="3d07b-238">Die Elemente der **Calendar Semester** -Attributhierarchie werden nach ihren Schlüsselwerten sortiert.</span><span class="sxs-lookup"><span data-stu-id="3d07b-238">The members of the **Calendar Semester** attribute hierarchy are sorted by their key value.</span></span> <span data-ttu-id="3d07b-239">Mit einem zusammengesetzten Schlüssel basiert die Sortierung der Elementschlüssel zuerst auf dem Wert des ersten Elementschlüssels und dann auf dem Wert des zweiten Elementschlüssels.</span><span class="sxs-lookup"><span data-stu-id="3d07b-239">With a composite key, the ordering of the member keys is based first on the value of the first member key, and then on the value of the second member key.</span></span> <span data-ttu-id="3d07b-240">Mit anderen Worten: Die Elemente der **Calendar Semester** -Attributhierarchie werden zuerst nach Semester und dann nach Jahr sortiert.</span><span class="sxs-lookup"><span data-stu-id="3d07b-240">In other words, the members of the **Calendar Semester** attribute hierarchy are sorted first by semester and then by year.</span></span>  
  
3.  <span data-ttu-id="3d07b-241">Klicken Sie im Eigenschaftenfenster auf die Schaltfläche mit den Auslassungspunkten (**...**), um den **KeyColumns** -Eigenschaftswert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3d07b-241">In the Properties window, click the ellipsis browse button (**...**) to change the **KeyColumns** property value.</span></span>  
  
4.  <span data-ttu-id="3d07b-242">Überprüfen Sie in der Liste **Schlüsselspalten** des Dialogfelds **Schlüsselspalten** , ob **CalendarSemester** ausgewählt ist. Klicken Sie anschließend auf den Pfeil nach unten, um die Reihenfolge der Elemente dieses zusammengesetzten Schlüssels umzukehren.</span><span class="sxs-lookup"><span data-stu-id="3d07b-242">In the **Key Columns** list of the **Key Columns** dialog box, verify that **CalendarSemester** is selected, and then click the down arrow to reverse the order of the members of this composite key.</span></span> <span data-ttu-id="3d07b-243">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-243">Click **OK**.</span></span>  
  
     <span data-ttu-id="3d07b-244">Die Elemente der Attributhierarchie sind jetzt zuerst nach Jahr und dann nach Semester sortiert.</span><span class="sxs-lookup"><span data-stu-id="3d07b-244">The members of the attribute hierarchy are now sorted first by year and then by semester.</span></span>  
  
5.  <span data-ttu-id="3d07b-245">Wählen Sie im Bereich **Attribute** die Option **Calendar Quarter** aus, und klicken Sie anschließend im Eigenschaftenfenster auf die Schaltfläche mit den Auslassungspunkten (**...**) für die **KeyColumns** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3d07b-245">Select **Calendar Quarter** in the **Attributes** pane, and then click the ellipsis browse button (**...**) for the **KeyColumns** property in the Properties window.</span></span>  
  
6.  <span data-ttu-id="3d07b-246">Überprüfen Sie in der Liste **Schlüsselspalten** des Dialogfelds **Schlüsselspalten** , ob **CalendarQuarter** ausgewählt ist. Klicken Sie anschließend auf den Pfeil nach unten, um die Reihenfolge der Elemente dieses zusammengesetzten Schlüssels umzukehren.</span><span class="sxs-lookup"><span data-stu-id="3d07b-246">In the **Key Columns** list of the **Key Columns** dialog box, verify that **CalendarQuarter** is selected, and then click the down arrow to reverse the order of the members of this composite key.</span></span> <span data-ttu-id="3d07b-247">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-247">Click **OK**.</span></span>  
  
     <span data-ttu-id="3d07b-248">Die Elemente der Attributhierarchie sind jetzt zuerst nach Jahr und dann nach Quartal sortiert.</span><span class="sxs-lookup"><span data-stu-id="3d07b-248">The members of the attribute hierarchy are now sorted first by year and then by quarter.</span></span>  
  
7.  <span data-ttu-id="3d07b-249">Wählen Sie im Bereich **Attribute** den Eintrag **English Month Name** aus, und klicken Sie anschließend im Fenster Eigenschaften auf die Schaltfläche mit den drei Auslassungspunkten (**...**) für die **KeyColumns** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3d07b-249">Select **English Month Name** in the **Attributes** pane, and then click the ellipsis button (**...**) for the **KeyColumns** property in the Properties window.</span></span>  
  
8.  <span data-ttu-id="3d07b-250">Überprüfen Sie in der Liste **Schlüsselspalten** des Dialogfelds **Schlüsselspalten** , ob **EnglishMonthName** ausgewählt ist. Klicken Sie anschließend auf den Pfeil nach unten, um die Reihenfolge der Elemente dieses zusammengesetzten Schlüssels umzukehren.</span><span class="sxs-lookup"><span data-stu-id="3d07b-250">In the **Key Columns** list of the **Key Columns** dialog box, verify that **EnglishMonthName** is selected, and then click the down arrow to reverse the order of the members of this composite key.</span></span> <span data-ttu-id="3d07b-251">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-251">Click **OK**.</span></span>  
  
     <span data-ttu-id="3d07b-252">Die Elemente der Attributhierarchie sind jetzt zuerst nach Jahr und dann nach Monat sortiert.</span><span class="sxs-lookup"><span data-stu-id="3d07b-252">The members of the attribute hierarchy are now sorted first by year and then by month.</span></span>  
  
9. <span data-ttu-id="3d07b-253">Klicken Sie im Menü **Erstellen** von [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf **Analysis Services Tutorial bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="3d07b-253">On the **Build** menu of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Deploy Analysis Services Tutorial**.</span></span> <span data-ttu-id="3d07b-254">Wenn die Bereitstellung erfolgreich abgeschlossen wurde, klicken Sie im Dimensions-Designer für die Dimension auf die Registerkarte **Browser** `Date` .</span><span class="sxs-lookup"><span data-stu-id="3d07b-254">When deployment has successfully completed, click the **Browser** tab in Dimension Designer for the `Date` dimension.</span></span>  
  
10. <span data-ttu-id="3d07b-255">Klicken Sie auf der Symbolleiste der Registerkarte **Browser** auf die Schaltfläche zum Wiederherstellen der Verbindung.</span><span class="sxs-lookup"><span data-stu-id="3d07b-255">On the toolbar of the **Browser** tab, click the Reconnect button.</span></span>  
  
11. <span data-ttu-id="3d07b-256">Überprüfen Sie die Elemente der Attributhierarchien **Calendar Quarter** - und **Calendar Semester** .</span><span class="sxs-lookup"><span data-stu-id="3d07b-256">Review the members of the **Calendar Quarter** and **Calendar Semester** attribute hierarchies.</span></span>  
  
     <span data-ttu-id="3d07b-257">Beachten Sie, dass die Elemente dieser Hierarchien jetzt in chronologischer Reihenfolge sortiert sind, also nach Jahr und dann nach Quartal beziehungsweise Semester.</span><span class="sxs-lookup"><span data-stu-id="3d07b-257">Notice that the members of these hierarchies are now sorted in chronological order, by year and then by quarter or semester, respectively.</span></span>  
  
12. <span data-ttu-id="3d07b-258">Überprüfen Sie die Elemente der Attributhierarchie **English Month Name** .</span><span class="sxs-lookup"><span data-stu-id="3d07b-258">Review the members of the **English Month Name** attribute hierarchy.</span></span>  
  
     <span data-ttu-id="3d07b-259">Beachten Sie, dass die Elemente der Attributhierarchie jetzt zuerst nach Jahr und dann alphabetisch nach Monat sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="3d07b-259">Notice that the members of the hierarchy are now sorted first by year and then alphabetically by month.</span></span> <span data-ttu-id="3d07b-260">Dies hängt mit der Tatsache zusammen, dass der Datentyp der EnglishCalendarMonth-Spalte in der Datenquellensicht eine Zeichenfolgenspalte ist, basierend auf dem Datentyp „nvarchar“ in der zugrunde liegenden relationalen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="3d07b-260">This is because the data type for the EnglishCalendarMonth column in the data source view is a string column, based on the nvarchar data type in the underlying relational database.</span></span> <span data-ttu-id="3d07b-261">Informationen darüber, wie die Monate innerhalb jedes Jahres chronologisch sortiert werden können, finden Sie unter [Sortieren von Attributelementen basierend auf einem sekundären Attribut](lesson-4-5-sorting-attribute-members-based-on-a-secondary-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="3d07b-261">For information about how to enable the months to be sorted chronologically within each year, see [Sorting Attribute Members Based on a Secondary Attribute](lesson-4-5-sorting-attribute-members-based-on-a-secondary-attribute.md).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="3d07b-262">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="3d07b-262">Next Task in Lesson</span></span>  
 [<span data-ttu-id="3d07b-263">Durchsuchen des bereitgestellten Cubes</span><span class="sxs-lookup"><span data-stu-id="3d07b-263">Browsing the Deployed Cube</span></span>](lesson-3-5-browsing-the-deployed-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="3d07b-264">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3d07b-264">See Also</span></span>  
 [<span data-ttu-id="3d07b-265">Dimensionen in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="3d07b-265">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
