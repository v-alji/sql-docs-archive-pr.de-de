---
title: Affinity64 Mask (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- processor affinity [SQL Server]
- affinity64 mask option
- binding processors [SQL Server]
ms.assetid: 75ed08c7-f85c-4e15-9ee1-e7bc545d3293
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d2ea6d2e364feaa67d91de0055617aac9dc285ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619349"
---
# <a name="affinity64-mask-server-configuration-option"></a><span data-ttu-id="fdbc4-102">Affinity64 Mask (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="fdbc4-102">affinity64 mask Server Configuration Option</span></span>
  <span data-ttu-id="fdbc4-103">Durch Affinity64 Mask werden Prozessoren an bestimmte Threads gebunden, ähnlich wie bei der Option Affinity Mask.</span><span class="sxs-lookup"><span data-stu-id="fdbc4-103">The affinity64 mask binds processors to specific threads, similar to the affinity mask option.</span></span> <span data-ttu-id="fdbc4-104">Verwenden Sie Affinity Mask, um die ersten 32 Prozessoren zu binden. Mit Affinity64 Mask binden Sie die restlichen Prozessoren auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="fdbc4-104">Use affinity mask to bind the first 32 processors, and use affinity64 mask to bind the remaining processors on the computer.</span></span> <span data-ttu-id="fdbc4-105">Diese Option wird nur in der 64-Bit-Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fdbc4-105">This option is only visible on the 64-bit version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoteDepNextAvoid](../../includes/ssnotedepnextavoid-md.md)] <span data-ttu-id="fdbc4-106">Verwenden Sie stattdessen [ALTER SERVER CONFIGURATION (Transact-SQL)](/sql/t-sql/statements/alter-server-configuration-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fdbc4-106">Use [ALTER SERVER CONFIGURATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-server-configuration-transact-sql) instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdbc4-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fdbc4-107">See Also</span></span>  
 <span data-ttu-id="fdbc4-108">[Affinitätsmaske (Serverkonfigurationsoption)](affinity-mask-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="fdbc4-108">[affinity mask Server Configuration Option](affinity-mask-server-configuration-option.md) </span></span>  
 <span data-ttu-id="fdbc4-109">[Überwachen der Ressourcenverwendung &#40;Systemmonitor&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="fdbc4-109">[Monitor Resource Usage &#40;System Monitor&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md) </span></span>  
 <span data-ttu-id="fdbc4-110">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fdbc4-110">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="fdbc4-111">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fdbc4-111">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="fdbc4-112">RECONFIGURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fdbc4-112">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  
