---
title: Localdbkreateinzustance-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBCreateInstance
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 3eebb485-8a53-4a79-82a9-57b8de9f8e84
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ff822c552176ad8c083a1c8ea6c0f2430f72972f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620409"
---
# <a name="localdbcreateinstance-function"></a><span data-ttu-id="50420-102">LocalDBCreateInstance-Funktion</span><span class="sxs-lookup"><span data-stu-id="50420-102">LocalDBCreateInstance Function</span></span>
  <span data-ttu-id="50420-103">Erstellt eine neue SQL Server Express LocalDB-Instanz.</span><span class="sxs-lookup"><span data-stu-id="50420-103">Creates a new SQL Server Express LocalDB instance.</span></span>  
  
 <span data-ttu-id="50420-104">**Headerdatei:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="50420-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50420-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="50420-105">Syntax</span></span>  
  
```  
HRESULT LocalDBCreateInstance(  
           PCWSTR wszVersion,  
           PCWSTR pInstanceName,   
           DWORD dwFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50420-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="50420-106">Parameters</span></span>  
 <span data-ttu-id="50420-107">*wszversion*</span><span class="sxs-lookup"><span data-stu-id="50420-107">*wszVersion*</span></span>  
 <span data-ttu-id="50420-108">[Eingabe] Die LocalDB-Version, z. B. 11.0 oder 11.0.1094.2.</span><span class="sxs-lookup"><span data-stu-id="50420-108">[Input] The LocalDB version, for example 11.0 or 11.0.1094.2.</span></span>  
  
 <span data-ttu-id="50420-109">*pinstancename*</span><span class="sxs-lookup"><span data-stu-id="50420-109">*pInstanceName*</span></span>  
 <span data-ttu-id="50420-110">[Eingabe] Der Name für die zu erstellende LocalDB-Instanz.</span><span class="sxs-lookup"><span data-stu-id="50420-110">[Input] The name for the LocalDB instance to create.</span></span>  
  
 <span data-ttu-id="50420-111">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="50420-111">*dwFlags*</span></span>  
 <span data-ttu-id="50420-112">[Eingabe] Zur künftigen Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="50420-112">[Input] Reserved for future use.</span></span> <span data-ttu-id="50420-113">Muss derzeit auf 0 festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="50420-113">Currently should be set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="50420-114">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="50420-114">Returns</span></span>  
 <span data-ttu-id="50420-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="50420-115">S_OK</span></span>  
 <span data-ttu-id="50420-116">Die Funktion wurde erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="50420-116">The function succeeded.</span></span>  
  
 [<span data-ttu-id="50420-117">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="50420-117">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="50420-118">SQL Server Express LocalDB ist nicht auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="50420-118">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="50420-119">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="50420-119">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="50420-120">Mindestens ein angegebener Eingabeparameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="50420-120">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="50420-121">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="50420-121">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="50420-122">Der angegebene Instanzname ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="50420-122">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="50420-123">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="50420-123">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="50420-124">Der Pfad, unter dem die Instanz gespeichert werden soll, ist länger als MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="50420-124">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="50420-125">LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION</span><span class="sxs-lookup"><span data-stu-id="50420-125">LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION</span></span>](../express-localdb-error-messages/localdb-error-instance-exists-with-lower-version.md)  
 <span data-ttu-id="50420-126">Die angegebene Instanz ist bereits vorhanden, aber ihre Version ist niedriger als angefordert.</span><span class="sxs-lookup"><span data-stu-id="50420-126">The specified instance already exists but its version is lower than requested.</span></span>  
  
 [<span data-ttu-id="50420-127">LOCALDB_ERROR_UNKNOWN_VERSION</span><span class="sxs-lookup"><span data-stu-id="50420-127">LOCALDB_ERROR_UNKNOWN_VERSION</span></span>](../express-localdb-error-messages/localdb-error-unknown-version.md)  
 <span data-ttu-id="50420-128">Die angegebene Version ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="50420-128">The specified version is not available.</span></span>  
  
 [<span data-ttu-id="50420-129">LOCALDB_ERROR_VERSION_REQUESTED_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="50420-129">LOCALDB_ERROR_VERSION_REQUESTED_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-version-requested-not-installed.md)  
 <span data-ttu-id="50420-130">Die angegebene Patchebene ist nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="50420-130">The specified patch level is not installed.</span></span>  
  
 [<span data-ttu-id="50420-131">LOCALDB_ERROR_CANNOT_CREATE_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="50420-131">LOCALDB_ERROR_CANNOT_CREATE_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-create-instance-folder.md)  
 <span data-ttu-id="50420-132">Ein Ordner kann nicht unter %userprofile% erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="50420-132">A folder cannot be created under %userprofile%.</span></span>  
  
 [<span data-ttu-id="50420-133">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="50420-133">LOCALDB_ERROR_CANNOT_GET_USER_PROFILE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-get-user-profile-folder.md)  
 <span data-ttu-id="50420-134">Ein Benutzerprofilordner kann nicht abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="50420-134">A user profile folder cannot be retrieved.</span></span>  
  
 [<span data-ttu-id="50420-135">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="50420-135">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="50420-136">Auf einen Instanzordner kann nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="50420-136">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="50420-137">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="50420-137">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="50420-138">Auf eine Instanzregistrierung kann nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="50420-138">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="50420-139">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="50420-139">LOCALDB_ERROR_CANNOT_MODIFY_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-modify-instance-registry.md)  
 <span data-ttu-id="50420-140">Eine Instanzregistrierung kann nicht bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="50420-140">An instance registry cannot be modified.</span></span>  
  
 [<span data-ttu-id="50420-141">LOCALDB_ERROR_SQL_SERVER_STARTUP_FAILED</span><span class="sxs-lookup"><span data-stu-id="50420-141">LOCALDB_ERROR_SQL_SERVER_STARTUP_FAILED</span></span>](../express-localdb-error-messages/localdb-error-sql-server-startup-failed.md)  
 <span data-ttu-id="50420-142">Ein SQL Server-Prozess wird gestartet, der SQL Server-Start ist jedoch fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="50420-142">A SQL Server process is started but SQL Server startup failed.</span></span>  
  
 [<span data-ttu-id="50420-143">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="50420-143">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="50420-144">Eine Instanzkonfiguration ist beschädigt.</span><span class="sxs-lookup"><span data-stu-id="50420-144">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="50420-145">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="50420-145">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="50420-146">Ein unerwarteter Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="50420-146">An unexpected error occurred.</span></span> <span data-ttu-id="50420-147">Weitere Informationen finden Sie im Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="50420-147">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50420-148">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="50420-148">Remarks</span></span>  
 <span data-ttu-id="50420-149">Wenn eine vollständig funktionierende LocalDB-Instanz mit dem angegebenen Namen bereits vorhanden ist und ihre Version der angeforderten entspricht oder höher ist, ist das Ergebnis S_OK.</span><span class="sxs-lookup"><span data-stu-id="50420-149">If a fully functional LocalDB instance with the specified name already exists and its version is equal to or higher than requested, the result is S_OK.</span></span>  
  
 <span data-ttu-id="50420-150">Wenn eine vorhandene Instanz beschädigt wird, schlagen nachfolgende Aufrufe der `LocalDBCreateInstance` API-Methode fehl.</span><span class="sxs-lookup"><span data-stu-id="50420-150">In cases when an existing instance becomes corrupted, subsequent calls to the `LocalDBCreateInstance` API method will fail.</span></span> <span data-ttu-id="50420-151">Beschädigte Instanzen müssen manuell korrigiert oder explizit gelöscht werden, bevor sie wieder verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="50420-151">Corrupted instances must be fixed manually or explicitly deleted before they can be used again.</span></span>  
  
 <span data-ttu-id="50420-152">Ein Codebeispiel, in dem die LocalDB-API verwendet wird, finden Sie unter [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="50420-152">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50420-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="50420-153">See Also</span></span>  
 [<span data-ttu-id="50420-154">SQL Server Express LocalDB-Header und Versionsinformationen</span><span class="sxs-lookup"><span data-stu-id="50420-154">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
