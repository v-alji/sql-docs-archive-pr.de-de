---
title: WMI-Fehler 0x8007052f | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- 0x8007052f (WMI error)
ms.assetid: a33f12bd-15c4-42a8-b343-de44c3e87729
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d6e857e0ccaad9b6f34bbdc9b88aea2e6d7291d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726797"
---
# <a name="wmi-error-0x8007052f"></a><span data-ttu-id="2580e-102">WMI-Fehler 0x8007052f</span><span class="sxs-lookup"><span data-stu-id="2580e-102">WMI Error 0x8007052f</span></span>
    
## <a name="details"></a><span data-ttu-id="2580e-103">Details</span><span class="sxs-lookup"><span data-stu-id="2580e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2580e-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="2580e-104">Product Name</span></span>|<span data-ttu-id="2580e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2580e-105">SQL Server</span></span>|  
|<span data-ttu-id="2580e-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2580e-106">Event ID</span></span>|<span data-ttu-id="2580e-107">0x8007052f</span><span class="sxs-lookup"><span data-stu-id="2580e-107">0x8007052f</span></span>|  
|<span data-ttu-id="2580e-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="2580e-108">Event Source</span></span>|<span data-ttu-id="2580e-109">WMI-Anbieterfehler</span><span class="sxs-lookup"><span data-stu-id="2580e-109">WMI Provider Error</span></span>|  
|<span data-ttu-id="2580e-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="2580e-110">Component</span></span>|<span data-ttu-id="2580e-111">SQL Server-Konfigurations-Manager</span><span class="sxs-lookup"><span data-stu-id="2580e-111">SQL Server Configuration Manager</span></span>|  
|<span data-ttu-id="2580e-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="2580e-112">Symbolic Name</span></span>|<span data-ttu-id="2580e-113">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="2580e-113">NA</span></span>|  
|<span data-ttu-id="2580e-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="2580e-114">Message Text</span></span>|<span data-ttu-id="2580e-115">Anmeldefehler: Eingeschränktes Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="2580e-115">Logon failure: user account restriction.</span></span> <span data-ttu-id="2580e-116">Mögliche Ursachen hierfür sind, dass leere Kennwörter nicht zulässig sind, Einschränkungen der Anmeldezeiten vorliegen oder eine Richtlinieneinschränkung erzwungen wurde.</span><span class="sxs-lookup"><span data-stu-id="2580e-116">Possible reasons are blank passwords not allowed, login hour restrictions, or a policy restriction has been enforced.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2580e-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="2580e-117">Explanation</span></span>  
 <span data-ttu-id="2580e-118">Dieser Fehler kann auftreten, wenn der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Konfigurations-Manager verwendet wird, um zu den integrierten Konten zu wechseln (Netzwerkdienst, Lokaler Dienst oder Lokales System), während [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] auf einem Windows Server 2003-Cluster oder einem Windows Server-Domänencontroller ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2580e-118">This error can occur when using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager to switch to the built-in accounts (Network Service, Local Service, or Local System) when [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is running on a Windows Server Cluster or Windows Server Domain Controller.</span></span> <span data-ttu-id="2580e-119">Führen Sie Dienste auf einem Windows Server-Cluster oder einem Windows Server-Domänencontroller nicht unter integrierten Konten aus.</span><span class="sxs-lookup"><span data-stu-id="2580e-119">Do not run services under built-in accounts on a Windows Server Cluster or Windows Server Domain Controller.</span></span> <span data-ttu-id="2580e-120">Empfehlungen zu Dienstkonten finden Sie unter "Einrichten von Windows-Dienstkonten" in der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="2580e-120">For recommendations on service accounts, see the topic Setting Up Windows Service Accounts in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2580e-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="2580e-121">User Action</span></span>  
 <span data-ttu-id="2580e-122">Konfigurieren Sie [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] für die Verwendung eines Domänenkontos.</span><span class="sxs-lookup"><span data-stu-id="2580e-122">Configure [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to use a domain account.</span></span>  
  
  
