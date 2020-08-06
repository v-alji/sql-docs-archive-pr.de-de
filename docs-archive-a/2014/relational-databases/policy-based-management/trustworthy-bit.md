---
title: Bit für die Kennzeichnung der Datenbank als vertrauenswürdig | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 3198188a-2b59-4865-9560-10f760934b8e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 062a63dd52f4641a0ddfcbc20cb9bad3cce6dc61
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615997"
---
# <a name="trustworthy-bit"></a><span data-ttu-id="f39f1-102">Bit für die Kennzeichnung der Datenbank als vertrauenswürdig</span><span class="sxs-lookup"><span data-stu-id="f39f1-102">Trustworthy Bit</span></span>
  <span data-ttu-id="f39f1-103">Diese Regel ermittelt, ob die dbo-Rolle für eine Datenbank der festen sysadmin-Serverrolle zugewiesen ist und das Bit für die Kennzeichnung der Datenbank als vertrauenswürdig aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f39f1-103">This rule determines whether the dbo role for a database is assigned to the sysadmin fixed server role and the database has its trustworthy bit set to ON.</span></span>  
  
 <span data-ttu-id="f39f1-104">Werden diese Bedingungen erfüllt, kann ein privilegierter Datenbankbenutzer Berechtigungen auf die sysadmin-Rolle erhöhen.</span><span class="sxs-lookup"><span data-stu-id="f39f1-104">If these conditions are met, a privileged database user can elevate privileges to the sysadmin role.</span></span> <span data-ttu-id="f39f1-105">In dieser Rolle kann der Benutzer unsichere Assemblys, die das System beeinträchtigen, erstellen und ausführen.</span><span class="sxs-lookup"><span data-stu-id="f39f1-105">In this role, the user can create and run unsafe assemblies that compromise the system.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="f39f1-106">Empfehlungen zu Best Practices</span><span class="sxs-lookup"><span data-stu-id="f39f1-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="f39f1-107">Deaktivieren Sie das Bit zur Kennzeichnung der Datenbank als vertrauenswürdig, oder heben Sie die sysadmin-Berechtigungen für die dbo-Datenbankrolle auf.</span><span class="sxs-lookup"><span data-stu-id="f39f1-107">Turn off the trustworthy bit or revoke sysadmin permissions from the dbo database role.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="f39f1-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f39f1-108">For More Information</span></span>  
 [<span data-ttu-id="f39f1-109">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f39f1-109">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="f39f1-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f39f1-110">See Also</span></span>  
 [<span data-ttu-id="f39f1-111">Überwachen und Erzwingen von Best Practices mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="f39f1-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
