---
title: Schätzen der Größe eines nicht gruppierten Index | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- space allocation [SQL Server], index size
- size [SQL Server], tables
- predicting table size [SQL Server]
- table size [SQL Server]
- estimating table size
- clustered indexes, table size
- designing databases [SQL Server], estimating size
- calculating table size
ms.assetid: c183b0e4-ef4c-4bfc-8575-5ac219c25b0a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 097c0e5568ba17b12f83d09e347eb3bf8b0bd7da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721481"
---
# <a name="estimate-the-size-of-a-nonclustered-index"></a><span data-ttu-id="d311e-102">Schätzen der Größe eines nicht gruppierten Index</span><span class="sxs-lookup"><span data-stu-id="d311e-102">Estimate the Size of a Nonclustered Index</span></span>
  <span data-ttu-id="d311e-103">Befolgen Sie diese Schritte, um abzuschätzen, wie viel Speicherplatz zum Speichern eines nicht gruppierten Index erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d311e-103">Follow these steps to estimate the amount of space that is required to store a nonclustered index:</span></span>  
  
1.  <span data-ttu-id="d311e-104">Berechnen Sie die Variablen zur Verwendung in Schritt 2 und 3.</span><span class="sxs-lookup"><span data-stu-id="d311e-104">Calculate variables for use in steps 2 and 3.</span></span>  
  
2.  <span data-ttu-id="d311e-105">Berechnen Sie den Speicherplatz, der zum Speichern der Indexinformationen in der Blattebene des nicht gruppierten Index verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d311e-105">Calculate the space used to store index information in the leaf level of the nonclustered index.</span></span>  
  
3.  <span data-ttu-id="d311e-106">Berechnen Sie den Speicherplatz, der zum Speichern der Indexinformationen in den inneren Knotenebenen des nicht gruppierten Index verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d311e-106">Calculate the space used to store index information in the non-leaf levels of the nonclustered index.</span></span>  
  
4.  <span data-ttu-id="d311e-107">Addieren Sie die berechneten Werte.</span><span class="sxs-lookup"><span data-stu-id="d311e-107">Total the calculated values.</span></span>  
  
## <a name="step-1-calculate-variables-for-use-in-steps-2-and-3"></a><span data-ttu-id="d311e-108">Schritt 1:</span><span class="sxs-lookup"><span data-stu-id="d311e-108">Step 1.</span></span> <span data-ttu-id="d311e-109">Berechnen der zu verwendenden Variablen in Schritt 2 und 3</span><span class="sxs-lookup"><span data-stu-id="d311e-109">Calculate Variables for Use in Steps 2 and 3</span></span>  
 <span data-ttu-id="d311e-110">Mit den folgenden Schritten können Sie die Variablen berechnen, mit denen die Größe des Speicherplatzes geschätzt wird, die zum Speichern der oberen Ebenen des Indexes erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d311e-110">You can use the following steps to calculate variables that are used to estimate the amount of space that is required to store the upper levels of the index.</span></span>  
  
1.  <span data-ttu-id="d311e-111">Geben Sie die Anzahl der Zeilen an, die die Tabelle enthalten wird:</span><span class="sxs-lookup"><span data-stu-id="d311e-111">Specify the number of rows that will be present in the table:</span></span>  
  
     <span data-ttu-id="d311e-112">***Num_Rows***  = Anzahl der Zeilen in der Tabelle</span><span class="sxs-lookup"><span data-stu-id="d311e-112">***Num_Rows***  = number of rows in the table</span></span>  
  
2.  <span data-ttu-id="d311e-113">Geben Sie die Anzahl der Spalten mit fester und mit variabler Länge im Indexschlüssel an, und berechnen Sie den Speicherplatz, der für deren Speicherung erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="d311e-113">Specify the number of fixed-length and variable-length columns in the index key and calculate the space that is required for their storage:</span></span>  
  
     <span data-ttu-id="d311e-114">Die Schlüsselspalten eines Indexes können Spalten fester und variabler Länge enthalten.</span><span class="sxs-lookup"><span data-stu-id="d311e-114">The key columns of an index can include fixed-length and variable-length columns.</span></span> <span data-ttu-id="d311e-115">Um die Größe der Indexzeilen auf der inneren Ebene zu schätzen, müssen Sie den Speicherplatz berechnen, der von jeder dieser Spaltengruppen innerhalb der Indexzeile belegt wird.</span><span class="sxs-lookup"><span data-stu-id="d311e-115">To estimate the interior level index row size, calculate the space that each of these groups of columns occupies within the index row.</span></span> <span data-ttu-id="d311e-116">Die Größe einer Spalte hängt von der Angabe für Datentyp und -länge ab.</span><span class="sxs-lookup"><span data-stu-id="d311e-116">The size of a column depends on the data type and length specification.</span></span>  
  
     <span data-ttu-id="d311e-117">***Num_Key_Cols***  = Gesamtanzahl der Schlüsselspalten (fester und variabler Länge)</span><span class="sxs-lookup"><span data-stu-id="d311e-117">***Num_Key_Cols***  = total number of key columns (fixed-length and variable-length)</span></span>  
  
     <span data-ttu-id="d311e-118">***Fixed_Key_Size***  = Gesamtzahl der Bytes in allen Schlüsselspalten fester Länge</span><span class="sxs-lookup"><span data-stu-id="d311e-118">***Fixed_Key_Size***  = total byte size of all fixed-length key columns</span></span>  
  
     <span data-ttu-id="d311e-119">***Num_Variable_Key_Cols***  = Anzahl der Schlüsselspalten variabler Länge</span><span class="sxs-lookup"><span data-stu-id="d311e-119">***Num_Variable_Key_Cols***  = number of variable-length key columns</span></span>  
  
     <span data-ttu-id="d311e-120">***Max_Var_Key_Size***  = Maximale Bytegröße aller Schlüsselspalten variabler Länge</span><span class="sxs-lookup"><span data-stu-id="d311e-120">***Max_Var_Key_Size***  = maximum byte size of all variable-length key columns</span></span>  
  
