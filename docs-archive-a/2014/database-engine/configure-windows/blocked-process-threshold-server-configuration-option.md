---
title: Schwellenwert für blockierte Prozesse (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- thresholds [SQL Server]
- blocked process threshold option
ms.assetid: 3d46d143-bc6a-4220-8b55-6baa37547c25
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9d5b61aaf23a8e74cb11afbf4e8bdb958fde6abe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721750"
---
# <a name="blocked-process-threshold-server-configuration-option"></a><span data-ttu-id="2e100-102">Schwellenwert für blockierte Prozesse (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="2e100-102">blocked process threshold Server Configuration Option</span></span>
  <span data-ttu-id="2e100-103">Mit der Option **Schwellenwert für blockierte Prozesse** geben Sie den Schwellenwert in Sekunden an, bei dem Berichte zu blockierten Prozessen generiert werden.</span><span class="sxs-lookup"><span data-stu-id="2e100-103">Use the **blocked process threshold** option to specify the threshold, in seconds, at which blocked process reports are generated.</span></span> <span data-ttu-id="2e100-104">Der Schwellenwert kann auf einen Wert zwischen 0 und 86.400 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2e100-104">The threshold can be set from 0 to 86,400.</span></span> <span data-ttu-id="2e100-105">Standardmäßig werden für blockierte Prozesse keine Berichte erstellt.</span><span class="sxs-lookup"><span data-stu-id="2e100-105">By default, no blocked process reports are produced.</span></span> <span data-ttu-id="2e100-106">Dieses Ereignis wird nicht für Systemtasks und Tasks generiert, die auf Ressourcen warten, die keine bekannten Deadlocks generieren.</span><span class="sxs-lookup"><span data-stu-id="2e100-106">This event is not generated for system tasks or for tasks that are waiting on resources that do not generate detectable deadlocks.</span></span>  
  
 <span data-ttu-id="2e100-107">Sie können eine [Warnung](../../ssms/agent/alerts.md) festlegen, die bei der Generierung dieses Ereignisses erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="2e100-107">You can define an [alert](../../ssms/agent/alerts.md) to be executed when this event is generated.</span></span> <span data-ttu-id="2e100-108">So können Sie beispielsweise angeben, dass Administrator eine Aufforderung zur Ergreifung der geeigneten Maßnahmen erhalten soll, um die Blockierung zu lösen.</span><span class="sxs-lookup"><span data-stu-id="2e100-108">So for example, you can choose to page the administrator to take appropriate action to handle the blocking situation.</span></span>  
  
 <span data-ttu-id="2e100-109">Für den Schwellenwert für blockierte Prozesse wird der Hintergrundthread der Deadlocküberwachung verwendet, um auf einen Zeitwert zu warten, der größer oder ein Vielfaches des konfigurierten Schwellenwerts ist.</span><span class="sxs-lookup"><span data-stu-id="2e100-109">Blocked process threshold uses the deadlock monitor background thread to walk through the list of tasks waiting for a time greater than or multiples of the configured threshold.</span></span> <span data-ttu-id="2e100-110">Das Ereignis wird pro Berichtsintervall einmal für jeden blockierten Task generiert.</span><span class="sxs-lookup"><span data-stu-id="2e100-110">The event is generated once per reporting interval for each of the blocked tasks.</span></span>  
  
 <span data-ttu-id="2e100-111">Der Bericht zu blockierten Prozessen erfolgt auf Grundlage der besten Leistung.</span><span class="sxs-lookup"><span data-stu-id="2e100-111">The blocked process report is done on a best effort basis.</span></span> <span data-ttu-id="2e100-112">Eine Berichterstellung in Echtzeit oder annähernder Echtzeit kann nicht sichergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2e100-112">There is no guarantee of any real-time or even close to real-time reporting.</span></span>  
  
 <span data-ttu-id="2e100-113">Die Einstellung tritt ohne Beenden und Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="2e100-113">The setting takes effect immediately without a server stop and restart.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2e100-114">Beispiele</span><span class="sxs-lookup"><span data-stu-id="2e100-114">Examples</span></span>  
 <span data-ttu-id="2e100-115">Im folgenden Beispiel wird der Wert für `blocked process threshold` auf `20` Sekunden festgelegt. Hiermit wird für jeden blockierten Task ein Bericht zu blockierten Prozessen generiert.</span><span class="sxs-lookup"><span data-stu-id="2e100-115">The following example sets the `blocked process threshold` to `20` seconds, generating a blocked process report for each task that is blocked.</span></span>  
  
```  
sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE ;  
GO  
sp_configure 'blocked process threshold', 20 ;  
GO  
RECONFIGURE ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="2e100-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2e100-116">See Also</span></span>  
 <span data-ttu-id="2e100-117">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2e100-117">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 [<span data-ttu-id="2e100-118">Blocked Process Report-Ereignisklasse</span><span class="sxs-lookup"><span data-stu-id="2e100-118">Blocked Process Report Event Class</span></span>](../../relational-databases/event-classes/blocked-process-report-event-class.md)  
  
  
