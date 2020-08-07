---
title: Reporting Services Abwärtskompatibilität | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services, backward compatibility
- SSRS, backward compatibility
- SQL Server Reporting Services, backward compatibility
- backward compatibility [Reporting Services]
ms.assetid: 675b0e0e-cfee-4790-9675-80fc3ea6d30f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7203740ba7f52dfc2cd3793a20fed9fecf5f9468
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719507"
---
# <a name="reporting-services-backward-compatibility"></a><span data-ttu-id="5743c-102">Abwärtskompatibilität von Reporting Services</span><span class="sxs-lookup"><span data-stu-id="5743c-102">Reporting Services Backward Compatibility</span></span>
  <span data-ttu-id="5743c-103">In diesem Abschnitt werden Änderungen im Verhalten Zwischenversionen von beschrieben [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5743c-103">This section describes changes in behavior between versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="5743c-104">Es werden Funktionen behandelt, die nicht mehr verfügbar sind oder in einer zukünftigen Version entfernt.</span><span class="sxs-lookup"><span data-stu-id="5743c-104">It covers features that are no longer available or are scheduled to be removed in a future release.</span></span> <span data-ttu-id="5743c-105">Es werden außerdem grundlegende Änderungen am Produkt beschrieben, die bekanntermaßen eine benutzerdefinierte Anwendung unterbrechen, die die [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Funktionalität enthält.</span><span class="sxs-lookup"><span data-stu-id="5743c-105">It also describes fundamental changes to the product that are known to break a custom application that includes [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5743c-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5743c-106">In This Section</span></span>  
  
|<span data-ttu-id="5743c-107">Thema</span><span class="sxs-lookup"><span data-stu-id="5743c-107">Topic</span></span>|<span data-ttu-id="5743c-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5743c-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5743c-109">Nicht mehr unterstützte Funktionen in SQL Server Reporting Services in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="5743c-109">Discontinued Functionality to SQL Server Reporting Services in SQL Server 2014</span></span>](discontinued-functionality-to-sql-server-reporting-services-in-sql-server.md)|<span data-ttu-id="5743c-110">Beschreibt Funktionen, die in früheren Versionen von [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] vorhanden waren, jedoch in späteren Versionen entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="5743c-110">Describes features that existed in earlier versions of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] but that have been removed in later versions.</span></span>|  
|[<span data-ttu-id="5743c-111">Als veraltet markierte Funktionen in SQL Server Reporting Services in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="5743c-111">Deprecated Features in SQL Server Reporting Services in SQL Server 2014</span></span>](deprecated-features-in-sql-server-reporting-services-ssrs.md)|<span data-ttu-id="5743c-112">Beschreibt Funktionen, die in dieser Version von [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] aus Gründen der Abwärtskompatibilität beibehalten wurden, die aber in einer zukünftigen Version von SQL Server entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="5743c-112">Describes features that exist this release of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] for backward compatibility, but which will be removed in a future version of SQL Server.</span></span>|  
|[<span data-ttu-id="5743c-113">Aktuelle Änderungen in SQL Server Reporting Services in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="5743c-113">Breaking Changes in SQL Server Reporting Services in SQL Server 2014</span></span>](breaking-changes-in-sql-server-reporting-services-in-sql-server-2016.md)|<span data-ttu-id="5743c-114">Beschreibt Probleme, die beim Aktualisieren von [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]auftreten können.</span><span class="sxs-lookup"><span data-stu-id="5743c-114">Describes issues that you might encounter when you upgrade [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="5743c-115">Verhaltensänderungen in SQL Server Reporting Services in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="5743c-115">Behavior Changes to SQL Server Reporting Services  in SQL Server 2014</span></span>](behavior-changes-to-sql-server-reporting-services-in-sql-server-2016.md)|<span data-ttu-id="5743c-116">Beschreibt Funktionen, die in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="5743c-116">Describes features that have changed in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5743c-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5743c-117">See Also</span></span>  
 <span data-ttu-id="5743c-118">[Abwärtskompatibilität](../../2014/getting-started/backward-compatibility.md) </span><span class="sxs-lookup"><span data-stu-id="5743c-118">[Backward Compatibility](../../2014/getting-started/backward-compatibility.md) </span></span>  
 [<span data-ttu-id="5743c-119">Analysis Services Backward Compatibility</span><span class="sxs-lookup"><span data-stu-id="5743c-119">Analysis Services Backward Compatibility</span></span>](../../2014/analysis-services/analysis-services-backward-compatibility.md)  
  
  
