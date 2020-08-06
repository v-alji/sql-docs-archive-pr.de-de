---
title: MSSQLSERVER_33085 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33085 (Database Engine error)
ms.assetid: c27b8d1d-668a-4ba8-8b61-25a5ebbc5485
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8d774ab115c2d0ddbbd7b35c7e32db17e39fcb2e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617058"
---
# <a name="mssqlserver_33085"></a><span data-ttu-id="9d6c1-102">MSSQLSERVER_33085</span><span class="sxs-lookup"><span data-stu-id="9d6c1-102">MSSQLSERVER_33085</span></span>
    
## <a name="details"></a><span data-ttu-id="9d6c1-103">Details</span><span class="sxs-lookup"><span data-stu-id="9d6c1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9d6c1-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="9d6c1-104">Product Name</span></span>|<span data-ttu-id="9d6c1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9d6c1-105">SQL Server</span></span>|  
|<span data-ttu-id="9d6c1-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="9d6c1-106">Event ID</span></span>|<span data-ttu-id="9d6c1-107">33085</span><span class="sxs-lookup"><span data-stu-id="9d6c1-107">33085</span></span>|  
|<span data-ttu-id="9d6c1-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="9d6c1-108">Event Source</span></span>|<span data-ttu-id="9d6c1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9d6c1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9d6c1-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="9d6c1-110">Component</span></span>|<span data-ttu-id="9d6c1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9d6c1-111">SQLEngine</span></span>|  
|<span data-ttu-id="9d6c1-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="9d6c1-112">Symbolic Name</span></span>|<span data-ttu-id="9d6c1-113">SEC_CRYPTOPROVE_METHOD_CANNOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="9d6c1-113">SEC_CRYPTOPROVE_METHOD_CANNOT_FOUND</span></span>|  
|<span data-ttu-id="9d6c1-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="9d6c1-114">Message Text</span></span>|<span data-ttu-id="9d6c1-115">Eine oder mehrere Methoden können nicht in der Kryptografieanbieterbibliothek gefunden werden ‚%.\*ls’.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-115">One or more methods cannot be found in cryptographic provider library '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9d6c1-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="9d6c1-116">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9d6c1-117">konnte den in der Fehlermeldung aufgelisteten Kryptografieanbieter nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-117">was unable to use the cryptographic provider listed in the error message.</span></span> <span data-ttu-id="9d6c1-118">Der Kryptografieanbieter hat eine erforderliche Methode nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-118">The cryptographic provider did not support a required method.</span></span> <span data-ttu-id="9d6c1-119">Der Status des Fehlers gibt an, welche Methode nicht gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-119">The state of the error indicates which method was not found.</span></span>  
  