3.  <span data-ttu-id="d311e-121">Berücksichtigen Sie auch den Datenzeilenlokator, der erforderlich ist, wenn der Index nicht eindeutig ist:</span><span class="sxs-lookup"><span data-stu-id="d311e-121">Account for the data row locator that is required if the index is nonunique:</span></span>  
  
     <span data-ttu-id="d311e-122">Wenn der nicht gruppierte Index nicht eindeutig ist, wird der Datenzeilenlokator mit dem Schlüssel des nicht gruppierten Indexes kombiniert, um einen eindeutigen Schlüsselwert für jede Zeile zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d311e-122">If the nonclustered index is nonunique, the data row locator is combined with the nonclustered index key to produce a unique key value for every row.</span></span>  
  
     <span data-ttu-id="d311e-123">Wenn sich der nicht gruppierte Index über einem Heap befindet, ist der Datenzeilenlokator die Heap-RID.</span><span class="sxs-lookup"><span data-stu-id="d311e-123">If the nonclustered index is over a heap, the data row locator is the heap RID.</span></span> <span data-ttu-id="d311e-124">Die Größe beträgt dann 8 Byte.</span><span class="sxs-lookup"><span data-stu-id="d311e-124">This is a size of 8 bytes.</span></span>  
  
     <span data-ttu-id="d311e-125">***Num_Key_Cols***  = ***Num_Key_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="d311e-125">***Num_Key_Cols***  = ***Num_Key_Cols*** + 1</span></span>  
  
     <span data-ttu-id="d311e-126">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="d311e-126">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + 1</span></span>  
  
     <span data-ttu-id="d311e-127">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + 8</span><span class="sxs-lookup"><span data-stu-id="d311e-127">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + 8</span></span>  
  
     <span data-ttu-id="d311e-128">Wenn sich der nicht gruppierte Index über einem gruppierten Index befindet, dann ist der Datenzeilenlokator der Gruppierungsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="d311e-128">If the nonclustered index is over a clustered index, the data row locator is the clustering key.</span></span> <span data-ttu-id="d311e-129">Bei den Spalten, die mit dem nicht gruppierten Index kombiniert werden müssen, handelt es sich um die im Gruppierungsschlüssel enthaltenen Spalten, die noch nicht in der Menge der nicht gruppierten Indexschlüsselspalten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d311e-129">The columns that must be combined with the nonclustered index key are those columns in the clustering key that are not already present in the set of nonclustered index key columns.</span></span>  
  
     <span data-ttu-id="d311e-130">***Num_Key_Cols***  = ***Num_Key_Cols*** + Anzahl der Gruppierungsschlüsselspalten, die nicht in der Menge der nicht gruppierten Indexschlüsselspalten vorhanden sind (+ 1, wenn der gruppierte Index nicht eindeutig ist)</span><span class="sxs-lookup"><span data-stu-id="d311e-130">***Num_Key_Cols***  = ***Num_Key_Cols*** + number of clustering key columns not in the set of nonclustered index key columns (+ 1 if the clustered index is nonunique)</span></span>  
  
     <span data-ttu-id="d311e-131">***Fixed_Key_Size***  = ***Fixed_Key_Size*** + Gesamtanzahl der Bytes in allen Gruppierungsschlüsselspalten fester Länge, die nicht in der Menge der nicht gruppierten Indexschlüsselspalten vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="d311e-131">***Fixed_Key_Size***  = ***Fixed_Key_Size*** + total byte size of fixed-length clustering key columns not in the set of nonclustered index key columns</span></span>  
  
     <span data-ttu-id="d311e-132">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + Anzahl der Gruppierungsschlüsselspalten variabler Länge, die nicht in der Menge der nicht gruppierten Indexschlüsselspalten vorhanden sind (+ 1, wenn der gruppierte Index nicht eindeutig ist)</span><span class="sxs-lookup"><span data-stu-id="d311e-132">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + number of variable-length clustering key columns not in the set of nonclustered index key columns (+ 1 if the clustered index is nonunique)</span></span>  
  
     <span data-ttu-id="d311e-133">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + maximale Anzahl der Bytes in den Gruppierungsschlüsselspalten variabler Länge, die nicht in der Menge der nicht gruppierten Indexschlüsselspalten vorhanden sind (+ 4, wenn der gruppierte Index nicht eindeutig ist)</span><span class="sxs-lookup"><span data-stu-id="d311e-133">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + maximum byte size of variable-length clustering key columns not in the set of nonclustered index key columns (+ 4 if the clustered index is nonunique)</span></span>  
  
