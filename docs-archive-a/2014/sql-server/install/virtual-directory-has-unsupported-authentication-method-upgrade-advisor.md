---
title: Virtuelles Verzeichnis weist eine nicht unterstützte Authentifizierungsmethode auf (Upgrade Advisor) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- virtual directories [Reporting Services]
ms.assetid: 216eca6f-9a66-42e1-aa54-dcf99cec9f7d
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 67b1c027b8ed020f65fdea7c093f6d5454f02c5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617406"
---
# <a name="virtual-directory-has-unsupported-authentication-method-upgrade-advisor"></a><span data-ttu-id="be64c-102">Das virtuelle Verzeichnis weist eine nicht unterstützte Authentifizierungsmethode auf (Upgrade Advisor)</span><span class="sxs-lookup"><span data-stu-id="be64c-102">Virtual directory has unsupported authentication method (Upgrade Advisor)</span></span>
  <span data-ttu-id="be64c-103">Upgrade Advisor hat im Berichts-Manager oder im virtuellen Verzeichnis des Berichtsservers eine nicht unterstützte Authentifizierungsmethode erkannt.</span><span class="sxs-lookup"><span data-stu-id="be64c-103">Upgrade Advisor detected an unsupported authentication method on the Report Manager or report server virtual directory.</span></span> <span data-ttu-id="be64c-104">Authentifizierungsmethoden, die von einem Upgrade nicht unterstützt werden, sind Anonymous, Digest und .NET Passport.</span><span class="sxs-lookup"><span data-stu-id="be64c-104">Authentication methods that are not supported by upgrade include Anonymous, Digest, and .NET Passport.</span></span>  
  
||  
|-|  
|<span data-ttu-id="be64c-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Einheitlicher Modus.</span><span class="sxs-lookup"><span data-stu-id="be64c-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="be64c-106">Komponente</span><span class="sxs-lookup"><span data-stu-id="be64c-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="be64c-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="be64c-107">Description</span></span>  
 <span data-ttu-id="be64c-108">Setup kann eine [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Installation nicht aktualisieren, die eine der folgenden Authentifizierungsmethoden verwendet</span><span class="sxs-lookup"><span data-stu-id="be64c-108">Setup cannot upgrade a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation that uses one of the following authentication methods</span></span>  
  
-   <span data-ttu-id="be64c-109">Anonym</span><span class="sxs-lookup"><span data-stu-id="be64c-109">Anonymous</span></span>  
  
-   <span data-ttu-id="be64c-110">Digest</span><span class="sxs-lookup"><span data-stu-id="be64c-110">Digest</span></span>  
  
-   <span data-ttu-id="be64c-111">.NET Passport</span><span class="sxs-lookup"><span data-stu-id="be64c-111">.NET Passport</span></span>  
  
 <span data-ttu-id="be64c-112">Um fortzufahren, können Sie entweder die Authentifizierungsmethode ändern, die für die virtuellen [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Verzeichnisse in den Internetinformationsdiensten (IIS) angegeben ist, oder die Installation migrieren.</span><span class="sxs-lookup"><span data-stu-id="be64c-112">To continue, you can either modify the Authentication method that is specified for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] virtual directories in Internet Information Services (IIS), or you can migrate your installation.</span></span> <span data-ttu-id="be64c-113">Weitere Informationen über das Migrieren einer Installation finden Sie in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="be64c-113">For more information about migrating your installation, see [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="be64c-114">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="be64c-114">Corrective Action</span></span>  
 <span data-ttu-id="be64c-115">Um das Upgrade fortzusetzen, ändern Sie in IIS die Authentifizierungsmethode für die virtuellen Verzeichnisse ReportServer und Reports.</span><span class="sxs-lookup"><span data-stu-id="be64c-115">To continue with upgrade, modify the Authentication method in IIS for the ReportServer and Reports virtual directories.</span></span> <span data-ttu-id="be64c-116">Weitere Informationen zum Ändern der Authentifizierungsmethode in IIS finden Sie in der IIS-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="be64c-116">For more information about modifying Authentication methods in IIS, see the IIS documentation.</span></span> <span data-ttu-id="be64c-117">Führen Sie nach dem Ändern der Authentifizierungsmethode für die virtuellen Verzeichnisse von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] den Upgrade Advisor erneut aus, um zu bestätigen, dass keine weiteren Upgradeprobleme vorliegen.</span><span class="sxs-lookup"><span data-stu-id="be64c-117">After you modify the Authentication method for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] virtual directories, re-run Upgrade Advisor to confirm that there are no other upgrade issues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be64c-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="be64c-118">See Also</span></span>  
 [<span data-ttu-id="be64c-119">Reporting Services Upgradeprobleme &#40;Upgrade Advisor&#41;</span><span class="sxs-lookup"><span data-stu-id="be64c-119">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
