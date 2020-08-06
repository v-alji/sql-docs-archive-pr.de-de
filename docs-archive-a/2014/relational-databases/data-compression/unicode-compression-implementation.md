---
title: Implementierung von Unicode-Komprimierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Unicode data compression
- compression [SQL Server], Unicode data
ms.assetid: 44e69e60-9b35-43fe-b9c7-8cf34eaea62a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4c928062169ed7feb03f1031362530474109976a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620991"
---
# <a name="unicode-compression-implementation"></a><span data-ttu-id="ec570-102">Implementierung von Unicode-Komprimierung</span><span class="sxs-lookup"><span data-stu-id="ec570-102">Unicode Compression Implementation</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ec570-103">verwendet eine Implementierung des Algorithmus „Standardkomprimierungsschema für Unicode (SCSU)“, um Unicode-Werte zu komprimieren, die in zeilen- oder seitenkomprimierten Objekten gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="ec570-103">uses an implementation of the Standard Compression Scheme for Unicode (SCSU) algorithm to compress Unicode values that are stored in row or page compressed objects.</span></span> <span data-ttu-id="ec570-104">Für diese komprimierten Objekte erfolgt die Unicode-Komprimierung für `nchar(n)`- und `nvarchar(n)`-Spalten automatisch.</span><span class="sxs-lookup"><span data-stu-id="ec570-104">For these compressed objects, Unicode compression is automatic for `nchar(n)` and `nvarchar(n)` columns.</span></span> <span data-ttu-id="ec570-105">[!INCLUDE[ssDE](../../includes/ssde-md.md)] speichert Unicode-Daten als 2 Bytes, unabhängig vom Gebietsschema.</span><span class="sxs-lookup"><span data-stu-id="ec570-105">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] stores Unicode data as 2 bytes, regardless of locale.</span></span> <span data-ttu-id="ec570-106">Dies wird UCS-2-Codierung genannt.</span><span class="sxs-lookup"><span data-stu-id="ec570-106">This is known as UCS-2 encoding.</span></span> <span data-ttu-id="ec570-107">Bei einigen Gebietsschemas kann durch die Implementierung der SCSU-Komprimierung in SQL Server bis zu 50 Prozent des Speicherplatzes eingespart werden.</span><span class="sxs-lookup"><span data-stu-id="ec570-107">For some locales, the implementation of SCSU compression in SQL Server can save up to 50 percent in storage space.</span></span>  
  
## <a name="supported-data-types"></a><span data-ttu-id="ec570-108">Unterstützte Datentypen</span><span class="sxs-lookup"><span data-stu-id="ec570-108">Supported Data Types</span></span>  
 <span data-ttu-id="ec570-109">Unicode-Komprimierung unterstützt den `nchar(n)`-Datentyp mit fester Länge und den `nvarchar(n)`-Datentyp.</span><span class="sxs-lookup"><span data-stu-id="ec570-109">Unicode compression supports the fixed-length `nchar(n)` and `nvarchar(n)` data types.</span></span> <span data-ttu-id="ec570-110">Datenwerte, die außerhalb von Zeilen oder in `nvarchar(max)`-Spalten gespeichert werden, werden nicht komprimiert.</span><span class="sxs-lookup"><span data-stu-id="ec570-110">Data values that are stored off row or in `nvarchar(max)` columns are not compressed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec570-111">Unicode-Komprimierung wird nicht für `nvarchar(max)`-Daten unterstützt, auch wenn sie in Zeile gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="ec570-111">Unicode compression is not supported for `nvarchar(max)` data even if it is stored in row.</span></span> <span data-ttu-id="ec570-112">Dieser Datentyp kann immer noch jedoch von der Seitenkomprimierung profitieren.</span><span class="sxs-lookup"><span data-stu-id="ec570-112">However, this data type can still benefit from page compression.</span></span>  
  
## <a name="upgrading-from-earlier-versions-of-sql-server"></a><span data-ttu-id="ec570-113">Aktualisieren von früheren Versionen von SQL Server</span><span class="sxs-lookup"><span data-stu-id="ec570-113">Upgrading from Earlier Versions of SQL Server</span></span>  
 <span data-ttu-id="ec570-114">Wenn eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datenbank auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] aktualisiert wird, werden keine Änderungen im Zusammenhang mit Unicode-Komprimierung für die Datenbankobjekte durchgeführt – unabhängig davon, ob diese komprimiert oder nicht komprimiert sind.</span><span class="sxs-lookup"><span data-stu-id="ec570-114">When a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database is upgraded to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], Unicode compression-related changes are not made to any database object, compressed or uncompressed.</span></span> <span data-ttu-id="ec570-115">Das Datenbankupgrade wirkt sich wie folgt auf Objekte aus:</span><span class="sxs-lookup"><span data-stu-id="ec570-115">After the database is upgraded, objects are affected as follows:</span></span>  
  
-   <span data-ttu-id="ec570-116">Wenn das Objekt nicht komprimiert ist, werden keine Änderungen durchgeführt, und das Objekt funktioniert wie bisher.</span><span class="sxs-lookup"><span data-stu-id="ec570-116">If the object is not compressed, no changes are made and the object continues to function as it did previously.</span></span>  
  
-   <span data-ttu-id="ec570-117">Zeilen- oder seitenkomprimierte Objekte funktionieren wie bisher.</span><span class="sxs-lookup"><span data-stu-id="ec570-117">Row- or page-compressed objects continue to function as they did previously.</span></span> <span data-ttu-id="ec570-118">Unkomprimierte Daten liegen in unkomprimierter Form vor, bis ihr Wert aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="ec570-118">Uncompressed data remains in uncompressed form until its value is updated.</span></span>  
  
