---
title: Localdbstoptracing-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBStopTracing
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 1d50e040-8602-4ffa-be8f-b8633fdfa7ff
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 2bf6051fe8c86728c2ebf0a0b2bc34fabb98edb9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609227"
---
# <a name="localdbstoptracing-function"></a><span data-ttu-id="23fc4-102">LocalDBStopTracing-Funktion</span><span class="sxs-lookup"><span data-stu-id="23fc4-102">LocalDBStopTracing Function</span></span>
  <span data-ttu-id="23fc4-103">Deaktiviert die Ablaufverfolgung der API-Aufrufe für alle SQL Server Express LocalDB-Instanzen, die zum aktuellen Windows-Benutzer gehören.</span><span class="sxs-lookup"><span data-stu-id="23fc4-103">Disables tracing of API calls for all the SQL Server Express LocalDB instances owned by the current Windows user.</span></span>  
  
 <span data-ttu-id="23fc4-104">**Headerdatei:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="23fc4-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23fc4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="23fc4-105">Syntax</span></span>  
  
```  
HRESULT LocalDBStopTracing();  
```  
  
## <a name="returns"></a><span data-ttu-id="23fc4-106">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="23fc4-106">Returns</span></span>  
 <span data-ttu-id="23fc4-107">S_OK</span><span class="sxs-lookup"><span data-stu-id="23fc4-107">S_OK</span></span>  
 <span data-ttu-id="23fc4-108">Die Funktion wurde erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="23fc4-108">The function succeeded.</span></span>  
  
 [<span data-ttu-id="23fc4-109">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="23fc4-109">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="23fc4-110">Ein unerwarteter Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="23fc4-110">An unexpected error occurred.</span></span> <span data-ttu-id="23fc4-111">Weitere Informationen finden Sie im Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="23fc4-111">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23fc4-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="23fc4-112">Remarks</span></span>  
 <span data-ttu-id="23fc4-113">Ein Codebeispiel, in dem die LocalDB-API verwendet wird, finden Sie unter [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="23fc4-113">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23fc4-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="23fc4-114">See Also</span></span>  
 [<span data-ttu-id="23fc4-115">SQL Server Express LocalDB-Header und Versionsinformationen</span><span class="sxs-lookup"><span data-stu-id="23fc4-115">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
