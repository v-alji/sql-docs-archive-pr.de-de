---
title: Localdbgetinstanceingefo-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBGetInstanceInfo
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 231706f5-26c6-42eb-ab47-315df6b8f824
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: dc7cbe2c59a7502a1fd0c8b4f92fb14e5defd50b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615398"
---
# <a name="localdbgetinstanceinfo-function"></a><span data-ttu-id="5bf7f-102">LocalDBGetInstanceInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="5bf7f-102">LocalDBGetInstanceInfo Function</span></span>
  <span data-ttu-id="5bf7f-103">Gibt Informationen für die angegebene SQL Server Express LocalDB-Instanz zurück (beispielsweise, ob sie vorhanden ist, die verwendete LocalDB-Version, ob sie ausgeführt wird usw.).</span><span class="sxs-lookup"><span data-stu-id="5bf7f-103">Returns information for the specified SQL Server Express LocalDB instance, such as whether it exists, the LocalDB version it uses, whether it is running, and so on.</span></span>  
  
 <span data-ttu-id="5bf7f-104">Die Informationen werden in einem `struct` namens " **localdbinstanceinfo**" zurückgegeben, der über die folgende Definition verfügt.</span><span class="sxs-lookup"><span data-stu-id="5bf7f-104">The information is returned in a `struct` named **LocalDBInstanceInfo**, which has the following definition.</span></span>  
  
```  
typedef struct _LocalDBInstanceInfo  
{  
      // Contains the size of the LocalDBInstanceInfo struct  
      DWORD  cbLocalDBInstanceInfoSize;  
  
      // Holds the instance name  
      TLocalDBInstanceNamewszInstanceName;  
  
      // TRUE if the instance files exist on disk, FALSE otherwise  
      BOOL   bExists;  
  
      // TRUE if the instance configuration registry is corrupted, FALSE otherwise  
      BOOLbConfigurationCorrupted;  
  
      // TRUE if the instance is running at the moment, FALSE otherwise  
      BOOL   bIsRunning;  
  
      // Holds the LocalDB version for the instance in the format: major.minor.build.revision  
      DWORD  dwMajor;  
      DWORD  dwMinor;  
      DWORD  dwBuild;  
      DWORD  dwRevision;  
  
      // Holds the date and time when the instance was started for the last time  
      FILETIME ftLastStartUTC;  
  
      // Holds the name of the TDS named pipe to connect to the instance  
      WCHARwszConnection;  
  
      // TRUE if the instance is shared, FALSE otherwise  
      BOOLbIsShared;  
  
      // Holds the shared name for the instance (if the instance is shared)  
      TLocalDBInstanceNamewszSharedInstanceName;  
  
      // Holds the SID of the instance owner (if the instance is shared)  
      WCHARwszOwnerSID;   
  
      // TRUE if the instance is Automatic, FALSE otherwise  
      BOOLbIsAutomatic;  
} LocalDBInstanceInfo;  
  
```  
  
 <span data-ttu-id="5bf7f-105">**Headerdatei:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="5bf7f-105">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bf7f-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="5bf7f-106">Syntax</span></span>  
  
