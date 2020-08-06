---
title: FILESTREAM-Unterstützung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- FILESTREAM [SQL Server], SQL Server Native Client
- SQL Server Native Client [FILESTREAM support]
ms.assetid: 1ad3400d-7fcd-40c9-87ae-f5afc61e0374
author: rothja
ms.author: jroth
ms.openlocfilehash: 18e9a002bfb205e2c0807234550998fe48120d20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698090"
---
# <a name="filestream-support"></a><span data-ttu-id="e234e-102">FILESTREAM-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="e234e-102">FILESTREAM Support</span></span>
  <span data-ttu-id="e234e-103">Die FILESTREAM-Funktion bietet eine Möglichkeit, große binäre Werte zu speichern und entweder über [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] oder durch direkten Zugriff auf das Windows-Dateisystem darauf zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="e234e-103">FILESTREAM provides a way to store and access large binary values, either through [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or by direct access to the Windows file system.</span></span> <span data-ttu-id="e234e-104">Ein großer Binärwert ist ein Wert, der größer als 2 Gigabyte (GB) ist.</span><span class="sxs-lookup"><span data-stu-id="e234e-104">A large binary value is a value larger than 2 gigabytes (GB).</span></span> <span data-ttu-id="e234e-105">Weitere Informationen zur verbesserten FILESTREAM-Unterstützung finden Sie unter [FILESTREAM &#40;SQL Server&#41;](../../blob/filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e234e-105">For more information about enhanced FILESTREAM support, see [FILESTREAM &#40;SQL Server&#41;](../../blob/filestream-sql-server.md).</span></span>  
  
 <span data-ttu-id="e234e-106">Wenn eine Datenbankverbindung geöffnet wird, wird `@@TEXTSIZE` standardmäßig auf -1 ("unbegrenzt") festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e234e-106">When a database connection is opened, `@@TEXTSIZE` will be set to -1 ("unlimited"), by default.</span></span>  
  
 <span data-ttu-id="e234e-107">Es ist auch möglich, mit Windows-Dateisystem-APIs auf FILESTREAM-Spalten zuzugreifen und diese zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e234e-107">It is also possible to access and update FILESTREAM columns using Windows file system APIs.</span></span>  
  
 <span data-ttu-id="e234e-108">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="e234e-108">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="e234e-109">FILESTREAM-Unterstützung &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="e234e-109">FILESTREAM Support &#40;OLE DB&#41;</span></span>](../ole-db/filestream-support-ole-db.md)  
  
-   [<span data-ttu-id="e234e-110">FILESTREAM-Unterstützung &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="e234e-110">FILESTREAM Support &#40;ODBC&#41;</span></span>](../odbc/filestream-support-odbc.md)  
  
-   [<span data-ttu-id="e234e-111">ZUgreifen auf FILESTREAM-Daten mit OpenSqlFilestream</span><span class="sxs-lookup"><span data-stu-id="e234e-111">Access FILESTREAM Data with OpenSqlFilestream</span></span>](../../blob/access-filestream-data-with-opensqlfilestream.md)  
  
## <a name="querying-for-filestream-columns"></a><span data-ttu-id="e234e-112">Abfragen von FILESTREAM-Spalten</span><span class="sxs-lookup"><span data-stu-id="e234e-112">Querying for FILESTREAM Columns</span></span>  
 <span data-ttu-id="e234e-113">Schemarowsets in OLE DB geben nicht an, ob eine Spalte eine FILESTREAM-Spalte ist.</span><span class="sxs-lookup"><span data-stu-id="e234e-113">Schema rowsets in OLE DB will not report whether a column is a FILESTREAM column.</span></span> <span data-ttu-id="e234e-114">ITableDefinition in OLE DB kann nicht verwendet werden, um eine FILESTREAM-Spalte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e234e-114">ITableDefinition in OLE DB cannot be used to create a FILESTREAM column.</span></span>  
  
 <span data-ttu-id="e234e-115">Katalog Funktionen wie SQLColumns in ODBC melden nicht, ob eine Spalte eine FILESTREAM-Spalte ist.</span><span class="sxs-lookup"><span data-stu-id="e234e-115">Catalog functions such as SQLColumns in ODBC will not report whether a column is a FILESTREAM column.</span></span>  
  
 <span data-ttu-id="e234e-116">Zum Erstellen von FILESTREAM-Spalten oder zum erkennen, welche vorhandenen Spalten FILESTREAM-Spalten sind, können Sie die- `is_filestream` Spalte der [sys. Columns](/sql/relational-databases/system-catalog-views/sys-columns-transact-sql) -Katalog Sicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="e234e-116">To create FILESTREAM columns or to detect which existing columns are FILESTREAM columns, you can use the `is_filestream` column of the [sys.columns](/sql/relational-databases/system-catalog-views/sys-columns-transact-sql) catalog view.</span></span>  
  
 <span data-ttu-id="e234e-117">Im Folgenden finden Sie ein Beispiel dazu:</span><span class="sxs-lookup"><span data-stu-id="e234e-117">The following is an example:</span></span>  
  
```  
-- Create a table with a FILESTREAM column.  
CREATE TABLE Bob_01 (GuidCol1 uniqueidentifier ROWGUIDCOL NOT NULL UNIQUE DEFAULT NEWID(), IntCol2 int, varbinaryCol3 varbinary(max) FILESTREAM);  
  
-- Find FILESTREAM columns.  
SELECT name FROM sys.columns WHERE is_filestream=1;  
  
-- Determine whether a column is a FILESTREAM column.  
SELECT is_filestream FROM sys.columns WHERE name = 'varbinaryCol3' AND object_id IN (SELECT object_id FROM sys.tables WHERE name='Bob_01');  
```  
  
## <a name="down-level-compatibility"></a><span data-ttu-id="e234e-118">Kompabilität mit früheren Versionen</span><span class="sxs-lookup"><span data-stu-id="e234e-118">Down-Level Compatibility</span></span>  
 <span data-ttu-id="e234e-119">Wenn der Client mit der Version von Native Client kompiliert wurde, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] die im Lieferumfang von enthalten war [!INCLUDE[ssVersion2005](../../../includes/sscurrent-md.md)] , `varbinary(max)` wird das Verhalten mit kompatibel sein [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e234e-119">If your client was compiled using the version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client that was included with [!INCLUDE[ssVersion2005](../../../includes/sscurrent-md.md)], `varbinary(max)` behavior will be compatible with [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="e234e-120">Das heißt, die Maximalgröße der zurückgegebenen Daten ist auf 2 GB beschränkt.</span><span class="sxs-lookup"><span data-stu-id="e234e-120">That is, the maximum size of returned data will be limited to 2 GB.</span></span> <span data-ttu-id="e234e-121">Ergebniswerte, die größer als 2 GB sind, werden abgeschnitten, und es wird die Warnung „Zeichenfolgendaten werden rechts abgeschnitten“ zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e234e-121">For result values larger that 2 GB, truncation will occur and a "string data right truncation" warning will be returned.</span></span>  
  
 <span data-ttu-id="e234e-122">Wenn Datentypkompatibilität auf 80 festgelegt wird, ist das Clientverhalten mit dem Verhalten von Clients früherer Versionen konsistent.</span><span class="sxs-lookup"><span data-stu-id="e234e-122">When data-type compatibility is set to 80, client behavior will be consistent with down-level client behavior.</span></span>  
  
 <span data-ttu-id="e234e-123">Für Clients, die SQLOLEDB oder andere Anbieter verwenden, die vor dem [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] Native Client freigegeben wurden, `varbinary(max)` wird Image zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="e234e-123">For clients that use SQLOLEDB or other providers that were released before the [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] Native Client, `varbinary(max)` will be mapped to image.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e234e-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e234e-124">See Also</span></span>  
 [<span data-ttu-id="e234e-125">SQL Server Native Client-Funktionen</span><span class="sxs-lookup"><span data-stu-id="e234e-125">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
