---
title: Erforderliche Berechtigungen zum Ausführen von SQL Server Profiler | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- Profiler [SQL Server Profiler], permissions
- traces [SQL Server], replaying
- replaying traces
- SQL Server Profiler, permissions
- security [SQL Server], SQL Server Profiler
ms.assetid: 5c580a87-88ae-4314-8fe1-54ade83f227f
author: stevestein
ms.author: sstein
ms.openlocfilehash: e73ffe2e127299db9a9e37e48f089aab2cccca52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722082"
---
# <a name="permissions-required-to-run-sql-server-profiler"></a><span data-ttu-id="104c8-102">Erforderliche Berechtigungen zum Ausführen von SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="104c8-102">Permissions Required to Run SQL Server Profiler</span></span>
  <span data-ttu-id="104c8-103">Standardmäßig sind zum Ausführen von [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] die gleichen Berechtigungen wie für die gespeicherten Transact-SQL-Prozeduren, die zum Erstellen von Ablaufverfolgungen verwendet werden, erforderlich.</span><span class="sxs-lookup"><span data-stu-id="104c8-103">By default, running [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] requires the same user permissions as the Transact-SQL stored procedures that are used to create traces.</span></span> <span data-ttu-id="104c8-104">Zum Ausführen von [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)]muss Benutzern die ALTER TRACE-Berechtigung erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="104c8-104">To run [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)], users must be granted the ALTER TRACE permission.</span></span> <span data-ttu-id="104c8-105">Weitere Informationen finden Sie unter [GRANT (Serverberechtigungen) &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-server-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="104c8-105">For more information, see [GRANT Server Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-server-permissions-transact-sql).</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="104c8-106">Benutzer mit den Berechtigungen SHOWPLAN, ALTER TRACE oder VIEW SERVER STATE können Abfragen anzeigen, die in der Showplan-Ausgabe erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="104c8-106">Users who have the SHOWPLAN, the ALTER TRACE, or the VIEW SERVER STATE permission can view queries that are captured in Showplan output.</span></span> <span data-ttu-id="104c8-107">Diese Abfragen enthalten möglicherweise vertrauliche Informationen wie Kennwörter.</span><span class="sxs-lookup"><span data-stu-id="104c8-107">These queries may contain sensitive information such as passwords.</span></span> <span data-ttu-id="104c8-108">Daher wird empfohlen, diese Berechtigungen nur Benutzern zu gewähren, die zum Zugreifen auf vertrauliche Informationen berechtigt sind, z. B. Mitglieder der festen Datenbankrolle "db_owner" oder Mitglieder der festen Serverrolle "sysadmin".</span><span class="sxs-lookup"><span data-stu-id="104c8-108">Therefore, we recommend that you only grant these permissions to users who are authorized to view sensitive information, such as members of the db_owner fixed database role, or members of the sysadmin fixed server role.</span></span> <span data-ttu-id="104c8-109">Darüber hinaus wird empfohlen, Showplan-Dateien oder Ablaufverfolgungsdateien, die Ereignisse mit Bezug zu Showplan enthalten, nur an einem Speicherort zu speichern, für den das NTFS-Dateisystem verwendet wird, und den Zugriff auf Benutzer zu beschränken, die zum Zugreifen auf vertrauliche Informationen berechtigt sind.</span><span class="sxs-lookup"><span data-stu-id="104c8-109">Additionally, we recommend that you only save Showplan files or trace files that contain Showplan-related events to a location that uses the NTFS file system, and that you restrict access to users who are authorized to view sensitive information.</span></span>

## <a name="permissions-used-to-replay-traces"></a><span data-ttu-id="104c8-110">Berechtigungen zur Wiedergabe von Ablaufverfolgungen</span><span class="sxs-lookup"><span data-stu-id="104c8-110">Permissions Used to Replay Traces</span></span>
 <span data-ttu-id="104c8-111">Für die Wiedergabe von Ablaufverfolgungen benötigt der Benutzer, der die Ablaufverfolgung wiedergibt, ebenfalls die ALTER TRACE-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="104c8-111">Replaying traces also requires that the user who is replaying the trace have the ALTER TRACE permission.</span></span>

 <span data-ttu-id="104c8-112">Während der Wiedergabe verwendet [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] jedoch den EXECUTE AS-Befehl, falls ein Audit Login-Ereignis in der wiedergegebenen Ablaufverfolgung gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="104c8-112">However, during replay, [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] uses the EXECUTE AS command if an Audit Login event is encountered in the trace that is being replayed.</span></span> [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] <span data-ttu-id="104c8-113">verwendet den EXECUTE AS-Befehl, um die Identität des Benutzers anzunehmen, der dem Anmeldeereignis zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="104c8-113">uses the EXECUTE AS command to impersonate the user who is associated with the login event.</span></span>

 <span data-ttu-id="104c8-114">Falls [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] ein Anmeldeereignis in einer wiedergegebenen Ablaufverfolgung findet, werden die folgenden Berechtigungsüberprüfungen ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="104c8-114">If [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] encounters a login event in a trace that is being replayed, the following permission checks are performed:</span></span>

1.  <span data-ttu-id="104c8-115">User1, der die ALTER TRACE-Berechtigung hat, startet die Wiedergabe einer Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="104c8-115">User1, who has the ALTER TRACE permission, starts replaying a trace.</span></span>

2.  <span data-ttu-id="104c8-116">Ein Anmeldeereignis für User2 wird in der wiedergegebenen Ablaufverfolgung gefunden.</span><span class="sxs-lookup"><span data-stu-id="104c8-116">A login event for User2 is encountered in the replayed trace.</span></span>

3.  [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] <span data-ttu-id="104c8-117">verwendet den EXECUTE AS-Befehl, um die Identität von User2 anzunehmen.</span><span class="sxs-lookup"><span data-stu-id="104c8-117">uses the EXECUTE AS command to impersonate User2.</span></span>

4.  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="104c8-118">versucht User2 zu identifizieren. In Abhängigkeit von den Ergebnissen trifft eine der folgenden Aussagen zu:</span><span class="sxs-lookup"><span data-stu-id="104c8-118">attempts to authenticate User2, and depending on the results, one of the following occurs:</span></span>

    1.  <span data-ttu-id="104c8-119">Falls User2 nicht authentifiziert werden kann, gibt [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] einen Fehler zurück und setzt die Wiedergabe der Ablaufverfolgung als User1 fort.</span><span class="sxs-lookup"><span data-stu-id="104c8-119">If User2 cannot be authenticated, [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] returns an error, and continues replaying the trace as User1.</span></span>

    2.  <span data-ttu-id="104c8-120">Falls User2 erfolgreich authentifiziert wird, wird die Wiedergabe der Ablaufverfolgung als User2 fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="104c8-120">If User2 is successfully authenticated, replaying the trace as User2 continues.</span></span>

5.  <span data-ttu-id="104c8-121">Die Berechtigungen für User2 werden in der Zieldatenbank überprüft. In Abhängigkeit von den Ergebnissen trifft eine der folgenden Aussagen zu:</span><span class="sxs-lookup"><span data-stu-id="104c8-121">Permissions for User2 are checked on the target database, and depending on the results, one of the following occurs:</span></span>

    1.  <span data-ttu-id="104c8-122">Falls User2 Berechtigungen für die Zieldatenbank hat, war der Identitätswechsel erfolgreich, und die Ablaufverfolgung wird als User2 wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="104c8-122">If User2 has permissions on the target database, impersonation has succeeded, and the trace is replayed as User2.</span></span>

    2.  <span data-ttu-id="104c8-123">Falls User2 keine Berechtigungen für die Zieldatenbank hat, sucht der Server nach einem Gastbenutzer in dieser Datenbank.</span><span class="sxs-lookup"><span data-stu-id="104c8-123">If User2 does not have permissions on the target database, the server checks for a Guest user on that database.</span></span>

6.  <span data-ttu-id="104c8-124">Das Vorhandensein eines Gastbenutzers wird in der Zieldatenbank überprüft. In Abhängigkeit von den Ergebnissen trifft eine der folgenden Aussagen zu:</span><span class="sxs-lookup"><span data-stu-id="104c8-124">Existence of a Guest user is checked on the target database, and depending on the results, one of the following occurs:</span></span>

    1.  <span data-ttu-id="104c8-125">Falls ein Gastkonto vorhanden ist, wird die Ablaufverfolgung mit dem Gastkonto wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="104c8-125">If a Guest account exists, the trace is replayed as the Guest account.</span></span>

    2.  <span data-ttu-id="104c8-126">Falls in der Zieldatenbank kein Gastkonto vorhanden ist, wird ein Fehler zurückgegeben, und die Ablaufverfolgung wird als User1 wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="104c8-126">If no Guest account exists on the target database, an error is returned and the trace is replayed as User1.</span></span>

 <span data-ttu-id="104c8-127">Das folgende Diagramm zeigt, wie bei der Wiedergabe von Ablaufverfolgungen die Berechtigungen überprüft werden:</span><span class="sxs-lookup"><span data-stu-id="104c8-127">The following diagram shows this process of checking permission when replaying traces:</span></span>

 <span data-ttu-id="104c8-128">![SQL Server Profiler: Berechtigungen zum Wiedergeben von Ablaufverfolgungen](../../database-engine/media/replaytracedecisiontree.gif "SQL Server Profiler: Berechtigungen zum Wiedergeben von Ablaufverfolgungen")</span><span class="sxs-lookup"><span data-stu-id="104c8-128">![SQL Server Profiler replay trace permissions](../../database-engine/media/replaytracedecisiontree.gif "SQL Server Profiler replay trace permissions")</span></span>

## <a name="see-also"></a><span data-ttu-id="104c8-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="104c8-129">See Also</span></span>
 <span data-ttu-id="104c8-130">[SQL Server Profiler gespeicherte Prozeduren &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql) [Replay](replay-traces.md) -Ablauf Verfolgungen [eine Ablauf Verfolgung erstellen &#40;SQL Server Profiler](create-a-trace-sql-server-profiler.md)&#41;eine Ablauf Verfolgungs [Tabelle](replay-a-trace-table-sql-server-profiler.md) wiedergeben &#40;SQL Server Profiler&#41;[eine Ablauf Verfolgungs Datei](replay-a-trace-file-sql-server-profiler.md) wiedergeben &#40;SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="104c8-130">[SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql) [Replay Traces](replay-traces.md) [Create a Trace &#40;SQL Server Profiler&#41;](create-a-trace-sql-server-profiler.md) [Replay a Trace Table &#40;SQL Server Profiler&#41;](replay-a-trace-table-sql-server-profiler.md) [Replay a Trace File &#40;SQL Server Profiler&#41;](replay-a-trace-file-sql-server-profiler.md)</span></span>