```  
HRESULT LocalDBGetInstanceInfo(  
           PCWSTR wszInstanceName,  
           PLocalDBInstanceInfo pInstanceInfo,  
           DWORD dwInstanceInfoSize   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bf7f-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="5bf7f-107">Parameters</span></span>  
 <span data-ttu-id="5bf7f-108">*wszinstancename*</span><span class="sxs-lookup"><span data-stu-id="5bf7f-108">*wszInstanceName*</span></span>  
 <span data-ttu-id="5bf7f-109">[Eingabe] Der Name der Instanz.</span><span class="sxs-lookup"><span data-stu-id="5bf7f-109">[Input] The instance name.</span></span>  
  
 <span data-ttu-id="5bf7f-110">*pinstanceingefo*</span><span class="sxs-lookup"><span data-stu-id="5bf7f-110">*pInstanceInfo*</span></span>  
 <span data-ttu-id="5bf7f-111">[Ausgabe] Der Puffer zum Speichern der Informationen zur LocalDB-Instanz.</span><span class="sxs-lookup"><span data-stu-id="5bf7f-111">[Output] The buffer to store the information about the LocalDB instance.</span></span>  
  
 <span data-ttu-id="5bf7f-112">*dwinstanceinfosize*</span><span class="sxs-lookup"><span data-stu-id="5bf7f-112">*dwInstanceInfoSize*</span></span>  
 <span data-ttu-id="5bf7f-113">Der Enthält die Größe des *instanceinfo* -Puffers.</span><span class="sxs-lookup"><span data-stu-id="5bf7f-113">[Input] Holds the size of the *InstanceInfo* buffer.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="5bf7f-114">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="5bf7f-114">Returns</span></span>  
 <span data-ttu-id="5bf7f-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="5bf7f-115">S_OK</span></span>  
 <span data-ttu-id="5bf7f-116">Die Funktion wurde erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5bf7f-116">The function succeeded.</span></span>  
  
 [<span data-ttu-id="5bf7f-117">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="5bf7f-117">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="5bf7f-118">SQL Server Express LocalDB ist nicht auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="5bf7f-118">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="5bf7f-119">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="5bf7f-119">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="5bf7f-120">Mindestens ein angegebener Eingabeparameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="5bf7f-120">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="5bf7f-121">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span><span class="sxs-lookup"><span data-stu-id="5bf7f-121">LOCALDB_ERROR_INVALID_INSTANCE_NAME</span></span>](../express-localdb-error-messages/localdb-error-invalid-instance-name.md)  
 <span data-ttu-id="5bf7f-122">Der angegebene Instanzname ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="5bf7f-122">The specified instance name is invalid.</span></span>  
  
 [<span data-ttu-id="5bf7f-123">LOCALDB_ERROR_UNKNOWN_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="5bf7f-123">LOCALDB_ERROR_UNKNOWN_INSTANCE</span></span>](../express-localdb-error-messages/localdb-error-unknown-instance.md)  
 <span data-ttu-id="5bf7f-124">Die Instanz ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="5bf7f-124">The instance does not exist.</span></span>  
  
 [<span data-ttu-id="5bf7f-125">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="5bf7f-125">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="5bf7f-126">Der Pfad, unter dem die Instanz gespeichert werden soll, ist länger als MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="5bf7f-126">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="5bf7f-127">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span><span class="sxs-lookup"><span data-stu-id="5bf7f-127">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_FOLDER</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-folder.md)  
 <span data-ttu-id="5bf7f-128">Auf einen Instanzordner kann nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="5bf7f-128">An instance folder cannot be accessed.</span></span>  
  
 [<span data-ttu-id="5bf7f-129">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="5bf7f-129">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="5bf7f-130">Auf eine Instanzregistrierung kann nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="5bf7f-130">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="5bf7f-131">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="5bf7f-131">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="5bf7f-132">Eine Instanzkonfiguration ist beschädigt.</span><span class="sxs-lookup"><span data-stu-id="5bf7f-132">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="5bf7f-133">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="5bf7f-133">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="5bf7f-134">Ein unerwarteter Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="5bf7f-134">An unexpected error occurred.</span></span> <span data-ttu-id="5bf7f-135">Weitere Informationen finden Sie im Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="5bf7f-135">See the event log for details.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5bf7f-136">Details</span><span class="sxs-lookup"><span data-stu-id="5bf7f-136">Details</span></span>  
 <span data-ttu-id="5bf7f-137">Der Grund für die Einführung des `struct` size-Arguments (*lpinstanceinfosize*) besteht darin, dass die API die Rückgabe verschiedener Versionen von **localdbinstanceinfostruct**ermöglicht und somit die vorwärts-und Abwärtskompatibilität effektiv ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="5bf7f-137">The rationale behind the introduction of the `struct` size argument (*lpInstanceInfoSize*) is to enable the API to return different versions of the **LocalDBInstanceInfostruct**, effectively enabling forward and backward compatibility.</span></span>  
  
 <span data-ttu-id="5bf7f-138">Wenn das `struct` Größen Argument (*lpinstanceinfosize*) mit der Größe einer bekannten Version von **localdbinstanceinfostruct**übereinstimmt, wird diese Version von `struct` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5bf7f-138">If the `struct` size argument (*lpInstanceInfoSize*) matches the size of a known version of the **LocalDBInstanceInfostruct**, that version of the `struct` is returned.</span></span> <span data-ttu-id="5bf7f-139">Andernfalls wird LOCALDB_ERROR_INVALID_PARAMETER zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5bf7f-139">Otherwise, LOCALDB_ERROR_INVALID_PARAMETER is returned.</span></span>  
  
 <span data-ttu-id="5bf7f-140">Ein typisches Beispiel für die Verwendung der **localdbgetinstanceingefo** -API sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="5bf7f-140">A typical example of **LocalDBGetInstanceInfo** API usage looks like this:</span></span>  
  
```  
LocalDBInstanceInfo ii;  
LocalDBInstanceInfo(L"Test", &ii, sizeof(LocalDBInstanceInfo));  
  
```  
  
 <span data-ttu-id="5bf7f-141">Ein Codebeispiel, in dem die LocalDB-API verwendet wird, finden Sie unter [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="5bf7f-141">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bf7f-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5bf7f-142">See Also</span></span>  
 [<span data-ttu-id="5bf7f-143">SQL Server Express LocalDB-Header und Versionsinformationen</span><span class="sxs-lookup"><span data-stu-id="5bf7f-143">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
