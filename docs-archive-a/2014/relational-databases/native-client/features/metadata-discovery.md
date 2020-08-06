---
title: Metadatenermittlung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: ec3c0f4f-f838-43ce-85f2-cf2761e2aac5
author: rothja
ms.author: jroth
ms.openlocfilehash: 571df9f21ab46a53c8aba7907039ce02afd6ad05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698067"
---
# <a name="metadata-discovery"></a><span data-ttu-id="c46dc-102">Metadatenermittlung</span><span class="sxs-lookup"><span data-stu-id="c46dc-102">Metadata Discovery</span></span>
  <span data-ttu-id="c46dc-103">Aufgrund der verbesserten Metadatenermittlung in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] können [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-Anwendungen sicherstellen, dass Spalten- oder Parametermetadaten, die von der Ausführung einer Abfrage zurückgegeben werden, mit dem Metadatenformat identisch oder kompatibel sind, das Sie vor dem Ausführen der Abfrage angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="c46dc-103">The metadata discovery improvement in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] allows [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client applications to ensure that column or parameter metadata returned from the execution of a query is identical to or compatible with the metadata format you specified before you executed the query.</span></span> <span data-ttu-id="c46dc-104">Wenn die nach der Ausführung der Abfrage zurückgegebenen Metadaten nicht mit dem Metadatenformat identisch sind, das Sie vor der Ausführung der Abfrage angegeben haben, wird ein Fehler ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="c46dc-104">You will receive an error if the metadata returned after query execution is not compatible with the metadata format you specified before query execution.</span></span>  
  
 <span data-ttu-id="c46dc-105">Sie können jetzt in bcp- und ODBC-Funktionen sowie in IBCPSession- und IBCPSession2-Schnittstellen verzögertes Lesen (verzögerte Metadatenerkennung) angeben, um Metadatenermittlung für Abfrageausgabevorgänge zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="c46dc-105">In bcp and ODBC functions, and IBCPSession and IBCPSession2 interfaces, you can now specify a delayed read (delayed metadata discovery) to avoid metadata discovery for query out operations.</span></span> <span data-ttu-id="c46dc-106">Dies verbessert die Leistung und schließt Metadatenermittlungsfehler aus.</span><span class="sxs-lookup"><span data-stu-id="c46dc-106">This improves performance and eliminates metadata discovery failures.</span></span>  
  
 <span data-ttu-id="c46dc-107">Wenn Sie eine Anwendung mit [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] entwickeln, jedoch eine Verbindung mit einer früheren Serverversion als [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]herstellen, entspricht die Funktionalität der Metadatenermittlung der Version des Servers.</span><span class="sxs-lookup"><span data-stu-id="c46dc-107">If you develop an application using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] but connect to a server version earlier than [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], metadata discovery functionality will correspond to the version of the server.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c46dc-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c46dc-108">Remarks</span></span>  
 <span data-ttu-id="c46dc-109">Die folgenden bcp-Funktionen wurden in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] verbessert, um verbesserte Metadatenermittlung bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="c46dc-109">The following bcp functions have been enhanced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] to provide improved metadata discovery:</span></span>  
  
-   [<span data-ttu-id="c46dc-110">bcp_columns</span><span class="sxs-lookup"><span data-stu-id="c46dc-110">bcp_columns</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md)  
  
-   [<span data-ttu-id="c46dc-111">bcp_control</span><span class="sxs-lookup"><span data-stu-id="c46dc-111">bcp_control</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md)  
  
-   [<span data-ttu-id="c46dc-112">bcp_getcolfmt</span><span class="sxs-lookup"><span data-stu-id="c46dc-112">bcp_getcolfmt</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-getcolfmt.md)  
  
-   [<span data-ttu-id="c46dc-113">bcp_readfmt</span><span class="sxs-lookup"><span data-stu-id="c46dc-113">bcp_readfmt</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md)  
  
