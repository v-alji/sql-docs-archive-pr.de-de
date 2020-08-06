---
title: MSSQLSERVER_33028 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33028 (Database Engine error)
ms.assetid: c5cec0e4-0bcd-4907-826f-e7d835cfcb37
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 555dcf0220793abc0e8af81b3f56867f9960c5f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617060"
---
# <a name="mssqlserver_33028"></a><span data-ttu-id="d30ca-102">MSSQLSERVER_33028</span><span class="sxs-lookup"><span data-stu-id="d30ca-102">MSSQLSERVER_33028</span></span>
    
## <a name="details"></a><span data-ttu-id="d30ca-103">Details</span><span class="sxs-lookup"><span data-stu-id="d30ca-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d30ca-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="d30ca-104">Product Name</span></span>|<span data-ttu-id="d30ca-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d30ca-105">SQL Server</span></span>|  
|<span data-ttu-id="d30ca-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="d30ca-106">Event ID</span></span>|<span data-ttu-id="d30ca-107">33028</span><span class="sxs-lookup"><span data-stu-id="d30ca-107">33028</span></span>|  
|<span data-ttu-id="d30ca-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="d30ca-108">Event Source</span></span>|<span data-ttu-id="d30ca-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d30ca-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d30ca-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="d30ca-110">Component</span></span>|<span data-ttu-id="d30ca-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d30ca-111">SQLEngine</span></span>|  
|<span data-ttu-id="d30ca-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="d30ca-112">Symbolic Name</span></span>|<span data-ttu-id="d30ca-113">SEC_CRYPTOPROV_CANTOPENSESSION</span><span class="sxs-lookup"><span data-stu-id="d30ca-113">SEC_CRYPTOPROV_CANTOPENSESSION</span></span>|  
|<span data-ttu-id="d30ca-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="d30ca-114">Message Text</span></span>|<span data-ttu-id="d30ca-115">Sitzung kann nicht für %S_MSG ‚%.\*ls’ geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="d30ca-115">Cannot open session for %S_MSG '%.\*ls'.</span></span> <span data-ttu-id="d30ca-116">Anbieterfehlercode: %d.</span><span class="sxs-lookup"><span data-stu-id="d30ca-116">Provider error code: %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d30ca-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="d30ca-117">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d30ca-118">konnte den in der Fehlermeldung aufgelisteten Kryptografieanbieter nicht öffnen.</span><span class="sxs-lookup"><span data-stu-id="d30ca-118">was unable to open the cryptographic provider listed in the error message.</span></span> <span data-ttu-id="d30ca-119">Der Kryptografieanbieter hat den aufgelisteten Fehlercode angegeben.</span><span class="sxs-lookup"><span data-stu-id="d30ca-119">The cryptographic provider supplied the error code listed.</span></span> <span data-ttu-id="d30ca-120">Sie müssen möglicherweise den Kryptografieanbieter für weitere Informationen über den Fehler verständigen.</span><span class="sxs-lookup"><span data-stu-id="d30ca-120">You may need to contact your cryptographic provider for more information about the error.</span></span>  
  
