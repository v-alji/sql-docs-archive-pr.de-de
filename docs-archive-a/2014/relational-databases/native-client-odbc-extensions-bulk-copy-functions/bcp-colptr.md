---
title: bcp_colptr | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_colptr
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_colptr function
ms.assetid: 02ece13e-1da3-4f9d-b860-3177e43d2471
author: rothja
ms.author: jroth
ms.openlocfilehash: 8b725ace58ee1768fbca1a433cdea27e3e0e546e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725693"
---
# <a name="bcp_colptr"></a><span data-ttu-id="06493-102">bcp_colptr</span><span class="sxs-lookup"><span data-stu-id="06493-102">bcp_colptr</span></span>
  <span data-ttu-id="06493-103">Legt die Datenadresse der Programmvariablen für die aktuelle Kopie in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]fest.</span><span class="sxs-lookup"><span data-stu-id="06493-103">Sets the program variable data address for the current copy into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06493-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="06493-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_colptr (  
HDBC   
hdbc  
,  
LPCBYTE   
pData  
,  
INT   
idxServerCol  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="06493-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="06493-105">Arguments</span></span>  
 <span data-ttu-id="06493-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="06493-106">*hdbc*</span></span>  
 <span data-ttu-id="06493-107">Das für den Massenkopiervorgang aktivierte ODBC-Verbindungshandle.</span><span class="sxs-lookup"><span data-stu-id="06493-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="06493-108">*pData*</span><span class="sxs-lookup"><span data-stu-id="06493-108">*pData*</span></span>  
 <span data-ttu-id="06493-109">Ist ein Zeiger auf die zu kopierenden Daten.</span><span class="sxs-lookup"><span data-stu-id="06493-109">Is a pointer to the data to copy.</span></span> <span data-ttu-id="06493-110">Wenn der gebundene Datentyp ein Typ mit umfangreichen Werten ist (beispielsweise SQLTEXT oder SQLIMAGE), dann kann *pData* NULL sein.</span><span class="sxs-lookup"><span data-stu-id="06493-110">If the bound data type is large value type (such as SQLTEXT or SQLIMAGE), *pData* can be NULL.</span></span> <span data-ttu-id="06493-111">Ein *pData* -Zeiger mit dem Wert NULL gibt an, dass lange Datenwerte mithilfe von [bcp_moretext](bcp-moretext.md)in Ausschnitten an SQL Server gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="06493-111">A NULL *pData* indicates long data values will be sent to SQL Server in chunks using [bcp_moretext](bcp-moretext.md).</span></span>  
  
 <span data-ttu-id="06493-112">Wenn *pData* auf NULL festgelegt wird und die Spalte, die dem gebundenen Feld zugeordnet ist, keinen umfangreichen Datentyp enthält, dann schlägt **bcp_colptr** fehl.</span><span class="sxs-lookup"><span data-stu-id="06493-112">If *pData* is set to NULL and the column corresponding to the bound field is not a large value type, **bcp_colptr** fails.</span></span>  
  
 <span data-ttu-id="06493-113">Weitere Informationen zu Datentypen für umfangreiche Werte finden Sie unter [bcp_bind](bcp-bind.md)**.**</span><span class="sxs-lookup"><span data-stu-id="06493-113">For more information on large value types, see [bcp_bind](bcp-bind.md)**.**</span></span>  
  
 <span data-ttu-id="06493-114">*idxServerCol*</span><span class="sxs-lookup"><span data-stu-id="06493-114">*idxServerCol*</span></span>  
 <span data-ttu-id="06493-115">Die Ordnungsposition der Spalte in der Datenbanktabelle, in die die Daten kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="06493-115">Is the ordinal position of the column in the database table to which the data is copied.</span></span> <span data-ttu-id="06493-116">Die erste Spalte einer Tabelle ist die Spalte 1.</span><span class="sxs-lookup"><span data-stu-id="06493-116">The first column in a table is column 1.</span></span> <span data-ttu-id="06493-117">Die Ordnungsposition einer Spalte wird von [SQLColumns](../native-client-odbc-api/sqlcolumns.md)ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="06493-117">The ordinal position of a column is reported by [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
## <a name="returns"></a><span data-ttu-id="06493-118">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="06493-118">Returns</span></span>  
 <span data-ttu-id="06493-119">SUCCEED oder FAIL.</span><span class="sxs-lookup"><span data-stu-id="06493-119">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06493-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="06493-120">Remarks</span></span>  
 <span data-ttu-id="06493-121">Mit der **bcp_colptr** -Funktion können Sie die Adresse der Quelldaten für eine bestimmte Spalte ändern, wenn Sie Daten mit [bcp_sendrow](bcp-sendrow.md)in SQL Server kopieren.</span><span class="sxs-lookup"><span data-stu-id="06493-121">The **bcp_colptr** function allows you to change the address of source data for a particular column when copying data to SQL Server with [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
 <span data-ttu-id="06493-122">Anfänglich wird der Zeiger auf Benutzerdaten durch einen Aufruf von **bcp_bind**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="06493-122">Initially, the pointer to user data is set by a call to **bcp_bind**.</span></span> <span data-ttu-id="06493-123">Wenn sich die Datenadresse der Programmvariablen zwischen Aufrufen von **bcp_sendrow**ändert, können Sie den Zeiger mit einem Aufruf von **bcp_colptr** auf die Datenadresse zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="06493-123">If the program variable data address changes between calls to **bcp_sendrow**, you can call **bcp_colptr** to reset the pointer to the data.</span></span> <span data-ttu-id="06493-124">Mit dem nächsten Aufruf von **bcp_sendrow** werden die Daten gesendet, die durch den Aufruf von **bcp_colptr**adressiert wurden.</span><span class="sxs-lookup"><span data-stu-id="06493-124">The next call to **bcp_sendrow** sends the data addressed by the call to **bcp_colptr**.</span></span>  
  
 <span data-ttu-id="06493-125">Für jede Tabellenspalte, deren Datenadresse geändert werden soll, muss ein separater **bcp_colptr** -Aufruf angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="06493-125">There must be a separate **bcp_colptr** call for every column in the table whose data address you want to modify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06493-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="06493-126">See Also</span></span>  
 [<span data-ttu-id="06493-127">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="06493-127">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
