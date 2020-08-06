---
title: Migrieren von Skripts zu VSTA | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- SSIS Script task, converting scripts
- Script component [Integration Services], converting scripts
- Script task [Integration Services], converting scripts
- SSIS Script component, converting scripts
ms.assetid: d685098b-86a1-46bf-939a-63d56951e009
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: afbc19c35f99a5abc5a6ebd92024e42baa6a9237
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724381"
---
# <a name="migrate-scripts-to-vsta"></a><span data-ttu-id="4812f-102">Migrieren von Skripts zu VSTA</span><span class="sxs-lookup"><span data-stu-id="4812f-102">Migrate Scripts to VSTA</span></span>
  <span data-ttu-id="4812f-103">Wenn Sie [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Pakete auf aktualisieren [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , werden die Skripts [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] in allen Skript Tasks oder Skript Komponenten zu [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) migriert.</span><span class="sxs-lookup"><span data-stu-id="4812f-103">When you upgrade [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] packages to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] migrates the scripts in any Script tasks or Script components to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span> <span data-ttu-id="4812f-104">VSTA ist die von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] verwendete Skriptumgebung.</span><span class="sxs-lookup"><span data-stu-id="4812f-104">VSTA is the scripting environment that [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] uses.</span></span> <span data-ttu-id="4812f-105">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] handelt es sich bei der Skript Umgebung für [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] um Anwendungen (VSA).</span><span class="sxs-lookup"><span data-stu-id="4812f-105">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], the scripting environment for [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] for Applications (VSA).</span></span>  
  
 <span data-ttu-id="4812f-106">Wenn die Skripts in den Skripttasks oder Skriptkomponenten auf Schnittstellen verweisen, müssen Sie diese Verweise ggf. ändern, bevor Sie das Paket aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4812f-106">If the scripts in either the Script tasks or Script components reference interfaces, you might have to modify those references before you upgrade the package.</span></span> <span data-ttu-id="4812f-107">Andernfalls tritt beim Aktualisieren des Pakets oder beim Überprüfen der Skripts je nach verwendeter Upgrademethode ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="4812f-107">Otherwise, the package will not be upgraded or the scripts will not be validated, depending on the upgrade method that you use.</span></span> <span data-ttu-id="4812f-108">Um diese Verweise zu ändern, ersetzen Sie die Verweise auf IDTs*xxx*90-Schnittstellen durch Verweise auf die entsprechenden IDTs*xxx*100-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="4812f-108">To modify these references, replace references to IDTS*xxx*90 interfaces with references to the corresponding IDTS*xxx*100 interfaces.</span></span>  
  
 <span data-ttu-id="4812f-109">Weitere Informationen zum Migrieren von Skripts und Upgradepaketen finden Sie unter [Aktualisieren von Integration Services Paketen](../../integration-services/install-windows/upgrade-integration-services-packages.md).</span><span class="sxs-lookup"><span data-stu-id="4812f-109">For more information about how to migrate scripts and upgrade packages, see [Upgrade Integration Services Packages](../../integration-services/install-windows/upgrade-integration-services-packages.md).</span></span>  
  
## <a name="understanding-migration-failures"></a><span data-ttu-id="4812f-110">Grundlegendes zu Migrationsfehlern</span><span class="sxs-lookup"><span data-stu-id="4812f-110">Understanding Migration Failures</span></span>  
 <span data-ttu-id="4812f-111">Beim Migrieren der Skripts kann aus einem der folgenden Gründe ein Fehler auftreten:</span><span class="sxs-lookup"><span data-stu-id="4812f-111">When you migrate the scripts, the migration can fail because of one of the following reasons:</span></span>  
  
-   <span data-ttu-id="4812f-112">Der Einstiegspunkt für das VSA-Skript wurde umbenannt.</span><span class="sxs-lookup"><span data-stu-id="4812f-112">The entry point for the VSA script was renamed.</span></span>  
  
     <span data-ttu-id="4812f-113">Mit dem Einstiegspunkt wird die Methode in der `ScriptMain`-Klasse im VSTA-Projekt angegeben, die die [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Laufzeit als Einstiegspunkt in den Code des Skripttasks aufruft.</span><span class="sxs-lookup"><span data-stu-id="4812f-113">The entry point specifies the method in the `ScriptMain` class in the VSTA project that the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] runtime calls as the entry point into the Script task code.</span></span> <span data-ttu-id="4812f-114">Die- `ScriptMain` Klasse ist die Standardklasse, die von den Skript Vorlagen generiert wird.</span><span class="sxs-lookup"><span data-stu-id="4812f-114">The `ScriptMain` class is the default class that the script templates generate.</span></span>  
  
-   <span data-ttu-id="4812f-115">Das VSA-Skript weist keinen Einstiegspunkt oder mehrere Einstiegspunkte auf.</span><span class="sxs-lookup"><span data-stu-id="4812f-115">There is no entry point or there are multiple entry points in the VSA script.</span></span>  
  
-   <span data-ttu-id="4812f-116">Es konnten keine Assemblyverweise hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="4812f-116">Assembly references could not be added.</span></span>  
  
-   <span data-ttu-id="4812f-117">Die `ScriptMain`-Klasse wurde so geändert, dass sie neben der `ScriptObjectModelSSIS`-Klasse von anderen Klassen erbt.</span><span class="sxs-lookup"><span data-stu-id="4812f-117">The `ScriptMain` class was modified to inherit from other classes in addition to the `ScriptObjectModelSSIS` class.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="4812f-118">[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]unterstützt keine mehrfache Vererbung.</span><span class="sxs-lookup"><span data-stu-id="4812f-118">[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] does not support multiple inheritance.</span></span>  
  
 <span data-ttu-id="4812f-119">Ein VSA-Skript, das verwendet, kann nicht [!INCLUDE[vbprvblong](../../includes/vbprvblong-md.md)] in ein VSTA-Skript konvertiert werden, das verwendet [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csharp_orcas_long](../../includes/csharp-orcas-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4812f-119">You cannot convert a VSA script that uses [!INCLUDE[vbprvblong](../../includes/vbprvblong-md.md)] to a VSTA script that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csharp_orcas_long](../../includes/csharp-orcas-long-md.md)].</span></span> <span data-ttu-id="4812f-120">Sie können jedoch ein neues VSTA-Skript erstellen, das verwendet [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csharp_orcas_long](../../includes/csharp-orcas-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4812f-120">However, you can create a new VSTA script that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csharp_orcas_long](../../includes/csharp-orcas-long-md.md)].</span></span> <span data-ttu-id="4812f-121">Weitere Informationen finden Sie unter [Coding and Debugging the Script Task](../../integration-services/control-flow/script-task.md) (Codieren und Debuggen des Skripttasks) und [Coding and Debugging the Script Component](../../integration-services/data-flow/transformations/script-component.md) (Codieren und Debuggen der Skriptkomponente).</span><span class="sxs-lookup"><span data-stu-id="4812f-121">For more information, see [Coding and Debugging the Script Task](../../integration-services/control-flow/script-task.md) and [Coding and Debugging the Script Component](../../integration-services/data-flow/transformations/script-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4812f-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4812f-122">See Also</span></span>  
 [<span data-ttu-id="4812f-123">Erweitern von Paketen mit Skripts</span><span class="sxs-lookup"><span data-stu-id="4812f-123">Extending Packages with Scripting</span></span>](../../relational-databases/server-management-objects-smo/tasks/scripting.md)  
  
  
