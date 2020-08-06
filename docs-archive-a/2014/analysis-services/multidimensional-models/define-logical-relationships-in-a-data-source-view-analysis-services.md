---
title: Definieren von logischen Beziehungen in einer Datenquellen Sicht (Analysis Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- adding relationships
- relationships [Analysis Services], data source views
- data source views [Analysis Services], relationships
ms.assetid: a20d6dae-e769-4131-8a59-7ef56f174220
author: minewiskan
ms.author: owend
ms.openlocfilehash: c46c2b360a4528aeb0eb88348d0d1242b22d8ef5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618384"
---
# <a name="define-logical-relationships-in-a-data-source-view-analysis-services"></a><span data-ttu-id="c6d84-102">Definieren von logischen Beziehungen in einer Datenquellensicht (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="c6d84-102">Define Logical Relationships in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="c6d84-103">Im Datenquellensicht-Assistenten und im Datenquellensicht-Designer werden automatisch Beziehungen zwischen Tabellen definiert, die einer Datenquellensicht (Data Source View, DSV) hinzugefügt werden. Das Definieren der Beziehungen erfolgt auf Grundlage der Beziehungen in der zugrunde liegenden Datenbank oder auf Grundlage der von Ihnen angegebenen Namensübereinstimmungskriterien.</span><span class="sxs-lookup"><span data-stu-id="c6d84-103">The Data Source View Wizard and Data Source View Designer automatically define relationships between tables added to a data source view (DSV) based on underlying database relationships or name matching criteria you specify.</span></span>  
  
 <span data-ttu-id="c6d84-104">Wenn Sie Daten aus mehreren Datenquellen verwenden, müssen Sie zur Ergänzung der automatisch definierten Beziehungen in der DSV u. U. logische Beziehungen manuell definieren.</span><span class="sxs-lookup"><span data-stu-id="c6d84-104">In cases where you are working with data from multiple data sources, you may need to manually define logical relationships in the DSV to supplement those relationships that are defined automatically.</span></span> <span data-ttu-id="c6d84-105">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] sind Beziehungen erforderlich, um Fakten- und Dimensionstabellen zu identifizieren, Abfragen zum Abrufen von Daten und Metadaten aus den zugrunde liegenden Datenquellen zu erstellen und die erweiterten Business Intelligence-Funktionen nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="c6d84-105">Relationships are required in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to identify fact and dimension tables, to construct queries for retrieving data and metadata from underlying data sources, and to take advantage of advanced business intelligence features.</span></span>  
  
 <span data-ttu-id="c6d84-106">Sie können die folgenden Arten von Beziehungen im Datenquellensicht-Designer definieren:</span><span class="sxs-lookup"><span data-stu-id="c6d84-106">You can define the following types of relationships in Data Source View Designer:</span></span>  
  
-   <span data-ttu-id="c6d84-107">Eine Beziehung von einer Tabelle zu einer anderen Tabelle in derselben Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="c6d84-107">A relationship from one table to another table in the same data source.</span></span>  
  
-   <span data-ttu-id="c6d84-108">Eine Beziehung von einer Tabelle zu sich selbst, wie in einer Über-/Unterordnungsbeziehung.</span><span class="sxs-lookup"><span data-stu-id="c6d84-108">A relationship from one table to itself, as in a parent-child relationship.</span></span>  
  
