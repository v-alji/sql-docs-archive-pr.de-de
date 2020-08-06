---
title: Absichern der Replikation über das Internet | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- security [SQL Server replication], Internet
- Internet [SQL Server replication], security
ms.assetid: 25b7af05-2721-4b24-9083-fb671e8bf4e0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 47408b2b9559d33da4563c6fc9560d20338ee01d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724486"
---
# <a name="securing-replication-over-the-internet"></a><span data-ttu-id="71d29-102">Securing Replication Over the Internet</span><span class="sxs-lookup"><span data-stu-id="71d29-102">Securing Replication Over the Internet</span></span>
  <span data-ttu-id="71d29-103">Die Replikation über das Internet bietet die größtmögliche Flexibilität, insbesondere für mobile Abonnenten. In diesem Fall muss jedoch die Internetreplikation entsprechend konfiguriert werden, um so die Sicherheit sicherstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="71d29-103">Replication over the Internet can provide flexibility, particularly for mobile Subscribers, but you must configure Internet replication appropriately to ensure adequate security.</span></span> <span data-ttu-id="71d29-104">Für die sichere Freigabe von Daten über das Internet werden die folgenden beiden Verfahren von[!INCLUDE[msCoName](../../../includes/msconame-md.md)] empfohlen:</span><span class="sxs-lookup"><span data-stu-id="71d29-104">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] recommends using one of two techniques for securely sharing information over the Internet:</span></span>  
  
-   <span data-ttu-id="71d29-105">Ein virtuelles privates Netzwerk (VPN)</span><span class="sxs-lookup"><span data-stu-id="71d29-105">Virtual private network (VPN)</span></span>  
  
-   <span data-ttu-id="71d29-106">Die Websynchronisierungsoption für die Mergereplikation</span><span class="sxs-lookup"><span data-stu-id="71d29-106">The Web synchronization option for merge replication</span></span>  
  
## <a name="virtual-private-network"></a><span data-ttu-id="71d29-107">Virtuelles privates Netzwerk</span><span class="sxs-lookup"><span data-stu-id="71d29-107">Virtual Private Network</span></span>  
 <span data-ttu-id="71d29-108">Virtuelle private Netzwerke bieten ein unkompliziertes und sicheres, in Schichten aufgebautes Verfahren zum Replizieren von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Daten über das Internet.</span><span class="sxs-lookup"><span data-stu-id="71d29-108">Virtual private networks provide a simple and secure layered approach to replicating [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data over the Internet.</span></span> <span data-ttu-id="71d29-109">Die VPN-Verbindung über das Internet funktioniert logisch gesehen als WAN-Verbindung (Wide Area Network) zwischen den Standorten.</span><span class="sxs-lookup"><span data-stu-id="71d29-109">The VPN connection over the Internet logically operates as a Wide Area Network (WAN) link between the sites.</span></span>  
  
 <span data-ttu-id="71d29-110">Dies wird erreicht, indem der Benutzer eine Tunnelverbindung über das Internet oder ein anderes öffentliches Netzwerk herstellen kann (mithilfe eines Protokolls, z. B. [!INCLUDE[msCoName](../../../includes/msconame-md.md)] PPTP (Point-to-Point Tunneling Protocol), das mit [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows NT 4.0 oder [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows 2000 verfügbar ist, oder L2TP (Layer Two Tunneling Protocol), das als Bestandteil des Betriebssystems Windows 2000 verfügbar ist).</span><span class="sxs-lookup"><span data-stu-id="71d29-110">This is achieved by allowing the user to tunnel through the Internet or another public network using a protocol such as [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Point-to-Point Tunneling Protocol (PPTP) available with the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows NT version 4.0 or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows 2000 operating system, or Layer Two Tunneling Protocol (L2TP) available with the Windows 2000 operating system.</span></span> <span data-ttu-id="71d29-111">Das Verfahren bietet die gleiche Sicherheit und die gleichen Funktionen, wie sie in einem privaten Netzwerk verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="71d29-111">This process provides security and features similar to those available in a private network.</span></span>  
  
 <span data-ttu-id="71d29-112">Weitere Informationen zum Einrichten eines VPN finden Sie in der [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="71d29-112">For more information about setting up a VPN, see the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows documentation.</span></span>  
  
## <a name="web-synchronization-through-iis"></a><span data-ttu-id="71d29-113">Websynchronisierung über IIS</span><span class="sxs-lookup"><span data-stu-id="71d29-113">Web Synchronization Through IIS</span></span>  
 <span data-ttu-id="71d29-114">Mit der Websynchronisierung für die Mergereplikation ist es möglich, Daten mit dem HTTPS-Protokoll zu replizieren; so können auch Daten durch eine Firewall repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="71d29-114">The web synchronization option for merge replication provides the ability to replicate data using the HTTPS protocol, which can be a convenient approach to replicating data through a firewall.</span></span> <span data-ttu-id="71d29-115">Weitere Informationen finden Sie unter [Konfigurieren der Websynchronisierung](../configure-web-synchronization.md) und [Sicherheitsarchitektur für die Websynchronisierung](security-architecture-for-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="71d29-115">For more information, see [Configure Web Synchronization](../configure-web-synchronization.md) and [Security Architecture for Web Synchronization](security-architecture-for-web-synchronization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71d29-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="71d29-116">See Also</span></span>  
 <span data-ttu-id="71d29-117">[Replication Security Best Practices](replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="71d29-117">[Replication Security Best Practices](replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="71d29-118">SQL Server-Replikation Sicherheit</span><span class="sxs-lookup"><span data-stu-id="71d29-118">SQL Server Replication Security</span></span>](view-and-modify-replication-security-settings.md)  
  
  
