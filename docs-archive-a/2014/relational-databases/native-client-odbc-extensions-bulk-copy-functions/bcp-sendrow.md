---
title: bcp_sendrow | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_sendrow
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_sendrow function
ms.assetid: ddbdb4bd-ad4e-4bf1-9a75-656aa26ce10a
author: rothja
ms.author: jroth
ms.openlocfilehash: 3d2f55486ba57101ffc7b1903de5d19ac8eaaca2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616046"
---
# <a name="bcp_sendrow"></a><span data-ttu-id="46e53-102">'bcp_sendrow'</span><span class="sxs-lookup"><span data-stu-id="46e53-102">bcp_sendrow</span></span>
  <span data-ttu-id="46e53-103">Sendet eine Datenzeile aus Programmvariablen an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46e53-103">Sends a row of data from program variables to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46e53-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="46e53-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_sendrow (  
    HDBC   
hdbc  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="46e53-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="46e53-105">Arguments</span></span>  
 <span data-ttu-id="46e53-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="46e53-106">*hdbc*</span></span>  
 <span data-ttu-id="46e53-107">Das für den Massenkopiervorgang aktivierte ODBC-Verbindungshandle.</span><span class="sxs-lookup"><span data-stu-id="46e53-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="46e53-108">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="46e53-108">Returns</span></span>  
 <span data-ttu-id="46e53-109">SUCCEED oder FAIL.</span><span class="sxs-lookup"><span data-stu-id="46e53-109">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46e53-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="46e53-110">Remarks</span></span>  
 <span data-ttu-id="46e53-111">Die **bcp_sendrow** -Funktion erstellt eine Zeile aus Programmvariablen und sendet sie an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46e53-111">The **bcp_sendrow** function builds a row from program variables and sends it to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="46e53-112">Vor dem Aufruf von **bcp_sendrow**müssen Sie Aufrufe an [bcp_bind](bcp-bind.md) vornehmen, um die Programmvariablen mit den Zeilendaten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="46e53-112">Before calling **bcp_sendrow**, you must make calls to [bcp_bind](bcp-bind.md) to specify the program variables containing row data.</span></span>  
  
 <span data-ttu-id="46e53-113">Wird **bcp_bind** unter Angabe eines langen Datentyps variabler Länge wie einem *eDataType* -Parameter von SQLTEXT und einem *pData* -Parameter ungleich NULL aufgerufen, sendet **bcp_sendrow** wie bei jedem anderen Datentyp den gesamten Datenwert.</span><span class="sxs-lookup"><span data-stu-id="46e53-113">If **bcp_bind** is called specifying a long, variable-length data type, for example, an *eDataType* parameter of SQLTEXT and a nonNULL *pData* parameter, **bcp_sendrow** sends the entiredata value, just as it does for any other data type.</span></span> <span data-ttu-id="46e53-114">Hat dagegen **bcp_bind** einen *pData* -Parameter mit NULL-Wert, gibt **bcp_sendrow** die Steuerung an die Anwendung zurück, sobald alle angegebenen Datenspalten an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="46e53-114">If, however, **bcp_bind** has a NULL *pData* parameter, **bcp_sendrow** returns control to the application immediately after all columns with data specified are sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="46e53-115">Die Anwendung kann dann wiederholt [bcp_moretext](bcp-moretext.md) aufrufen, um die langen Daten variabler Länge Segment für Segment an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]zu senden.</span><span class="sxs-lookup"><span data-stu-id="46e53-115">The application can then call [bcp_moretext](bcp-moretext.md) repeatedly to send the long, variable-length data to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a chunk at a time.</span></span> <span data-ttu-id="46e53-116">Weitere Informationen finden Sie unter [bcp_moretext](bcp-moretext.md).</span><span class="sxs-lookup"><span data-stu-id="46e53-116">For more information, see [bcp_moretext](bcp-moretext.md).</span></span>  
  
 <span data-ttu-id="46e53-117">Wenn mit **bcp_sendrow** Zeilen aus Programmvariablen in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Tabellen massenkopiert werden, wird für die Zeilen erst dann ein Commit durchgeführt, wenn der Benutzer [bcp_batch](bcp-batch.md) oder [bcp_done](bcp-done.md)aufruft.</span><span class="sxs-lookup"><span data-stu-id="46e53-117">When **bcp_sendrow** is used to bulk copy rows from program variables into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables, rows are committed only when the user calls [bcp_batch](bcp-batch.md) or [bcp_done](bcp-done.md).</span></span> <span data-ttu-id="46e53-118">Der Benutzer kann **bcp_batch** wahlweise einmal für alle *n* Zeilen aufrufen oder dann, wenn bei den eingehenden Daten eine Pause auftritt.</span><span class="sxs-lookup"><span data-stu-id="46e53-118">The user can choose to call **bcp_batch** once every *n* rows or when there is a lull between periods of incoming data.</span></span> <span data-ttu-id="46e53-119">Wird **bcp_batch** nie aufgerufen, wird ein Commit für die Zeilen ausgeführt, wenn **bcp_done** aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="46e53-119">If **bcp_batch** is never called, the rows are committed when **bcp_done** is called.</span></span>  
  
 <span data-ttu-id="46e53-120">Informationen zu einem Breaking Change beim Massen kopieren ab finden Sie unter [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] [Durchführen von Massen Kopier Vorgängen &#40;ODBC-&#41;](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="46e53-120">For information about a breaking change in bulk-copying beginning in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], see [Performing Bulk Copy Operations &#40;ODBC&#41;](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46e53-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46e53-121">See Also</span></span>  
 [<span data-ttu-id="46e53-122">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="46e53-122">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
