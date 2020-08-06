---
title: Tabellen- und Zeilengröße in speicheroptimierten Tabellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: b0a248a4-4488-4cc8-89fc-46906a8c24a1
author: rothja
ms.author: jroth
ms.openlocfilehash: 74cc40b7d1f2d0132d79d1e9ae15c2321ac9b74a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725729"
---
# <a name="table-and-row-size-in-memory-optimized-tables"></a><span data-ttu-id="cf05f-102">Tabellen- und Zeilengröße in speicheroptimierten Tabellen</span><span class="sxs-lookup"><span data-stu-id="cf05f-102">Table and Row Size in Memory-Optimized Tables</span></span>
  <span data-ttu-id="cf05f-103">Eine speicheroptimierte Tabelle besteht aus einer Auflistung von Zeilen und Indizes, die Zeiger auf die Zeilen enthalten.</span><span class="sxs-lookup"><span data-stu-id="cf05f-103">A memory-optimized table consists of a collection of rows and indexes that contain pointers to rows.</span></span> <span data-ttu-id="cf05f-104">In einer speicheroptimierten Tabelle dürfen Zeilen eine maximale Länge von 8.060 Bytes aufweisen.</span><span class="sxs-lookup"><span data-stu-id="cf05f-104">In a memory-optimized table, rows cannot be longer than 8,060 bytes.</span></span> <span data-ttu-id="cf05f-105">Wenn Sie eine Vorstellung von der Größe einer speicheroptimierten Tabelle haben, können Sie besser einschätzen, ob Ihr Computer über genügend Arbeitsspeicher verfügt.</span><span class="sxs-lookup"><span data-stu-id="cf05f-105">Understanding the size of a memory-optimized table will help you understand if your computer has enough memory.</span></span>  
  
 <span data-ttu-id="cf05f-106">Es gibt zwei Gründe für das Berechnen der Tabellen- und Zeilengröße:</span><span class="sxs-lookup"><span data-stu-id="cf05f-106">There are two reasons for computing table and row size:</span></span>  
  
-   <span data-ttu-id="cf05f-107">Wie viel Arbeitsspeicher verwendet eine Tabelle?</span><span class="sxs-lookup"><span data-stu-id="cf05f-107">How much memory does a table use?</span></span>  
  
    -   <span data-ttu-id="cf05f-108">Der Arbeitsspeicher, der für die Tabelle verwendet wird, kann nicht genau berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="cf05f-108">The amount of memory used by the table cannot be calculated exactly.</span></span> <span data-ttu-id="cf05f-109">Viele Faktoren beeinflussen den verwendeten Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="cf05f-109">Many factors affect the amount of memory used.</span></span> <span data-ttu-id="cf05f-110">Faktoren wie seitenbasierte Speicherbelegung, Ort, Caching und Auffüllung.</span><span class="sxs-lookup"><span data-stu-id="cf05f-110">Factors such as page-based memory allocation, locality, caching, and padding.</span></span> <span data-ttu-id="cf05f-111">Darüber hinaus mehrere Versionen von Zeilen, denen entweder aktive Transaktionen zugeordnet sind oder die auf die Garbage Collection warten.</span><span class="sxs-lookup"><span data-stu-id="cf05f-111">Also, multiple versions of rows that either have active transactions associated or that are waiting for garbage collection.</span></span>  
  
    -   <span data-ttu-id="cf05f-112">Die minimale Größe, die für die Daten und Indizes in der Tabelle erforderlich ist, wird durch die Berechnung von [table size] angegeben, wie unten erläutert.</span><span class="sxs-lookup"><span data-stu-id="cf05f-112">The minimum size required for the data and indexes in the table is given by the calculation for [table size], discussed below.</span></span>  
  
    -   <span data-ttu-id="cf05f-113">Da die Berechnung der Arbeitsspeicherverwendung bestenfalls eine Näherung darstellt, ist es ratsam, auch eine Kapazitätsplanung in den Bereitstellungsplänen vorzusehen.</span><span class="sxs-lookup"><span data-stu-id="cf05f-113">Calculating memory use is at best an approximation and you are advised to include capacity planning in your deployment plans.</span></span>  
  
-   <span data-ttu-id="cf05f-114">Die Datengröße einer Zeile und die Frage, ob die maximale Zeilengröße von 8.060 Bytes eingehalten wird.</span><span class="sxs-lookup"><span data-stu-id="cf05f-114">The data size of a row, and does it fit in the 8,060 byte row size limitation?</span></span> <span data-ttu-id="cf05f-115">Um diese Fragen zu beantworten, verwenden Sie die Berechnung von [row body size], wie unten erläutert.</span><span class="sxs-lookup"><span data-stu-id="cf05f-115">To answer these questions, use the computation for [row body size], discussed below.</span></span>  
  
 <span data-ttu-id="cf05f-116">Die folgende Abbildung zeigt eine Tabelle mit Indizes und Zeilen, die wiederum Zeilenüberschriften und Text enthalten:</span><span class="sxs-lookup"><span data-stu-id="cf05f-116">The following figure illustrates a table with indexes and rows, which in turn have row headers and bodies:</span></span>  
  
 <span data-ttu-id="cf05f-117">![Speicheroptimierte Tabelle.](../../database-engine/media/hekaton-guide-1.gif "Speicheroptimierte Tabelle")</span><span class="sxs-lookup"><span data-stu-id="cf05f-117">![Memory optimized table.](../../database-engine/media/hekaton-guide-1.gif "Memory optimized table.")</span></span>  
<span data-ttu-id="cf05f-118">Speicheroptimierte Tabelle, bestehend aus Indizes und Zeilen.</span><span class="sxs-lookup"><span data-stu-id="cf05f-118">Memory-optimized table, consisting of indexes and rows.</span></span>  
  
 <span data-ttu-id="cf05f-119">Die Größe einer Tabelle im Arbeitsspeicher in Bytes wird wie folgt berechnet:</span><span class="sxs-lookup"><span data-stu-id="cf05f-119">The in-memory size of a table, in bytes, is computed as follows:</span></span>  
  
