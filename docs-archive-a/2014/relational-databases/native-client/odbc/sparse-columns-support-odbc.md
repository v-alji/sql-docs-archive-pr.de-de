---
title: Unterstützung für Spalten mit geringer Dichte (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 11ae959f-2fb6-4b85-ac5d-1476a82136d4
author: rothja
ms.author: jroth
ms.openlocfilehash: 076709f3f37e92492f7c3f8c20ee692416d9e867
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718073"
---
# <a name="sparse-columns-support-odbc"></a><span data-ttu-id="2f9ae-102">Unterstützung für Spalten mit geringer Dichte (ODBC)</span><span class="sxs-lookup"><span data-stu-id="2f9ae-102">Sparse Columns Support (ODBC)</span></span>
  <span data-ttu-id="2f9ae-103">In diesem Thema wird die Unterstützung des ODBC-Treibers von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client für Sparsespalten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2f9ae-103">This topic describes [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC support for sparse columns.</span></span> <span data-ttu-id="2f9ae-104">Ein Beispiel zur Veranschaulichung der ODBC-Unterstützung für sparsespalten finden Sie unter " [aufzurufen von SQLColumns" für eine Tabelle mit Spalten](../../native-client-odbc-how-to/call-sqlcolumns-on-a-table-with-sparse-columns.md)</span><span class="sxs-lookup"><span data-stu-id="2f9ae-104">For a sample demonstrating ODBC support for sparse columns, see [Call SQLColumns on a Table with Sparse Columns](../../native-client-odbc-how-to/call-sqlcolumns-on-a-table-with-sparse-columns.md).</span></span> <span data-ttu-id="2f9ae-105">Weitere Informationen zu Sparsespalten finden Sie unter [Sparse Columns Support in SQL Server Native Client](../features/sparse-columns-support-in-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="2f9ae-105">For more information about sparse columns, see [Sparse Columns Support in SQL Server Native Client](../features/sparse-columns-support-in-sql-server-native-client.md).</span></span>  
  
## <a name="statement-metadata"></a><span data-ttu-id="2f9ae-106">Anweisungsmetadaten</span><span class="sxs-lookup"><span data-stu-id="2f9ae-106">Statement Metadata</span></span>  
 <span data-ttu-id="2f9ae-107">Das Deskriptorfeld für den Anwendungsparameterdeskriptor (APD) und das SQL_SOPT_SS_NAME_SCOPE-Anweisungsattribut akzeptieren die zusätzlichen Werte SQL_SS_NAME_SCOPE_EXTENDED und SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET.</span><span class="sxs-lookup"><span data-stu-id="2f9ae-107">The application parameter descriptor (APD) descriptor field and SQL_SOPT_SS_NAME_SCOPE statement attribute accepts the additional values SQL_SS_NAME_SCOPE_EXTENDED and SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET.</span></span> <span data-ttu-id="2f9ae-108">Diese Werte geben an, welche Spalten in dem von [SQLColumns](../../native-client-odbc-api/sqlcolumns.md)zurückgegebenen Resultset enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="2f9ae-108">These values specify which columns are included in the result set returned by [SQLColumns](../../native-client-odbc-api/sqlcolumns.md).</span></span> <span data-ttu-id="2f9ae-109">Weitere Informationen zu SQL_SOPT_SS_NAME_SCOPE finden Sie unter [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="2f9ae-109">For more information about SQL_SOPT_SS_NAME_SCOPE, see [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="2f9ae-110">Mithilfe eines neuen Implementierungszeilendeskriptors (IRD), ein schreibgeschütztes SQLSMALLINT-Feld namens SQL_CA_SS_IS_COLUMN_SET, kann bestimmt werden, ob eine Spalte einen XML `column_set`-Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="2f9ae-110">A new implementation row descriptor (IRD), a read-only SQLSMALLINT field called SQL_CA_SS_IS_COLUMN_SET, can be used to determine if a column is an XML `column_set` value.</span></span> <span data-ttu-id="2f9ae-111">SQL_CA_SS_IS_COLUMN_SET akzeptiert die Werte SQL_TRUE und SQL_FALSE.</span><span class="sxs-lookup"><span data-stu-id="2f9ae-111">SQL_CA_SS_IS_COLUMN_SET takes the values SQL_TRUE and SQL_FALSE.</span></span>  
  
## <a name="catalog-metadata"></a><span data-ttu-id="2f9ae-112">Katalogmetadaten</span><span class="sxs-lookup"><span data-stu-id="2f9ae-112">Catalog Metadata</span></span>  
 <span data-ttu-id="2f9ae-113">Zwei [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -spezifische Spalten (SS_IS_SPARSE and SS_IS_COLUMN_SET) wurden dem Resultset für [SQLColumns](../../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="2f9ae-113">Two [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] specific columns (SS_IS_SPARSE and SS_IS_COLUMN_SET) have been added to the result set for [SQLColumns](../../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
## <a name="odbc-function-support-for-sparse-columns"></a><span data-ttu-id="2f9ae-114">ODBC-Funktionsunterstützung für Spalten mit geringer Dichte</span><span class="sxs-lookup"><span data-stu-id="2f9ae-114">ODBC Function Support for Sparse Columns</span></span>  
 <span data-ttu-id="2f9ae-115">Die folgenden ODBC-Funktionen wurden aktualisiert, um Sparsespalten in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client zu unterstützen:</span><span class="sxs-lookup"><span data-stu-id="2f9ae-115">The following ODBC functions have been updated to support sparse columns in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client:</span></span>  
  
-   [<span data-ttu-id="2f9ae-116">SQLColAttribute</span><span class="sxs-lookup"><span data-stu-id="2f9ae-116">SQLColAttribute</span></span>](../../native-client-odbc-api/sqlcolattribute.md)  
  
-   [<span data-ttu-id="2f9ae-117">SQLColumns</span><span class="sxs-lookup"><span data-stu-id="2f9ae-117">SQLColumns</span></span>](../../native-client-odbc-api/sqlcolumns.md)  
  
-   [<span data-ttu-id="2f9ae-118">SQLGetDescField</span><span class="sxs-lookup"><span data-stu-id="2f9ae-118">SQLGetDescField</span></span>](../../native-client-odbc-api/sqlgetdescfield.md)  
  
-   [<span data-ttu-id="2f9ae-119">SQLSetDescField</span><span class="sxs-lookup"><span data-stu-id="2f9ae-119">SQLSetDescField</span></span>](../../native-client-odbc-api/sqlsetdescfield.md)  
  
-   [<span data-ttu-id="2f9ae-120">SQLSetStmtAttr</span><span class="sxs-lookup"><span data-stu-id="2f9ae-120">SQLSetStmtAttr</span></span>](../../native-client-odbc-api/sqlsetstmtattr.md)  
  
## <a name="see-also"></a><span data-ttu-id="2f9ae-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2f9ae-121">See Also</span></span>  
 [<span data-ttu-id="2f9ae-122">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="2f9ae-122">SQL Server Native Client &#40;ODBC&#41;</span></span>](sql-server-native-client-odbc.md)  
  
  
