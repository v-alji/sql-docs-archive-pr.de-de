---
title: SQL Server Abwärtskompatibilität | Microsoft-Dokumentation
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ac47cb74-5578-417d-bcef-f970d9527705
author: rothja
ms.author: jroth
ms.openlocfilehash: a4d38041ce4daa12911dc706d382460324931c90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698457"
---
# <a name="sql-server-backward-compatibility"></a><span data-ttu-id="8de1c-102">SQL Server-Abwärtskompatibilität</span><span class="sxs-lookup"><span data-stu-id="8de1c-102">SQL Server Backward Compatibility</span></span>
  <span data-ttu-id="8de1c-103">In den Themen zur Abwärtskompatibilität werden Änderungen beschrieben, die in den verschiedenen Versionen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] zu einem abweichenden Verhalten von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]führen.</span><span class="sxs-lookup"><span data-stu-id="8de1c-103">Topics in the backward compatibility section describe changes in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] behavior between versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8de1c-104">Zu den Funktionen, auf die in diesem Themenbereich eingegangen wird, gehören Datenprogrammierbarkeit, Oberflächen-Konfigurationstools, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Setup, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Dienste und andere umfassendere Änderungen der Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="8de1c-104">Features included in this topic area include data programmability, surface area configuration tools, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Setup, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] services, and other broad functionality changes.</span></span>  
  
|<span data-ttu-id="8de1c-105">Thema</span><span class="sxs-lookup"><span data-stu-id="8de1c-105">Topic</span></span>|<span data-ttu-id="8de1c-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8de1c-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="8de1c-107">Als veraltet markierte SQL Server-Funktionen in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="8de1c-107">Deprecated SQL Server Features in SQL Server 2014</span></span>](../../2014/getting-started/deprecated-sql-server-features-in-sql-server-2014.md)|<span data-ttu-id="8de1c-108">Als veraltet markierte [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Funktionen in dieser Version.</span><span class="sxs-lookup"><span data-stu-id="8de1c-108">Deprecated [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] features in this release.</span></span> <span data-ttu-id="8de1c-109">In diesem Thema werden die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Konfiguration und die Setupfunktionen erläutert.</span><span class="sxs-lookup"><span data-stu-id="8de1c-109">This topic covers [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration, and Setup functionality.</span></span>|  
|[<span data-ttu-id="8de1c-110">Nicht mehr unterstützte SQL Server-Funktionen in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="8de1c-110">Discontinued SQL Server Features in SQL Server 2014</span></span>](../../2014/getting-started/discontinued-sql-server-features-in-sql-server-2014.md)|<span data-ttu-id="8de1c-111">Nicht mehr unterstützte [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Funktionalität in dieser Version.</span><span class="sxs-lookup"><span data-stu-id="8de1c-111">Discontinued [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] functionality in this release.</span></span> <span data-ttu-id="8de1c-112">In diesem Thema werden die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Konfiguration und die Setupfunktionen erläutert.</span><span class="sxs-lookup"><span data-stu-id="8de1c-112">This topic covers [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration, and Setup functionality.</span></span>|  
|[<span data-ttu-id="8de1c-113">Wichtige Änderungen von SQL Server-Funktionen in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="8de1c-113">Breaking Changes to SQL Server Features in SQL Server 2014</span></span>](../../2014/getting-started/breaking-changes-to-sql-server-features-in-sql-server-2014.md)|<span data-ttu-id="8de1c-114">Änderungen, die notwendige Änderungen an Anwendungen nach sich ziehen können.</span><span class="sxs-lookup"><span data-stu-id="8de1c-114">Changes that might require changes to applications.</span></span> <span data-ttu-id="8de1c-115">In diesem Thema werden die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Konfiguration und die Setupfunktionen erläutert.</span><span class="sxs-lookup"><span data-stu-id="8de1c-115">This topic covers [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration, and Setup functionality.</span></span>|  
|[<span data-ttu-id="8de1c-116">Verhaltensänderungen von SQL Server-Features in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="8de1c-116">Behavior Changes to SQL Server Features in SQL Server 2014</span></span>](../../2014/getting-started/behavior-changes-to-sql-server-features-in-sql-server-2014.md)|<span data-ttu-id="8de1c-117">Verhaltensänderungen an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Funktionen in dieser Version.</span><span class="sxs-lookup"><span data-stu-id="8de1c-117">Behavioral  changes to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] features in this release.</span></span> <span data-ttu-id="8de1c-118">In diesem Thema werden die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Konfiguration und die Setupfunktionen erläutert.</span><span class="sxs-lookup"><span data-stu-id="8de1c-118">This topic covers [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration, and Setup functionality.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8de1c-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8de1c-119">See Also</span></span>  
 [<span data-ttu-id="8de1c-120">Abwärtskompatibilität</span><span class="sxs-lookup"><span data-stu-id="8de1c-120">Backward Compatibility</span></span>](../../2014/getting-started/backward-compatibility.md)  
  
  
