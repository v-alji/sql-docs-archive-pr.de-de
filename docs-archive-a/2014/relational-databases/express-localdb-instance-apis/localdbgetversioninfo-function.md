---
title: Localdbgetversioninfo-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBGetVersionInfo
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: d4aaea30-1d0d-4436-bcdc-5c101d27b1c1
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: e30bb4dcd4c258db899883f650dbfe7100171ef8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725829"
---
# <a name="localdbgetversioninfo-function"></a><span data-ttu-id="95ac9-102">LocalDBGetVersionInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="95ac9-102">LocalDBGetVersionInfo Function</span></span>
  <span data-ttu-id="95ac9-103">Gibt Informationen zur angegebenen SQL Server Express-LocalDB-Version zurück, z. B., ob sie vorhanden ist sowie die vollständige LocalDB-Versionsnummer (inklusive Build- und Releasenummer).</span><span class="sxs-lookup"><span data-stu-id="95ac9-103">Returns information for the specified SQL Server Express LocalDB version, such as whether it exists and the full LocalDB version number (including build and release numbers).</span></span>  
  
 <span data-ttu-id="95ac9-104">Die Informationen werden in Form eines `struct` namens **localdbversioninfo**zurückgegeben, das über die folgende Definition verfügt.</span><span class="sxs-lookup"><span data-stu-id="95ac9-104">The information is returned in the form of a `struct` named **LocalDBVersionInfo**, which has the following definition.</span></span>  
  
```  
typedef struct _LocalDBVersionInfo  
{  
      // Contains the size of the LocalDBVersionInfo struct  
      DWORD  cbLocalDBVersionInfoSize;  
  
      // Holds the version name  
      TLocalDBVersionwszVersion;  
  
      // TRUE if the instance files exist on disk, FALSE otherwise  
      BOOL   bExists;  
  
      // Holds the LocalDB version for the instance in the format: major.minor.build.revision  
      DWORD  dwMajor;  
      DWORD  dwMinor;  
      DWORD  dwBuild;  
      DWORD  dwRevision;  
} LocalDBVersionInfo;  
  
```  
  
 <span data-ttu-id="95ac9-105">**Headerdatei:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="95ac9-105">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95ac9-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="95ac9-106">Syntax</span></span>  
  
```  
HRESULT LocalDBGetVersionInfo(  
           PCWSTR wszVersionName,           PLocalDBVersionInfo pVersionInfo,           DWORD dwVersionInfoSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95ac9-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="95ac9-107">Parameters</span></span>  
 <span data-ttu-id="95ac9-108">*wszversionname*</span><span class="sxs-lookup"><span data-stu-id="95ac9-108">*wszVersionName*</span></span>  
 <span data-ttu-id="95ac9-109">[Eingabe] Der Name der LocalDB-Version.</span><span class="sxs-lookup"><span data-stu-id="95ac9-109">[Input] The LocalDB version name.</span></span>  
  
 <span data-ttu-id="95ac9-110">*pversioninfo*</span><span class="sxs-lookup"><span data-stu-id="95ac9-110">*pVersionInfo*</span></span>  
 <span data-ttu-id="95ac9-111">[Ausgabe] Der Puffer zum Speichern der Informationen zur LocalDB-Version.</span><span class="sxs-lookup"><span data-stu-id="95ac9-111">[Output] The buffer to store the information about the LocalDB version.</span></span>  
  
 <span data-ttu-id="95ac9-112">*dwversioninfosize*</span><span class="sxs-lookup"><span data-stu-id="95ac9-112">*dwVersionInfoSize*</span></span>  
 <span data-ttu-id="95ac9-113">Der Enthält die Größe des *VERSIONINFO* -Puffers.</span><span class="sxs-lookup"><span data-stu-id="95ac9-113">[Input] Holds the size of the *VersionInfo* buffer.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="95ac9-114">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="95ac9-114">Returns</span></span>  
 <span data-ttu-id="95ac9-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="95ac9-115">S_OK</span></span>  
 <span data-ttu-id="95ac9-116">Die Funktion wurde erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="95ac9-116">The function succeeded.</span></span>  
  
 [<span data-ttu-id="95ac9-117">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="95ac9-117">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="95ac9-118">SQL Server Express LocalDB ist nicht auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="95ac9-118">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="95ac9-119">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="95ac9-119">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="95ac9-120">Mindestens ein angegebener Eingabeparameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="95ac9-120">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="95ac9-121">LOCALDB_ERROR_UNKNOWN_VERSION</span><span class="sxs-lookup"><span data-stu-id="95ac9-121">LOCALDB_ERROR_UNKNOWN_VERSION</span></span>](../express-localdb-error-messages/localdb-error-unknown-version.md)  
 <span data-ttu-id="95ac9-122">Die angegebene LocalDB-Version ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="95ac9-122">The specified LocalDB version does not exist.</span></span>  
  
 [<span data-ttu-id="95ac9-123">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="95ac9-123">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="95ac9-124">Ein unerwarteter Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="95ac9-124">An unexpected error occurred.</span></span> <span data-ttu-id="95ac9-125">Weitere Informationen finden Sie im Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="95ac9-125">See the event log for details.</span></span>  
  
## <a name="details"></a><span data-ttu-id="95ac9-126">Details</span><span class="sxs-lookup"><span data-stu-id="95ac9-126">Details</span></span>  
 <span data-ttu-id="95ac9-127">Der Grund für die Einführung des `struct` size-Arguments (*lpversioninfosize*) besteht darin, dass die API die Rückgabe verschiedener Versionen von **localdbversioninfostruct**ermöglicht und somit die vorwärts-und Abwärtskompatibilität effektiv ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="95ac9-127">The rationale behind the introduction of the `struct` size argument (*lpVersionInfoSize*) is to enable the API to return different versions of the **LocalDBVersionInfostruct**, effectively enabling forward and backward compatibility.</span></span>  
  
 <span data-ttu-id="95ac9-128">Wenn das `struct` Größen Argument (*lpversioninfosize*) mit der Größe einer bekannten Version von **localdbversioninfostruct**übereinstimmt, wird diese Version von `struct` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="95ac9-128">If the `struct` size argument (*lpVersionInfoSize*) matches the size of a known version of the **LocalDBVersionInfostruct**, that version of the `struct` is returned.</span></span> <span data-ttu-id="95ac9-129">Andernfalls wird LOCALDB_ERROR_INVALID_PARAMETER zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="95ac9-129">Otherwise, LOCALDB_ERROR_INVALID_PARAMETER is returned.</span></span>  
  
 <span data-ttu-id="95ac9-130">Ein typisches Beispiel für die Verwendung der **localdbgetversioninfo** -API sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="95ac9-130">A typical example of **LocalDBGetVersionInfo** API usage looks like this:</span></span>  
  
```  
LocalDBVersionInfo vi;  
LocalDBVersionInfo(L"11.0", &vi, sizeof(LocalDBVersionInfo));  
  
```  
  
## <a name="remarks"></a><span data-ttu-id="95ac9-131">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="95ac9-131">Remarks</span></span>  
 <span data-ttu-id="95ac9-132">Ein Codebeispiel, in dem die LocalDB-API verwendet wird, finden Sie unter [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="95ac9-132">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95ac9-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="95ac9-133">See Also</span></span>  
 [<span data-ttu-id="95ac9-134">SQL Server Express LocalDB-Header und Versionsinformationen</span><span class="sxs-lookup"><span data-stu-id="95ac9-134">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
