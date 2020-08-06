---
title: ServerProperty gibt das korrekte Ergebnis für die LCID-Eigenschaft in SQL Server 2005 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- SERVERPROPERTY function
ms.assetid: 833a2fc9-b480-4697-aa7b-9677e78ee0b4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ebb125a86e6e30f2c3638004593da7657f02f1a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700623"
---
# <a name="serverproperty-returns-correct-result-for-lcid-property-in-sql-server-2005"></a><span data-ttu-id="2b232-102">SERVERPROPERTY gibt korrektes Ergebnis für die LCID-Eigenschaft in SQL Server 2005 zurück</span><span class="sxs-lookup"><span data-stu-id="2b232-102">SERVERPROPERTY returns correct result for LCID property in SQL Server 2005</span></span>
  <span data-ttu-id="2b232-103">Wenn SERVERPROPERTY('LCID') für Server mit binärer Sortierung ausgeführt wird, gibt die Funktion den Windows-Gebietsschemabezeichner (LCID) zurück, der der Sortierung des Servers entspricht.</span><span class="sxs-lookup"><span data-stu-id="2b232-103">When SERVERPROPERTY('LCID') is run on binary collation servers, the function returns the Windows locale identifier (LCID) that corresponds to the collation of the server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b232-104">Bei Batch- oder Ablaufverfolgungsdateien, die Verweise auf SERVERPROPERTY ('LCID') enthalten und auf anderen Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgeführt werden, erkennt der Upgrade Advisor diese Verhaltensänderung nur dann, wenn die anderen Instanzen über dieselbe Sortierung verfügen wie die aktuelle Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b232-104">For batch and trace files that contain references to SERVERPROPERTY ('LCID') and are run on other instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Upgrade Advisor will detect this behavior change only if the other instances have the same collation as the current instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="2b232-105">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="2b232-105">Corrective Action</span></span>  
 <span data-ttu-id="2b232-106">Ändern Sie Anwendungen so, dass sie die Rückgabe des Windows-LCID, der der Sortierung des Servers entspricht, durch SERVERPROPERTY('LCID') erwarten.</span><span class="sxs-lookup"><span data-stu-id="2b232-106">Modify applications to expect SERVERPROPERTY('LCID') to return the Windows LCID that corresponds to the collation of the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b232-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2b232-107">See Also</span></span>  
 <span data-ttu-id="2b232-108">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="2b232-108">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="2b232-109">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="2b232-109">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
