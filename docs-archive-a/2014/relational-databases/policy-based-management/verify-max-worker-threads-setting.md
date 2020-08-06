---
title: Überprüfen Sie die Max Worker Threads Einstellung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 2d94adfd-3ba1-493a-b29a-b436f9d583df
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5dbffb87f58d2beb633f43ff18680222ea62cf5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615984"
---
# <a name="verify-max-worker-threads-setting"></a><span data-ttu-id="b5204-102">Überprüfen der Einstellung 'Max. Anzahl von Arbeitsthreads'</span><span class="sxs-lookup"><span data-stu-id="b5204-102">Verify Max Worker Threads Setting</span></span>
  <span data-ttu-id="b5204-103">Diese Regel überprüft die Serveroption Max. Anzahl von Arbeitsthreads auf potenziell falsche Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="b5204-103">This rule checks the max worker threads server option for potentially incorrect settings.</span></span> <span data-ttu-id="b5204-104">Das Festlegen der Option Max. Anzahl von Arbeitsthreads auf einen niedrigen Wert verhindert die prompte Reaktion vieler Threads auf eingehende Clientanforderungen, was dazu führen kann, dass Threads nicht mehr auf die CPU zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="b5204-104">Setting the max worker threads option to a small value may prevent enough threads from servicing incoming client requests in a timely manner and could lead to "thread starvation".</span></span> <span data-ttu-id="b5204-105">Legen Sie die Option jedoch auf einen hohen Wert fest, wird möglicherweise Adressraum verschwendet, da jeder aktive Thread auf 32-Bit-Servern 512 KB und auf 64-Bit-Servern 4 MB Speicherplatz in Anspruch nimmt.</span><span class="sxs-lookup"><span data-stu-id="b5204-105">However, setting the option to a large value can waste address space, because each active thread consumes 512 KB on 32-bit servers and up to 4 MB on 64-bit servers.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="b5204-106">Empfehlungen zu Best Practices</span><span class="sxs-lookup"><span data-stu-id="b5204-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="b5204-107">Legen Sie die max. Anzahl von NIB-Arbeitsthreads (Option) auf 0 fest.</span><span class="sxs-lookup"><span data-stu-id="b5204-107">Set the max worker threads option to 0.</span></span> <span data-ttu-id="b5204-108">Dadurch ermittelt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] basierend auf den Benutzeranforderungen automatisch die richtige Anzahl aktiver Arbeitsthreads.</span><span class="sxs-lookup"><span data-stu-id="b5204-108">This enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to automatically determine the correct number of active worker threads based on user requests.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="b5204-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b5204-109">For More Information</span></span>  
 [<span data-ttu-id="b5204-110">Konfigurieren der Serverkonfigurationsoption Maximale Anzahl von Arbeitsthreads</span><span class="sxs-lookup"><span data-stu-id="b5204-110">Configure the max worker threads Server Configuration Option</span></span>](../../database-engine/configure-windows/configure-the-max-worker-threads-server-configuration-option.md)  
  
## <a name="see-also"></a><span data-ttu-id="b5204-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b5204-111">See Also</span></span>  
 [<span data-ttu-id="b5204-112">Überwachen und Erzwingen von Best Practices mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="b5204-112">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
