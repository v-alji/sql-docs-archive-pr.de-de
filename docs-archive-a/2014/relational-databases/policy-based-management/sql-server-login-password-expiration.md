---
title: Ablauf des SQL Server-Anmeldekennworts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 7e3bf9da-a436-433d-847a-47c30428cad3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 678e8e9c6b567014bdd49e89d043165bc48d168a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608590"
---
# <a name="sql-server-login-password-expiration"></a><span data-ttu-id="13be1-102">Ablauf des SQL Server-Anmeldekennworts</span><span class="sxs-lookup"><span data-stu-id="13be1-102">SQL Server Login Password Expiration</span></span>
  <span data-ttu-id="13be1-103">Diese Regel überprüft, ob der Ablauf des Kennworts für jede [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="13be1-103">This rule checks whether "Password expiration" of each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login is enabled.</span></span> <span data-ttu-id="13be1-104">Wenn die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Authentifizierung aktiviert ist und die Betriebssystemversion älter ist als [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)], könnte ein Angreifer ein bekanntes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldekennwort wiederholt nutzen.</span><span class="sxs-lookup"><span data-stu-id="13be1-104">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication is enabled and if the operating system version is earlier than [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)], an attacker could repeatedly exploit a known [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login password.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="13be1-105">Empfehlungen zu Best Practices</span><span class="sxs-lookup"><span data-stu-id="13be1-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="13be1-106">Es wird empfohlen, das Betriebssystem auf [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)]zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="13be1-106">We recommend that you upgrade the operating system to [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)].</span></span>  
  
 <span data-ttu-id="13be1-107">Wenn die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Authentifizierung in Ihrer Umgebung nicht erforderlich ist, verwenden Sie die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="13be1-107">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication is not required in your environment, use Windows Authentication.</span></span> <span data-ttu-id="13be1-108">Weitere Informationen finden Sie unter [Auswählen eines Authentifizierungsmodus](../security/choose-an-authentication-mode.md).</span><span class="sxs-lookup"><span data-stu-id="13be1-108">For more information, see [Choose an Authentication Mode](../security/choose-an-authentication-mode.md).</span></span>  
  
 <span data-ttu-id="13be1-109">Aktivieren Sie den Ablauf des Kennworts für alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldungen.</span><span class="sxs-lookup"><span data-stu-id="13be1-109">Enable "Password expiration" for all the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins.</span></span> <span data-ttu-id="13be1-110">Verwenden Sie [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) , um die Kennwortrichtlinie für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="13be1-110">Use [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) to configure the password policy for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="13be1-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="13be1-111">For More Information</span></span>  
 [<span data-ttu-id="13be1-112">Kennwortrichtlinie</span><span class="sxs-lookup"><span data-stu-id="13be1-112">Password Policy</span></span>](../security/password-policy.md)  
  
## <a name="see-also"></a><span data-ttu-id="13be1-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="13be1-113">See Also</span></span>  
 [<span data-ttu-id="13be1-114">Überwachen und Erzwingen von Best Practices mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="13be1-114">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
