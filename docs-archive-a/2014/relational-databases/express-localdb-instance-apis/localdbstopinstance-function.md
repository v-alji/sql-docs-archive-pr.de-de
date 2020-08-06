---
title: Localdbstopinstance-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBStopInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 4bd73187-0aac-4f03-ac54-2b78e41917e5
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 48b014e65e0a02a5f866e5301b12dae3cd255b95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695614"
---
# <a name="localdbstopinstance-function"></a><span data-ttu-id="8ca8c-102">LocalDBStopInstance-Funktion</span><span class="sxs-lookup"><span data-stu-id="8ca8c-102">LocalDBStopInstance Function</span></span>
  <span data-ttu-id="8ca8c-103">Beendet die angegebene SQL Server Express LocalDB-Instanz.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-103">Stops the specified SQL Server Express LocalDB instance from running.</span></span>  
  
 <span data-ttu-id="8ca8c-104">**Headerdatei:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="8ca8c-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ca8c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ca8c-105">Syntax</span></span>  
  
```  
HRESULT LocalDBStopInstance(  
           PCWSTR pInstanceName,  
           DWORD dwFlags,   
           ULONG ulTimeout   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ca8c-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8ca8c-106">Parameters</span></span>  
 <span data-ttu-id="8ca8c-107">*pinstancename*</span><span class="sxs-lookup"><span data-stu-id="8ca8c-107">*pInstanceName*</span></span>  
 <span data-ttu-id="8ca8c-108">[Eingabe] Der Name der LocalDB-Instanz, die angehalten werden soll.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-108">[Input] The name of the LocalDB instance to stop.</span></span>  
  
 <span data-ttu-id="8ca8c-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="8ca8c-109">*dwFlags*</span></span>  
 <span data-ttu-id="8ca8c-110">[Eingabe] Ein Flagwert oder eine Kombination der Flagwerte, die den Weg zum Beenden der Instanz angibt.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-110">[Input] One or a combination of the flag values specifying the way to stop the instance.</span></span>  
  
 <span data-ttu-id="8ca8c-111">Verfügbare Flags:</span><span class="sxs-lookup"><span data-stu-id="8ca8c-111">Available flags:</span></span>  
  
 <span data-ttu-id="8ca8c-112">LOCALDB_SHUTDOWN_KILL_PROCESS</span><span class="sxs-lookup"><span data-stu-id="8ca8c-112">LOCALDB_SHUTDOWN_KILL_PROCESS</span></span>  
 <span data-ttu-id="8ca8c-113">Sofortiges Herunterfahren unter Verwendung des Betriebssystembefehls zum Beenden von Prozessen.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-113">Shut down immediately using the kill process operating system command.</span></span>  
  
 <span data-ttu-id="8ca8c-114">LOCALDB_SHUTDOWN_WITH_NOWAIT</span><span class="sxs-lookup"><span data-stu-id="8ca8c-114">LOCALDB_SHUTDOWN_WITH_NOWAIT</span></span>  
 <span data-ttu-id="8ca8c-115">Herunterfahren mithilfe des Transact-SQL-Befehls der WITH NOWAIT-Option.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-115">Shut down using the WITH NOWAIT option Transact-SQL command.</span></span>  
  
 <span data-ttu-id="8ca8c-116">Wenn keines der Flags festgelegt ist, wird die LocalDB-Instanz mithilfe des Transact-SQL-Befehls SHUTDOWN heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-116">If none of the flags is set, the LocalDB instance will be shut down using the SHUTDOWN Transact-SQL command.</span></span> <span data-ttu-id="8ca8c-117">Wenn beide Flags festgelegt sind, hat das LOCALDB_SHUTDOWN_KILL_PROCESS-Flag Vorrang.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-117">If both flags are set, the LOCALDB_SHUTDOWN_KILL_PROCESS flag takes precedence.</span></span>  
  
 <span data-ttu-id="8ca8c-118">*ulTimeout*</span><span class="sxs-lookup"><span data-stu-id="8ca8c-118">*ulTimeout*</span></span>  
 <span data-ttu-id="8ca8c-119">[Eingabe] Die Wartezeit in Sekunden, bis dieser Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-119">[Input] The time in seconds to wait for this operation to complete.</span></span> <span data-ttu-id="8ca8c-120">Wenn dieser Wert 0 beträgt, kehrt diese Funktion sofort zurück, ohne zu warten, bis die LocalDB-Instanz beendet ist.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-120">If this value is 0, this function will return immediately without waiting for the LocalDB instance to stop.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="8ca8c-121">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="8ca8c-121">Returns</span></span>  
 <span data-ttu-id="8ca8c-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="8ca8c-122">S_OK</span></span>  
 <span data-ttu-id="8ca8c-123">Die Funktion wurde erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-123">The function succeeded.</span></span>  
  
 [<span data-ttu-id="8ca8c-124">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="8ca8c-124">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="8ca8c-125">SQL Server Express LocalDB ist nicht auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-125">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="8ca8c-126">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="8ca8c-126">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="8ca8c-127">Mindestens ein angegebener Eingabeparameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-127">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="8ca8c-128">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="8ca8c-128">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="8ca8c-129">Der angegebene Instanzname ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-129">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="8ca8c-130">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="8ca8c-130">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="8ca8c-131">Die Instanz ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-131">The instance does not exist.</span></span>  
  
 [<span data-ttu-id="8ca8c-132">LOCALDB_ERROR_WAIT_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8ca8c-132">LOCALDB_ERROR_WAIT_TIMEOUT</span></span>](../express-localdb-error-messages/localdb-error-wait-timeout.md)  
 <span data-ttu-id="8ca8c-133">Beim versuchten Abrufen der Synchronisierungssperren ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-133">A time-out occurred while trying to acquire the synchronization locks.</span></span>  
  
 [<span data-ttu-id="8ca8c-134">LOCALDB_ERROR_INSTANCE_STOP_FAILED</span><span class="sxs-lookup"><span data-stu-id="8ca8c-134">LOCALDB_ERROR_INSTANCE_STOP_FAILED</span></span>](../express-localdb-error-messages/localdb-error-instance-stop-failed.md)  
 <span data-ttu-id="8ca8c-135">Der Beendigungsvorgang wurde nicht innerhalb der angegebenen Zeit abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-135">The stop operation failed to complete within the given time.</span></span>  
  
 [<span data-ttu-id="8ca8c-136">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="8ca8c-136">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="8ca8c-137">Der Pfad, unter dem die Instanz gespeichert werden soll, ist länger als MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-137">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="8ca8c-138">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="8ca8c-138">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-get-user-profile-folder.md)  
 <span data-ttu-id="8ca8c-139">Ein Benutzerprofilordner kann nicht abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-139">A user profile folder cannot be retrieved.</span></span>  
  
 [<span data-ttu-id="8ca8c-140">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="8ca8c-140">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="8ca8c-141">Auf einen Instanzordner kann nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-141">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="8ca8c-142">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="8ca8c-142">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="8ca8c-143">Auf eine Instanzregistrierung kann nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-143">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="8ca8c-144">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="8ca8c-144">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="8ca8c-145">Eine Instanzkonfiguration ist beschädigt.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-145">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="8ca8c-146">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8ca8c-146">LOCALDB_ERROR_CALLER_IS_NOT_OWNER</span></span>](../express-localdb-error-messages/localdb-error-caller-is-not-owner.md)  
 <span data-ttu-id="8ca8c-147">API-Aufrufer ist kein Eigentümer der LocalDB-Instanz.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-147">API caller is not LocalDB instance owner.</span></span>  
  
 [<span data-ttu-id="8ca8c-148">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="8ca8c-148">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="8ca8c-149">Ein unerwarteter Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-149">An unexpected error occurred.</span></span> <span data-ttu-id="8ca8c-150">Weitere Informationen finden Sie im Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="8ca8c-150">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ca8c-151">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8ca8c-151">Remarks</span></span>  
 <span data-ttu-id="8ca8c-152">Ein Codebeispiel, in dem die LocalDB-API verwendet wird, finden Sie unter [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="8ca8c-152">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ca8c-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8ca8c-153">See Also</span></span>  
 [<span data-ttu-id="8ca8c-154">SQL Server Express LocalDB-Header und Versionsinformationen</span><span class="sxs-lookup"><span data-stu-id="8ca8c-154">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
