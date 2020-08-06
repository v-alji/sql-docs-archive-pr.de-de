---
title: Geänderte Funktionen (Enthaltene Datenbank) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- contained database, modifications to DBs
ms.assetid: a2942509-39a2-4903-b504-ae80a300a9de
author: stevestein
ms.author: sstein
ms.openlocfilehash: bc52821deeb879022881f838c61823b23c0c10c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725838"
---
# <a name="modified-features-contained-database"></a><span data-ttu-id="21f8a-102">Geänderte Funktionen (Enthaltene Datenbank)</span><span class="sxs-lookup"><span data-stu-id="21f8a-102">Modified Features (Contained Database)</span></span>
  <span data-ttu-id="21f8a-103">Die folgenden Funktionen wurden geändert, damit sie von einer teilweise eigenständigen Datenbank unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="21f8a-103">The following features have been modified to be supported by a partially contained database.</span></span> <span data-ttu-id="21f8a-104">Funktionen wurden i. d. R. so geändert, dass sie die Datenbankbegrenzung nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="21f8a-104">Features are usually modified so they do not cross the database boundary.</span></span>  
  
 <span data-ttu-id="21f8a-105">Weitere Informationen finden Sie unter [Contained Databases](contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="21f8a-105">For more information, see [Contained Databases](contained-databases.md).</span></span>  
  
## <a name="alter-database"></a><span data-ttu-id="21f8a-106">ALTER DATABASE</span><span class="sxs-lookup"><span data-stu-id="21f8a-106">ALTER DATABASE</span></span>  
  
### <a name="application-level"></a><span data-ttu-id="21f8a-107">Anwendungsebene</span><span class="sxs-lookup"><span data-stu-id="21f8a-107">Application Level</span></span>  
 <span data-ttu-id="21f8a-108">Wenn die ALTER DATABASE-Anweisung aus einer enthaltenen Datenbank heraus verwendet wird, unterscheidet sich die Syntax von der für eine nicht enthaltene Datenbank.</span><span class="sxs-lookup"><span data-stu-id="21f8a-108">When using the ALTER DATABASE statement from inside of a contained database, the syntax differs from that used for a non-contained database.</span></span> <span data-ttu-id="21f8a-109">Zu diesen Unterschieden zählen u. a. Einschränkungen für die Elemente der Anweisung, die sich über die Datenbank hinaus zur Instanz erstrecken.</span><span class="sxs-lookup"><span data-stu-id="21f8a-109">This difference includes restrictions of elements of the statement that extend beyond the database to the instance.</span></span> <span data-ttu-id="21f8a-110">Weitere Informationen zu dieser Einstellung finden Sie unter [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="21f8a-110">For more information, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
### <a name="instance-level"></a><span data-ttu-id="21f8a-111">Instanzebene</span><span class="sxs-lookup"><span data-stu-id="21f8a-111">Instance Level</span></span>  
 <span data-ttu-id="21f8a-112">Die Syntax für ALTER DATABASE bei Verwendung außerhalb einer enthaltenen Datenbank unterscheidet sich von der für nicht enthaltene Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="21f8a-112">The syntax for the ALTER DATABASE when used outside of a contained database differs from that used for non-contained databases.</span></span> <span data-ttu-id="21f8a-113">Diese Änderungen verhindern, dass die Datenbankbegrenzung überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="21f8a-113">These changes prevent crossing the database boundary.</span></span> <span data-ttu-id="21f8a-114">Weitere Informationen zu dieser Einstellung finden Sie unter [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="21f8a-114">For more information, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
## <a name="create-database"></a><span data-ttu-id="21f8a-115">CREATE DATABASE</span><span class="sxs-lookup"><span data-stu-id="21f8a-115">CREATE DATABASE</span></span>  
 <span data-ttu-id="21f8a-116">Die CREATE DATABASE-Syntax für eine enthaltene Datenbank unterscheidet sich von der für eine nicht enthaltene Datenbank.</span><span class="sxs-lookup"><span data-stu-id="21f8a-116">The CREATE DATABASE syntax for a contained database differs from that for a non-contained database.</span></span> <span data-ttu-id="21f8a-117">Informationen zu neuen Syntaxanforderungen und -optionen finden Sie unter [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="21f8a-117">See [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql)for information about new syntax requirements and allowances.</span></span>  
  
## <a name="temporary-tables"></a><span data-ttu-id="21f8a-118">Temporäre Tabellen</span><span class="sxs-lookup"><span data-stu-id="21f8a-118">Temporary Tables</span></span>  
 <span data-ttu-id="21f8a-119">Lokale temporäre Tabellen sind in einer enthaltenen Datenbank zulässig, ihr Verhalten unterscheidet sich jedoch von dem temporärer Tabellen in nicht enthaltenen Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="21f8a-119">Local temporary tables are permitted within a contained database, but their behavior differs from those in non-contained databases.</span></span> <span data-ttu-id="21f8a-120">In abhängigen Datenbanken werden temporäre Tabellendaten in der Sortierung von **tempdb** sortiert.</span><span class="sxs-lookup"><span data-stu-id="21f8a-120">In non-contained databases, temporary table data is collated in the collation of **tempdb**.</span></span> <span data-ttu-id="21f8a-121">In einer enthaltenen Datenbank werden temporäre Tabellendaten in der Sortierung der enthaltenen Datenbank sortiert.</span><span class="sxs-lookup"><span data-stu-id="21f8a-121">In a contained database temporary table data is collated in the collation of the contained database.</span></span>  
  
 <span data-ttu-id="21f8a-122">Sämtliche Metadaten, die temporären Tabellen zugeordnet sind (z. B. Tabellen- und Spaltennamen, Indizes usw.) liegen in der Katalogsortierung vor.</span><span class="sxs-lookup"><span data-stu-id="21f8a-122">All metadata associated with temporary tables (for example, table and column names, indexes, and so on) will be in the catalog collation.</span></span>  
  
 <span data-ttu-id="21f8a-123">Benannte Einschränkungen dürfen in temporären Tabellen nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="21f8a-123">Named constraints may not be used in temporary tables.</span></span>  
  
 <span data-ttu-id="21f8a-124">Temporäre Tabellen dürfen nicht auf benutzerdefinierte Typen, XML-Schemaauflistungen und benutzerdefinierte Funktionen verweisen.</span><span class="sxs-lookup"><span data-stu-id="21f8a-124">Temporary tables may not refer to user-defined types, XML schema collections, or user-defined functions.</span></span>  
  
## <a name="collation"></a><span data-ttu-id="21f8a-125">Sortierung</span><span class="sxs-lookup"><span data-stu-id="21f8a-125">Collation</span></span>  
 <span data-ttu-id="21f8a-126">Im abhängigen Datenbankmodell sind drei separate Sortierungstypen vorhanden: Datenbanksortierung, Instanzsortierung und tempdb-Sortierung.</span><span class="sxs-lookup"><span data-stu-id="21f8a-126">In the non-contained database model, there are three separate types of collation: Database collation, Instance collation, and tempdb collation.</span></span> <span data-ttu-id="21f8a-127">In enthaltenen Datenbanken hingegen werden nur zwei Sortierungen verwendet: die Datenbanksortierung und die neue Katalogsortierung.</span><span class="sxs-lookup"><span data-stu-id="21f8a-127">Contained databases use only two collations, database collation and the new catalog collation.</span></span> <span data-ttu-id="21f8a-128">Weitere Details zur Sortierung in eigenständigen Datenbanken finden Sie unter [Contained Database Collations](contained-database-collations.md) .</span><span class="sxs-lookup"><span data-stu-id="21f8a-128">See [Contained Database Collations](contained-database-collations.md) for more details on contained database collation.</span></span>  
  
## <a name="user-options"></a><span data-ttu-id="21f8a-129">user options</span><span class="sxs-lookup"><span data-stu-id="21f8a-129">User Options</span></span>  
 <span data-ttu-id="21f8a-130">Beim Aktivieren eigenständiger Datenbanken muss die [Benutzeroptionen-Option](../../database-engine/configure-windows/configure-the-user-options-server-configuration-option.md) für die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]auf 0 (null) festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="21f8a-130">When enabling contained databases, the [user options Option](../../database-engine/configure-windows/configure-the-user-options-server-configuration-option.md) must be set to 0 for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21f8a-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="21f8a-131">See Also</span></span>  
 <span data-ttu-id="21f8a-132">[Contained Database Collations](contained-database-collations.md) </span><span class="sxs-lookup"><span data-stu-id="21f8a-132">[Contained Database Collations](contained-database-collations.md) </span></span>  
 [<span data-ttu-id="21f8a-133">Eigenständige Datenbanken</span><span class="sxs-lookup"><span data-stu-id="21f8a-133">Contained Databases</span></span>](contained-databases.md)  
  
  
