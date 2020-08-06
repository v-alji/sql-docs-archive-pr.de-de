---
title: Sicherheit des SQL Server-Anmeldekennworts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: b0862c3a-926b-490c-a37f-382e50146a3e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5534748fbbf810539f2dcfc22239e4b987cf0f77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696717"
---
# <a name="sql-server-login-password-strength"></a><span data-ttu-id="4a26f-102">Sicherheit des SQL Server-Anmeldekennworts</span><span class="sxs-lookup"><span data-stu-id="4a26f-102">SQL Server Login Password Strength</span></span>
  <span data-ttu-id="4a26f-103">Diese Regel überprüft, ob Kennwortrichtlinie erzwingen für jede [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4a26f-103">This rule checks whether "Enforce password policy" of each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login is enabled.</span></span> <span data-ttu-id="4a26f-104">Wenn die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Authentifizierung aktiviert ist und die Betriebssystemversion älter ist als [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)], könnte ein Angreifer ein bekanntes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldekennwort wiederholt nutzen.</span><span class="sxs-lookup"><span data-stu-id="4a26f-104">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication is enabled and if the operating system version is earlier than [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)], an attacker could repeatedly exploit a known [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login password.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="4a26f-105">Empfehlungen zu Best Practices</span><span class="sxs-lookup"><span data-stu-id="4a26f-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="4a26f-106">Es wird empfohlen, das Betriebssystem auf [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)]zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4a26f-106">We recommend that you upgrade the operating system to [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)].</span></span>  
  
 <span data-ttu-id="4a26f-107">Wenn die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Authentifizierung in Ihrer Umgebung nicht erforderlich ist, verwenden Sie die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="4a26f-107">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication is not required in your environment, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="4a26f-108">Aktivieren Sie Kennwortrichtlinie erzwingen für alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldungen.</span><span class="sxs-lookup"><span data-stu-id="4a26f-108">Enable "Enforce password policy" for all the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins.</span></span> <span data-ttu-id="4a26f-109">Verwenden Sie [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) , um die Kennwortrichtlinie für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4a26f-109">Use [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) to configure the password policy for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="4a26f-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4a26f-110">For More Information</span></span>  
 [<span data-ttu-id="4a26f-111">Kennwortrichtlinie</span><span class="sxs-lookup"><span data-stu-id="4a26f-111">Password Policy</span></span>](../security/password-policy.md)  
  
## <a name="see-also"></a><span data-ttu-id="4a26f-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4a26f-112">See Also</span></span>  
 [<span data-ttu-id="4a26f-113">Überwachen und Erzwingen von Best Practices mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="4a26f-113">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