```  
[table size] = [size of index 1] + ... + [size of index n] + ([row size] * [row count])  
```  
  
 <span data-ttu-id="cf05f-120">Die Größe eines Hashindexes wird bei Erstellung der Tabelle festgelegt und hängt von der tatsächlichen Bucketanzahl ab.</span><span class="sxs-lookup"><span data-stu-id="cf05f-120">The size of a hash index is fixed at table creation time and depends on the actual bucket count.</span></span> <span data-ttu-id="cf05f-121">Der bucket_count-Wert, der mit der Indexspezifikation angegeben wird, wird auf die nächste Zweierpotenz aufgerundet, um [actual bucket count] zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="cf05f-121">The bucket_count specified with the index specification is rounded up to the nearest power of 2 to obtain the [actual bucket count].</span></span> <span data-ttu-id="cf05f-122">Wenn der angegebene bucket_count-Wert beispielsweise 100000 ist, beträgt [actual bucket count] für den Index 131072.</span><span class="sxs-lookup"><span data-stu-id="cf05f-122">For example, if the specified bucket_count is 100000, the [actual bucket count] for the index is 131072.</span></span>  
  
```  
[hash index size] = 8 * [actual bucket count]  
```  
  
 <span data-ttu-id="cf05f-123">Die Zeilengröße wird berechnet, indem die Überschrift und der Text addiert werden:</span><span class="sxs-lookup"><span data-stu-id="cf05f-123">The row size is computed by adding the header and the body:</span></span>  
  
```  
[row size] = [row header size] + [actual row body size]  
[row header size] = 24 + 8 * [number of indices]  
```  
  
 <span data-ttu-id="cf05f-124">**Zeilentextgröße**</span><span class="sxs-lookup"><span data-stu-id="cf05f-124">**Row body size**</span></span>  
  
 <span data-ttu-id="cf05f-125">Die Berechnung von [row body size] wird in der folgenden Tabelle erläutert.</span><span class="sxs-lookup"><span data-stu-id="cf05f-125">The calculation of [row body size] is discussed in the following table.</span></span>  
  
 <span data-ttu-id="cf05f-126">Es gibt zwei verschiedene Berechnungen für die Zeilentextgröße: die berechnete Größe und die tatsächliche Größe:</span><span class="sxs-lookup"><span data-stu-id="cf05f-126">There are two different computations for row body size: computed size and the actual size:</span></span>  
  
-   <span data-ttu-id="cf05f-127">Die berechnete Größe, bezeichnet mit [computed row body size], wird verwendet, um festzustellen, ob die Zeilengrößeneinschränkung von 8.060 Bytes überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="cf05f-127">The computed size, denoted with [computed row body size], is used to determine if the row size limitation of 8,060 bytes is exceeded.</span></span>  
  
-   <span data-ttu-id="cf05f-128">Die tatsächliche Größe, bezeichnet mit [actual row body size], ist die tatsächliche Speichergröße des Zeilentexts im Arbeitsspeicher und in den Prüfpunktdateien.</span><span class="sxs-lookup"><span data-stu-id="cf05f-128">The actual size, denoted with [actual row body size], is the actual storage size of the row body in memory and in the checkpoint files.</span></span>  
  
 <span data-ttu-id="cf05f-129">[computed row body size] und [actual row body size] werden ähnlich berechnet.</span><span class="sxs-lookup"><span data-stu-id="cf05f-129">Both [computed row body size] and [actual row body size] are calculated similarly.</span></span> <span data-ttu-id="cf05f-130">Der einzige Unterschied ist die Berechnung der Größe von (n)varchar(i)- und varbinary(i)-Spalten, wie unten in der folgenden Tabelle dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cf05f-130">The only difference is the calculation of the size of (n)varchar(i) and varbinary(i) columns, as reflected at the bottom of the following table.</span></span> <span data-ttu-id="cf05f-131">Bei der berechneten Zeilentextgröße wird die deklarierte Größe *i* als Größe der Spalte verwendet, während für die tatsächliche Zeilentextgröße die tatsächliche Größe der Daten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cf05f-131">The computed row body size uses the declared size *i* as the size of the column, while the actual row body size uses the actual size of the data.</span></span>  
  
 <span data-ttu-id="cf05f-132">In der folgenden Tabelle wird die Berechnung der Zeilentextgröße beschrieben, die wie folgt angegeben wird: [actual row body size] = SUM([size of shallow types]) + 2 + 2 \* [number of deep type columns].</span><span class="sxs-lookup"><span data-stu-id="cf05f-132">The following table describes the calculation of the row body size, given as [actual row body size] = SUM([size of shallow types]) + 2 + 2 \* [number of deep type columns].</span></span>  
  
