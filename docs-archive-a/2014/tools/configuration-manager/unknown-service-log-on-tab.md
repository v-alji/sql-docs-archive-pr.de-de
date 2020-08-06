---
title: Unbekannter Dienst (Registerkarte Anmelden) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: e9b35cb5-d8ae-42ea-b59e-deedc99c4823
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0bda49cd95475d4f922f41ebe1701a814c3f60fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609619"
---
# <a name="unknown-service-log-on-tab"></a><span data-ttu-id="b96f2-102">Unbekannter Dienst (Registerkarte Anmelden)</span><span class="sxs-lookup"><span data-stu-id="b96f2-102">Unknown Service (Log On Tab)</span></span>
  <span data-ttu-id="b96f2-103">Der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Konfigurations-Manager kann diesen Dienst nicht identifizieren.</span><span class="sxs-lookup"><span data-stu-id="b96f2-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager is unable to identify this service.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b96f2-104">-Konfigurations-Manager werden Dienstinformationen vom WMI-Anbieter auf dem Computer empfangen, auf dem der Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b96f2-104">Configuration Manager receives service information from the WMI provider on the computer running the service.</span></span> <span data-ttu-id="b96f2-105">Entweder ist beim Lesen der Diensteigenschaften ein Fehler aufgetreten, oder die Diensteigenschaften sind nicht vollständig.</span><span class="sxs-lookup"><span data-stu-id="b96f2-105">Either there was an error while reading the service properties, or the service properties are not complete.</span></span> <span data-ttu-id="b96f2-106">Eine mögliche Problemlösung besteht darin, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager zu schließen und erneut zu öffnen, oder den WMI-Anbieter auf dem Computer zu überprüfen, auf dem der Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b96f2-106">To resolve the problem, try closing and reopening [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, or check the WMI provider on the computer running the service.</span></span>  
  
 <span data-ttu-id="b96f2-107">Der WMI-Anbieter ist eine Windows-Komponente.</span><span class="sxs-lookup"><span data-stu-id="b96f2-107">The WMI provider is a Windows component.</span></span> <span data-ttu-id="b96f2-108">Informationen zum Prüfen von Berechtigungen für den WMI-Anbieter finden Sie unter "Vorgehensweise: Konfigurieren von WMI zum Anzeigen des Serverstatus in SQL Server-Tools" in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="b96f2-108">For information on how to check permissions on the WMI provider, see "How to: Configure WMI to Show Server Status in SQL Server Tools" in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="b96f2-109">Verwenden Sie im Dialogfeld **Eigenschaften von Unbekannter Dienst** die Registerkarte **Anmelden** , um das von diesem Dienst verwendete Konto anzugeben und den Dienst zu starten und zu beenden, falls Sie davon ausgehen, dass Sie den richtigen Dienst angezeigt bekommen.</span><span class="sxs-lookup"><span data-stu-id="b96f2-109">If you believe you are viewing the correct service, use the **Log On** tab of the **Unknown Service Properties** dialog box to specify the account used by this service, and to start and stop the service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b96f2-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="b96f2-110">Options</span></span>  
 <span data-ttu-id="b96f2-111">**Lokales System**</span><span class="sxs-lookup"><span data-stu-id="b96f2-111">**Local System account**</span></span>  
 <span data-ttu-id="b96f2-112">Geben Sie ein lokales Systemkonto an, das kein Kennwort erfordert.</span><span class="sxs-lookup"><span data-stu-id="b96f2-112">Specify a local system account, which does not require a password.</span></span> <span data-ttu-id="b96f2-113">Das lokale Systemkonto kann die Zusammenarbeit mit anderen Servern verhindern. Dies hängt von den Privilegien ab, die dem Konto erteilt wurden.</span><span class="sxs-lookup"><span data-stu-id="b96f2-113">However, the local system account may prevent the service from interacting with other servers, depending on the privileges granted to the account.</span></span>  
  
 <span data-ttu-id="b96f2-114">**Dieses Konto**</span><span class="sxs-lookup"><span data-stu-id="b96f2-114">**This account**</span></span>  
 <span data-ttu-id="b96f2-115">Geben Sie ein lokales oder ein Domänenbenutzerkonto an, das die Windows-Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="b96f2-115">Specify a local or domain user account that uses Windows Authentication.</span></span> <span data-ttu-id="b96f2-116">Das Verwenden eines Domänenbenutzerkontos mit minimalen Berechtigungen für Dienste wird empfohlen.</span><span class="sxs-lookup"><span data-stu-id="b96f2-116">We recommend using a domain user account with minimal rights for services.</span></span> <span data-ttu-id="b96f2-117">Informationen zum Auswählen eines Kontos finden Sie unter "Einrichten von Windows-Dienstkonten" in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="b96f2-117">For information about selecting an account, "Setting Up Windows Service Accounts" in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="b96f2-118">**Kontoname**</span><span class="sxs-lookup"><span data-stu-id="b96f2-118">**Account Name**</span></span>  
 <span data-ttu-id="b96f2-119">Geben Sie den Kontonamen des lokalen oder Domänenbenutzers an.</span><span class="sxs-lookup"><span data-stu-id="b96f2-119">Specify the local or domain user account name.</span></span>  
  
 <span data-ttu-id="b96f2-120">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="b96f2-120">**Password**</span></span>  
 <span data-ttu-id="b96f2-121">Geben Sie das Kennwort des Kontos ein.</span><span class="sxs-lookup"><span data-stu-id="b96f2-121">Type the password of the account.</span></span>  
  
 <span data-ttu-id="b96f2-122">**Kennwort bestätigen**</span><span class="sxs-lookup"><span data-stu-id="b96f2-122">**Confirm password**</span></span>  
 <span data-ttu-id="b96f2-123">Geben Sie das Kennwort des Kontos erneut ein.</span><span class="sxs-lookup"><span data-stu-id="b96f2-123">Type the password of the account again.</span></span>  
  
 <span data-ttu-id="b96f2-124">**Starten**</span><span class="sxs-lookup"><span data-stu-id="b96f2-124">**Start**</span></span>  
 <span data-ttu-id="b96f2-125">Starten Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="b96f2-125">Start the service.</span></span>  
  
 <span data-ttu-id="b96f2-126">**Beenden**</span><span class="sxs-lookup"><span data-stu-id="b96f2-126">**Stop**</span></span>  
 <span data-ttu-id="b96f2-127">Beenden Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="b96f2-127">Stop the service.</span></span>  
  
 <span data-ttu-id="b96f2-128">**Anhalten**</span><span class="sxs-lookup"><span data-stu-id="b96f2-128">**Pause**</span></span>  
 <span data-ttu-id="b96f2-129">Halten Sie den Dienst an.</span><span class="sxs-lookup"><span data-stu-id="b96f2-129">Pause the service.</span></span>  
  
 <span data-ttu-id="b96f2-130">**Fortsetzen**</span><span class="sxs-lookup"><span data-stu-id="b96f2-130">**Resume**</span></span>  
 <span data-ttu-id="b96f2-131">Setzen Sie einen angehaltenen Dienst fort.</span><span class="sxs-lookup"><span data-stu-id="b96f2-131">Resume a paused service.</span></span>  
  
  
