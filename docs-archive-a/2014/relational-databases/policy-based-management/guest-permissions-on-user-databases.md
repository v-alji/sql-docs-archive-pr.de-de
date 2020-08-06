---
title: Gastberechtigungen für Benutzerdatenbanken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 540f1c6d-df51-497e-958a-3a0f429d2920
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 344c5fd0639876998f1585c32fac5f7599f664e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609186"
---
# <a name="guest-permissions-on-user-databases"></a><span data-ttu-id="9103a-102">Gastberechtigungen für Benutzerdatenbanken</span><span class="sxs-lookup"><span data-stu-id="9103a-102">Guest Permissions on User Databases</span></span>
  <span data-ttu-id="9103a-103">Diese Regel bestimmt, ob der Gastbenutzer die Berechtigung besitzt, auf die Datenbank zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="9103a-103">This rule determines whether the guest user has permission to access the database.</span></span> <span data-ttu-id="9103a-104">Diese Regel gilt nur für Benutzerdatenbanken.</span><span class="sxs-lookup"><span data-stu-id="9103a-104">This rule applies to user databases only.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="9103a-105">Empfehlungen zu Best Practices</span><span class="sxs-lookup"><span data-stu-id="9103a-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="9103a-106">Widerrufen Sie die Gastbenutzerberechtigung für den Datenbankzugriff, wenn sie nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="9103a-106">Revoke the guest user permission to access the database if it is not required.</span></span>  
  
 <span data-ttu-id="9103a-107">Der Gastbenutzer kann nicht gelöscht, aber deaktiviert werden. Zu diesem Zweck heben Sie die CONNECT-Berechtigung auf, indem Sie REVOKE CONNECT FROM GUEST in einer beliebigen Datenbank außer master, tempdb oder msdb ausführen.</span><span class="sxs-lookup"><span data-stu-id="9103a-107">The guest user cannot be dropped, but guest user can be disabled by revoking its CONNECT permission by executing REVOKE CONNECT FROM GUEST within any database other than master, tempdb, or msdb.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="9103a-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9103a-108">For More Information</span></span>  
 [<span data-ttu-id="9103a-109">Sichern von SQL Server</span><span class="sxs-lookup"><span data-stu-id="9103a-109">Securing SQL Server</span></span>](../security/securing-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="9103a-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9103a-110">See Also</span></span>  
 [<span data-ttu-id="9103a-111">Überwachen und Erzwingen von Best Practices mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="9103a-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