|<span data-ttu-id="cf05f-133">`Section`</span><span class="sxs-lookup"><span data-stu-id="cf05f-133">Section</span></span>|<span data-ttu-id="cf05f-134">Size</span><span class="sxs-lookup"><span data-stu-id="cf05f-134">Size</span></span>|<span data-ttu-id="cf05f-135">Kommentare</span><span class="sxs-lookup"><span data-stu-id="cf05f-135">Comments</span></span>|  
|-------------|----------|--------------|  
|<span data-ttu-id="cf05f-136">Spalten flacher Typen</span><span class="sxs-lookup"><span data-stu-id="cf05f-136">Shallow type columns</span></span>|<span data-ttu-id="cf05f-137">SUM([size of shallow types])</span><span class="sxs-lookup"><span data-stu-id="cf05f-137">SUM([size of shallow types])</span></span><br /><br /> <span data-ttu-id="cf05f-138">**Die Größe der einzelnen Typen lautet wie folgt:**</span><span class="sxs-lookup"><span data-stu-id="cf05f-138">**Size of the individual types is as follows:**</span></span><br /><br /> <span data-ttu-id="cf05f-139">Bit: 1</span><span class="sxs-lookup"><span data-stu-id="cf05f-139">Bit &#124; 1</span></span><br /><br /> <span data-ttu-id="cf05f-140">Tinyint: 1</span><span class="sxs-lookup"><span data-stu-id="cf05f-140">Tinyint &#124; 1</span></span><br /><br /> <span data-ttu-id="cf05f-141">Smallint: 2</span><span class="sxs-lookup"><span data-stu-id="cf05f-141">Smallint &#124; 2</span></span><br /><br /> <span data-ttu-id="cf05f-142">Int: 4</span><span class="sxs-lookup"><span data-stu-id="cf05f-142">Int &#124; 4</span></span><br /><br /> <span data-ttu-id="cf05f-143">Real: 4</span><span class="sxs-lookup"><span data-stu-id="cf05f-143">Real &#124; 4</span></span><br /><br /> <span data-ttu-id="cf05f-144">Smalldatetime: 4</span><span class="sxs-lookup"><span data-stu-id="cf05f-144">Smalldatetime &#124; 4</span></span><br /><br /> <span data-ttu-id="cf05f-145">Smallmoney: 4</span><span class="sxs-lookup"><span data-stu-id="cf05f-145">Smallmoney &#124; 4</span></span><br /><br /> <span data-ttu-id="cf05f-146">Bigint: 8</span><span class="sxs-lookup"><span data-stu-id="cf05f-146">Bigint &#124; 8</span></span><br /><br /> <span data-ttu-id="cf05f-147">Datetime: 8</span><span class="sxs-lookup"><span data-stu-id="cf05f-147">Datetime &#124; 8</span></span><br /><br /> <span data-ttu-id="cf05f-148">Datetime2: 8</span><span class="sxs-lookup"><span data-stu-id="cf05f-148">Datetime2 &#124; 8</span></span><br /><br /> <span data-ttu-id="cf05f-149">Float: 8</span><span class="sxs-lookup"><span data-stu-id="cf05f-149">Float 8</span></span><br /><br /> <span data-ttu-id="cf05f-150">Money: 8</span><span class="sxs-lookup"><span data-stu-id="cf05f-150">Money 8</span></span><br /><br /> <span data-ttu-id="cf05f-151">Numeric (Precision <= 18) &#124; 8</span><span class="sxs-lookup"><span data-stu-id="cf05f-151">Numeric (precision <=18) &#124; 8</span></span><br /><br /> <span data-ttu-id="cf05f-152">Time: 8</span><span class="sxs-lookup"><span data-stu-id="cf05f-152">Time &#124; 8</span></span><br /><br /> <span data-ttu-id="cf05f-153">Numeric (Precision>18) &#124; 16</span><span class="sxs-lookup"><span data-stu-id="cf05f-153">Numeric(precision>18) &#124; 16</span></span><br /><br /> <span data-ttu-id="cf05f-154">Uniqueidentifier: 16</span><span class="sxs-lookup"><span data-stu-id="cf05f-154">Uniqueidentifier &#124; 16</span></span>||  
|<span data-ttu-id="cf05f-155">Auffüllung flacher Spalten</span><span class="sxs-lookup"><span data-stu-id="cf05f-155">Shallow column padding</span></span>|<span data-ttu-id="cf05f-156">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="cf05f-156">Possible values are:</span></span><br /><br /> <span data-ttu-id="cf05f-157">1, wenn Spalten tiefer Typen vorhanden sind und die gesamte Datengröße der flachen Spalten eine ungerade Zahl darstellt.</span><span class="sxs-lookup"><span data-stu-id="cf05f-157">1 if there are deep type columns and the total data size of the shallow columns is as odd number.</span></span><br /><br /> <span data-ttu-id="cf05f-158">0 andernfalls</span><span class="sxs-lookup"><span data-stu-id="cf05f-158">0 otherwise</span></span>|<span data-ttu-id="cf05f-159">Tiefe Typen sind die Typen (var)binary und (n)(var)char.</span><span class="sxs-lookup"><span data-stu-id="cf05f-159">Deep types are the types (var)binary and (n)(var)char.</span></span>|  
|<span data-ttu-id="cf05f-160">Offsetarray für Spalten tiefer Typen</span><span class="sxs-lookup"><span data-stu-id="cf05f-160">Offset array for deep type columns</span></span>|<span data-ttu-id="cf05f-161">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="cf05f-161">Possible values are:</span></span><br /><br /> <span data-ttu-id="cf05f-162">0, wenn keine Spalten tiefer Typen vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="cf05f-162">0 if there are no deep type columns</span></span><br /><br /> <span data-ttu-id="cf05f-163">2 + 2 \* [number of deep type columns] andernfalls</span><span class="sxs-lookup"><span data-stu-id="cf05f-163">2 + 2 \* [number of deep type columns] otherwise</span></span>|<span data-ttu-id="cf05f-164">Tiefe Typen sind die Typen (var)binary und (n)(var)char.</span><span class="sxs-lookup"><span data-stu-id="cf05f-164">Deep types are the types (var)binary and (n)(var)char.</span></span>|  
|<span data-ttu-id="cf05f-165">NULL-Array</span><span class="sxs-lookup"><span data-stu-id="cf05f-165">NULL array</span></span>|<span data-ttu-id="cf05f-166">[number of nullable columns] / 8, aufgerundet auf vollständige Bytes.</span><span class="sxs-lookup"><span data-stu-id="cf05f-166">[number of nullable columns] / 8, rounded up to full bytes.</span></span>|<span data-ttu-id="cf05f-167">Das Array verfügt über ein Bit pro Spalte, die NULL zulässt.</span><span class="sxs-lookup"><span data-stu-id="cf05f-167">The array has one bit per nullable column.</span></span> <span data-ttu-id="cf05f-168">Dies wird auf vollständige Bytes aufgerundet.</span><span class="sxs-lookup"><span data-stu-id="cf05f-168">This is rounded up to full bytes.</span></span>|  
|<span data-ttu-id="cf05f-169">NULL-Arrayauffüllung</span><span class="sxs-lookup"><span data-stu-id="cf05f-169">NULL array padding</span></span>|<span data-ttu-id="cf05f-170">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="cf05f-170">Possible values are:</span></span><br /><br /> <span data-ttu-id="cf05f-171">1, wenn Spalten tiefer Typen vorhanden sind und die Größe des NULL-Arrays eine ungerade Anzahl von Bytes darstellt.</span><span class="sxs-lookup"><span data-stu-id="cf05f-171">1 if there are deep type columns and the size of the NULL array is an odd number of bytes.</span></span><br /><br /> <span data-ttu-id="cf05f-172">0 andernfalls</span><span class="sxs-lookup"><span data-stu-id="cf05f-172">0 otherwise</span></span>|<span data-ttu-id="cf05f-173">Tiefe Typen sind die Typen (var)binary und (n)(var)char.</span><span class="sxs-lookup"><span data-stu-id="cf05f-173">Deep types are the types (var)binary and (n)(var)char.</span></span>|  
|<span data-ttu-id="cf05f-174">Auffüllen</span><span class="sxs-lookup"><span data-stu-id="cf05f-174">Padding</span></span>|<span data-ttu-id="cf05f-175">Wenn keine Spalten tiefer Typen vorhanden sind: 0 0</span><span class="sxs-lookup"><span data-stu-id="cf05f-175">If there are no deep type columns: 0</span></span><br /><br /> <span data-ttu-id="cf05f-176">Wenn Spalten tiefer Typen vorhanden sind, wird eine 0-7-Byte-Auffüllung hinzugefügt, basierend auf der größten Ausrichtung, die für eine flache Spalte erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="cf05f-176">If there are deep type columns, 0-7 bytes of padding is added, based on the largest alignment required by a shallow column.</span></span> <span data-ttu-id="cf05f-177">Jede flache Spalte erfordert eine Ausrichtung gleich ihrer Größe, wie oben beschrieben. Nur GUID-Spalten erfordern eine Ausrichtung von einem Byte (nicht 16) und numerische Spalten immer eine Ausrichtung von 8 Bytes (nie 16).</span><span class="sxs-lookup"><span data-stu-id="cf05f-177">Each shallow column requires alignment equal to its size as documented above, except that GUID columns need alignment of 1 byte (not 16) and numeric columns always need alignment of 8 bytes (never 16).</span></span> <span data-ttu-id="cf05f-178">Die größte Ausrichtungsanforderung unter allen flachen Spalten wird verwendet, und eine 0-7-Byte-Auffüllung wird so hinzugefügt, dass die bisherige Gesamtgröße (ohne die Spalten tiefer Typen) ein Vielfaches der erforderlichen Ausrichtung ergibt.</span><span class="sxs-lookup"><span data-stu-id="cf05f-178">The largest alignment requirement among all shallow columns is used, and 0-7 bytes of padding is added in such a way that the total size so far (without the deep type columns) is a multiple of the required alignment.</span></span>|<span data-ttu-id="cf05f-179">Tiefe Typen sind die Typen (var)binary und (n)(var)char.</span><span class="sxs-lookup"><span data-stu-id="cf05f-179">Deep types are the types (var)binary and (n)(var)char.</span></span>|  
|<span data-ttu-id="cf05f-180">Spalten tiefer Typen mit fester Länge</span><span class="sxs-lookup"><span data-stu-id="cf05f-180">Fixed-length deep type columns</span></span>|<span data-ttu-id="cf05f-181">SUM([size of fixed length deep type columns])</span><span class="sxs-lookup"><span data-stu-id="cf05f-181">SUM([size of fixed length deep type columns])</span></span><br /><br /> <span data-ttu-id="cf05f-182">Die Größe jeder Spalte lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="cf05f-182">The size of each column is as follows:</span></span><br /><br /> <span data-ttu-id="cf05f-183">i für char(i) und binary(i).</span><span class="sxs-lookup"><span data-stu-id="cf05f-183">i for char(i) and binary(i).</span></span><br /><br /> <span data-ttu-id="cf05f-184">2 \* i für nchar(i)</span><span class="sxs-lookup"><span data-stu-id="cf05f-184">2 \* i for nchar(i)</span></span>|<span data-ttu-id="cf05f-185">Spalten tiefer Typen mit fester Länge sind Spalten des Typs char(i), nchar(i) oder binary(i).</span><span class="sxs-lookup"><span data-stu-id="cf05f-185">Fixed-length deep type columns are columns of type char(i), nchar(i), or binary(i).</span></span>|  
|<span data-ttu-id="cf05f-186">Spalten tiefer Typen mit variabler Länge [computed size]</span><span class="sxs-lookup"><span data-stu-id="cf05f-186">Variable length deep type columns [computed size]</span></span>|<span data-ttu-id="cf05f-187">SUM([computed size of variable length deep type columns])</span><span class="sxs-lookup"><span data-stu-id="cf05f-187">SUM([computed size of variable length deep type columns])</span></span><br /><br /> <span data-ttu-id="cf05f-188">Die berechnete Größe jeder Spalte lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="cf05f-188">The computed size of each column is as follows:</span></span><br /><br /> <span data-ttu-id="cf05f-189">i für varchar(i) und varbinary(i)</span><span class="sxs-lookup"><span data-stu-id="cf05f-189">i for varchar(i) and varbinary(i)</span></span><br /><br /> <span data-ttu-id="cf05f-190">2 \* i für nvarchar(i)</span><span class="sxs-lookup"><span data-stu-id="cf05f-190">2 \* i for nvarchar(i)</span></span>|<span data-ttu-id="cf05f-191">Diese Zeile wird nur auf [computed row body size] angewendet.</span><span class="sxs-lookup"><span data-stu-id="cf05f-191">This row only applied to [computed row body size].</span></span><br /><br /> <span data-ttu-id="cf05f-192">Spalten tiefer Typen mit variabler Länge sind Spalten des Typs varchar(i), nvarchar(i) oder varbinary(i).</span><span class="sxs-lookup"><span data-stu-id="cf05f-192">Variable-length deep type columns are columns of type varchar(i), nvarchar(i), or varbinary(i).</span></span> <span data-ttu-id="cf05f-193">Die berechnete Größe wird durch die maximale Länge (i) der Spalte bestimmt.</span><span class="sxs-lookup"><span data-stu-id="cf05f-193">The computed size is determined by the max length (i) of the column.</span></span>|  
|<span data-ttu-id="cf05f-194">Spalten tiefer Typen mit variabler Länge [actual size]</span><span class="sxs-lookup"><span data-stu-id="cf05f-194">Variable length deep type columns [actual size]</span></span>|<span data-ttu-id="cf05f-195">SUM([actual size of variable length deep type columns])</span><span class="sxs-lookup"><span data-stu-id="cf05f-195">SUM([actual size of variable length deep type columns])</span></span><br /><br /> <span data-ttu-id="cf05f-196">Die tatsächliche Größe jeder Spalte lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="cf05f-196">The actual size of each column is as follows:</span></span><br /><br /> <span data-ttu-id="cf05f-197">n, wobei n der Anzahl der in der Spalte gespeicherten Zeichen entspricht; für varchar(i).</span><span class="sxs-lookup"><span data-stu-id="cf05f-197">n, where n is the number of characters stored in the column, for varchar(i).</span></span><br /><br /> <span data-ttu-id="cf05f-198">2 \* n, wobei n der Anzahl der in der Spalte gespeicherten Zeichen entspricht; für nvarchar(i).</span><span class="sxs-lookup"><span data-stu-id="cf05f-198">2 \* n, where n is the number of characters stored in the column, for nvarchar(i).</span></span><br /><br /> <span data-ttu-id="cf05f-199">n, wobei n der Anzahl der in der Spalte gespeicherten Bytes ist; für varbinary(i).</span><span class="sxs-lookup"><span data-stu-id="cf05f-199">n, where n is the number of bytes stored in the column, for varbinary(i).</span></span>|<span data-ttu-id="cf05f-200">Diese Zeile wird nur auf [actual row body size] angewendet.</span><span class="sxs-lookup"><span data-stu-id="cf05f-200">This row only applied to [actual row body size].</span></span><br /><br /> <span data-ttu-id="cf05f-201">Die tatsächliche Größe wird durch die Daten bestimmt, die in den Spalten der Zeile gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="cf05f-201">The actual size is determined by the data stored in the columns in the row.</span></span>|  
  
