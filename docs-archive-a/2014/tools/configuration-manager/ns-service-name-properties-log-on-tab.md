---
title: Eigenschaften von NS $- &lt; Dienst Name &gt; (Registerkarte "Anmelden") | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 5e6816ec-d4c5-4429-8033-b97427584890
author: stevestein
ms.author: sstein
ms.openlocfilehash: b175895f2385717a67642a41a44dc0d47a1d8d92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722113"
---
# <a name="nsltservice-namegt-properties-log-on-tab"></a><span data-ttu-id="062c3-102">Eigenschaften von NS$&lt;Dienstname&gt; (Registerkarte „Anmelden“)</span><span class="sxs-lookup"><span data-stu-id="062c3-102">NS$&lt;service name&gt; Properties (Log On Tab)</span></span>
  <span data-ttu-id="062c3-103">Verwenden Sie im Dialogfeld **Notification Services-Eigenschaften** die Registerkarte **Anmelden** , um das vom [!INCLUDE[ssNS](../../includes/ssns-md.md)] -Dienst verwendete Konto anzugeben und den Dienst zu starten und zu beenden.</span><span class="sxs-lookup"><span data-stu-id="062c3-103">Use the **Log On** tab of the **Notification Services Properties** dialog box to specify the account used by the [!INCLUDE[ssNS](../../includes/ssns-md.md)] service, and to start and stop the service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="062c3-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="062c3-104">Options</span></span>  
 <span data-ttu-id="062c3-105">**Lokales System**</span><span class="sxs-lookup"><span data-stu-id="062c3-105">**Local System account**</span></span>  
 <span data-ttu-id="062c3-106">Geben Sie ein lokales Systemkonto an, das kein Kennwort erfordert.</span><span class="sxs-lookup"><span data-stu-id="062c3-106">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="062c3-107">Das lokale Systemkonto kann sich allerdings einschränkend auf die Zusammenarbeit mit anderen Servern auswirken. Dies hängt von den Privilegien ab, die dem Konto erteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="062c3-107">However, the local system account may restrict the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="062c3-108">**Dieses Konto**</span><span class="sxs-lookup"><span data-stu-id="062c3-108">**This account**</span></span>  
 <span data-ttu-id="062c3-109">Geben Sie ein lokales oder ein Domänenbenutzerkonto an, das die [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="062c3-109">Specify a local or domain user account that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="062c3-110">empfiehlt, ein Domänenbenutzerkonto mit minimalen Berechtigungen für Dienste zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="062c3-110">recommends using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="062c3-111">Informationen zum Auswählen eines Kontos finden Sie in der Onlinedokumentation unter "Einrichten von Windows-Dienstkonten".</span><span class="sxs-lookup"><span data-stu-id="062c3-111">For information about selecting an account, search Books Online for the topic, "Setting Up Windows Service Accounts."</span></span>  
  
 <span data-ttu-id="062c3-112">**Kontoname**</span><span class="sxs-lookup"><span data-stu-id="062c3-112">**Account Name**</span></span>  
 <span data-ttu-id="062c3-113">Geben Sie den Kontonamen des lokalen oder Domänenbenutzers an.</span><span class="sxs-lookup"><span data-stu-id="062c3-113">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="062c3-114">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="062c3-114">**Password**</span></span>  
 <span data-ttu-id="062c3-115">Geben Sie das Kennwort des Kontos ein.</span><span class="sxs-lookup"><span data-stu-id="062c3-115">Type the password of the account.</span></span>  
  
 <span data-ttu-id="062c3-116">**Kennwort bestätigen**</span><span class="sxs-lookup"><span data-stu-id="062c3-116">**Confirm password**</span></span>  
 <span data-ttu-id="062c3-117">Geben Sie das Kennwort des Kontos erneut ein.</span><span class="sxs-lookup"><span data-stu-id="062c3-117">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="062c3-118">**Starten**</span><span class="sxs-lookup"><span data-stu-id="062c3-118">**Start**</span></span>  
 <span data-ttu-id="062c3-119">Starten Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="062c3-119">Start the service.</span></span>  
  
 <span data-ttu-id="062c3-120">**Beenden**</span><span class="sxs-lookup"><span data-stu-id="062c3-120">**Stop**</span></span>  
 <span data-ttu-id="062c3-121">Beenden Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="062c3-121">Stop the service.</span></span>  
  
 <span data-ttu-id="062c3-122">**Anhalten**</span><span class="sxs-lookup"><span data-stu-id="062c3-122">**Pause**</span></span>  
 <span data-ttu-id="062c3-123">Halten Sie den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="062c3-123">Pause the service.</span></span>  
  
 <span data-ttu-id="062c3-124">**Fortsetzen**</span><span class="sxs-lookup"><span data-stu-id="062c3-124">**Resume**</span></span>  
 <span data-ttu-id="062c3-125">Setzen Sie einen angehaltenen Dienst fort.</span><span class="sxs-lookup"><span data-stu-id="062c3-125">Resume a paused service.</span></span>  
  
  