4.  <span data-ttu-id="d311e-134">Ein Teil der Zeile, der als NULL-Bitmuster bezeichnet wird, kann für das Verwalten der NULL-Zulässigkeit der Spalte reserviert sein.</span><span class="sxs-lookup"><span data-stu-id="d311e-134">Part of the row, known as the null bitmap, may be reserved to manage column nullability.</span></span> <span data-ttu-id="d311e-135">Berechnen Sie dessen Größe:</span><span class="sxs-lookup"><span data-stu-id="d311e-135">Calculate its size:</span></span>  
  
     <span data-ttu-id="d311e-136">Wenn der Indexschlüssel Spalten enthält, die NULL-Werte zulassen (einschließlich erforderlicher Gruppierungsschlüsselspalten wie in Schritt 1.3 beschrieben), ist ein Teil der Indexzeile für das NULL-Bitmuster reserviert.</span><span class="sxs-lookup"><span data-stu-id="d311e-136">If there are nullable columns in the index key, including any necessary clustering key columns as described in Step 1.3, part of the index row is reserved for the null bitmap.</span></span>  
  
     <span data-ttu-id="d311e-137">***Index_Null_Bitmap***  = 2 + ((Anzahl der Spalten in der Indexzeile + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="d311e-137">***Index_Null_Bitmap***  = 2 + ((number of columns in the index row + 7) / 8)</span></span>  
  
     <span data-ttu-id="d311e-138">Nur der ganzzahlige Teil des vorherigen Ausdrucks darf verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d311e-138">Only the integer part of the previous expression should be used.</span></span> <span data-ttu-id="d311e-139">Der Rest wird verworfen.</span><span class="sxs-lookup"><span data-stu-id="d311e-139">Discard any remainder.</span></span>  
  
     <span data-ttu-id="d311e-140">Wenn keine Schlüsselspalten vorhanden sind, die NULL-Werte zulassen, legen Sie ***Index_Null_Bitmap*** auf 0 fest.</span><span class="sxs-lookup"><span data-stu-id="d311e-140">If there are no nullable key columns, set ***Index_Null_Bitmap*** to 0.</span></span>  
  
5.  <span data-ttu-id="d311e-141">Berechnen Sie die Größe der Daten variabler Länge:</span><span class="sxs-lookup"><span data-stu-id="d311e-141">Calculate the variable length data size:</span></span>  
  
     <span data-ttu-id="d311e-142">Wenn der Indexschlüssel Spalten variabler Länge enthält (einschließlich erforderlicher Schlüsselspalten des gruppierten Indexes), müssen Sie ermitteln, wie viel Speicherplatz zum Speichern der Spalten innerhalb der Indexzeile verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="d311e-142">If there are variable-length columns in the index key, including any necessary clustered index key columns, determine how much space is used to store the columns within the index row:</span></span>  
  
     <span data-ttu-id="d311e-143">***Variable_Key_Size***  = 2 + (***Num_Variable_Key_Cols*** x 2) + ***Max_Var_Key_Size***</span><span class="sxs-lookup"><span data-stu-id="d311e-143">***Variable_Key_Size***  = 2 + (***Num_Variable_Key_Cols*** x 2) + ***Max_Var_Key_Size***</span></span>  
  
     <span data-ttu-id="d311e-144">Die zu ***Max_Var_Key_Size*** hinzugefügten Bytes dienen der Nachverfolgung jeder einzelnen Variablenspalte. Bei dieser Formel wird angenommen, dass alle Spalten variabler Länge zu 100 Prozent gefüllt sind.</span><span class="sxs-lookup"><span data-stu-id="d311e-144">The bytes added to ***Max_Var_Key_Size*** are for tracking each variable column.This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="d311e-145">Wenn sich abzeichnet, dass ein niedrigerer Prozentsatz des Speicherplatzes für Spalten variabler Länge verwendet wird, können Sie den ***Max_Var_Key_Size*** -Wert mithilfe dieses Prozentsatzes anpassen, um einen genaueren Schätzwert für die Gesamtgröße der Tabelle zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d311e-145">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Key_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
     <span data-ttu-id="d311e-146">Wenn keine Spalten variabler Länge vorhanden sind, legen Sie ***Variable_Key_Size*** auf 0 fest.</span><span class="sxs-lookup"><span data-stu-id="d311e-146">If there are no variable-length columns, set ***Variable_Key_Size*** to 0.</span></span>  
  
6.  <span data-ttu-id="d311e-147">Berechnen Sie die Länge der Indexzeile:</span><span class="sxs-lookup"><span data-stu-id="d311e-147">Calculate the index row size:</span></span>  
  
     <span data-ttu-id="d311e-148">***Index_Row_Size***  = ***Fixed_Key_Size*** + ***Variable_Key_Size*** + ***Index_Null_Bitmap*** + 1 (für Zeilenüberschriftenaufwand einer Indexzeile) + 6 (für ID-Zeiger der untergeordneten Seite)</span><span class="sxs-lookup"><span data-stu-id="d311e-148">***Index_Row_Size***  = ***Fixed_Key_Size*** + ***Variable_Key_Size*** + ***Index_Null_Bitmap*** + 1 (for row header overhead of an index row) + 6 (for the child page ID pointer)</span></span>  
  
7.  <span data-ttu-id="d311e-149">Berechnen Sie die Anzahl der Indexzeilen pro Seite (8096 freie Byte pro Seite):</span><span class="sxs-lookup"><span data-stu-id="d311e-149">Calculate the number of index rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="d311e-150">***Index_Rows_Per_Page***  = 8096 / (***Index_Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="d311e-150">***Index_Rows_Per_Page***  = 8096 / (***Index_Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="d311e-151">Da sich eine Indexzeile nicht auf zwei Seiten erstreckt, muss die Anzahl der Indexzeilen pro Seite auf die nächste ganze Zeile abgerundet werden.</span><span class="sxs-lookup"><span data-stu-id="d311e-151">Because index rows do not span pages, the number of index rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="d311e-152">Die Angabe 2 in der Formel bezieht sich auf den Eingang der Zeile in das Slotarray der Seite.</span><span class="sxs-lookup"><span data-stu-id="d311e-152">The 2 in the formula is for the row's entry in the page's slot array.</span></span>  
  
## <a name="step-2-calculate-the-space-used-to-store-index-information-in-the-leaf-level"></a><span data-ttu-id="d311e-153">Schritt 2:</span><span class="sxs-lookup"><span data-stu-id="d311e-153">Step 2.</span></span> <span data-ttu-id="d311e-154">Berechnen des Speicherplatzes, der zum Speichern der Indexinformationen in der Blattebene verwendet wird</span><span class="sxs-lookup"><span data-stu-id="d311e-154">Calculate the Space Used to Store Index Information in the Leaf Level</span></span>  
 <span data-ttu-id="d311e-155">Mit den folgenden Schritten können Sie den Umfang des Speicherplatzes schätzen, der zum Speichern der Blattebene des Indexes erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d311e-155">You can use the following steps to estimate the amount of space that is required to store the leaf level of the index.</span></span> <span data-ttu-id="d311e-156">Sie benötigen die in Schritt 1 aufgezeichneten Werte, um diesen Schritt durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="d311e-156">You will need the values preserved from Step 1 to complete this step.</span></span>  
  
1.  <span data-ttu-id="d311e-157">Geben Sie die Anzahl der Spalten mit fester und mit variabler Länge auf Blattebene an, und berechnen Sie den Speicherplatz, der für deren Speicherung erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="d311e-157">Specify the number of fixed-length and variable-length columns at the leaf level and calculate the space that is required for their storage:</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d311e-158">Sie können einen nicht gruppierten Index erweitern, indem Nichtschlüsselspalten zusätzlich zu Indexschlüsselspalten eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="d311e-158">You can extend a nonclustered index by including nonkey columns in addition to the index key columns.</span></span> <span data-ttu-id="d311e-159">Diese zusätzlichen Spalten werden auf der Blattebene des nicht gruppierten Indexes gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d311e-159">These additional columns are only stored at the leaf level of the nonclustered index.</span></span> <span data-ttu-id="d311e-160">Weitere Informationen finden Sie unter [Create Indexes with Included Columns](../indexes/create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="d311e-160">For more information, see [Create Indexes with Included Columns](../indexes/create-indexes-with-included-columns.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d311e-161">Sie können `varchar`-, `nvarchar`-, `varbinary`- oder `sql_variant`-Spalten kombinieren, mit dem Ergebnis, dass die definierte Tabellengesamtbreite größer als 8.060 Byte ist.</span><span class="sxs-lookup"><span data-stu-id="d311e-161">You can combine `varchar`, `nvarchar`, `varbinary`, or `sql_variant` columns that cause the total defined table width to exceed 8,060 bytes.</span></span> <span data-ttu-id="d311e-162">Die Länge jeder einzelnen Spalte unterliegt auch weiterhin der Beschränkung von 8.000 Byte für eine `varchar`-, `varbinary`- oder `sql_variant`-Spalte und von 4.000 Byte für `nvarchar`-Spalten.</span><span class="sxs-lookup"><span data-stu-id="d311e-162">The length of each one of these columns must still fall within the limit of 8,000 bytes for a `varchar`, `varbinary`, or `sql_variant` column, and 4,000 bytes for `nvarchar` columns.</span></span> <span data-ttu-id="d311e-163">Die kombinierte Breite kann jedoch den Grenzwert von 8.060 Byte in einer Tabelle überschreiten.</span><span class="sxs-lookup"><span data-stu-id="d311e-163">However, their combined widths may exceed the 8,060 byte limit in a table.</span></span> <span data-ttu-id="d311e-164">Dies gilt auch für die Zeilen auf Blattebene eines nicht gruppierten Indexes, die eingeschlossene Spalten enthalten.</span><span class="sxs-lookup"><span data-stu-id="d311e-164">This also applies to nonclustered index leaf rows that have included columns.</span></span>  
  
     <span data-ttu-id="d311e-165">Wenn der nicht gruppierte Index keine eingeschlossenen Spalten besitzt, verwenden Sie die Werte aus Schritt 1 einschließlich aller Änderungen, die ggf. in Schritt 1.3 vorgenommen wurden:</span><span class="sxs-lookup"><span data-stu-id="d311e-165">If the nonclustered index does not have any included columns, use the values from Step 1, including any modifications determined in Step 1.3:</span></span>  
  
     <span data-ttu-id="d311e-166">***Num_Leaf_Cols***  = ***Num_Key_Cols***</span><span class="sxs-lookup"><span data-stu-id="d311e-166">***Num_Leaf_Cols***  = ***Num_Key_Cols***</span></span>  
  
     <span data-ttu-id="d311e-167">***Fixed_Leaf_Size***  = ***Fixed_Key_Size***</span><span class="sxs-lookup"><span data-stu-id="d311e-167">***Fixed_Leaf_Size***  = ***Fixed_Key_Size***</span></span>  
  
     <span data-ttu-id="d311e-168">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Key_Cols***</span><span class="sxs-lookup"><span data-stu-id="d311e-168">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Key_Cols***</span></span>  
  
     <span data-ttu-id="d311e-169">***Max_Var_Leaf_Size***  = ***Max_Var_Key_Size***</span><span class="sxs-lookup"><span data-stu-id="d311e-169">***Max_Var_Leaf_Size***  = ***Max_Var_Key_Size***</span></span>  
  
     <span data-ttu-id="d311e-170">Wenn der nicht gruppierte Index keine eingeschlossenen Spalten besitzt, fügen Sie die entsprechenden Werte den Werten aus Schritt 1 einschließlich allen Änderungen, die ggf. in Schritt 1.3 vorgenommen wurden, hinzu.</span><span class="sxs-lookup"><span data-stu-id="d311e-170">If the nonclustered index does have included columns, add the appropriate values to the values from Step 1, including any modifications in Step 1.3.</span></span> <span data-ttu-id="d311e-171">Die Größe einer Spalte hängt von der Angabe für Datentyp und -länge ab.</span><span class="sxs-lookup"><span data-stu-id="d311e-171">The size of a column depends on the data type and length specification.</span></span> <span data-ttu-id="d311e-172">Weitere Informationen finden Sie unter [Datentypen &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d311e-172">For more information, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
     <span data-ttu-id="d311e-173">***Num_Leaf_Cols***  = ***Num_Key_Cols*** + Anzahl der enthaltenen Spalten</span><span class="sxs-lookup"><span data-stu-id="d311e-173">***Num_Leaf_Cols***  = ***Num_Key_Cols*** + number of included columns</span></span>  
  
     <span data-ttu-id="d311e-174">***Fixed_Leaf_Size***  = ***Fixed_Key_Size*** + Gesamtzahl der Bytes der enthaltenen Schlüsselspalten fester Länge</span><span class="sxs-lookup"><span data-stu-id="d311e-174">***Fixed_Leaf_Size***  = ***Fixed_Key_Size*** + total byte size of fixed-length included columns</span></span>  
  
     <span data-ttu-id="d311e-175">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Key_Cols*** + Anzahl der enthaltenen Spalten variabler Länge</span><span class="sxs-lookup"><span data-stu-id="d311e-175">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Key_Cols*** + number of variable-length included columns</span></span>  
  
     <span data-ttu-id="d311e-176">***Max_Var_Leaf_Size***  = ***Max_Var_Key_Size*** + Maximale Bytegröße der enthaltenen Spalten variabler Länge</span><span class="sxs-lookup"><span data-stu-id="d311e-176">***Max_Var_Leaf_Size***  = ***Max_Var_Key_Size*** + maximum byte size of variable-length included columns</span></span>  
  
2.  <span data-ttu-id="d311e-177">Konto für den Datenzeilenlokator:</span><span class="sxs-lookup"><span data-stu-id="d311e-177">Account for the data row locator:</span></span>  
  
     <span data-ttu-id="d311e-178">Wenn der nicht gruppierte Index nicht eindeutig ist, wurde der Aufwand für den Datenzeilenlokator bereits in Schritt 1.3 berücksichtigt. In diesem Fall sind keine zusätzlichen Änderungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d311e-178">If the nonclustered index is nonunique, the overhead for the data row locator has already been considered in Step 1.3 and no additional modifications are required.</span></span> <span data-ttu-id="d311e-179">Fahren Sie mit dem nächsten Schritt fort.</span><span class="sxs-lookup"><span data-stu-id="d311e-179">Go to the next step.</span></span>  
  
     <span data-ttu-id="d311e-180">Wenn der nicht gruppierte Index eindeutig ist, muss der Datenzeilenlokator in allen Zeilen auf der Blattebene berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="d311e-180">If the nonclustered index is unique, the data row locator must be accounted for in all rows at the leaf level.</span></span>  
  
     <span data-ttu-id="d311e-181">Wenn sich der nicht gruppierte Index über einem Heap befindet, ist der Datenzeilenlokator die Heap-RID (Größe 8 Byte).</span><span class="sxs-lookup"><span data-stu-id="d311e-181">If the nonclustered index is over a heap, the data row locator is the heap RID (size 8 bytes).</span></span>  
  
     <span data-ttu-id="d311e-182">***Num_Leaf_Cols***  = ***Num_Leaf_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="d311e-182">***Num_Leaf_Cols***  = ***Num_Leaf_Cols*** + 1</span></span>  
  
     <span data-ttu-id="d311e-183">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Leaf_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="d311e-183">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Leaf_Cols*** + 1</span></span>  
  
     <span data-ttu-id="d311e-184">***Max_Var_Leaf_Size***  = ***Max_Var_Leaf_Size*** + 8</span><span class="sxs-lookup"><span data-stu-id="d311e-184">***Max_Var_Leaf_Size***  = ***Max_Var_Leaf_Size*** + 8</span></span>  
  
     <span data-ttu-id="d311e-185">Wenn sich der nicht gruppierte Index über einem gruppierten Index befindet, dann ist der Datenzeilenlokator der Gruppierungsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="d311e-185">If the nonclustered index is over a clustered index, the data row locator is the clustering key.</span></span> <span data-ttu-id="d311e-186">Bei den Spalten, die mit dem nicht gruppierten Index kombiniert werden müssen, handelt es sich um die im Gruppierungsschlüssel enthaltenen Spalten, die noch nicht in der Menge der nicht gruppierten Indexschlüsselspalten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d311e-186">The columns that must be combined with the nonclustered index key are those columns in the clustering key that are not already present in the set of nonclustered index key columns.</span></span>  
  
     <span data-ttu-id="d311e-187">***Num_Leaf_Cols***  = ***Num_Leaf_Cols*** + Anzahl der Gruppierungsschlüsselspalten, die nicht in der Menge der nicht gruppierten Indexschlüsselspalten vorhanden sind (+ 1, wenn der gruppierte Index nicht eindeutig ist)</span><span class="sxs-lookup"><span data-stu-id="d311e-187">***Num_Leaf_Cols***  = ***Num_Leaf_Cols*** + number of clustering key columns not in the set of nonclustered index key columns (+ 1 if the clustered index is nonunique)</span></span>  
  
     <span data-ttu-id="d311e-188">***Fixed_Leaf_Size***  = ***Fixed_Leaf_Size*** + Anzahl der Bytes in allen Gruppierungsschlüsselspalten fester Länge, die nicht in der Menge der nicht gruppierten Indexschlüsselspalten vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="d311e-188">***Fixed_Leaf_Size***  = ***Fixed_Leaf_Size*** + number of fixed-length clustering key columns not in the set of nonclustered index key columns</span></span>  
  
     <span data-ttu-id="d311e-189">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Leaf_Cols*** + Anzahl der Gruppierungsschlüsselspalten variabler Länge, die nicht in der Menge der nicht gruppierten Indexschlüsselspalten vorhanden sind (+ 1, wenn der gruppierte Index nicht eindeutig ist)</span><span class="sxs-lookup"><span data-stu-id="d311e-189">***Num_Variable_Leaf_Cols***  = ***Num_Variable_Leaf_Cols*** + number of variable-length clustering key columns not in the set of nonclustered index key columns (+ 1 if the clustered index is nonunique)</span></span>  
  
     <span data-ttu-id="d311e-190">***Max_Var_Leaf_Size***  = ***Max_Var_Leaf_Size*** + Anzahl der Bytes in den Gruppierungsschlüsselspalten variabler Länge, die nicht in der Menge der nicht gruppierten Indexschlüsselspalten vorhanden sind (+ 4, wenn der gruppierte Index nicht eindeutig ist)</span><span class="sxs-lookup"><span data-stu-id="d311e-190">***Max_Var_Leaf_Size***  = ***Max_Var_Leaf_Size*** + size in bytes of the variable-length clustering key columns not in the set of nonclustered index key columns (+ 4 if the clustered index is nonunique)</span></span>  
  
3.  <span data-ttu-id="d311e-191">Berechnen der Größe des NULL-Bitmusters:</span><span class="sxs-lookup"><span data-stu-id="d311e-191">Calculate the null bitmap size:</span></span>  
  
     <span data-ttu-id="d311e-192">***Leaf_Null_Bitmap***  = 2 + ((***Num_Leaf_Cols*** + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="d311e-192">***Leaf_Null_Bitmap***  = 2 + ((***Num_Leaf_Cols*** + 7) / 8)</span></span>  
  
     <span data-ttu-id="d311e-193">Nur der ganzzahlige Teil des vorherigen Ausdrucks darf verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d311e-193">Only the integer part of the previous expression should be used.</span></span> <span data-ttu-id="d311e-194">Der Rest wird verworfen.</span><span class="sxs-lookup"><span data-stu-id="d311e-194">Discard any remainder.</span></span>  
  
4.  <span data-ttu-id="d311e-195">Berechnen Sie die Größe der Daten variabler Länge:</span><span class="sxs-lookup"><span data-stu-id="d311e-195">Calculate the variable length data size:</span></span>  
  
     <span data-ttu-id="d311e-196">Wenn der Indexschlüssel Spalten variabler Länge enthält (einschließlich erforderlicher Gruppierungsschlüsselspalten wie zuvor in Schritt 2.2 beschrieben), müssen Sie ermitteln, wie viel Speicherplatz zum Speichern der Spalten innerhalb der Indexzeile verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="d311e-196">If there are variable-length columns in the index key, including any necessary clustering key columns as described previously in Step 2.2, determine how much space is used to store the columns within the index row:</span></span>  
  
     <span data-ttu-id="d311e-197">***Variable_Leaf_Size***  = 2 + (***Num_Variable_Leaf_Cols*** x 2) + ***Max_Var_Leaf_Size***</span><span class="sxs-lookup"><span data-stu-id="d311e-197">***Variable_Leaf_Size***  = 2 + (***Num_Variable_Leaf_Cols*** x 2) + ***Max_Var_Leaf_Size***</span></span>  
  
     <span data-ttu-id="d311e-198">Die zu ***Max_Var_Key_Size*** hinzugefügten Bytes dienen der Nachverfolgung jeder einzelnen Variablenspalte. Bei dieser Formel wird angenommen, dass alle Spalten variabler Länge zu 100 Prozent gefüllt sind.</span><span class="sxs-lookup"><span data-stu-id="d311e-198">The bytes added to ***Max_Var_Key_Size*** are for tracking each variable column.This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="d311e-199">Wenn sich abzeichnet, dass ein niedrigerer Prozentsatz des Speicherplatzes für Spalten variabler Länge verwendet wird, können Sie den ***Max_Var_Leaf_Size*** -Wert mithilfe dieses Prozentsatzes anpassen, um einen genaueren Schätzwert für die Gesamtgröße der Tabelle zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d311e-199">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Leaf_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
     <span data-ttu-id="d311e-200">Wenn keine Spalten variabler Länge vorhanden sind, legen Sie ***Variable_Leaf_Size*** auf 0 fest.</span><span class="sxs-lookup"><span data-stu-id="d311e-200">If there are no variable-length columns, set ***Variable_Leaf_Size*** to 0.</span></span>  
  
5.  <span data-ttu-id="d311e-201">Berechnen Sie die Länge der Indexzeile:</span><span class="sxs-lookup"><span data-stu-id="d311e-201">Calculate the index row size:</span></span>  
  
     <span data-ttu-id="d311e-202">***Leaf_Row_Size***   =  ***Fixed_Leaf_Size***  +  ***Variable_Leaf_Size***  +  ***Leaf_Null_Bitmap*** + 1 (für Zeilen Überschriften Aufwand einer Index Zeile) + 6 (für den ID-Zeiger der untergeordneten Seite)</span><span class="sxs-lookup"><span data-stu-id="d311e-202">***Leaf_Row_Size***  = ***Fixed_Leaf_Size*** + ***Variable_Leaf_Size*** + ***Leaf_Null_Bitmap*** + 1 (for row header overhead of an index row) + 6 (for the child page ID pointer)</span></span>  
  
6.  <span data-ttu-id="d311e-203">Berechnen Sie die Anzahl der Indexzeilen pro Seite (8096 freie Byte pro Seite):</span><span class="sxs-lookup"><span data-stu-id="d311e-203">Calculate the number of index rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="d311e-204">***Leaf_Rows_Per_Page***  = 8096 / (***Leaf_Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="d311e-204">***Leaf_Rows_Per_Page***  = 8096 / (***Leaf_Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="d311e-205">Da sich eine Indexzeile nicht auf zwei Seiten erstreckt, muss die Anzahl der Indexzeilen pro Seite auf die nächste ganze Zeile abgerundet werden.</span><span class="sxs-lookup"><span data-stu-id="d311e-205">Because index rows do not span pages, the number of index rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="d311e-206">Die Angabe 2 in der Formel bezieht sich auf den Eingang der Zeile in das Slotarray der Seite.</span><span class="sxs-lookup"><span data-stu-id="d311e-206">The 2 in the formula is for the row's entry in the page's slot array.</span></span>  
  
7.  <span data-ttu-id="d311e-207">Berechnen Sie die Anzahl der reservierten freien Zeilen pro Seite anhand des angegebenen [Füllfaktors](../indexes/specify-fill-factor-for-an-index.md) :</span><span class="sxs-lookup"><span data-stu-id="d311e-207">Calculate the number of reserved free rows per page, based on the [fill factor](../indexes/specify-fill-factor-for-an-index.md) specified:</span></span>  
  
     <span data-ttu-id="d311e-208">***Free_Rows_Per_Page***  = 8096 x ((100 - ***Fill_Factor***) / 100) / (***Leaf_Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="d311e-208">***Free_Rows_Per_Page***  = 8096 x ((100 - ***Fill_Factor***) / 100) / (***Leaf_Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="d311e-209">Bei dem in der Berechnung verwendeten Füllfaktor handelt es sich nicht um einen Prozentwert, sondern um einen ganzzahligen Wert.</span><span class="sxs-lookup"><span data-stu-id="d311e-209">The fill factor used in the calculation is an integer value instead of a percentage.</span></span> <span data-ttu-id="d311e-210">Da sich eine Zeile nicht auf zwei Seiten erstreckt, muss die Anzahl der Zeilen pro Seite auf die nächste ganze Zeile abgerundet werden.</span><span class="sxs-lookup"><span data-stu-id="d311e-210">Because rows do not span pages, the number of rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="d311e-211">Mit ansteigendem Füllfaktor werden mehr Daten auf jeder Seite gespeichert, und die Anzahl der Seiten nimmt ab.</span><span class="sxs-lookup"><span data-stu-id="d311e-211">As the fill factor grows, more data will be stored on each page and there will be fewer pages.</span></span> <span data-ttu-id="d311e-212">Die Angabe 2 in der Formel bezieht sich auf den Eingang der Zeile in das Slotarray der Seite.</span><span class="sxs-lookup"><span data-stu-id="d311e-212">The 2 in the formula is for the row's entry in the page's slot array.</span></span>  
  
8.  <span data-ttu-id="d311e-213">Berechnen Sie die Anzahl der Seiten, die zum Speichern aller Zeilen benötigt werden:</span><span class="sxs-lookup"><span data-stu-id="d311e-213">Calculate the number of pages required to store all the rows:</span></span>  
  
     <span data-ttu-id="d311e-214">***Num_Leaf_Pages***  = ***Num_Rows*** / (***Leaf_Rows_Per_Page*** - ***Free_Rows_Per_Page***)</span><span class="sxs-lookup"><span data-stu-id="d311e-214">***Num_Leaf_Pages***  = ***Num_Rows*** / (***Leaf_Rows_Per_Page*** - ***Free_Rows_Per_Page***)</span></span>  
  
     <span data-ttu-id="d311e-215">Die geschätzte Seitenanzahl muss auf die nächste ganze Seite aufgerundet werden.</span><span class="sxs-lookup"><span data-stu-id="d311e-215">The number of pages estimated should be rounded up to the nearest whole page.</span></span>  
  
9. <span data-ttu-id="d311e-216">Berechnen Sie die Größe des Indexes (insgesamt 8.192 Byte pro Seite):</span><span class="sxs-lookup"><span data-stu-id="d311e-216">Calculate the size of the index (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="d311e-217">***Leaf_Space_Used***  = 8192 x ***Num_Leaf_Pages***</span><span class="sxs-lookup"><span data-stu-id="d311e-217">***Leaf_Space_Used***  = 8192 x ***Num_Leaf_Pages***</span></span>  
  
## <a name="step-3-calculate-the-space-used-to-store-index-information-in-the-non-leaf-levels"></a><span data-ttu-id="d311e-218">Schritt 3:</span><span class="sxs-lookup"><span data-stu-id="d311e-218">Step 3.</span></span> <span data-ttu-id="d311e-219">Berechnen des Speicherplatzes, der zum Speichern der Indexinformationen in den inneren Knotenebenen verwendet wird</span><span class="sxs-lookup"><span data-stu-id="d311e-219">Calculate the Space Used to Store Index Information in the Non-leaf Levels</span></span>  
 <span data-ttu-id="d311e-220">Befolgen Sie diese Schritte, um abzuschätzen, wie viel Speicherplatz zum Speichern der Zwischen- und Stammebenen des Indexes erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d311e-220">Follow these steps to estimate the amount of space that is required to store the intermediate and root levels of the index.</span></span> <span data-ttu-id="d311e-221">Sie benötigen die in Schritt 2 und 3 errechneten Werte, um diesen Schritt durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="d311e-221">You will need the values preserved from steps 2 and 3 to complete this step.</span></span>  
  
1.  <span data-ttu-id="d311e-222">Berechnen Sie die Anzahl der inneren Knotenebenen im Index:</span><span class="sxs-lookup"><span data-stu-id="d311e-222">Calculate the number of non-leaf levels in the index:</span></span>  
  
     <span data-ttu-id="d311e-223">***Nicht Blatt Ebenen*** = 1 + Protokoll Index_Rows_Per_Page (***Num_Leaf_Pages***  /  ***Index_Rows_Per_Page***)</span><span class="sxs-lookup"><span data-stu-id="d311e-223">***Non-leaf Levels***  = 1 + log Index_Rows_Per_Page (***Num_Leaf_Pages*** / ***Index_Rows_Per_Page***)</span></span>  
  
     <span data-ttu-id="d311e-224">Runden Sie diese Zahl auf die nächste ganze Zahl auf.</span><span class="sxs-lookup"><span data-stu-id="d311e-224">Round this value up to the nearest whole number.</span></span> <span data-ttu-id="d311e-225">Dieser Wert schließt die Blattebene des nicht gruppierten Index nicht mit ein.</span><span class="sxs-lookup"><span data-stu-id="d311e-225">This value does not include the leaf level of the nonclustered index.</span></span>  
  
2.  <span data-ttu-id="d311e-226">Berechnen Sie die Anzahl der inneren Knotenseiten im Index:</span><span class="sxs-lookup"><span data-stu-id="d311e-226">Calculate the number of non-leaf pages in the index:</span></span>  
  
     <span data-ttu-id="d311e-227">***Num_Index_Pages*** = ∑ Level (***Num_Leaf_Pages/Index_Rows_Per_Page***<sup>Ebene</sup>), wobei 1 <= Level <= ***Levels***</span><span class="sxs-lookup"><span data-stu-id="d311e-227">***Num_Index_Pages***  = ∑Level (***Num_Leaf_Pages/Index_Rows_Per_Page***<sup>Level</sup>)where 1 <= Level <= ***Levels***</span></span>  
  
     <span data-ttu-id="d311e-228">Runden Sie jeden Summanden auf die nächste ganze Zahl auf.</span><span class="sxs-lookup"><span data-stu-id="d311e-228">Round each summand up to the nearest whole number.</span></span> <span data-ttu-id="d311e-229">Stellen Sie sich als einfaches Beispiel einen Index vor, bei dem ***Num_Leaf_Pages*** = 1000 und ***Index_Rows_Per_Page*** = 25. gilt.</span><span class="sxs-lookup"><span data-stu-id="d311e-229">As a simple example, consider an index where ***Num_Leaf_Pages*** = 1000 and ***Index_Rows_Per_Page*** = 25.</span></span> <span data-ttu-id="d311e-230">Die erste Indexebene über der Blattebene speichert 1.000 Indexzeilen, dies bedeutet eine Indexzeile pro Blattseite. Dabei passen 25 Indexzeilen auf eine Seite.</span><span class="sxs-lookup"><span data-stu-id="d311e-230">The first index level above the leaf level stores 1000 index rows, which is one index row per leaf page, and 25 index rows can fit per page.</span></span> <span data-ttu-id="d311e-231">Dies bedeutet, dass 40 Seiten zum Speichern dieser 1.000 Indexzeilen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d311e-231">This means that 40 pages are required to store those 1000 index rows.</span></span> <span data-ttu-id="d311e-232">Die nächste Ebene des Indexes muss 40 Zeilen speichern.</span><span class="sxs-lookup"><span data-stu-id="d311e-232">The next level of the index has to store 40 rows.</span></span> <span data-ttu-id="d311e-233">Dies bedeutet, dass zwei Seiten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d311e-233">This means that it requires 2 pages.</span></span> <span data-ttu-id="d311e-234">Die letzte Ebene des Indexes muss zwei Zeilen speichern.</span><span class="sxs-lookup"><span data-stu-id="d311e-234">The final level of the index has to store 2 rows.</span></span> <span data-ttu-id="d311e-235">Dies bedeutet, dass eine Seite erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d311e-235">This means that it requires 1 page.</span></span> <span data-ttu-id="d311e-236">Daraus ergeben sich 43 innere Knotenseiten im Index.</span><span class="sxs-lookup"><span data-stu-id="d311e-236">This yields 43 non-leaf index pages.</span></span> <span data-ttu-id="d311e-237">Wenn Sie diese Werte in den oben genannten Formeln verwenden, erhalten Sie folgendes Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="d311e-237">When these numbers are used in the previous formulas, the result is as follows:</span></span>  
  
     <span data-ttu-id="d311e-238">***Nicht-leaf_Levels*** = 1 + log25 (1000/25) = 3</span><span class="sxs-lookup"><span data-stu-id="d311e-238">***Non-leaf_Levels***  = 1 + log25 (1000 / 25) = 3</span></span>  
  
     <span data-ttu-id="d311e-239">***Num_Index_Pages*** = 1000/(25<sup>3</sup>) + 1000/(25<sup>2</sup>) + 1000/(25<sup>1</sup>) = 1 + 2 + 40 = 43, dies ist die Anzahl der im Beispiel beschriebenen Seiten.</span><span class="sxs-lookup"><span data-stu-id="d311e-239">***Num_Index_Pages*** = 1000/(25<sup>3</sup>)+ 1000/(25<sup>2</sup>) + 1000/(25<sup>1</sup>) = 1 + 2 + 40 = 43, which is the number of pages described in the example.</span></span>  
  
3.  <span data-ttu-id="d311e-240">Berechnen Sie die Größe des Indexes (insgesamt 8.192 Byte pro Seite):</span><span class="sxs-lookup"><span data-stu-id="d311e-240">Calculate the size of the index (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="d311e-241">***Index_Space_Used***  = 8192 x ***Num_Index_Pages***</span><span class="sxs-lookup"><span data-stu-id="d311e-241">***Index_Space_Used***  = 8192 x ***Num_Index_Pages***</span></span>  
  
## <a name="step-4-total-the-calculated-values"></a><span data-ttu-id="d311e-242">Schritt 4.</span><span class="sxs-lookup"><span data-stu-id="d311e-242">Step 4.</span></span> <span data-ttu-id="d311e-243">Addieren der berechneten Werte</span><span class="sxs-lookup"><span data-stu-id="d311e-243">Total the Calculated Values</span></span>  
 <span data-ttu-id="d311e-244">Addieren Sie die Werte, die in den beiden vorherigen Schritten erzielt wurden:</span><span class="sxs-lookup"><span data-stu-id="d311e-244">Total the values obtained from the previous two steps:</span></span>  
  
 <span data-ttu-id="d311e-245">Größe des nicht gruppierten Indexes (in Bytes) = ***Leaf_Space_Used*** + ***Index_Space_used***</span><span class="sxs-lookup"><span data-stu-id="d311e-245">Nonclustered index size (bytes) = ***Leaf_Space_Used*** + ***Index_Space_used***</span></span>  
  
 <span data-ttu-id="d311e-246">In dieser Berechnung wird Folgendes nicht berücksichtigt:</span><span class="sxs-lookup"><span data-stu-id="d311e-246">This calculation does not consider the following:</span></span>  
  
-   <span data-ttu-id="d311e-247">Partitionierung</span><span class="sxs-lookup"><span data-stu-id="d311e-247">Partitioning</span></span>  
  
     <span data-ttu-id="d311e-248">Der Speicherplatzaufwand aus der Partitionierung ist geringfügig, seine Berechnung jedoch komplex.</span><span class="sxs-lookup"><span data-stu-id="d311e-248">The space overhead from partitioning is minimal, but complex to calculate.</span></span> <span data-ttu-id="d311e-249">Er muss nicht berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="d311e-249">It is not important to include.</span></span>  
  
-   <span data-ttu-id="d311e-250">Zuordnungsseiten</span><span class="sxs-lookup"><span data-stu-id="d311e-250">Allocation pages</span></span>  
  
     <span data-ttu-id="d311e-251">Mindestens eine IAM-Seite wird zum Nachverfolgen der für einen Heap zugeordneten Seiten verwendet, der Speicherplatzaufwand ist jedoch nur minimal. Außerdem ist kein Algorithmus verfügbar, um deterministisch genau zu berechnen, wie viele IAM-Seiten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d311e-251">There is at least one IAM page used to track the pages allocated to a heap, but the space overhead is minimal and there is no algorithm to deterministically calculate exactly how many IAM pages will be used.</span></span>  
  
-   <span data-ttu-id="d311e-252">LOB-Werte (Large Object)</span><span class="sxs-lookup"><span data-stu-id="d311e-252">Large object (LOB) values</span></span>  
  
     <span data-ttu-id="d311e-253">Der Algorithmus zum Berechnen des genauen Speicherplatzes, der zum Speichern der Werte der LOB-Datentypen `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, `ntext`, `xml` und `image` erforderlich ist, ist komplex.</span><span class="sxs-lookup"><span data-stu-id="d311e-253">The algorithm to determine exactly how much space will be used to store the LOB data types `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, `ntext`, `xml`, and `image` values is complex.</span></span> <span data-ttu-id="d311e-254">Es ist ausreichend, einfach die durchschnittliche Größe der erwarteten LOB-Werte zu addieren, diese mit ***Num_Rows***zu multiplizieren und das Ergebnis dann zur Gesamtgröße des nicht gruppierten Indexes zu addieren.</span><span class="sxs-lookup"><span data-stu-id="d311e-254">It is sufficient to just add the average size of the LOB values expected, multiply by ***Num_Rows***, and add that to the total nonclustered index size.</span></span>  
  
-   <span data-ttu-id="d311e-255">Komprimierung</span><span class="sxs-lookup"><span data-stu-id="d311e-255">Compression</span></span>  
  
     <span data-ttu-id="d311e-256">Sie können die Größe eines komprimierten Index nicht im Vorfeld berechnen.</span><span class="sxs-lookup"><span data-stu-id="d311e-256">You cannot pre-calculate the size of a compressed index.</span></span>  
  
-   <span data-ttu-id="d311e-257">Spalten mit geringer Dichte</span><span class="sxs-lookup"><span data-stu-id="d311e-257">Sparse columns</span></span>  
  
     <span data-ttu-id="d311e-258">Informationen zu den Speicherplatzanforderungen von Sparsespalten finden Sie unter [Use Sparse Columns](../tables/use-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="d311e-258">For information about the space requirements of sparse columns, see [Use Sparse Columns](../tables/use-sparse-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d311e-259">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d311e-259">See Also</span></span>  
 <span data-ttu-id="d311e-260">[Beschreibung von gruppierten und nicht gruppierten Indizes](../indexes/clustered-and-nonclustered-indexes-described.md) </span><span class="sxs-lookup"><span data-stu-id="d311e-260">[Clustered and Nonclustered Indexes Described](../indexes/clustered-and-nonclustered-indexes-described.md) </span></span>  
 <span data-ttu-id="d311e-261">[Erstellen nicht gruppierter Indizes](../indexes/create-nonclustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="d311e-261">[Create Nonclustered Indexes](../indexes/create-nonclustered-indexes.md) </span></span>  
 <span data-ttu-id="d311e-262">[Erstellen gruppierter Indizes](../indexes/create-clustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="d311e-262">[Create Clustered Indexes](../indexes/create-clustered-indexes.md) </span></span>  
 <span data-ttu-id="d311e-263">[Schätzen der Größe einer Tabelle](estimate-the-size-of-a-table.md) </span><span class="sxs-lookup"><span data-stu-id="d311e-263">[Estimate the Size of a Table](estimate-the-size-of-a-table.md) </span></span>  
 <span data-ttu-id="d311e-264">[Schätzen der Größe eines gruppierten Indexes](estimate-the-size-of-a-clustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="d311e-264">[Estimate the Size of a Clustered Index](estimate-the-size-of-a-clustered-index.md) </span></span>  
 <span data-ttu-id="d311e-265">[Schätzen der Größe eines Heaps](estimate-the-size-of-a-heap.md) </span><span class="sxs-lookup"><span data-stu-id="d311e-265">[Estimate the Size of a Heap](estimate-the-size-of-a-heap.md) </span></span>  
 [<span data-ttu-id="d311e-266">Schätzen der Größe einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="d311e-266">Estimate the Size of a Database</span></span>](estimate-the-size-of-a-database.md)  
  
  
