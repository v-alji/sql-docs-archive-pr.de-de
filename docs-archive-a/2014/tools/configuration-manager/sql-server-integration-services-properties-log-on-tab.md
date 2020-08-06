---
title: Eigenschaften von SQL Server Integration Services (Registerkarte „Anmelden“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: c0eb1b87-6bb0-475e-8492-0fd3c3f910ea
author: stevestein
ms.author: sstein
ms.openlocfilehash: dfef02a82872ea1df25e7ccb8526e488aaa5f406
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722101"
---
# <a name="sql-server-integration-services-properties-log-on-tab"></a><span data-ttu-id="118f9-102">Eigenschaften von SQL Server Integration Services (Registerkarte Anmelden)</span><span class="sxs-lookup"><span data-stu-id="118f9-102">SQL Server Integration Services Properties (Log On Tab)</span></span>
  <span data-ttu-id="118f9-103">Verwenden Sie im Dialogfeld **Eigenschaften** in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] die Registerkarte **Anmelden**, um das vom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Dienst verwendete Konto anzugeben und den Dienst zu starten und zu beenden.</span><span class="sxs-lookup"><span data-stu-id="118f9-103">Use the **Log On** tab of the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] **Properties** dialog box to specify the account used by the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] service, and to start and stop the service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="118f9-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="118f9-104">Options</span></span>  
 <span data-ttu-id="118f9-105">**Lokales System**</span><span class="sxs-lookup"><span data-stu-id="118f9-105">**Local System account**</span></span>  
 <span data-ttu-id="118f9-106">Geben Sie ein lokales Systemkonto an, das kein Kennwort erfordert.</span><span class="sxs-lookup"><span data-stu-id="118f9-106">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="118f9-107">Das lokale Systemkonto kann sich allerdings einschränkend auf die Zusammenarbeit mit anderen Servern auswirken. Dies hängt von den Privilegien ab, die dem Konto erteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="118f9-107">However, the local system account may restrict the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="118f9-108">**Dieses Konto**</span><span class="sxs-lookup"><span data-stu-id="118f9-108">**This account**</span></span>  
 <span data-ttu-id="118f9-109">Geben Sie ein lokales oder ein Domänenbenutzerkonto an, das die [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="118f9-109">Specify a local or domain user account that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="118f9-110">empfiehlt, ein Domänenbenutzerkonto mit minimalen Berechtigungen für Dienste zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="118f9-110">recommends using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="118f9-111">Informationen zum Auswählen eines Kontos finden Sie in der Onlinedokumentation unter "Einrichten von Windows-Dienstkonten".</span><span class="sxs-lookup"><span data-stu-id="118f9-111">For information about selecting an account, search Books Online for the topic, "Setting Up Windows Service Accounts."</span></span>  
  
 <span data-ttu-id="118f9-112">**Kontoname**</span><span class="sxs-lookup"><span data-stu-id="118f9-112">**Account Name**</span></span>  
 <span data-ttu-id="118f9-113">Geben Sie den Kontonamen des lokalen oder Domänenbenutzers an.</span><span class="sxs-lookup"><span data-stu-id="118f9-113">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="118f9-114">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="118f9-114">**Password**</span></span>  
 <span data-ttu-id="118f9-115">Geben Sie das Kennwort des Kontos ein.</span><span class="sxs-lookup"><span data-stu-id="118f9-115">Type the password of the account.</span></span>  
  
 <span data-ttu-id="118f9-116">**Kennwort bestätigen**</span><span class="sxs-lookup"><span data-stu-id="118f9-116">**Confirm password**</span></span>  
 <span data-ttu-id="118f9-117">Geben Sie das Kennwort des Kontos erneut ein.</span><span class="sxs-lookup"><span data-stu-id="118f9-117">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="118f9-118">**Starten**</span><span class="sxs-lookup"><span data-stu-id="118f9-118">**Start**</span></span>  
 <span data-ttu-id="118f9-119">Starten Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="118f9-119">Start the service.</span></span>  
  
 <span data-ttu-id="118f9-120">**Beenden**</span><span class="sxs-lookup"><span data-stu-id="118f9-120">**Stop**</span></span>  
 <span data-ttu-id="118f9-121">Beenden Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="118f9-121">Stop the service.</span></span>  
  
 <span data-ttu-id="118f9-122">**Anhalten**</span><span class="sxs-lookup"><span data-stu-id="118f9-122">**Pause**</span></span>  
 <span data-ttu-id="118f9-123">Halten Sie den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="118f9-123">Pause the service.</span></span>  
  
 <span data-ttu-id="118f9-124">**Fortsetzen**</span><span class="sxs-lookup"><span data-stu-id="118f9-124">**Resume**</span></span>  
 <span data-ttu-id="118f9-125">Setzen Sie einen angehaltenen Dienst fort.</span><span class="sxs-lookup"><span data-stu-id="118f9-125">Resume a paused service.</span></span>  
  
  
