---
title: Identifizieren ähnlicher Datenzeilen mithilfe der Transformation für Fuzzygruppierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Fuzzy Grouping transformation
- match similar data [Integration Services]
- similar data rows [Integration Services]
- fuzzy matches
ms.assetid: ffcb41a6-e23d-49ea-8c32-ac980e3dc495
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4e6d49548c211b38a35d6f5f7efc3d50fec93588
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621105"
---
# <a name="identify-similar-data-rows-by-using-the-fuzzy-grouping-transformation"></a><span data-ttu-id="1acb9-102">Identifizieren ähnlicher Datenzeilen mithilfe der Transformation für Fuzzygruppierung</span><span class="sxs-lookup"><span data-stu-id="1acb9-102">Identify Similar Data Rows by Using the Fuzzy Grouping Transformation</span></span>
  <span data-ttu-id="1acb9-103">Das Paket muss bereits mindestens einen Datenflusstask und eine Quelle enthalten, damit Sie eine Transformation für Fuzzygruppierung hinzufügen und konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="1acb9-103">To add and configure a Fuzzy Grouping transformation, the package must already include at least one Data Flow task and a source.</span></span>  
  
### <a name="to-implement-fuzzy-grouping-transformation-in-a-data-flow"></a><span data-ttu-id="1acb9-104">So implementieren Sie eine Transformation für Fuzzygruppierung in einem Datenfluss</span><span class="sxs-lookup"><span data-stu-id="1acb9-104">To implement Fuzzy Grouping transformation in a data flow</span></span>  
  
1.  <span data-ttu-id="1acb9-105">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="1acb9-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="1acb9-106">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="1acb9-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="1acb9-107">Klicken Sie auf die Registerkarte **Datenfluss** , und ziehen Sie dann aus dem Fenster **Toolbox**die Transformation für Fuzzygruppierung auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="1acb9-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Fuzzy Grouping transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="1acb9-108">Verbinden Sie die Transformation für Fuzzygruppierung mit dem Datenfluss, indem Sie den Konnektor von der Datenquelle oder einer vorherigen Transformation auf die Transformation für Fuzzygruppierung ziehen.</span><span class="sxs-lookup"><span data-stu-id="1acb9-108">Connect the Fuzzy Grouping transformation to the data flow by dragging the connector from the data source or a previous transformation to the Fuzzy Grouping transformation.</span></span>  
  
5.  <span data-ttu-id="1acb9-109">Doppelklicken Sie auf die Transformation für Fuzzygruppierung.</span><span class="sxs-lookup"><span data-stu-id="1acb9-109">Double-click the Fuzzy Grouping transformation.</span></span>  
  
6.  <span data-ttu-id="1acb9-110">Wählen Sie im Dialogfeld **Transformations-Editor für Fuzzygruppierung** auf der Registerkarte **Verbindungs-Manager** einen OLE DB-Verbindungs-Manager aus, der eine Verbindung mit einer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Datenbank herstellt.</span><span class="sxs-lookup"><span data-stu-id="1acb9-110">In the **Fuzzy Grouping Transformation Editor** dialog box, on the **Connection Manager** tab, select an OLE DB connection manager that connects to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1acb9-111">Für die Transformation muss eine Verbindung mit einer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Datenbank vorhanden sein, damit temporäre Tabellen und Indizes erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="1acb9-111">The transformation requires a connection to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database to create temporary tables and indexes.</span></span>  
  
7.  <span data-ttu-id="1acb9-112">Klicken Sie auf die Registerkarte **Spalten** , und aktivieren Sie in der Liste **Verfügbare Eingabespalten** die Kontrollkästchen der Eingabespalten, die zum Identifizieren ähnlicher Zeilen im Dataset verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1acb9-112">Click the **Columns** tab and, in the **Available Input Columns** list, select the check box of the input columns to use to identify similar rows in the dataset.</span></span>  
  
8.  <span data-ttu-id="1acb9-113">Aktivieren Sie das Kontrollkästchen in der **Pass-Through** -Spalte, um die Eingabespalten für das Pass-Through an die Transformationsausgabe zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="1acb9-113">Select the check box in the **Pass Through** column to identify the input columns to pass through to the transformation output.</span></span> <span data-ttu-id="1acb9-114">Pass-Through-Spalten werden nicht in die Identifizierung doppelter Zeilen eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="1acb9-114">Pass-through columns are not included in the process of identification of duplicate rows.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1acb9-115">Eingabespalten, die zum Gruppieren verwendet werden, werden automatisch als Pass-Through-Spalten ausgewählt. Die Auswahl dieser Spalten kann nicht aufgehoben werden, während sie zum Gruppieren verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1acb9-115">Input columns that are used for grouping are automatically selected as pass-through columns, and they cannot be unselected while used for grouping.</span></span>  
  
9. <span data-ttu-id="1acb9-116">Aktualisieren Sie optional die Namen von Ausgabespalten in der **Ausgabealias** -Spalte.</span><span class="sxs-lookup"><span data-stu-id="1acb9-116">Optionally, update the names of output columns in the **Output Alias** column.</span></span>  
  