-   <span data-ttu-id="c6d84-109">Eine Beziehung von einer Tabelle in einer Datenquelle zu einer anderen Tabelle in einer anderen Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="c6d84-109">A relationship from one table in a data source to another table in a different data source.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c6d84-110">Die in einer DSV definierten Beziehungen sind logischer Natur und geben möglicherweise nicht die in der zugrunde liegenden Datenquelle definierten tatsächlichen Beziehungen wieder.</span><span class="sxs-lookup"><span data-stu-id="c6d84-110">The relationships defined in a DSV are logical and may not reflect the actual relationships defined in the underlying data source.</span></span> <span data-ttu-id="c6d84-111">Sie können im Datenquellensicht-Designer Beziehungen erstellen, die es in der zugrunde liegenden Datenquelle nicht gibt, und Beziehungen entfernen, die vom Datenquellensicht-Designer aus vorhandenen Fremdschlüsselbeziehungen in der zugrunde liegenden Datenquelle erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="c6d84-111">You can create relationships in Data Source View Designer that do not exist in the underlying data source, and remove relationships created by Data Source View Designer from existing foreign key relationships in the underlying data source.</span></span>  
  
 <span data-ttu-id="c6d84-112">Beziehungen sind zielgerichtet.</span><span class="sxs-lookup"><span data-stu-id="c6d84-112">Relationships are directed.</span></span> <span data-ttu-id="c6d84-113">Jedem Wert in der Quellspalte ist ein entsprechender Wert in der Zielspalte zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="c6d84-113">For every value in the source column, there is a corresponding value in the destination column.</span></span> <span data-ttu-id="c6d84-114">In einem Datenquellensicht-Diagramm, wie z. B. den im Bereich **Diagramm** angezeigten Diagrammen, weist ein Pfeil in der Zeile zwischen zwei Tabellen auf die Richtung der Beziehung hin.</span><span class="sxs-lookup"><span data-stu-id="c6d84-114">In a data source view diagram, such as the diagrams displayed in the **Diagram** pane, an arrow on the line between two tables indicates the direction of the relationship.</span></span>  
  
 <span data-ttu-id="c6d84-115">Dieses Thema enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="c6d84-115">This topic includes the following sections:</span></span>  
  
 [<span data-ttu-id="c6d84-116">So fügen Sie eine Beziehung zwischen Tabellen, benannten Abfragen oder Sichten hinzu</span><span class="sxs-lookup"><span data-stu-id="c6d84-116">To add a relationship between tables, named queries, or views</span></span>](#bkmk_addRel)  
  
 [<span data-ttu-id="c6d84-117">So können Sie eine Beziehung im Diagrammbereich anzeigen oder ändern</span><span class="sxs-lookup"><span data-stu-id="c6d84-117">To view or modify a relationship in the Diagram pane</span></span>](#bkmk_diagrampane)  
  
 [<span data-ttu-id="c6d84-118">So können Sie eine Beziehung im Bereich "Tabellen" anzeigen oder ändern</span><span class="sxs-lookup"><span data-stu-id="c6d84-118">To view or modify a relationship in the Tables pane</span></span>](#bkmk_tablespane)  
  
##  <a name="to-add-a-relationship-between-tables-named-queries-or-views"></a><a name="bkmk_addRel"></a><span data-ttu-id="c6d84-119">So fügen Sie eine Beziehung zwischen Tabellen, benannten Abfragen oder Sichten hinzu</span><span class="sxs-lookup"><span data-stu-id="c6d84-119">To add a relationship between tables, named queries, or views</span></span>  
  
1.  <span data-ttu-id="c6d84-120">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das Projekt, oder stellen Sie eine Verbindung mit der Datenbank her, das bzw. die die Datenquellensicht enthält, in der Sie eine logische Beziehung hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="c6d84-120">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you wish to add a logical relationship.</span></span>  
  
2.  <span data-ttu-id="c6d84-121">Erweitern Sie im Projektmappen-Explorer den Ordner **Datenquellensichten** , und doppelklicken Sie anschließend auf die Datenquellensicht, um sie im **Datenquellensicht-Designer**zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c6d84-121">In Solution Explorer, expand the **Data Source Views** folder, then double-click the data source view to open it in **Data Source View Designer**.</span></span>  
  
3.  <span data-ttu-id="c6d84-122">Klicken Sie im Bereich **Tabellen** mit der rechten Maustaste auf die Tabelle, benannte Abfrage oder Sicht, der Sie eine Beziehung hinzufügen möchten, und klicken Sie anschließend auf **Neue Beziehung**.</span><span class="sxs-lookup"><span data-stu-id="c6d84-122">Right-click the table, named query or view to which you want to add a relationship in either the **Tables** pane and then click **New Relationship**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c6d84-123">Zum Suchen nach einer Tabelle, Sicht oder benannten Abfrage können Sie die Option **Tabelle suchen** verwenden, indem Sie entweder auf das Menü **Datenquellensicht** klicken oder mit der rechten Maustaste auf einen offenen Bereich im Bereich **Tabelle** oder **Diagramm** klicken.</span><span class="sxs-lookup"><span data-stu-id="c6d84-123">To locate a table, view or named query, you can use the **Find Table** option by either clicking the **Data Source View** menu or right-clicking in an open area of the **Tables** or **Diagram** panes.</span></span>  
  
4.  <span data-ttu-id="c6d84-124">Führen Sie im Dialogfeld **Beziehung angeben** folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c6d84-124">In the **Specify Relationship** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="c6d84-125">Wählen Sie die geeignete Tabelle, benannte Abfrage oder Sicht in der Liste **Quelltabelle (Fremdschlüsseltabelle)** aus.</span><span class="sxs-lookup"><span data-stu-id="c6d84-125">Select the appropriate table, named query, or view in the **Source (foreign key) table** list.</span></span>  
  
    2.  <span data-ttu-id="c6d84-126">Wählen Sie die geeignete Tabelle, benannte Abfrage oder Sicht in den Listen **Zieltabelle (Primärschlüsseltabelle)** aus.</span><span class="sxs-lookup"><span data-stu-id="c6d84-126">Select the appropriate table, named query, or view in the **Destination (primary key) table** lists.</span></span>  
  
    3.  <span data-ttu-id="c6d84-127">Wählen Sie in den Listen **Quellspalten** und **Zielspalten** Spalten aus, um eine Beziehung zwischen den beiden Tabellen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c6d84-127">Select columns from the **Source Columns** and **Destination Columns** lists to create a relationship between the two tables.</span></span>  
  
         <span data-ttu-id="c6d84-128">Wenn in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] durch das stichprobenartige Untersuchen der Daten in der zugrunde liegenden Tabelle, Sicht oder benannten Abfrage erkannt wird, dass Sie die Beziehung in der falschen Richtung (vom Primärschlüssel zum Fremdschlüssel anstatt vom Fremdschlüssel zum Primärschlüssel) definiert haben, werden Sie aufgefordert, die Richtung umzukehren.</span><span class="sxs-lookup"><span data-stu-id="c6d84-128">If [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] detects, by sampling the data in the underlying table, view, or named query, that you have defined the relationship in the wrong direction (from the primary key to the foreign key rather than from the foreign key to the primary key), you will be prompted to reverse the order.</span></span> <span data-ttu-id="c6d84-129">Sie können die Richtung schnell umkehren, indem Sie auf **Umkehren**klicken.</span><span class="sxs-lookup"><span data-stu-id="c6d84-129">To quickly reverse the order, click **Reverse**.</span></span>  
  
         <span data-ttu-id="c6d84-130">Wenn in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] erkannt wird, dass bereits eine Beziehung für die ausgewählten Spalten vorhanden ist, wird eine entsprechende Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c6d84-130">If [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] detects that a relationship already exists for the columns you have selected, you will be prompted.</span></span> <span data-ttu-id="c6d84-131">Es ist nicht möglich, doppelte Beziehungen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="c6d84-131">You cannot define duplicate relationships.</span></span>  
  
    4.  <span data-ttu-id="c6d84-132">Geben Sie optional im Feld **Beschreibung** eine Beschreibung für die Beziehung ein.</span><span class="sxs-lookup"><span data-stu-id="c6d84-132">Optionally, in the **Description** box, type a description for the relationship.</span></span>  
  
##  <a name="to-view-or-modify-a-relationship-in-the-diagram-pane"></a><a name="bkmk_diagrampane"></a> <span data-ttu-id="c6d84-133">So können Sie eine Beziehung im Bereich "Diagramm" anzeigen oder ändern</span><span class="sxs-lookup"><span data-stu-id="c6d84-133">To view or modify a relationship in the Diagram pane</span></span>  
  
-   <span data-ttu-id="c6d84-134">Klicken Sie im Bereich **Diagramm** im **Datenquellensicht-Designer**mit der rechten Maustaste auf die Beziehung, die Sie anzeigen möchten, und klicken Sie auf **Beziehung bearbeiten** (oder doppelklicken Sie einfach auf den Beziehungspfeil).</span><span class="sxs-lookup"><span data-stu-id="c6d84-134">In the **Diagram** pane in **Data Source View Designer**, right-click the relationship that you want to view and click **Edit Relationship** (or simply double-click the relationship arrow).</span></span>  <span data-ttu-id="c6d84-135">Verwenden Sie das Dialogfeld **Beziehung bearbeiten** , um die Beziehung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c6d84-135">Use the **Edit Relationship** dialog box to modify the relationship.</span></span>  
  
##  <a name="to-view-or-modify-a-relationship-in-the-tables-pane"></a><a name="bkmk_tablespane"></a> <span data-ttu-id="c6d84-136">So können Sie eine Beziehung im Bereich "Tabellen" anzeigen oder ändern</span><span class="sxs-lookup"><span data-stu-id="c6d84-136">To view or modify a relationship in the Tables pane</span></span>  
  
1.  <span data-ttu-id="c6d84-137">Suchen und erweitern Sie im Bereich **Tabelle** im **Datenquellensicht-Designer**die Tabelle, Sicht oder benannte Abfrage, die die Beziehung enthält, die Sie anzeigen oder ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="c6d84-137">In the **Tables** pane in **Data Source View Designer**, locate and then expand the table, view or named query containing the relationship that you wish to view or modify.</span></span>  
  
2.  <span data-ttu-id="c6d84-138">Erweitern Sie den Ordner **Beziehungen** .</span><span class="sxs-lookup"><span data-stu-id="c6d84-138">Expand the **Relationships** folder.</span></span>  <span data-ttu-id="c6d84-139">Die Beziehungen zwischen der ausgewählten Tabelle, Sicht oder benannten Abfrage und anderen Tabellen, Sichten und benannten Abfragen werden zusammen mit der Beziehungsspalte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c6d84-139">The relationships between the selected table, view or named query and other tables, views and named queries appear with the relationship column listed.</span></span>  
  
3.  <span data-ttu-id="c6d84-140">Klicken Sie mit der rechten Maustaste auf die zu ändernde Beziehung, und klicken Sie anschließend auf **Beziehung bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="c6d84-140">Right-click the relationship you want to modify, and then click **Edit Relationship**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6d84-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c6d84-141">See Also</span></span>  
 [<span data-ttu-id="c6d84-142">Datenquellsichten in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="c6d84-142">Data Source Views in Multidimensional Models</span></span>](data-source-views-in-multidimensional-models.md)  
  
  
