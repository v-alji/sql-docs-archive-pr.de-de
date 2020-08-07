---
title: IP-Adress Einschränkung erkannt (Upgrade Advisor) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], upgrade issues
ms.assetid: 9a154455-c68f-4403-a3a7-b90f4d35eecb
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 2028e59e91d42bfdced2d18fa6ce129dfb108302
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700629"
---
# <a name="ip-address-restriction-detected-upgrade-advisor"></a><span data-ttu-id="c7fda-102">IP-Adresseinschränkung erkannt (Upgrade Advisor)</span><span class="sxs-lookup"><span data-stu-id="c7fda-102">IP address restriction detected (Upgrade Advisor)</span></span>
  <span data-ttu-id="c7fda-103">Der Upgrade Advisor hat mindestens eine IP-Adresseinschränkung auf der IIS-Website gefunden, die den Berichtsserver bzw. die virtuellen Verzeichnisse des Berichts-Managers hostet.</span><span class="sxs-lookup"><span data-stu-id="c7fda-103">Upgrade Advisor detected one or more IP address restrictions on the IIS Web site that hosts the report server or Report Manager virtual directories.</span></span> [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="c7fda-104">stellt keine systeminterne Unterstützung für IP-Adresseinschränkungen bereit.</span><span class="sxs-lookup"><span data-stu-id="c7fda-104">does not provide native support for IP address restrictions.</span></span>  
  
||  
|-|  
|<span data-ttu-id="c7fda-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Einheimischen.</span><span class="sxs-lookup"><span data-stu-id="c7fda-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="c7fda-106">Komponente</span><span class="sxs-lookup"><span data-stu-id="c7fda-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="c7fda-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c7fda-107">Description</span></span>  
 <span data-ttu-id="c7fda-108">Das Setup kann keine IP-Adresseinschränkungen für URLs definieren, die für einen aktualisierten Berichtsserver erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="c7fda-108">Setup cannot define IP address restrictions on URLs created for an upgraded report server.</span></span> <span data-ttu-id="c7fda-109">Das Upgrade kann fortgesetzt werden, jedoch werden keine IP-Adresseinschränkungen für die [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-URLs definiert.</span><span class="sxs-lookup"><span data-stu-id="c7fda-109">Upgrade can continue, but IP address restrictions will not be defined on the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] URLs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="c7fda-110">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="c7fda-110">Corrective Action</span></span>  
 <span data-ttu-id="c7fda-111">Verwenden Sie nach dem Upgrade ISA Server, Ihre Firewallsoftware oder eine andere Lösung, um Anforderungen spezifischer IP-Adressen an den Berichtsserver zuzulassen oder abzuweisen.</span><span class="sxs-lookup"><span data-stu-id="c7fda-111">After upgrade, use ISA Server, your firewall software, or another solution to allow or exclude requests from specific IP addresses to the report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7fda-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c7fda-112">See Also</span></span>  
 [<span data-ttu-id="c7fda-113">Reporting Services Upgradeprobleme &#40;Upgrade Advisor&#41;</span><span class="sxs-lookup"><span data-stu-id="c7fda-113">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
