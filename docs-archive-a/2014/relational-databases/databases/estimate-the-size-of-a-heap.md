---
title: Schätzen der Größe eines Heaps | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- disk space [SQL Server], indexes
- estimating heap size
- size [SQL Server], heap
- space [SQL Server], indexes
- heaps
ms.assetid: 81fd5ec9-ce0f-4c2c-8ba0-6c483cea6c75
author: stevestein
ms.author: sstein
ms.openlocfilehash: f32432d07a9731d849ceb793daf209cfc505b0ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622665"
---
# <a name="estimate-the-size-of-a-heap"></a><span data-ttu-id="00bbc-102">Schätzen der Größe eines Heaps</span><span class="sxs-lookup"><span data-stu-id="00bbc-102">Estimate the Size of a Heap</span></span>
  <span data-ttu-id="00bbc-103">Mit den folgenden Schritten können Sie den Umfang des Speicherplatzes schätzen, der zum Speichern von Daten in einem Heap erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="00bbc-103">You can use the following steps to estimate the amount of space that is required to store data in a heap:</span></span>  
  
1.  <span data-ttu-id="00bbc-104">Geben Sie die Anzahl der Zeilen an, die die Tabelle enthalten wird:</span><span class="sxs-lookup"><span data-stu-id="00bbc-104">Specify the number of rows that will be present in the table:</span></span>  
  
     <span data-ttu-id="00bbc-105">***Num_Rows***  = Anzahl der Zeilen in der Tabelle</span><span class="sxs-lookup"><span data-stu-id="00bbc-105">***Num_Rows***  = number of rows in the table</span></span>  
  
2.  <span data-ttu-id="00bbc-106">Geben Sie die Anzahl der Spalten mit fester und mit variabler Länge an, und berechnen Sie den Speicherplatz, der für deren Speicherung erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="00bbc-106">Specify the number of fixed-length and variable-length columns and calculate the space that is required for their storage:</span></span>  
  
     <span data-ttu-id="00bbc-107">Berechnen Sie den Speicherplatz, der zum Speichern jeder dieser Spaltengruppen innerhalb der Datenzeile erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="00bbc-107">Calculate the space that each of these groups of columns occupies within the data row.</span></span> <span data-ttu-id="00bbc-108">Die Größe einer Spalte hängt von der Angabe für Datentyp und -länge ab.</span><span class="sxs-lookup"><span data-stu-id="00bbc-108">The size of a column depends on the data type and length specification.</span></span>  
  
     <span data-ttu-id="00bbc-109">***Num_Cols***  = Gesamtanzahl der Spalten (mit fester und variabler Länge)</span><span class="sxs-lookup"><span data-stu-id="00bbc-109">***Num_Cols***  = total number of columns (fixed-length and variable-length)</span></span>  
  
     <span data-ttu-id="00bbc-110">***Fixed_Data_Size***  = Gesamtzahl der Bytes in allen Spalten fester Länge</span><span class="sxs-lookup"><span data-stu-id="00bbc-110">***Fixed_Data_Size***  = total byte size of all fixed-length columns</span></span>  
  
     <span data-ttu-id="00bbc-111">***Num_Variable_Cols***  = Anzahl der Spalten variabler Länge</span><span class="sxs-lookup"><span data-stu-id="00bbc-111">***Num_Variable_Cols***  = number of variable-length columns</span></span>  
  
     <span data-ttu-id="00bbc-112">***Max_Var_Size***  = Maximale gesamte Bytegröße aller Spalten variabler Länge</span><span class="sxs-lookup"><span data-stu-id="00bbc-112">***Max_Var_Size***  = maximum total byte size of all variable-length columns</span></span>  
  
