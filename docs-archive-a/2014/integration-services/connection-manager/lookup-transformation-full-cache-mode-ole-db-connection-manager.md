---
title: Implementieren einer Such Transformation im voll Cache Modus mithilfe des OLE DB-Verbindungs-Managers | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Lookup transformation [Integration Services]
ms.assetid: c4150e1b-bdff-4f7a-af4c-3401c34def83
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f77a753dd71bc487d57492371906fc48bc114357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621143"
---
# <a name="implement-a-lookup-transformation-in-full-cache-mode-using-the-ole-db-connection-manager"></a><span data-ttu-id="cc85a-102">Implementieren einer Suchtransformation im Vollcachemodus mit dem OLE DB-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="cc85a-102">Implement a Lookup Transformation in Full Cache Mode Using the OLE DB Connection Manager</span></span>
  <span data-ttu-id="cc85a-103">Sie können die Transformation für Suche so konfigurieren, dass der Vollcachemodus und ein OLE DB-Verbindungs-Manager verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cc85a-103">You can configure the Lookup transformation to use full cache mode and an OLE DB connection manager.</span></span> <span data-ttu-id="cc85a-104">Im Vollcachemodus wird das Verweisdataset in den Cache geladen, bevor die Transformation für Suche ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cc85a-104">In the full cache mode, the reference dataset is loaded into cache before the Lookup transformation runs.</span></span>  
  
 <span data-ttu-id="cc85a-105">Die Transformation für Suche führt Suchvorgänge aus, indem Daten in Eingabespalten aus einer verbundenen Datenquelle mit Spalten in einem Verweisdataset verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="cc85a-105">The Lookup transformation performs lookups by joining data in input columns from a connected data source with columns in a reference dataset.</span></span> <span data-ttu-id="cc85a-106">Weitere Informationen finden Sie unter [Lookup Transformation](../data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="cc85a-106">For more information, see [Lookup Transformation](../data-flow/transformations/lookup-transformation.md).</span></span>  
  
 <span data-ttu-id="cc85a-107">Wenn Sie die Transformation für Suche für einen OLE DB-Verbindungs-Manager konfigurieren, wählen Sie eine Tabelle, Sicht oder SQL-Abfrage zum Generieren des Verweisdatasets aus.</span><span class="sxs-lookup"><span data-stu-id="cc85a-107">When you configure the Lookup transformation to use an OLE DB connection manager, you select a table, view, or SQL query to generate the reference dataset.</span></span>  
  
### <a name="to-implement-a-lookup-transformation-in-full-cache-mode-by-using-ole-db-connection-manager"></a><span data-ttu-id="cc85a-108">So implementieren Sie eine Transformation für Suche im Vollcachemodus mit dem OLE DB-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="cc85a-108">To implement a Lookup transformation in full cache mode by using OLE DB connection manager</span></span>  
  
1.  <span data-ttu-id="cc85a-109">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Projekt mit dem gewünschten Paket, und doppelklicken Sie dann im Projektmappen-Explorer auf das Paket.</span><span class="sxs-lookup"><span data-stu-id="cc85a-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want, and then double-click the package in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="cc85a-110">Ziehen Sie auf der Registerkarte **Datenfluss** die Transformation für Suche aus der **Toolbox**auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="cc85a-110">On the **Data Flow** tab, from the **Toolbox**, drag the Lookup transformation to the design surface.</span></span>  
  
3.  <span data-ttu-id="cc85a-111">Verbinden Sie die Suchtransformation mit dem Datenfluss, indem Sie einen Konnektor von einer Quelle oder einer vorherigen Transformation auf die Suchtransformation ziehen.</span><span class="sxs-lookup"><span data-stu-id="cc85a-111">Connect the Lookup transformation to the data flow by dragging a connector from a source or a previous transformation to the Lookup transformation.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cc85a-112">Eine Suchtransformation erzeugt möglicherweise einen Fehler, wenn sie sich mit einem Flatfile verbindet, das ein leeres Datenfeld enthält.</span><span class="sxs-lookup"><span data-stu-id="cc85a-112">A Lookup transformation might not validate if that transformation connects to a flat file that contains an empty date field.</span></span> <span data-ttu-id="cc85a-113">Die Gültigkeit der Transformation hängt davon ab, ob der Verbindungs-Manager für das Flatfile so konfiguriert wurde, dass NULL-Werte beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="cc85a-113">Whether the transformation validates depends on whether the connection manager for the flat file has been configured to retain null values.</span></span> <span data-ttu-id="cc85a-114">Um sicherzustellen, dass die Suchtransformation gültig ist, wählen Sie im **Quelleneditor für Flatfiles**auf der **Seite Verbindungs-Manager**die Option **NULL-Werte aus der Quelle als NULL-Werte im Datenfluss beibehalten** .</span><span class="sxs-lookup"><span data-stu-id="cc85a-114">To ensure that the Lookup transformation validates, in the **Flat File Source Editor**, on the **Connection Manager Page**, select the **Retain null values from the source as null values in the data flow** option.</span></span>  
  
4.  <span data-ttu-id="cc85a-115">Doppelklicken Sie auf die Quelle oder die vorherige Transformation, um die Komponente zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="cc85a-115">Double-click the source or previous transformation to configure the component.</span></span>  
  
5.  <span data-ttu-id="cc85a-116">Doppelklicken Sie auf die Transformation für Suche, und wählen Sie dann im **Transformations-Editor für Suche**auf der Seite **Allgemein** die Option **Vollcache**aus.</span><span class="sxs-lookup"><span data-stu-id="cc85a-116">Double-click the Lookup transformation, and then in the **Lookup Transformation Editor**, on the **General** page, select **Full cache**.</span></span>  
  
6.  <span data-ttu-id="cc85a-117">Wählen Sie im Bereich **Verbindungstyp** **OLE DB-Verbindungs-Manager**aus.</span><span class="sxs-lookup"><span data-stu-id="cc85a-117">In the **Connection type** area, select **OLE DB connection manager**.</span></span>  
  
7.  <span data-ttu-id="cc85a-118">Wählen Sie in der Liste **Angeben, wie Zeilen ohne übereinstimmende Einträge behandelt werden sollen** eine Fehlerbehandlungsoption für Zeilen ohne übereinstimmende Einträge aus.</span><span class="sxs-lookup"><span data-stu-id="cc85a-118">In the **Specify how to handle rows with no matching entries** list, select an error handling option for rows without matching entries.</span></span>  
  
8.  <span data-ttu-id="cc85a-119">Wählen Sie auf der Seite Verbindung einen Verbindungs-Manager aus der Liste **OLE DB-Verbindungs-Manager** aus, oder klicken Sie auf **Neu** , um einen neuen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cc85a-119">On the Connection page, select a connection manager from the **OLE DB connection manager** list or click **New** to create a new connection manager.</span></span> <span data-ttu-id="cc85a-120">Weitere Informationen finden Sie unter [OLE DB Connection Manager](ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="cc85a-120">For more information, see [OLE DB Connection Manager](ole-db-connection-manager.md).</span></span>  
  
9. <span data-ttu-id="cc85a-121">Führen Sie eine der folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="cc85a-121">Do one of the following tasks:</span></span>  
  
    -   <span data-ttu-id="cc85a-122">Klicken Sie auf **Tabelle oder Sicht verwenden**, und wählen Sie dann eine Tabelle oder eine Sicht aus, oder klicken Sie auf **Neu** , um eine Tabelle oder Sicht zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cc85a-122">Click **Use a table or a view**, and then either select a table or view, or click **New** to create a table or view.</span></span>  
  
         <span data-ttu-id="cc85a-123">Oder</span><span class="sxs-lookup"><span data-stu-id="cc85a-123">-or-</span></span>  
  
    -   <span data-ttu-id="cc85a-124">Klicken Sie auf **Ergebnisse einer SQL-Abfrage verwenden**, und erstellen Sie im Fenster **SQL-Befehl** eine Abfrage, oder klicken Sie auf **Abfrage erstellen** , um eine Abfrage mithilfe der grafischen Tools des **Abfrage-Generators** zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cc85a-124">Click **Use results of an SQL query**, and then build a query in the **SQL Command** window, or click **Build Query** to build a query by using the graphical tools that the **Query Builder** provides.</span></span>  
  
         <span data-ttu-id="cc85a-125">Oder</span><span class="sxs-lookup"><span data-stu-id="cc85a-125">-or-</span></span>  
  
    -   <span data-ttu-id="cc85a-126">Klicken Sie alternativ auf **Durchsuchen** , um eine SQL-Anweisung aus einer Datei zu importieren.</span><span class="sxs-lookup"><span data-stu-id="cc85a-126">Alternatively, click **Browse** to import an SQL statement from a file.</span></span>  
  
     <span data-ttu-id="cc85a-127">Um die SQL-Abfrage zu überprüfen, klicken Sie auf **Abfrage analysieren**.</span><span class="sxs-lookup"><span data-stu-id="cc85a-127">To validate the SQL query, click **Parse Query**.</span></span>  
  
     <span data-ttu-id="cc85a-128">Um ein Beispiel der Daten anzuzeigen, klicken Sie auf **Vorschau**.</span><span class="sxs-lookup"><span data-stu-id="cc85a-128">To view a sample of the data, click **Preview**.</span></span>  
  
10. <span data-ttu-id="cc85a-129">Klicken Sie auf die Seite **Spalten** , und ziehen Sie mindestens eine Spalte aus der Liste **Verfügbare Eingabespalten** in eine Spalte in der Liste **Verfügbare Suchspalten** .</span><span class="sxs-lookup"><span data-stu-id="cc85a-129">Click the **Columns** page, and then from the **Available Input Columns** list, drag at least one column to a column in the **Available Lookup Column** list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cc85a-130">Die Transformation für Suche ordnet automatisch Spalten mit dem gleichen Namen und dem gleichen Datentyp zu.</span><span class="sxs-lookup"><span data-stu-id="cc85a-130">The Lookup transformation automatically maps columns that have the same name and the same data type.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cc85a-131">Die Spalten müssen übereinstimmende Datentypen aufweisen, damit sie zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="cc85a-131">Columns must have matching data types to be mapped.</span></span> <span data-ttu-id="cc85a-132">Weitere Informationen finden Sie unter [Integration Services Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="cc85a-132">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
11. <span data-ttu-id="cc85a-133">Schließen Sie Suchspalten in die Ausgabe ein, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="cc85a-133">Include lookup columns in the output by doing the following tasks:</span></span>  
  
    1.  <span data-ttu-id="cc85a-134">In der Liste **Verfügbare Suchspalten** .</span><span class="sxs-lookup"><span data-stu-id="cc85a-134">In the **Available Lookup Columns** list.</span></span> <span data-ttu-id="cc85a-135">wählen Sie Spalten aus.</span><span class="sxs-lookup"><span data-stu-id="cc85a-135">select columns.</span></span>  
  
    2.  <span data-ttu-id="cc85a-136">Geben Sie in der Liste **Suchvorgang** an, ob die Werte aus den Suchspalten Werte in der Eingabespalte ersetzen oder ob sie in eine neue Spalte geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="cc85a-136">In **Lookup Operation** list, specify whether the values from the lookup columns replace values in the input column or are written to a new column.</span></span>  
  
12. <span data-ttu-id="cc85a-137">Um die Fehlerausgabe zu konfigurieren, klicken Sie auf die Seite **Fehlerausgabe** , und legen Sie die Fehlerbehandlungsoptionen fest.</span><span class="sxs-lookup"><span data-stu-id="cc85a-137">To configure the error output, click the **Error Output** page and set the error handling options.</span></span> <span data-ttu-id="cc85a-138">Weitere Informationen finden Sie unter [Transformations-Editor für Suche &#40;Seite Fehlerausgabe&#41;](../lookup-transformation-editor-error-output-page.md).</span><span class="sxs-lookup"><span data-stu-id="cc85a-138">For more information, see [Lookup Transformation Editor &#40;Error Output Page&#41;](../lookup-transformation-editor-error-output-page.md).</span></span>  
  
13. <span data-ttu-id="cc85a-139">Klicken Sie auf **OK** , um die Änderungen an der Suchtransformation zu speichern, und führen Sie dann das Paket aus.</span><span class="sxs-lookup"><span data-stu-id="cc85a-139">Click **OK** to save your changes to the Lookup transformation, and then run the package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc85a-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cc85a-140">See Also</span></span>  
 <span data-ttu-id="cc85a-141">[Implementieren einer Suchtransformation im Vollcachemodus mit dem Cacheverbindungs-Manager](lookup-transformation-full-cache-mode-ole-db-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="cc85a-141">[Implement a Lookup Transformation in Full Cache Mode Using the Cache Connection Manager](lookup-transformation-full-cache-mode-ole-db-connection-manager.md) </span></span>  
 <span data-ttu-id="cc85a-142">[Implementieren einer Suche im Modus „Kein Cache“ oder „Teilcache“](../data-flow/transformations/implement-a-lookup-in-no-cache-or-partial-cache-mode.md) </span><span class="sxs-lookup"><span data-stu-id="cc85a-142">[Implement a Lookup in No Cache or Partial Cache Mode](../data-flow/transformations/implement-a-lookup-in-no-cache-or-partial-cache-mode.md) </span></span>  
 [<span data-ttu-id="cc85a-143">SQL Server Integration Services-Transformationen</span><span class="sxs-lookup"><span data-stu-id="cc85a-143">Integration Services Transformations</span></span>](../data-flow/transformations/integration-services-transformations.md)  
  
  
