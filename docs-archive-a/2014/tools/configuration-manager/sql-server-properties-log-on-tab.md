---
title: Eigenschaften von SQL Server (Registerkarte „Anmelden“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 405073fc-eaa3-43c6-bf82-2cd58cacc1c3
author: stevestein
ms.author: sstein
ms.openlocfilehash: adec9ed7c69023218baa96ab8f8edbb6f2b365bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618409"
---
# <a name="sql-server-properties-log-on-tab"></a><span data-ttu-id="8e0b9-102">SQL Server-Eigenschaften (Registerkarte Anmelden)</span><span class="sxs-lookup"><span data-stu-id="8e0b9-102">SQL Server Properties (Log On Tab)</span></span>
  <span data-ttu-id="8e0b9-103">Verwenden Sie im Dialogfeld **Eigenschaften von SQL Server** die Registerkarte **Anmelden** , um das vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst verwendete Konto anzugeben, das Kennwort des Kontos zu ändern sowie den Dienst zu starten und zu beenden.</span><span class="sxs-lookup"><span data-stu-id="8e0b9-103">Use the **Log On** tab of the **SQL Server Properties** dialog box to specify the account used by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service, to change the password of an account, and to start and stop the service.</span></span> <span data-ttu-id="8e0b9-104">Die Kennwortänderung eines Kontos wird sofort wirksam.</span><span class="sxs-lookup"><span data-stu-id="8e0b9-104">Changing the password of an account takes effect immediately.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e0b9-105">Beim Ändern des Kontonamens, der von einem Dienst auf einer gruppierten Instanz verwendet wird, muss das neue Konto Mitglied der Domänengruppe sein, die während des Setups für den zu ändernden Dienst angegeben wird. Andernfalls müssen Sie die Berechtigung zum Hinzufügen von Mitgliedern zu dieser Gruppe besitzen.</span><span class="sxs-lookup"><span data-stu-id="8e0b9-105">When changing the account name used by a service on a clustered instance, the new account must be a member of the domain group specified during setup for the service being changed, or you must have permission to add members to that group.</span></span> <span data-ttu-id="8e0b9-106">Wenden Sie sich an Ihren Domänenadministrator, falls Sie keine Berechtigung zum Ändern der Gruppenmitgliedschaft haben.</span><span class="sxs-lookup"><span data-stu-id="8e0b9-106">If you do not have permission to modify group membership, contact the domain administrator.</span></span>  
>   
>  <span data-ttu-id="8e0b9-107">Weitere Informationen über das Auswählen eines Kontos zum Ausführen des Dienstes finden Sie unter "Einrichten von Windows-Dienstkonten" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="8e0b9-107">For more information about selecting an account to run the service, see "Setting Up Windows Service Accounts" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8e0b9-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="8e0b9-108">Options</span></span>  
 <span data-ttu-id="8e0b9-109">**Integriertes Konto**</span><span class="sxs-lookup"><span data-stu-id="8e0b9-109">**Built-in account**</span></span>  
 <span data-ttu-id="8e0b9-110">**Lokales System**</span><span class="sxs-lookup"><span data-stu-id="8e0b9-110">**Local System**</span></span>  
 -   <span data-ttu-id="8e0b9-111">Geben Sie das lokale Systemkonto an.</span><span class="sxs-lookup"><span data-stu-id="8e0b9-111">Specify the local system account.</span></span> <span data-ttu-id="8e0b9-112">Dieses Konto erfordert kein Kennwort.</span><span class="sxs-lookup"><span data-stu-id="8e0b9-112">This account does not require a password.</span></span> <span data-ttu-id="8e0b9-113">Das lokale Systemkonto kann die Zusammenarbeit mit anderen Servern verhindern. Dies hängt von den Privilegien ab, die dem Konto erteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="8e0b9-113">However, the local system account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="8e0b9-114">**Lokaler Dienst**</span><span class="sxs-lookup"><span data-stu-id="8e0b9-114">**Local Service**</span></span>  
 -   <span data-ttu-id="8e0b9-115">Geben Sie das lokale Dienstkonto an.</span><span class="sxs-lookup"><span data-stu-id="8e0b9-115">Specify the local service account.</span></span> <span data-ttu-id="8e0b9-116">Dieses Konto erfordert kein Kennwort.</span><span class="sxs-lookup"><span data-stu-id="8e0b9-116">This account does not require a password.</span></span> <span data-ttu-id="8e0b9-117">Das lokale Dienstkonto kann die Zusammenarbeit mit anderen Servern verhindern. Dies hängt von den Privilegien ab, die dem Konto erteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="8e0b9-117">However, the local service account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="8e0b9-118">**Netzwerkdienst**</span><span class="sxs-lookup"><span data-stu-id="8e0b9-118">**Network Service**</span></span>  
 -   <span data-ttu-id="8e0b9-119">Für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] - oder den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst empfiehlt sich die Verwendung des Netzwerkdienstkontos.</span><span class="sxs-lookup"><span data-stu-id="8e0b9-119">We recommend that you do not use the Network Service account for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent services.</span></span> <span data-ttu-id="8e0b9-120">Lokale Benutzerkonten oder Domänenbenutzerkonten sind für die Dienste besser geeignet.</span><span class="sxs-lookup"><span data-stu-id="8e0b9-120">Local User or Domain User accounts are more appropriate for these services.</span></span>  
  
 <span data-ttu-id="8e0b9-121">**Dieses Konto**</span><span class="sxs-lookup"><span data-stu-id="8e0b9-121">**This account**</span></span>  
 <span data-ttu-id="8e0b9-122">Geben Sie ein lokales oder ein Domänenbenutzerkonto an, das die Windows-Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="8e0b9-122">Specify a local or domain user account that uses Windows Authentication.</span></span> <span data-ttu-id="8e0b9-123">Das Verwenden eines Domänenbenutzerkontos mit minimalen Berechtigungen für Dienste wird empfohlen.</span><span class="sxs-lookup"><span data-stu-id="8e0b9-123">We recommend that you use a domain user account that has minimal rights for services.</span></span>  
  
 <span data-ttu-id="8e0b9-124">**Kontoname**</span><span class="sxs-lookup"><span data-stu-id="8e0b9-124">**Account Name**</span></span>  
 <span data-ttu-id="8e0b9-125">Geben Sie den Kontonamen des lokalen oder Domänenbenutzers an.</span><span class="sxs-lookup"><span data-stu-id="8e0b9-125">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="8e0b9-126">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="8e0b9-126">**Password**</span></span>  
 <span data-ttu-id="8e0b9-127">Geben Sie das Kennwort des Kontos ein.</span><span class="sxs-lookup"><span data-stu-id="8e0b9-127">Type the password of the account.</span></span>  
  
 <span data-ttu-id="8e0b9-128">**Kennwort bestätigen**</span><span class="sxs-lookup"><span data-stu-id="8e0b9-128">**Confirm password**</span></span>  
 <span data-ttu-id="8e0b9-129">Geben Sie das Kennwort des Kontos erneut ein.</span><span class="sxs-lookup"><span data-stu-id="8e0b9-129">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="8e0b9-130">**Starten**</span><span class="sxs-lookup"><span data-stu-id="8e0b9-130">**Start**</span></span>  
 <span data-ttu-id="8e0b9-131">Starten Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="8e0b9-131">Start the service.</span></span>  
  
 <span data-ttu-id="8e0b9-132">**Beenden**</span><span class="sxs-lookup"><span data-stu-id="8e0b9-132">**Stop**</span></span>  
 <span data-ttu-id="8e0b9-133">Beenden Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="8e0b9-133">Stop the service.</span></span>  
  
 <span data-ttu-id="8e0b9-134">**Anhalten**</span><span class="sxs-lookup"><span data-stu-id="8e0b9-134">**Pause**</span></span>  
 <span data-ttu-id="8e0b9-135">Halten Sie den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="8e0b9-135">Pause the service.</span></span>  
  
 <span data-ttu-id="8e0b9-136">**Fortsetzen**</span><span class="sxs-lookup"><span data-stu-id="8e0b9-136">**Resume**</span></span>  
 <span data-ttu-id="8e0b9-137">Setzen Sie einen angehaltenen Dienst fort.</span><span class="sxs-lookup"><span data-stu-id="8e0b9-137">Resume a paused service.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8e0b9-138">Standardmäßig können nur Mitglieder der lokalen Administratorgruppe einen Dienst starten, beenden, anhalten, fortsetzen oder neu starten.</span><span class="sxs-lookup"><span data-stu-id="8e0b9-138">By default, only members of the local administrators group can start, stop, pause, resume or restart a service.</span></span> <span data-ttu-id="8e0b9-139">Informationen dazu, wie Sie es Nichtadministratoren ermöglichen, Dienste zu verwalten, finden Sie unter [How to grant users rights to manage services in Windows Server 2003](https://support.microsoft.com/kb/325349)(So erteilen Sie Benutzern die Berechtigung zum Verwalten von Diensten in Windows Server 2003).</span><span class="sxs-lookup"><span data-stu-id="8e0b9-139">To grant non-administrators the ability to manage services, see [How to grant users rights to manage services in Windows Server 2003](https://support.microsoft.com/kb/325349).</span></span> <span data-ttu-id="8e0b9-140">(Dieser Vorgang ist bei anderen Versionen von Windows ähnlich.)</span><span class="sxs-lookup"><span data-stu-id="8e0b9-140">(The process is similar on other versions of Windows.)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8e0b9-141">Beim Starten von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]könnte ein WMI-Fehler, der den Ausdruck "Nicht implementiert [0x80004001]" enthält, darauf hinweisen, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht auf dem Zielcomputer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="8e0b9-141">When starting [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a WMI error containing the phrase "not implemented [0x80004001]" may indicate that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not installed on the target computer.</span></span>  
  
  