3.  <span data-ttu-id="00bbc-113">Ein Teil der Zeile, der als NULL-Bitmuster (Null_Bitmap) bezeichnet wird, wird für das Verwalten der NULL-Zulässigkeit der Spalte reserviert.</span><span class="sxs-lookup"><span data-stu-id="00bbc-113">Part of the row, known as the null bitmap, is reserved to manage column nullability.</span></span> <span data-ttu-id="00bbc-114">Berechnen Sie dessen Größe:</span><span class="sxs-lookup"><span data-stu-id="00bbc-114">Calculate its size:</span></span>  
  
     <span data-ttu-id="00bbc-115">***Null_Bitmap***  = 2 + ((***Num_Cols*** + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="00bbc-115">***Null_Bitmap***  = 2 + ((***Num_Cols*** + 7) / 8)</span></span>  
  
     <span data-ttu-id="00bbc-116">Nur der ganzzahlige Teil dieses Ausdrucks darf verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="00bbc-116">Only the integer part of this expression should be used.</span></span> <span data-ttu-id="00bbc-117">Der Rest wird verworfen.</span><span class="sxs-lookup"><span data-stu-id="00bbc-117">Discard any remainder.</span></span>  
  
4.  <span data-ttu-id="00bbc-118">Berechnen Sie die Größe der Daten variabler Länge:</span><span class="sxs-lookup"><span data-stu-id="00bbc-118">Calculate the variable-length data size:</span></span>  
  
     <span data-ttu-id="00bbc-119">Wenn die Tabelle Spalten variabler Länge enthält, müssen Sie den Speicherplatz ermitteln, der von den Spalten innerhalb der Zeile verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="00bbc-119">If there are variable-length columns in the table, determine how much space is used to store the columns within the row:</span></span>  
  
     <span data-ttu-id="00bbc-120">***Variable_Data_Size***  = 2 + (***Num_Variable_Cols*** x 2) + ***Max_Var_Size***</span><span class="sxs-lookup"><span data-stu-id="00bbc-120">***Variable_Data_Size***  = 2 + (***Num_Variable_Cols*** x 2) + ***Max_Var_Size***</span></span>  
  
     <span data-ttu-id="00bbc-121">Die zu ***Max_Var_Size*** hinzugefügten Bytes dienen der Nachverfolgung der einzelnen Spalten mit variabler Länge.</span><span class="sxs-lookup"><span data-stu-id="00bbc-121">The bytes added to ***Max_Var_Size*** are for tracking each variable-length column.</span></span> <span data-ttu-id="00bbc-122">Bei dieser Formel wird angenommen, dass alle Spalten variabler Länge zu 100 % gefüllt sind.</span><span class="sxs-lookup"><span data-stu-id="00bbc-122">This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="00bbc-123">Wenn sich abzeichnet, dass ein niedrigerer Prozentsatz des Speicherplatzes für Spalten variabler Länge verwendet wird, können Sie den ***Max_Var_Size*** -Wert mithilfe dieses Prozentsatzes anpassen, um einen genaueren Schätzwert für die Gesamtgröße der Tabelle zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="00bbc-123">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="00bbc-124">Sie können `varchar`-, `nvarchar`-, `varbinary`- oder `sql_variant`-Spalten kombinieren, mit dem Ergebnis, dass die definierte Tabellengesamtbreite größer als 8.060 Byte ist.</span><span class="sxs-lookup"><span data-stu-id="00bbc-124">You can combine `varchar`, `nvarchar`, `varbinary`, or `sql_variant` columns that cause the total defined table width to exceed 8,060 bytes.</span></span> <span data-ttu-id="00bbc-125">Die Länge jeder dieser Spalten muss für eine-,-oder-Spalte weiterhin den Grenzwert von 8.000 Bytes überschreiten `varchar` `nvarchar,``varbinary` `sql_variant` .</span><span class="sxs-lookup"><span data-stu-id="00bbc-125">The length of each one of these columns must still fall within the limit of 8,000 bytes for a `varchar`, `nvarchar,``varbinary`, or `sql_variant` column.</span></span> <span data-ttu-id="00bbc-126">Die kombinierte Breite kann jedoch den Grenzwert von 8.060 Byte in einer Tabelle überschreiten.</span><span class="sxs-lookup"><span data-stu-id="00bbc-126">However, their combined widths may exceed the 8,060 byte limit in a table.</span></span>  
  
     <span data-ttu-id="00bbc-127">Wenn keine Spalten variabler Länge vorhanden sind, legen Sie ***Variable_Data_Size*** auf 0 fest.</span><span class="sxs-lookup"><span data-stu-id="00bbc-127">If there are no variable-length columns, set ***Variable_Data_Size*** to 0.</span></span>  
  
5.  <span data-ttu-id="00bbc-128">Berechnen Sie die Gesamtzeilenlänge:</span><span class="sxs-lookup"><span data-stu-id="00bbc-128">Calculate the total row size:</span></span>  
  
     <span data-ttu-id="00bbc-129">***Row_Size***  = ***Fixed_Data_Size*** + ***Variable_Data_Size*** + ***Null_Bitmap*** + 4</span><span class="sxs-lookup"><span data-stu-id="00bbc-129">***Row_Size***  = ***Fixed_Data_Size*** + ***Variable_Data_Size*** + ***Null_Bitmap*** + 4</span></span>  
  
     <span data-ttu-id="00bbc-130">Der Wert 4 in der Formel ist der Zeilenüberschriftenaufwand der Datenzeile.</span><span class="sxs-lookup"><span data-stu-id="00bbc-130">The value 4 in the formula is the row header overhead of the data row.</span></span>  
  
6.  <span data-ttu-id="00bbc-131">Berechnen Sie die Anzahl der Zeilen pro Seite (8.096 freie Byte pro Seite):</span><span class="sxs-lookup"><span data-stu-id="00bbc-131">Calculate the number of rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="00bbc-132">***Rows_Per_Page***  = 8096 / (***Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="00bbc-132">***Rows_Per_Page***  = 8096 / (***Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="00bbc-133">Da sich eine Zeile nicht auf zwei Seiten erstreckt, muss die Anzahl der Zeilen pro Seite auf die nächste ganze Zeile abgerundet werden.</span><span class="sxs-lookup"><span data-stu-id="00bbc-133">Because rows do not span pages, the number of rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="00bbc-134">Die Angabe 2 in der Formel bezieht sich auf den Eingang der Zeile in das Slotarray der Seite.</span><span class="sxs-lookup"><span data-stu-id="00bbc-134">The value 2 in the formula is for the row's entry in the slot array of the page.</span></span>  
  
7.  <span data-ttu-id="00bbc-135">Berechnen Sie die Anzahl der Seiten, die zum Speichern aller Zeilen benötigt werden:</span><span class="sxs-lookup"><span data-stu-id="00bbc-135">Calculate the number of pages required to store all the rows:</span></span>  
  
     <span data-ttu-id="00bbc-136">***Num_Pages***  = ***Num_Rows*** / ***Rows_Per_Page***</span><span class="sxs-lookup"><span data-stu-id="00bbc-136">***Num_Pages***  = ***Num_Rows*** / ***Rows_Per_Page***</span></span>  
  
     <span data-ttu-id="00bbc-137">Die geschätzte Seitenanzahl muss auf die nächste ganze Seite aufgerundet werden.</span><span class="sxs-lookup"><span data-stu-id="00bbc-137">The number of pages estimated should be rounded up to the nearest whole page.</span></span>  
  
8.  <span data-ttu-id="00bbc-138">Berechnen Sie den Umfang des Speicherplatzes, der zum Speichern der Daten im Heap erforderlich ist (insgesamt 8.192 Byte pro Seite):</span><span class="sxs-lookup"><span data-stu-id="00bbc-138">Calculate the amount of space that is required to store the data in the heap (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="00bbc-139">Heapgröße (Bytes) = 8.192 × ***Num_Pages***</span><span class="sxs-lookup"><span data-stu-id="00bbc-139">Heap size (bytes) = 8192 x ***Num_Pages***</span></span>  
  
 <span data-ttu-id="00bbc-140">In dieser Berechnung wird Folgendes nicht berücksichtigt:</span><span class="sxs-lookup"><span data-stu-id="00bbc-140">This calculation does not consider the following:</span></span>  
  
-   <span data-ttu-id="00bbc-141">Partitionierung</span><span class="sxs-lookup"><span data-stu-id="00bbc-141">Partitioning</span></span>  
  
     <span data-ttu-id="00bbc-142">Der Speicherplatzaufwand aus der Partitionierung ist geringfügig, seine Berechnung jedoch komplex.</span><span class="sxs-lookup"><span data-stu-id="00bbc-142">The space overhead from partitioning is minimal, but complex to calculate.</span></span> <span data-ttu-id="00bbc-143">Er muss nicht berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="00bbc-143">It is not important to include.</span></span>  
  
-   <span data-ttu-id="00bbc-144">Zuordnungsseiten</span><span class="sxs-lookup"><span data-stu-id="00bbc-144">Allocation pages</span></span>  
  
     <span data-ttu-id="00bbc-145">Mindestens eine IAM-Seite wird zum Nachverfolgen der für einen Heap zugeordneten Seiten verwendet, der Speicherplatzaufwand ist jedoch nur minimal. Außerdem ist kein Algorithmus verfügbar, um deterministisch genau zu berechnen, wie viele IAM-Seiten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="00bbc-145">There is at least one IAM page used to track the pages allocated to a heap, but the space overhead is minimal and there is no algorithm to deterministically calculate exactly how many IAM pages will be used.</span></span>  
  
-   <span data-ttu-id="00bbc-146">LOB-Werte (Large Object)</span><span class="sxs-lookup"><span data-stu-id="00bbc-146">Large object (LOB) values</span></span>  
  
     <span data-ttu-id="00bbc-147">Der Algorithmus, um genau zu bestimmen, wie viel Speicherplatz zum Speichern der LOB-Datentypen `varchar(max)` , `varbinary(max)` ,, `nvarchar(max)` `text` , **ntextxml**und `image` Werte verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="00bbc-147">The algorithm to determine exactly how much space will be used to store the LOB data types `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, **ntextxml**, and `image` values is complex.</span></span> <span data-ttu-id="00bbc-148">Es reicht aus, lediglich die Durchschnittsgröße der erwarteten LOB-Werte zu addieren und diesen Wert zur Heapgesamtgröße zu addieren.</span><span class="sxs-lookup"><span data-stu-id="00bbc-148">It is sufficient to just add the average size of the LOB values that are expected and add that to the total heap size.</span></span>  
  
-   <span data-ttu-id="00bbc-149">Komprimierung</span><span class="sxs-lookup"><span data-stu-id="00bbc-149">Compression</span></span>  
  
     <span data-ttu-id="00bbc-150">Sie können die Größe eines komprimierten Heaps nicht im Voraus berechnen.</span><span class="sxs-lookup"><span data-stu-id="00bbc-150">You cannot pre-calculate the size of a compressed heap.</span></span>  
  
-   <span data-ttu-id="00bbc-151">Spalten mit geringer Dichte</span><span class="sxs-lookup"><span data-stu-id="00bbc-151">Sparse columns</span></span>  
  
     <span data-ttu-id="00bbc-152">Informationen zu den Speicherplatzanforderungen von Sparsespalten finden Sie unter [Use Sparse Columns](../tables/use-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="00bbc-152">For information about the space requirements of sparse columns, see [Use Sparse Columns](../tables/use-sparse-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00bbc-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="00bbc-153">See Also</span></span>  
 <span data-ttu-id="00bbc-154">[Heaps &#40;Tabellen ohne gruppierte Indizes&#41;](../indexes/heaps-tables-without-clustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="00bbc-154">[Heaps &#40;Tables without Clustered Indexes&#41;](../indexes/heaps-tables-without-clustered-indexes.md) </span></span>  
 <span data-ttu-id="00bbc-155">[Beschreibung von gruppierten und nicht gruppierten Indizes](../indexes/clustered-and-nonclustered-indexes-described.md) </span><span class="sxs-lookup"><span data-stu-id="00bbc-155">[Clustered and Nonclustered Indexes Described](../indexes/clustered-and-nonclustered-indexes-described.md) </span></span>  
 <span data-ttu-id="00bbc-156">[Erstellen gruppierter Indizes](../indexes/create-clustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="00bbc-156">[Create Clustered Indexes](../indexes/create-clustered-indexes.md) </span></span>  
 <span data-ttu-id="00bbc-157">[Erstellen nicht gruppierter Indizes](../indexes/create-nonclustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="00bbc-157">[Create Nonclustered Indexes](../indexes/create-nonclustered-indexes.md) </span></span>  
 <span data-ttu-id="00bbc-158">[Schätzen der Größe einer Tabelle](estimate-the-size-of-a-table.md) </span><span class="sxs-lookup"><span data-stu-id="00bbc-158">[Estimate the Size of a Table](estimate-the-size-of-a-table.md) </span></span>  
 <span data-ttu-id="00bbc-159">[Schätzen der Größe eines gruppierten Indexes](estimate-the-size-of-a-clustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="00bbc-159">[Estimate the Size of a Clustered Index](estimate-the-size-of-a-clustered-index.md) </span></span>  
 <span data-ttu-id="00bbc-160">[Schätzen der Größe eines nicht gruppierten Index](estimate-the-size-of-a-nonclustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="00bbc-160">[Estimate the Size of a Nonclustered Index](estimate-the-size-of-a-nonclustered-index.md) </span></span>  
 [<span data-ttu-id="00bbc-161">Schätzen der Größe einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="00bbc-161">Estimate the Size of a Database</span></span>](estimate-the-size-of-a-database.md)  
  
  
