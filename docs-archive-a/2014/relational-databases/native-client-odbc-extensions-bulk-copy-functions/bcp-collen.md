---
title: bcp_collen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_collen
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_collen function
ms.assetid: faaf1f7a-81f2-4852-a178-56602c33673a
author: rothja
ms.author: jroth
ms.openlocfilehash: 3099e26b0c2cd0d1cfee7578f5b149b812f01765
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725689"
---
# <a name="bcp_collen"></a><span data-ttu-id="49c50-102">bcp_collen</span><span class="sxs-lookup"><span data-stu-id="49c50-102">bcp_collen</span></span>
  <span data-ttu-id="49c50-103">Legt die Datenlänge in der Programmvariable für das aktuelle Massenkopieren nach [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]fest.</span><span class="sxs-lookup"><span data-stu-id="49c50-103">Sets the data length in the program variable for the current bulk copy into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49c50-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="49c50-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_collen (  
HDBC   
hdbc  
,  
DBINT   
cbData  
,  
INT   
idxServerCol  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="49c50-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="49c50-105">Arguments</span></span>  
 <span data-ttu-id="49c50-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="49c50-106">*hdbc*</span></span>  
 <span data-ttu-id="49c50-107">Das für den Massenkopiervorgang aktivierte ODBC-Verbindungshandle.</span><span class="sxs-lookup"><span data-stu-id="49c50-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="49c50-108">*cbData*</span><span class="sxs-lookup"><span data-stu-id="49c50-108">*cbData*</span></span>  
 <span data-ttu-id="49c50-109">Die Länge der Daten in der Programmvariable ohne die Länge eines Längenindikators oder Längenabschlusszeichens.</span><span class="sxs-lookup"><span data-stu-id="49c50-109">Is the length of the data in the program variable, not including the length of any length indicator or terminator.</span></span> <span data-ttu-id="49c50-110">Wenn Sie *cbData* auf SQL_NULL_DATA setzen, wird angegeben, dass alle zum Server kopierten Zeilen einen NULL-Wert für die Spalte enthalten.</span><span class="sxs-lookup"><span data-stu-id="49c50-110">Setting *cbData* to SQL_NULL_DATA indicates all rows copied to the server contain a NULL value for the column.</span></span> <span data-ttu-id="49c50-111">Wenn Sie es auf SQL_VARLEN_DATA setzen, geben Sie damit an, dass ein Zeichenfolgenabschlusszeichen oder eine andere Methode verwendet wird, um die Länge der kopierten Daten zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="49c50-111">Setting it to SQL_VARLEN_DATA indicates that a string terminator or other method is used to determine the length of data copied.</span></span> <span data-ttu-id="49c50-112">Wenn sowohl ein Längenindikator als auch ein Abschlusszeichen vorliegen, bestimmt das System, was verwendet werden soll, daran, bei welchem Vorgang weniger Daten kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="49c50-112">If both a length indicator and a terminator exist, the system uses whichever one results in less data being copied.</span></span>  
  
 <span data-ttu-id="49c50-113">*idxServerCol*</span><span class="sxs-lookup"><span data-stu-id="49c50-113">*idxServerCol*</span></span>  
 <span data-ttu-id="49c50-114">Die Ordnungsposition der Spalte in der Tabelle, in die die Daten kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="49c50-114">Is the ordinal position of the column in the table to which the data is copied.</span></span> <span data-ttu-id="49c50-115">Die erste Spalte ist 1.</span><span class="sxs-lookup"><span data-stu-id="49c50-115">The first column is 1.</span></span> <span data-ttu-id="49c50-116">Die Ordnungsposition einer Spalte wird von [SQLColumns](../native-client-odbc-api/sqlcolumns.md)ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="49c50-116">The ordinal position of a column is reported by [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
## <a name="returns"></a><span data-ttu-id="49c50-117">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="49c50-117">Returns</span></span>  
 <span data-ttu-id="49c50-118">SUCCEED oder FAIL.</span><span class="sxs-lookup"><span data-stu-id="49c50-118">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49c50-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="49c50-119">Remarks</span></span>  
 <span data-ttu-id="49c50-120">Mit der **bcp_collen** -Funktion können Sie die Datenlänge in der Programmvariable für eine bestimmte Spalte ändern, wenn Sie Daten mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bcp_sendrow [nach](bcp-sendrow.md)kopieren.</span><span class="sxs-lookup"><span data-stu-id="49c50-120">The **bcp_collen** function allows you to change the data length in the program variable for a particular column when copying data to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
 <span data-ttu-id="49c50-121">Anfänglich wird die Datenlänge beim Aufrufen von [bcp_bind](bcp-bind.md) bestimmt.</span><span class="sxs-lookup"><span data-stu-id="49c50-121">Initially, the data length is determined when [bcp_bind](bcp-bind.md) is called.</span></span> <span data-ttu-id="49c50-122">Wenn sich die Datenlänge zwischen den Aufrufen von **bcp_sendrow** ändert und kein Längenpräfix oder -abschlusszeichen verwendet wird, können Sie **bcp_collen** aufrufen, um die Länge zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="49c50-122">If the data length changes between calls to **bcp_sendrow** and no length prefix or terminator is being used, you can call **bcp_collen** to reset the length.</span></span> <span data-ttu-id="49c50-123">Mit dem nächsten Aufruf von **bcp_sendrow** wird der Längensatz vom Aufruf von **bcp_collen**verwendet.</span><span class="sxs-lookup"><span data-stu-id="49c50-123">The next call to **bcp_sendrow** uses the length set by the call to **bcp_collen**.</span></span>  
  
 <span data-ttu-id="49c50-124">Für jede Spalte in der Tabelle, deren Datenlänge Sie ändern möchten, muss **bcp_collen** einmal aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="49c50-124">You must call **bcp_collen** once for each column in the table whose data length you want to modify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49c50-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="49c50-125">See Also</span></span>  
 [<span data-ttu-id="49c50-126">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="49c50-126">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
