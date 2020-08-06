---
title: SQL Server-Agent-Eigenschaften (Registerkarte „Anmelden“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 01fc6329-5d6b-4186-9565-395f375477bb
author: stevestein
ms.author: sstein
ms.openlocfilehash: cd899e8824adacd07fa1d8d7d51b2143d10cadd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617334"
---
# <a name="sql-server-agent-properties-log-on-tab"></a><span data-ttu-id="6b72f-102">SQL Server-Agent-Eigenschaften (Registerkarte Anmelden)</span><span class="sxs-lookup"><span data-stu-id="6b72f-102">SQL Server Agent Properties (Log On Tab)</span></span>
  <span data-ttu-id="6b72f-103">Verwenden Sie im Dialogfeld **SQL Server-Agent-Eigenschaften** die Registerkarte **Anmelden** , um das vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agentdienst verwendete Konto anzugeben und den Dienst zu starten und zu beenden.</span><span class="sxs-lookup"><span data-stu-id="6b72f-103">Use the **Log On** tab of the **SQL Server Agent Properties** dialog box to specify the account used by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service, and to start and stop the service.</span></span> <span data-ttu-id="6b72f-104">Das Ändern eines Kennworts für ein Konto wird sofort wirksam. Es ist kein Neustart des Dienstes erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6b72f-104">Changing the password of an account takes effect immediately without restarting the service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6b72f-105">Beim Ändern des Kontonamens, der von einem Dienst auf einer gruppierten Instanz verwendet wird, muss das neue Konto Mitglied der Domänengruppe sein, die während des Setups für den zu ändernden Dienst angegeben wird. Andernfalls müssen Sie die Berechtigung zum Hinzufügen von Mitgliedern zu dieser Gruppe besitzen.</span><span class="sxs-lookup"><span data-stu-id="6b72f-105">When changing the account name used by a service on a clustered instance, the new account must be a member of the domain group specified during setup for the service being changed, or you must have permission to add members to that group.</span></span> <span data-ttu-id="6b72f-106">Wenden Sie sich an Ihren Domänenadministrator, falls Sie keine Berechtigung zum Ändern der Gruppenmitgliedschaft haben.</span><span class="sxs-lookup"><span data-stu-id="6b72f-106">If you do not have permission to modify group membership, contact the domain administrator.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6b72f-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="6b72f-107">Options</span></span>  
 <span data-ttu-id="6b72f-108">**Lokales System**</span><span class="sxs-lookup"><span data-stu-id="6b72f-108">**Local System account**</span></span>  
 <span data-ttu-id="6b72f-109">Geben Sie ein lokales Systemkonto an, das kein Kennwort erfordert.</span><span class="sxs-lookup"><span data-stu-id="6b72f-109">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="6b72f-110">Das lokale Systemkonto kann sich allerdings einschränkend auf die Zusammenarbeit mit anderen Servern auswirken. Dies hängt von den Privilegien ab, die dem Konto erteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="6b72f-110">However, the local system account may restrict the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="6b72f-111">**Dieses Konto**</span><span class="sxs-lookup"><span data-stu-id="6b72f-111">**This account**</span></span>  
 <span data-ttu-id="6b72f-112">Geben Sie ein lokales oder ein Domänenbenutzerkonto an, das die Windows-Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="6b72f-112">Specify a local or domain user account that uses Windows Authentication.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="6b72f-113">empfiehlt, ein Domänenbenutzerkonto mit minimalen Berechtigungen für Dienste zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6b72f-113">recommends using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="6b72f-114">Informationen zum Auswählen eines Kontos finden Sie in der Onlinedokumentation unter "Einrichten von Windows-Dienstkonten".</span><span class="sxs-lookup"><span data-stu-id="6b72f-114">For information about selecting an account, search Books Online for "Setting Up Windows Service Accounts."</span></span>  
  
 <span data-ttu-id="6b72f-115">**Kontoname**</span><span class="sxs-lookup"><span data-stu-id="6b72f-115">**Account Name**</span></span>  
 <span data-ttu-id="6b72f-116">Geben Sie den Kontonamen des lokalen oder Domänenbenutzers an.</span><span class="sxs-lookup"><span data-stu-id="6b72f-116">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="6b72f-117">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="6b72f-117">**Password**</span></span>  
 <span data-ttu-id="6b72f-118">Geben Sie das Kennwort des Kontos ein.</span><span class="sxs-lookup"><span data-stu-id="6b72f-118">Type the password of the account.</span></span>  
  
 <span data-ttu-id="6b72f-119">**Kennwort bestätigen**</span><span class="sxs-lookup"><span data-stu-id="6b72f-119">**Confirm password**</span></span>  
 <span data-ttu-id="6b72f-120">Geben Sie das Kennwort des Kontos erneut ein.</span><span class="sxs-lookup"><span data-stu-id="6b72f-120">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="6b72f-121">**Starten**</span><span class="sxs-lookup"><span data-stu-id="6b72f-121">**Start**</span></span>  
 <span data-ttu-id="6b72f-122">Starten Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="6b72f-122">Start the service.</span></span>  
  
 <span data-ttu-id="6b72f-123">**Beenden**</span><span class="sxs-lookup"><span data-stu-id="6b72f-123">**Stop**</span></span>  
 <span data-ttu-id="6b72f-124">Beenden Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="6b72f-124">Stop the service.</span></span>  
  
 <span data-ttu-id="6b72f-125">**Anhalten**</span><span class="sxs-lookup"><span data-stu-id="6b72f-125">**Pause**</span></span>  
 <span data-ttu-id="6b72f-126">Halten Sie den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="6b72f-126">Pause the service.</span></span>  
  
 <span data-ttu-id="6b72f-127">**Fortsetzen**</span><span class="sxs-lookup"><span data-stu-id="6b72f-127">**Resume**</span></span>  
 <span data-ttu-id="6b72f-128">Setzen Sie einen angehaltenen Dienst fort.</span><span class="sxs-lookup"><span data-stu-id="6b72f-128">Resume a paused service.</span></span>  
  
  
