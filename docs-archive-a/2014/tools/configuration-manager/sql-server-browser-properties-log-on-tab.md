---
title: Eigenschaften von SQL Server-Browser (Registerkarte „Anmelden“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: c77871ec-c2f4-4e4a-9a10-5aeb4ae70507
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0c1f7d0cfd9e9b05a2a04f3c3e9efba687522298
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695058"
---
# <a name="sql-server-browser-properties-log-on-tab"></a><span data-ttu-id="14717-102">Eigenschaften von SQL Server-Browser (Registerkarte Anmelden)</span><span class="sxs-lookup"><span data-stu-id="14717-102">SQL Server Browser Properties (Log On Tab)</span></span>
  <span data-ttu-id="14717-103">Das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Browser-Programm wird als Dienst auf dem Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="14717-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser program runs as a service on the server.</span></span> <span data-ttu-id="14717-104">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Browser lauscht auf eingehende Anforderungen für [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Ressourcen und stellt Informationen zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanzen zur Verfügung, die auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="14717-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser listens for incoming requests for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources and provides information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="14717-105">-Browser lauscht an einem UDP-Port. Nicht authentifizierte Anforderungen werden mithilfe von SSRP ( [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Resolution Protocol) akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="14717-105">Browser listens on a UDP port and accepts unauthenticated requests using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Resolution Protocol (SSRP).</span></span>  
  
 <span data-ttu-id="14717-106">Das Ändern eines Kennworts für ein Konto wird sofort wirksam. Es ist kein Neustart des Dienstes erforderlich.</span><span class="sxs-lookup"><span data-stu-id="14717-106">Changing the password of an account takes effect immediately without restarting the service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="14717-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="14717-107">Options</span></span>  
 <span data-ttu-id="14717-108">**Lokales System**</span><span class="sxs-lookup"><span data-stu-id="14717-108">**Local System account**</span></span>  
 <span data-ttu-id="14717-109">Führen Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Browser-Dienst im Sicherheitskontext des lokalen Systemkontos aus.</span><span class="sxs-lookup"><span data-stu-id="14717-109">Run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service in the security context of the Local System account.</span></span> <span data-ttu-id="14717-110">Verwenden Sie nach Möglichkeit ein Konto mit geringen Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="14717-110">When possible, use a low-permission account instead.</span></span>  
  
 <span data-ttu-id="14717-111">**Dieses Konto**</span><span class="sxs-lookup"><span data-stu-id="14717-111">**This account**</span></span>  
 <span data-ttu-id="14717-112">Geben Sie ein lokales oder ein Domänenbenutzerkonto an, das die Windows-Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="14717-112">Specify a local or domain user account that uses Windows Authentication.</span></span> <span data-ttu-id="14717-113">Das Verwenden eines Domänenbenutzerkontos mit minimalen Berechtigungen für Dienste wird empfohlen.</span><span class="sxs-lookup"><span data-stu-id="14717-113">We recommend using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="14717-114">Informationen zum Auswählen eines Kontos finden Sie unter "Einrichten von Windows-Dienstkonten" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="14717-114">For information about selecting an account, see "Setting Up Windows Service Accounts" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="14717-115">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="14717-115">**Browse**</span></span>  
 <span data-ttu-id="14717-116">Suchen Sie nach einem Benutzer oder einem integriertem Sicherheitsprinzipal.</span><span class="sxs-lookup"><span data-stu-id="14717-116">Browse for a user or built-in security principal.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="14717-117">Verwenden Sie ein Konto mit geringen Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="14717-117">Use a low-permission account.</span></span> <span data-ttu-id="14717-118">Informationen zu den Berechtigungen, die für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Browserdienst erforderlich sind, finden Sie im Abschnitt „Sicherheit“ von [SQL Server-Browserdienst](../../../2014/tools/configuration-manager/sql-server-browser-service.md).</span><span class="sxs-lookup"><span data-stu-id="14717-118">For information about the permissions required for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser Service, see the Security section of [SQL Server Browser Service](../../../2014/tools/configuration-manager/sql-server-browser-service.md).</span></span>  
  
 <span data-ttu-id="14717-119">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="14717-119">**Password**</span></span>  
 <span data-ttu-id="14717-120">Geben Sie das Kennwort des Sicherheitsprinzipals ein.</span><span class="sxs-lookup"><span data-stu-id="14717-120">Enter the password of the security principal.</span></span>  
  
 <span data-ttu-id="14717-121">**Kennwort bestätigen**</span><span class="sxs-lookup"><span data-stu-id="14717-121">**Confirm password**</span></span>  
 <span data-ttu-id="14717-122">Bestätigen Sie das Kennwort des Sicherheitsprinzipals.</span><span class="sxs-lookup"><span data-stu-id="14717-122">Confirm the password of the security principal.</span></span>  
  
 <span data-ttu-id="14717-123">**Dienststatus**</span><span class="sxs-lookup"><span data-stu-id="14717-123">**Service status**</span></span>  
 <span data-ttu-id="14717-124">Zeigt an, ob dieser Dienst ausgeführt wird, angehalten oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="14717-124">Indicates whether this service is running, stopped, or disabled.</span></span> <span data-ttu-id="14717-125">„ **…** “ gibt einen ausstehenden Statuswechsel an.</span><span class="sxs-lookup"><span data-stu-id="14717-125">"**...**" indicates a state change is pending.</span></span>  
  
 <span data-ttu-id="14717-126">**Starten**</span><span class="sxs-lookup"><span data-stu-id="14717-126">**Start**</span></span>  
 <span data-ttu-id="14717-127">Starten Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Browserdienst.</span><span class="sxs-lookup"><span data-stu-id="14717-127">Start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
 <span data-ttu-id="14717-128">**Beenden**</span><span class="sxs-lookup"><span data-stu-id="14717-128">**Stop**</span></span>  
 <span data-ttu-id="14717-129">Beenden Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Browserdienst.</span><span class="sxs-lookup"><span data-stu-id="14717-129">Stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
 <span data-ttu-id="14717-130">**Anhalten**</span><span class="sxs-lookup"><span data-stu-id="14717-130">**Pause**</span></span>  
 <span data-ttu-id="14717-131">Halten Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Browser-Dienst an.</span><span class="sxs-lookup"><span data-stu-id="14717-131">Pause the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
 <span data-ttu-id="14717-132">**Fortsetzen**</span><span class="sxs-lookup"><span data-stu-id="14717-132">**Resume**</span></span>  
 <span data-ttu-id="14717-133">Setzen Sie die Ausführung eines angehaltenen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Browserdiensts fort.</span><span class="sxs-lookup"><span data-stu-id="14717-133">Resume a paused [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14717-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="14717-134">See Also</span></span>  
 [<span data-ttu-id="14717-135">SQL Server-Browserdienst</span><span class="sxs-lookup"><span data-stu-id="14717-135">SQL Server Browser Service</span></span>](../../../2014/tools/configuration-manager/sql-server-browser-service.md)  
  
  
