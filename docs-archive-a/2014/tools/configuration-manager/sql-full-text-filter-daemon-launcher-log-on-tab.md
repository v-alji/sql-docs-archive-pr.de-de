---
title: Startprogramm für SQL-Volltextfilterdaemon (Registerkarte „Anmelden“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 13e260f9-a75f-430b-88a3-959ddcead8fe
author: stevestein
ms.author: sstein
ms.openlocfilehash: cb3f23907e96214929617bf2923e46148c0ab1f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621763"
---
# <a name="sql-full-text-filter-daemon-launcher-log-on-tab"></a><span data-ttu-id="399dc-102">Startprogramm für SQL-Volltextfilterdaemon (Registerkarte Anmelden)</span><span class="sxs-lookup"><span data-stu-id="399dc-102">SQL Full-text Filter Daemon Launcher (Log On Tab)</span></span>
  <span data-ttu-id="399dc-103">Ab [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]wird der Dienst SQL-Volltextfilterdaemon (FDHOST-Startprogramm) von der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Volltextsuche verwendet.</span><span class="sxs-lookup"><span data-stu-id="399dc-103">Beginning in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], the SQL Full-text Filter Daemon Launcher (FDHOST Launcher) service is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] full-text search.</span></span> <span data-ttu-id="399dc-104">Dieser Dienst muss ausgeführt werden, wenn Sie die Volltextsuche verwenden.</span><span class="sxs-lookup"><span data-stu-id="399dc-104">This service must be running if you use full-text search.</span></span> <span data-ttu-id="399dc-105">Informationen über die Prozesse des Filterdaemonhosts finden Sie unter "Architektur der Volltextsuche" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="399dc-105">For information about the filter daemon host processes, see "Full-Text Search Architecture" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="399dc-106">Verwenden Sie im Dialogfeld **Eigenschaften von Startprogramm für SQL-Volltextfilterdaemon** die Registerkarte **Anmelden** , um das vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Volltextdienst verwendete Konto anzugeben, das Kennwort des Kontos zu ändern sowie den Dienst zu starten und zu beenden.</span><span class="sxs-lookup"><span data-stu-id="399dc-106">Use the **Log On** tab of the **SQL Full-text Filter Daemon Launcher  Properties** dialog box to specify the account used by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] full-text service, to change the password of an account, and to start and stop the service.</span></span> <span data-ttu-id="399dc-107">Das Ändern eines Kennworts für ein Konto wird nach einem Neustart des Diensts wirksam.</span><span class="sxs-lookup"><span data-stu-id="399dc-107">Changing the password of an account takes affect after restarting the service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="399dc-108">Beim Ändern des Kontonamens, der von einem Dienst auf einer gruppierten Instanz verwendet wird, muss das neue Konto Mitglied der Domänengruppe sein, die während des Setups für den zu ändernden Dienst angegeben wird, oder Sie müssen die Berechtigung zum Hinzufügen von Mitgliedern zu dieser Gruppe besitzen.</span><span class="sxs-lookup"><span data-stu-id="399dc-108">When changing the account name used by a service on a clustered instance, either the new account must be a member of the domain group specified during setup for the service, or you must have permission to add members to that group.</span></span> <span data-ttu-id="399dc-109">Wenden Sie sich an Ihren Domänenadministrator, falls Sie keine Berechtigung zum Ändern der Gruppenmitgliedschaft haben.</span><span class="sxs-lookup"><span data-stu-id="399dc-109">If you do not have permission to modify group membership, contact the domain administrator.</span></span>  
