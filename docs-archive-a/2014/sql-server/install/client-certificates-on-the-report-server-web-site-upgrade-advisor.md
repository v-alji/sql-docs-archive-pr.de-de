---
title: Client Zertifikate auf der Berichts Server-Website (Upgrade Advisor) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], upgrade issues
ms.assetid: 5ecce26b-99df-4109-8e51-d150d369dff7
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 563a64e695ef552a712a5678f56d38fdfbff619f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617507"
---
# <a name="client-certificates-on-the-report-server-web-site-upgrade-advisor"></a><span data-ttu-id="6272f-102">Clientzertifikate auf der Berichtsserver-Website (Upgrade Advisor)</span><span class="sxs-lookup"><span data-stu-id="6272f-102">Client certificates on the report server web site (Upgrade Advisor)</span></span>
  <span data-ttu-id="6272f-103">Der Upgrade Advisor hat ein oder mehrere Clientzertifikate auf der IIS-Website gefunden, die die virtuellen Verzeichnisse des Berichtsservers oder des Berichts-Managers hostet.</span><span class="sxs-lookup"><span data-stu-id="6272f-103">Upgrade Advisor detected one or more client certificates on the IIS Web site that hosts the report server or Report Manager virtual directories.</span></span>  
  
||  
|-|  
|<span data-ttu-id="6272f-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Einheitlicher Modus.</span><span class="sxs-lookup"><span data-stu-id="6272f-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="6272f-105">Komponente</span><span class="sxs-lookup"><span data-stu-id="6272f-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="6272f-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6272f-106">Description</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="6272f-107">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]die Verwendung von Client Zertifikaten zum Authentifizieren von Benutzern wird von nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6272f-107">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not support the use of client certificates to authenticate users.</span></span> <span data-ttu-id="6272f-108">Das Upgrade kann fortgesetzt werden, jedoch werden vom aktualisierten Berichtsserver keine Clientzertifikate verwendet.</span><span class="sxs-lookup"><span data-stu-id="6272f-108">Upgrade can continue, but client certificates will not be used by the upgraded report server.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="6272f-109">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="6272f-109">Corrective Action</span></span>  
 <span data-ttu-id="6272f-110">Sie müssen eine separate Lösung verwenden, wie beispielsweise ISA Server, damit die Anforderungen für die Authentifizierung mit Clientzertifikaten erfüllt werden.</span><span class="sxs-lookup"><span data-stu-id="6272f-110">You will have to use a separate solution such as ISA Server to ensure any client certificate authentication requirements are addressed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6272f-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6272f-111">See Also</span></span>  
 [<span data-ttu-id="6272f-112">Reporting Services Upgradeprobleme &#40;Upgrade Advisor&#41;</span><span class="sxs-lookup"><span data-stu-id="6272f-112">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
