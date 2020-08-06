---
title: Festlegen der AUTO_SHRINK-Datenbankoption auf OFF | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 16403850-d745-4754-b84f-5f01aaecd24e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 42d79ed13a691c3d39a28e7ab35a740a9f613fac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724525"
---
# <a name="set-the-auto_shrink-database-option-to-off"></a><span data-ttu-id="20cb7-102">Festlegen der AUTO_SHRINK-Datenbankoption auf OFF</span><span class="sxs-lookup"><span data-stu-id="20cb7-102">Set the AUTO_SHRINK Database Option to OFF</span></span>
  <span data-ttu-id="20cb7-103">Diese Regel überprüft, ob die AUTO_SHRINK-Datenbankoption auf OFF festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="20cb7-103">This rule checks whether the AUTO_SHRINK database option is set to OFF.</span></span> <span data-ttu-id="20cb7-104">Häufiges Verkleinern und Erweitern einer Datenbank kann zu physischer Fragmentierung führen.</span><span class="sxs-lookup"><span data-stu-id="20cb7-104">Frequently shrinking and expanding a database can lead to physical fragmentation.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="20cb7-105">Empfehlungen zu Best Practices</span><span class="sxs-lookup"><span data-stu-id="20cb7-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="20cb7-106">Legen Sie die AUTO_SHRINK-Datenbankoption auf OFF fest.</span><span class="sxs-lookup"><span data-stu-id="20cb7-106">Set the AUTO_SHRINK database option to OFF.</span></span> <span data-ttu-id="20cb7-107">Wenn Sie wissen, dass der freigegebene Speicherplatz in Zukunft nicht benötigt wird, können Sie den Speicherplatz durch manuelles Verkleinern der Datenbank freigeben.</span><span class="sxs-lookup"><span data-stu-id="20cb7-107">If you know that the space that you are reclaiming will not be needed in the future, you can reclaim the space by manually shrinking the database.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="20cb7-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="20cb7-108">For More Information</span></span>  
 <span data-ttu-id="20cb7-109">Microsoft Knowledge Base-Artikel [315512](https://go.microsoft.com/fwlink/?linkid=117750)</span><span class="sxs-lookup"><span data-stu-id="20cb7-109">Microsoft Knowledge Base article [315512](https://go.microsoft.com/fwlink/?linkid=117750)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20cb7-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="20cb7-110">See Also</span></span>  
 [<span data-ttu-id="20cb7-111">Überwachen und Erzwingen von Best Practices mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="20cb7-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
