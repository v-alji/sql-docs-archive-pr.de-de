---
title: Änderungen am Verhalten in syslockinfo und sp_lock | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- syslockinfo
- sp_lock
ms.assetid: b9892ae3-ac15-48be-8b52-78dbed6467ed
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 65ace190004cab911dd8996642720620eba94935
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617520"
---
# <a name="changes-to-behavior-in-syslockinfo-and-sp_lock"></a><span data-ttu-id="b08b6-102">Änderungen am Verhalten von 'syslockinfo' und 'sp_lock'</span><span class="sxs-lookup"><span data-stu-id="b08b6-102">Changes to behavior in syslockinfo and sp_lock</span></span>
  <span data-ttu-id="b08b6-103">**syslockinfo** und **sp_lock** können unerwartete Werte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="b08b6-103">**syslockinfo** and **sp_lock** may return unexpected values.</span></span> <span data-ttu-id="b08b6-104">Sie können auch zusätzliche Zeilen zurückgeben, während vorherige Versionen von **syslockinfo** und **sp_lock** maximal zwei Zeilen pro Sperr Ressource zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="b08b6-104">They may also return additional rows, whereas previous versions of **syslockinfo** and **sp_lock** returned a maximum of two rows per lock resource.</span></span>  
  
 <span data-ttu-id="b08b6-105">Um auf Informationen von **syslockinfo** zuzugreifen oder **sp_lock** auszuführen, ist die View Server State-Berechtigung auf dem Server erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b08b6-105">To access information from **syslockinfo** or execute **sp_lock** requires VIEW SERVER STATE permission on the server.</span></span>  
  
## <a name="component"></a><span data-ttu-id="b08b6-106">Komponente</span><span class="sxs-lookup"><span data-stu-id="b08b6-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="b08b6-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b08b6-107">Description</span></span>  
 <span data-ttu-id="b08b6-108">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] werden die Spalten **rsc_objid** und **rsc_indid** in **syslockinfo** und die Spalten **objID** und **indid** in **sp_lock** die Objekt-ID und die Index-ID konsistent zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="b08b6-108">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], the **rsc_objid** and **rsc_indid** columns in **syslockinfo** and the **objid** and **indid** columns in **sp_lock** consistently return the object ID and index ID.</span></span> <span data-ttu-id="b08b6-109">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] kann der Wert 0 (null) zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b08b6-109">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], a value of 0 may be returned.</span></span>  
  
 <span data-ttu-id="b08b6-110">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] geben **syslockinfo** und **sp_lock** in einer einzelnen Transaktion maximal zwei Zeilen für eine bestimmte Sperr Ressource zurück.</span><span class="sxs-lookup"><span data-stu-id="b08b6-110">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], **syslockinfo** and **sp_lock** return a maximum of two rows for any given lock resource in a single transaction.</span></span> <span data-ttu-id="b08b6-111">Wenn die Sperrenpartitionierung aktiviert ist, werden ab [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] möglicherweise mehrere Zeilen für dieselbe Ressource zurückgegeben, die unter einer Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b08b6-111">Starting with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], when lock partitioning is enabled, multiple rows for the same resource running under one transaction may be returned.</span></span> <span data-ttu-id="b08b6-112">Möglicherweise werden bis zu n + 1 Zeilen zurückgegeben, wobei N die Anzahl der CPUs ist.</span><span class="sxs-lookup"><span data-stu-id="b08b6-112">There may be up to N + 1 rows returned, where N is the number of CPUs.</span></span> <span data-ttu-id="b08b6-113">Außerdem können die GRANTED-Anforderung und die WAITING-Anforderung jetzt für dieselbe Ressource angezeigt werden, was in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] nicht möglich war.</span><span class="sxs-lookup"><span data-stu-id="b08b6-113">Also, it is now possible to have GRANTED and WAITING requests displayed for the same resource, which was not possible in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="b08b6-114">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b08b6-114">Permissions</span></span>  
 <span data-ttu-id="b08b6-115">Erfordert die VIEW SERVER STATE-Berechtigung auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="b08b6-115">Requires VIEW SERVER STATE permission on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b08b6-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b08b6-116">See Also</span></span>  
 <span data-ttu-id="b08b6-117">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="b08b6-117">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="b08b6-118">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="b08b6-118">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
