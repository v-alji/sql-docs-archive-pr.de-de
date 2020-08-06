---
title: Erstellen systemintern kompilierter gespeicherter Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: e6b34010-cf62-4f65-bbdf-117f291cde7b
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 3e8e8139427c7f2ad92eea856be8da542f65e344
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615388"
---
# <a name="creating-natively-compiled-stored-procedures"></a><span data-ttu-id="17aca-102">Erstellen systemintern kompilierter gespeicherter Prozeduren</span><span class="sxs-lookup"><span data-stu-id="17aca-102">Creating Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="17aca-103">Von systemintern kompilierten gespeicherten Prozeduren wird nicht die vollständige [!INCLUDE[tsql](../../includes/tsql-md.md)] -Programmier- und -Abfrageoberfläche implementiert.</span><span class="sxs-lookup"><span data-stu-id="17aca-103">Natively compiled stored procedures do not implement the full [!INCLUDE[tsql](../../includes/tsql-md.md)] programmability and query surface area.</span></span> <span data-ttu-id="17aca-104">Es gibt bestimmte [!INCLUDE[tsql](../../includes/tsql-md.md)] -Konstrukte, die innerhalb systemintern kompilierter gespeicherter Prozeduren nicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="17aca-104">There are certain [!INCLUDE[tsql](../../includes/tsql-md.md)] constructs that cannot be used inside natively compiled stored procedures.</span></span> <span data-ttu-id="17aca-105">Weitere Informationen finden Sie [unter Unterstützte Konstrukte in System intern kompilierten gespeicherten Prozeduren](../in-memory-oltp/supported-features-for-natively-compiled-t-sql-modules.md).</span><span class="sxs-lookup"><span data-stu-id="17aca-105">For more information, see [Supported Constructs in Natively Compiled Stored Procedures](../in-memory-oltp/supported-features-for-natively-compiled-t-sql-modules.md).</span></span>  
  
 <span data-ttu-id="17aca-106">Allerdings gibt es auch mehrere [!INCLUDE[tsql](../../includes/tsql-md.md)] -Funktionen, die nur für systemintern kompilierte gespeicherte Prozeduren unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="17aca-106">There are, however, several [!INCLUDE[tsql](../../includes/tsql-md.md)] features that are only supported for natively compiled stored procedures:</span></span>  
  
