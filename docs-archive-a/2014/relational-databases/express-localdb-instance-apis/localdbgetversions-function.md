---
title: Localdbgetversions-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBGetVersions
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 033a9c6b-0d7f-4f8a-ab60-33cd6fee0d33
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 37d2a927346252f1b126f5e3a4ec78ea03cde0a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724737"
---
# <a name="localdbgetversions-function"></a><span data-ttu-id="db09b-102">LocalDBGetVersions-Funktion</span><span class="sxs-lookup"><span data-stu-id="db09b-102">LocalDBGetVersions Function</span></span>
  <span data-ttu-id="db09b-103">Gibt alle auf dem Computer verfügbaren SQL Server Express LocalDB-Versionen zurück.</span><span class="sxs-lookup"><span data-stu-id="db09b-103">Returns all SQL Server Express LocalDB versions available on the computer.</span></span>  
  
 <span data-ttu-id="db09b-104">**Headerdatei:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="db09b-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db09b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="db09b-105">Syntax</span></span>  
  
```  
#define MAX_LOCALDB_VERSION_LENGTH 43typedef WCHAR TLocalDBVersion[MAX_LOCALDB_VERSION_LENGTH + 1];typedef TLocalDBVersion* PTLocalDBVersion;HRESULT LocalDBGetVersions(           PTLocalDBVersion pVersion,           LPDWORD lpdwNumberOfVersions);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db09b-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="db09b-106">Parameters</span></span>  
 <span data-ttu-id="db09b-107">*pVersionNames*</span><span class="sxs-lookup"><span data-stu-id="db09b-107">*pVersionNames*</span></span>  
 <span data-ttu-id="db09b-108">Ausgeben Enthält die Namen der localdb-Versionen, die auf der Arbeitsstation des Benutzers verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="db09b-108">[Output] Contains names of the LocalDB versions that are available on the user's workstation.</span></span>  
  
 <span data-ttu-id="db09b-109">*lpdwnumofversions*</span><span class="sxs-lookup"><span data-stu-id="db09b-109">*lpdwNumberOfVersions*</span></span>  
 <span data-ttu-id="db09b-110">[Eingabe/Ausgabe] Enthält bei Eingabe die Anzahl der Slots für Versionen im *pVersionNames* -Puffer.</span><span class="sxs-lookup"><span data-stu-id="db09b-110">[Input/Output] On input holds the number of slots for versions in the *pVersionNames* buffer.</span></span>   
<span data-ttu-id="db09b-111">Enthält bei Ausgabe die Anzahl der vorhandenen LocalDB-Versionen.</span><span class="sxs-lookup"><span data-stu-id="db09b-111">On output, holds the number of existing LocalDB versions.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="db09b-112">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="db09b-112">Returns</span></span>  
 <span data-ttu-id="db09b-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="db09b-113">S_OK</span></span>  
 <span data-ttu-id="db09b-114">Die Funktion wurde erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="db09b-114">The function succeeded.</span></span>  
  
 [<span data-ttu-id="db09b-115">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="db09b-115">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="db09b-116">SQL Server Express LocalDB ist nicht auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="db09b-116">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="db09b-117">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="db09b-117">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="db09b-118">Mindestens ein angegebener Eingabeparameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="db09b-118">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="db09b-119">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="db09b-119">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>](../express-localdb-error-messages/localdb-error-insufficient-buffer.md)  
 <span data-ttu-id="db09b-120">Der Eingabepuffer ist zu kurz. Abschneiden wurde nicht angefordert.</span><span class="sxs-lookup"><span data-stu-id="db09b-120">The input buffer is too short, and truncation was not requested.</span></span>  
  
 [<span data-ttu-id="db09b-121">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="db09b-121">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="db09b-122">Ein unerwarteter Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="db09b-122">An unexpected error occurred.</span></span> <span data-ttu-id="db09b-123">Weitere Informationen finden Sie im Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="db09b-123">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db09b-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="db09b-124">Remarks</span></span>  
 <span data-ttu-id="db09b-125">Ein Codebeispiel, in dem die LocalDB-API verwendet wird, finden Sie unter [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="db09b-125">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db09b-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="db09b-126">See Also</span></span>  
 [<span data-ttu-id="db09b-127">SQL Server Express LocalDB-Header und Versionsinformationen</span><span class="sxs-lookup"><span data-stu-id="db09b-127">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
