---
title: Schätzen der Größe eines gruppierten Indexes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- space allocation [SQL Server], index size
- size [SQL Server], tables
- disk space [SQL Server], indexes
- predicting table size [SQL Server]
- table size [SQL Server]
- estimating table size
- space [SQL Server], indexes
- clustered indexes, table size
- nonclustered indexes [SQL Server], table size
- designing databases [SQL Server], estimating size
- calculating table size
ms.assetid: 2b5137f8-98ad-46b5-9aae-4c980259bf8d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4d224c5ae55cc5ec7690ca0962cbc2130bac22e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725870"
---
# <a name="estimate-the-size-of-a-clustered-index"></a><span data-ttu-id="2cfc7-102">Schätzen der Größe eines gruppierten Indexes</span><span class="sxs-lookup"><span data-stu-id="2cfc7-102">Estimate the Size of a Clustered Index</span></span>
  <span data-ttu-id="2cfc7-103">Mit den folgenden Schritten können Sie den Umfang des Speicherplatzes schätzen, der zum Speichern eines gruppierten Indexes erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="2cfc7-103">You can use the following steps to estimate the amount of space that is required to store data in a clustered index:</span></span>  
  
1.  <span data-ttu-id="2cfc7-104">Berechnen des Speicherplatzes, der zum Speichern der Daten in der Blattebene des gruppierten Indexes erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-104">Calculate the space used to store data in the leaf level of the clustered index.</span></span>  
  
2.  <span data-ttu-id="2cfc7-105">Berechnen des Speicherplatzes, der zum Speichern von Indexinformationen für den gruppierten Index verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-105">Calculate the space used to store index information for the clustered index.</span></span>  
  
3.  <span data-ttu-id="2cfc7-106">Addieren Sie die berechneten Werte.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-106">Total the calculated values.</span></span>  
  
## <a name="step-1-calculate-the-space-used-to-store-data-in-the-leaf-level"></a><span data-ttu-id="2cfc7-107">Schritt 1:</span><span class="sxs-lookup"><span data-stu-id="2cfc7-107">Step 1.</span></span> <span data-ttu-id="2cfc7-108">Berechnen des Speicherplatzes, der zum Speichern der Daten in der Blattebene verwendet wird</span><span class="sxs-lookup"><span data-stu-id="2cfc7-108">Calculate the Space Used to Store Data in the Leaf Level</span></span>  
  
1.  <span data-ttu-id="2cfc7-109">Geben Sie die Anzahl der Zeilen an, die die Tabelle enthalten wird:</span><span class="sxs-lookup"><span data-stu-id="2cfc7-109">Specify the number of rows that will be present in the table:</span></span>  
  
     <span data-ttu-id="2cfc7-110">***Num_Rows***  = Anzahl der Zeilen in der Tabelle</span><span class="sxs-lookup"><span data-stu-id="2cfc7-110">***Num_Rows***  = number of rows in the table</span></span>  
  
2.  <span data-ttu-id="2cfc7-111">Geben Sie die Anzahl der Spalten mit fester und mit variabler Länge an, und berechnen Sie den Speicherplatz, der für deren Speicherung erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="2cfc7-111">Specify the number of fixed-length and variable-length columns and calculate the space that is required for their storage:</span></span>  
  
     <span data-ttu-id="2cfc7-112">Berechnen Sie den Speicherplatz, der zum Speichern jeder dieser Spaltengruppen innerhalb der Datenzeile erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-112">Calculate the space that each of these groups of columns occupies within the data row.</span></span> <span data-ttu-id="2cfc7-113">Die Größe einer Spalte hängt von der Angabe für Datentyp und -länge ab.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-113">The size of a column depends on the data type and length specification.</span></span>  
  
     <span data-ttu-id="2cfc7-114">***Num_Cols***  = Gesamtanzahl der Spalten (mit fester und variabler Länge)</span><span class="sxs-lookup"><span data-stu-id="2cfc7-114">***Num_Cols***  = total number of columns (fixed-length and variable-length)</span></span>  
  
     <span data-ttu-id="2cfc7-115">***Fixed_Data_Size***  = Gesamtzahl der Bytes in allen Spalten fester Länge</span><span class="sxs-lookup"><span data-stu-id="2cfc7-115">***Fixed_Data_Size***  = total byte size of all fixed-length columns</span></span>  
  
     <span data-ttu-id="2cfc7-116">***Num_Variable_Cols***  = Anzahl der Spalten variabler Länge</span><span class="sxs-lookup"><span data-stu-id="2cfc7-116">***Num_Variable_Cols***  = number of variable-length columns</span></span>  
  
     <span data-ttu-id="2cfc7-117">***Max_Var_Size***  = Maximale Bytegröße aller Spalten variabler Länge</span><span class="sxs-lookup"><span data-stu-id="2cfc7-117">***Max_Var_Size***  = maximum byte size of all variable-length columns</span></span>  
  
