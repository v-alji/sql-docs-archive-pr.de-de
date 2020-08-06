---
title: Eigenschaften von Analysis-Servern (Registerkarte „Anmelden“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: a82e0c98-efaa-4b0b-9582-3c879ee42444
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8db5576e48e7f12ef1733175875d2cd065e376fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725194"
---
# <a name="analysis-server-properties-log-on-tab"></a><span data-ttu-id="439c0-102">Analysis-Server-Eigenschaften (Registerkarte Anmelden)</span><span class="sxs-lookup"><span data-stu-id="439c0-102">Analysis Server Properties (Log On Tab)</span></span>
  <span data-ttu-id="439c0-103">Verwenden Sie im Dialogfeld **Eigenschaften für Analysis-Server** die Registerkarte **Anmelden** , um das vom [!INCLUDE[ssAS](../../includes/ssas-md.md)] -Dienst verwendete Konto anzugeben und den Dienst zu starten und zu beenden.</span><span class="sxs-lookup"><span data-stu-id="439c0-103">Use the **Log On** tab of the **Analysis Server Properties** dialog box to specify the account used by the [!INCLUDE[ssAS](../../includes/ssas-md.md)] service, and to start and stop the service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="439c0-104">Beim Ändern der Option **Kontoname** , die von einem Dienst auf einer gruppierten Instanz verwendet wird, muss das neue Konto Mitglied der Domänengruppe sein, die während des Setups für den zu ändernden Dienst angegeben wird. Andernfalls müssen Sie die Berechtigung zum Hinzufügen von Mitgliedern zu dieser Gruppe besitzen.</span><span class="sxs-lookup"><span data-stu-id="439c0-104">When changing the **Account Name** used by a service on a clustered instance, the new account must either be a member of the domain group specified during setup for the service being changed, or you must have permission to add members to that group.</span></span> <span data-ttu-id="439c0-105">Wenden Sie sich an Ihren Domänenadministrator, falls Sie keine Berechtigung zum Ändern der Gruppenmitgliedschaft haben.</span><span class="sxs-lookup"><span data-stu-id="439c0-105">If you do not have permission to modify group membership, contact the domain administrator.</span></span>  
  
## <a name="options"></a><span data-ttu-id="439c0-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="439c0-106">Options</span></span>  
 <span data-ttu-id="439c0-107">**Lokales System**</span><span class="sxs-lookup"><span data-stu-id="439c0-107">**Local System account**</span></span>  
 <span data-ttu-id="439c0-108">Geben Sie ein lokales Systemkonto an, das kein Kennwort erfordert.</span><span class="sxs-lookup"><span data-stu-id="439c0-108">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="439c0-109">Das lokale Systemkonto kann sich allerdings einschränkend auf die Zusammenarbeit mit anderen Servern auswirken. Dies hängt von den Privilegien ab, die dem Konto erteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="439c0-109">However, the local system account may restrict the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="439c0-110">**Dieses Konto**</span><span class="sxs-lookup"><span data-stu-id="439c0-110">**This account**</span></span>  
 <span data-ttu-id="439c0-111">Geben Sie ein lokales oder ein Domänenbenutzerkonto an, das die [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="439c0-111">Specify a local or domain user account that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="439c0-112">empfiehlt, ein Domänenbenutzerkonto mit minimalen Berechtigungen für Dienste zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="439c0-112">recommends using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="439c0-113">Informationen zum Auswählen eines Kontos finden Sie in der Onlinedokumentation unter "Einrichten von Windows-Dienstkonten".</span><span class="sxs-lookup"><span data-stu-id="439c0-113">For information about selecting an account, search Books Online for the topic Setting Up Windows Service Accounts.</span></span>  
  
 <span data-ttu-id="439c0-114">**Kontoname**</span><span class="sxs-lookup"><span data-stu-id="439c0-114">**Account Name**</span></span>  
 <span data-ttu-id="439c0-115">Geben Sie den Kontonamen des lokalen oder Domänenbenutzers an.</span><span class="sxs-lookup"><span data-stu-id="439c0-115">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="439c0-116">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="439c0-116">**Password**</span></span>  
 <span data-ttu-id="439c0-117">Geben Sie das Kennwort des Kontos ein.</span><span class="sxs-lookup"><span data-stu-id="439c0-117">Type the password of the account.</span></span>  
  
 <span data-ttu-id="439c0-118">**Kennwort bestätigen**</span><span class="sxs-lookup"><span data-stu-id="439c0-118">**Confirm password**</span></span>  
 <span data-ttu-id="439c0-119">Geben Sie das Kennwort des Kontos erneut ein.</span><span class="sxs-lookup"><span data-stu-id="439c0-119">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="439c0-120">**Starten**</span><span class="sxs-lookup"><span data-stu-id="439c0-120">**Start**</span></span>  
 <span data-ttu-id="439c0-121">Starten Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="439c0-121">Start the service.</span></span>  
  
 <span data-ttu-id="439c0-122">**Beenden**</span><span class="sxs-lookup"><span data-stu-id="439c0-122">**Stop**</span></span>  
 <span data-ttu-id="439c0-123">Beenden Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="439c0-123">Stop the service.</span></span>  
  
 <span data-ttu-id="439c0-124">**Anhalten**</span><span class="sxs-lookup"><span data-stu-id="439c0-124">**Pause**</span></span>  
 <span data-ttu-id="439c0-125">Halten Sie den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="439c0-125">Pause the service.</span></span>  
  
 <span data-ttu-id="439c0-126">**Fortsetzen**</span><span class="sxs-lookup"><span data-stu-id="439c0-126">**Resume**</span></span>  
 <span data-ttu-id="439c0-127">Setzen Sie einen angehaltenen Dienst fort.</span><span class="sxs-lookup"><span data-stu-id="439c0-127">Resume a paused service.</span></span>  
  
  
