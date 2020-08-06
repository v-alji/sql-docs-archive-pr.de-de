---
title: bcp_columns | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_columns
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_columns function
ms.assetid: 5376f6fe-9508-439a-8c66-778d77f19ac3
author: rothja
ms.author: jroth
ms.openlocfilehash: 028bb80e88a29b366e3a489abae06c8b3b30cdf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698157"
---
# <a name="bcp_columns"></a><span data-ttu-id="cc35a-102">bcp_columns</span><span class="sxs-lookup"><span data-stu-id="cc35a-102">bcp_columns</span></span>
  <span data-ttu-id="cc35a-103">Legt die Gesamtanzahl der Spalten fest, die in der Benutzerdatei gefunden wurden und mit einem Massenkopiervorgang in oder aus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cc35a-103">Sets the total number of columns found in the user file for use with a bulk copy into or out of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cc35a-104">[bcp_setbulkmode](bcp-setbulkmode.md) können anstelle von bcp_columns und [bcp_colfmt](bcp-colfmt.md)verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cc35a-104">[bcp_setbulkmode](bcp-setbulkmode.md) can be used instead of bcp_columns and [bcp_colfmt](bcp-colfmt.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc35a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cc35a-105">Syntax</span></span>  
  
```  
  
RETCODE bcp_columns (  
HDBC   
hdbc  
,  
INT   
nColumns  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="cc35a-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="cc35a-106">Arguments</span></span>  
 <span data-ttu-id="cc35a-107">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="cc35a-107">*hdbc*</span></span>  
 <span data-ttu-id="cc35a-108">Das für den Massenkopiervorgang aktivierte ODBC-Verbindungshandle.</span><span class="sxs-lookup"><span data-stu-id="cc35a-108">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="cc35a-109">*nColumns*</span><span class="sxs-lookup"><span data-stu-id="cc35a-109">*nColumns*</span></span>  
 <span data-ttu-id="cc35a-110">Die Gesamtzahl der Spalten in der Benutzerdatei.</span><span class="sxs-lookup"><span data-stu-id="cc35a-110">Is the total number of columns in the user file.</span></span> <span data-ttu-id="cc35a-111">Auch wenn Sie das Massen Kopieren von Daten aus der Benutzerdatei in eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Tabelle vorbereiten und nicht alle Spalten in der Benutzerdatei kopieren möchten, müssen Sie *nColumns* trotzdem auf die Gesamtzahl der Benutzerdatei Spalten festlegen.</span><span class="sxs-lookup"><span data-stu-id="cc35a-111">Even if you are preparing to bulk copy data from the user file to an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table and do not intend to copy all columns in the user file, you must still set *nColumns* to the total number of user-file columns.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="cc35a-112">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="cc35a-112">Returns</span></span>  
 <span data-ttu-id="cc35a-113">SUCCEED oder FAIL.</span><span class="sxs-lookup"><span data-stu-id="cc35a-113">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc35a-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="cc35a-114">Remarks</span></span>  
 <span data-ttu-id="cc35a-115">Diese Funktion kann erst aufgerufen werden, nachdem [bcp_init](bcp-init.md) mit einem gültigen Dateinamen aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="cc35a-115">This function can be called only after [bcp_init](bcp-init.md) has been called with a valid file name.</span></span>  
  
 <span data-ttu-id="cc35a-116">Sie sollten diese Funktion nur aufrufen, wenn Sie ein Benutzerdateiformat verwenden möchten, das sich vom Standardformat unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="cc35a-116">You should call this function only if you intend to use a user-file format that differs from the default.</span></span> <span data-ttu-id="cc35a-117">Weitere Informationen zu einer Beschreibung des standardmäßigen Benutzerdatei Formats finden Sie unter **bcp_init**.</span><span class="sxs-lookup"><span data-stu-id="cc35a-117">For more information about a description of the default user-file format, see **bcp_init**.</span></span>  
  
 <span data-ttu-id="cc35a-118">Nach `bcp_columns` dem Aufrufen von müssen Sie für jede Spalte in der Benutzerdatei [bcp_colfmt](bcp-colfmt.md)aufrufen, um ein benutzerdefiniertes Dateiformat vollständig zu definieren.</span><span class="sxs-lookup"><span data-stu-id="cc35a-118">After calling `bcp_columns`, you must call [bcp_colfmt](bcp-colfmt.md)for each column in the user file to completely define a custom file format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc35a-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cc35a-119">See Also</span></span>  
 [<span data-ttu-id="cc35a-120">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="cc35a-120">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