10. <span data-ttu-id="1acb9-117">Aktualisieren Sie optional die Namen von bereinigten Spalten in der **Gruppenausgabealias** -Spalte.</span><span class="sxs-lookup"><span data-stu-id="1acb9-117">Optionally, update the names of cleaned columns in the **Group OutputAlias** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1acb9-118">Die Standardnamen von Spalten sind die Namen der Eingabespalten mit dem Suffix "_clean".</span><span class="sxs-lookup"><span data-stu-id="1acb9-118">The default names of columns are the names of the input columns with a "_clean" suffix.</span></span>  
  
11. <span data-ttu-id="1acb9-119">Aktualisieren Sie optional den zu verwendenden Übereinstimmungstyp in der **Übereinstimmungstyp** -Spalte.</span><span class="sxs-lookup"><span data-stu-id="1acb9-119">Optionally, update the type of match to use in the **Match Type** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1acb9-120">Mindestens eine Spalte muss die Fuzzyübereinstimmung verwenden.</span><span class="sxs-lookup"><span data-stu-id="1acb9-120">At least one column must use fuzzy matching.</span></span>  
  
12. <span data-ttu-id="1acb9-121">Geben Sie die minimale Ähnlichkeit von Spalten in der **Minimale Ähnlichkeit** -Spalte an.</span><span class="sxs-lookup"><span data-stu-id="1acb9-121">Specify the minimum similarity level columns in the **Minimum Similarity** column.</span></span> <span data-ttu-id="1acb9-122">Der Wert muss zwischen 0 und 1 liegen.</span><span class="sxs-lookup"><span data-stu-id="1acb9-122">The value must be between 0 and 1.</span></span> <span data-ttu-id="1acb9-123">Je näher der Wert an 1 liegt, desto ähnlicher müssen die Werte in den Eingabespalten sein, um eine Gruppe zu bilden.</span><span class="sxs-lookup"><span data-stu-id="1acb9-123">The closer the value is to 1, the more similar the values in the input columns must be to form a group.</span></span> <span data-ttu-id="1acb9-124">Eine minimale Ähnlichkeit von 1 bedeutet eine genaue Übereinstimmung.</span><span class="sxs-lookup"><span data-stu-id="1acb9-124">A minimum similarity of 1 indicates an exact match.</span></span>  
  
13. <span data-ttu-id="1acb9-125">Aktualisieren Sie optional die Namen von Ähnlichkeitsspalten in der **Ähnlichkeitsausgabealias** -Spalte.</span><span class="sxs-lookup"><span data-stu-id="1acb9-125">Optionally, update the names of similarity columns in the **Similarity Output Alias** column.</span></span>  
  
14. <span data-ttu-id="1acb9-126">Aktualisieren Sie die Werte in der **Zahlen** -Spalte, um die Behandlung von Zahlen in Datenwerten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1acb9-126">To specify the handling of numbers in data values, update the values in the **Numerals** column.</span></span>  
  
15. <span data-ttu-id="1acb9-127">Um anzugeben, wie die Transformation die Zeichenfolgendaten in einer Spalte vergleicht, ändern Sie die Standardauswahl von Vergleichsoptionen in der **Vergleichsflags** -Spalte.</span><span class="sxs-lookup"><span data-stu-id="1acb9-127">To specify how the transformation compares the string data in a column, modify the default selection of comparison options in the **Comparison Flags** column.</span></span>  
  
16. <span data-ttu-id="1acb9-128">Klicken Sie auf die Registerkarte **Erweitert** , um die Namen der Spalten zu ändern, die die Transformation der Ausgabe für den eindeutigen Zeilenbezeichner (_key_in), den doppelten Zeilenbezeichner (_key_out) und den Ähnlichkeitswert (_score) hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="1acb9-128">Click the **Advanced** tab to modify the names of the columns that the transformation adds to the output for the unique row identifier (_key_in), the duplicate row identifier (_key_out), and the similarity value (_score).</span></span>  
  
17. <span data-ttu-id="1acb9-129">Passen Sie optional den Schwellenwert für die Ähnlichkeit mithilfe des Schiebereglers an.</span><span class="sxs-lookup"><span data-stu-id="1acb9-129">Optionally, adjust the similarity threshold by moving the slider bar.</span></span>  
  
18. <span data-ttu-id="1acb9-130">Deaktivieren Sie optional die Kontrollkästchen für Tokentrennzeichen, um Trennzeichen in den Daten zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="1acb9-130">Optionally, clear the token delimiter check boxes to ignore delimiters in the data.</span></span>  
  
19. <span data-ttu-id="1acb9-131">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1acb9-131">Click **OK**.</span></span>  
  
20. <span data-ttu-id="1acb9-132">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="1acb9-132">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1acb9-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1acb9-133">See Also</span></span>  
 <span data-ttu-id="1acb9-134">[Fuzzy Grouping Transformation](fuzzy-grouping-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="1acb9-134">[Fuzzy Grouping Transformation](fuzzy-grouping-transformation.md) </span></span>  
 <span data-ttu-id="1acb9-135">[SQL Server Integration Services-Transformationen](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="1acb9-135">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="1acb9-136">[SQL Server Integration Services-Pfade](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="1acb9-136">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="1acb9-137">Datenflusstask</span><span class="sxs-lookup"><span data-stu-id="1acb9-137">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
