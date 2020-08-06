---
title: Localdbshareingestance-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBShareInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 21eb3b9a-7d32-455b-89bb-f624198cd202
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 238bff0b3512ceb03ead186dc001165274bd4e30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617000"
---
# <a name="localdbshareinstance-function"></a><span data-ttu-id="f15af-102">LocalDBShareInstance-Funktion</span><span class="sxs-lookup"><span data-stu-id="f15af-102">LocalDBShareInstance Function</span></span>
  <span data-ttu-id="f15af-103">Gibt die angegebene SQL Server Express-LocalDB-Instanz für andere Benutzer des Computers frei und verwendet den angegebenen Freigabenamen.</span><span class="sxs-lookup"><span data-stu-id="f15af-103">Shares the specified SQL Server Express LocalDB instance with other users of the computer, using the specified shared name.</span></span>  
  
 <span data-ttu-id="f15af-104">**Headerdatei:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="f15af-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f15af-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f15af-105">Syntax</span></span>  
  
```  
HRESULT LocalDBShareInstance(  
           PSID pOwnerSID,  
           PCWSTR pInstancePrivateName,  
           PCWSTR pInstanceSharedName,   
           DWORD dwFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f15af-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f15af-106">Parameters</span></span>  
 <span data-ttu-id="f15af-107">*pownersid*</span><span class="sxs-lookup"><span data-stu-id="f15af-107">*pOwnerSID*</span></span>  
 <span data-ttu-id="f15af-108">[Eingabe] Die SID des Instanzeigentümers.</span><span class="sxs-lookup"><span data-stu-id="f15af-108">[Input] The SID of the instance owner.</span></span>  
  
 <span data-ttu-id="f15af-109">*pinstanceprivatename*</span><span class="sxs-lookup"><span data-stu-id="f15af-109">*pInstancePrivateName*</span></span>  
 <span data-ttu-id="f15af-110">[Eingabe] Der private Name für die freizugebende LocalDB-Instanz.</span><span class="sxs-lookup"><span data-stu-id="f15af-110">[Input] The private name for the LocalDB instance to share.</span></span>  
  
 <span data-ttu-id="f15af-111">*pinstancesharedname*</span><span class="sxs-lookup"><span data-stu-id="f15af-111">*pInstanceSharedName*</span></span>  
 <span data-ttu-id="f15af-112">[Eingabe] Der Freigabename für die freizugebende LocalDB-Instanz.</span><span class="sxs-lookup"><span data-stu-id="f15af-112">[Input] The shared name for the LocalDB instance to share.</span></span>  
  
 <span data-ttu-id="f15af-113">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="f15af-113">*dwFlags*</span></span>  
 <span data-ttu-id="f15af-114">[Eingabe] Zur künftigen Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="f15af-114">[Input] Reserved for future use.</span></span> <span data-ttu-id="f15af-115">Muss derzeit auf 0 festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="f15af-115">Currently should be set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="f15af-116">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="f15af-116">Returns</span></span>  
 <span data-ttu-id="f15af-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="f15af-117">S_OK</span></span>  
 <span data-ttu-id="f15af-118">Die Funktion wurde erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f15af-118">The function succeeded.</span></span>  
  
 [<span data-ttu-id="f15af-119">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="f15af-119">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="f15af-120">SQL Server Express LocalDB ist nicht auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="f15af-120">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="f15af-121">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="f15af-121">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="f15af-122">Mindestens ein angegebener Eingabeparameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="f15af-122">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="f15af-123">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="f15af-123">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="f15af-124">Der angegebene Instanzname ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="f15af-124">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="f15af-125">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="f15af-125">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="f15af-126">Die angegebene Instanz ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="f15af-126">The specified instance does not exist.</span></span>  
  
 [<span data-ttu-id="f15af-127">LOCALDB_ERROR_ADMIN_RIGHTS_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="f15af-127">LOCALDB_ERROR_ADMIN_RIGHTS_REQUIRED</span></span>](../express-localdb-error-messages/localdb-error-admin-rights-required.md)  
 <span data-ttu-id="f15af-128">Administratorberechtigungen sind erforderlich, um diesen Vorgang auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f15af-128">Administrator privileges are required in order to execute this operation.</span></span>  
  
 [<span data-ttu-id="f15af-129">LOCALDB_ERROR_SHARED_NAME_TAKEN</span><span class="sxs-lookup"><span data-stu-id="f15af-129">LOCALDB_ERROR_SHARED_NAME_TAKEN</span></span>](../express-localdb-error-messages/localdb-error-shared-name-taken.md)  
 <span data-ttu-id="f15af-130">Der angegebene freigegebene Name wird bereits verwendet.</span><span class="sxs-lookup"><span data-stu-id="f15af-130">The specified shared name is already taken.</span></span>  
  
 [<span data-ttu-id="f15af-131">LOCALDB_ERROR_INSTANCE_ALREADY_SHARED</span><span class="sxs-lookup"><span data-stu-id="f15af-131">LOCALDB_ERROR_INSTANCE_ALREADY_SHARED</span></span>](../express-localdb-error-messages/localdb-error-instance-already-shared.md)  
 <span data-ttu-id="f15af-132">Die angegebene Instanz ist bereits freigegeben.</span><span class="sxs-lookup"><span data-stu-id="f15af-132">The specified instance is already shared.</span></span>  
  
 [<span data-ttu-id="f15af-133">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="f15af-133">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="f15af-134">Ein unerwarteter Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f15af-134">An unexpected error occurred.</span></span> <span data-ttu-id="f15af-135">Weitere Informationen finden Sie im Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="f15af-135">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f15af-136">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f15af-136">Remarks</span></span>  
 <span data-ttu-id="f15af-137">Ein Codebeispiel, in dem die LocalDB-API verwendet wird, finden Sie unter [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="f15af-137">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f15af-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f15af-138">See Also</span></span>  
 [<span data-ttu-id="f15af-139">SQL Server Express LocalDB-Header und Versionsinformationen</span><span class="sxs-lookup"><span data-stu-id="f15af-139">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
