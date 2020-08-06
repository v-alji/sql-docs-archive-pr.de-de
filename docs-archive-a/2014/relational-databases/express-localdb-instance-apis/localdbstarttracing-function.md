---
title: Localdbstarttracing-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBStartTracing
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: c7b83833-6d2a-4a06-9cb7-42767bed52c6
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 1b10482e9839d43e29da72dbe2c194a01d8248eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726946"
---
# <a name="localdbstarttracing-function"></a><span data-ttu-id="fe762-102">LocalDBStartTracing-Funktion</span><span class="sxs-lookup"><span data-stu-id="fe762-102">LocalDBStartTracing Function</span></span>
  <span data-ttu-id="fe762-103">Aktiviert die Ablaufverfolgung der API-Aufrufe für alle SQL Server Express LocalDB-Instanzen, die zum aktuellen Windows-Benutzer gehören.</span><span class="sxs-lookup"><span data-stu-id="fe762-103">Enables tracing of API calls for all the SQL Server Express LocalDB instances owned by the current Windows user.</span></span>  
  
 <span data-ttu-id="fe762-104">**Headerdatei:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="fe762-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe762-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe762-105">Syntax</span></span>  
  
```  
HRESULT LocalDBStartTracing();  
```  
  
## <a name="returns"></a><span data-ttu-id="fe762-106">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="fe762-106">Returns</span></span>  
 <span data-ttu-id="fe762-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="fe762-107">S_OK</span></span>  
 <span data-ttu-id="fe762-108">Die Funktion wurde erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fe762-108">The function succeeded.</span></span>  
  
 [<span data-ttu-id="fe762-109">LOCALDB_ERROR_XEVENT_FAILED</span><span class="sxs-lookup"><span data-stu-id="fe762-109">LOCALDB_ERROR_XEVENT_FAILED</span></span>](../express-localdb-error-messages/localdb-error-xevent-failed.md)  
 <span data-ttu-id="fe762-110">Fehler beim Starten der XEvent-Engine innerhalb der LocalDB-Instanz-API.</span><span class="sxs-lookup"><span data-stu-id="fe762-110">Failed to start XEvent engine within the LocalDB Instance API.</span></span>  
  
 [<span data-ttu-id="fe762-111">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="fe762-111">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="fe762-112">Ein unerwarteter Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="fe762-112">An unexpected error occurred.</span></span> <span data-ttu-id="fe762-113">Weitere Informationen finden Sie im Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="fe762-113">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe762-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fe762-114">Remarks</span></span>  
 <span data-ttu-id="fe762-115">Ein Codebeispiel, in dem die LocalDB-API verwendet wird, finden Sie unter [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="fe762-115">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe762-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fe762-116">See Also</span></span>  
 [<span data-ttu-id="fe762-117">SQL Server Express LocalDB-Header und Versionsinformationen</span><span class="sxs-lookup"><span data-stu-id="fe762-117">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
