---
title: Verwenden von Datendateien und Format Dateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy [ODBC], file formats
- ODBC, functions
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [SQL Server Native Client]
- ODBC, bulk copy operations
- bulk copy [ODBC], data files
ms.assetid: c01b7155-3f0a-473d-90b7-87a97bc56ca5
author: rothja
ms.author: jroth
ms.openlocfilehash: 4e0ee92f79e2c8cab9605db0188e01898df8c23e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725709"
---
# <a name="using-data-files-and-format-files"></a><span data-ttu-id="3796c-102">Verwenden von Datendateien und Formatdateien</span><span class="sxs-lookup"><span data-stu-id="3796c-102">Using Data Files and Format Files</span></span>
  <span data-ttu-id="3796c-103">Das einfachste Massenkopierprogramm geht wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="3796c-103">The simplest bulk copy program does the following:</span></span>  
  
1.  <span data-ttu-id="3796c-104">Ruft [bcp_init](../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) auf, um das Massen kopieren (BCP_OUT) aus einer Tabelle oder Sicht in eine Datendatei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3796c-104">Calls [bcp_init](../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) to specify bulk copying out (set BCP_OUT) from a table or view to a data file.</span></span>  
  
2.  <span data-ttu-id="3796c-105">Ruft [bcp_exec](../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) auf, um den Massen Kopiervorgang auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3796c-105">Calls [bcp_exec](../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) to execute the bulk copy operation.</span></span>  
  
 <span data-ttu-id="3796c-106">Die Datendatei wird im einheitlichen Modus erstellt. Daher werden Daten aus allen Spalten in der Tabelle oder Sicht in der Datendatei im gleichen Format wie in der Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3796c-106">The data file is created in native mode; therefore, data from all columns in the table or view are stored in the data file in the same format as in the database.</span></span> <span data-ttu-id="3796c-107">Die Datei kann dann mit derselben Vorgehensweise auf einen Server massenkopiert werden, mit der Ausnahme, dass DB_IN statt DB_OUT festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="3796c-107">The file can then be bulk copied into a server by using these same steps and setting DB_IN instead of DB_OUT.</span></span> <span data-ttu-id="3796c-108">Dies funktioniert jedoch nur, wenn sowohl die Quell- als auch die Zieltabellen genau dieselbe Struktur aufweisen.</span><span class="sxs-lookup"><span data-stu-id="3796c-108">This works only if both the source and target tables have exactly the same structure.</span></span> <span data-ttu-id="3796c-109">Die resultierende Datendatei kann auch mit dem Schalter **/n** (einheitlicher Modus) als Eingabe für das **bcp** -Hilfsprogramm verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3796c-109">The resulting data file can also be input to the **bcp** utility by using the **/n** (native mode) switch.</span></span>  
  
 <span data-ttu-id="3796c-110">So führen Sie einen Massenkopiervorgang des Resultsets einer [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung aus, anstatt direkt aus einer Tabelle oder Sicht zu kopieren:</span><span class="sxs-lookup"><span data-stu-id="3796c-110">To bulk copy out the result set of a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement instead of directly from a table or view:</span></span>  
  
1.  <span data-ttu-id="3796c-111">Ruft **bcp_init** auf, um das Massen kopieren anzugeben, aber geben Sie NULL für den Tabellennamen an.</span><span class="sxs-lookup"><span data-stu-id="3796c-111">Call **bcp_init** to specify bulk copying out, but specify NULL for the table name.</span></span>  
  
2.  <span data-ttu-id="3796c-112">Ruft [bcp_control](../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) auf, bei dem *eOption* auf BCPHINTS festgelegt und *iValue* auf einen Zeiger auf eine SQLTCHAR-Zeichenfolge festgelegt ist, die die Transact-SQL-Anweisung enthält.</span><span class="sxs-lookup"><span data-stu-id="3796c-112">Call [bcp_control](../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) with *eOption* set to BCPHINTS and *iValue* set to a pointer to a SQLTCHAR string containing the Transact-SQL statement.</span></span>  
  
3.  <span data-ttu-id="3796c-113">Rufen Sie **bcp_exec** auf, um den Massenkopiervorgang auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3796c-113">Call **bcp_exec** to execute the bulk copy operation.</span></span>  
  
 <span data-ttu-id="3796c-114">Die [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung kann jede Anweisung sein, die ein Resultset generiert.</span><span class="sxs-lookup"><span data-stu-id="3796c-114">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statement can be any statement that generates a result set.</span></span> <span data-ttu-id="3796c-115">Die Datendatei wird mit dem ersten Resultset der [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung erstellt.</span><span class="sxs-lookup"><span data-stu-id="3796c-115">The data file is created containing the first result set of the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="3796c-116">Beim Massenkopieren wird jedes Resultset nach dem ersten ignoriert, wenn die [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung mehrere Resultsets generiert.</span><span class="sxs-lookup"><span data-stu-id="3796c-116">Bulk copy ignores any result set after the first if the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement generates multiple result sets.</span></span>  
  
 <span data-ttu-id="3796c-117">Wenn Sie eine Datendatei erstellen möchten, in der Spaltendaten in einem anderen Format als in der Tabelle gespeichert werden, rufen Sie [bcp_columns](../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md) auf, um anzugeben, wie viele Spalten geändert werden, und rufen Sie dann [bcp_colfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md) für jede Spalte auf, deren Format Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="3796c-117">To create a data file in which column data is stored in a different format than in the table, call [bcp_columns](../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md) to specify how many columns will be changed, then call [bcp_colfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md) for each column whose format you want to change.</span></span> <span data-ttu-id="3796c-118">Dies erfolgt nach dem Aufrufen von **bcp_init** , aber vor dem Aufrufen von **bcp_exec**.</span><span class="sxs-lookup"><span data-stu-id="3796c-118">This is done after calling **bcp_init** but before calling **bcp_exec**.</span></span> <span data-ttu-id="3796c-119">**bcp_colfmt** gibt das Format an, in dem die Daten der Spalte in der Datendatei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="3796c-119">**bcp_colfmt** specifies the format in which the column's data is stored in the data file.</span></span> <span data-ttu-id="3796c-120">Sie kann verwendet werden, wenn ein Massen Kopiervorgang oder ein Massen Kopiervorgang durch Sie können **bcp_colfmt** auch zum Festlegen der Zeilen-und Spalten Terminatoren verwenden.</span><span class="sxs-lookup"><span data-stu-id="3796c-120">It can be used when bulk copying in or out. You can also use **bcp_colfmt** to set the row and column terminators.</span></span> <span data-ttu-id="3796c-121">Wenn die Daten z. b. keine Tabulator Zeichen enthalten, können Sie eine durch Tabstopps getrennte Datei erstellen, indem Sie **bcp_colfmt** verwenden, um das Tabstopp Zeichen als Abschluss Zeichen für die einzelnen Spalten festzulegen.</span><span class="sxs-lookup"><span data-stu-id="3796c-121">For example, if your data contains no tab characters, you can create a tab-delimited file by using **bcp_colfmt** to set the tab character as the terminator for each column.</span></span>  
  
 <span data-ttu-id="3796c-122">Beim Massen kopieren und Verwenden von **bcp_colfmt**können Sie auf einfache Weise eine Format Datei erstellen, die die erstellte Datendatei beschreibt, indem Sie [bcp_writefmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-writefmt.md) nach dem letzten Aufruf von **bcp_colfmt**aufrufen.</span><span class="sxs-lookup"><span data-stu-id="3796c-122">When bulk copying out and using **bcp_colfmt**, you can easily create a format file describing the data file you have created by calling [bcp_writefmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-writefmt.md) after the last call to **bcp_colfmt**.</span></span>  
  
 <span data-ttu-id="3796c-123">Beim Massen kopieren aus einer Datendatei, die von einer Format Datei beschrieben wird, lesen Sie die Format Datei, indem Sie [bcp_readfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md) nach **bcp_init** , aber vor **bcp_exec**aufrufen.</span><span class="sxs-lookup"><span data-stu-id="3796c-123">When bulk copying in from a data file described by a format file, read the format file by calling [bcp_readfmt](../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md) after **bcp_init** but before **bcp_exec**.</span></span>  
  
 <span data-ttu-id="3796c-124">Die **bcp_control** -Funktion steuert beim Massen kopieren [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aus einer Datendatei mehrere Optionen.</span><span class="sxs-lookup"><span data-stu-id="3796c-124">The **bcp_control** function controls several options when bulk copying into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a data file.</span></span> <span data-ttu-id="3796c-125">**bcp_control** legt Optionen fest, z. b. die maximale Anzahl von Fehlern vor dem Beenden, die Zeile in der Datei, in der der Massen Kopiervorgang gestartet werden soll, die Zeile, für die der Vorgang beendet werden soll, und die Batch Größe.</span><span class="sxs-lookup"><span data-stu-id="3796c-125">**bcp_control** sets options, such as the maximum number of errors before termination, the row in the file on which to start the bulk copy, the row to stop on, and the batch size.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3796c-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3796c-126">See Also</span></span>  
 [<span data-ttu-id="3796c-127">Ausführen von Massen Kopier Vorgängen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="3796c-127">Performing Bulk Copy Operations &#40;ODBC&#41;</span></span>](performing-bulk-copy-operations-odbc.md)  
  
  