|<span data-ttu-id="9d6c1-120">State</span><span class="sxs-lookup"><span data-stu-id="9d6c1-120">State</span></span>|<span data-ttu-id="9d6c1-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9d6c1-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9d6c1-122">1</span><span class="sxs-lookup"><span data-stu-id="9d6c1-122">1</span></span>|<span data-ttu-id="9d6c1-123">SqlCryptInitializeProvider</span><span class="sxs-lookup"><span data-stu-id="9d6c1-123">SqlCryptInitializeProvider</span></span>|  
|<span data-ttu-id="9d6c1-124">2</span><span class="sxs-lookup"><span data-stu-id="9d6c1-124">2</span></span>|<span data-ttu-id="9d6c1-125">SqlCryptFreeProvider</span><span class="sxs-lookup"><span data-stu-id="9d6c1-125">SqlCryptFreeProvider</span></span>|  
|<span data-ttu-id="9d6c1-126">3</span><span class="sxs-lookup"><span data-stu-id="9d6c1-126">3</span></span>|<span data-ttu-id="9d6c1-127">SqlCryptOpenSession</span><span class="sxs-lookup"><span data-stu-id="9d6c1-127">SqlCryptOpenSession</span></span>|  
|<span data-ttu-id="9d6c1-128">4</span><span class="sxs-lookup"><span data-stu-id="9d6c1-128">4</span></span>|<span data-ttu-id="9d6c1-129">SqlCryptCloseSession</span><span class="sxs-lookup"><span data-stu-id="9d6c1-129">SqlCryptCloseSession</span></span>|  
|<span data-ttu-id="9d6c1-130">5</span><span class="sxs-lookup"><span data-stu-id="9d6c1-130">5</span></span>|<span data-ttu-id="9d6c1-131">SqlCryptGetProviderInfo</span><span class="sxs-lookup"><span data-stu-id="9d6c1-131">SqlCryptGetProviderInfo</span></span>|  
|<span data-ttu-id="9d6c1-132">6</span><span class="sxs-lookup"><span data-stu-id="9d6c1-132">6</span></span>|<span data-ttu-id="9d6c1-133">SqlCryptGetNextAlgorithmId</span><span class="sxs-lookup"><span data-stu-id="9d6c1-133">SqlCryptGetNextAlgorithmId</span></span>|  
|<span data-ttu-id="9d6c1-134">7</span><span class="sxs-lookup"><span data-stu-id="9d6c1-134">7</span></span>|<span data-ttu-id="9d6c1-135">SqlCryptGetAlgorithmInfo</span><span class="sxs-lookup"><span data-stu-id="9d6c1-135">SqlCryptGetAlgorithmInfo</span></span>|  
|<span data-ttu-id="9d6c1-136">8</span><span class="sxs-lookup"><span data-stu-id="9d6c1-136">8</span></span>|<span data-ttu-id="9d6c1-137">SqlCryptCreateKey</span><span class="sxs-lookup"><span data-stu-id="9d6c1-137">SqlCryptCreateKey</span></span>|  
|<span data-ttu-id="9d6c1-138">9</span><span class="sxs-lookup"><span data-stu-id="9d6c1-138">9</span></span>|<span data-ttu-id="9d6c1-139">SqlCryptDropKey</span><span class="sxs-lookup"><span data-stu-id="9d6c1-139">SqlCryptDropKey</span></span>|  
|<span data-ttu-id="9d6c1-140">10</span><span class="sxs-lookup"><span data-stu-id="9d6c1-140">10</span></span>|<span data-ttu-id="9d6c1-141">SqlCryptGetNextKeyId</span><span class="sxs-lookup"><span data-stu-id="9d6c1-141">SqlCryptGetNextKeyId</span></span>|  
|<span data-ttu-id="9d6c1-142">11</span><span class="sxs-lookup"><span data-stu-id="9d6c1-142">11</span></span>|<span data-ttu-id="9d6c1-143">SqlCryptGetKeyInfoByKeyId</span><span class="sxs-lookup"><span data-stu-id="9d6c1-143">SqlCryptGetKeyInfoByKeyId</span></span>|  
|<span data-ttu-id="9d6c1-144">12</span><span class="sxs-lookup"><span data-stu-id="9d6c1-144">12</span></span>|<span data-ttu-id="9d6c1-145">SqlCryptGetKeyInfoByThumb</span><span class="sxs-lookup"><span data-stu-id="9d6c1-145">SqlCryptGetKeyInfoByThumb</span></span>|  
|<span data-ttu-id="9d6c1-146">13</span><span class="sxs-lookup"><span data-stu-id="9d6c1-146">13</span></span>|<span data-ttu-id="9d6c1-147">SqlCryptGetKeyInfoByName</span><span class="sxs-lookup"><span data-stu-id="9d6c1-147">SqlCryptGetKeyInfoByName</span></span>|  
|<span data-ttu-id="9d6c1-148">14</span><span class="sxs-lookup"><span data-stu-id="9d6c1-148">14</span></span>|<span data-ttu-id="9d6c1-149">SqlCryptExportKey</span><span class="sxs-lookup"><span data-stu-id="9d6c1-149">SqlCryptExportKey</span></span>|  
|<span data-ttu-id="9d6c1-150">15</span><span class="sxs-lookup"><span data-stu-id="9d6c1-150">15</span></span>|<span data-ttu-id="9d6c1-151">SqlCryptImportKey</span><span class="sxs-lookup"><span data-stu-id="9d6c1-151">SqlCryptImportKey</span></span>|  
|<span data-ttu-id="9d6c1-152">16</span><span class="sxs-lookup"><span data-stu-id="9d6c1-152">16</span></span>|<span data-ttu-id="9d6c1-153">SqlCryptEncrypt</span><span class="sxs-lookup"><span data-stu-id="9d6c1-153">SqlCryptEncrypt</span></span>|  
|<span data-ttu-id="9d6c1-154">17</span><span class="sxs-lookup"><span data-stu-id="9d6c1-154">17</span></span>|<span data-ttu-id="9d6c1-155">SqlCryptDecrypt</span><span class="sxs-lookup"><span data-stu-id="9d6c1-155">SqlCryptDecrypt</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="9d6c1-156">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="9d6c1-156">User Action</span></span>  
 <span data-ttu-id="9d6c1-157">Wenden Sie sich an den Kryptografieanbieter, um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-157">Contact the cryptographic provider for more information.</span></span>  
  
  