-   [<span data-ttu-id="c46dc-114">bcp_setcolfmt</span><span class="sxs-lookup"><span data-stu-id="c46dc-114">bcp_setcolfmt</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-setcolfmt.md)  
  
 <span data-ttu-id="c46dc-115">Das Angeben des Metadatenformats mit [bcp_setbulkmode](../../native-client-odbc-extensions-bulk-copy-functions/bcp-setbulkmode.md)führt ebenfalls zu einer Leistungsverbesserung.</span><span class="sxs-lookup"><span data-stu-id="c46dc-115">You will also see a performance improvement when specifying metadata format using [bcp_setbulkmode](../../native-client-odbc-extensions-bulk-copy-functions/bcp-setbulkmode.md).</span></span>  
  
 <span data-ttu-id="c46dc-116">[bcp_control](../../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) verfügt über eine neue *eOption* zum Steuern des Verhaltens von bcp_readfmt: `BCPDELAYREADFMT` .</span><span class="sxs-lookup"><span data-stu-id="c46dc-116">[bcp_control](../../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) has a new *eOption* to control the behavior of bcp_readfmt: `BCPDELAYREADFMT`.</span></span>  
  
 <span data-ttu-id="c46dc-117">Die folgenden ODBC-Funktionen wurden in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] verbessert, um verbesserte Metadatenermittlung bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="c46dc-117">The following ODBC functions have been enhanced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] to provide improved metadata discovery:</span></span>  
  
-   [<span data-ttu-id="c46dc-118">SQLNumResultCols</span><span class="sxs-lookup"><span data-stu-id="c46dc-118">SQLNumResultCols</span></span>](../../native-client-odbc-api/sqlnumresultcols.md)  
  
-   [<span data-ttu-id="c46dc-119">SQLDescribeCol</span><span class="sxs-lookup"><span data-stu-id="c46dc-119">SQLDescribeCol</span></span>](../../native-client-odbc-api/sqldescribecol.md)  
  
-   [<span data-ttu-id="c46dc-120">SQLNumParams</span><span class="sxs-lookup"><span data-stu-id="c46dc-120">SQLNumParams</span></span>](../../native-client-odbc-api/sqlnumparams.md)  
  
-   [<span data-ttu-id="c46dc-121">SQLDescribeParam</span><span class="sxs-lookup"><span data-stu-id="c46dc-121">SQLDescribeParam</span></span>](../../native-client-odbc-api/sqldescribeparam.md)  
  
 <span data-ttu-id="c46dc-122">Die folgenden OLE DB-Elementfunktionen wurden in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] verbessert, um verbesserte Metadatenermittlung bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="c46dc-122">The following OLE DB member functions have been enhanced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] to provide improved metadata discovery:</span></span>  
  
-   <span data-ttu-id="c46dc-123">IColumnsInfo::GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="c46dc-123">IColumnsInfo::GetColumnInfo</span></span>  
  
-   <span data-ttu-id="c46dc-124">IColumnsRowset::GetColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="c46dc-124">IColumnsRowset::GetColumnsRowset</span></span>  
  
-   <span data-ttu-id="c46dc-125">ICommandWithParameters::GetParameterInfo (Weitere Informationen finden Sie unter [ICommandWithParameters](../../native-client-ole-db-interfaces/icommandwithparameters.md).)</span><span class="sxs-lookup"><span data-stu-id="c46dc-125">ICommandWithParameters::GetParameterInfo (see [ICommandWithParameters](../../native-client-ole-db-interfaces/icommandwithparameters.md) for more information)</span></span>  
  
 <span data-ttu-id="c46dc-126">Das Angeben des Metadatenformats mit IBCPSession::BCPSetBulkMode führt ebenfalls zu einer Leistungsverbesserung.</span><span class="sxs-lookup"><span data-stu-id="c46dc-126">You will also see a performance improvement when specifying metadata format using IBCPSession::BCPSetBulkMode</span></span>  
  
 <span data-ttu-id="c46dc-127">Die verbesserte Metadatenermittlung in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client wurde durch das Hinzufügen von zwei gespeicherten Prozeduren in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]ermöglicht:</span><span class="sxs-lookup"><span data-stu-id="c46dc-127">The improved metadata discovery in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client is possible because of the addition of two stored procedures in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]:</span></span>  
  
-   <span data-ttu-id="c46dc-128">sp_describe_first_result_set</span><span class="sxs-lookup"><span data-stu-id="c46dc-128">sp_describe_first_result_set</span></span>  
  
-   <span data-ttu-id="c46dc-129">sp_describe_undeclared_parameters</span><span class="sxs-lookup"><span data-stu-id="c46dc-129">sp_describe_undeclared_parameters</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c46dc-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c46dc-130">See Also</span></span>  
 [<span data-ttu-id="c46dc-131">SQL Server Native Client-Funktionen</span><span class="sxs-lookup"><span data-stu-id="c46dc-131">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
