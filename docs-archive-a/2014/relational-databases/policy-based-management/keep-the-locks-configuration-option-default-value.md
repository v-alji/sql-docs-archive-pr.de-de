---
title: Beibehalten des Standardwerts für die Konfigurationsoption „locks“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: f214f05b-5f0b-4786-b2ad-b8b4b6e58d72
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a1d1dcf82d9cd0ef8ef2c15cb68ef78b53a8a54a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609171"
---
# <a name="keep-the-locks-configuration-option-default-value"></a><span data-ttu-id="c61e0-102">Beibehalten des Standardwerts für die Konfigurationsoption 'locks'</span><span class="sxs-lookup"><span data-stu-id="c61e0-102">Keep the Locks Configuration Option Default Value</span></span>
  <span data-ttu-id="c61e0-103">Diese Regel überprüft den Wert der Konfigurationsoption Sperren.</span><span class="sxs-lookup"><span data-stu-id="c61e0-103">This rule checks the value of the locks configuration option.</span></span> <span data-ttu-id="c61e0-104">Durch diese Option wird die maximale Anzahl verfügbarer Sperren festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c61e0-104">This option determines the maximum number of available locks.</span></span> <span data-ttu-id="c61e0-105">Diese schränkt ein, wie viel Arbeitsspeicher [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] für Sperren verwendet.</span><span class="sxs-lookup"><span data-stu-id="c61e0-105">This limits how much memory the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses for locks.</span></span> <span data-ttu-id="c61e0-106">In der Standardeinstellung 0 kann [!INCLUDE[ssDE](../../includes/ssde-md.md)] Sperrstrukturen je nach Systemanforderungen dynamisch zuordnen bzw. deren Zuordnung aufheben.</span><span class="sxs-lookup"><span data-stu-id="c61e0-106">The default setting of 0 enables the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to allocate and deallocate lock structures dynamically based on changing system requirements.</span></span>  
  
 <span data-ttu-id="c61e0-107">Wenn Sperren einen Wert ungleich 0 (null) hat, werden Stapelverarbeitungsaufträge angehalten, und es wird eine Fehlermeldung angezeigt, dass keine Sperren vorhanden sind, wenn der angegebene Wert überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="c61e0-107">If locks is nonzero, batch jobs will stop, and an "out of locks" error message will be generated, if the value specified is exceeded.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="c61e0-108">Empfehlungen zu Best Practices</span><span class="sxs-lookup"><span data-stu-id="c61e0-108">Best Practices Recommendations</span></span>  
 <span data-ttu-id="c61e0-109">Verwenden Sie die gespeicherte Systemprozedur sp_configure, um den Wert von Sperren mithilfe der folgenden Anweisung auf die Standardeinstellung zu ändern:</span><span class="sxs-lookup"><span data-stu-id="c61e0-109">Use the sp_configure system stored procedure to change the value of locks to its default setting by using the following statement:</span></span>  
  
```  
EXEC sp_configure 'locks', 0;  
```  
  
## <a name="for-more-information"></a><span data-ttu-id="c61e0-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c61e0-110">For More Information</span></span>  
 [<span data-ttu-id="c61e0-111">Konfigurieren der Serverkonfigurationsoption Sperren</span><span class="sxs-lookup"><span data-stu-id="c61e0-111">Configure the locks Server Configuration Option</span></span>](../../database-engine/configure-windows/configure-the-locks-server-configuration-option.md)  
  
 [<span data-ttu-id="c61e0-112">sys.dm_tran_locks &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c61e0-112">sys.dm_tran_locks &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql)  
  
 [<span data-ttu-id="c61e0-113">sys.dm_os_wait_stats &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c61e0-113">sys.dm_os_wait_stats &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-wait-stats-transact-sql)  
  
 [<span data-ttu-id="c61e0-114">Microsoft Knowledge Base-Artikel 271509</span><span class="sxs-lookup"><span data-stu-id="c61e0-114">Microsoft Knowledge Base article 271509</span></span>](https://go.microsoft.com/fwlink/?linkid=117788)  
  
## <a name="see-also"></a><span data-ttu-id="c61e0-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c61e0-115">See Also</span></span>  
 [<span data-ttu-id="c61e0-116">Überwachen und Erzwingen von Best Practices mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="c61e0-116">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