|<span data-ttu-id="d30ca-121">Fehlercode</span><span class="sxs-lookup"><span data-stu-id="d30ca-121">Error code</span></span>|<span data-ttu-id="d30ca-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d30ca-122">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="d30ca-123">0</span><span class="sxs-lookup"><span data-stu-id="d30ca-123">0</span></span>|<span data-ttu-id="d30ca-124">Erfolg.</span><span class="sxs-lookup"><span data-stu-id="d30ca-124">Success.</span></span> <span data-ttu-id="d30ca-125">Kein Fehler.</span><span class="sxs-lookup"><span data-stu-id="d30ca-125">No error.</span></span>|  
|<span data-ttu-id="d30ca-126">1</span><span class="sxs-lookup"><span data-stu-id="d30ca-126">1</span></span>|<span data-ttu-id="d30ca-127">Fehler.</span><span class="sxs-lookup"><span data-stu-id="d30ca-127">Failure.</span></span> <span data-ttu-id="d30ca-128">Ein unbekannter oder unerwarteter Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d30ca-128">An unspecified or unexpected error occurred.</span></span> <span data-ttu-id="d30ca-129">Es sind keine zusätzlichen Informationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d30ca-129">Additional information is not available.</span></span>|  
|<span data-ttu-id="d30ca-130">2</span><span class="sxs-lookup"><span data-stu-id="d30ca-130">2</span></span>|<span data-ttu-id="d30ca-131">Nicht genügend Pufferspeicher.</span><span class="sxs-lookup"><span data-stu-id="d30ca-131">Insufficient Buffer.</span></span> <span data-ttu-id="d30ca-132">Speicherplatz konnte nicht für den Kryptografieanbieter reserviert werden.</span><span class="sxs-lookup"><span data-stu-id="d30ca-132">Space could not be allocated for the cryptographic provider.</span></span>|  
|<span data-ttu-id="d30ca-133">3</span><span class="sxs-lookup"><span data-stu-id="d30ca-133">3</span></span>|<span data-ttu-id="d30ca-134">Nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d30ca-134">Not Supported.</span></span> <span data-ttu-id="d30ca-135">Der Kryptografieanbieter wird nicht von dieser Version unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d30ca-135">The cryptographic provider is not supported by this release.</span></span> <span data-ttu-id="d30ca-136">Wählen Sie einen anderen Kryptografieanbieter aus.</span><span class="sxs-lookup"><span data-stu-id="d30ca-136">Select another cryptographic provider.</span></span>|  
|<span data-ttu-id="d30ca-137">4</span><span class="sxs-lookup"><span data-stu-id="d30ca-137">4</span></span>|<span data-ttu-id="d30ca-138">Nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="d30ca-138">Not Found.</span></span> <span data-ttu-id="d30ca-139">Der angegebene Kryptografieanbieter ist nicht vorhanden,oder Sie haben keine Autorisierung für den Zugriff auf die Dateien.</span><span class="sxs-lookup"><span data-stu-id="d30ca-139">The specified cryptographic provider is not present or you do not have authorization to access the files.</span></span>|  
|<span data-ttu-id="d30ca-140">5</span><span class="sxs-lookup"><span data-stu-id="d30ca-140">5</span></span>|<span data-ttu-id="d30ca-141">Authorization Failure.</span><span class="sxs-lookup"><span data-stu-id="d30ca-141">Authorization Failure.</span></span> <span data-ttu-id="d30ca-142">Dies kann durch ein falsches Kennwort oder einen falschen Benutzernamen bei der Erstellung von Anmeldeinformationen verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="d30ca-142">Can result from providing an incorrect password or username when creating the credential.</span></span> <span data-ttu-id="d30ca-143">Dies kann verursacht werden, wenn die Anmeldeinformationen nicht vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d30ca-143">Can result if the credential does not exist.</span></span>|  
|<span data-ttu-id="d30ca-144">6</span><span class="sxs-lookup"><span data-stu-id="d30ca-144">6</span></span>|<span data-ttu-id="d30ca-145">Ungültiges Argument.</span><span class="sxs-lookup"><span data-stu-id="d30ca-145">Invalid Argument.</span></span> <span data-ttu-id="d30ca-146">Ein ungültiges Argument wurde an den Kryptografieanbieter übergeben.</span><span class="sxs-lookup"><span data-stu-id="d30ca-146">An invalid argument was passed to the cryptographic provider.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="d30ca-147">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="d30ca-147">User Action</span></span>  
 <span data-ttu-id="d30ca-148">Beheben Sie den Fehler oder wenden Sie sich an den Kryptografieanbieter, um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d30ca-148">Resolve the error, or contact the cryptographic provider for more information.</span></span>  
  
  
