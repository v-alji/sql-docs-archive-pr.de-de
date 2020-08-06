---
title: Eigenständige Datenbanken bei Always On-Verfügbarkeitsgruppen (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- contained database [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: cacce3ae-e940-4566-8298-6607c4268e74
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 74c8a0b41ee7224dad83fb41691a4898c15b7b38
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608862"
---
# <a name="contained-databases-with-always-on-availability-groups-sql-server"></a><span data-ttu-id="58beb-102">Eigenständige Datenbanken bei Always On-Verfügbarkeitsgruppen (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="58beb-102">Contained Databases with Always On Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="58beb-103">Dieses Thema enthält Informationen zum Verwenden einer eigenständigen Datenbank in [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] mit [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58beb-103">This topic contains information about the using a contained database with [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="58beb-104">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="58beb-104">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="58beb-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="58beb-105">Prerequisites</span></span>](#Prerequisites)  
  
-   [<span data-ttu-id="58beb-106">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="58beb-106">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="58beb-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="58beb-107">Prerequisites</span></span>  
  
-   <span data-ttu-id="58beb-108">Vor dem Hinzufügen einer enthaltenen Datenbank zu einer Verfügbarkeitsgruppe muss gewährleistet sein, dass die Serveroption `contained database authentication` auf jeder Serverinstanz, die ein Verfügbarkeitsreplikat für die Verfügbarkeitsgruppe hostet, auf `1` gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="58beb-108">Before adding a contained database to an availability group, ensure that the `contained database authentication` server option is set to `1` on every server instance that hosts an availability replica for the availability group.</span></span> <span data-ttu-id="58beb-109">Weitere Informationen finden Sie unter [Contained Database Authentication (Serverkonfigurationsoption)](../../configure-windows/contained-database-authentication-server-configuration-option.md) und [Serverkonfigurationsoptionen &#40;SQL Server&#41;](../../configure-windows/server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="58beb-109">For more information, see [contained database authentication Server Configuration Option](../../configure-windows/contained-database-authentication-server-configuration-option.md) and [Server Configuration Options &#40;SQL Server&#41;](../../configure-windows/server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="58beb-110">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="58beb-110">Related Tasks</span></span>  
  
-   [<span data-ttu-id="58beb-111">Serverkonfigurationsoptionen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="58beb-111">Server Configuration Options &#40;SQL Server&#41;</span></span>](../../configure-windows/server-configuration-options-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="58beb-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="58beb-112">See Also</span></span>  
 <span data-ttu-id="58beb-113">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="58beb-113">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="58beb-114">Eigenständige Datenbanken</span><span class="sxs-lookup"><span data-stu-id="58beb-114">Contained Databases</span></span>](../../../relational-databases/databases/contained-databases.md)  
  
  
