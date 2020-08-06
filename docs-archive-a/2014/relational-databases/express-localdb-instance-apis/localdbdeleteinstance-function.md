---
title: Localdbdelta eteinstance-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBDeleteInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 37cb2a7e-672a-4223-b6f3-a94d7b8d58cd
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8d4c873e045c5effed476ca9d147270d159ec3b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620404"
---
# <a name="localdbdeleteinstance-function"></a><span data-ttu-id="0573a-102">LocalDBDeleteInstance-Funktion</span><span class="sxs-lookup"><span data-stu-id="0573a-102">LocalDBDeleteInstance Function</span></span>
  <span data-ttu-id="0573a-103">Entfernt die angegebene SQL Server Express LocalDB-Instanz.</span><span class="sxs-lookup"><span data-stu-id="0573a-103">Removes the specified SQL Server Express LocalDB instance.</span></span>  
  
 <span data-ttu-id="0573a-104">**Headerdatei:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="0573a-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0573a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0573a-105">Syntax</span></span>  
  
```  
HRESULT LocalDBDeleteInstance(  
           PCWSTR pInstanceName,  
           DWORD dwFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0573a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0573a-106">Parameters</span></span>  
 <span data-ttu-id="0573a-107">*pinstancename*</span><span class="sxs-lookup"><span data-stu-id="0573a-107">*pInstanceName*</span></span>  
 <span data-ttu-id="0573a-108">[Eingabe] Der Name der LocalDB-Instanz, die entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0573a-108">[Input] The name of the LocalDB instance to remove.</span></span>  
  
 <span data-ttu-id="0573a-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="0573a-109">*dwFlags*</span></span>  
 <span data-ttu-id="0573a-110">[Eingabe] Zur künftigen Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="0573a-110">[Input] Reserved for future use.</span></span> <span data-ttu-id="0573a-111">Muss derzeit auf 0 festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="0573a-111">Currently should be set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="0573a-112">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="0573a-112">Returns</span></span>  
 <span data-ttu-id="0573a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="0573a-113">S_OK</span></span>  
 <span data-ttu-id="0573a-114">Die Funktion wurde erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0573a-114">The function succeeded.</span></span>  
  
 [<span data-ttu-id="0573a-115">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="0573a-115">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="0573a-116">SQL Server Express LocalDB ist nicht auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="0573a-116">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="0573a-117">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="0573a-117">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="0573a-118">Mindestens ein angegebener Eingabeparameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="0573a-118">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="0573a-119">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="0573a-119">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="0573a-120">Der angegebene Instanzname ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="0573a-120">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="0573a-121">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="0573a-121">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="0573a-122">Die angegebene Instanz ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="0573a-122">The specified instance does not exist.</span></span>  
  
 [<span data-ttu-id="0573a-123">LOCALDB_ERROR_INSTANCE_BUSY</span><span class="sxs-lookup"><span data-stu-id="0573a-123">LOCALDB_ERROR_INSTANCE_BUSY</span></span>](../express-localdb-error-messages/localdb-error-instance-busy.md)  
 <span data-ttu-id="0573a-124">Die angegebene Instanz wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0573a-124">The specified instance is running.</span></span>  
  
 [<span data-ttu-id="0573a-125">LOCALDB_ERROR_WAIT_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0573a-125">LOCALDB_ERROR_WAIT_TIMEOUT</span></span>](../express-localdb-error-messages/localdb-error-wait-timeout.md)  
 <span data-ttu-id="0573a-126">Beim versuchten Abrufen der Synchronisierungssperren ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0573a-126">A time-out occurred while trying to acquire synchronization locks.</span></span>  
  
 [<span data-ttu-id="0573a-127">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="0573a-127">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="0573a-128">Der Pfad, unter dem die Instanz gespeichert werden soll, ist länger als MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="0573a-128">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="0573a-129">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="0573a-129">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-get-user-profile-folder.md)  
 <span data-ttu-id="0573a-130">Ein Benutzerprofilordner kann nicht abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0573a-130">A user profile folder cannot be retrieved.</span></span>  
  
 [<span data-ttu-id="0573a-131">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="0573a-131">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="0573a-132">Auf einen Instanzordner kann nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="0573a-132">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="0573a-133">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="0573a-133">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="0573a-134">Auf eine Instanzregistrierung kann nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="0573a-134">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="0573a-135">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="0573a-135">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-modify-instance-registry.md)  
 <span data-ttu-id="0573a-136">Eine Instanzregistrierung kann nicht bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="0573a-136">An instance registry cannot be modified.</span></span>  
  
 [<span data-ttu-id="0573a-137">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="0573a-137">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="0573a-138">Eine Instanzkonfiguration ist beschädigt.</span><span class="sxs-lookup"><span data-stu-id="0573a-138">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="0573a-139">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0573a-139">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span></span>](../express-localdb-error-messages/localdb-error-caller-is-not-owner.md)  
 <span data-ttu-id="0573a-140">API-Aufrufer ist kein Eigentümer der lokalen Datenbankinstanz.</span><span class="sxs-lookup"><span data-stu-id="0573a-140">API caller is not Local Database instance owner.</span></span>  
  
 [<span data-ttu-id="0573a-141">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="0573a-141">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="0573a-142">Ein unerwarteter Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0573a-142">An unexpected error occurred.</span></span> <span data-ttu-id="0573a-143">Weitere Informationen finden Sie im Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="0573a-143">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0573a-144">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0573a-144">Remarks</span></span>  
 <span data-ttu-id="0573a-145">Ein Codebeispiel, in dem die LocalDB-API verwendet wird, finden Sie unter [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="0573a-145">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0573a-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0573a-146">See Also</span></span>  
 [<span data-ttu-id="0573a-147">SQL Server Express LocalDB-Header und Versionsinformationen</span><span class="sxs-lookup"><span data-stu-id="0573a-147">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
