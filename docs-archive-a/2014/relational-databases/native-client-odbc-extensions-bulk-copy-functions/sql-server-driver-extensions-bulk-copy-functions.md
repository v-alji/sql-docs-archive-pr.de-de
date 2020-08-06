---
title: Massen Kopierfunktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [ODBC], functions
- ODBC, bulk copy operations
- functions [ODBC]
ms.assetid: 6526b892-1d58-4f55-8335-f09887f6ea02
author: rothja
ms.author: jroth
ms.openlocfilehash: 02dba8cf4d510d2ec5f20e600302bb692c749f97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619098"
---
# <a name="bulk-copy-functions"></a><span data-ttu-id="dc80f-102">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="dc80f-102">Bulk Copy Functions</span></span>
  <span data-ttu-id="dc80f-103">Die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-spezifische API-Erweiterung für Massenkopierfunktionen des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC-Treibers ermöglicht es Clientanwendungen, einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Tabelle auf schnelle Weise Datenzeilen hinzuzufügen bzw. Datenzeilen aus einer Tabelle zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="dc80f-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific bulk-copy API extension of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver allows client applications to rapidly add data rows to, or extract data rows from, a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="dc80f-104">Bei der Verwendung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client können Sie die Massenkopierfunktionen (BCP) in SQLNCLI11.LIB und SQLNCLI.H nutzen.</span><span class="sxs-lookup"><span data-stu-id="dc80f-104">When using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, you can reference the bulk copy functions (BCP) in SQLNCLI11.LIB and SQLNCLI.H.</span></span>  
  
 <span data-ttu-id="dc80f-105">Eine Anwendung, die BCP-API-Funktionsaufrufe verwendet, sollte mit der Bibliothek (LIB-Datei) verknüpft werden, die mit dem von der Anwendung verwendeten Treiber (DLL-Datei) geliefert wurde.</span><span class="sxs-lookup"><span data-stu-id="dc80f-105">An application that uses BCP API function calls should link with the library (.lib) that shipped with the driver (.dll) used by the application.</span></span> <span data-ttu-id="dc80f-106">Eine BCP-Anwendung sollte nicht mit mehr als einer Treiberbibliothek verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="dc80f-106">A BCP application should not link with more than one driver library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dc80f-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="dc80f-107">In This Section</span></span>  
  
-   [<span data-ttu-id="dc80f-108">bcp_batch</span><span class="sxs-lookup"><span data-stu-id="dc80f-108">bcp_batch</span></span>](bcp-batch.md)  
  
-   [<span data-ttu-id="dc80f-109">bcp_bind</span><span class="sxs-lookup"><span data-stu-id="dc80f-109">bcp_bind</span></span>](bcp-bind.md)  
  
-   [<span data-ttu-id="dc80f-110">bcp_colfmt</span><span class="sxs-lookup"><span data-stu-id="dc80f-110">bcp_colfmt</span></span>](bcp-colfmt.md)  
  
-   [<span data-ttu-id="dc80f-111">bcp_collen</span><span class="sxs-lookup"><span data-stu-id="dc80f-111">bcp_collen</span></span>](bcp-collen.md)  
  
-   [<span data-ttu-id="dc80f-112">bcp_colptr</span><span class="sxs-lookup"><span data-stu-id="dc80f-112">bcp_colptr</span></span>](bcp-colptr.md)  
  
-   [<span data-ttu-id="dc80f-113">bcp_columns</span><span class="sxs-lookup"><span data-stu-id="dc80f-113">bcp_columns</span></span>](bcp-columns.md)  
  
-   [<span data-ttu-id="dc80f-114">bcp_control</span><span class="sxs-lookup"><span data-stu-id="dc80f-114">bcp_control</span></span>](bcp-control.md)  
  
-   [<span data-ttu-id="dc80f-115">'bcp_done'</span><span class="sxs-lookup"><span data-stu-id="dc80f-115">bcp_done</span></span>](bcp-done.md)  
  
-   [<span data-ttu-id="dc80f-116">bcp_exec</span><span class="sxs-lookup"><span data-stu-id="dc80f-116">bcp_exec</span></span>](bcp-exec.md)  
  
-   [<span data-ttu-id="dc80f-117">bcp_getcolfmt</span><span class="sxs-lookup"><span data-stu-id="dc80f-117">bcp_getcolfmt</span></span>](bcp-getcolfmt.md)  
  
-   [<span data-ttu-id="dc80f-118">bcp_gettypename</span><span class="sxs-lookup"><span data-stu-id="dc80f-118">bcp_gettypename</span></span>](bcp-gettypename.md)  
  
-   [<span data-ttu-id="dc80f-119">bcp_init</span><span class="sxs-lookup"><span data-stu-id="dc80f-119">bcp_init</span></span>](bcp-init.md)  
  
-   [<span data-ttu-id="dc80f-120">bcp_moretext</span><span class="sxs-lookup"><span data-stu-id="dc80f-120">bcp_moretext</span></span>](bcp-moretext.md)  
  
-   [<span data-ttu-id="dc80f-121">bcp_readfmt</span><span class="sxs-lookup"><span data-stu-id="dc80f-121">bcp_readfmt</span></span>](bcp-readfmt.md)  
  
-   [<span data-ttu-id="dc80f-122">'bcp_sendrow'</span><span class="sxs-lookup"><span data-stu-id="dc80f-122">bcp_sendrow</span></span>](bcp-sendrow.md)  
  
-   [<span data-ttu-id="dc80f-123">bcp_setbulkmode</span><span class="sxs-lookup"><span data-stu-id="dc80f-123">bcp_setbulkmode</span></span>](bcp-setbulkmode.md)  
  
-   [<span data-ttu-id="dc80f-124">bcp_setcolfmt</span><span class="sxs-lookup"><span data-stu-id="dc80f-124">bcp_setcolfmt</span></span>](bcp-setcolfmt.md)  
  
-   [<span data-ttu-id="dc80f-125">bcp_writefmt</span><span class="sxs-lookup"><span data-stu-id="dc80f-125">bcp_writefmt</span></span>](bcp-writefmt.md)  
  
## <a name="see-also"></a><span data-ttu-id="dc80f-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dc80f-126">See Also</span></span>  
 <span data-ttu-id="dc80f-127">[Erweiterungen des SQL Server Treibers](../../database-engine/dev-guide/sql-server-driver-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="dc80f-127">[SQL Server Driver Extensions](../../database-engine/dev-guide/sql-server-driver-extensions.md) </span></span>  
 [<span data-ttu-id="dc80f-128">Ausführen von Massen Kopier Vorgängen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="dc80f-128">Performing Bulk Copy Operations &#40;ODBC&#41;</span></span>](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md)  
  
  
