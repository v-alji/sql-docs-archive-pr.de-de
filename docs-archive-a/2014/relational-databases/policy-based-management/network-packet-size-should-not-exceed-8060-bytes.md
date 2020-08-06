---
title: Netzwerkpaketgröße darf 8060 Bytes nicht überschreiten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 86db5da1-afe4-4fbb-8bf8-33cedc7e4361
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 01b500cbe65107767d73bc2901b6d5e028b94ee9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616000"
---
# <a name="network-packet-size-should-not-exceed-8060-bytes"></a><span data-ttu-id="ee224-102">Netzwerkpaketgröße darf 8060 Bytes nicht überschreiten</span><span class="sxs-lookup"><span data-stu-id="ee224-102">Network Packet Size Should Not Exceed 8060 Bytes</span></span>
  <span data-ttu-id="ee224-103">Wenn der für sp_configure 'Netzwerkpaketgröße' angegebene Wert oder die Netzwerkpaketgröße eines angemeldeten Benutzers 8060 Bytes überschreitet, führt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verschiedene Speicherbelegungsvorgänge aus.</span><span class="sxs-lookup"><span data-stu-id="ee224-103">If the value specified for sp_configure 'network packet size' or if the network packet size of any logged-in user is more than 8060 bytes, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs different memory allocation operations.</span></span> <span data-ttu-id="ee224-104">Dies kann zu einer Zunahme des virtuellen Adressraums führen, der nicht für den Pufferpool reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="ee224-104">This can cause an increase in the process virtual address space that is not reserved for the buffer pool.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="ee224-105">Empfehlungen zu Best Practices</span><span class="sxs-lookup"><span data-stu-id="ee224-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="ee224-106">Die Netzwerkpaketgröße sollte 8060 Bytes nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="ee224-106">The network packet size should not exceed 8060 bytes.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="ee224-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ee224-107">For More Information</span></span>  
 [<span data-ttu-id="ee224-108">Microsoft Knowledge Base-Artikel 903002</span><span class="sxs-lookup"><span data-stu-id="ee224-108">Microsoft Knowledge Base article 903002</span></span>](https://go.microsoft.com/fwlink/?linkid=117749)  
  
## <a name="see-also"></a><span data-ttu-id="ee224-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ee224-109">See Also</span></span>  
 [<span data-ttu-id="ee224-110">Überwachen und Erzwingen von Best Practices mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="ee224-110">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
