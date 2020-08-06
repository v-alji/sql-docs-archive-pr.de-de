---
title: Sicherheit auf Zeilenebene | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- row level security described
- row level security
- access control predicates
- security [SQL Server], predicate based access control
- predicate based security
ms.assetid: 7221fa4e-ca4a-4d5c-9f93-1b8a4af7b9e8
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: c67f84723e79b66d0454fb509f2fa9ced03dac7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697706"
---
# <a name="row-level-security"></a><span data-ttu-id="cd636-102">Sicherheit auf Zeilenebene</span><span class="sxs-lookup"><span data-stu-id="cd636-102">Row-Level Security</span></span>
  <span data-ttu-id="cd636-103">Bei der Sicherheit auf Zeilenebene können Kunden den Zugriff auf Zeilen in einer Datenbanktabelle basierend auf den Merkmalen des Benutzers steuern, der eine Abfrage ausführt (z.B. Gruppenmitgliedschaft oder Ausführungskontext).</span><span class="sxs-lookup"><span data-stu-id="cd636-103">Row-Level Security enables customers to control access to rows in a database table based on the characteristics of the user executing a query (e.g., group membership or execution context).</span></span> <span data-ttu-id="cd636-104">Sicherheit auf Zeilenebene ist jetzt in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2016 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cd636-104">Row-Level Security is now available in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2016.</span></span> <span data-ttu-id="cd636-105">Die aktuelle Beschreibung dieser Funktion finden Sie in der aktuellen Dokumentation [Sicherheit auf Zeilenebene](https://msdn.microsoft.com/library/dn765131.aspx) .</span><span class="sxs-lookup"><span data-stu-id="cd636-105">See [Row-Level Security](https://msdn.microsoft.com/library/dn765131.aspx) in the current documentation for the current description of this feature.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd636-106">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cd636-106">See Also</span></span>  
 <span data-ttu-id="cd636-107">[Erstellen einer Sicherheitsrichtlinie &#40;Azure SQL-Datenbank&#41;](/sql/t-sql/statements/create-security-policy-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cd636-107">[CREATE SECURITY POLICY &#40;Azure SQL Database&#41;](/sql/t-sql/statements/create-security-policy-transact-sql) </span></span>  
 <span data-ttu-id="cd636-108">[Ändern der Sicherheitsrichtlinie &#40;Azure SQL-Datenbank&#41;](/sql/t-sql/statements/alter-security-policy-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cd636-108">[ALTER SECURITY POLICY &#40;Azure SQL Database&#41;](/sql/t-sql/statements/alter-security-policy-transact-sql) </span></span>  
 <span data-ttu-id="cd636-109">[Sicherheitsrichtlinie &#40;Azure SQL-Datenbank löschen&#41;](/sql/t-sql/statements/drop-security-policy-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cd636-109">[DROP SECURITY POLICY &#40;Azure SQL Database&#41;](/sql/t-sql/statements/drop-security-policy-transact-sql) </span></span>  
 <span data-ttu-id="cd636-110">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cd636-110">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span></span>  
 <span data-ttu-id="cd636-111">[sys. security_policies &#40;Azure SQL-Datenbank&#41;](/sql/relational-databases/system-catalog-views/sys-security-policies-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cd636-111">[sys.security_policies &#40;Azure SQL Database&#41;](/sql/relational-databases/system-catalog-views/sys-security-policies-transact-sql) </span></span>  
 <span data-ttu-id="cd636-112">[sys. security_predicates &#40;Azure SQL-Datenbank&#41;](/sql/relational-databases/system-catalog-views/sys-security-predicates-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cd636-112">[sys.security_predicates &#40;Azure SQL Database&#41;](/sql/relational-databases/system-catalog-views/sys-security-predicates-transact-sql) </span></span>  
 [<span data-ttu-id="cd636-113">Erstellen benutzerdefinierter Funktionen &#40;Datenbank-Engine&#41;</span><span class="sxs-lookup"><span data-stu-id="cd636-113">Create User-defined Functions &#40;Database Engine&#41;</span></span>](../user-defined-functions/create-user-defined-functions-database-engine.md)  
  
  
