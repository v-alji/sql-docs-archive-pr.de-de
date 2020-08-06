---
title: Localdbformatmessage-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- LocalDBFormatMessage
api_location:
- sqluserinstance.dll
topic_type:
- apiref
ms.assetid: 31b3152a-94cf-4f75-a31b-296d7dd16dbe
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ece28f19e3488fae248bf26c3a54a018ba6efd0c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726942"
---
# <a name="localdbformatmessage-function"></a><span data-ttu-id="98f31-102">LocalDBFormatMessage-Funktion</span><span class="sxs-lookup"><span data-stu-id="98f31-102">LocalDBFormatMessage Function</span></span>
  <span data-ttu-id="98f31-103">Gibt die lokalisierte Textbeschreibung für den angegebenen SQL Server Express LocalDB-Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="98f31-103">Returns the localized textual description for the specified SQL Server Express LocalDB error.</span></span>  
  
 <span data-ttu-id="98f31-104">**Headerdatei:** sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="98f31-104">**Header file:** sqlncli.h</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98f31-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="98f31-105">Syntax</span></span>  
  
```  
HRESULT LocalDBFormatMessage(  
           HRESULT hrLocalDB,  
           DWORD dwFlags,   
           DWORD dwLanguageId,   
           LPWSTR wszMessage,   
           LPDWORD lpcchMessage   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98f31-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="98f31-106">Parameters</span></span>  
 <span data-ttu-id="98f31-107">*hrlocaldb*</span><span class="sxs-lookup"><span data-stu-id="98f31-107">*hrLocalDB*</span></span>  
 <span data-ttu-id="98f31-108">[Eingabe] Der LocalDB-Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="98f31-108">[Input] The LocalDB error code.</span></span>  
  
 <span data-ttu-id="98f31-109">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="98f31-109">*dwFlags*</span></span>  
 <span data-ttu-id="98f31-110">[Eingabe] Die Flags, die das Verhalten dieser Funktion angeben.</span><span class="sxs-lookup"><span data-stu-id="98f31-110">[Input] The flags specifying the behavior of this function.</span></span>  
  
 <span data-ttu-id="98f31-111">Verfügbare Flags:</span><span class="sxs-lookup"><span data-stu-id="98f31-111">Available flags:</span></span>  
  
 <span data-ttu-id="98f31-112">LOCALDB_TRUNCATE_ERR_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="98f31-112">LOCALDB_TRUNCATE_ERR_MESSAGE</span></span>  
 <span data-ttu-id="98f31-113">Wenn der Eingabepuffer zu kurz ist, wird die Fehlermeldung abgeschnitten, damit sie in den Puffer passt.</span><span class="sxs-lookup"><span data-stu-id="98f31-113">If the input buffer is too short, the error message will be truncated to fit the buffer.</span></span>  
  
 <span data-ttu-id="98f31-114">*dwLanguageId*</span><span class="sxs-lookup"><span data-stu-id="98f31-114">*dwLanguageId*</span></span>  
 <span data-ttu-id="98f31-115">[Eingabe] Die gewünschte Sprache (LANGID) oder 0, falls die Win32 FormatMessage-Sprachreihenfolge verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="98f31-115">[Input] The language desired (LANGID) or 0, in which case the Win32 FormatMessage language order is used.</span></span>  
  
 <span data-ttu-id="98f31-116">*wszMessage*</span><span class="sxs-lookup"><span data-stu-id="98f31-116">*wszMessage*</span></span>  
 <span data-ttu-id="98f31-117">[Ausgabe] Der Puffer zum Speichern der LocalDB-Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="98f31-117">[Output] The buffer to store the LocalDB error message.</span></span>  
  
 <span data-ttu-id="98f31-118">*lpcchmessage*</span><span class="sxs-lookup"><span data-stu-id="98f31-118">*lpcchMessage*</span></span>  
 <span data-ttu-id="98f31-119">[Eingabe/Ausgabe] Bei Eingabe enthält dieses Objekt die Größe des *wszMessage* -Puffers in Zeichen.</span><span class="sxs-lookup"><span data-stu-id="98f31-119">[Input/Output] On input contains the size of the *wszMessage* buffer in characters.</span></span> <span data-ttu-id="98f31-120">Wenn der angegebene Puffer zu klein ist, enthält dieses Objekt bei Ausgabe die erforderliche Puffergröße in Zeichen, einschließlich sämtlicher nachfolgender Nullen.</span><span class="sxs-lookup"><span data-stu-id="98f31-120">On output, if the given buffer size is too small, contains the buffer size required in characters, including any trailing nulls.</span></span> <span data-ttu-id="98f31-121">Wenn die Funktion erfolgreich ausgeführt wird, enthält dieses Objekt die Anzahl der Zeichen in der Meldung, ohne nachfolgende Nullen.</span><span class="sxs-lookup"><span data-stu-id="98f31-121">If the function succeeds, contains the number of characters in the message, excluding any trailing nulls.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="98f31-122">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="98f31-122">Returns</span></span>  
 <span data-ttu-id="98f31-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="98f31-123">S_OK</span></span>  
 <span data-ttu-id="98f31-124">Die Funktion wurde erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="98f31-124">The function succeeded.</span></span>  
  
 [<span data-ttu-id="98f31-125">LOCALDB_ERROR_NOT_INSTALLED</span><span class="sxs-lookup"><span data-stu-id="98f31-125">LOCALDB_ERROR_NOT_INSTALLED</span></span>](../express-localdb-error-messages/localdb-error-not-installed.md)  
 <span data-ttu-id="98f31-126">SQL Server Express LocalDB ist nicht auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="98f31-126">SQL Server Express LocalDB is not installed on the computer.</span></span>  
  
 [<span data-ttu-id="98f31-127">LOCALDB_ERROR_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="98f31-127">LOCALDB_ERROR_INVALID_PARAMETER</span></span>](../express-localdb-error-messages/localdb-error-invalid-parameter.md)  
 <span data-ttu-id="98f31-128">Mindestens ein angegebener Eingabeparameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="98f31-128">One or more specified input parameters are invalid.</span></span>  
  
 [<span data-ttu-id="98f31-129">LOCALDB_ERROR_UNKNOWN_ERROR_CODE</span><span class="sxs-lookup"><span data-stu-id="98f31-129">LOCALDB_ERROR_UNKNOWN_ERROR_CODE</span></span>](../express-localdb-error-messages/localdb-error-unknown-error-code.md)  
 <span data-ttu-id="98f31-130">Die angeforderte Meldung ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="98f31-130">The requested message does not exist.</span></span>  
  
 [<span data-ttu-id="98f31-131">LOCALDB_ERROR_UNKNOWN_LANGUAGE_ID</span><span class="sxs-lookup"><span data-stu-id="98f31-131">LOCALDB_ERROR_UNKNOWN_LANGUAGE_ID</span></span>](../express-localdb-error-messages/localdb-error-unknown-language-id.md)  
 <span data-ttu-id="98f31-132">Die Meldung ist in der angeforderten Sprache nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="98f31-132">The message is not available in the requested language.</span></span>  
  
 [<span data-ttu-id="98f31-133">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="98f31-133">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>](../express-localdb-error-messages/localdb-error-insufficient-buffer.md)  
 <span data-ttu-id="98f31-134">Der Eingabepuffer *wszMessage* ist zu kurz. Abschneiden wird nicht angefordert.</span><span class="sxs-lookup"><span data-stu-id="98f31-134">The input buffer *wszMessage* is too short, and truncation is not requested.</span></span>  
  
 [<span data-ttu-id="98f31-135">LOCALDB_ERROR_INTERNAL_ERROR</span><span class="sxs-lookup"><span data-stu-id="98f31-135">LOCALDB_ERROR_INTERNAL_ERROR</span></span>](../express-localdb-error-messages/localdb-error-internal-error.md)  
 <span data-ttu-id="98f31-136">Ein unerwarteter Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="98f31-136">An unexpected error occurred.</span></span> <span data-ttu-id="98f31-137">Weitere Informationen finden Sie im Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="98f31-137">See the event log for details.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98f31-138">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="98f31-138">Remarks</span></span>  
 <span data-ttu-id="98f31-139">Ein Codebeispiel, in dem die LocalDB-API verwendet wird, finden Sie unter [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span><span class="sxs-lookup"><span data-stu-id="98f31-139">For a code sample that uses LocalDB API, see [SQL Server Express LocalDB Reference](../sql-server-express-localdb-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98f31-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="98f31-140">See Also</span></span>  
 [<span data-ttu-id="98f31-141">SQL Server Express LocalDB-Header und Versionsinformationen</span><span class="sxs-lookup"><span data-stu-id="98f31-141">SQL Server Express LocalDB Header and Version Information</span></span>](sql-server-express-localdb-header-and-version-information.md)  
  
  
