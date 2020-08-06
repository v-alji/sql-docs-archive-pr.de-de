---
title: Ersetzen einer Tabelle oder einer benannten Abfrage in einer Datenquellen Sicht (Analysis Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- replacing tables
- data source views [Analysis Services], tables
- named queries [Analysis Services], replacing tables
- tables [Analysis Services], data source views
- partitions [Analysis Services], named queries
ms.assetid: 60c2a018-1299-4915-b60e-e73316524def
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2b5055de60ba757c9dcfa118e4e2c4748c6534e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619403"
---
# <a name="replace-a-table-or-a-named-query-in-a-data-source-view-analysis-services"></a><span data-ttu-id="57065-102">Ersetzen einer Tabelle oder einer benannten Abfrage in einer Datenquellensicht (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="57065-102">Replace a Table or a Named Query in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="57065-103">Im Datenquellensicht-Designer können Sie eine Tabelle, eine Sicht oder eine benannte Abfrage in einer Datenquellensicht durch eine andere Tabelle oder Sicht aus derselben oder einer anderen Datenquelle bzw. durch eine benannte Abfrage, die in der Datenquellensicht definiert wurde, ersetzen.</span><span class="sxs-lookup"><span data-stu-id="57065-103">In Data Source View Designer, you can replace a table, view, or named query in a data source view (DSV) with a different table or view from the same or a different data source, or with a named query defined in the DSV.</span></span> <span data-ttu-id="57065-104">Beim Ersetzen einer Tabelle bleiben die Verweise aller anderen Objekte einer Datenbank oder eines Projekts von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] auf diese Tabelle erhalten, da die Objekt-ID der Tabelle in der Datenquellensicht nicht geändert wird.</span><span class="sxs-lookup"><span data-stu-id="57065-104">When you replace a table, all other objects in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database or project that have references to the table continue to reference the table because the object ID for the table in the DSV does not change.</span></span> <span data-ttu-id="57065-105">Alle Beziehungen, die weiterhin relevant sind (basierend auf der Übereinstimmung des Namens und des Spaltentyps), werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="57065-105">Any relationships that are still relevant (based on name and column-type matching) are retained.</span></span> <span data-ttu-id="57065-106">Wenn Sie eine Tabelle löschen und anschließend eine Tabelle hinzufügen, gehen im Gegensatz dazu Verweise und Beziehungen verloren und müssen neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="57065-106">In contrast, if you delete and then add a table, references and relationships are lost and must be recreated.</span></span>  
  
 <span data-ttu-id="57065-107">Zum Ersetzen einer Tabelle durch eine andere Tabelle muss eine aktive Verbindung zur Datenquelle im Datenquellensicht-Designer im Projektmodus vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="57065-107">To replace a table with another table, you must have an active connection to the source data in Data Source View Designer in project mode.</span></span>  
  
 <span data-ttu-id="57065-108">Am häufigsten wird eine Tabelle in der Datenquellensicht durch eine andere Tabelle der Datenquelle ersetzt.</span><span class="sxs-lookup"><span data-stu-id="57065-108">You most frequently replace a table in the data source view with another table in the data source.</span></span> <span data-ttu-id="57065-109">Allerdings können Sie auch eine benannte Abfrage durch eine Tabelle ersetzen.</span><span class="sxs-lookup"><span data-stu-id="57065-109">However, you can also replace a named query with a table.</span></span> <span data-ttu-id="57065-110">Sie haben beispielsweise zuvor eine Tabelle durch eine benannte Abfrage ersetzt, und Sie möchten jetzt die Tabelle wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="57065-110">For example, you previously replaced a table with a named query, and now want to revert to a table.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="57065-111">Befolgen Sie beim Umbenennen einer Tabelle in einer Datenquelle die Schritte zum Ersetzen einer Tabelle, und geben Sie die umbenannte Tabelle als Quelle für die entsprechende Tabelle in der Datenquellensicht an, bevor Sie eine Datenquellensicht aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="57065-111">If you rename a table in a data source, follow the steps for replacing a table and specify the renamed table as the source of the corresponding table in the DSV before you refresh a DSV.</span></span> <span data-ttu-id="57065-112">Nach dem Ersetzen und Umbenennen werden die Tabelle sowie die Verweise und Beziehungen der Tabelle in der Datenquellensicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="57065-112">Completing the replacement and renaming process preserves the table, the table's references, and the table's relationships in the DSV.</span></span> <span data-ttu-id="57065-113">Andernfalls wird beim Aktualisieren der Datenquellensicht eine umbenannte Tabelle in der Datenquelle als gelöscht interpretiert.</span><span class="sxs-lookup"><span data-stu-id="57065-113">Otherwise, when you refresh the DSV, a renamed table in data source is interpreted as being deleted.</span></span> <span data-ttu-id="57065-114">Weitere Informationen finden Sie unter [Aktualisieren des Schemas in einer Datenquellensicht &#40;Analysis Services&#41;](refresh-the-schema-in-a-data-source-view-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="57065-114">For more information, see [Refresh the Schema in a Data Source View &#40;Analysis Services&#41;](refresh-the-schema-in-a-data-source-view-analysis-services.md).</span></span>  
  
##  <a name="replace-a-table-with-a-named-query"></a><a name="bkmk_nq"></a><span data-ttu-id="57065-115">Ersetzen einer Tabelle durch eine benannte Abfrage</span><span class="sxs-lookup"><span data-stu-id="57065-115">Replace a table with a named query</span></span>  
  
1.  <span data-ttu-id="57065-116">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das Projekt, oder stellen Sie eine Verbindung mit der Datenbank her, das bzw. die die Datenquellensicht enthält, in der Sie eine Tabelle oder benannte Abfrage ersetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="57065-116">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you want to replace a table or a named query.</span></span>  
  
2.  <span data-ttu-id="57065-117">Erweitern Sie im Projektmappen-Explorer den Ordner **Datenquellensichten** , und doppelklicken Sie anschließend auf die Datenquellensicht.</span><span class="sxs-lookup"><span data-stu-id="57065-117">In Solution Explorer, expand the **Data Source Views** folder, and then double-click the data source view.</span></span>  
  
3.  <span data-ttu-id="57065-118">Öffnen Sie das Dialogfeld **Benannte Abfrage erstellen** .</span><span class="sxs-lookup"><span data-stu-id="57065-118">Open the **Create Named Query** dialog box.</span></span> <span data-ttu-id="57065-119">Klicken Sie im Bereich **Tabellen** oder **Diagramm** mit der rechten Maustaste auf die Tabelle, die Sie ersetzen möchten, zeigen Sie auf **Tabelle ersetzen** , und klicken Sie dann auf **Durch neue benannte Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="57065-119">In either **Tables** or **Diagram** pane, right-click the table that you wish to replace, point to **Replace Table** and then click **With New Named Query**.</span></span>  
  
4.  <span data-ttu-id="57065-120">Definieren Sie im Dialogfeld **Benannte Abfrage erstellen** die benannte Abfrage, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="57065-120">In the **Create Named Query** dialog box, define the named query and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="57065-121">Speichern Sie die geänderte Datenquellensicht.</span><span class="sxs-lookup"><span data-stu-id="57065-121">Save the modified data source view.</span></span>  
  
## <a name="replace-a-table-or-named-query-with-a-table"></a><span data-ttu-id="57065-122">Ersetzen einer Tabelle oder benannten Abfrage durch eine Tabelle</span><span class="sxs-lookup"><span data-stu-id="57065-122">Replace a table or named query with a table</span></span>  
  
1.  <span data-ttu-id="57065-123">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das Projekt, oder stellen Sie eine Verbindung mit der Datenbank her, das bzw. die die Datenquellensicht enthält, in der Sie eine Tabelle oder benannte Abfrage ersetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="57065-123">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you want to replace a table or a named query.</span></span>  
  
2.  <span data-ttu-id="57065-124">Erweitern Sie im Projektmappen-Explorer den Ordner **Datenquellensichten** , und doppelklicken Sie anschließend auf die Datenquellensicht.</span><span class="sxs-lookup"><span data-stu-id="57065-124">In Solution Explorer, expand the **Data Source Views** folder, and then double-click the data source view.</span></span>  
  
3.  <span data-ttu-id="57065-125">Öffnen Sie das Dialogfeld **Tabelle durch eine andere Tabelle ersetzen** .</span><span class="sxs-lookup"><span data-stu-id="57065-125">Open the **Replace Table with Other Table** dialog box.</span></span> <span data-ttu-id="57065-126">Klicken Sie im Bereich **Tabellen** oder **Diagramm** mit der rechten Maustaste auf die Tabelle oder benannte Abfrage, die Sie ersetzen möchten, zeigen Sie auf **Tabelle ersetzen** , und klicken Sie dann auf **Durch andere Tabelle**.</span><span class="sxs-lookup"><span data-stu-id="57065-126">In either **Tables** or **Diagram** pane, right-click the table or named query that you wish to replace, point to **Replace Table** and then click **With Other Table**.</span></span>  
  
4.  <span data-ttu-id="57065-127">Führen Sie im Dialogfeld **Tabelle durch eine andere Tabelle ersetzen** folgende Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="57065-127">In the **Replace Table with Other Table** dialog box:</span></span>  
  
    1.  <span data-ttu-id="57065-128">Wählen Sie im Dropdown-Listenfeld **Datenquelle** die gewünschte Datenquelle aus.</span><span class="sxs-lookup"><span data-stu-id="57065-128">In the **DataSource** drop-down list box, select the desired data source</span></span>  
  
    2.  <span data-ttu-id="57065-129">Wählen Sie die Tabelle aus, durch die Sie die Tabelle oder benannte Abfrage ersetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="57065-129">Select the table with which you wish to replace the table or named query</span></span>  
  
5.  <span data-ttu-id="57065-130">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="57065-130">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="57065-131">Speichern Sie die geänderte Datenquellensicht.</span><span class="sxs-lookup"><span data-stu-id="57065-131">Save the modified data source view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57065-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="57065-132">See Also</span></span>  
 [<span data-ttu-id="57065-133">Datenquellsichten in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="57065-133">Data Source Views in Multidimensional Models</span></span>](data-source-views-in-multidimensional-models.md)  
  
  
