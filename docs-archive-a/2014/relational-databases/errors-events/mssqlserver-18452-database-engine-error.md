---
title: MSSQLSERVER_18452 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 18456 (Database Engine error)
- 18452 (Database Engine error)
ms.assetid: 21da332c-e81d-4dee-a9d2-95598911b3be
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5786d5de4748f6bbf59d2bd4acecd7ca77977f11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619146"
---
# <a name="mssqlserver_18452"></a><span data-ttu-id="dfc3c-102">MSSQLSERVER_18452</span><span class="sxs-lookup"><span data-stu-id="dfc3c-102">MSSQLSERVER_18452</span></span>
    
## <a name="details"></a><span data-ttu-id="dfc3c-103">Details</span><span class="sxs-lookup"><span data-stu-id="dfc3c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dfc3c-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="dfc3c-104">Product Name</span></span>|<span data-ttu-id="dfc3c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="dfc3c-105">SQL Server</span></span>|  
|<span data-ttu-id="dfc3c-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="dfc3c-106">Event ID</span></span>|<span data-ttu-id="dfc3c-107">18452</span><span class="sxs-lookup"><span data-stu-id="dfc3c-107">18452</span></span>|  
|<span data-ttu-id="dfc3c-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="dfc3c-108">Event Source</span></span>|<span data-ttu-id="dfc3c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="dfc3c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="dfc3c-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="dfc3c-110">Component</span></span>|<span data-ttu-id="dfc3c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="dfc3c-111">SQLEngine</span></span>|  
|<span data-ttu-id="dfc3c-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="dfc3c-112">Symbolic Name</span></span>|<span data-ttu-id="dfc3c-113">LOGON_INVALID_CONNECT</span><span class="sxs-lookup"><span data-stu-id="dfc3c-113">LOGON_INVALID_CONNECT</span></span>|  
|<span data-ttu-id="dfc3c-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="dfc3c-114">Message Text</span></span>|<span data-ttu-id="dfc3c-115">Fehler bei der Anmeldung für den Benutzer '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="dfc3c-115">Login failed for user '%.\*ls'.</span></span> <span data-ttu-id="dfc3c-116">Die Anmeldung ist eine SQL Server-Anmeldung und kann nicht mit der Windows-Authentifizierung verwendet werden.%.\*ls</span><span class="sxs-lookup"><span data-stu-id="dfc3c-116">The login is a SQL Server login and cannot be used with Windows Authentication.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dfc3c-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="dfc3c-117">Explanation</span></span>  
 <span data-ttu-id="dfc3c-118">Der Benutzer hat versucht, sich mit Anmeldeinformationen anzumelden, die nicht überprüft werden können.</span><span class="sxs-lookup"><span data-stu-id="dfc3c-118">The user attempted to login with credentials that cannot be validated.</span></span> <span data-ttu-id="dfc3c-119">Mögliche Ursachen sind:</span><span class="sxs-lookup"><span data-stu-id="dfc3c-119">Possible causes are:</span></span>  
  
-   <span data-ttu-id="dfc3c-120">Die Anmeldung ist möglicherweise eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Anmeldung, aber der Server akzeptiert nur Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="dfc3c-120">The login may be a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login but the server only accepts Windows Authentication.</span></span>  
  
-   <span data-ttu-id="dfc3c-121">Sie versuchen, eine Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Authentifizierung herzustellen, aber die Anmeldeinformationen sind in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="dfc3c-121">You are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication but the login used does not exist on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="dfc3c-122">Die Anmeldung verwendet möglicherweise die Windows-Authentifizierung, aber die Anmeldung ist ein nicht erkannter Windows-Prinzipal.</span><span class="sxs-lookup"><span data-stu-id="dfc3c-122">The login may use Windows Authentication but the login is an unrecognized Windows principal.</span></span> <span data-ttu-id="dfc3c-123">Ein nicht erkannter Windows-Prinzipal bedeutet, dass die Anmeldung nicht von Windows überprüft werden kann.</span><span class="sxs-lookup"><span data-stu-id="dfc3c-123">An unrecognized Windows principal means that the login cannot be verified by Windows.</span></span> <span data-ttu-id="dfc3c-124">Das konnte daran liegen, dass die Windows-Anmeldung von einer nicht vertrauenswürdigen Domäne stammt.</span><span class="sxs-lookup"><span data-stu-id="dfc3c-124">This could be because the Windows login is from an untrusted domain.</span></span>  
  
 <span data-ttu-id="dfc3c-125">Ähnliche Probleme können den weniger spezifischen Fehler 18456 verursachen.</span><span class="sxs-lookup"><span data-stu-id="dfc3c-125">Similar problems can cause the less-specific error 18456.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dfc3c-126">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="dfc3c-126">User Action</span></span>  
 <span data-ttu-id="dfc3c-127">Wenn Sie versuchen, eine Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Authentifizierung herzustellen, überprüfen Sie, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] im gemischten Authentifizierungsmodus konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="dfc3c-127">If you are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, verify that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured in Mixed Authentication Mode.</span></span>  
  
 <span data-ttu-id="dfc3c-128">Wenn Sie versuchen, eine Verbindung mit der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Authentifizierung herzustellen, überprüfen Sie, dass die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Anmeldeinformationen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="dfc3c-128">If you are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, verify that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login exists.</span></span>  
  
 <span data-ttu-id="dfc3c-129">Wenn Sie versuchen, eine Verbindung mit Windows-Authentifizierung herzustellen, überprüfen Sie, dass Sie ordnungsgemäß bei der richtigen Domäne angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="dfc3c-129">If you are trying to connect using Windows Authentication, verify that you are properly logged into the correct domain.</span></span>  
  
  