>   
>  <span data-ttu-id="399dc-110">Weitere Informationen über das Auswählen eines Kontos zum Ausführen des Dienstes finden Sie unter "Einrichten von Windows-Dienstkonten" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="399dc-110">For more information about selecting an account to run the service, see "Setting Up Windows Service Accounts" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="options"></a><span data-ttu-id="399dc-111">Tastatur</span><span class="sxs-lookup"><span data-stu-id="399dc-111">Options</span></span>  
 <span data-ttu-id="399dc-112">**Integriertes Konto**</span><span class="sxs-lookup"><span data-stu-id="399dc-112">**Built-in account**</span></span>  
 <span data-ttu-id="399dc-113">**Lokales System**</span><span class="sxs-lookup"><span data-stu-id="399dc-113">**Local System**</span></span>  
 <span data-ttu-id="399dc-114">Geben Sie das lokale Systemkonto an.</span><span class="sxs-lookup"><span data-stu-id="399dc-114">Specify the local system account.</span></span> <span data-ttu-id="399dc-115">Dieses Konto erfordert kein Kennwort.</span><span class="sxs-lookup"><span data-stu-id="399dc-115">This account does not require a password.</span></span> <span data-ttu-id="399dc-116">Das lokale Systemkonto kann die Zusammenarbeit mit anderen Servern verhindern. Dies hängt von den Privilegien ab, die dem Konto erteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="399dc-116">However, the local system account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="399dc-117">**Lokaler Dienst**</span><span class="sxs-lookup"><span data-stu-id="399dc-117">**Local Service**</span></span>  
 <span data-ttu-id="399dc-118">Geben Sie das lokale Dienstkonto an.</span><span class="sxs-lookup"><span data-stu-id="399dc-118">Specify the local service account.</span></span> <span data-ttu-id="399dc-119">Dieses Konto erfordert kein Kennwort.</span><span class="sxs-lookup"><span data-stu-id="399dc-119">This account does not require a password.</span></span> <span data-ttu-id="399dc-120">Das lokale Dienstkonto kann die Zusammenarbeit mit anderen Servern verhindern. Dies hängt von den Privilegien ab, die dem Konto erteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="399dc-120">However, the local service account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="399dc-121">**Netzwerkdienst**</span><span class="sxs-lookup"><span data-stu-id="399dc-121">**Network Service**</span></span>  
 <span data-ttu-id="399dc-122">Für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] - oder die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienste empfiehlt sich die Verwendung des Netzwerkdienstkontos.</span><span class="sxs-lookup"><span data-stu-id="399dc-122">We recommend that you do not use the Network Service account for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent services.</span></span> <span data-ttu-id="399dc-123">Lokale Benutzerkonten oder Domänenbenutzerkonten sind für die Dienste besser geeignet.</span><span class="sxs-lookup"><span data-stu-id="399dc-123">Local User or Domain User accounts are more appropriate for these services.</span></span>  
  
 <span data-ttu-id="399dc-124">**Dieses Konto**</span><span class="sxs-lookup"><span data-stu-id="399dc-124">**This account**</span></span>  
 <span data-ttu-id="399dc-125">Geben Sie ein lokales oder ein Domänenbenutzerkonto an, das die Windows-Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="399dc-125">Specify a local or domain user account that uses Windows Authentication.</span></span> <span data-ttu-id="399dc-126">Das Verwenden eines Domänenbenutzerkontos mit minimalen Berechtigungen für Dienste wird empfohlen.</span><span class="sxs-lookup"><span data-stu-id="399dc-126">We recommend that you use a domain user account that has minimal rights for services.</span></span>  
  
 <span data-ttu-id="399dc-127">**Kontoname**</span><span class="sxs-lookup"><span data-stu-id="399dc-127">**Account Name**</span></span>  
 <span data-ttu-id="399dc-128">Geben Sie den Kontonamen des lokalen oder Domänenbenutzers an.</span><span class="sxs-lookup"><span data-stu-id="399dc-128">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="399dc-129">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="399dc-129">**Password**</span></span>  
 <span data-ttu-id="399dc-130">Geben Sie das Kennwort des Kontos ein.</span><span class="sxs-lookup"><span data-stu-id="399dc-130">Type the password of the account.</span></span>  
  
 <span data-ttu-id="399dc-131">**Kennwort bestätigen**</span><span class="sxs-lookup"><span data-stu-id="399dc-131">**Confirm password**</span></span>  
 <span data-ttu-id="399dc-132">Geben Sie das Kennwort des Kontos erneut ein.</span><span class="sxs-lookup"><span data-stu-id="399dc-132">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="399dc-133">**Starten**</span><span class="sxs-lookup"><span data-stu-id="399dc-133">**Start**</span></span>  
 <span data-ttu-id="399dc-134">Starten Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="399dc-134">Start the service.</span></span>  
  
 <span data-ttu-id="399dc-135">**Beenden**</span><span class="sxs-lookup"><span data-stu-id="399dc-135">**Stop**</span></span>  
 <span data-ttu-id="399dc-136">Beenden Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="399dc-136">Stop the service.</span></span>  
  
 <span data-ttu-id="399dc-137">**Anhalten**</span><span class="sxs-lookup"><span data-stu-id="399dc-137">**Pause**</span></span>  
 <span data-ttu-id="399dc-138">Halten Sie den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="399dc-138">Pause the service.</span></span> <span data-ttu-id="399dc-139">Für diesen Dienst nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="399dc-139">Not available for this service.</span></span>  
  
 <span data-ttu-id="399dc-140">**Fortsetzen**</span><span class="sxs-lookup"><span data-stu-id="399dc-140">**Resume**</span></span>  
 <span data-ttu-id="399dc-141">Setzen Sie einen angehaltenen Dienst fort.</span><span class="sxs-lookup"><span data-stu-id="399dc-141">Resume a paused service.</span></span>  
  
  
