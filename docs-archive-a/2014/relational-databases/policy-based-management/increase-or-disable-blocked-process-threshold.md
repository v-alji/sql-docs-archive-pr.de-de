---
title: Erhöhen oder Deaktivieren des Schwellenwerts für blockierte Prozesse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 71db8ef6-341b-4465-99db-5c63e48d4c7d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a7a90aea3fa8fb4d9c423cea1ec6008b01cde883
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609181"
---
# <a name="increase-or-disable-blocked-process-threshold"></a><span data-ttu-id="afe2a-102">Erhöhen oder Deaktivieren des Schwellenwerts für blockierte Prozesse</span><span class="sxs-lookup"><span data-stu-id="afe2a-102">Increase or Disable Blocked Process Threshold</span></span>
  <span data-ttu-id="afe2a-103">Diese Regel überprüft, ob die Option Schwellenwert für blockierte Prozesse auf 0 (deaktiviert) oder auf einen Wert größer oder gleich 5 (Sekunden) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="afe2a-103">This rules checks that the blocked process threshold option is set to 0 (disabled) or set to a value higher than or equal to 5 (seconds).</span></span> <span data-ttu-id="afe2a-104">Ein Festlegen der Option Schwellenwert für blockierte Prozesse auf einen Wert von 1 bis 4 kann dazu führen, dass die Deadlocküberwachung permanent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="afe2a-104">Setting the blocked process threshold option to a value from 1 to 4 can cause the deadlock monitor to run constantly.</span></span> <span data-ttu-id="afe2a-105">Die Werte 1 bis 4 sollten nur bei der Problembehandlung und niemals langfristig oder in einer Produktionsumgebung ohne Unterstützung des Kundendiensts und -supports von [!INCLUDE[msCoName](../../includes/msconame-md.md)] verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="afe2a-105">Values 1 to 4 should only be used for troubleshooting, and never long term or in a production environment without the assistance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="afe2a-106">Empfehlungen zu Best Practices</span><span class="sxs-lookup"><span data-stu-id="afe2a-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="afe2a-107">Um dieses Problem zu lösen, legen Sie die Option Schwellenwert für blockierte Prozesse auf den Wert 5 (Sekunden) oder höher fest, oder deaktivieren Sie den Schwellenwert für blockierte Prozesse, indem Sie den Wert auf 0 (null) festlegen.</span><span class="sxs-lookup"><span data-stu-id="afe2a-107">To resolve this problem, set the blocked process threshold option to a value of 5 (seconds) or higher, or disable blocked process threshold by setting the value to 0.</span></span> <span data-ttu-id="afe2a-108">Führen Sie die folgende Anweisung aus, um den Schwellenwert für blockierte Prozesse auf den Wert `5` Sekunden festzulegen:</span><span class="sxs-lookup"><span data-stu-id="afe2a-108">To set the blocked process threshold to a value of `5` seconds, execute the following statement:</span></span>  
  
```  
sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE ;  
GO  
sp_configure 'blocked process threshold', 5 ;  
GO  
RECONFIGURE ;  
GO  
```  
  
## <a name="for-more-information"></a><span data-ttu-id="afe2a-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="afe2a-109">For More Information</span></span>  
 [<span data-ttu-id="afe2a-110">Schwellenwert für blockierte Prozesse (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="afe2a-110">blocked process threshold Server Configuration Option</span></span>](../../database-engine/configure-windows/blocked-process-threshold-server-configuration-option.md)  
  
## <a name="see-also"></a><span data-ttu-id="afe2a-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="afe2a-111">See Also</span></span>  
 [<span data-ttu-id="afe2a-112">Überwachen und Erzwingen von Best Practices mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="afe2a-112">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
