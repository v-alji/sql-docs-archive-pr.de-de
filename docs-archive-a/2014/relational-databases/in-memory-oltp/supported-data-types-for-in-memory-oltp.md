---
title: Unterstützte Datentypen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: a7380ef0-c9d7-49e4-b6de-fad34752b9f3
author: rothja
ms.author: jroth
ms.openlocfilehash: a7dda500486c39a66f871d5934f957028fc51e9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724665"
---
# <a name="supported-data-types"></a><span data-ttu-id="170e4-102">Unterstützte Datentypen</span><span class="sxs-lookup"><span data-stu-id="170e4-102">Supported Data Types</span></span>
  <span data-ttu-id="170e4-103">Die folgenden Datentypen werden in Speicher optimierten Tabellen und nativ kompilierten gespeicherten Prozeduren **unterstützt** :</span><span class="sxs-lookup"><span data-stu-id="170e4-103">The following data types are **supported** in memory-optimized tables and natively compiled stored procedures:</span></span>  
  
 <span data-ttu-id="170e4-104">**Numerische Datentypen**</span><span class="sxs-lookup"><span data-stu-id="170e4-104">**Numeric Data Types**</span></span>  
  
|<span data-ttu-id="170e4-105">Datentyp</span><span class="sxs-lookup"><span data-stu-id="170e4-105">Data type</span></span>|<span data-ttu-id="170e4-106">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="170e4-106">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="170e4-107">INT</span><span class="sxs-lookup"><span data-stu-id="170e4-107">int</span></span>|[<span data-ttu-id="170e4-108">int, bigint, smallint und tinyint &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="170e4-108">int, bigint, smallint, and tinyint &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|<span data-ttu-id="170e4-109">BIGINT</span><span class="sxs-lookup"><span data-stu-id="170e4-109">bigint</span></span>|[<span data-ttu-id="170e4-110">int, bigint, smallint und tinyint &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="170e4-110">int, bigint, smallint, and tinyint &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|<span data-ttu-id="170e4-111">SMALLINT</span><span class="sxs-lookup"><span data-stu-id="170e4-111">smallint</span></span>|[<span data-ttu-id="170e4-112">int, bigint, smallint und tinyint &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="170e4-112">int, bigint, smallint, and tinyint &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|<span data-ttu-id="170e4-113">TINYINT</span><span class="sxs-lookup"><span data-stu-id="170e4-113">tinyint</span></span>|[<span data-ttu-id="170e4-114">int, bigint, smallint und tinyint &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="170e4-114">int, bigint, smallint, and tinyint &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/int-bigint-smallint-and-tinyint-transact-sql)|  
|<span data-ttu-id="170e4-115">Decimal</span><span class="sxs-lookup"><span data-stu-id="170e4-115">decimal</span></span>|[<span data-ttu-id="170e4-116">decimal und numeric &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="170e4-116">decimal and numeric &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/decimal-and-numeric-transact-sql)|  
|<span data-ttu-id="170e4-117">NUMERIC</span><span class="sxs-lookup"><span data-stu-id="170e4-117">numeric</span></span>|[<span data-ttu-id="170e4-118">decimal und numeric &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="170e4-118">decimal and numeric &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/decimal-and-numeric-transact-sql)|  
|<span data-ttu-id="170e4-119">float</span><span class="sxs-lookup"><span data-stu-id="170e4-119">float</span></span>|[<span data-ttu-id="170e4-120">float und real &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="170e4-120">float and real &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/float-and-real-transact-sql)|  
|<span data-ttu-id="170e4-121">real</span><span class="sxs-lookup"><span data-stu-id="170e4-121">real</span></span>|[<span data-ttu-id="170e4-122">float und real &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="170e4-122">float and real &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/float-and-real-transact-sql)|  
|<span data-ttu-id="170e4-123">money</span><span class="sxs-lookup"><span data-stu-id="170e4-123">money</span></span>|[<span data-ttu-id="170e4-124">money und smallmoney &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="170e4-124">money and smallmoney &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/money-and-smallmoney-transact-sql)|  
|<span data-ttu-id="170e4-125">SMALLMONEY</span><span class="sxs-lookup"><span data-stu-id="170e4-125">smallmoney</span></span>|[<span data-ttu-id="170e4-126">money und smallmoney &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="170e4-126">money and smallmoney &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/money-and-smallmoney-transact-sql)|  
  
 <span data-ttu-id="170e4-127">**Zeichenfolge-Datentypen**</span><span class="sxs-lookup"><span data-stu-id="170e4-127">**String Data Types**</span></span>  
  
|<span data-ttu-id="170e4-128">Datentyp</span><span class="sxs-lookup"><span data-stu-id="170e4-128">Data type</span></span>|<span data-ttu-id="170e4-129">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="170e4-129">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="170e4-130">char(n)</span><span class="sxs-lookup"><span data-stu-id="170e4-130">char(n)</span></span>|[<span data-ttu-id="170e4-131">char und varchar &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="170e4-131">char and varchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/char-and-varchar-transact-sql)|  
|<span data-ttu-id="170e4-132">varchar (n) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="170e4-132">varchar(n) <sup>1</sup></span></span>|[<span data-ttu-id="170e4-133">char und varchar &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="170e4-133">char and varchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/char-and-varchar-transact-sql)|  
|<span data-ttu-id="170e4-134">nchar(n)</span><span class="sxs-lookup"><span data-stu-id="170e4-134">nchar(n)</span></span>|[<span data-ttu-id="170e4-135">nchar und nvarchar &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="170e4-135">nchar and nvarchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql)|  
|<span data-ttu-id="170e4-136">nvarchar (n) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="170e4-136">nvarchar(n) <sup>1</sup></span></span>|[<span data-ttu-id="170e4-137">nchar und nvarchar &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="170e4-137">nchar and nvarchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql)|  
|<span data-ttu-id="170e4-138">sysname</span><span class="sxs-lookup"><span data-stu-id="170e4-138">sysname</span></span>|[<span data-ttu-id="170e4-139">nchar und nvarchar &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="170e4-139">nchar and nvarchar &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql)|  
  
 <span data-ttu-id="170e4-140"><sup>1</sup> die Beschränkung beträgt 8060 Byte pro Zeilen gesamt, Zählung (n) in Typen variabler Länge.</span><span class="sxs-lookup"><span data-stu-id="170e4-140"><sup>1</sup> Limitation is 8060 bytes per row total, counting (n) in variable-length types.</span></span>  
  
 <span data-ttu-id="170e4-141">Weitere Informationen zu unterstützten Sortierungen finden Sie unter [Sortierungen und Codepages](../../database-engine/collations-and-code-pages.md).</span><span class="sxs-lookup"><span data-stu-id="170e4-141">For information about supported collations, see [Collations and Code Pages](../../database-engine/collations-and-code-pages.md).</span></span>  
  
 <span data-ttu-id="170e4-142">**Datums- und Uhrzeitdatentypen:**</span><span class="sxs-lookup"><span data-stu-id="170e4-142">**Date and Time Data Types**</span></span>  
  
|<span data-ttu-id="170e4-143">Datentyp</span><span class="sxs-lookup"><span data-stu-id="170e4-143">Data type</span></span>|<span data-ttu-id="170e4-144">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="170e4-144">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="170e4-145">date</span><span class="sxs-lookup"><span data-stu-id="170e4-145">date</span></span>|[<span data-ttu-id="170e4-146">date &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="170e4-146">date &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/date-transact-sql)|  
|<span data-ttu-id="170e4-147">time</span><span class="sxs-lookup"><span data-stu-id="170e4-147">time</span></span>|[<span data-ttu-id="170e4-148">time &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="170e4-148">time &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/time-transact-sql)|  
|<span data-ttu-id="170e4-149">datetime</span><span class="sxs-lookup"><span data-stu-id="170e4-149">datetime</span></span>|[<span data-ttu-id="170e4-150">datetime &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="170e4-150">datetime &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/datetime-transact-sql)|  
|<span data-ttu-id="170e4-151">datetime2</span><span class="sxs-lookup"><span data-stu-id="170e4-151">datetime2</span></span>|[<span data-ttu-id="170e4-152">datetime2 &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="170e4-152">datetime2 &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/datetime2-transact-sql)|  
|<span data-ttu-id="170e4-153">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="170e4-153">smalldatetime</span></span>|[<span data-ttu-id="170e4-154">smalldatetime &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="170e4-154">smalldatetime &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/smalldatetime-transact-sql)|  
  
 <span data-ttu-id="170e4-155">**Binärdatentypen**</span><span class="sxs-lookup"><span data-stu-id="170e4-155">**Binary Data Types**</span></span>  
  
|<span data-ttu-id="170e4-156">Datentyp</span><span class="sxs-lookup"><span data-stu-id="170e4-156">Data type</span></span>|<span data-ttu-id="170e4-157">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="170e4-157">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="170e4-158">bit</span><span class="sxs-lookup"><span data-stu-id="170e4-158">bit</span></span>|[<span data-ttu-id="170e4-159">bit &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="170e4-159">bit &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/bit-transact-sql)|  
|<span data-ttu-id="170e4-160">binary(n)</span><span class="sxs-lookup"><span data-stu-id="170e4-160">binary(n)</span></span>|[<span data-ttu-id="170e4-161">binary und varbinary &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="170e4-161">binary and varbinary &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/binary-and-varbinary-transact-sql)|  
|<span data-ttu-id="170e4-162">varbinary (n) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="170e4-162">varbinary(n) <sup>1</sup></span></span>|[<span data-ttu-id="170e4-163">binary und varbinary &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="170e4-163">binary and varbinary &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/binary-and-varbinary-transact-sql)|  
  
 <span data-ttu-id="170e4-164"><sup>1</sup> die Beschränkung beträgt 8060 Byte pro Zeilen gesamt, Zählung (n) in Typen variabler Länge.</span><span class="sxs-lookup"><span data-stu-id="170e4-164"><sup>1</sup> Limitation is 8060 bytes per row total, counting (n) in variable-length types.</span></span>  
  
 <span data-ttu-id="170e4-165">**Andere Datentypen**</span><span class="sxs-lookup"><span data-stu-id="170e4-165">**Other data types**</span></span>  
  
|<span data-ttu-id="170e4-166">Datentyp</span><span class="sxs-lookup"><span data-stu-id="170e4-166">Data type</span></span>|<span data-ttu-id="170e4-167">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="170e4-167">For more information</span></span>|  
|---------------|--------------------------|  
|<span data-ttu-id="170e4-168">UNIQUEIDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="170e4-168">uniqueidentifier</span></span>|[<span data-ttu-id="170e4-169">uniqueidentifier &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="170e4-169">uniqueidentifier &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/uniqueidentifier-transact-sql)|  
  
 <span data-ttu-id="170e4-170">**Nicht unterstützte Datentypen**</span><span class="sxs-lookup"><span data-stu-id="170e4-170">**Unsupported Data Types**</span></span>  
  
 <span data-ttu-id="170e4-171">Die folgenden Datentypen werden nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="170e4-171">The following data types are not supported:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="170e4-172">DATETIMEOFFSET</span><span class="sxs-lookup"><span data-stu-id="170e4-172">DATETIMEOFFSET</span></span>|<span data-ttu-id="170e4-173">GEOGRAPHY</span><span class="sxs-lookup"><span data-stu-id="170e4-173">GEOGRAPHY</span></span>|<span data-ttu-id="170e4-174">GEOMETRY</span><span class="sxs-lookup"><span data-stu-id="170e4-174">GEOMETRY</span></span>|  
|<span data-ttu-id="170e4-175">HIERARCHYID</span><span class="sxs-lookup"><span data-stu-id="170e4-175">HIERARCHYID</span></span>|<span data-ttu-id="170e4-176">Large Objects (LOBs, große Objekte).</span><span class="sxs-lookup"><span data-stu-id="170e4-176">Large Objects (LOBs).</span></span> <span data-ttu-id="170e4-177">Beispielsweise varchar(max), nvarchar(max), varbinary(max), image, xml, text oder ntext.</span><span class="sxs-lookup"><span data-stu-id="170e4-177">For example, varchar(max), nvarchar(max), varbinary(max), image, xml, text, and ntext.</span></span>|<span data-ttu-id="170e4-178">ROWVERSION</span><span class="sxs-lookup"><span data-stu-id="170e4-178">ROWVERSION</span></span>|  
|<span data-ttu-id="170e4-179">sql_variant</span><span class="sxs-lookup"><span data-stu-id="170e4-179">sql_variant</span></span>|<span data-ttu-id="170e4-180">CLR-Funktionen</span><span class="sxs-lookup"><span data-stu-id="170e4-180">CLR functions</span></span>|<span data-ttu-id="170e4-181">Benutzerdefinierte Typen (User-defined types, UDTs)</span><span class="sxs-lookup"><span data-stu-id="170e4-181">User-defined types (UDTs)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="170e4-182">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="170e4-182">See Also</span></span>  
 <span data-ttu-id="170e4-183">[Transact-SQL-Unterstützung für In-Memory OLTP](transact-sql-support-for-in-memory-oltp.md) </span><span class="sxs-lookup"><span data-stu-id="170e4-183">[Transact-SQL Support for In-Memory OLTP](transact-sql-support-for-in-memory-oltp.md) </span></span>  
 <span data-ttu-id="170e4-184">[Implementieren von LOB-Spalten in einer Speicher optimierten Tabelle](../../database-engine/implementing-lob-columns-in-a-memory-optimized-table.md) </span><span class="sxs-lookup"><span data-stu-id="170e4-184">[Implementing LOB Columns in a Memory-Optimized Table](../../database-engine/implementing-lob-columns-in-a-memory-optimized-table.md) </span></span>  
 [<span data-ttu-id="170e4-185">Implementieren von SQL_VARIANT in einer speicheroptimierten Tabelle</span><span class="sxs-lookup"><span data-stu-id="170e4-185">Implementing SQL_VARIANT in a Memory-Optimized Table</span></span>](implementing-sql-variant-in-a-memory-optimized-table.md)  
  
  
