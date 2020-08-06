---
title: Berechtigungshierarchie (Datenbank-Engine) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.server.permissions.f1--May use common.permissions
helpviewer_keywords:
- security [SQL Server], denying access
- hierarchies [SQL Server], permissions
- securables [SQL Server]
- security [SQL Server], permissions
- permissions [SQL Server], hierarchy
- security [SQL Server], granting access
ms.assetid: f6d20a55-ef03-4e14-85f9-009902889866
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 9a04e5595e509de63b362b31b240e113e635581d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697749"
---
# <a name="permissions-hierarchy-database-engine"></a><span data-ttu-id="df096-102">Berechtigungshierarchie (Datenbank-Engine)</span><span class="sxs-lookup"><span data-stu-id="df096-102">Permissions Hierarchy (Database Engine)</span></span>
  <span data-ttu-id="df096-103">In [!INCLUDE[ssDE](../../../includes/ssde-md.md)] wird eine hierarchische Auflistung der Entitäten verwaltet, die mit Berechtigungen gesichert werden können.</span><span class="sxs-lookup"><span data-stu-id="df096-103">The [!INCLUDE[ssDE](../../../includes/ssde-md.md)] manages a hierarchical collection of entities that can be secured with permissions.</span></span> <span data-ttu-id="df096-104">Diese Entitäten werden als *sicherungsfähige Elemente*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="df096-104">These entities are known as *securables*.</span></span> <span data-ttu-id="df096-105">Die wichtigsten sicherungsfähigen Elemente sind Server und Datenbanken, diskrete Berechtigungen können jedoch auf einer viel differenzierteren Ebene festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="df096-105">The most prominent securables are servers and databases, but discrete permissions can be set at a much finer level.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="df096-106">reguliert die Aktionen von Prinzipalen auf sicherungsfähigen Elementen, indem überprüft wird, ob ihnen entsprechende Berechtigungen gewährt wurden.</span><span class="sxs-lookup"><span data-stu-id="df096-106">regulates the actions of principals on securables by verifying that they have been granted appropriate permissions.</span></span>

 <span data-ttu-id="df096-107">In der folgenden Abbildung werden die Beziehungen zwischen den [!INCLUDE[ssDE](../../../includes/ssde-md.md)] -Berechtigungshierarchien dargestellt.</span><span class="sxs-lookup"><span data-stu-id="df096-107">The following illustration shows the relationships among the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] permissions hierarchies.</span></span>

 <span data-ttu-id="df096-108">![Abbildung mit den Berechtigungshierarchien in Datenbank-Engine](../../database-engine/media/wj-security-layers.gif "Abbildung mit den Berechtigungshierarchien in Datenbank-Engine")</span><span class="sxs-lookup"><span data-stu-id="df096-108">![Diagram of Database Engine permissions hierarchies](../../database-engine/media/wj-security-layers.gif "Diagram of Database Engine permissions hierarchies")</span></span>

## <a name="chart-of-sql-server-permissions"></a><span data-ttu-id="df096-109">Diagramm der SQL Server-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="df096-109">Chart of SQL Server Permissions</span></span>
 <span data-ttu-id="df096-110">Navigieren Sie zu [https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf](https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf), um ein Diagramm aller [!INCLUDE[ssDE](../../../includes/ssde-md.md)] -Berechtigungen im PDF-Format abzurufen.</span><span class="sxs-lookup"><span data-stu-id="df096-110">For a poster sized chart of all [!INCLUDE[ssDE](../../../includes/ssde-md.md)] permissions in pdf format, see [https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf](https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf).</span></span>

## <a name="working-with-permissions"></a><span data-ttu-id="df096-111">Arbeiten mit Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="df096-111">Working with Permissions</span></span>
 <span data-ttu-id="df096-112">Berechtigungen können mit den bekannten [!INCLUDE[tsql](../../includes/tsql-md.md)] -Abfragen GRANT, DENY und REVOKE geändert werden.</span><span class="sxs-lookup"><span data-stu-id="df096-112">Permissions can be manipulated with the familiar [!INCLUDE[tsql](../../includes/tsql-md.md)] queries GRANT, DENY, and REVOKE.</span></span> <span data-ttu-id="df096-113">Informationen über Berechtigungen finden Sie in den Katalogsichten [sys.server_permissions](/sql/relational-databases/system-catalog-views/sys-server-permissions-transact-sql) und [sys.database_permissions](/sql/relational-databases/system-catalog-views/sys-database-permissions-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="df096-113">Information about permissions is visible in the [sys.server_permissions](/sql/relational-databases/system-catalog-views/sys-server-permissions-transact-sql) and [sys.database_permissions](/sql/relational-databases/system-catalog-views/sys-database-permissions-transact-sql) catalog views.</span></span> <span data-ttu-id="df096-114">Zudem wird die Abfrage von Berechtigungsinformationen mithilfe von integrierten Funktionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="df096-114">There is also support for querying permissions information by using built-in functions.</span></span>

## <a name="see-also"></a><span data-ttu-id="df096-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="df096-115">See Also</span></span>
 <span data-ttu-id="df096-116">[Sichern von SQL Server](securing-sql-server.md) [Berechtigungen &#40;Datenbank-Engine&#41;](permissions-database-engine.md) Sicherungs fähigen [Securables](securables.md) [Prinzipalen &#40;](authentication-access/principals-database-engine.md) Datenbank-Engine&#41;&#40;&#41;Transact- [SQL](/sql/t-sql/statements/grant-transact-sql) [-&#40;&#41;](/sql/t-sql/statements/revoke-transact-sql) Transact-SQL-&#40;&#41;HAS_PERMS_BY_NAME Transact- [SQL &#40;&#41;](/sql/t-sql/statements/deny-transact-sql) [fn_builtin_permissions](/sql/t-sql/functions/has-perms-by-name-transact-sql) &#40;Transact-SQL&#41;[sys. server_permissions &#40;Transact-SQL](/sql/relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql) [-&#41;](/sql/relational-databases/system-catalog-views/sys-server-permissions-transact-sql) [sys.database_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-permissions-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="df096-116">[Securing SQL Server](securing-sql-server.md) [Permissions &#40;Database Engine&#41;](permissions-database-engine.md) [Securables](securables.md) [Principals &#40;Database Engine&#41;](authentication-access/principals-database-engine.md) [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) [REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) [DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql) [HAS_PERMS_BY_NAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/has-perms-by-name-transact-sql) [sys.fn_builtin_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql) [sys.server_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-permissions-transact-sql) [sys.database_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-permissions-transact-sql)</span></span>


