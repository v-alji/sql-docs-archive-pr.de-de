---
title: Localdbgetinhaltungen-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBGetInstances
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: f95a9980-8bc0-426c-8aa1-e2660b6784cf
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4a6f758bd647fd69a14f72a0651bb3e2e33a7c79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695617"
---
# <a name="localdbgetinstances-function"></a><span data-ttu-id="cbcf1-102">LocalDBGetInstances-Funktion</span><span class="sxs-lookup"><span data-stu-id="cbcf1-102">LocalDBGetInstances Function</span></span>
  <span data-ttu-id="cbcf1-103">Gibt alle SQL Server Express LocalDB-Instanzen mit der angegebenen Version zurück.</span><span class="sxs-lookup"><span data-stu-id="cbcf1-103">Returns all SQL Server Express LocalDB instances with the given version.</span></span>  
  
 <span data-ttu-id="cbcf1-104">**Headerdatei:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="cbcf1-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbcf1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cbcf1-105">Syntax</span></span>  
  
```  
#define MAX_LOCALDB_INSTANCE_NAME_LENGTH 128typedef WCHAR TLocalDBInstanceName[MAX_LOCALDB_INSTANCE_NAME_LENGTH + 1];typedef TLocalDBInstanceName* PTLocalDBInstanceName;  
HRESULT LocalDBGetInstances(  
           PTLocalDBInstanceName pInstanceNames,  
           LPDWORD lpdwNumberOfInstances  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbcf1-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="cbcf1-106">Parameters</span></span>  
 <span data-ttu-id="cbcf1-107">*pInstanceNames*</span><span class="sxs-lookup"><span data-stu-id="cbcf1-107">*pInstanceNames*</span></span>  
 <span data-ttu-id="cbcf1-108">Ausgeben Wenn diese Funktion zurückgegeben wird, enthält Sie die Namen der benannten und der localdb-Standard Instanzen auf der Arbeitsstation des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="cbcf1-108">[Output] When this function returns, contains the names of both named and default LocalDB instances on the user's workstation.</span></span>  
  
 <span data-ttu-id="cbcf1-109">*lpdwnumofinhaltungen*</span><span class="sxs-lookup"><span data-stu-id="cbcf1-109">*lpdwNumberOfInstances*</span></span>  
 <span data-ttu-id="cbcf1-110">[Eingabe/Ausgabe] Bei Eingabe enthält dieses Objekt die Anzahl der Slots für Instanznamen im *pInstanceNames* -Puffer.</span><span class="sxs-lookup"><span data-stu-id="cbcf1-110">[Input/Output] On input, contains the number of slots for instance names in the *pInstanceNames* buffer.</span></span> <span data-ttu-id="cbcf1-111">Enthält bei Ausgabe die Anzahl der localdb-Instanzen, die auf der Arbeitsstation des Benutzers gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="cbcf1-111">On output, contains the number of LocalDB instances found on the user's workstation.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="cbcf1-112">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="cbcf1-112">Returns</span></span>  
 <span data-ttu-id="cbcf1-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="cbcf1-113">S_OK</span></span>  
 <span data-ttu-id="cbcf1-114">Die Funktion wurde erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cbcf1-114">The function succeeded.</span></span>  
  
 [<span data-ttu-id="cbcf1-115">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="cbcf1-115">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="cbcf1-116">SQL Server Express LocalDB ist nicht auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="cbcf1-116">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="cbcf1-117">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="cbcf1-117">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="cbcf1-118">Mindestens ein angegebener Eingabeparameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="cbcf1-118">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="cbcf1-119">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="cbcf1-119">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>](../express-localdb-error-messages/localdb-error-insufficient-buffer.md)  
 <span data-ttu-id="cbcf1-120">Der Eingabepuffer ist zu kurz. Abschneiden wurde nicht angefordert.</span><span class="sxs-lookup"><span data-stu-id="cbcf1-120">The input buffer is too short, and truncation was not requested.</span></span>  
  
 [<span data-ttu-id="cbcf1-121">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="cbcf1-121">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>](../express-localdb-error-messages/localdb-error-instance-folder-path-too-long.md)  
 <span data-ttu-id="cbcf1-122">Der Pfad, unter dem die Instanz gespeichert werden soll, ist länger als MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="cbcf1-122">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
 [<span data-ttu-id="cbcf1-123">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span><span class="sxs-lookup"><span data-stu-id="cbcf1-123">LOCALDB_ERROR_CANNOT_ACCESS_INSTANCE_REGISTRY</span></span>](../express-localdb-error-messages/localdb-error-cannot-access-instance-registry.md)  
 <span data-ttu-id="cbcf1-124">Auf eine Instanzregistrierung kann nicht zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="cbcf1-124">An instance registry cannot be accessed.</span></span>  
  
 [<span data-ttu-id="cbcf1-125">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="cbcf1-125">LOCALDB_ERROR_INSTANCE_CONFIGURATION_CORRUPT</span></span>](../express-localdb-error-messages/localdb-error-instance-configuration-corrupt.md)  
 <span data-ttu-id="cbcf1-126">Eine Instanzkonfiguration ist beschädigt.</span><span class="sxs-lookup"><span data-stu-id="cbcf1-126">An instance configuration is corrupted.</span></span>  
  
 [<span data-ttu-id="cbcf1-127">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="cbcf1-127">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="cbcf1-128">Ein unerwarteter Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="cbcf1-128">An unexpected error occurred.</span></span> <span data-ttu-id="cbcf1-129">Weitere Informationen finden Sie im Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="cbcf1-129">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbcf1-130">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="cbcf1-130">Remarks</span></span>  
 <span data-ttu-id="cbcf1-131">Ein Codebeispiel, in dem die LocalDB-API verwendet wird, finden Sie unter [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="cbcf1-131">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbcf1-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cbcf1-132">See Also</span></span>  
 [<span data-ttu-id="cbcf1-133">SQL Server Express LocalDB-Header und Versionsinformationen</span><span class="sxs-lookup"><span data-stu-id="cbcf1-133">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  