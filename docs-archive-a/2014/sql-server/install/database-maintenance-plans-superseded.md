---
title: Erersetzte Datenbank-Wartungspläne | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- suspended database maintenance plans
- database maintenance plans [SQL Server Agent]
- maintenance plans [SQL Server Agent]
ms.assetid: efac127c-6c81-4c7a-a6c4-9aae5d15545d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 3aea75cc4ecc94ccbaeb1f35cecd0b18ff3a65ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608244"
---
# <a name="database-maintenance-plans-superseded"></a><span data-ttu-id="1f824-102">Außer Kraft gesetzte Datenbank-Wartungspläne</span><span class="sxs-lookup"><span data-stu-id="1f824-102">Database maintenance plans superseded</span></span>
    
## <a name="component"></a><span data-ttu-id="1f824-103">Komponente</span><span class="sxs-lookup"><span data-stu-id="1f824-103">Component</span></span>  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="1f824-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Agent</span><span class="sxs-lookup"><span data-stu-id="1f824-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="1f824-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1f824-105">Description</span></span>  
 <span data-ttu-id="1f824-106">Vorhandene Datenbank-Wartungspläne werden aktualisiert und funktionieren weiterhin.</span><span class="sxs-lookup"><span data-stu-id="1f824-106">Existing database maintenance plans are upgraded and continue to work.</span></span> <span data-ttu-id="1f824-107">Sie können allerdings keine neuen Datenbank-Wartungspläne mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] erstellen.</span><span class="sxs-lookup"><span data-stu-id="1f824-107">However, you will not be able to create new database maintenance plans by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="1f824-108">Um die Wartungspläne im Objekt-Explorer anzuzeigen, erweitern Sie Verwaltung und dann Legacy.</span><span class="sxs-lookup"><span data-stu-id="1f824-108">To view the maintenance plans in Object Explorer, expand Management, and then expand Legacy.</span></span> <span data-ttu-id="1f824-109">Sie können vorhandene Daten Bank Wartungspläne in das neue Format migrieren, indem Sie im Kontextmenü für einen beliebigen Datenbank-Wartungsplan **Migrieren** auswählen.</span><span class="sxs-lookup"><span data-stu-id="1f824-109">You can migrate existing database maintenance plans to the new format by selecting **Migrate** from the context menu for any database maintenance plan.</span></span> <span data-ttu-id="1f824-110">Da die neue Wartungsplanfunktion kein direkter Ersatz der Datenbank-Wartungspläne ist, stehen möglicherweise einige Funktionen nach der Migration nicht mehr zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1f824-110">Because the new maintenance plan feature is not a direct replacement of database maintenance plans, some functionality might be lost after migration.</span></span> <span data-ttu-id="1f824-111">Bei der Migration eines Datenbank-Wartungsplans wird der alte Plan nicht gelöscht, sodass Sie seine Funktionalität als Wartungsplan testen können, bevor Sie den alten Plan entfernen.</span><span class="sxs-lookup"><span data-stu-id="1f824-111">Migrating a database maintenance plan does not delete the old plan, so you can test its functionality as a maintenance plan before removing the old plan.</span></span>  
  
 <span data-ttu-id="1f824-112">Die folgenden Funktionen werden innerhalb der Datenbank-Wartungspläne nicht mehr unterstützt:</span><span class="sxs-lookup"><span data-stu-id="1f824-112">The following features are no longer supported within database maintenance plans:</span></span>  
  
-   <span data-ttu-id="1f824-113">Protokollversand</span><span class="sxs-lookup"><span data-stu-id="1f824-113">Log shipping</span></span>  
  
-   <span data-ttu-id="1f824-114">Der **Versuch, geringfügige Probleme zu beheben,** der Task " **Daten Bank Integritätsprüfung** "</span><span class="sxs-lookup"><span data-stu-id="1f824-114">The **Attempt to repair any minor problems** option of the **Database Integrity Check** task</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="1f824-115">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="1f824-115">Corrective Action</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1f824-116">verhindert ein Einschließen des Protokollversands in Datenbankwartungspläne.</span><span class="sxs-lookup"><span data-stu-id="1f824-116">prevents log shipping from being included in a database maintenance plan.</span></span> <span data-ttu-id="1f824-117">Weitere Informationen finden Sie unter "Protokollversand" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="1f824-117">For more information, see "Log Shipping" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
  
