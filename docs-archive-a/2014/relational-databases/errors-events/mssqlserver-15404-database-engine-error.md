---
title: MSSQLSERVER_15404 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 15404 (Database Engine error)
ms.assetid: 69677f02-bc81-4e4a-99b8-5c1bd1de36df
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: beb854c866256728574e06f8c9efb50fb354e15a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620947"
---
# <a name="mssqlserver_15404"></a><span data-ttu-id="0bdee-102">MSSQLSERVER_15404</span><span class="sxs-lookup"><span data-stu-id="0bdee-102">MSSQLSERVER_15404</span></span>
    
## <a name="details"></a><span data-ttu-id="0bdee-103">Details</span><span class="sxs-lookup"><span data-stu-id="0bdee-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0bdee-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="0bdee-104">Product Name</span></span>|<span data-ttu-id="0bdee-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0bdee-105">SQL Server</span></span>|  
|<span data-ttu-id="0bdee-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="0bdee-106">Event ID</span></span>|<span data-ttu-id="0bdee-107">15404</span><span class="sxs-lookup"><span data-stu-id="0bdee-107">15404</span></span>|  
|<span data-ttu-id="0bdee-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="0bdee-108">Event Source</span></span>|<span data-ttu-id="0bdee-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0bdee-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0bdee-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="0bdee-110">Component</span></span>|<span data-ttu-id="0bdee-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0bdee-111">SQLEngine</span></span>|  
|<span data-ttu-id="0bdee-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="0bdee-112">Symbolic Name</span></span>|<span data-ttu-id="0bdee-113">SEC_NTGRP_ERROR</span><span class="sxs-lookup"><span data-stu-id="0bdee-113">SEC_NTGRP_ERROR</span></span>|  
|<span data-ttu-id="0bdee-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="0bdee-114">Message Text</span></span>|<span data-ttu-id="0bdee-115">Die Informationen über Windows NT-Gruppe oder -Benutzer *user*, Fehlercode *code* konnten nicht abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0bdee-115">Could not obtain information about Windows NT group/user '*user*', error code *code*.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0bdee-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="0bdee-116">Explanation</span></span>  
 <span data-ttu-id="0bdee-117">Wenn ein ungültiger Prinzipal angegeben wird, wird 15404 bei der Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="0bdee-117">15404 is used in authentication when an invalid principal is specified.</span></span> <span data-ttu-id="0bdee-118">Oder der Identitätswechsel eines Windows-Kontos schlägt fehl, weil keine vollständige Vertrauensstellung zwischen dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienstkonto und der Domäne des Windows-Kontos besteht.</span><span class="sxs-lookup"><span data-stu-id="0bdee-118">Or, impersonation of a Windows account fails because there is no full trust relationship between the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and the domain of the Windows account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0bdee-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="0bdee-119">User Action</span></span>  
 <span data-ttu-id="0bdee-120">Überprüfen Sie, ob der Windows-Prinzipal vorhanden und nicht falsch geschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="0bdee-120">Check that the Windows principal exists and is not misspelled.</span></span>  
  
 <span data-ttu-id="0bdee-121">Wenn dieser Fehler aus einer fehlenden vollständigen Vertrauensstellung zwischen dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienstkonto und der Domäne des Windows-Kontos resultiert, kann er durch eine der folgenden Aktionen behoben werden:</span><span class="sxs-lookup"><span data-stu-id="0bdee-121">If this error is the result of a lack of a full trust relationship between the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and the domain of the Windows account, one of the following actions can resolve the error:</span></span>  
  
-   <span data-ttu-id="0bdee-122">Verwenden Sie für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienst ein Konto, das aus derselben Domäne wie der Windows-Benutzer stammt.</span><span class="sxs-lookup"><span data-stu-id="0bdee-122">Use an account from the same domain as the Windows user for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
-   <span data-ttu-id="0bdee-123">Wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ein Computerkonto wie Netzwerkdienst oder Lokales System verwendet, muss der Computer von der Domäne, in der der Windows-Benutzer enthalten ist, als vertrauenswürdig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="0bdee-123">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is using a machine account such as Network Service or Local System, the machine must be trusted by the domain containing the Windows User.</span></span>  
  
-   <span data-ttu-id="0bdee-124">Verwenden Sie ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Konto.</span><span class="sxs-lookup"><span data-stu-id="0bdee-124">Use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
  
