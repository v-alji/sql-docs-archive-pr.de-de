---
title: Festlegen der Datenbankoption AUTO_CLOSE auf OFF | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: e6b03364-263a-4ec4-9794-de9869d396ce
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: db6cf5a3f82c3493a8732958594743104fccc968
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724526"
---
# <a name="set-the-auto_close-database-option-to-off"></a><span data-ttu-id="3f214-102">Festlegen der Datenbankoption AUTO_CLOSE auf OFF</span><span class="sxs-lookup"><span data-stu-id="3f214-102">Set the AUTO_CLOSE Database Option to OFF</span></span>
  <span data-ttu-id="3f214-103">Diese Regel überprüft, ob die AUTO_CLOSE-Option auf OFF festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="3f214-103">This rule checks whether the AUTO_ CLOSE option is set OFF.</span></span> <span data-ttu-id="3f214-104">Wenn AUTO_CLOSE auf ON festgelegt ist, kann diese Option bei Datenbanken, auf die häufig zugegriffen wird, aufgrund des erhöhten Aufwands zum Öffnen und Schließen der Datenbank nach jeder Verbindung zu einer Leistungseinbuße führen.</span><span class="sxs-lookup"><span data-stu-id="3f214-104">When AUTO_CLOSE is set ON, this option can cause performance degradation on frequently accessed databases because of the increased overhead of opening and closing the database after each connection.</span></span> <span data-ttu-id="3f214-105">AUTO_CLOSE bewirkt auch die Leerung des Prozedurcaches nach jeder Verbindung.</span><span class="sxs-lookup"><span data-stu-id="3f214-105">AUTO_CLOSE also flushes the procedure cache after each connection.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="3f214-106">Empfehlungen zu Best Practices</span><span class="sxs-lookup"><span data-stu-id="3f214-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="3f214-107">Wenn auf eine Datenbank häufig zugegriffen wird, legen Sie die AUTO_CLOSE-Option für die Datenbank auf OFF fest.</span><span class="sxs-lookup"><span data-stu-id="3f214-107">If a database is accessed frequently, set the AUTO_CLOSE option to OFF for the database.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="3f214-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3f214-108">For More Information</span></span>  
 [<span data-ttu-id="3f214-109">ALTER DATABASE SET-Optionen &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3f214-109">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-set-options)  
  
## <a name="see-also"></a><span data-ttu-id="3f214-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3f214-110">See Also</span></span>  
 [<span data-ttu-id="3f214-111">Überwachen und Erzwingen von Best Practices mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="3f214-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
