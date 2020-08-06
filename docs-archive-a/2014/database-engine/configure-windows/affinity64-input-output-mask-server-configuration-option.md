---
title: affinity64 I/O mask (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- processor affinity [SQL Server]
- binding processors [SQL Server]
- affinity64 I/O mask option
ms.assetid: d304eae7-5116-40ee-a0fa-0a3c0bc20c01
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19616f5718254bde5601ea1beeec21412ad867de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619351"
---
# <a name="affinity64-input-output-mask-server-configuration-option"></a><span data-ttu-id="0b6bf-102">affinity64 I/O mask (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="0b6bf-102">affinity64 Input-Output mask Server Configuration Option</span></span>
  <span data-ttu-id="0b6bf-103">Die Option **affinity64 I/O mask** bindet die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenträger-E/A an eine bestimmte Teilmenge der CPUs. Diese Option verhält sich ähnlich wie die Option **affinity I/O mask** .</span><span class="sxs-lookup"><span data-stu-id="0b6bf-103">The **affinity64 I/O mask** binds [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disk I/O to a specified subset of CPUs, similar to the **affinity I/O mask** option.</span></span> <span data-ttu-id="0b6bf-104">Verwenden Sie **affinity I/O mask** , um die ersten 32 Prozessoren zu binden, und mit **affinity64 I/O mask** binden Sie die restlichen Prozessoren auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="0b6bf-104">Use **affinity I/O mask** to bind the first 32 processors, and use **affinity64 I/O mask** to bind the remaining processors on the computer.</span></span> <span data-ttu-id="0b6bf-105">Wenn Sie **affinity64 I/O mask**neu konfigurieren, müssen Sie die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]neu starten.</span><span class="sxs-lookup"><span data-stu-id="0b6bf-105">If you reconfigure the **affinity64 I/O mask**, you must restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0b6bf-106">Diese Option wird nur in der 64-Bit-Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b6bf-106">This option is only visible on the 64-bit version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b6bf-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0b6bf-107">See Also</span></span>  
 <span data-ttu-id="0b6bf-108">[Affinity I/O Mask (Serverkonfigurationsoption)](affinity-input-output-mask-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="0b6bf-108">[affinity Input-Output mask Server Configuration Option](affinity-input-output-mask-server-configuration-option.md) </span></span>  
 <span data-ttu-id="0b6bf-109">[Überwachen der Ressourcenverwendung &#40;Systemmonitor&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="0b6bf-109">[Monitor Resource Usage &#40;System Monitor&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md) </span></span>  
 <span data-ttu-id="0b6bf-110">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0b6bf-110">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="0b6bf-111">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0b6bf-111">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="0b6bf-112">RECONFIGURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0b6bf-112">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  
