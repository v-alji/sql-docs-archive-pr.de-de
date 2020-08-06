---
title: Ändern der Customer-Dimension | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5b5aed99-1760-4bc7-b248-52ecb0b97ebc
author: minewiskan
ms.author: owend
ms.openlocfilehash: bd5c5c47205a89f8429b0b6f0ba55da266d5e811
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620034"
---
# <a name="modifying-the-customer-dimension"></a><span data-ttu-id="8ac1f-102">Ändern der Customer-Dimension</span><span class="sxs-lookup"><span data-stu-id="8ac1f-102">Modifying the Customer Dimension</span></span>
  <span data-ttu-id="8ac1f-103">Es gibt viele verschiedene Möglichkeiten zum Verbessern der Benutzerfreundlichkeit und Funktionalität der Dimensionen in einem Cube.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-103">There are many different ways that you can increase the usability and functionality of the dimensions in a cube.</span></span> <span data-ttu-id="8ac1f-104">Mit den Schritten in diesem Thema ändern Sie die Customer-Dimension.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-104">In the tasks in this topic, you modify the Customer dimension.</span></span>  
  
## <a name="renaming-attributes"></a><span data-ttu-id="8ac1f-105">Umbenennen von Attributen</span><span class="sxs-lookup"><span data-stu-id="8ac1f-105">Renaming Attributes</span></span>  
 <span data-ttu-id="8ac1f-106">Sie können Attributnamen auf der Registerkarte **Dimensionsstruktur** des Dimensions-Designers ändern.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-106">You can change attribute names with the **Dimension Structure** tab of Dimension Designer.</span></span>  
  
#### <a name="to-rename-an-attribute"></a><span data-ttu-id="8ac1f-107">So benennen Sie ein Attribut um</span><span class="sxs-lookup"><span data-stu-id="8ac1f-107">To rename an attribute</span></span>  
  
1.  <span data-ttu-id="8ac1f-108">Wechseln Sie in **zum** Dimensions-Designer [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]für die Customer-Dimension.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-108">Switch to **Dimension Designer** for the Customer dimension in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="8ac1f-109">Doppelklicken Sie dazu auf die Dimension **Customer** im Knoten **Dimensionen** des Projektmappen-Explorers.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-109">To do this, double-click the **Customer** dimension in the **Dimensions** node of Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="8ac1f-110">Klicken Sie im Bereich **Attribute** mit der rechten Maustaste auf **English Country Region Name**, und klicken Sie anschließend auf **Umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-110">In the **Attributes** pane, right-click **English Country Region Name**, and then click **Rename**.</span></span> <span data-ttu-id="8ac1f-111">Ändern Sie den Namen des Attributs in `Country-Region` .</span><span class="sxs-lookup"><span data-stu-id="8ac1f-111">Change the name of the attribute to `Country-Region`.</span></span>  
  
3.  <span data-ttu-id="8ac1f-112">Ändern Sie die Namen der folgenden Attribute auf die gleiche Art:</span><span class="sxs-lookup"><span data-stu-id="8ac1f-112">Change the names of the following attributes in the same manner:</span></span>  
  
    -   <span data-ttu-id="8ac1f-113">**English Education** -Attribut: ändern in`Education`</span><span class="sxs-lookup"><span data-stu-id="8ac1f-113">**English Education** attribute - change to `Education`</span></span>  
  
    -   <span data-ttu-id="8ac1f-114">**English-Beruf** -Attribut-ändern in`Occupation`</span><span class="sxs-lookup"><span data-stu-id="8ac1f-114">**English Occupation** attribute - change to `Occupation`</span></span>  
  
    -   <span data-ttu-id="8ac1f-115">**State Province Name** -Attribut-ändern in`State-Province`</span><span class="sxs-lookup"><span data-stu-id="8ac1f-115">**State Province Name** attribute - change to `State-Province`</span></span>  
  