##  <a name="row-structure"></a><a name="bkmk_RowStructure"></a><span data-ttu-id="cf05f-202">Zeilen Struktur</span><span class="sxs-lookup"><span data-stu-id="cf05f-202">Row Structure</span></span>  
 <span data-ttu-id="cf05f-203">Die Zeilen in einer speicheroptimierten Tabelle verfügen über folgende Komponenten:</span><span class="sxs-lookup"><span data-stu-id="cf05f-203">The rows in a memory-optimized table have the following components:</span></span>  
  
-   <span data-ttu-id="cf05f-204">Die Zeilenüberschrift enthält den Zeitstempel, der erforderlich ist, um Zeilenversionsverwaltung zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="cf05f-204">The row header contains the timestamp necessary to implement row versioning.</span></span> <span data-ttu-id="cf05f-205">Die Zeilenüberschrift enthält auch den Indexzeiger, um die Zeilenverkettung in den Hashbuckets zu implementieren (oben beschrieben).</span><span class="sxs-lookup"><span data-stu-id="cf05f-205">The row header also contains the index pointer to implement the row chaining in the hash buckets (described above).</span></span>  
  
-   <span data-ttu-id="cf05f-206">Der Zeilentext enthält die tatsächlichen Spaltendaten, darunter einige zusätzliche Informationen wie das NULL-Array für Spalten, die NULL-Werte zulassen, und das Offsetarray für Datentypen variabler Länge.</span><span class="sxs-lookup"><span data-stu-id="cf05f-206">The row body contains the actual column data, which includes some auxiliary information like the null array for nullable columns and the offset array for variable-length data types.</span></span>  
  
 <span data-ttu-id="cf05f-207">Die folgende Abbildung veranschaulicht die Zeilenstruktur für eine Tabelle mit zwei Indizes:</span><span class="sxs-lookup"><span data-stu-id="cf05f-207">The following figure illustrates the row structure for a table that has two indexes:</span></span>  
  
 <span data-ttu-id="cf05f-208">![Zeilenstruktur für eine Tabelle, die zwei Indizes umfasst](../../database-engine/media/hekaton-tables-4.gif "Zeilenstruktur für eine Tabelle, die zwei Indizes umfasst")</span><span class="sxs-lookup"><span data-stu-id="cf05f-208">![Row structure for a table that has two indexes.](../../database-engine/media/hekaton-tables-4.gif "Row structure for a table that has two indexes.")</span></span>  
  
 <span data-ttu-id="cf05f-209">Die Zeitstempel für Beginn und Ende geben den Zeitraum an, in dem eine bestimmte Zeilenversion gültig ist.</span><span class="sxs-lookup"><span data-stu-id="cf05f-209">The begin and end timestamps indicate the period in which a particular row version is valid.</span></span> <span data-ttu-id="cf05f-210">Für Transaktionen, die in diesem Intervall beginnen, ist diese Zeilenversion sichtbar.</span><span class="sxs-lookup"><span data-stu-id="cf05f-210">Transactions that start in this interval can see this row version.</span></span> <span data-ttu-id="cf05f-211">Weitere Informationen finden Sie unter [Transaktionen in speicheroptimierten Tabellen](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="cf05f-211">For more details see [Transactions in Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
 <span data-ttu-id="cf05f-212">Die Indexzeiger zeigen auf die nächste Zeile in der Kette, die dem Hashbucket angehört.</span><span class="sxs-lookup"><span data-stu-id="cf05f-212">The index pointers point to the next row in the chain belonging to the hash bucket.</span></span> <span data-ttu-id="cf05f-213">Die folgende Abbildung veranschaulicht die Struktur einer Tabelle mit zwei Spalten (Name, Ort) und mit zwei Indizes: einem für den Spaltennamen und einen für den Spaltenort.</span><span class="sxs-lookup"><span data-stu-id="cf05f-213">The following figure illustrates the structure of a table with two columns (name, city), and with two indexes, one on the column name, and one on the column city.</span></span>  
  
 <span data-ttu-id="cf05f-214">![Struktur einer Tabelle mit zwei Spalten und Indizes](../../database-engine/media/hekaton-tables-5.gif "Struktur einer Tabelle mit zwei Spalten und Indizes")</span><span class="sxs-lookup"><span data-stu-id="cf05f-214">![Structure of a table with two columns and indexes.](../../database-engine/media/hekaton-tables-5.gif "Structure of a table with two columns and indexes.")</span></span>  
  
 <span data-ttu-id="cf05f-215">In dieser Abbildung werden die Namen John und Jane zum ersten Hashbucket hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cf05f-215">In this figure, the names John and Jane are hashed to the first bucket.</span></span> <span data-ttu-id="cf05f-216">Susan wird dem zweiten Hashbucket hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cf05f-216">Susan is hashed to the second bucket.</span></span> <span data-ttu-id="cf05f-217">Die Städte Beijing (Peking) und Bogota werden dem ersten Hashbucket hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cf05f-217">The cities Beijing and Bogota are hashed to the first bucket.</span></span> <span data-ttu-id="cf05f-218">Paris und Prag werden dem zweiten Hashbucket hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cf05f-218">Paris and Prague are hashed to the second bucket.</span></span>  
  
 <span data-ttu-id="cf05f-219">Somit ergeben sie folgende Ketten für den Hashindex für Namen:</span><span class="sxs-lookup"><span data-stu-id="cf05f-219">Thus, the chains for the hash index on name are as follows:</span></span>  
  
-   <span data-ttu-id="cf05f-220">Erster Bucket: (John, Beijing), (John, Paris), (Jane, Prague)</span><span class="sxs-lookup"><span data-stu-id="cf05f-220">First bucket: (John, Beijing); (John, Paris); (Jane, Prague)</span></span>  
  
-   <span data-ttu-id="cf05f-221">Zweiter Bucket: (Susan, Bogota)</span><span class="sxs-lookup"><span data-stu-id="cf05f-221">Second bucket: (Susan, Bogota)</span></span>  
  
 <span data-ttu-id="cf05f-222">Die Ketten für den Index für die Stadt lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="cf05f-222">The chains for the index on city are as follows:</span></span>  
  
-   <span data-ttu-id="cf05f-223">Erster Bucket: (John, Beijing), (Susan, Bogota)</span><span class="sxs-lookup"><span data-stu-id="cf05f-223">First bucket: (John, Beijing), (Susan, Bogota)</span></span>  
  
-   <span data-ttu-id="cf05f-224">Zweiter Bucket: (John, Paris), (Jane, Prague)</span><span class="sxs-lookup"><span data-stu-id="cf05f-224">Second bucket: (John, Paris), (Jane, Prague)</span></span>  
  
 <span data-ttu-id="cf05f-225">Ein Endzeit Stempel &#x221e; (unendlich) gibt an, dass dies die aktuell gültige Version der Zeile ist.</span><span class="sxs-lookup"><span data-stu-id="cf05f-225">An end timestamp &#x221e; (infinity) indicates that this is the currently valid version of the row.</span></span> <span data-ttu-id="cf05f-226">Die Zeile wurde nicht aktualisiert oder gelöscht, seitdem diese Zeilenversion geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="cf05f-226">The row has not been updated or deleted since this row version was written.</span></span>  
  
 <span data-ttu-id="cf05f-227">Eine Zeit, die größer als 200 ist, enthält die Tabelle die folgenden Zeilen:</span><span class="sxs-lookup"><span data-stu-id="cf05f-227">For a time greater than 200, the table contains the following rows:</span></span>  
  
|<span data-ttu-id="cf05f-228">Name</span><span class="sxs-lookup"><span data-stu-id="cf05f-228">Name</span></span>|<span data-ttu-id="cf05f-229">City</span><span class="sxs-lookup"><span data-stu-id="cf05f-229">City</span></span>|  
|----------|----------|  
|<span data-ttu-id="cf05f-230">John</span><span class="sxs-lookup"><span data-stu-id="cf05f-230">John</span></span>|<span data-ttu-id="cf05f-231">Peking (Beijing)</span><span class="sxs-lookup"><span data-stu-id="cf05f-231">Beijing</span></span>|  
|<span data-ttu-id="cf05f-232">Jane</span><span class="sxs-lookup"><span data-stu-id="cf05f-232">Jane</span></span>|<span data-ttu-id="cf05f-233">Prag</span><span class="sxs-lookup"><span data-stu-id="cf05f-233">Prague</span></span>|  
  
 <span data-ttu-id="cf05f-234">Allerdings wird jeder aktiven Transaktion mit Anfangszeit 100 die folgende Version der Tabelle angezeigt:</span><span class="sxs-lookup"><span data-stu-id="cf05f-234">However, any active transaction with begin time 100 will see the following version of the table:</span></span>  
  
|<span data-ttu-id="cf05f-235">Name</span><span class="sxs-lookup"><span data-stu-id="cf05f-235">Name</span></span>|<span data-ttu-id="cf05f-236">City</span><span class="sxs-lookup"><span data-stu-id="cf05f-236">City</span></span>|  
|----------|----------|  
|<span data-ttu-id="cf05f-237">John</span><span class="sxs-lookup"><span data-stu-id="cf05f-237">John</span></span>|<span data-ttu-id="cf05f-238">Paris</span><span class="sxs-lookup"><span data-stu-id="cf05f-238">Paris</span></span>|  
|<span data-ttu-id="cf05f-239">Jane</span><span class="sxs-lookup"><span data-stu-id="cf05f-239">Jane</span></span>|<span data-ttu-id="cf05f-240">Prag</span><span class="sxs-lookup"><span data-stu-id="cf05f-240">Prague</span></span>|  
|<span data-ttu-id="cf05f-241">Susan</span><span class="sxs-lookup"><span data-stu-id="cf05f-241">Susan</span></span>|<span data-ttu-id="cf05f-242">Bogota</span><span class="sxs-lookup"><span data-stu-id="cf05f-242">Bogata</span></span>|  
  
##  <a name="example-table-and-row-size-computation"></a><a name="bkmk_ExampleComputation"></a> <span data-ttu-id="cf05f-243">Beispiel: Tabellen- und Zeilengrößenberechnung</span><span class="sxs-lookup"><span data-stu-id="cf05f-243">Example: Table and Row Size Computation</span></span>  
 <span data-ttu-id="cf05f-244">Für Hashindizes wird die tatsächliche Bucketanzahl auf die nächste Zweierpotenz aufgerundet.</span><span class="sxs-lookup"><span data-stu-id="cf05f-244">For hash indexes, the actual bucket count is rounded up to the nearest power of 2.</span></span> <span data-ttu-id="cf05f-245">Wenn der angegebene bucket_count-Wert beispielsweise 100000 ist, beträgt die tatsächliche Bucketanzahl für den Index 131072.</span><span class="sxs-lookup"><span data-stu-id="cf05f-245">For example, if the specified bucket_count is 100000, the actual bucket count for the index is 131072.</span></span>  
  
 <span data-ttu-id="cf05f-246">Betrachten Sie eine Orders-Tabelle mit folgender Definition:</span><span class="sxs-lookup"><span data-stu-id="cf05f-246">Consider an Orders table with the following definition:</span></span>  
  
```sql  
CREATE TABLE dbo.Orders (  
     OrderID int NOT NULL   
           PRIMARY KEY NONCLUSTERED,  
     CustomerID int NOT NULL   
           INDEX IX_CustomerID HASH WITH (BUCKET_COUNT=10000),  
     OrderDate datetime NOT NULL,  
     OrderDescription nvarchar(1000)  
) WITH (MEMORY_OPTIMIZED=ON)  
GO  
```  
  
 <span data-ttu-id="cf05f-247">Beachten Sie, dass diese Tabelle einen Hashindex und einen nicht gruppierten Index (den Primärschlüssel) aufweist.</span><span class="sxs-lookup"><span data-stu-id="cf05f-247">Notice that this table has one hash index and a nonclustered index (the primary key).</span></span> <span data-ttu-id="cf05f-248">Darüber hinaus weist sie drei Spalten fester Länge und eine Spalte variabler Länge auf, wobei eine der Spalten NULL-Werte zulässt (OrderDescription).</span><span class="sxs-lookup"><span data-stu-id="cf05f-248">It also has three fixed-length columns and one variable-length column, with one of the columns being NULLable (OrderDescription).</span></span> <span data-ttu-id="cf05f-249">Nehmen wir an, die Orders-Tabelle hat 8379 Zeilen, und die durchschnittliche Länge der Werte in der orderdescription-Spalte beträgt 78 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="cf05f-249">Let's assume the Orders table has 8379 rows, and the average length of the values in the OrderDescription column is 78 characters.</span></span>  
  
 <span data-ttu-id="cf05f-250">Um die Tabellengröße zu ermitteln, ermitteln Sie zuerst die Größe der Indizes.</span><span class="sxs-lookup"><span data-stu-id="cf05f-250">To determine the table size, first determine the size of the indexes.</span></span> <span data-ttu-id="cf05f-251">Der bucket_count-Wert für beide Indizes wird mit 10000 angegeben.</span><span class="sxs-lookup"><span data-stu-id="cf05f-251">The bucket_count for both indexes is specified as 10000.</span></span> <span data-ttu-id="cf05f-252">Dieser wird auf die nächste Zweierpotenz aufgerundet: 16384</span><span class="sxs-lookup"><span data-stu-id="cf05f-252">This is rounded up to the nearest power of 2: 16384.</span></span> <span data-ttu-id="cf05f-253">Daher ergibt sich die Gesamtgröße der Indizes für die Orders-Tabelle wie folgt:</span><span class="sxs-lookup"><span data-stu-id="cf05f-253">Therefore, the total size of the indexes for the Orders table is:</span></span>  
  
```  
8 * 16384 = 131072 bytes  
```  
  
 <span data-ttu-id="cf05f-254">Was bleibt, ist die Tabellendatengröße:</span><span class="sxs-lookup"><span data-stu-id="cf05f-254">What remains is the table data size, which is,</span></span>  
  
```  
[row size] * [row count] = [row size] * 8379  
```  
  
 <span data-ttu-id="cf05f-255">(Die Beispieltabelle enthält 8379 Zeilen.) Jetzt haben wir:</span><span class="sxs-lookup"><span data-stu-id="cf05f-255">(The example table has 8379 rows.) Now, we have:</span></span>  
  
```  
[row size] = [row header size] + [actual row body size]  
[row header size] = 24 + 8 * [number of indices] = 24 + 8 * 1 = 32 bytes  
```  
  
 <span data-ttu-id="cf05f-256">Als Nächstes berechnen wir [actual row body size]:</span><span class="sxs-lookup"><span data-stu-id="cf05f-256">Next, let's calculate [actual row body size]:</span></span>  
  
-   <span data-ttu-id="cf05f-257">Spalten flacher Typen:</span><span class="sxs-lookup"><span data-stu-id="cf05f-257">Shallow type columns:</span></span>  
  
    ```  
    SUM([size of shallow types]) = 4 [int] + 4 [int] + 8 [datetime] = 16  
    ```  
  
-   <span data-ttu-id="cf05f-258">Die Auffüllung flacher Spalten ist 0, da die Gesamtgröße der flachen Spalten einem geraden Wert entspricht.</span><span class="sxs-lookup"><span data-stu-id="cf05f-258">Shallow column padding is 0, as the total shallow column size is even.</span></span>  
  
-   <span data-ttu-id="cf05f-259">Offsetarray für Spalten tiefer Typen:</span><span class="sxs-lookup"><span data-stu-id="cf05f-259">Offset array for deep type columns:</span></span>  
  
    ```  
    2 + 2 * [number of deep type columns] = 2 + 2 * 1 = 4  
    ```  
  
-   <span data-ttu-id="cf05f-260">NULL-Array = 1</span><span class="sxs-lookup"><span data-stu-id="cf05f-260">NULL array = 1</span></span>  
  
-   <span data-ttu-id="cf05f-261">NULL-Arrayauffüllung = 1, da die NULL-Arraygröße ungerade ist und eine Spalte tiefen Typs vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="cf05f-261">NULL array padding = 1, as the NULL array size is odd and there is a deep type column.</span></span>  
  
-   <span data-ttu-id="cf05f-262">Auffüllen</span><span class="sxs-lookup"><span data-stu-id="cf05f-262">Padding</span></span>  
  
    -   <span data-ttu-id="cf05f-263">8 ist die größte Ausrichtungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="cf05f-263">8 is the largest alignment requirement.</span></span>  
  
    -   <span data-ttu-id="cf05f-264">Die bisherige Größe ist 16 + 0 + 4 + 1 + 1 = 22.</span><span class="sxs-lookup"><span data-stu-id="cf05f-264">Size so far is 16 + 0 + 4 + 1 + 1 = 22.</span></span>  
  
    -   <span data-ttu-id="cf05f-265">Das nächste Vielfache von 8 ist 24.</span><span class="sxs-lookup"><span data-stu-id="cf05f-265">Nearest multiple of 8 is 24.</span></span>  
  
    -   <span data-ttu-id="cf05f-266">Die Gesamtauffüllung beträgt 24 - 22 = 2 Bytes.</span><span class="sxs-lookup"><span data-stu-id="cf05f-266">Total padding is 24 - 22 = 2 bytes.</span></span>  
  
-   <span data-ttu-id="cf05f-267">Es sind keine Spalten tiefer Typen mit fester Länge vorhanden (Spalten tiefer Typen mit fester Länge: 0.).</span><span class="sxs-lookup"><span data-stu-id="cf05f-267">There are no fixed-length deep type columns (Fixed-length deep type columns: 0.).</span></span>  
  
-   <span data-ttu-id="cf05f-268">Die tatsächliche Größe der Spalte tiefen Typs ist 2 \* 78 = 156.</span><span class="sxs-lookup"><span data-stu-id="cf05f-268">The actual size of deep type column is 2 \* 78 = 156.</span></span> <span data-ttu-id="cf05f-269">Die einzelne Spalte tiefen Typs OrderDescription hat den Typ nvarchar.</span><span class="sxs-lookup"><span data-stu-id="cf05f-269">The single deep type column OrderDescription has type nvarchar.</span></span>  
  
```  
[actual row body size] = 24 + 156 = 180 bytes  
```  
  
 <span data-ttu-id="cf05f-270">Um die Berechnung abzuschließen:</span><span class="sxs-lookup"><span data-stu-id="cf05f-270">To complete the calculation:</span></span>  
  
```  
[row size] = 32 + 180 = 212 bytes  
[table size] = 8 * 16384 + 212 * 8379 = 131072 + 1776348 = 1907420  
```  
  
 <span data-ttu-id="cf05f-271">Die gesamte Tabellengröße im Arbeitsspeicher entspricht daher ungefähr 2 MB.</span><span class="sxs-lookup"><span data-stu-id="cf05f-271">Total table size in memory is thus approximately 2 megabytes.</span></span> <span data-ttu-id="cf05f-272">Dabei wird weder der mögliche Mehraufwand durch die Speicherbelegung noch die Zeilenversionsverwaltung berücksichtigt, die für die Transaktionen benötigt wird, die auf diese Tabelle zugreifen.</span><span class="sxs-lookup"><span data-stu-id="cf05f-272">This does not account for potential overhead incurred by memory allocation as well as any row versioning required for the transactions accessing this table.</span></span>  
  
 <span data-ttu-id="cf05f-273">Der tatsächliche Arbeitsspeicher, der dieser Tabelle zugeordnet ist und von ihr und den zugehörigen Indizes verwendet wird, kann über die folgende Abfrage abgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="cf05f-273">The actual memory allocated for and used by this table and its indexes can be obtained through the following query:</span></span>  
  
```sql  
select * from sys.dm_db_xtp_table_memory_stats  
where object_id = object_id('dbo.Orders')  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf05f-274">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cf05f-274">See Also</span></span>  
 [<span data-ttu-id="cf05f-275">Speicheroptimierte Tabellen</span><span class="sxs-lookup"><span data-stu-id="cf05f-275">Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
  
  
