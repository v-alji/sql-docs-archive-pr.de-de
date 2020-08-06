---
title: Verwenden von Datenbank-E-Mail anstelle von SQL Mail | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: b08df7be-d8be-4184-a661-38ec0ac85cd1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a6a957b65975645bdeb9f55faee4e650b53718b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615986"
---
# <a name="use-database-mail-instead-of-sql-mail"></a><span data-ttu-id="f55a6-102">Verwenden von Datenbank-E-Mail anstelle von SQL Mail</span><span class="sxs-lookup"><span data-stu-id="f55a6-102">Use Database Mail Instead of SQL Mail</span></span>
  <span data-ttu-id="f55a6-103">Diese Regel überprüft die sys.configurations-Katalogsicht, um zu bestimmen, ob die serverweite Konfigurationoption von SQL Mail XPs auf ON festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f55a6-103">This rule checks the sys.configurations catalog view to determine whether the SQL Mail XPs server-wide configuration option is set to ON.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="f55a6-104">Empfehlungen zu Best Practices</span><span class="sxs-lookup"><span data-stu-id="f55a6-104">Best Practices Recommendations</span></span>  
 <span data-ttu-id="f55a6-105">SQL Mail wird in einer zukünftigen Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]entfernt.</span><span class="sxs-lookup"><span data-stu-id="f55a6-105">SQL Mail will be removed in a future version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f55a6-106">Nutzen Sie diese Funktionen bei Neuentwicklungen nicht mehr, und planen Sie die Änderung von Anwendungen, die diese Funktion zurzeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="f55a6-106">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span> <span data-ttu-id="f55a6-107">Verwenden Sie zum Versenden von E-Mail-Nachrichten Datenbank-E-Mail.</span><span class="sxs-lookup"><span data-stu-id="f55a6-107">To send mail, use Database Mail.</span></span>  
  
 <span data-ttu-id="f55a6-108">SQL Mail wird prozessintern zum [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f55a6-108">SQL Mail runs in-process to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="f55a6-109">Wenn SQL Mail beendet wird, wird der Server ebenfalls beendet.</span><span class="sxs-lookup"><span data-stu-id="f55a6-109">If SQL Mail goes down, so does the server.</span></span> <span data-ttu-id="f55a6-110">Datenbank-E-Mail wird in einem separaten Prozess außerhalb von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgeführt. Sie ist skalierbar und benötigt keine Extended MAPI-Clientkomponenten auf dem Produktionsserver.</span><span class="sxs-lookup"><span data-stu-id="f55a6-110">Database Mail runs outside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in a separate process, is scalable, and does not require Extended MAPI client components to be installed on the production server.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="f55a6-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f55a6-111">For More Information</span></span>  
 [<span data-ttu-id="f55a6-112">Datenbank-E-Mail</span><span class="sxs-lookup"><span data-stu-id="f55a6-112">Database Mail</span></span>](../database-mail/database-mail.md)  
  
## <a name="see-also"></a><span data-ttu-id="f55a6-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f55a6-113">See Also</span></span>  
 [<span data-ttu-id="f55a6-114">Überwachen und Erzwingen von Best Practices mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="f55a6-114">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