4.  <span data-ttu-id="8ac1f-116">Klicken Sie im Menü **File** (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="8ac1f-116">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="creating-a-hierarchy"></a><span data-ttu-id="8ac1f-117">Erstellen einer Hierarchie</span><span class="sxs-lookup"><span data-stu-id="8ac1f-117">Creating a Hierarchy</span></span>  
 <span data-ttu-id="8ac1f-118">Sie können eine neue Hierarchie erstellen, indem Sie ein Attribut aus dem Bereich **Attribute** in den Bereich **Hierarchien** ziehen.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-118">You can create a new hierarchy by dragging an attribute from the **Attributes** pane to the **Hierarchies** pane.</span></span>  
  
#### <a name="to-create-a-hierarchy"></a><span data-ttu-id="8ac1f-119">So erstellen Sie eine Hierarchie</span><span class="sxs-lookup"><span data-stu-id="8ac1f-119">To create a hierarchy</span></span>  
  
1.  <span data-ttu-id="8ac1f-120">Ziehen Sie das- `Country-Region` Attribut aus dem Bereich **Attribute** in den Bereich **Hierarchien** .</span><span class="sxs-lookup"><span data-stu-id="8ac1f-120">Drag the `Country-Region` attribute from the **Attributes** pane into the **Hierarchies** pane.</span></span>  
  
2.  <span data-ttu-id="8ac1f-121">Ziehen Sie das- `State-Province` Attribut aus dem Bereich **Attribute** in die Zelle des Bereichs **\<new level>** **Hierarchien** unterhalb der `Country-Region` Ebene.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-121">Drag the `State-Province` attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the `Country-Region` level.</span></span>  
  
3.  <span data-ttu-id="8ac1f-122">Ziehen Sie das **City** -Attribut aus dem Bereich **Attribute** in die Zelle des Bereichs **\<new level>** **Hierarchien** unterhalb der `State-Province` Ebene.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-122">Drag the **City** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the `State-Province` level.</span></span>  
  
4.  <span data-ttu-id="8ac1f-123">Klicken Sie im Bereich **Hierarchien** der Registerkarte **Dimensions Struktur** mit der rechten Maustaste auf die Titelleiste der **Hierarchie** Hierarchie, wählen Sie **Umbenennen**aus, und geben Sie dann ein `Customer Geography` .</span><span class="sxs-lookup"><span data-stu-id="8ac1f-123">In the **Hierarchies** pane of the **Dimension Structure** tab, right-click the title bar of the **Hierarchy** hierarchy, select **Rename**, and then type `Customer Geography`.</span></span>  
  
     <span data-ttu-id="8ac1f-124">Der Name der Hierarchie lautet jetzt `Customer Geography` .</span><span class="sxs-lookup"><span data-stu-id="8ac1f-124">The name of the hierarchy is now `Customer Geography`.</span></span>  
  
5.  <span data-ttu-id="8ac1f-125">Klicken Sie im Menü **File** (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="8ac1f-125">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="adding-a-named-calculation"></a><span data-ttu-id="8ac1f-126">Hinzufügen einer benannten Berechnung</span><span class="sxs-lookup"><span data-stu-id="8ac1f-126">Adding a Named Calculation</span></span>  
 <span data-ttu-id="8ac1f-127">Sie können eine benannte Berechnung, bei der es sich um einen SQL-Ausdruck handelt, der als eine berechnete Spalte dargestellt wird, zu einer Tabelle in einer Datenquellensicht hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-127">You can add a named calculation, which is a SQL expression that is represented as a calculated column, to a table in a data source view.</span></span> <span data-ttu-id="8ac1f-128">Der Ausdruck wird als Spalte in der Tabelle angezeigt und verhält sich auch so.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-128">The expression appears and behaves as a column in the table.</span></span> <span data-ttu-id="8ac1f-129">Mithilfe von benannten Ausdrücken können Sie das relationale Schema von vorhandenen Tabellen in einer Datenquellensicht erweitern, ohne die Tabelle in der zugrunde liegenden Datenquelle zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-129">Named calculations let you extend the relational schema of existing tables in a data source view without modifying the table in the underlying data source.</span></span> <span data-ttu-id="8ac1f-130">Weitere Informationen finden Sie unter [Definieren von benannten Berechnungen in einer Datenquellensicht &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)</span><span class="sxs-lookup"><span data-stu-id="8ac1f-130">For more information, see [Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)</span></span>  
  
#### <a name="to-add-a-named-calculation"></a><span data-ttu-id="8ac1f-131">So fügen Sie eine benannte Berechnung hinzu</span><span class="sxs-lookup"><span data-stu-id="8ac1f-131">To add a named calculation</span></span>  
  
1.  <span data-ttu-id="8ac1f-132">Öffnen Sie die \*\* [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW 2012\*\* -Datenquellen Sicht, indem Sie in Projektmappen-Explorer im Ordner **Datenquellen Sichten** darauf doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-132">Open the **[!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] DW 2012** data source view by double-clicking it in the **Data Source Views** folder in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="8ac1f-133">Klicken Sie mit der rechten Maustaste im Bereich **Tabellen** auf der linken Seite auf **Customer**und anschließend auf **Neue benannte Berechnung**.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-133">In the **Tables** pane on the left, right-click **Customer**, and then click **New Named Calculation**.</span></span>  
  
3.  <span data-ttu-id="8ac1f-134">Geben Sie im Dialogfeld **benannte Berechnung erstellen** `FullName` im Feld **Spaltenname** ein, und geben Sie dann die folgende `CASE` Anweisung in das Feld **Ausdruck** ein (Sie können die Anweisung auch kopieren und Einfügen):</span><span class="sxs-lookup"><span data-stu-id="8ac1f-134">In the **Create Named Calculation** dialog box, type `FullName` in the **Column name** box, and then type or copy and paste the following `CASE` statement in the **Expression** box:</span></span>  
  
    ```  
    CASE  
       WHEN MiddleName IS NULL THEN  
       FirstName + ' ' + LastName  
       ELSE  
       FirstName + ' ' + MiddleName + ' ' + LastName  
    END  
    ```  
  
     <span data-ttu-id="8ac1f-135">Die `CASE` -Anweisung verkettet die Spalten **FirstName**, **MiddleName**und **LastName** in eine einzelne Spalte, die Sie in der Customer-Dimension als angezeigten Namen für das **Customer** -Attribut verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-135">The `CASE` statement concatenates the **FirstName**, **MiddleName**, and **LastName** columns into a single column that you will use in the Customer dimension as the displayed name for the **Customer** attribute.</span></span>  
  
4.  <span data-ttu-id="8ac1f-136">Klicken Sie auf **OK**, und erweitern Sie **Customer** im **Tabellen** -Bereich.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-136">Click **OK**, and then expand **Customer** in the **Tables** pane.</span></span>  
  
     <span data-ttu-id="8ac1f-137">Die `FullName` benannte Berechnung wird in der Liste der Spalten in der Customer-Tabelle mit einem Symbol angezeigt, das angibt, dass es sich um eine benannte Berechnung handelt.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-137">The `FullName` named calculation appears in the list of columns in the Customer table, with an icon that indicates that it is a named calculation.</span></span>  
  
5.  <span data-ttu-id="8ac1f-138">Klicken Sie im Menü **File** (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="8ac1f-138">On the **File** menu, click **Save All**.</span></span>  
  
6.  <span data-ttu-id="8ac1f-139">Klicken Sie im Bereich **Tabellen** mit der rechten Maustaste auf **Customer**, und klicken Sie anschließend auf **Daten durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-139">In the **Tables** pane, right-click **Customer**, and then click **Explore Data**.</span></span>  
  
7.  <span data-ttu-id="8ac1f-140">Überprüfen Sie die letzte Spalte in der Sicht **Customer-Tabelle durchsuchen** .</span><span class="sxs-lookup"><span data-stu-id="8ac1f-140">Review the last column in the **Explore Customer Table** view.</span></span>  
  
     <span data-ttu-id="8ac1f-141">Beachten Sie, dass die `FullName` Spalte in der Datenquellen Sicht angezeigt wird, wobei Daten aus verschiedenen Spalten aus der zugrunde liegenden Datenquelle und ohne Änderung der ursprünglichen Datenquelle ordnungsgemäß verkettet werden.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-141">Notice that the `FullName` column appears in the data source view, correctly concatenating data from several columns from the underlying data source and without modifying the original data source.</span></span>  
  
8.  <span data-ttu-id="8ac1f-142">Schließen Sie die Registerkarte **Customer-Tabelle durchsuchen** .</span><span class="sxs-lookup"><span data-stu-id="8ac1f-142">Close the **Explore Customer Table** tab.</span></span>  
  
## <a name="using-the-named-calculation-for-member-names"></a><span data-ttu-id="8ac1f-143">Verwenden der benannten Berechnung für Elementnamen</span><span class="sxs-lookup"><span data-stu-id="8ac1f-143">Using the Named Calculation for Member Names</span></span>  
 <span data-ttu-id="8ac1f-144">Nachdem Sie eine benannte Berechnung in der Datenquellensicht erstellt haben, können Sie sie als Eigenschaft eines Attributs verwenden.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-144">After you have created a named calculation in the data source view, you can use the named calculation as a property of an attribute.</span></span>  
  
#### <a name="to-use-the-named-calculation-for-member-names"></a><span data-ttu-id="8ac1f-145">So verwenden Sie die benannte Berechnung für Elementnamen</span><span class="sxs-lookup"><span data-stu-id="8ac1f-145">To use the named calculation for member names</span></span>  
  
1.  <span data-ttu-id="8ac1f-146">Wechseln Sie zum Dimensions-Designer für die Customer-Dimension.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-146">Switch to Dimension Designer for the Customer dimension.</span></span>  
  
2.  <span data-ttu-id="8ac1f-147">Klicken Sie im Bereich **Attribute** der Registerkarte **Dimensionsstruktur** auf das **Customer Key** -Attribut.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-147">In the **Attributes** pane of the **Dimension Structure** tab, click the **Customer Key** attribute.</span></span>  
  
3.  <span data-ttu-id="8ac1f-148">Öffnen Sie das Fenster Eigenschaften, und klicken Sie in der Titelleiste auf die Schaltfläche **Automatisch im Hintergrund** , sodass dieses Fenster geöffnet bleibt.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-148">Open the Properties window and click the **Auto Hide** button on the title bar so that it stays open.</span></span>  
  
4.  <span data-ttu-id="8ac1f-149">Geben Sie im Eigenschaften Feld **Name den Namen** ein `Full Name` .</span><span class="sxs-lookup"><span data-stu-id="8ac1f-149">In the **Name** property field, type `Full Name`.</span></span>  
  
5.  <span data-ttu-id="8ac1f-150">Klicken Sie unten auf das Eigenschafts Feld **namecolumzun** und dann auf die Schaltfläche zum Durchsuchen (**...**), um das Dialogfeld **Namensspalte** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-150">Click in the **NameColumn** property field at the bottom, and then click the browse (**...**) button to open the **Name Column** dialog box.</span></span>  
  
6.  <span data-ttu-id="8ac1f-151">Wählen Sie `FullName` unten in der Liste **Quell Spalte** die Option aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-151">Select `FullName` at the bottom of the **Source column** list, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="8ac1f-152">Ziehen Sie auf der Registerkarte Dimensions Struktur das- `Full Name` Attribut aus dem Bereich **Attribute** in die Zelle des Bereichs **\<new level>** **Hierarchien** unterhalb der **City** -Ebene.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-152">In the Dimensions Structure tab, drag the `Full Name` attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **City** level.</span></span>  
  
8.  <span data-ttu-id="8ac1f-153">Klicken Sie im Menü **File** (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="8ac1f-153">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-display-folders"></a><span data-ttu-id="8ac1f-154">Definieren von Anzeigeordnern</span><span class="sxs-lookup"><span data-stu-id="8ac1f-154">Defining Display Folders</span></span>  
 <span data-ttu-id="8ac1f-155">Sie können Anzeigeordner verwenden, um Benutzer- und Attributhierarchien in Ordnerstrukturen zu gruppieren und so die Benutzerfreundlichkeit zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-155">You can use display folders to group user and attribute hierarchies into folder structures to increase usability.</span></span>  
  
#### <a name="to-define-display-folders"></a><span data-ttu-id="8ac1f-156">So definieren Sie Anzeigeordner</span><span class="sxs-lookup"><span data-stu-id="8ac1f-156">To define display folders</span></span>  
  
1.  <span data-ttu-id="8ac1f-157">Öffnen Sie die Registerkarte **Dimensionsstruktur** für die Customer-Dimension.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-157">Open the **Dimension Structure** tab for the Customer dimension.</span></span>  
  
2.  <span data-ttu-id="8ac1f-158">Wählen Sie im Bereich **Attribute** die folgenden Attribute, indem Sie beim Klicken die STRG-Taste gedrückt halten:</span><span class="sxs-lookup"><span data-stu-id="8ac1f-158">In the **Attributes** pane, select the following attributes by holding down the CTRL key while clicking each of them:</span></span>  
  
    -   <span data-ttu-id="8ac1f-159">**City (Ort)**</span><span class="sxs-lookup"><span data-stu-id="8ac1f-159">**City**</span></span>  
  
    -   `Country-Region`  
  
    -   <span data-ttu-id="8ac1f-160">**Postal Code**</span><span class="sxs-lookup"><span data-stu-id="8ac1f-160">**Postal Code**</span></span>  
  
    -   `State-Province`  
  
3.  <span data-ttu-id="8ac1f-161">Klicken Sie im Eigenschaftenfenster oben auf das **AttributeHierarchyDisplayFolder** -Eigenschaften Feld (möglicherweise müssen Sie darauf zeigen, um den vollständigen Namen anzuzeigen), und geben Sie dann ein `Location` .</span><span class="sxs-lookup"><span data-stu-id="8ac1f-161">In the Properties window, click the **AttributeHierarchyDisplayFolder** property field at the top (you might need to point to it to see the full name), and then type `Location`.</span></span>  
  
4.  <span data-ttu-id="8ac1f-162">Klicken Sie im Bereich **Hierarchien** `Customer Geography` auf, und wählen Sie dann in der Eigenschaftenfenster auf der rechten Seite `Location` als Wert der **DisplayFolder** -Eigenschaft aus.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-162">In the **Hierarchies** pane, click `Customer Geography`, and then in the Properties window on the right, select `Location` as the value of the **DisplayFolder** property.</span></span>  
  
5.  <span data-ttu-id="8ac1f-163">Wählen Sie im Bereich **Attribute** die folgenden Attribute, indem Sie beim Klicken die STRG-Taste gedrückt halten:</span><span class="sxs-lookup"><span data-stu-id="8ac1f-163">In the **Attributes** pane, select the following attributes by holding down the CTRL key while clicking each of them:</span></span>  
  
    -   <span data-ttu-id="8ac1f-164">**Commute Distance**</span><span class="sxs-lookup"><span data-stu-id="8ac1f-164">**Commute Distance**</span></span>  
  
    -   `Education`  
  
    -   <span data-ttu-id="8ac1f-165">**Geschlecht**</span><span class="sxs-lookup"><span data-stu-id="8ac1f-165">**Gender**</span></span>  
  
    -   <span data-ttu-id="8ac1f-166">**House Owner Flag**</span><span class="sxs-lookup"><span data-stu-id="8ac1f-166">**House Owner Flag**</span></span>  
  
    -   <span data-ttu-id="8ac1f-167">**Marital Status**</span><span class="sxs-lookup"><span data-stu-id="8ac1f-167">**Marital Status**</span></span>  
  
    -   <span data-ttu-id="8ac1f-168">**Number Cars Owned**</span><span class="sxs-lookup"><span data-stu-id="8ac1f-168">**Number Cars Owned**</span></span>  
  
    -   <span data-ttu-id="8ac1f-169">**Anzahl der Kinder zu Hause**</span><span class="sxs-lookup"><span data-stu-id="8ac1f-169">**Number Children At Home**</span></span>  
  
    -   `Occupation`  
  
    -   <span data-ttu-id="8ac1f-170">**Total Children**</span><span class="sxs-lookup"><span data-stu-id="8ac1f-170">**Total Children**</span></span>  
  
    -   <span data-ttu-id="8ac1f-171">**Yearly Income**</span><span class="sxs-lookup"><span data-stu-id="8ac1f-171">**Yearly Income**</span></span>  
  
6.  <span data-ttu-id="8ac1f-172">Klicken Sie in der Eigenschaftenfenster oben auf das Eigenschaften Feld **AttributeHierarchyDisplayFolder** , und geben Sie dann ein `Demographic` .</span><span class="sxs-lookup"><span data-stu-id="8ac1f-172">In the Properties window, click the **AttributeHierarchyDisplayFolder** property field at the top, and then type `Demographic`.</span></span>  
  
7.  <span data-ttu-id="8ac1f-173">Wählen Sie im Bereich **Attribute** die folgenden Attribute, indem Sie beim Klicken die STRG-Taste gedrückt halten:</span><span class="sxs-lookup"><span data-stu-id="8ac1f-173">In the **Attributes** pane, select the following attributes by holding down the CTRL key while clicking each of them:</span></span>  
  
    -   <span data-ttu-id="8ac1f-174">**E-Mail-Adresse**</span><span class="sxs-lookup"><span data-stu-id="8ac1f-174">**Email Address**</span></span>  
  
    -   <span data-ttu-id="8ac1f-175">**Smartphone**</span><span class="sxs-lookup"><span data-stu-id="8ac1f-175">**Phone**</span></span>  
  
8.  <span data-ttu-id="8ac1f-176">Klicken Sie im Eigenschaftenfenster auf das **AttributeHierarchyDisplayFolder** -Eigenschaften Feld, und geben Sie ein `Contacts` .</span><span class="sxs-lookup"><span data-stu-id="8ac1f-176">In the Properties window, click the **AttributeHierarchyDisplayFolder** property field and type `Contacts`.</span></span>  
  
9. <span data-ttu-id="8ac1f-177">Klicken Sie im Menü **File** (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="8ac1f-177">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-composite-keycolumns"></a><span data-ttu-id="8ac1f-178">Definieren von zusammengesetzten KeyColumns</span><span class="sxs-lookup"><span data-stu-id="8ac1f-178">Defining Composite KeyColumns</span></span>  
 <span data-ttu-id="8ac1f-179">Die Eigenschaft **KeyColumns** enthält die Spalte bzw. Spalten, die den Schlüssel für das Attribut darstellen.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-179">The **KeyColumns** property contains the column or columns that represent the key for the attribute.</span></span> <span data-ttu-id="8ac1f-180">In dieser Lektion erstellen Sie einen zusammengesetzten Schlüssel für das **City** -Attribut und das- `State-Province` Attribut.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-180">In this lesson, you create a composite key for the **City** and `State-Province` attributes.</span></span> <span data-ttu-id="8ac1f-181">Zusammengesetzte Schlüssel können hilfreich sein, wenn Sie ein Attribut eindeutig identifizieren müssen.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-181">Composite keys can be helpful when you need to uniquely identify an attribute.</span></span> <span data-ttu-id="8ac1f-182">Wenn Sie z. b. später in diesem Tutorial Attribut Beziehungen definieren, muss ein **City** -Attribut ein-Attribut eindeutig identifizieren `State-Province` .</span><span class="sxs-lookup"><span data-stu-id="8ac1f-182">For example, when you define attribute relationships later in this tutorial, a **City** attribute must uniquely identify a `State-Province` attribute.</span></span> <span data-ttu-id="8ac1f-183">Es können jedoch mehrere Orte mit dem gleichen Namen in verschiedenen Staaten geben.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-183">However, there could be several cities with the same name in different states.</span></span> <span data-ttu-id="8ac1f-184">Aus diesem Grund erstellen Sie für das **City** -Attribut einen zusammengesetzten Schlüssel, der sich aus den Spalten **StateProvinceName** und **City** zusammensetzt.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-184">For this reason, you will create a composite key that is composed of the **StateProvinceName** and **City** columns for the **City** attribute.</span></span> <span data-ttu-id="8ac1f-185">Weitere Informationen finden Sie unter [Ändern der KeyColumn-Eigenschaft eines Attributs](multidimensional-models/attribute-properties-modify-the-keycolumn-property.md).</span><span class="sxs-lookup"><span data-stu-id="8ac1f-185">For more information, see [Modify the KeyColumn Property of an Attribute](multidimensional-models/attribute-properties-modify-the-keycolumn-property.md).</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-city-attribute"></a><span data-ttu-id="8ac1f-186">So definieren Sie zusammengesetzte KeyColumns für das City-Attribut</span><span class="sxs-lookup"><span data-stu-id="8ac1f-186">To define composite KeyColumns for the City attribute</span></span>  
  
1.  <span data-ttu-id="8ac1f-187">Öffnen Sie die Registerkarte **Dimensionsstruktur** für die Customer-Dimension.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-187">Open the **Dimension Structure** tab for the Customer dimension.</span></span>  
  
2.  <span data-ttu-id="8ac1f-188">Klicken Sie im Bereich **Attribute** auf das **City** -Attribut.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-188">In the **Attributes** pane, click the **City** attribute.</span></span>  
  
3.  <span data-ttu-id="8ac1f-189">Klicken Sie im Fenster **Eigenschaften** weiter unten auf das Feld **KeyColumns** und anschließend auf die Schaltfläche zum Durchsuchen (**...**).</span><span class="sxs-lookup"><span data-stu-id="8ac1f-189">In the **Properties** window, click in the **KeyColumns** field near the bottom, and then click the browse (**...**) button.</span></span>  
  
4.  <span data-ttu-id="8ac1f-190">Wählen Sie im Dialogfeld **Schlüsselspalten** die Spalte **StateProvinceName** in der Liste **Verfügbare Spalten**aus, und klicken Sie anschließend auf die Schaltfläche **>** .</span><span class="sxs-lookup"><span data-stu-id="8ac1f-190">In the **Key Columns** dialog box, in the **Available Columns** list, select the column **StateProvinceName**, and then click the **>** button.</span></span>  
  
     <span data-ttu-id="8ac1f-191">Die Spalten **City** und **StateProvinceName** werden jetzt in der Liste **Schlüsselspalten** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-191">The **City** and **StateProvinceName** columns are now displayed in the **Key Columns** list.</span></span>  
  
5.  <span data-ttu-id="8ac1f-192">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-192">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="8ac1f-193">Um die **NameColumn** -Eigenschaft des **City** -Attributs festzulegen, klicken Sie in das Feld **NameColumn** des Fensters „Eigenschaften“ und anschließend auf die Schaltfläche zum Durchsuchen (**...**).</span><span class="sxs-lookup"><span data-stu-id="8ac1f-193">To set the **NameColumn** property of the **City** attribute, click the **NameColumn** field in the Properties window, and then click the browse (**...**) button.</span></span>  
  
7.  <span data-ttu-id="8ac1f-194">Wählen Sie im Dialogfeld **Namensspalte** in der Liste **Quellspalte** die Option **City**aus, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-194">In the **Name Column** dialog box, in the **Source column** list, select **City**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="8ac1f-195">Klicken Sie im Menü **File** (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="8ac1f-195">On the **File** menu, click **Save All**.</span></span>  
  
#### <a name="to-define-composite-keycolumns-for-the-state-province-attribute"></a><span data-ttu-id="8ac1f-196">So definieren Sie zusammengesetzte KeyColumns für das State-Province-Attribut</span><span class="sxs-lookup"><span data-stu-id="8ac1f-196">To define composite KeyColumns for the State-Province attribute</span></span>  
  
1.  <span data-ttu-id="8ac1f-197">Stellen Sie sicher, dass die Registerkarte **Dimensionsstruktur** für die Customer-Dimension geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-197">Make sure the **Dimension Structure** tab for the Customer dimension is open.</span></span>  
  
2.  <span data-ttu-id="8ac1f-198">Klicken Sie im Bereich **Attribute** auf das `State-Province` Attribut.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-198">In the **Attributes** pane, click the `State-Province` attribute.</span></span>  
  
3.  <span data-ttu-id="8ac1f-199">Klicken Sie im Fenster **Eigenschaften** auf das Feld **KeyColumns** und anschließend auf die Schaltfläche zum Durchsuchen (**...**).</span><span class="sxs-lookup"><span data-stu-id="8ac1f-199">In the **Properties** window, click in the **KeyColumns** field, and then click the browse (**...**) button.</span></span>  
  
4.  <span data-ttu-id="8ac1f-200">Wählen Sie im Dialogfeld **Schlüsselspalten** die Spalte **EnglishCountryRegionName** in der Liste **Verfügbare Spalten**aus, und klicken Sie anschließend auf die Schaltfläche **>** .</span><span class="sxs-lookup"><span data-stu-id="8ac1f-200">In the **Key Columns** dialog box, in the **Available Columns** list, select the column **EnglishCountryRegionName**, and then click the **>** button.</span></span>  
  
     <span data-ttu-id="8ac1f-201">Die Spalten **EnglishCountryRegionName** und **StateProvinceName** werden jetzt in der Liste **Schlüsselspalten** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-201">The **EnglishCountryRegionName** and **StateProvinceName** columns are now displayed in the **Key Columns** list.</span></span>  
  
5.  <span data-ttu-id="8ac1f-202">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-202">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="8ac1f-203">Um die **namecolumzun** -Eigenschaft des `State-Province` Attributs festzulegen, klicken Sie im Eigenschaftenfenster auf das Feld **namecolenn** und dann auf die Schaltfläche zum Durchsuchen (**..**.).</span><span class="sxs-lookup"><span data-stu-id="8ac1f-203">To set the **NameColumn** property of the `State-Province` attribute, click the **NameColumn** field in the Properties window, and then click the browse (**...**) button.</span></span>  
  
7.  <span data-ttu-id="8ac1f-204">Wählen Sie im Dialogfeld **Namensspalte** in der Liste **Quellspalte** die Option **StateProvinceName**aus, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-204">In the **Name Column** dialog box, in the **Source column** list, select **StateProvinceName**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="8ac1f-205">Klicken Sie im Menü **File** (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="8ac1f-205">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-attribute-relationships"></a><span data-ttu-id="8ac1f-206">Definieren von Attributbeziehungen</span><span class="sxs-lookup"><span data-stu-id="8ac1f-206">Defining Attribute Relationships</span></span>  
 <span data-ttu-id="8ac1f-207">Sofern die zugrunde liegenden Daten dies unterstützen, sollten Sie auch Attributbeziehungen zwischen Attributen definieren.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-207">If the underlying data supports it, you should define attribute relationships between attributes.</span></span> <span data-ttu-id="8ac1f-208">Durch Definieren von Attributbeziehungen wird die Dimensions-, Partitions- und Abfrageverarbeitung beschleunigt.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-208">Defining attribute relationships speeds up dimension, partition, and query processing.</span></span> <span data-ttu-id="8ac1f-209">Weitere Informationen finden Sie unter [Definieren von Attributbeziehungen](multidimensional-models/attribute-relationships-define.md) und [Attributbeziehungen](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="8ac1f-209">For more information, see [Define Attribute Relationships](multidimensional-models/attribute-relationships-define.md) and [Attribute Relationships](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span></span>  
  
#### <a name="to-define-attribute-relationships"></a><span data-ttu-id="8ac1f-210">So definieren Sie Attributbeziehungen</span><span class="sxs-lookup"><span data-stu-id="8ac1f-210">To define attribute relationships</span></span>  
  
1.  <span data-ttu-id="8ac1f-211">Klicken Sie im **Dimensions-Designer** für die Customer-Dimension auf die Registerkarte **Attribut Beziehungen** . Möglicherweise müssen Sie warten.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-211">In the **Dimension Designer** for the Customer dimension, click the **Attribute Relationships** tab. You might need to wait.</span></span>  
  
2.  <span data-ttu-id="8ac1f-212">Klicken Sie im Diagramm mit der rechten Maustaste auf das **City** -Attribut, und wählen Sie anschließend **Neue Attributbeziehung**aus.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-212">In the diagram, right-click the **City** attribute, and then click **New Attribute Relationship**.</span></span>  
  
3.  <span data-ttu-id="8ac1f-213">Im Dialogfeld **Attributbeziehung erstellen** ist das **Quellattribut\*\*\*\*City**.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-213">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **City**.</span></span> <span data-ttu-id="8ac1f-214">Legen Sie das **zugehörige Attribut** auf fest `State-Province` .</span><span class="sxs-lookup"><span data-stu-id="8ac1f-214">Set the **Related Attribute** to `State-Province`.</span></span>  
  
4.  <span data-ttu-id="8ac1f-215">Stellen Sie in der Liste **Beziehungstyp** den Beziehungstyp auf **Fest**ein.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-215">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
     <span data-ttu-id="8ac1f-216">Der Beziehungstyp ist **Fest** , da sich Beziehungen zwischen den Elementen nicht im Laufe der Zeit ändern.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-216">The relationship type is **Rigid** because relationships between the members will not change over time.</span></span> <span data-ttu-id="8ac1f-217">Ein Ort wird beispielsweise normalerweise nicht Teil eines anderen Bundeslands oder Kantons.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-217">For example, it would be unusual for a city to become part of a different state or province.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="8ac1f-218">Klicken Sie im Diagramm mit der rechten Maustaste auf das `State-Province` Attribut, und wählen Sie dann **neue Attribut Beziehung**aus.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-218">In the diagram, right-click the `State-Province` attribute and then select **New Attribute Relationship**.</span></span>  
  
7.  <span data-ttu-id="8ac1f-219">Im Dialogfeld **Attribut Beziehung erstellen** ist das **Quell Attribut** `State-Province` .</span><span class="sxs-lookup"><span data-stu-id="8ac1f-219">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is `State-Province`.</span></span> <span data-ttu-id="8ac1f-220">Legen Sie das **zugehörige Attribut** auf fest `Country-Region` .</span><span class="sxs-lookup"><span data-stu-id="8ac1f-220">Set the **Related Attribute** to `Country-Region`.</span></span>  
  
8.  <span data-ttu-id="8ac1f-221">Stellen Sie in der Liste **Beziehungstyp** den Beziehungstyp auf **Fest**ein.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-221">In the **Relationship type** list, set the relationship type to **Rigid**.</span></span>  
  
9. <span data-ttu-id="8ac1f-222">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-222">Click **OK**.</span></span>  
  
10. <span data-ttu-id="8ac1f-223">Klicken Sie im Menü **File** (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="8ac1f-223">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="deploying-changes-processing-the-objects-and-viewing-the-changes"></a><span data-ttu-id="8ac1f-224">Bereitstellen von Änderungen, Verarbeiten der Objekte und Anzeigen der Änderungen</span><span class="sxs-lookup"><span data-stu-id="8ac1f-224">Deploying Changes, Processing the Objects, and Viewing the Changes</span></span>  
 <span data-ttu-id="8ac1f-225">Nach dem Ändern von Attributen und Hierarchien müssen Sie die Änderungen bereitstellen und die verknüpften Objekte neu verarbeiten, bevor Sie die Änderungen anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-225">After you have changed attributes and hierarchies, you must deploy the changes and reprocess the related objects before you can view the changes.</span></span>  
  
#### <a name="to-deploy-the-changes-process-the-objects-and-view-the-changes"></a><span data-ttu-id="8ac1f-226">So stellen Sie die Änderungen bereit, verarbeiten die Objekte und zeigen die Änderungen an</span><span class="sxs-lookup"><span data-stu-id="8ac1f-226">To deploy the changes, process the objects, and view the changes</span></span>  
  
1.  <span data-ttu-id="8ac1f-227">Klicken Sie im Menü **Erstellen** von [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf **Analysis Services Tutorial bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-227">On the **Build** menu of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="8ac1f-228">Nachdem die Meldung angezeigt wird, dass die **Bereitstellung erfolgreich abgeschlossen** wurde, klicken Sie auf die Registerkarte **Browser** im Dimensions-Designer für die Customer-Dimension, und klicken Sie links in der Symbolleiste auf die Schaltfläche zum Wiederherstellen der Verbindung.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-228">After you receive the **Deployment Completed Successfully** message, click the **Browser** tab of Dimension Designer for the Customer dimension, and then click the Reconnect button on the left side of the toolbar of the designer.</span></span>  
  
3.  <span data-ttu-id="8ac1f-229">Vergewissern Sie sich, dass `Customer Geography` in der Liste **Hierarchie** ausgewählt ist, und erweitern Sie dann im Browserbereich **alle**, **Australien**, **New South Wales**und anschließend **Coffs Harbour**.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-229">Verify that `Customer Geography` is selected in the **Hierarchy** list, and then in the browser pane, expand **All**, expand **Australia**, expand **New South Wales**, and then expand **Coffs Harbour**.</span></span>  
  
     <span data-ttu-id="8ac1f-230">Im Browser werden die Kunden in dem Ort angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-230">The browser displays the customers in the city.</span></span>  
  
4.  <span data-ttu-id="8ac1f-231">Wechseln Sie zum **Cube-Designer** , um den [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial Cube anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-231">Switch to **Cube Designer** for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span> <span data-ttu-id="8ac1f-232">Doppelklicken Sie hierzu auf den **Analysis Services Tutorial** -Cube im **Cubes** -Knoten **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-232">To do this, double-click the **Analysis Services Tutorial** cube in the **Cubes** node of **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="8ac1f-233">Klicken Sie auf die Registerkarte **Browser** und anschließend in der Symbolleiste des Designers auf die Schaltfläche zum Wiederherstellen der Verbindung.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-233">Click the **Browser** tab, and then click the Reconnect button on the toolbar of the designer.</span></span>  
  
6.  <span data-ttu-id="8ac1f-234">Erweitern Sie im Bereich **Measuregruppe** den Eintrag **Customer**.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-234">In the **Measure Group** pane, expand **Customer**.</span></span>  
  
     <span data-ttu-id="8ac1f-235">Beachten Sie, dass anstelle einer langen Liste von Attributen nur die Anzeigeordner und Attribute, die keine Anzeigeordnerwerte aufweisen, unterhalb von Customer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8ac1f-235">Notice that instead of a long list of attributes, only the display folders and the attributes that do not have display folder values appear underneath Customer.</span></span>  
  
7.  <span data-ttu-id="8ac1f-236">Klicken Sie im Menü **File** (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="8ac1f-236">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="8ac1f-237">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="8ac1f-237">Next Task in Lesson</span></span>  
 [<span data-ttu-id="8ac1f-238">Ändern der Product-Dimension</span><span class="sxs-lookup"><span data-stu-id="8ac1f-238">Modifying the Product Dimension</span></span>](lesson-3-3-modifying-the-product-dimension.md)  
  
## <a name="see-also"></a><span data-ttu-id="8ac1f-239">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8ac1f-239">See Also</span></span>  
 <span data-ttu-id="8ac1f-240">[Dimensions Attribut-Eigenschaften Referenz](multidimensional-models/dimension-attribute-properties-reference.md) </span><span class="sxs-lookup"><span data-stu-id="8ac1f-240">[Dimension Attribute Properties Reference](multidimensional-models/dimension-attribute-properties-reference.md) </span></span>  
 <span data-ttu-id="8ac1f-241">[Entfernen eines Attributs aus einer Dimension](multidimensional-models/attribute-properties-remove-an-attribute-from-a-dimension.md) </span><span class="sxs-lookup"><span data-stu-id="8ac1f-241">[Remove an Attribute from a Dimension](multidimensional-models/attribute-properties-remove-an-attribute-from-a-dimension.md) </span></span>  
 <span data-ttu-id="8ac1f-242">[Umbenennen eines Attributs](multidimensional-models/attribute-properties-rename-an-attribute.md) </span><span class="sxs-lookup"><span data-stu-id="8ac1f-242">[Rename an Attribute](multidimensional-models/attribute-properties-rename-an-attribute.md) </span></span>  
 [<span data-ttu-id="8ac1f-243">Definieren von benannten Berechnungen in einer Datenquellensicht &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8ac1f-243">Define Named Calculations in a Data Source View &#40;Analysis Services&#41;</span></span>](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md)  
  
  