3.  <span data-ttu-id="2cfc7-118">Wenn der gruppierte Index nicht eindeutig ist, berücksichtigen Sie die *uniqueifier* -Spalte:</span><span class="sxs-lookup"><span data-stu-id="2cfc7-118">If the clustered index is nonunique, account for the *uniqueifier* column:</span></span>  
  
     <span data-ttu-id="2cfc7-119">Die Uniqueifier-Spalte ist eine Spalte variabler Länge mit NULL-Zulässigkeit.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-119">The uniqueifier is a nullable, variable-length column.</span></span> <span data-ttu-id="2cfc7-120">Sie ist in Spalten Nicht-NULL und 4 Byte lang, deren Schlüsselwerte nicht eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-120">It will be nonnull and 4 bytes in size in rows that have nonunique key values.</span></span> <span data-ttu-id="2cfc7-121">Dieser Wert ist Teil des Indexschlüssels und für die Sicherstellung erforderlich, dass jede Zeile über einen eindeutigen Schlüsselwert verfügt.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-121">This value is part of the index key and is required to make sure that every row has a unique key value.</span></span>  
  
     <span data-ttu-id="2cfc7-122">***Num_Cols***  = ***Num_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="2cfc7-122">***Num_Cols***  = ***Num_Cols*** + 1</span></span>  
  
     <span data-ttu-id="2cfc7-123">***Num_Variable_Cols***  = ***Num_Variable_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="2cfc7-123">***Num_Variable_Cols***  = ***Num_Variable_Cols*** + 1</span></span>  
  
     <span data-ttu-id="2cfc7-124">***Max_Var_Size***  = ***Max_Var_Size*** + 4</span><span class="sxs-lookup"><span data-stu-id="2cfc7-124">***Max_Var_Size***  = ***Max_Var_Size*** + 4</span></span>  
  
     <span data-ttu-id="2cfc7-125">Diese Änderungen gehen davon aus, dass alle Werte nicht eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-125">These modifications assume that all values will be nonunique.</span></span>  
  
