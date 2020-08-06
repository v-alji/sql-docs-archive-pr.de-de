---
title: Localdbstartinstance-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBStartInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: cb325f5d-10ee-4a56-ba28-db0074ab3926
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 748bc373e8b0dbad0a91247e068d21b67f2dbc1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622124"
---
# <a name="localdbstartinstance-function"></a><span data-ttu-id="e35c6-102">LocalDBStartInstance-Funktion</span><span class="sxs-lookup"><span data-stu-id="e35c6-102">LocalDBStartInstance Function</span></span>
  <span data-ttu-id="e35c6-103">Startet die angegebene SQL Server Express LocalDB-Instanz.</span><span class="sxs-lookup"><span data-stu-id="e35c6-103">Starts the specified SQL Server Express LocalDB instance.</span></span>  
  
 <span data-ttu-id="e35c6-104">**Headerdatei:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="e35c6-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e35c6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e35c6-105">Syntax</span></span>  
  
```  
HRESULT LocalDBStartInstance(  
           PCWSTR pInstanceName,  
           DWORD dwFlags,   
           LPWSTR wszSqlConnection,   
           LPDWORD lpcchSqlConnection   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e35c6-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e35c6-106">Parameters</span></span>  
 <span data-ttu-id="e35c6-107">*pinstancename*</span><span class="sxs-lookup"><span data-stu-id="e35c6-107">*pInstanceName*</span></span>  
 <span data-ttu-id="e35c6-108">[Eingabe] Der Name der LocalDB-Instanz, die gestartet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e35c6-108">[Input] The name of the LocalDB instance to start.</span></span>  
  
 <span data-ttu-id="e35c6-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="e35c6-109">*dwFlags*</span></span>  
 <span data-ttu-id="e35c6-110">[Eingabe] Zur künftigen Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="e35c6-110">[Input] Reserved for future use.</span></span> <span data-ttu-id="e35c6-111">Muss derzeit auf 0 festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="e35c6-111">Currently should be set to 0.</span></span>  
  
 <span data-ttu-id="e35c6-112">*wszSqlConnection*</span><span class="sxs-lookup"><span data-stu-id="e35c6-112">*wszSqlConnection*</span></span>  
 <span data-ttu-id="e35c6-113">[Ausgabe] Der Puffer zum Speichern der Verbindungszeichenfolge in der LocalDB-Instanz.</span><span class="sxs-lookup"><span data-stu-id="e35c6-113">[Output] The buffer to store the connection string to the LocalDB instance.</span></span>  
  
 <span data-ttu-id="e35c6-114">*lpcchSqlConnection*</span><span class="sxs-lookup"><span data-stu-id="e35c6-114">*lpcchSqlConnection*</span></span>  
 <span data-ttu-id="e35c6-115">[Eingabe/Ausgabe] Bei Eingabe enthält dieses Objekt die Größe des *wszSqlConnection* -Puffers in Zeichen, einschließlich sämtlicher nachfolgender Nullen.</span><span class="sxs-lookup"><span data-stu-id="e35c6-115">[Input/Output] On input contains the size of the *wszSqlConnection* buffer in characters, including any trailing nulls.</span></span> <span data-ttu-id="e35c6-116">Wenn der angegebene Puffer zu klein ist, enthält dieses Objekt bei Ausgabe die erforderliche Puffergröße in Zeichen, einschließlich sämtlicher nachfolgender Nullen.</span><span class="sxs-lookup"><span data-stu-id="e35c6-116">On output, if the given buffer size is too small, contains the required buffer size in characters, including any trailing nulls.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="e35c6-117">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="e35c6-117">Returns</span></span>  
 <span data-ttu-id="e35c6-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="e35c6-118">S_OK</span></span>  
 <span data-ttu-id="e35c6-119">Die Funktion wurde erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e35c6-119">The function succeeded.</span></span>  
  
 [<span data-ttu-id="e35c6-120">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="e35c6-120">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="e35c6-121">SQL Server Express LocalDB ist nicht auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="e35c6-121">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="e35c6-122">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="e35c6-122">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="e35c6-123">Mindestens ein angegebener Eingabeparameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="e35c6-123">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="e35c6-124">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="e35c6-124">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="e35c6-125">Der angegebene Instanzname ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="e35c6-125">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="e35c6-126">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="e35c6-126">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="e35c6-127">Die Instanz ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="e35c6-127">The instance does not exist.</span></span>  
  
 [<span data-ttu-id="e35c6-128">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="e35c6-128">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>](../express-localdb-error-messages/localdb-error-insufficient-buffer.md)  
 <span data-ttu-id="e35c6-129">Der angegebene Puffer *wszSqlConnection* ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="e35c6-129">The specified buffer *wszSqlConnection* is too small.</span></span>  
  
 [<span data-ttu-id="e35c6-130">LOCALDB_ERROR_WAIT_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e35c6-130">LOCALDB_ERROR_WAIT_TIMEOUT</span></span>](../express-localdb-error-messages/localdb-error-wait-timeout.md)  
 <span data-ttu-id="e35c6-131">Beim versuchten Abrufen der Synchronisierungssperren ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e35c6-131">A time-out occurred while trying to acquire the synchronization locks.</span></span>  
  
 [<span data-ttu-id="e35c6-132">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="e35c6-132">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="e35c6-133">Der Pfad, unter dem die Instanz gespeichert werden soll, ist länger als MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="e35c6-133">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="e35c6-134">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="e35c6-134">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-get-user-profile-folder.md)  
 <span data-ttu-id="e35c6-135">Ein Benutzerprofilordner kann nicht abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e35c6-135">A user profile folder cannot be retrieved.</span></span>  
  
 [<span data-ttu-id="e35c6-136">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="e35c6-136">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="e35c6-137">Auf einen Instanzordner kann nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="e35c6-137">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="e35c6-138">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="e35c6-138">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="e35c6-139">Auf eine Instanzregistrierung kann nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="e35c6-139">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="e35c6-140">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="e35c6-140">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-modify-instance-registry.md)  
 <span data-ttu-id="e35c6-141">Eine Instanzregistrierung kann nicht bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="e35c6-141">An instance registry cannot be modified.</span></span>  
  
 [<span data-ttu-id="e35c6-142">LOCALDB_ERROR_CANNOT_CREATE_SQL_PROCESS</span><span class="sxs-lookup"><span data-stu-id="e35c6-142">LOCALDB_ERROR_CANNOT_CREATE_SQL_PROCESS</span></span>](../express-localdb-error-messages/localdb-error-cannot-create-sql-process.md)  
 <span data-ttu-id="e35c6-143">Ein Prozess für SQL Server kann nicht erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e35c6-143">A process for SQL Server cannot be created.</span></span>  
  
 [<span data-ttu-id="e35c6-144">LOCALDB_ERROR_SQL_SERVER_STARTUP_FAILED</span><span class="sxs-lookup"><span data-stu-id="e35c6-144">LOCALDB_ERROR_SQL_SERVER_STARTUP_FAILED</span></span>](../express-localdb-error-messages/localdb-error-sql-server-startup-failed.md)  
 <span data-ttu-id="e35c6-145">Ein SQL Server-Prozess wurde gestartet, der SQL Server-Start ist jedoch fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="e35c6-145">A SQL Server process was started, but SQL Server startup failed.</span></span>  
  
 [<span data-ttu-id="e35c6-146">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="e35c6-146">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="e35c6-147">Eine Instanzkonfiguration war beschädigt.</span><span class="sxs-lookup"><span data-stu-id="e35c6-147">An instance configuration was corrupted.</span></span>  
  
 [<span data-ttu-id="e35c6-148">LOCALDB_ERROR_AUTO_INSTANCE_CREATE_FAILED</span><span class="sxs-lookup"><span data-stu-id="e35c6-148">LOCALDB_ERROR_AUTO_INSTANCE_CREATE_FAILED</span></span>](../express-localdb-error-messages/localdb-error-auto-instance-create-failed.md)  
 <span data-ttu-id="e35c6-149">Kann keine automatische Instanz erstellen.</span><span class="sxs-lookup"><span data-stu-id="e35c6-149">Cannot create an automatic instance.</span></span> <span data-ttu-id="e35c6-150">Fehlerdetails finden Sie im Windows-Anwendungsereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="e35c6-150">See the Windows Application event log for error details.</span></span>  
  
 [<span data-ttu-id="e35c6-151">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="e35c6-151">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="e35c6-152">Ein unerwarteter Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e35c6-152">An unexpected error occurred.</span></span> <span data-ttu-id="e35c6-153">Weitere Informationen finden Sie im Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="e35c6-153">See the event log for details.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e35c6-154">Details</span><span class="sxs-lookup"><span data-stu-id="e35c6-154">Details</span></span>  
 <span data-ttu-id="e35c6-155">Das Verbindungspufferargument (*wszSqlConnection*) und das Verbindungspuffergrößen-Argument (*lpcchSqlConnection*) sind optional.</span><span class="sxs-lookup"><span data-stu-id="e35c6-155">Both the connection buffer argument (*wszSqlConnection*) and the connection buffer size argument (*lpcchSqlConnection*) are optional.</span></span> <span data-ttu-id="e35c6-156">In der folgenden Tabelle werden Optionen zum Verwenden dieser Argumente und ihrer Ergebnisse angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e35c6-156">The following table shows options for using these arguments and their results.</span></span>  
  
|<span data-ttu-id="e35c6-157">Buffer</span><span class="sxs-lookup"><span data-stu-id="e35c6-157">Buffer</span></span>|<span data-ttu-id="e35c6-158">Puffergröße</span><span class="sxs-lookup"><span data-stu-id="e35c6-158">Buffer size</span></span>|<span data-ttu-id="e35c6-159">Sinn</span><span class="sxs-lookup"><span data-stu-id="e35c6-159">Rationale</span></span>|<span data-ttu-id="e35c6-160">Aktion</span><span class="sxs-lookup"><span data-stu-id="e35c6-160">Action</span></span>|  
|------------|-----------------|---------------|------------|  
|<span data-ttu-id="e35c6-161">NULL</span><span class="sxs-lookup"><span data-stu-id="e35c6-161">NULL</span></span>|<span data-ttu-id="e35c6-162">NULL</span><span class="sxs-lookup"><span data-stu-id="e35c6-162">NULL</span></span>|<span data-ttu-id="e35c6-163">Der Benutzer möchte die Instanz starten und benötigt keinen Pipenamen.</span><span class="sxs-lookup"><span data-stu-id="e35c6-163">User wants to start the instance and doesn't need a pipe name.</span></span>|<span data-ttu-id="e35c6-164">Startet eine Instanz (keine Piperückgabe und keine erforderliche Puffergrößenrückgabe).</span><span class="sxs-lookup"><span data-stu-id="e35c6-164">Starts an instance (no pipe return and no required buffer size return).</span></span>|  
|<span data-ttu-id="e35c6-165">NULL</span><span class="sxs-lookup"><span data-stu-id="e35c6-165">NULL</span></span>|<span data-ttu-id="e35c6-166">Anzahl</span><span class="sxs-lookup"><span data-stu-id="e35c6-166">Present</span></span>|<span data-ttu-id="e35c6-167">Benutzer fragt nach der Ausgabepuffergröße.</span><span class="sxs-lookup"><span data-stu-id="e35c6-167">User asks for the output buffer size.</span></span> <span data-ttu-id="e35c6-168">(Im nächsten Aufruf bittet der Benutzer wahrscheinlich um einen tatsächlichen Start.)</span><span class="sxs-lookup"><span data-stu-id="e35c6-168">(In the next call the user will probably ask for an actual start.)</span></span>|<span data-ttu-id="e35c6-169">Gibt eine erforderliche Puffergröße (kein Start und keine Piperückgabe) zurück.</span><span class="sxs-lookup"><span data-stu-id="e35c6-169">Returns a required buffer size (no start and no pipe return).</span></span> <span data-ttu-id="e35c6-170">Ergebnis ist S_OK.</span><span class="sxs-lookup"><span data-stu-id="e35c6-170">Result is S_OK.</span></span>|  
|<span data-ttu-id="e35c6-171">Anzahl</span><span class="sxs-lookup"><span data-stu-id="e35c6-171">Present</span></span>|<span data-ttu-id="e35c6-172">NULL</span><span class="sxs-lookup"><span data-stu-id="e35c6-172">NULL</span></span>|<span data-ttu-id="e35c6-173">Nicht zulässig; falsche Eingabe.</span><span class="sxs-lookup"><span data-stu-id="e35c6-173">Not allowed; incorrect input.</span></span>|<span data-ttu-id="e35c6-174">Das zurückgegebene Ergebnis ist LOCALDB_ERROR_INVALID_PARAMETER.</span><span class="sxs-lookup"><span data-stu-id="e35c6-174">Returned result is LOCALDB_ERROR_INVALID_PARAMETER.</span></span>|  
|<span data-ttu-id="e35c6-175">Anzahl</span><span class="sxs-lookup"><span data-stu-id="e35c6-175">Present</span></span>|<span data-ttu-id="e35c6-176">Anzahl</span><span class="sxs-lookup"><span data-stu-id="e35c6-176">Present</span></span>|<span data-ttu-id="e35c6-177">Der Benutzer möchte die Instanz starten und benötigt den Pipenamen, zu dem nach dem Start eine Verbindung hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e35c6-177">User wants to start the instance and needs the pipe name to connect to it after it is started.</span></span>|<span data-ttu-id="e35c6-178">Überprüft die Puffergröße, startet die Instanz und gibt den Pipenamen im Puffer zurück.</span><span class="sxs-lookup"><span data-stu-id="e35c6-178">Checks the buffer size, starts the instance, and returns the pipe name in the buffer.</span></span> <br /><span data-ttu-id="e35c6-179">Das Puffergrößen Argument gibt die Länge der Zeichenfolge "Server =" zurück, ohne abschließende Nullen.</span><span class="sxs-lookup"><span data-stu-id="e35c6-179">The buffer size argument returns the length of the "server=" string, not including terminating nulls.</span></span>|  
  
 <span data-ttu-id="e35c6-180">Ein Codebeispiel, in dem die LocalDB-API verwendet wird, finden Sie unter [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="e35c6-180">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e35c6-181">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e35c6-181">See Also</span></span>  
 [<span data-ttu-id="e35c6-182">SQL Server Express LocalDB-Header und Versionsinformationen</span><span class="sxs-lookup"><span data-stu-id="e35c6-182">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