-   <span data-ttu-id="17aca-107">ATOMIC-Blöcke.</span><span class="sxs-lookup"><span data-stu-id="17aca-107">Atomic blocks.</span></span> <span data-ttu-id="17aca-108">Weitere Informationen finden Sie unter [ATOMIC-Blöcke](atomic-blocks-in-native-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="17aca-108">For more information, see [Atomic Blocks](atomic-blocks-in-native-procedures.md).</span></span>  
  
-   <span data-ttu-id="17aca-109">`NOT NULL`-Einschränkungen für Parameter von systemintern kompilierten gespeicherten Prozeduren und darin enthaltene Variablen.</span><span class="sxs-lookup"><span data-stu-id="17aca-109">`NOT NULL` constraints on parameters of and variables in natively compiled stored procedures.</span></span> <span data-ttu-id="17aca-110">Sie können als `NULL` deklarierten Parametern oder Variablen keine `NOT NULL`-Werte zuweisen.</span><span class="sxs-lookup"><span data-stu-id="17aca-110">You cannot assign `NULL` values to parameters or variables declared as `NOT NULL`.</span></span> <span data-ttu-id="17aca-111">Weitere Informationen finden Sie unter [DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="17aca-111">For more information, see [DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql).</span></span>  
  
-   <span data-ttu-id="17aca-112">Schemabindung von systemintern kompilierten gespeicherten Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="17aca-112">Schema binding of natively compiled stored procedures.</span></span>  
  
 <span data-ttu-id="17aca-113">Systemintern kompilierte gespeicherte Prozeduren werden mithilfe von [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) erstellt.</span><span class="sxs-lookup"><span data-stu-id="17aca-113">Natively compiled stored procedures are created using [CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql).</span></span> <span data-ttu-id="17aca-114">Das folgende Beispiel zeigt eine speicheroptimierte Tabelle und eine systemintern kompilierte gespeicherte Prozedur, die zum Einfügen von Zeilen in die Tabelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="17aca-114">The following example shows a memory-optimized table and a natively compiled stored procedure used for inserting rows into the table.</span></span>  
  
```sql  
create table dbo.Ord  
(OrdNo integer not null primary key nonclustered,   
 OrdDate datetime not null,   
 CustCode nvarchar(5) not null)   
 with (memory_optimized=on)  
go  
  
create procedure dbo.OrderInsert(@OrdNo integer, @CustCode nvarchar(5))  
with native_compilation, schemabinding, execute as owner  
as   
begin atomic with  
(transaction isolation level = snapshot,  
language = N'English')  
  
  declare @OrdDate datetime = getdate();  
  insert into dbo.Ord (OrdNo, CustCode, OrdDate) values (@OrdNo, @CustCode, @OrdDate);  
end  
go  
```  
  
 <span data-ttu-id="17aca-115">Im Codebeispiel ist an `NATIVE_COMPILATION` erkennbar, dass diese gespeicherte [!INCLUDE[tsql](../../includes/tsql-md.md)]-Prozedur eine systemintern kompilierte gespeicherte Prozedur ist.</span><span class="sxs-lookup"><span data-stu-id="17aca-115">In the code sample, `NATIVE_COMPILATION` indicates that this [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure is a natively compiled stored procedure.</span></span> <span data-ttu-id="17aca-116">Die folgenden Optionen sind erforderlich:</span><span class="sxs-lookup"><span data-stu-id="17aca-116">The following options are required:</span></span>  
  
|<span data-ttu-id="17aca-117">Option</span><span class="sxs-lookup"><span data-stu-id="17aca-117">Option</span></span>|<span data-ttu-id="17aca-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="17aca-118">Description</span></span>|  
|------------|-----------------|  
|`SCHEMABINDING`|<span data-ttu-id="17aca-119">Systemintern kompilierte gespeicherte Prozeduren müssen an das Schema der Objekte gebunden werden, auf die sie verweisen.</span><span class="sxs-lookup"><span data-stu-id="17aca-119">Natively compiled stored procedures must be bound to the schema of the objects it references.</span></span> <span data-ttu-id="17aca-120">Dies bedeutet, dass Tabellenverweise der Prozedur nicht gelöscht werden können.</span><span class="sxs-lookup"><span data-stu-id="17aca-120">This means that table references by the procedure cannot be dropped.</span></span> <span data-ttu-id="17aca-121">Tabellen, auf die in der Prozedur verwiesen wird, müssen ihren Schema Namen enthalten, und Platzhalter Zeichen ( \* ) sind in Abfragen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="17aca-121">Tables referenced in the procedure must include their schema name, and wildcards (\*) are not allowed in queries.</span></span> <span data-ttu-id="17aca-122">`SCHEMABINDING` wird nur in dieser Version von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] für systemintern kompilierte gespeicherte Prozeduren unterstützt.</span><span class="sxs-lookup"><span data-stu-id="17aca-122">`SCHEMABINDING` is only supported for natively compiled stored procedures in this version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>|  
|`EXECUTE AS`|<span data-ttu-id="17aca-123">Systemintern kompilierte gespeicherte Prozeduren bieten keine Unterstützung für den standardmäßigen Ausführungskontext `EXECUTE AS CALLER`.</span><span class="sxs-lookup"><span data-stu-id="17aca-123">Natively compiled stored procedures do not support `EXECUTE AS CALLER`, which is the default execution context.</span></span> <span data-ttu-id="17aca-124">Daher muss der Ausführungskontext angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="17aca-124">Therefore, specifying the execution context is required.</span></span> <span data-ttu-id="17aca-125">Die Optionen `EXECUTE AS OWNER` , der `EXECUTE AS` *Benutzer*und `EXECUTE AS SELF` werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="17aca-125">The options `EXECUTE AS OWNER`, `EXECUTE AS`*user*, and `EXECUTE AS SELF` are supported.</span></span>|  
|`BEGIN ATOMIC`|<span data-ttu-id="17aca-126">Der Text einer systemintern kompilierten gespeicherten Prozedur muss genau ein ATOMIC-Block sein.</span><span class="sxs-lookup"><span data-stu-id="17aca-126">The natively compiled stored procedure body must consist of exactly one atomic block.</span></span> <span data-ttu-id="17aca-127">ATOMIC-Blöcke gewährleisten die unteilbare Ausführung der gespeicherten Prozedur.</span><span class="sxs-lookup"><span data-stu-id="17aca-127">Atomic blocks guarantee atomic execution of the stored procedure.</span></span> <span data-ttu-id="17aca-128">Wenn die Prozedur außerhalb des Kontexts einer aktiven Transaktion aufgerufen wird, wird eine neue Transaktion gestartet, für die am Ende des ATOMIC-Blocks ein Commit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="17aca-128">If the procedure is invoked outside the context of an active transaction, it will start a new transaction, which commits at the end of the atomic block.</span></span> <span data-ttu-id="17aca-129">ATOMIC-Blöcke in systemintern kompilierten gespeicherten Prozeduren weisen zwei erforderliche Optionen auf:</span><span class="sxs-lookup"><span data-stu-id="17aca-129">Atomic blocks in natively compiled stored procedures have two required options:</span></span><br /><br /> <span data-ttu-id="17aca-130">`TRANSACTION ISOLATION LEVEL`.</span><span class="sxs-lookup"><span data-stu-id="17aca-130">`TRANSACTION ISOLATION LEVEL`.</span></span> <span data-ttu-id="17aca-131">Siehe [Transaktions Isolations Stufen](../../database-engine/transaction-isolation-levels.md) für unterstützte Isolations Stufen.</span><span class="sxs-lookup"><span data-stu-id="17aca-131">See [Transaction Isolation Levels](../../database-engine/transaction-isolation-levels.md) for supported isolation levels.</span></span><br /><br /> <span data-ttu-id="17aca-132">`LANGUAGE`.</span><span class="sxs-lookup"><span data-stu-id="17aca-132">`LANGUAGE`.</span></span> <span data-ttu-id="17aca-133">Die Sprache der gespeicherten Prozedur muss auf eine der verfügbaren Sprachen bzw. einen der verfügbaren Sprachenaliase festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="17aca-133">The language for the stored procedure must be set to one of the available languages or language aliases.</span></span>|  
  
 <span data-ttu-id="17aca-134">Bei `EXECUTE AS` und Windows-Anmeldungen kann ein Fehler aufgrund des Identitätswechsels auftreten, der über `EXECUTE AS` ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="17aca-134">Regarding `EXECUTE AS` and Windows logins, an error can occur because of the impersonation done through `EXECUTE AS`.</span></span> <span data-ttu-id="17aca-135">Wenn ein Benutzerkonto die Windows-Authentifizierung verwendet, muss zwischen dem Dienstkonto, das für die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Instanz verwendet wird, und der Domäne der Windows-Anmeldung vollständige Vertrauenswürdigkeit bestehen.</span><span class="sxs-lookup"><span data-stu-id="17aca-135">If a user account uses Windows Authentication, there must be full trust between the service account used for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance and the domain of the Windows login.</span></span> <span data-ttu-id="17aca-136">Wenn keine volle Vertrauenswürdigkeit vorhanden ist, wird beim Erstellen einer System intern kompilierten gespeicherten Prozedur die folgende Fehlermeldung zurückgegeben: Meldung 15404, Informationen zum Windows NT-Gruppen-/Benutzerbenutzername ' username ' konnten nicht abgerufen werden. Fehlercode 0x5.</span><span class="sxs-lookup"><span data-stu-id="17aca-136">If there is not full trust, the following error message is returned when creating a natively compiled stored procedure: Msg 15404, Could not obtain information about Windows NT group/user 'username', error code 0x5.</span></span>  
  
 <span data-ttu-id="17aca-137">Um diesen Fehler zu beheben, verwenden Sie eine der folgenden Aktionen:</span><span class="sxs-lookup"><span data-stu-id="17aca-137">To resolve this error, use one of the following:</span></span>  
  
-   <span data-ttu-id="17aca-138">Verwenden Sie für den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Dienst ein Konto, das aus derselben Domäne wie der Windows-Benutzer stammt.</span><span class="sxs-lookup"><span data-stu-id="17aca-138">Use an account from the same domain as the Windows user for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span>  
  
-   <span data-ttu-id="17aca-139">Wenn [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ein Computer Konto wie Netzwerkdienst oder lokales System verwendet, muss der Computer von der Domäne, die den Windows-Benutzer enthält, als vertrauenswürdig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="17aca-139">If [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is using a machine account such as Network Service or Local System, the machine must be trusted by the domain containing the Windows user.</span></span>  
  
-   <span data-ttu-id="17aca-140">Verwenden Sie die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="17aca-140">Use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="17aca-141">Möglicherweise wird auch Fehler 15517 angezeigt, wenn Sie eine systemintern kompilierte gespeicherte Prozedur erstellen.</span><span class="sxs-lookup"><span data-stu-id="17aca-141">You may also see error 15517 when creating a natively compiled stored procedure.</span></span> <span data-ttu-id="17aca-142">Weitere Informationen finden Sie unter [MSSQLSERVER_15517](../errors-events/mssqlserver-15517-database-engine-error.md).</span><span class="sxs-lookup"><span data-stu-id="17aca-142">For more information, see [MSSQLSERVER_15517](../errors-events/mssqlserver-15517-database-engine-error.md).</span></span>  
  
## <a name="updating-a-natively-compiled-stored-procedure"></a><span data-ttu-id="17aca-143">Aktualisieren einer systemintern kompilierten gespeicherten Prozedur</span><span class="sxs-lookup"><span data-stu-id="17aca-143">Updating a Natively Compiled Stored Procedure</span></span>  
 <span data-ttu-id="17aca-144">Das Ausführen von Änderungsvorgängen für systemintern kompilierte gespeicherte Prozeduren wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="17aca-144">Performing alter operations on natively compiled stored procedures is not supported.</span></span> <span data-ttu-id="17aca-145">Eine Möglichkeit, eine systemintern kompilierte gespeicherte Prozedur zu ändern, ist das Löschen und erneute Erstellen der gespeicherten Prozedur:</span><span class="sxs-lookup"><span data-stu-id="17aca-145">One way to modify a natively compiled stored procedure is to drop and recreate the stored procedure:</span></span>  
  
1.  <span data-ttu-id="17aca-146">Generieren Sie ein Skript mit Berechtigungen für die gespeicherte Prozedur.</span><span class="sxs-lookup"><span data-stu-id="17aca-146">Generate script for the permissions on the stored procedure.</span></span>  
  
2.  <span data-ttu-id="17aca-147">Generieren Sie optional ein Skript für die gespeicherte Prozedur, und speichern Sie es als Sicherung.</span><span class="sxs-lookup"><span data-stu-id="17aca-147">Optional, generate script for the stored procedure and save as a backup.</span></span>  
  
3.  <span data-ttu-id="17aca-148">Löschen Sie die gespeicherte Prozedur.</span><span class="sxs-lookup"><span data-stu-id="17aca-148">Drop the stored procedure.</span></span>  
  
4.  <span data-ttu-id="17aca-149">Erstellen Sie die geänderte gespeicherte Prozedur.</span><span class="sxs-lookup"><span data-stu-id="17aca-149">Create the altered stored procedure.</span></span>  
  
5.  <span data-ttu-id="17aca-150">Wenden Sie das Skript mit den Berechtigungen erneut auf die gespeicherte Prozedur an.</span><span class="sxs-lookup"><span data-stu-id="17aca-150">Re-apply the scripted permissions to the stored procedure.</span></span>  
  
 <span data-ttu-id="17aca-151">Der Nachteil bei dieser Vorgehensweise besteht darin, dass die Anwendung vom Beginn von Schritt 3 bis zum Abschluss von Schritt 5 offline ist.</span><span class="sxs-lookup"><span data-stu-id="17aca-151">The disadvantage to this procedure is the application will be offline from the start of step 3 through the completion of step 5.</span></span> <span data-ttu-id="17aca-152">Dies kann mehrere Sekunden dauern, und der Client, der die Anwendung verwendet, erhält in dieser Zeit möglicherweise Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="17aca-152">This may take a few seconds and the client using the application may see error messages.</span></span>  
  
 <span data-ttu-id="17aca-153">Eine andere (effektive) Möglichkeit zum Ändern einer systemintern kompilierten gespeicherten Prozedur besteht darin, zuerst eine neue Version der gespeicherten Prozedur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="17aca-153">Another way to (effectively) modify a natively compiled stored procedure is to first create a new version of the stored procedure.</span></span> <span data-ttu-id="17aca-154">In diesem Fall erhält die systemintern kompilierte gespeicherte Prozedur eine zugehörige Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="17aca-154">Here, the natively compiled stored procedure has an associated version number.</span></span> <span data-ttu-id="17aca-155">Die alte Version erhält die Bezeichnung SP_Vold und die neue Version die Bezeichnung SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="17aca-155">We will call the old version SP_Vold and the new version SP_Vnew.</span></span>  
  
1.  <span data-ttu-id="17aca-156">Generieren Sie ein Skript mit den Berechtigungen für SP_Vold.</span><span class="sxs-lookup"><span data-stu-id="17aca-156">Generate script for the permissions on SP_Vold.</span></span>  
  
2.  <span data-ttu-id="17aca-157">Erstellen Sie SP_Vnew.</span><span class="sxs-lookup"><span data-stu-id="17aca-157">Create SP_Vnew.</span></span>  
  
3.  <span data-ttu-id="17aca-158">Wenden Sie die Berechtigungen von SP_Vold auf SP_Vnew an.</span><span class="sxs-lookup"><span data-stu-id="17aca-158">Apply the permissions of SP_Vold to SP_Vnew.</span></span>  
  
4.  <span data-ttu-id="17aca-159">Aktualisieren Sie die Verweise auf SP_Vold, sodass sie auf SP_Vnew zeigen.</span><span class="sxs-lookup"><span data-stu-id="17aca-159">Update references to SP_Vold to point to SP_Vnew.</span></span> <span data-ttu-id="17aca-160">Hierbei haben Sie verschiedene Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="17aca-160">This can be accomplished in different of ways, for example:</span></span>  
  
     <span data-ttu-id="17aca-161">Verwenden Sie eine gespeicherte Wrapperprozedur (datenträgerbasiert), und ändern Sie diese Prozedur, sodass sie auf SP_Vnew zeigt.</span><span class="sxs-lookup"><span data-stu-id="17aca-161">Use a wrapper (disk-based) stored procedure, and alter that procedure to point to SP_Vnew.</span></span> <span data-ttu-id="17aca-162">Der Nachteil bei dieser Vorgehensweise sind die Leistungsverluste durch die Dereferenzierung.</span><span class="sxs-lookup"><span data-stu-id="17aca-162">The disadvantage of this approach is the performance impact of the indirection.</span></span>  
  
    ```sql  
    ALTER PROCEDURE dbo.SP p1,...,pn  
    AS  
      EXEC dbo.SP_Vnew p1,...,pn  
    GO  
    ```  
  
5.  <span data-ttu-id="17aca-163">Löschen Sie optional SP_Vold.</span><span class="sxs-lookup"><span data-stu-id="17aca-163">Optional, drop SP_Vold.</span></span>  
  
 <span data-ttu-id="17aca-164">Der Vorteil dieser Vorgehensweise besteht darin, dass die Anwendung nicht offline geschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="17aca-164">The advantage of this approach is that the application does not go offline.</span></span> <span data-ttu-id="17aca-165">Allerdings sind mehr Schritte erforderlich, um die Verweise beizubehalten und sicherzustellen, dass sie immer auf die neueste Version der gespeicherten Prozedur zeigen.</span><span class="sxs-lookup"><span data-stu-id="17aca-165">However, more work is required to maintain the references and make sure they always point to the latest version of the stored procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17aca-166">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="17aca-166">See Also</span></span>  
 [<span data-ttu-id="17aca-167">Nativ kompilierte gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="17aca-167">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
