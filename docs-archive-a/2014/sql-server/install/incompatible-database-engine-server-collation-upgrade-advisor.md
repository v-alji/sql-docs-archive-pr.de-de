---
title: Nicht kompatible Datenbank-Engine Server-Sortierung (Upgrade Advisor) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 80f499d6-2c90-49eb-a5b3-0bb5b7faaa3b
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: b6ce0555bdf5a878e56d87a8bd55b5ce6c4b2649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621829"
---
# <a name="incompatible-database-engine-server-collation-upgrade-advisor"></a><span data-ttu-id="f0b3e-102">Inkompatible Serversortierung für Datenbank-Engine (Upgrade Advisor)</span><span class="sxs-lookup"><span data-stu-id="f0b3e-102">Incompatible Database Engine Server Collation (Upgrade Advisor)</span></span>
  <span data-ttu-id="f0b3e-103">Der Upgrade Advisor hat erkannt, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] dass eine Instanz von verwendet [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , die für die Verwendung einer nicht kompatiblen Server Sortierung konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="f0b3e-103">Upgrade Advisor detected [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is using an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that is configured to use an incompatible server collation.</span></span>  
  
||  
|-|  
|<span data-ttu-id="f0b3e-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Im SharePoint-Modus.</span><span class="sxs-lookup"><span data-stu-id="f0b3e-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="f0b3e-105">Komponente</span><span class="sxs-lookup"><span data-stu-id="f0b3e-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="f0b3e-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f0b3e-106">Description</span></span>  
 <span data-ttu-id="f0b3e-107">Der Upgrade Advisor hat erkannt, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] dass eine Instanz von verwendet [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , die für die Verwendung einer nicht kompatiblen Server Sortierung konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="f0b3e-107">Upgrade Advisor detected [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is using an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that is configured to use an incompatible server collation.</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="f0b3e-108">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Der SharePoint-Modus nutzt die SharePoint-Architektur für gemeinsame Dienste.</span><span class="sxs-lookup"><span data-stu-id="f0b3e-108">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode utilizes the SharePoint shared services architecture.</span></span> <span data-ttu-id="f0b3e-109">SharePoint unterstützt für Groß-/Kleinschreibung beachtende oder Serversortierungen oder binäre Serversortierungen konfigurierten [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] nicht.</span><span class="sxs-lookup"><span data-stu-id="f0b3e-109">SharePoint does not support [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] configured for case sensitive or server collations or binary server collations.</span></span> <span data-ttu-id="f0b3e-110">Nicht kompatible Sortierungen schließen Sortierungen sein, bei denen standardmäßig zwischen Groß-/Kleinschreibung unterschieden wird bzw. die eine binäre Sortierung aufweisen, und eine Basissortierung, die standardmäßig kompatibel ist, aber anhand eines der folgenden Sortierungskennzeichner konfiguriert wurde:</span><span class="sxs-lookup"><span data-stu-id="f0b3e-110">Incompatible collations include collations that are by default case sensitive or binary and a base collation that by default is compatible but has been configured with any of the following collation designators:</span></span>  
  
-   <span data-ttu-id="f0b3e-111">**Binär (Binary)**</span><span class="sxs-lookup"><span data-stu-id="f0b3e-111">**Binary**</span></span>  
  
-   <span data-ttu-id="f0b3e-112">**Groß-/Kleinschreibung**</span><span class="sxs-lookup"><span data-stu-id="f0b3e-112">**Case-sensitive**</span></span>  
  
-   <span data-ttu-id="f0b3e-113">**Binär-Codepunkt**</span><span class="sxs-lookup"><span data-stu-id="f0b3e-113">**Binary-codepoint**</span></span>  
  
 <span data-ttu-id="f0b3e-114">Da die aktuelle [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]-Serversortierung nicht kompatibel ist, werden Upgrades blockiert.</span><span class="sxs-lookup"><span data-stu-id="f0b3e-114">Because the current [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] server collation is incompatible, upgrade is blocked.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="f0b3e-115">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="f0b3e-115">Corrective Action</span></span>  
 <span data-ttu-id="f0b3e-116">Die [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]-Eigenschaft für die Serversortierung kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f0b3e-116">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] server collation property cannot be changed.</span></span> <span data-ttu-id="f0b3e-117">Sie sind nicht in der Lage, ein Upgrade von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="f0b3e-117">You will not be able to complete an upgrade of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="f0b3e-118">Sie müssen die [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Installation zu einem neuen Server migrieren, der eine kompatible Serversortierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="f0b3e-118">You will need to migrate your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation to a new server which is using a compatible server collation.</span></span> <span data-ttu-id="f0b3e-119">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="f0b3e-119">For more information, see the following:</span></span>  
  
-   [<span data-ttu-id="f0b3e-120">Aktualisieren und Migrieren von Reporting Services</span><span class="sxs-lookup"><span data-stu-id="f0b3e-120">Upgrade and Migrate Reporting Services</span></span>](https://go.microsoft.com/fwlink/?LinkId=233227)  
  
-   [<span data-ttu-id="f0b3e-121">Auswählen einer SQL Server-Sortierung</span><span class="sxs-lookup"><span data-stu-id="f0b3e-121">Selecting a SQL Server Collation</span></span>](https://go.microsoft.com/fwlink/?LinkId=233226)  
  
  