4.  <span data-ttu-id="2cfc7-126">Ein Teil der Zeile, der als NULL-Bitmuster (Null_Bitmap) bezeichnet wird, wird für das Verwalten der NULL-Zulässigkeit der Spalte reserviert.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-126">Part of the row, known as the null bitmap, is reserved to manage column nullability.</span></span> <span data-ttu-id="2cfc7-127">Berechnen Sie dessen Größe:</span><span class="sxs-lookup"><span data-stu-id="2cfc7-127">Calculate its size:</span></span>  
  
     <span data-ttu-id="2cfc7-128">***Null_Bitmap***  = 2 + ((***Num_Cols*** + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="2cfc7-128">***Null_Bitmap***  = 2 + ((***Num_Cols*** + 7) / 8)</span></span>  
  
     <span data-ttu-id="2cfc7-129">Nur der ganzzahlige Teil des oben aufgeführten Ausdrucks sollte verwendet werden; verwerfen Sie den Nachkommateil.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-129">Only the integer part of the previous expression should be used; discard any remainder.</span></span>  
  
5.  <span data-ttu-id="2cfc7-130">Berechnen Sie die Größe der Daten variabler Länge:</span><span class="sxs-lookup"><span data-stu-id="2cfc7-130">Calculate the variable-length data size:</span></span>  
  
     <span data-ttu-id="2cfc7-131">Wenn die Tabelle Spalten variabler Länge enthält, müssen Sie den Speicherplatz ermitteln, der von den Spalten innerhalb der Zeile verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="2cfc7-131">If there are variable-length columns in the table, determine how much space is used to store the columns within the row:</span></span>  
  
     <span data-ttu-id="2cfc7-132">***Variable_Data_Size***  = 2 + (***Num_Variable_Cols*** x 2) + ***Max_Var_Size***</span><span class="sxs-lookup"><span data-stu-id="2cfc7-132">***Variable_Data_Size***  = 2 + (***Num_Variable_Cols*** x 2) + ***Max_Var_Size***</span></span>  
  
     <span data-ttu-id="2cfc7-133">Die zu ***Max_Var_Size*** hinzugefügten Bytes dienen der Nachverfolgung jeder einzelnen variablen Spalte.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-133">The bytes added to ***Max_Var_Size*** are for tracking each variable column.</span></span> <span data-ttu-id="2cfc7-134">Bei dieser Formel wird angenommen, dass alle Spalten variabler Länge zu 100 % gefüllt sind.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-134">This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="2cfc7-135">Wenn sich abzeichnet, dass ein niedrigerer Prozentsatz des Speicherplatzes für Spalten variabler Länge verwendet wird, können Sie den ***Max_Var_Size*** -Wert mithilfe dieses Prozentsatzes anpassen, um einen genaueren Schätzwert für die Gesamtgröße der Tabelle zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-135">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2cfc7-136">Sie können `varchar`-, `nvarchar`-, `varbinary`- oder `sql_variant`-Spalten kombinieren, mit dem Ergebnis, dass die definierte Tabellengesamtbreite größer als 8.060 Byte ist.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-136">You can combine `varchar`, `nvarchar`, `varbinary`, or `sql_variant` columns that cause the total defined table width to exceed 8,060 bytes.</span></span> <span data-ttu-id="2cfc7-137">Die Länge jeder einzelnen Spalte unterliegt auch weiterhin der Beschränkung von 8.000 Byte für eine `varchar`-, `varbinary`- oder `sql_variant`-Spalte und von 4.000 Byte für `nvarchar`-Spalten.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-137">The length of each one of these columns must still fall within the limit of 8,000 bytes for a `varchar`, `varbinary`, or `sql_variant` column, and 4,000 bytes for `nvarchar` columns.</span></span> <span data-ttu-id="2cfc7-138">Die kombinierte Breite kann jedoch den Grenzwert von 8.060 Byte in einer Tabelle überschreiten.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-138">However, their combined widths may exceed the 8,060 byte limit in a table.</span></span>  
  
     <span data-ttu-id="2cfc7-139">Wenn keine Spalten variabler Länge vorhanden sind, legen Sie ***Variable_Data_Size*** auf 0 fest.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-139">If there are no variable-length columns, set ***Variable_Data_Size*** to 0.</span></span>  
  
6.  <span data-ttu-id="2cfc7-140">Berechnen Sie die Gesamtzeilenlänge:</span><span class="sxs-lookup"><span data-stu-id="2cfc7-140">Calculate the total row size:</span></span>  
  
     <span data-ttu-id="2cfc7-141">***Row_Size***  = ***Fixed_Data_Size*** + ***Variable_Data_Size*** + ***Null_Bitmap*** + 4</span><span class="sxs-lookup"><span data-stu-id="2cfc7-141">***Row_Size***  = ***Fixed_Data_Size*** + ***Variable_Data_Size*** + ***Null_Bitmap*** + 4</span></span>  
  
     <span data-ttu-id="2cfc7-142">Der Wert 4 ist der Zeilenüberschriftenaufwand der Datenzeile.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-142">The value 4 is the row header overhead of a data row.</span></span>  
  
7.  <span data-ttu-id="2cfc7-143">Berechnen Sie die Anzahl der Zeilen pro Seite (8.096 freie Byte pro Seite):</span><span class="sxs-lookup"><span data-stu-id="2cfc7-143">Calculate the number of rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="2cfc7-144">***Rows_Per_Page***  = 8096 / (***Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="2cfc7-144">***Rows_Per_Page***  = 8096 / (***Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="2cfc7-145">Da sich eine Zeile nicht auf zwei Seiten erstreckt, muss die Anzahl der Zeilen pro Seite auf die nächste ganze Zeile abgerundet werden.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-145">Because rows do not span pages, the number of rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="2cfc7-146">Die Angabe 2 in der Formel bezieht sich auf den Eingang der Zeile in das Slotarray der Seite.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-146">The value 2 in the formula is for the row's entry in the slot array of the page.</span></span>  
  
8.  <span data-ttu-id="2cfc7-147">Berechnen Sie die Anzahl der reservierten freien Zeilen pro Seite anhand des angegebenen [Füllfaktors](../indexes/specify-fill-factor-for-an-index.md) :</span><span class="sxs-lookup"><span data-stu-id="2cfc7-147">Calculate the number of reserved free rows per page, based on the [fill factor](../indexes/specify-fill-factor-for-an-index.md) specified:</span></span>  
  
     <span data-ttu-id="2cfc7-148">***Free_Rows_Per_Page***  = 8096 x ((100 - ***Fill_Factor***) / 100) / (***Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="2cfc7-148">***Free_Rows_Per_Page***  = 8096 x ((100 - ***Fill_Factor***) / 100) / (***Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="2cfc7-149">Bei dem in der Berechnung verwendeten Füllfaktor handelt es sich nicht um einen Prozentwert, sondern um einen ganzzahligen Wert.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-149">The fill factor used in the calculation is an integer value instead of a percentage.</span></span> <span data-ttu-id="2cfc7-150">Da sich eine Zeile nicht auf zwei Seiten erstreckt, muss die Anzahl der Zeilen pro Seite auf die nächste ganze Zeile abgerundet werden.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-150">Because rows do not span pages, the number of rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="2cfc7-151">Mit ansteigendem Füllfaktor werden mehr Daten auf jeder Seite gespeichert, und die Anzahl der Seiten nimmt ab.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-151">As the fill factor grows, more data will be stored on each page and there will be fewer pages.</span></span> <span data-ttu-id="2cfc7-152">Die Angabe 2 in der Formel bezieht sich auf den Eingang der Zeile in das Slotarray der Seite.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-152">The value 2 in the formula is for the row's entry in the slot array of the page.</span></span>  
  
9. <span data-ttu-id="2cfc7-153">Berechnen Sie die Anzahl der Seiten, die zum Speichern aller Zeilen benötigt werden:</span><span class="sxs-lookup"><span data-stu-id="2cfc7-153">Calculate the number of pages required to store all the rows:</span></span>  
  
     <span data-ttu-id="2cfc7-154">***Num_Leaf_Pages***  = ***Num_Rows*** / (***Rows_Per_Page*** - ***Free_Rows_Per_Page***)</span><span class="sxs-lookup"><span data-stu-id="2cfc7-154">***Num_Leaf_Pages***  = ***Num_Rows*** / (***Rows_Per_Page*** - ***Free_Rows_Per_Page***)</span></span>  
  
     <span data-ttu-id="2cfc7-155">Die geschätzte Seitenanzahl muss auf die nächste ganze Seite aufgerundet werden.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-155">The number of pages estimated should be rounded up to the nearest whole page.</span></span>  
  
10. <span data-ttu-id="2cfc7-156">Berechnen Sie den Umfang des Speicherplatzes, der zum Speichern der Daten in der Blattebene erforderlich ist (insgesamt 8192 Byte pro Seite):</span><span class="sxs-lookup"><span data-stu-id="2cfc7-156">Calculate the amount of space that is required to store the data in the leaf level (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="2cfc7-157">***Leaf_space_used***  = 8192 x ***Num_Leaf_Pages***</span><span class="sxs-lookup"><span data-stu-id="2cfc7-157">***Leaf_space_used***  = 8192 x ***Num_Leaf_Pages***</span></span>  
  
## <a name="step-2-calculate-the-space-used-to-store-index-information"></a><span data-ttu-id="2cfc7-158">Schritt 2:</span><span class="sxs-lookup"><span data-stu-id="2cfc7-158">Step 2.</span></span> <span data-ttu-id="2cfc7-159">Berechnen des Speicherplatzes, der zum Speichern der Indexinformationen verwendet wird</span><span class="sxs-lookup"><span data-stu-id="2cfc7-159">Calculate the Space Used to Store Index Information</span></span>  
 <span data-ttu-id="2cfc7-160">Mit den folgenden Schritten können Sie den Umfang des Speicherplatzes schätzen, der zum Speichern der oberen Ebenen des Indexes erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="2cfc7-160">You can use the following steps to estimate the amount of space that is required to store the upper levels of the index:</span></span>  
  
1.  <span data-ttu-id="2cfc7-161">Geben Sie die Anzahl der Spalten mit fester und mit variabler Länge im Indexschlüssel an, und berechnen Sie den Speicherplatz, der für deren Speicherung erforderlich ist:</span><span class="sxs-lookup"><span data-stu-id="2cfc7-161">Specify the number of fixed-length and variable-length columns in the index key and calculate the space that is required for their storage:</span></span>  
  
     <span data-ttu-id="2cfc7-162">Die Schlüsselspalten eines Indexes können Spalten fester und variabler Länge enthalten.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-162">The key columns of an index can include fixed-length and variable-length columns.</span></span> <span data-ttu-id="2cfc7-163">Um die Größe der Indexzeilen auf der inneren Ebene zu schätzen, müssen Sie den Speicherplatz berechnen, der von jeder dieser Spaltengruppen innerhalb der Indexzeile belegt wird.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-163">To estimate the interior level index row size, calculate the space that each of these groups of columns occupies within the index row.</span></span> <span data-ttu-id="2cfc7-164">Die Größe einer Spalte hängt von der Angabe für Datentyp und -länge ab.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-164">The size of a column depends on the data type and length specification.</span></span>  
  
     <span data-ttu-id="2cfc7-165">***Num_Key_Cols***  = Gesamtanzahl der Schlüsselspalten (fester und variabler Länge)</span><span class="sxs-lookup"><span data-stu-id="2cfc7-165">***Num_Key_Cols***  = total number of key columns (fixed-length and variable-length)</span></span>  
  
     <span data-ttu-id="2cfc7-166">***Fixed_Key_Size***  = Gesamtzahl der Bytes in allen Schlüsselspalten fester Länge</span><span class="sxs-lookup"><span data-stu-id="2cfc7-166">***Fixed_Key_Size***  = total byte size of all fixed-length key columns</span></span>  
  
     <span data-ttu-id="2cfc7-167">***Num_Variable_Key_Cols***  = Anzahl der Schlüsselspalten variabler Länge</span><span class="sxs-lookup"><span data-stu-id="2cfc7-167">***Num_Variable_Key_Cols***  = number of variable-length key columns</span></span>  
  
     <span data-ttu-id="2cfc7-168">***Max_Var_Key_Size***  = Maximale Bytegröße aller Schlüsselspalten variabler Länge</span><span class="sxs-lookup"><span data-stu-id="2cfc7-168">***Max_Var_Key_Size***  = maximum byte size of all variable-length key columns</span></span>  
  
2.  <span data-ttu-id="2cfc7-169">Berücksichtigen Sie ggf. den Uniqueifier, der erforderlich ist, wenn der Index nicht eindeutig ist:</span><span class="sxs-lookup"><span data-stu-id="2cfc7-169">Account for any uniqueifier needed if the index is nonunique:</span></span>  
  
     <span data-ttu-id="2cfc7-170">Die Uniqueifier-Spalte ist eine Spalte variabler Länge mit NULL-Zulässigkeit.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-170">The uniqueifier is a nullable, variable-length column.</span></span> <span data-ttu-id="2cfc7-171">Sie ist in Spalten Nicht-NULL und 4 Byte lang, deren Indexschlüsselwerte nicht eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-171">It will be nonnull and 4 bytes in size in rows that have nonunique index key values.</span></span> <span data-ttu-id="2cfc7-172">Dieser Wert ist Teil des Indexschlüssels und für die Sicherstellung erforderlich, dass jede Zeile über einen eindeutigen Schlüsselwert verfügt.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-172">This value is part of the index key and is required to make sure that every row has a unique key value.</span></span>  
  
     <span data-ttu-id="2cfc7-173">***Num_Key_Cols***  = ***Num_Key_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="2cfc7-173">***Num_Key_Cols***  = ***Num_Key_Cols*** + 1</span></span>  
  
     <span data-ttu-id="2cfc7-174">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + 1</span><span class="sxs-lookup"><span data-stu-id="2cfc7-174">***Num_Variable_Key_Cols***  = ***Num_Variable_Key_Cols*** + 1</span></span>  
  
     <span data-ttu-id="2cfc7-175">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + 4</span><span class="sxs-lookup"><span data-stu-id="2cfc7-175">***Max_Var_Key_Size***  = ***Max_Var_Key_Size*** + 4</span></span>  
  
     <span data-ttu-id="2cfc7-176">Diese Änderungen gehen davon aus, dass alle Werte nicht eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-176">These modifications assume that all values will be nonunique.</span></span>  
  
3.  <span data-ttu-id="2cfc7-177">Berechnen der Größe des NULL-Bitmusters:</span><span class="sxs-lookup"><span data-stu-id="2cfc7-177">Calculate the null bitmap size:</span></span>  
  
     <span data-ttu-id="2cfc7-178">Wenn der Index Spalten mit NULL-Zulässigkeit enthält, ist ein Teil der Indexzeile dem NULL-Bitmuster zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-178">If there are nullable columns in the index key, part of the index row is reserved for the null bitmap.</span></span> <span data-ttu-id="2cfc7-179">Berechnen Sie dessen Größe:</span><span class="sxs-lookup"><span data-stu-id="2cfc7-179">Calculate its size:</span></span>  
  
     <span data-ttu-id="2cfc7-180">***Index_Null_Bitmap***  = 2 + ((Anzahl der Spalten in der Indexzeile + 7) / 8)</span><span class="sxs-lookup"><span data-stu-id="2cfc7-180">***Index_Null_Bitmap***  = 2 + ((number of columns in the index row + 7) / 8)</span></span>  
  
     <span data-ttu-id="2cfc7-181">Nur der ganzzahlige Teil des vorherigen Ausdrucks darf verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-181">Only the integer part of the previous expression should be used.</span></span> <span data-ttu-id="2cfc7-182">Der Rest wird verworfen.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-182">Discard any remainder.</span></span>  
  
     <span data-ttu-id="2cfc7-183">Wenn keine Schlüsselspalten vorhanden sind, die NULL-Werte zulassen, legen Sie ***Index_Null_Bitmap*** auf 0 fest.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-183">If there are no nullable key columns, set ***Index_Null_Bitmap*** to 0.</span></span>  
  
4.  <span data-ttu-id="2cfc7-184">Berechnen Sie die Größe der Daten variabler Länge:</span><span class="sxs-lookup"><span data-stu-id="2cfc7-184">Calculate the variable-length data size:</span></span>  
  
     <span data-ttu-id="2cfc7-185">Wenn der Index Spalten variabler Länge enthält, müssen Sie den Speicherplatz ermitteln, der von den Spalten innerhalb der Indexzeile verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="2cfc7-185">If there are variable-length columns in the index, determine how much space is used to store the columns within the index row:</span></span>  
  
     <span data-ttu-id="2cfc7-186">***Variable_Key_Size***  = 2 + (***Num_Variable_Key_Cols*** x 2) + ***Max_Var_Key_Size***</span><span class="sxs-lookup"><span data-stu-id="2cfc7-186">***Variable_Key_Size***  = 2 + (***Num_Variable_Key_Cols*** x 2) + ***Max_Var_Key_Size***</span></span>  
  
     <span data-ttu-id="2cfc7-187">Die zu ***Max_Var_Key_Size*** hinzugefügten Bytes dienen der Nachverfolgung der einzelnen Spalten variabler Länge.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-187">The bytes added to ***Max_Var_Key_Size*** are for tracking each variable-length column.</span></span> <span data-ttu-id="2cfc7-188">Bei dieser Formel wird angenommen, dass alle Spalten variabler Länge zu 100 % gefüllt sind.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-188">This formula assumes that all variable-length columns are 100 percent full.</span></span> <span data-ttu-id="2cfc7-189">Wenn sich abzeichnet, dass ein niedrigerer Prozentsatz des Speicherplatzes für Spalten variabler Länge verwendet wird, können Sie den ***Max_Var_Key_Size*** -Wert mithilfe dieses Prozentsatzes anpassen, um einen genaueren Schätzwert für die Gesamtgröße der Tabelle zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-189">If you anticipate that a smaller percentage of the variable-length column storage space will be used, you can adjust the ***Max_Var_Key_Size*** value by that percentage to yield a more accurate estimate of the overall table size.</span></span>  
  
     <span data-ttu-id="2cfc7-190">Wenn keine Spalten variabler Länge vorhanden sind, legen Sie ***Variable_Key_Size*** auf 0 fest.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-190">If there are no variable-length columns, set ***Variable_Key_Size*** to 0.</span></span>  
  
5.  <span data-ttu-id="2cfc7-191">Berechnen Sie die Länge der Indexzeile:</span><span class="sxs-lookup"><span data-stu-id="2cfc7-191">Calculate the index row size:</span></span>  
  
     <span data-ttu-id="2cfc7-192">***Index_Row_Size***  = ***Fixed_Key_Size*** + ***Variable_Key_Size*** + ***Index_Null_Bitmap*** + 1 (für Zeilenüberschriftenaufwand einer Indexzeile) + 6 (für ID-Zeiger der untergeordneten Seite)</span><span class="sxs-lookup"><span data-stu-id="2cfc7-192">***Index_Row_Size***  = ***Fixed_Key_Size*** + ***Variable_Key_Size*** + ***Index_Null_Bitmap*** + 1 (for row header overhead of an index row) + 6 (for the child page ID pointer)</span></span>  
  
6.  <span data-ttu-id="2cfc7-193">Berechnen Sie die Anzahl der Indexzeilen pro Seite (8096 freie Byte pro Seite):</span><span class="sxs-lookup"><span data-stu-id="2cfc7-193">Calculate the number of index rows per page (8096 free bytes per page):</span></span>  
  
     <span data-ttu-id="2cfc7-194">***Index_Rows_Per_Page***  = 8096 / (***Index_Row_Size*** + 2)</span><span class="sxs-lookup"><span data-stu-id="2cfc7-194">***Index_Rows_Per_Page***  = 8096 / (***Index_Row_Size*** + 2)</span></span>  
  
     <span data-ttu-id="2cfc7-195">Da sich eine Indexzeile nicht auf zwei Seiten erstreckt, muss die Anzahl der Indexzeilen pro Seite auf die nächste ganze Zeile abgerundet werden.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-195">Because index rows do not span pages, the number of index rows per page should be rounded down to the nearest whole row.</span></span> <span data-ttu-id="2cfc7-196">Die Angabe 2 in der Formel bezieht sich auf den Eingang der Zeile in das Slotarray der Seite.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-196">The 2 in the formula is for the row's entry in the page's slot array.</span></span>  
  
7.  <span data-ttu-id="2cfc7-197">Berechnen Sie die Anzahl der Ebenen im Index:</span><span class="sxs-lookup"><span data-stu-id="2cfc7-197">Calculate the number of levels in the index:</span></span>  
  
     <span data-ttu-id="2cfc7-198">***Nicht-leaf_Levels*** = 1 + Protokoll Index_Rows_Per_Page (***Num_Leaf_Pages***  /  ***Index_Rows_Per_Page***)</span><span class="sxs-lookup"><span data-stu-id="2cfc7-198">***Non-leaf_Levels***  = 1 + log Index_Rows_Per_Page (***Num_Leaf_Pages*** / ***Index_Rows_Per_Page***)</span></span>  
  
     <span data-ttu-id="2cfc7-199">Runden Sie diese Zahl auf die nächste ganze Zahl auf.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-199">Round this value up to the nearest whole number.</span></span> <span data-ttu-id="2cfc7-200">Dieser Wert schließt die Blattebene des gruppierten Index nicht mit ein.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-200">This value does not include the leaf level of the clustered index.</span></span>  
  
8.  <span data-ttu-id="2cfc7-201">Berechnen Sie die Anzahl der inneren Knotenseiten im Index:</span><span class="sxs-lookup"><span data-stu-id="2cfc7-201">Calculate the number of non-leaf pages in the index:</span></span>  
  
     <span data-ttu-id="2cfc7-202">***Num_Index_Pages =*** ∑ Ebene ***(Num_Leaf_Pages/(Index_Rows_Per_Page***<sup>Ebene</sup>***))***</span><span class="sxs-lookup"><span data-stu-id="2cfc7-202">***Num_Index_Pages =*** ∑Level ***(Num_Leaf_Pages / (Index_Rows_Per_Page***<sup>Level</sup>***))***</span></span>  
  
     <span data-ttu-id="2cfc7-203">wobei 1 <= Level <= ***Non-leaf_Levels***</span><span class="sxs-lookup"><span data-stu-id="2cfc7-203">where 1 <= Level <= ***Non-leaf_Levels***</span></span>  
  
     <span data-ttu-id="2cfc7-204">Runden Sie jeden Summanden auf die nächste ganze Zahl auf.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-204">Round each summand up to the nearest whole number.</span></span> <span data-ttu-id="2cfc7-205">Stellen Sie sich als einfaches Beispiel einen Index vor, bei dem ***Num_Leaf_Pages*** = 1000 und ***Index_Rows_Per_Page*** = 25. gilt.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-205">As a simple example, consider an index where ***Num_Leaf_Pages*** = 1000 and ***Index_Rows_Per_Page*** = 25.</span></span> <span data-ttu-id="2cfc7-206">Die erste Indexebene über der Blattebene speichert 1.000 Indexzeilen, dies bedeutet eine Indexzeile pro Blattseite. Dabei passen 25 Indexzeilen auf eine Seite.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-206">The first index level above the leaf level stores 1000 index rows, which is one index row per leaf page, and 25 index rows can fit per page.</span></span> <span data-ttu-id="2cfc7-207">Dies bedeutet, dass 40 Seiten zum Speichern dieser 1.000 Indexzeilen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-207">This means that 40 pages are required to store those 1000 index rows.</span></span> <span data-ttu-id="2cfc7-208">Die nächste Ebene des Indexes muss 40 Zeilen speichern.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-208">The next level of the index has to store 40 rows.</span></span> <span data-ttu-id="2cfc7-209">Dies bedeutet, dass 2 Seiten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-209">This means it requires 2 pages.</span></span> <span data-ttu-id="2cfc7-210">Die letzte Ebene des Indexes muss zwei Zeilen speichern.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-210">The final level of the index has to store 2 rows.</span></span> <span data-ttu-id="2cfc7-211">Dies bedeutet, dass eine Seite erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-211">This means it requires 1 page.</span></span> <span data-ttu-id="2cfc7-212">Daraus ergeben sich 43 innere Knotenseiten im Index.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-212">This gives 43 non-leaf index pages.</span></span> <span data-ttu-id="2cfc7-213">Wenn Sie diese Werte in den oben genannten Formeln verwenden, ergibt sich Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2cfc7-213">When these numbers are used in the previous formulas, the outcome is as follows:</span></span>  
  
     <span data-ttu-id="2cfc7-214">***Nicht-leaf_Levels*** = 1 + log25 (1000/25) = 3</span><span class="sxs-lookup"><span data-stu-id="2cfc7-214">***Non-leaf_Levels***  = 1 + log25 (1000 / 25) = 3</span></span>  
  
     <span data-ttu-id="2cfc7-215">***Num_Index_Pages*** = 1000/(25<sup>3</sup>) + 1000/(25<sup>2</sup>) + 1000/(25<sup>1</sup>) = 1 + 2 + 40 = 43, dies ist die Anzahl der im Beispiel beschriebenen Seiten.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-215">***Num_Index_Pages*** = 1000/(25<sup>3</sup>)+ 1000/(25<sup>2</sup>) + 1000/(25<sup>1</sup>) = 1 + 2 + 40 = 43, which is the number of pages described in the example.</span></span>  
  
9. <span data-ttu-id="2cfc7-216">Berechnen Sie die Größe des Indexes (insgesamt 8.192 Byte pro Seite):</span><span class="sxs-lookup"><span data-stu-id="2cfc7-216">Calculate the size of the index (8192 total bytes per page):</span></span>  
  
     <span data-ttu-id="2cfc7-217">***Index_Space_Used***  = 8192 x ***Num_Index_Pages***</span><span class="sxs-lookup"><span data-stu-id="2cfc7-217">***Index_Space_Used***  = 8192 x ***Num_Index_Pages***</span></span>  
  
## <a name="step-3-total-the-calculated-values"></a><span data-ttu-id="2cfc7-218">Schritt 3:</span><span class="sxs-lookup"><span data-stu-id="2cfc7-218">Step 3.</span></span> <span data-ttu-id="2cfc7-219">Addieren der berechneten Werte</span><span class="sxs-lookup"><span data-stu-id="2cfc7-219">Total the Calculated Values</span></span>  
 <span data-ttu-id="2cfc7-220">Addieren Sie die Werte, die in den beiden vorherigen Schritten erzielt wurden:</span><span class="sxs-lookup"><span data-stu-id="2cfc7-220">Total the values obtained from the previous two steps:</span></span>  
  
 <span data-ttu-id="2cfc7-221">Größe des gruppierten Indexes (in Bytes) = ***Leaf_Space_Used*** + ***Index_Space_used***</span><span class="sxs-lookup"><span data-stu-id="2cfc7-221">Clustered index size (bytes) = ***Leaf_Space_Used*** + ***Index_Space_used***</span></span>  
  
 <span data-ttu-id="2cfc7-222">In dieser Berechnung wird Folgendes nicht berücksichtigt:</span><span class="sxs-lookup"><span data-stu-id="2cfc7-222">This calculation does not consider the following:</span></span>  
  
-   <span data-ttu-id="2cfc7-223">Partitionierung</span><span class="sxs-lookup"><span data-stu-id="2cfc7-223">Partitioning</span></span>  
  
     <span data-ttu-id="2cfc7-224">Der Speicherplatzaufwand aus der Partitionierung ist geringfügig, seine Berechnung jedoch komplex.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-224">The space overhead from partitioning is minimal, but complex to calculate.</span></span> <span data-ttu-id="2cfc7-225">Er muss nicht berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-225">It is not important to include.</span></span>  
  
-   <span data-ttu-id="2cfc7-226">Zuordnungsseiten</span><span class="sxs-lookup"><span data-stu-id="2cfc7-226">Allocation pages</span></span>  
  
     <span data-ttu-id="2cfc7-227">Mindestens eine IAM-Seite wird zum Nachverfolgen der für einen Heap zugeordneten Seiten verwendet, der Speicherplatzaufwand ist jedoch nur minimal. Außerdem ist kein Algorithmus verfügbar, um deterministisch genau zu berechnen, wie viele IAM-Seiten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-227">There is at least one IAM page used to track the pages allocated to a heap, but the space overhead is minimal and there is no algorithm to deterministically calculate exactly how many IAM pages will be used.</span></span>  
  
-   <span data-ttu-id="2cfc7-228">LOB-Werte (Large Object)</span><span class="sxs-lookup"><span data-stu-id="2cfc7-228">Large object (LOB) values</span></span>  
  
     <span data-ttu-id="2cfc7-229">Der Algorithmus zum Berechnen des genauen Speicherplatzes, der zum Speichern der Werte der LOB-Datentypen `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, `ntext`, `xml` und `image` erforderlich ist, ist komplex.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-229">The algorithm to determine exactly how much space will be used to store the LOB data types `varchar(max)`, `varbinary(max)`, `nvarchar(max)`, `text`, `ntext`, `xml`, and `image` values is complex.</span></span> <span data-ttu-id="2cfc7-230">Es ist ausreichend, einfach die durchschnittliche Größe der erwarteten LOB-Werte zu addieren, diese mit ***Num_Rows***zu multiplizieren und das Ergebnis dann zur Gesamtgröße des gruppierten Indexes zu addieren.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-230">It is sufficient to just add the average size of the LOB values that are expected, multiply by ***Num_Rows***, and add that to the total clustered index size.</span></span>  
  
-   <span data-ttu-id="2cfc7-231">Komprimierung</span><span class="sxs-lookup"><span data-stu-id="2cfc7-231">Compression</span></span>  
  
     <span data-ttu-id="2cfc7-232">Sie können die Größe eines komprimierten Index nicht im Vorfeld berechnen.</span><span class="sxs-lookup"><span data-stu-id="2cfc7-232">You cannot pre-calculate the size of a compressed index.</span></span>  
  
-   <span data-ttu-id="2cfc7-233">Spalten mit geringer Dichte</span><span class="sxs-lookup"><span data-stu-id="2cfc7-233">Sparse columns</span></span>  
  
     <span data-ttu-id="2cfc7-234">Informationen zu den Speicherplatzanforderungen von Sparsespalten finden Sie unter [Use Sparse Columns](../tables/use-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="2cfc7-234">For information about the space requirements of sparse columns, see [Use Sparse Columns](../tables/use-sparse-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cfc7-235">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2cfc7-235">See Also</span></span>  
 <span data-ttu-id="2cfc7-236">[Beschreibung von gruppierten und nicht gruppierten Indizes](../indexes/clustered-and-nonclustered-indexes-described.md) </span><span class="sxs-lookup"><span data-stu-id="2cfc7-236">[Clustered and Nonclustered Indexes Described](../indexes/clustered-and-nonclustered-indexes-described.md) </span></span>  
 <span data-ttu-id="2cfc7-237">[Schätzen der Größe einer Tabelle](estimate-the-size-of-a-table.md) </span><span class="sxs-lookup"><span data-stu-id="2cfc7-237">[Estimate the Size of a Table](estimate-the-size-of-a-table.md) </span></span>  
 <span data-ttu-id="2cfc7-238">[Erstellen gruppierter Indizes](../indexes/create-clustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="2cfc7-238">[Create Clustered Indexes](../indexes/create-clustered-indexes.md) </span></span>  
 <span data-ttu-id="2cfc7-239">[Erstellen nicht gruppierter Indizes](../indexes/create-nonclustered-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="2cfc7-239">[Create Nonclustered Indexes](../indexes/create-nonclustered-indexes.md) </span></span>  
 <span data-ttu-id="2cfc7-240">[Schätzen der Größe eines nicht gruppierten Index](estimate-the-size-of-a-nonclustered-index.md) </span><span class="sxs-lookup"><span data-stu-id="2cfc7-240">[Estimate the Size of a Nonclustered Index](estimate-the-size-of-a-nonclustered-index.md) </span></span>  
 <span data-ttu-id="2cfc7-241">[Schätzen der Größe eines Heaps](estimate-the-size-of-a-heap.md) </span><span class="sxs-lookup"><span data-stu-id="2cfc7-241">[Estimate the Size of a Heap](estimate-the-size-of-a-heap.md) </span></span>  
 [<span data-ttu-id="2cfc7-242">Schätzen der Größe einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="2cfc7-242">Estimate the Size of a Database</span></span>](estimate-the-size-of-a-database.md)  
  
  
