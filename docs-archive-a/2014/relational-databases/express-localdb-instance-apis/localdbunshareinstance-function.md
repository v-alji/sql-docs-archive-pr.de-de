---
title: Localdbunshareinstance-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBUnshareInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 54012ccb-eded-43f7-8ea5-da5ce79224c6
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 77ebf8cad9d410b047fccede4360ca0041637986
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609228"
---
# <a name="localdbunshareinstance-function"></a><span data-ttu-id="91fa5-102">LocalDBUnshareInstance-Funktion</span><span class="sxs-lookup"><span data-stu-id="91fa5-102">LocalDBUnshareInstance Function</span></span>
  <span data-ttu-id="91fa5-103">Beendet die Freigabe der angegebenen SQL Server Express LocalDB-Instanz.</span><span class="sxs-lookup"><span data-stu-id="91fa5-103">Stops the sharing of the specified SQL Server Express LocalDB instance.</span></span>  
  
 <span data-ttu-id="91fa5-104">**Headerdatei:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="91fa5-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91fa5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="91fa5-105">Syntax</span></span>  
  
```  
HRESULT LocalDBUnShareInstance(  
           PCWSTR pInstanceSharedName,   
           DWORD dwFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91fa5-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="91fa5-106">Parameters</span></span>  
 <span data-ttu-id="91fa5-107">*pinstancesharedname*</span><span class="sxs-lookup"><span data-stu-id="91fa5-107">*pInstanceSharedName*</span></span>  
 <span data-ttu-id="91fa5-108">[Eingabe] Der Freigabename für die LocalDB-Instanz, deren Freigabe aufgehoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="91fa5-108">[Input] The shared name for the LocalDB instance to unshare.</span></span>  
  
 <span data-ttu-id="91fa5-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="91fa5-109">*dwFlags*</span></span>  
 <span data-ttu-id="91fa5-110">[Eingabe] Zur künftigen Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="91fa5-110">[Input] Reserved for future use.</span></span> <span data-ttu-id="91fa5-111">Muss derzeit auf 0 festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="91fa5-111">Currently should be set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="91fa5-112">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="91fa5-112">Returns</span></span>  
 <span data-ttu-id="91fa5-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="91fa5-113">S_OK</span></span>  
 <span data-ttu-id="91fa5-114">Die Funktion wurde erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="91fa5-114">The function succeeded.</span></span>  
  
 [<span data-ttu-id="91fa5-115">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="91fa5-115">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="91fa5-116">SQL Server Express LocalDB ist nicht auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="91fa5-116">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="91fa5-117">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="91fa5-117">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="91fa5-118">Mindestens ein angegebener Eingabeparameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="91fa5-118">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="91fa5-119">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="91fa5-119">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="91fa5-120">Der angegebene Instanzname ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="91fa5-120">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="91fa5-121">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="91fa5-121">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="91fa5-122">Die angegebene Instanz ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="91fa5-122">The specified instance does not exist.</span></span>  
  
 [<span data-ttu-id="91fa5-123">LOCALDB_ERROR_ADMIN_RIGHTS_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="91fa5-123">LOCALDB_ERROR_ADMIN_RIGHTS_REQUIRED</span></span>](../express-localdb-error-messages/localdb-error-admin-rights-required.md)  
 <span data-ttu-id="91fa5-124">Administratorberechtigungen sind erforderlich, um diesen Vorgang auszuführen.</span><span class="sxs-lookup"><span data-stu-id="91fa5-124">Administrator privileges are required in order to execute this operation.</span></span>  
  
 [<span data-ttu-id="91fa5-125">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="91fa5-125">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="91fa5-126">Ein unerwarteter Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="91fa5-126">An unexpected error occurred.</span></span> <span data-ttu-id="91fa5-127">Weitere Informationen finden Sie im Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="91fa5-127">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91fa5-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="91fa5-128">Remarks</span></span>  
 <span data-ttu-id="91fa5-129">Ein Codebeispiel, in dem die LocalDB-API verwendet wird, finden Sie unter [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="91fa5-129">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91fa5-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="91fa5-130">See Also</span></span>  
 [<span data-ttu-id="91fa5-131">SQL Server Express LocalDB-Header und Versionsinformationen</span><span class="sxs-lookup"><span data-stu-id="91fa5-131">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
