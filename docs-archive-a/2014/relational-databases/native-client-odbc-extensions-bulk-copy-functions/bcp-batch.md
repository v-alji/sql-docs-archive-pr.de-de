---
title: bcp_batch | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_batch
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_batch function
ms.assetid: 0bda489e-86bc-4a7e-80f6-96047e03f281
author: rothja
ms.author: jroth
ms.openlocfilehash: 24cdf6e2934c2b80a55d8fa1fcc572a976b636ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617937"
---
# <a name="bcp_batch"></a><span data-ttu-id="084d0-102">bcp_batch</span><span class="sxs-lookup"><span data-stu-id="084d0-102">bcp_batch</span></span>
  <span data-ttu-id="084d0-103">Führt einen Commit für alle zuvor aus Programmvariablen massenkopierten Zeilen aus, die von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bcp_sendrow [an](bcp-sendrow.md)gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="084d0-103">Commits all rows previously bulk copied from program variables and sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="084d0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="084d0-104">Syntax</span></span>  
  
```  
  
DBINT bcp_batch (HDBC  
hdbc  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="084d0-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="084d0-105">Arguments</span></span>  
 <span data-ttu-id="084d0-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="084d0-106">*hdbc*</span></span>  
 <span data-ttu-id="084d0-107">Das für den Massenkopiervorgang aktivierte ODBC-Verbindungshandle.</span><span class="sxs-lookup"><span data-stu-id="084d0-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="084d0-108">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="084d0-108">Returns</span></span>  
 <span data-ttu-id="084d0-109">Die Anzahl von Zeilen, die nach dem letzten Aufruf von **bcp_batch**gespeichert wurden, oder -1 im Fall eines Fehlers.</span><span class="sxs-lookup"><span data-stu-id="084d0-109">The number of rows saved after the last call to **bcp_batch**, or -1 in case of error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="084d0-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="084d0-110">Remarks</span></span>  
 <span data-ttu-id="084d0-111">Batches von Massenkopiervorgängen stellen Transaktionen dar.</span><span class="sxs-lookup"><span data-stu-id="084d0-111">Bulk copy batches define transactions.</span></span> <span data-ttu-id="084d0-112">Wenn eine Anwendung mit [bcp_bind](bcp-bind.md) und **bcp_sendrow** Zeilen von Programmvariablen in SQL-Server-Tabellen massenkopiert, wird für die Zeilen nur dann ein Commit durchgeführt, wenn das Programm **bcp_batch** oder [bcp_done](bcp-done.md)aufruft.</span><span class="sxs-lookup"><span data-stu-id="084d0-112">When an application uses [bcp_bind](bcp-bind.md) and **bcp_sendrow** to bulk copy rows from program variables to SQL Server tables, the rows are committed only when the program calls **bcp_batch** or [bcp_done](bcp-done.md).</span></span>  
  
 <span data-ttu-id="084d0-113">Sie können **bcp_batch** einmal für jede *n* Zeilen aufrufen oder dann, wenn bei den eingehenden Daten eine Pause auftritt (wie in einer Telemetrieanwendung).</span><span class="sxs-lookup"><span data-stu-id="084d0-113">You can call **bcp_batch** once every *n* rows or when there is a lull in incoming data (as in a telemetry application).</span></span> <span data-ttu-id="084d0-114">Wenn eine Anwendung **bcp_batch** nicht aufruft, wird nur dann ein Commit für die massenkopierten Zeilen ausgeführt, wenn **bcp_done** aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="084d0-114">If an application does not call **bcp_batch** the bulk copied rows are committed only when **bcp_done** is called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="084d0-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="084d0-115">See Also</span></span>  
 [<span data-ttu-id="084d0-116">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="084d0-116">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