-   <span data-ttu-id="ec570-119">Neue Zeilen, die in eine zeilen- oder seitenkomprimierte Tabelle eingefügt werden, werden mittels Unicode-Komprimierung komprimiert.</span><span class="sxs-lookup"><span data-stu-id="ec570-119">New rows that are inserted into a row- or page-compressed table are compressed using Unicode compression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ec570-120">Um die Vorteile der Unicode-Komprimierung in vollem Umfang zu nutzen, muss das Objekt mit Seiten- oder Zeilenkomprimierung neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ec570-120">To take full advantage of the benefits of Unicode compression, the object must be rebuilt with page or row compression.</span></span>  
  
## <a name="how-unicode-compression-affects-data-storage"></a><span data-ttu-id="ec570-121">Auswirkungen der Unicode-Komprimierung auf Datenspeicher</span><span class="sxs-lookup"><span data-stu-id="ec570-121">How Unicode Compression Affects Data Storage</span></span>  
 <span data-ttu-id="ec570-122">Wenn ein Index erstellt wird oder neu erstellt wird oder wenn ein Wert in einer Tabelle geändert wird, die mit Zeilen- oder Seitenkomprimierung komprimiert wurde, wird der betroffene Index oder Wert nur dann komprimiert gespeichert, wenn die komprimierte Größe kleiner als die aktuelle Größe ist.</span><span class="sxs-lookup"><span data-stu-id="ec570-122">When an index is created or rebuilt or when a value is changed in a table that was compressed with row or page compression, the affected index or value is stored compressed only if its compressed size is less than its current size.</span></span> <span data-ttu-id="ec570-123">Dies verhindert, dass Zeilen in einer Tabelle oder in einem Index aufgrund der Unicode-Komprimierung an Größe zunehmen.</span><span class="sxs-lookup"><span data-stu-id="ec570-123">This prevents rows in a table or index from increasing in size because of Unicode compression.</span></span>  
  
 <span data-ttu-id="ec570-124">Der Speicherplatz, der durch die Komprimierung eingespart wird, ist von den Eigenschaften der Daten abhängig, die komprimiert werden, und vom Gebietsschema der Daten.</span><span class="sxs-lookup"><span data-stu-id="ec570-124">The storage space that compression saves depends on the characteristics of the data that is being compressed and the locale of the data.</span></span> <span data-ttu-id="ec570-125">In der folgenden Tabelle werden die Speicherplatzeinsparungen aufgelistet, die für verschiedene Gebietsschemas erreicht werden können.</span><span class="sxs-lookup"><span data-stu-id="ec570-125">The following table lists the space savings that can be achieved for several locales.</span></span>  
  
|<span data-ttu-id="ec570-126">Gebietsschema</span><span class="sxs-lookup"><span data-stu-id="ec570-126">Locale</span></span>|<span data-ttu-id="ec570-127">Komprimierung in Prozent</span><span class="sxs-lookup"><span data-stu-id="ec570-127">Compression percent</span></span>|  
|------------|-------------------------|  
|<span data-ttu-id="ec570-128">Englisch</span><span class="sxs-lookup"><span data-stu-id="ec570-128">English</span></span>|<span data-ttu-id="ec570-129">50%</span><span class="sxs-lookup"><span data-stu-id="ec570-129">50%</span></span>|  
|<span data-ttu-id="ec570-130">Deutsch</span><span class="sxs-lookup"><span data-stu-id="ec570-130">German</span></span>|<span data-ttu-id="ec570-131">50%</span><span class="sxs-lookup"><span data-stu-id="ec570-131">50%</span></span>|  
|<span data-ttu-id="ec570-132">Hindi</span><span class="sxs-lookup"><span data-stu-id="ec570-132">Hindi</span></span>|<span data-ttu-id="ec570-133">50%</span><span class="sxs-lookup"><span data-stu-id="ec570-133">50%</span></span>|  
|<span data-ttu-id="ec570-134">Türkisch</span><span class="sxs-lookup"><span data-stu-id="ec570-134">Turkish</span></span>|<span data-ttu-id="ec570-135">48 %</span><span class="sxs-lookup"><span data-stu-id="ec570-135">48%</span></span>|  
|<span data-ttu-id="ec570-136">Vietnamesisch</span><span class="sxs-lookup"><span data-stu-id="ec570-136">Vietnamese</span></span>|<span data-ttu-id="ec570-137">39%</span><span class="sxs-lookup"><span data-stu-id="ec570-137">39%</span></span>|  
|<span data-ttu-id="ec570-138">Japanisch</span><span class="sxs-lookup"><span data-stu-id="ec570-138">Japanese</span></span>|<span data-ttu-id="ec570-139">15 %</span><span class="sxs-lookup"><span data-stu-id="ec570-139">15%</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec570-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ec570-140">See Also</span></span>  
 <span data-ttu-id="ec570-141">[Datenkomprimierung](data-compression.md) </span><span class="sxs-lookup"><span data-stu-id="ec570-141">[Data Compression](data-compression.md) </span></span>  
 <span data-ttu-id="ec570-142">[sp_estimate_data_compression_savings &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-estimate-data-compression-savings-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ec570-142">[sp_estimate_data_compression_savings &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-estimate-data-compression-savings-transact-sql) </span></span>  
 <span data-ttu-id="ec570-143">[Implementierung von Seitenkomprimierung](page-compression-implementation.md) </span><span class="sxs-lookup"><span data-stu-id="ec570-143">[Page Compression Implementation](page-compression-implementation.md) </span></span>  
 [<span data-ttu-id="ec570-144">sys.dm_db_persisted_sku_features &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ec570-144">sys.dm_db_persisted_sku_features &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-persisted-sku-features-transact-sql)  
  
  
