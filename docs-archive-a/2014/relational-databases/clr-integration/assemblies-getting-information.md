---
title: Informationen zu Assemblys | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- assemblies [CLR integration], metadata
- status information [SQL Server], assemblies
- metadata [SQL Server], assemblies
ms.assetid: 6aa7f18e-baad-4481-9777-8c3b230b392f
author: rothja
ms.author: jroth
ms.openlocfilehash: ec559ba5ccbb53dd92f3a5e1175a10a59fbaf43c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720071"
---
# <a name="getting-information-about-assemblies"></a><span data-ttu-id="451e6-102">Abrufen von Informationen zu Assemblys</span><span class="sxs-lookup"><span data-stu-id="451e6-102">Getting Information About Assemblies</span></span>
  <span data-ttu-id="451e6-103">Die folgenden Katalogsichten und Funktionen können nach Metadaten zu Assemblys abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="451e6-103">The following catalog views and functions can be queried for metadata about assemblies.</span></span>  
  
 <span data-ttu-id="451e6-104">**So rufen Sie Informationen zu einzelnen Assemblys ab**</span><span class="sxs-lookup"><span data-stu-id="451e6-104">**To get information about individual assemblies**</span></span>  
  
-   [<span data-ttu-id="451e6-105">Assemblyproperty &#40;Transact-SQL-&#41;</span><span class="sxs-lookup"><span data-stu-id="451e6-105">ASSEMBLYPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/assemblyproperty-transact-sql)  
  
 <span data-ttu-id="451e6-106">**So rufen Sie Informationen zu allen Assemblys in der Datenbank ab**</span><span class="sxs-lookup"><span data-stu-id="451e6-106">**To get information about all assemblies in the database**</span></span>  
  
-   [<span data-ttu-id="451e6-107">sys.assemblies &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="451e6-107">sys.assemblies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assemblies-transact-sql)  
  
 <span data-ttu-id="451e6-108">**So rufen Sie Informationen zu Assemblydateien einschließlich Assemblybinärdateien, -quelldateien und -debugdateien ab**</span><span class="sxs-lookup"><span data-stu-id="451e6-108">**To get information about assembly files, including assembly binaries, source files, and debug files**</span></span>  
  
-   [<span data-ttu-id="451e6-109">sys.assembly_files &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="451e6-109">sys.assembly_files &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-files-transact-sql)  
  
 <span data-ttu-id="451e6-110">**So rufen Sie Informationen zu assemblyübergreifenden Verweisen ab**</span><span class="sxs-lookup"><span data-stu-id="451e6-110">**To get information about cross-assembly references**</span></span>  
  
-   [<span data-ttu-id="451e6-111">sys.assembly_references &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="451e6-111">sys.assembly_references &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-references-transact-sql)  
  
 <span data-ttu-id="451e6-112">**So rufen Sie Informationen zu benutzerdefinierten Typen ab**</span><span class="sxs-lookup"><span data-stu-id="451e6-112">**To get assembly information about user-defined types**</span></span>  
  
-   [<span data-ttu-id="451e6-113">sys.assembly_types &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="451e6-113">sys.assembly_types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-types-transact-sql)  
  
-   [<span data-ttu-id="451e6-114">sys.types &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="451e6-114">sys.types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-types-transact-sql)  
  
 <span data-ttu-id="451e6-115">**So rufen Sie Assemblyinformationen zu CLR-gespeicherten Prozeduren, -Triggern und -Funktionen ab**</span><span class="sxs-lookup"><span data-stu-id="451e6-115">**To get assembly information about common language runtime (CLR) stored procedures, triggers, and functions**</span></span>  
  
-   [<span data-ttu-id="451e6-116">sys.assembly_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="451e6-116">sys.assembly_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql)  
  
 <span data-ttu-id="451e6-117">**So rufen Sie Informationen zu Nicht-CLR-Objekten ab**</span><span class="sxs-lookup"><span data-stu-id="451e6-117">**To get information about non-CLR objects**</span></span>  
  
-   [<span data-ttu-id="451e6-118">sys.sql_modules &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="451e6-118">sys.sql_modules &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="451e6-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="451e6-119">See Also</span></span>  
 <span data-ttu-id="451e6-120">[Assemblys &#40;Datenbank-Engine&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="451e6-120">[Assemblies &#40;Database Engine&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span></span>  
 <span data-ttu-id="451e6-121">[Entwerfen von Assembly](../../relational-databases/clr-integration/assemblies-designing.md) </span><span class="sxs-lookup"><span data-stu-id="451e6-121">[Designing Assemblies](../../relational-databases/clr-integration/assemblies-designing.md) </span></span>  
 [<span data-ttu-id="451e6-122">Implementieren von Assemblys</span><span class="sxs-lookup"><span data-stu-id="451e6-122">Implementing Assemblies</span></span>](assemblies-implementing.md)  
  
  
