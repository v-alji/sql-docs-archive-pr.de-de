---
title: Dialogfeld „IP-Adresse hinzufügen“ (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygrouplistener.addipaddress.f1
ms.assetid: 98c9ad3b-ff3c-4c1d-b344-59a72fca137c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5192e6414b34bee6de09d45a7284f25404235dc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609460"
---
# <a name="add-ip-address-dialog-box-sql-server-management-studio"></a><span data-ttu-id="6b408-102">Dialogfeld IP-Adresse hinzufügen (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="6b408-102">Add IP Address Dialog Box (SQL Server Management Studio)</span></span>
  <span data-ttu-id="6b408-103"> In diesem F1-Hilfethema werden die Optionen des Dialogfelds **IP-Adresse hinzufügen** beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6b408-103">This F1 help topic describes the options of the **Add IP Address** dialog box.</span></span> <span data-ttu-id="6b408-104">Auf dieses Dialogfeld wird über das Dialogfeld **Neuer Verfügbarkeitsgruppenlistener** und über die Registerkarte **Listener** der Seite **Replikate angeben** des [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] oder des [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="6b408-104">This dialog box accessed from the **New Availability Group Listener** dialog box and the **Listener** tab of the **Specify Replicas** page of the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] or the [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6b408-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6b408-105">Prerequisites</span></span>  
 <span data-ttu-id="6b408-106">Bevor Sie beginnen, einem Verfügbarkeitsgruppenlistener Subnetze hinzuzufügen, stellen Sie sicher, dass Sie die IP-Adresse für jedes Subnetz und bei einer IPv4-Adresse die Subnetzmaske kennen.</span><span class="sxs-lookup"><span data-stu-id="6b408-106">Before you begin to add subnets to an availability group listener, ensure that know the IP address for each subnet and, for an IPv4 address, the subnet mask.</span></span>  
  
##  <a name="add-ip-address-options"></a><a name="PageOptions"></a> <span data-ttu-id="6b408-107">Optionen für "IP-Adresse hinzufügen"</span><span class="sxs-lookup"><span data-stu-id="6b408-107">Add IP Address Options</span></span>  
 <span data-ttu-id="6b408-108">**Subnetz**</span><span class="sxs-lookup"><span data-stu-id="6b408-108">**Subnet**</span></span>  
 <span data-ttu-id="6b408-109">Verwenden Sie die Dropdownliste, um eine Adresse für das Subnetz auszuwählen, das Sie dem Verfügbarkeitsgruppenlistener hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6b408-109">Use the drop list to select an address for the subnet that you are adding to the availability group listener.</span></span> <span data-ttu-id="6b408-110">Standardmäßig besitzt ein Subnetz sowohl eine IPv4-Adresse als auch eine IPv6-Adresse.</span><span class="sxs-lookup"><span data-stu-id="6b408-110">By default a subnet possesses both an IPv4 address and an IPv6 address.</span></span> <span data-ttu-id="6b408-111">Beim ersten Verwenden des Dialogfelds **IP-Adresse hinzufügen** zeigt die Dropdownliste **Subnetz** beide Subnetzadressen für jedes Subnetz an, das ein Replikat für die Verfügbarkeitsgruppe hostet.</span><span class="sxs-lookup"><span data-stu-id="6b408-111">The first time you use the **Add IP Address** dialog,  the **Subnet** drop list displays both subnet addresses for each subnet that hosts a replica for the availability group.</span></span> <span data-ttu-id="6b408-112">Um dem Listener ein angegebenes Subnetz hinzuzufügen, wählen Sie eine der Subnetzadressen aus.</span><span class="sxs-lookup"><span data-stu-id="6b408-112">To add a given subnet to the listener, select one of its subnet addresses.</span></span>  
  
 <span data-ttu-id="6b408-113">Nachdem Sie das Dialogfeld **IP-Adresse hinzufügen** abgeschlossen und auf **OK** geklickt haben, um dem Listener eine ausgewählte Subnetzadresse hinzuzufügen, filtert die Dropdownliste **Subnetz** diese Subnetzadresse heraus.</span><span class="sxs-lookup"><span data-stu-id="6b408-113">After you complete the **Add IP Address** dialog box and click **OK** to add a selected subnet address to the listener, the **Subnet** drop list filters out that subnet address.</span></span> <span data-ttu-id="6b408-114">Alle nicht ausgewählten Subnetzadressen verbleiben in der Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="6b408-114">All unselected subnet addresses remain on the drop list.</span></span> <span data-ttu-id="6b408-115">Stellen Sie sicher, dass Sie dem Listener nur genau eine Subnetzadresse pro Subnetz hinzufügen, anderenfalls schlägt die Listenererstellung fehl.</span><span class="sxs-lookup"><span data-stu-id="6b408-115">Be sure that you add one and only one subnet address per subnet to the listener, or listener creation will fail.</span></span>  
  
 <span data-ttu-id="6b408-116">**Adressen**</span><span class="sxs-lookup"><span data-stu-id="6b408-116">**Addresses**</span></span>  
 <span data-ttu-id="6b408-117">Verwenden Sie dieses Feld, um eine statische IP-Adresse für die ausgewählte Subnetzadresse einzugeben.</span><span class="sxs-lookup"><span data-stu-id="6b408-117">Use this field to enter a static IP address for the selected subnet address.</span></span> <span data-ttu-id="6b408-118">Wenden Sie sich an Ihren Netzwerkadministrator, um diese IP-Adresse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6b408-118">Contact your network administrator for this IP address.</span></span> <span data-ttu-id="6b408-119">Stellen Sie sicher, dass Sie eine gültige Adresse für die ausgewählte Subnetzadresse eingeben, anderenfalls schlägt die Listenererstellung fehl.</span><span class="sxs-lookup"><span data-stu-id="6b408-119">Ensure that you enter a valid address for the selected subnet address, or listener creation will fail.</span></span>  
  
 <span data-ttu-id="6b408-120">**IPv4-Adresse**</span><span class="sxs-lookup"><span data-stu-id="6b408-120">**IPv4 Address**</span></span>  
 <span data-ttu-id="6b408-121">Wenn Sie die IPv4-Subnetzadresse eines Subnetzes ausgewählt haben, geben Sie hier eine gültige statische IPv4-Adresse ein.</span><span class="sxs-lookup"><span data-stu-id="6b408-121">If you selected the IPv4 subnet address of a subnet, enter a valid IPv4 static address here.</span></span>  
  
 <span data-ttu-id="6b408-122">**Subnetzmaske**</span><span class="sxs-lookup"><span data-stu-id="6b408-122">**Subnet Mask**</span></span>  
 <span data-ttu-id="6b408-123">Bei einer IPv4-Adresse zeigt dieses schreibgeschützte Feld die Subnetzmaske des ausgewählten Subnetzes an.</span><span class="sxs-lookup"><span data-stu-id="6b408-123">For an IPv4 address, this read-only field displays the subnet mask of the selected subnet.</span></span>  
  
 <span data-ttu-id="6b408-124">**IPv6-Adresse**</span><span class="sxs-lookup"><span data-stu-id="6b408-124">**IPv6 Address**</span></span>  
 <span data-ttu-id="6b408-125">Wenn Sie die IPv6-Subnetzadresse eines Subnetzes ausgewählt haben, geben Sie hier eine gültige statische IPv6-Adresse ein.</span><span class="sxs-lookup"><span data-stu-id="6b408-125">If you selected the IPv6 subnet address of a subnet, enter a valid IPv6 static address here.</span></span>  
  
 <span data-ttu-id="6b408-126">**OK**</span><span class="sxs-lookup"><span data-stu-id="6b408-126">**OK**</span></span>  
 <span data-ttu-id="6b408-127">Klicken Sie hier, um das Subnetz, dessen Adresse Sie ausgewählt haben, mit der angegebenen statischen IP-Adresse hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="6b408-127">Click to create add the subnet whose address you selected, along with the static IP address that you specified.</span></span> <span data-ttu-id="6b408-128">Dem Subnetzraster des Dialogfelds **Neuer Verfügbarkeitsgruppenlistener** oder **Replikate angeben** wird eine Zeile mit diesen Werten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6b408-128">A row containing these values will be added to the subnet grid of the **New Availability Group Listener** or **Specify Replicas** dialog box.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6b408-129">Im Dialogfeld **IP-Adresse hinzufügen** wird die IP-Adresse nicht überprüft.</span><span class="sxs-lookup"><span data-stu-id="6b408-129">The **Add IP Address** dialog does not verify the IP address.</span></span> <span data-ttu-id="6b408-130">Auch verhindert das Dialogfeld nicht, dass Sie die zweite Subnetzadresse für ein Subnetz hinzufügen, das Sie bereits dem Verfügbarkeitsgruppenlistener hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="6b408-130">Also the dialog does not prevent you from adding the second subnet address for a subnet that you have already added to the availability group listener.</span></span>  
  
 <span data-ttu-id="6b408-131">**Abbrechen**</span><span class="sxs-lookup"><span data-stu-id="6b408-131">**Cancel**</span></span>  
 <span data-ttu-id="6b408-132">Klicken Sie, um die Auswahl abzubrechen und zum Dialogfeld **Neuer Verfügbarkeitsgruppenlistener** oder zur Registerkarte **Listener** zurückzukehren, ohne eine statische IP-Adresse für ein Subnetz hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="6b408-132">Click to cancel your selections, and return to the **New Availability Group Listener** dialog box or **Listener** tab without adding a static IP address for any subnet.</span></span>  
  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="6b408-133">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="6b408-133">Related Tasks</span></span>  
  
-   [<span data-ttu-id="6b408-134">Erstellen oder Konfigurieren eines Verfügbarkeitsgruppenlisteners &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6b408-134">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="6b408-135">Verwenden des Dialogfelds Neue Verfügbarkeitsgruppe &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6b408-135">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="6b408-136">Verwenden des Assistenten zum Hinzufügen von Replikaten zu Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="6b408-136">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
  
## <a name="see-also"></a><span data-ttu-id="6b408-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6b408-137">See Also</span></span>  
 <span data-ttu-id="6b408-138">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6b408-138">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="6b408-139">[Verfügbarkeitsgruppenlistener, Clientkonnektivität und Anwendungsfailover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span><span class="sxs-lookup"><span data-stu-id="6b408-139">[Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span></span>  
 [<span data-ttu-id="6b408-140">AlwaysOn-Clientkonnektivität (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6b408-140">AlwaysOn Client Connectivity (SQL Server)</span></span>](always-on-client-connectivity-sql-server.md)  
  
  
