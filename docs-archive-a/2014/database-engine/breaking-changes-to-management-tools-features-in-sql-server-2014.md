---
title: Wichtige Änderungen an Funktionen der Verwaltungs Tools in SQL Server 2014 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/27/2018
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 3ff3fad8-b569-4516-bd58-5a3efeb537e2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0487b6ab0958e0b83d4e8e34be507b5b3211ac87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619379"
---
# <a name="breaking-changes-to-management-tools-features-in-sql-server-2014"></a><span data-ttu-id="58e2a-102">Wichtige Änderungen an Funktionen der Verwaltungstools in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="58e2a-102">Breaking Changes to Management Tools Features in SQL Server 2014</span></span>
  <span data-ttu-id="58e2a-103">In diesem Thema werden aktuelle Änderungen an Funktionen der Verwaltungstools beschrieben.</span><span class="sxs-lookup"><span data-stu-id="58e2a-103">This topic describes breaking changes to management tools features.</span></span> <span data-ttu-id="58e2a-104">Diese Änderungen können u. U. zur Funktionsunfähigkeit von Anwendungen, Skripts oder Funktionen führen, die auf früheren Versionen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]basieren.</span><span class="sxs-lookup"><span data-stu-id="58e2a-104">These changes might break applications, scripts, or functionalities that are based on earlier versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="58e2a-105">Diese Probleme können nach einem Upgrade auftreten.</span><span class="sxs-lookup"><span data-stu-id="58e2a-105">You might encounter these issues when you upgrade.</span></span> <span data-ttu-id="58e2a-106">Weitere Informationen finden Sie unter [Use Upgrade Advisor to Prepare for Upgrades](../../2014/sql-server/install/use-upgrade-advisor-to-prepare-for-upgrades.md).</span><span class="sxs-lookup"><span data-stu-id="58e2a-106">For more information, see [Use Upgrade Advisor to Prepare for Upgrades](../../2014/sql-server/install/use-upgrade-advisor-to-prepare-for-upgrades.md).</span></span>  
  
## <a name="breaking-changes-in-sssql14"></a><span data-ttu-id="58e2a-107">Wichtige Änderungen in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58e2a-107">Breaking Changes in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]</span></span>  
 <span data-ttu-id="58e2a-108">Informationen werden später bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="58e2a-108">Information to come later.</span></span>  
  
## <a name="breaking-changes-in-sssql11"></a><span data-ttu-id="58e2a-109">Wichtige Änderungen in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58e2a-109">Breaking Changes in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]</span></span>  
  
### <a name="you-cannot-use-sssql11-management-tools-to-create-a-utility-control-point-on-a-sskilimanjaro-instance-of-sql-server"></a><span data-ttu-id="58e2a-110">Sie können keine [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] -Verwaltungstools zum Erstellen eines Steuerungspunkts für das Hilfsprogramm auf einer [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] -Instanz von SQL Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="58e2a-110">You cannot use [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] Management Tools to create a utility control point on a [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] instance of SQL Server</span></span>  
 <span data-ttu-id="58e2a-111">Verwenden Sie [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)]-Verwaltungstools, um auf einer Instanz von [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] einen Steuerungspunkt für das Hilfsprogramm zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="58e2a-111">To create a utility control point on an instance of [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)], use [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] Management Tools.</span></span>  
  
### <a name="smo-has-been-reversioned-in-sssql11"></a><span data-ttu-id="58e2a-112">SMO liegt in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] in einer neuen Version vor.</span><span class="sxs-lookup"><span data-stu-id="58e2a-112">SMO has been reversioned in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]</span></span>  
 <span data-ttu-id="58e2a-113">Mit SMO aus [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] oder früheren Versionen entwickelter Code kann nicht ohne kleinere Änderungen für [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="58e2a-113">Code developed with SMO from [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] or earlier versions might not build against [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] without minor modifications.</span></span> <span data-ttu-id="58e2a-114">Weitere Informationen finden Sie unter [Backward Compatibility in SMO](../relational-databases/server-management-objects-smo/backward-compatibility-in-smo.md).</span><span class="sxs-lookup"><span data-stu-id="58e2a-114">For more information, see [Backward Compatibility in SMO](../relational-databases/server-management-objects-smo/backward-compatibility-in-smo.md).</span></span>  

## <a name="breaking-changes-in-sql-server-2005"></a><a name="previous-versions"></a><span data-ttu-id="58e2a-115">Wichtige Änderungen in SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="58e2a-115">Breaking Changes in SQL Server 2005</span></span>  

[!INCLUDE[Archived documentation for very old versions of SQL Server](../includes/paragraph-content/previous-versions-archive-documentation-sql-server.md)]

## <a name="see-also"></a><span data-ttu-id="58e2a-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="58e2a-116">See Also</span></span>  
 [<span data-ttu-id="58e2a-117">Abwärtskompatibilität</span><span class="sxs-lookup"><span data-stu-id="58e2a-117">Backward Compatibility</span></span>](../../2014/getting-started/backward-compatibility.md)  
 [<span data-ttu-id="58e2a-118">Weitere Informationen zu wichtigen Änderungen an Funktionen der Verwaltungs Tools in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="58e2a-118">More about Breaking Changes to Management Tools Features in SQL Server 2014</span></span>](breaking-changes-to-database-engine-features-in-sql-server-2016.md?view=sql-server-2014)  
  
  
