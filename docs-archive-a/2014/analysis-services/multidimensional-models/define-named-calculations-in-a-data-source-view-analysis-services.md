---
title: Definieren von benannten Berechnungen in einer Datenquellen Sicht (Analysis Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying named calculations
- data source views [Analysis Services], named calculations
- named calculations [Analysis Services]
ms.assetid: 729e7b12-6185-4b73-8bcb-cfe459b15355
author: minewiskan
ms.author: owend
ms.openlocfilehash: ae901c340fe29c042430d928a4abaea8e8cfe84b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618379"
---
# <a name="define-named-calculations-in-a-data-source-view-analysis-services"></a><span data-ttu-id="ad92c-102">Definieren von benannten Berechnungen in einer Datenquellensicht (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="ad92c-102">Define Named Calculations in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="ad92c-103">Eine benannte Berechnung ist ein SQL-Ausdruck, der als berechnete Spalte dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="ad92c-103">A named calculation is a SQL expression represented as a calculated column.</span></span> <span data-ttu-id="ad92c-104">Dieser Ausdruck wird als Spalte in der Tabelle angezeigt und verhält sich auch wie eine Spalte.</span><span class="sxs-lookup"><span data-stu-id="ad92c-104">This expression appears and behaves as a column in the table.</span></span> <span data-ttu-id="ad92c-105">Mit einer benannten Berechnung können Sie das relationale Schema vorhandener Tabellen oder Sichten in einer Datenquellensicht erweitern, ohne die Tabellen oder Sichten in der zugrunde liegenden Datenquelle zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ad92c-105">A named calculation lets you extend the relational schema of existing tables or views in a data source view without modifying the tables or views in the underlying data source.</span></span> <span data-ttu-id="ad92c-106">Betrachten Sie die folgenden Beispiele:</span><span class="sxs-lookup"><span data-stu-id="ad92c-106">Consider the following examples:</span></span>

-   <span data-ttu-id="ad92c-107">Erstellen Sie eine einzelne benannte Berechnung, die von mehreren Spalten in einer Faktentabelle abgeleitet wird (erstellen Sie z. B. einen Steuerbetrag, indem ein Steuersatz mit einem Verkaufspreis multipliziert wird).</span><span class="sxs-lookup"><span data-stu-id="ad92c-107">Create a single named calculation that is derived from multiple columns in a fact table (for example, creating Tax Amount by multiplying a tax rate by a sales price).</span></span>

-   <span data-ttu-id="ad92c-108">Erstellen Sie einen benutzerfreundlichen Namen für ein Dimensionselement.</span><span class="sxs-lookup"><span data-stu-id="ad92c-108">Construct a user friendly name for a dimension member.</span></span>

-   <span data-ttu-id="ad92c-109">Um die Abfrageleistung zu optimieren, erstellen Sie eine benannte Berechnung in der DSV, anstatt ein berechnetes Element in einem Cube zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ad92c-109">As a query performance enhancement, create a named calculation in the DSV instead of creating a calculated member in a cube.</span></span> <span data-ttu-id="ad92c-110">Benannte Berechnungen werden während der Verarbeitung berechnet, wohingegen berechnete Elemente zur Abfragezeit berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="ad92c-110">Named calculations are calculated during processing whereas calculated members are calculated at query time.</span></span>

## <a name="creating-named-calculations"></a><span data-ttu-id="ad92c-111">Erstellen benannter Berechnungen</span><span class="sxs-lookup"><span data-stu-id="ad92c-111">Creating Named Calculations</span></span>

> [!NOTE]
>  <span data-ttu-id="ad92c-112">Sie können einer benannten Abfrage keine benannte Berechnung hinzufügen. Die benannte Abfrage darf auch nicht auf einer Tabelle basieren, die eine benannte Berechnung enthält.</span><span class="sxs-lookup"><span data-stu-id="ad92c-112">You cannot add a named calculation to a named query, nor can you base a named query on a table that contains a named calculation.</span></span>

 <span data-ttu-id="ad92c-113">Beim Erstellen einer benannten Berechnung geben Sie einen Namen, den SQL-Ausdruck und (optional) eine Beschreibung für die Berechnung an.</span><span class="sxs-lookup"><span data-stu-id="ad92c-113">When you create a named calculation, you specify a name, the SQL expression, and, optionally, a description of the calculation.</span></span> <span data-ttu-id="ad92c-114">Der SQL-Ausdruck kann auf andere Tabellen in der Datenquellensicht verweisen.</span><span class="sxs-lookup"><span data-stu-id="ad92c-114">The SQL expression can refer to other tables in the data source view.</span></span> <span data-ttu-id="ad92c-115">Nachdem Sie die benannte Berechnung definiert haben, wird der in einer benannten Berechnung enthaltene Ausdruck an den Datenquellenanbieter gesendet und als die folgende SQL-Anweisung validiert, in der `<Expression>` den Ausdruck enthält, der die benannte Berechnung definiert.</span><span class="sxs-lookup"><span data-stu-id="ad92c-115">After the named calculation is defined, the expression in a named calculation is sent to the provider for the data source and validated as the following SQL statement in which `<Expression>` contains the expression that defines the named calculation.</span></span>

```
SELECT 
   <Table Name in Data Source>.*, 
   <Expression> AS <Column Name> 
FROM 
   <Table Name in Data Source> AS <Table Name in Data Source View>
```

 <span data-ttu-id="ad92c-116">Der Datentyp der Spalte wird von dem Datentyp des Skalarwertes bestimmt, der von dem Ausdruck zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ad92c-116">The data type of the column is determined by the data type of the scalar value returned by the expression.</span></span> <span data-ttu-id="ad92c-117">Wenn der Anbieter keine Fehler im Ausdruck findet, wird die Spalte der Tabelle hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ad92c-117">If the provider does not find any errors in the expression, the column is added to the table.</span></span>

 <span data-ttu-id="ad92c-118">Spalten, auf die im Ausdruck verwiesen wird, sollten nicht gekennzeichnet oder nur durch den Tabellennamen gekennzeichnet sein.</span><span class="sxs-lookup"><span data-stu-id="ad92c-118">Columns referenced in the expression should not be qualified or should be qualified by the table name only.</span></span> <span data-ttu-id="ad92c-119">Wenn Sie z. B. auf die SaleAmount-Spalte in einer Tabelle verweisen möchten, ist `SaleAmount` oder `Sales.SaleAmount` gültig, aber `dbo.Sales.SaleAmount` generiert einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="ad92c-119">For example, to refer to the SaleAmount column in a table, `SaleAmount` or `Sales.SaleAmount` is valid, but `dbo.Sales.SaleAmount` generates an error.</span></span>

 <span data-ttu-id="ad92c-120">Dieser Ausdruck wird nicht automatisch in Klammern eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="ad92c-120">The expression is not automatically enclosed between parentheses.</span></span> <span data-ttu-id="ad92c-121">Deshalb müssen Sie die Klammern in das Feld **Ausdruck** eingeben, wenn ein Ausdruck, z. B. eine SELECT-Anweisung, Klammern erfordert.</span><span class="sxs-lookup"><span data-stu-id="ad92c-121">Therefore, if an expression, such as a SELECT statement, requires parentheses, you must type the parentheses in the **Expression** box.</span></span> <span data-ttu-id="ad92c-122">Der folgende Ausdruck ist beispielsweise nur gültig, wenn Sie die Klammern eingeben.</span><span class="sxs-lookup"><span data-stu-id="ad92c-122">For example, the following expression is valid only if you type the parentheses.</span></span>

```
(SELECT Description FROM Categories WHERE Categories.CategoryID = CategoryID)
```

## <a name="add-or-edit-a-named-calculation"></a><span data-ttu-id="ad92c-123">Hinzufügen oder Bearbeiten einer benannten Berechnung</span><span class="sxs-lookup"><span data-stu-id="ad92c-123">Add or Edit a Named Calculation</span></span>

1.  <span data-ttu-id="ad92c-124">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das Projekt, oder stellen Sie eine Verbindung mit der Datenbank her, in der die Datenquellensicht enthalten ist, in der Sie eine benannte Berechnung definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ad92c-124">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you wish to define a named calculation.</span></span>

2.  <span data-ttu-id="ad92c-125">Erweitern Sie im Projektmappen-Explorer den Ordner **Datenquellensichten** , und doppelklicken Sie anschließend auf die Datenquellensicht.</span><span class="sxs-lookup"><span data-stu-id="ad92c-125">In Solution Explorer, expand the **Data Source Views** folder, then double-click the data source view.</span></span>

3.  <span data-ttu-id="ad92c-126">Klicken Sie im Bereich **Tabellen** oder **Diagramm** mit der rechten Maustaste auf die Tabelle, in der Sie die benannte Berechnung definieren möchten, und klicken Sie anschließend auf **Neue benannte Berechnung**.</span><span class="sxs-lookup"><span data-stu-id="ad92c-126">Right-click the table in which you wish to define the named calculation in either the **Tables** or the **Diagram** pane, and then click **New Named Calculation**.</span></span> <span data-ttu-id="ad92c-127">Stellen Sie sicher, dass Sie mit der rechten Maustaste auf den Tabellennamen klicken und nicht auf ein Attribut.</span><span class="sxs-lookup"><span data-stu-id="ad92c-127">Be sure to right-click on the table name, and not on an attribute.</span></span> <span data-ttu-id="ad92c-128">Das Menü sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="ad92c-128">The menu should look like the following:</span></span>

     <span data-ttu-id="ad92c-129">![Screenshot des Diagrammarbeitsbereichs, Kontextmenü](../media/ssas-olapdsv-diagram.gif "Screenshot des Diagrammarbeitsbereichs, Kontextmenü")</span><span class="sxs-lookup"><span data-stu-id="ad92c-129">![Screenshot of diagram workspace, right-click menu](../media/ssas-olapdsv-diagram.gif "Screenshot of diagram workspace, right-click menu")</span></span>

    > [!NOTE]
    >  <span data-ttu-id="ad92c-130">Um nach einer Tabelle oder Sicht zu suchen, können Sie die Option **Tabelle suchen** verwenden, indem Sie entweder auf das Menü **Datenquellensicht** klicken oder mit der rechten Maustaste auf einen offenen Bereich im Bereich **Tabellen** oder **Diagramm** klicken.</span><span class="sxs-lookup"><span data-stu-id="ad92c-130">To locate a table or view, you can use the **Find Table** option by either clicking the **Data Source View** menu or right-clicking in an open area of the **Tables** or **Diagram** panes.</span></span>

4.  <span data-ttu-id="ad92c-131">Führen Sie im Dialogfeld **Benannte Berechnung erstellen** folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="ad92c-131">In the **Create Named Calculations** dialog box, do the following:</span></span>

    -   <span data-ttu-id="ad92c-132">Geben Sie im Textfeld **Spaltenname** den Namen der neuen Spalte ein.</span><span class="sxs-lookup"><span data-stu-id="ad92c-132">In the **Column name** text box, type the name of the new column.</span></span>

    -   <span data-ttu-id="ad92c-133">Geben Sie im Textfeld **Beschreibung** eine Beschreibung für die neue Spalte ein.</span><span class="sxs-lookup"><span data-stu-id="ad92c-133">In the **Description** text box type a description for the new column.</span></span>

    -   <span data-ttu-id="ad92c-134">Geben Sie im Textfeld **Ausdruck** den Ausdruck ein, der den Inhalt der neuen Spalte ergibt, und verwenden Sie hierbei den SQL-Dialekt, der für den jeweiligen Datenanbieter geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="ad92c-134">In the **Expression** text box, type the expression that yields the content of the new column in the SQL dialect appropriate for the data provider.</span></span>

5.  <span data-ttu-id="ad92c-135">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ad92c-135">Click **OK**.</span></span>

     <span data-ttu-id="ad92c-136">Die Spalte mit der benannten Berechnung wird als letzte Spalte in der Tabelle für die Datenquellensicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ad92c-136">The named calculation column appears as the last column in the data source view table.</span></span> <span data-ttu-id="ad92c-137">Ein Rechnersymbol weist darauf hin, dass die Spalte eine benannte Berechnung enthält.</span><span class="sxs-lookup"><span data-stu-id="ad92c-137">A calculator symbol indicates that the column contains a named calculation.</span></span>

## <a name="delete-a-named-calculation"></a><span data-ttu-id="ad92c-138">Löschen einer benannten Berechnung</span><span class="sxs-lookup"><span data-stu-id="ad92c-138">Delete a Named Calculation</span></span>
 <span data-ttu-id="ad92c-139">Wenn Sie versuchen, eine benannte Berechnung zu löschen, wird eine Liste der im Projekt oder in der Datenbank definierten Objekte angezeigt, die durch den Löschvorgang ungültig werden.</span><span class="sxs-lookup"><span data-stu-id="ad92c-139">When you attempt to delete a named calculation, you are prompted with a list of the objects defined in the project or database that will be invalidated by the deletion.</span></span> <span data-ttu-id="ad92c-140">Überprüfen Sie die Liste sorgfältig vor dem Löschen der Berechnung.</span><span class="sxs-lookup"><span data-stu-id="ad92c-140">Review the list carefully before deleting the calculation.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad92c-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ad92c-141">See Also</span></span>
 [<span data-ttu-id="ad92c-142">Definieren von benannten Abfragen in einer Datenquellensicht &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ad92c-142">Define Named Queries in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-queries-in-a-data-source-view-analysis-services.md)


