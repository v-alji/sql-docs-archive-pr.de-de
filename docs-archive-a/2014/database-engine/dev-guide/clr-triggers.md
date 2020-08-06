---
title: CLR-Trigger | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
dev_langs:
- TSQL
- VB
- CSharp
helpviewer_keywords:
- inserted tables
- database objects [CLR integration], triggers
- common language runtime [SQL Server], triggers
- updated columns
- building database objects [CLR integration], triggers
- triggers [CLR integration]
- deleted tables
- EventData property
- SqlTriggerContext class
- transactions [CLR integration]
ms.assetid: 302a4e4a-3172-42b6-9cc0-4a971ab49c1c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 91f12b0d97d2e2065c5bb08d175253c22dffb032
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615537"
---
# <a name="clr-triggers"></a><span data-ttu-id="e5e4c-102">CLR-Trigger</span><span class="sxs-lookup"><span data-stu-id="e5e4c-102">CLR Triggers</span></span>
  <span data-ttu-id="e5e4c-103">Aufgrund der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Integration mit der [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Common Language Runtime (CLR) können Sie jede beliebige [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Sprache verwenden, um CLR-Trigger zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-103">Because of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] integration with the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] common language runtime (CLR), you can use any [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] language to create CLR triggers.</span></span> <span data-ttu-id="e5e4c-104">Dieser Abschnitt enthält spezifische Informationen zu Triggern, die mit CLR-Integration implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-104">This section covers information specific to triggers implemented with CLR integration.</span></span> <span data-ttu-id="e5e4c-105">Eine ausführliche Erläuterung der Trigger finden Sie unter [DDL-Trigger](../../relational-databases/triggers/ddl-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="e5e4c-105">For a complete discussion of triggers, see [DDL Triggers](../../relational-databases/triggers/ddl-triggers.md).</span></span>  
  
## <a name="what-are-triggers"></a><span data-ttu-id="e5e4c-106">Was sind Trigger?</span><span class="sxs-lookup"><span data-stu-id="e5e4c-106">What Are Triggers?</span></span>  
 <span data-ttu-id="e5e4c-107">Ein Trigger ist ein besonderer Typ einer gespeicherten Prozedur, die automatisch ausgeführt wird, wenn ein Sprachereignis ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-107">A trigger is a special type of stored procedure that automatically runs when a language event executes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e5e4c-108">enthält zwei allgemeine Typen von Triggern: DML-Trigger (Data Manipulation Language, Datenbearbeitungssprache) und DDL-Trigger (Data Definition Language, Datendefinitionssprache).</span><span class="sxs-lookup"><span data-stu-id="e5e4c-108">includes two general types of triggers: data manipulation language (DML) and data definition language (DDL) triggers.</span></span> <span data-ttu-id="e5e4c-109">DML-Trigger können verwendet werden, wenn die Anweisungen `INSERT`, `UPDATE` oder `DELETE` Daten in einer angegebenen Tabelle oder Sicht ändern.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-109">DML triggers can be used when `INSERT`, `UPDATE`, or `DELETE` statements modify data in a specified table or view.</span></span> <span data-ttu-id="e5e4c-110">DDL-Trigger lösen gespeicherte Prozeduren als Reaktion auf verschiedene DDL-Anweisungen aus. Dies sind in erster Linie Anweisungen, die mit `CREATE`, `ALTER` und `DROP` beginnen.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-110">DDL triggers fire stored procedures in response to a variety of DDL statements, which are primarily statements that begin with `CREATE`, `ALTER`, and `DROP`.</span></span> <span data-ttu-id="e5e4c-111">DDL-Trigger können für Verwaltungsaufgaben verwendet werden, z. B. zum Überwachen und Steuern von Datenbankvorgängen.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-111">DDL triggers can be used for administrative tasks, such as auditing and regulating database operations.</span></span>  
  
## <a name="unique-capabilities-of-clr-triggers"></a><span data-ttu-id="e5e4c-112">Spezifische Funktionen von CLR-Triggern</span><span class="sxs-lookup"><span data-stu-id="e5e4c-112">Unique Capabilities of CLR Triggers</span></span>  
 <span data-ttu-id="e5e4c-113">In [!INCLUDE[tsql](../../includes/tsql-md.md)] geschriebene Trigger können feststellen, welche Spalten der auslösenden Sicht oder Tabelle mit den Funktionen `UPDATE(column)` und `COLUMNS_UPDATED()` aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-113">Triggers written in [!INCLUDE[tsql](../../includes/tsql-md.md)] have the capability of determining which columns from the firing view or table have been updated by using the `UPDATE(column)` and `COLUMNS_UPDATED()` functions.</span></span>  
  
 <span data-ttu-id="e5e4c-114">In einer CLR-Sprache geschriebene Trigger unterscheiden sich in einigen bedeutenden Punkten von anderen CLR-Integrationsobjekten.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-114">Triggers written in a CLR language differ from other CLR integration objects in several significant ways.</span></span> <span data-ttu-id="e5e4c-115">CLR-Trigger bieten folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="e5e4c-115">CLR triggers can:</span></span>  
  
-   <span data-ttu-id="e5e4c-116">Verweisen auf Daten in den Tabellen `INSERTED` und `DELETED`</span><span class="sxs-lookup"><span data-stu-id="e5e4c-116">Reference data in the `INSERTED` and `DELETED` tables</span></span>  
  
-   <span data-ttu-id="e5e4c-117">Bestimmen, welche Spalten in Folge eines `UPDATE`-Vorgangs geändert wurden</span><span class="sxs-lookup"><span data-stu-id="e5e4c-117">Determine which columns have been modified as a result of an `UPDATE` operation</span></span>  
  
-   <span data-ttu-id="e5e4c-118">Zugreifen auf Informationen über Datenbankobjekte, die von der Ausführung von DDL-Anweisungen beeinflusst werden</span><span class="sxs-lookup"><span data-stu-id="e5e4c-118">Access information about database objects affected by the execution of DDL statements.</span></span>  
  
 <span data-ttu-id="e5e4c-119">Diese Funktionen werden grundsätzlich in der Abfragesprache oder durch die `SqlTriggerContext`-Klasse zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-119">These capabilities are provided inherently in the query language, or by the `SqlTriggerContext` class.</span></span> <span data-ttu-id="e5e4c-120">Informationen zu den Vorteilen der CLR-Integration und zur Auswahl zwischen verwaltetem Code und [!INCLUDE[tsql](../../includes/tsql-md.md)] finden Sie unter [Übersicht über die CLR-Integration](../../relational-databases/clr-integration/clr-integration-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e5e4c-120">For information about the advantages of CLR integration and choosing between managed code and [!INCLUDE[tsql](../../includes/tsql-md.md)], see [Overview of CLR Integration](../../relational-databases/clr-integration/clr-integration-overview.md).</span></span>  
  
## <a name="using-the-sqltriggercontext-class"></a><span data-ttu-id="e5e4c-121">Verwenden der SqlTriggerContext-Klasse</span><span class="sxs-lookup"><span data-stu-id="e5e4c-121">Using the SqlTriggerContext Class</span></span>  
 <span data-ttu-id="e5e4c-122">Die `SqlTriggerContext`-Klasse kann nicht öffentlich erstellt werden und kann nur durch Zugreifen auf die `SqlContext.TriggerContext`-Eigenschaft innerhalb des Texts eines CLR-Triggers abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-122">The `SqlTriggerContext` class cannot be publicly constructed and can only be obtained by accessing the `SqlContext.TriggerContext` property within the body of a CLR trigger.</span></span> <span data-ttu-id="e5e4c-123">Die `SqlTriggerContext`-Klasse kann vom aktiven `SqlContext` durch Aufrufen der `SqlContext.TriggerContext`-Eigenschaft abgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="e5e4c-123">The `SqlTriggerContext` class can be obtained from the active `SqlContext` by calling the `SqlContext.TriggerContext` property:</span></span>  
  
 `SqlTriggerContext myTriggerContext = SqlContext.TriggerContext;`  
  
 <span data-ttu-id="e5e4c-124">Die `SqlTriggerContext`-Klasse stellt Kontextinformationen über den Trigger zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-124">The `SqlTriggerContext` class provides context information about the trigger.</span></span> <span data-ttu-id="e5e4c-125">Diese Kontextinformationen umfassen den Typ der Aktion, die den Trigger ausgelöst hat, die Spalten, die bei einem Aktualisierungs Vorgang geändert wurden, und im Fall eines DDL-Auslösers eine XML- `EventData` Struktur, die den auslösenden Vorgang beschreibt.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-125">This contextual information includes the type of action that caused the trigger to fire, which columns were modified in an UPDATE operation, and, in the case of a DDL trigger, an XML `EventData` structure which describes the triggering operation.</span></span> <span data-ttu-id="e5e4c-126">Weitere Informationen finden Sie unter [EventData &#40;Transact-SQL-&#41;](/sql/t-sql/functions/eventdata-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e5e4c-126">For more information, see [EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql).</span></span>  
  
### <a name="determining-the-trigger-action"></a><span data-ttu-id="e5e4c-127">Bestimmen der Triggeraktion</span><span class="sxs-lookup"><span data-stu-id="e5e4c-127">Determining the Trigger Action</span></span>  
 <span data-ttu-id="e5e4c-128">Sobald Sie eine `SqlTriggerContext`-Klasse erhalten haben, können Sie damit den Typ der Aktion bestimmen, mit der der Trigger ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-128">Once you have obtained a `SqlTriggerContext`, you can use it to determine the type of action that caused the trigger to fire.</span></span> <span data-ttu-id="e5e4c-129">Diese Informationen stehen über die `TriggerAction`-Eigenschaft der `SqlTriggerContext`-Klasse zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-129">This information is available through the `TriggerAction` property of the `SqlTriggerContext` class.</span></span>  
  
 <span data-ttu-id="e5e4c-130">Für DML-Trigger kann die `TriggerAction`-Eigenschaft die folgenden Werte aufweisen:</span><span class="sxs-lookup"><span data-stu-id="e5e4c-130">For DML triggers, the `TriggerAction` property can be one of the following values:</span></span>  
  
-   <span data-ttu-id="e5e4c-131">TriggerAction.Update (0x1)</span><span class="sxs-lookup"><span data-stu-id="e5e4c-131">TriggerAction.Update (0x1)</span></span>  
  
-   <span data-ttu-id="e5e4c-132">TriggerAction.Insert (0x2)</span><span class="sxs-lookup"><span data-stu-id="e5e4c-132">TriggerAction.Insert (0x2)</span></span>  
  
-   <span data-ttu-id="e5e4c-133">TriggerAction.Delete (0x3)</span><span class="sxs-lookup"><span data-stu-id="e5e4c-133">TriggerAction.Delete(0x3)</span></span>  
  
-   <span data-ttu-id="e5e4c-134">Für DDL-Trigger ist die Liste möglicher TriggerAction-Werte beachtlich länger.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-134">For DDL triggers, the list of possible TriggerAction values is considerably longer.</span></span> <span data-ttu-id="e5e4c-135">Weitere Informationen hierzu finden Sie im Abschnitt "TriggerAction Enumeration" in der .NET Framework-SDK-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-135">Please see "TriggerAction Enumeration" in the .NET Framework SDK for more information.</span></span>  
  
### <a name="using-the-inserted-and-deleted-tables"></a><span data-ttu-id="e5e4c-136">Verwenden der Tabellen 'inserted' und 'deleted'</span><span class="sxs-lookup"><span data-stu-id="e5e4c-136">Using the Inserted and Deleted Tables</span></span>  
 <span data-ttu-id="e5e4c-137">In DML-Triggeranweisungen werden zwei spezielle Tabellen verwendet: die **eingefügte** Tabelle und die **Gelöschte** Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-137">Two special tables are used in DML trigger statements: the **inserted** table and the **deleted** table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e5e4c-138">erstellt und verwendet diese Tabellen automatisch.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-138">automatically creates and manages these tables.</span></span> <span data-ttu-id="e5e4c-139">Sie können diese temporären Tabellen verwenden, um die Auswirkungen bestimmter Datenänderungen zu testen und Bedingungen für DML-Triggeraktionen festzulegen. Die Daten in den Tabellen können Sie jedoch nicht direkt ändern.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-139">You can use these temporary tables to test the effects of certain data modifications and to set conditions for DML trigger actions; however, you cannot alter the data in the tables directly.</span></span>  
  
 <span data-ttu-id="e5e4c-140">CLR-Trigger können über den Prozess internen CLR-Anbieter auf die **eingefügten** und **gelöschten** Tabellen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-140">CLR triggers can access the **inserted** and **deleted** tables through the CLR in-process provider.</span></span> <span data-ttu-id="e5e4c-141">Dazu wird ein `SqlCommand`-Objekt vom SqlContext-Objekt abgerufen.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-141">This is done by obtaining a `SqlCommand` object from the SqlContext object.</span></span> <span data-ttu-id="e5e4c-142">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e5e4c-142">For example:</span></span>  
  
 <span data-ttu-id="e5e4c-143">C#</span><span class="sxs-lookup"><span data-stu-id="e5e4c-143">C#</span></span>  
  
```  
SqlConnection connection = new SqlConnection ("context connection = true");  
connection.Open();  
SqlCommand command = connection.CreateCommand();  
command.CommandText = "SELECT * from " + "inserted";  
```  
  
 <span data-ttu-id="e5e4c-144">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e5e4c-144">Visual Basic</span></span>  
  
```  
Dim connection As New SqlConnection("context connection=true")  
Dim command As SqlCommand  
connection.Open()  
command = connection.CreateCommand()  
command.CommandText = "SELECT * FROM " + "inserted"  
```  
  
### <a name="determining-updated-columns"></a><span data-ttu-id="e5e4c-145">Bestimmen aktualisierter Spalten</span><span class="sxs-lookup"><span data-stu-id="e5e4c-145">Determining Updated Columns</span></span>  
 <span data-ttu-id="e5e4c-146">Sie können die Anzahl der vom UPDATE-Vorgang betroffenen Spalten bestimmen, indem Sie die `ColumnCount`-Eigenschaft des `SqlTriggerContext`-Objekts verwenden.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-146">You can determine the number of columns that were modified by an UPDATE operation by using the `ColumnCount` property of the `SqlTriggerContext` object.</span></span> <span data-ttu-id="e5e4c-147">Um zu bestimmen, ob die Spalte aktualisiert wurde, verwenden Sie die `IsUpdatedColumn`-Methode, mit der die Spaltenordnungszahl als Eingabeparameter übernommen wird.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-147">You can use the `IsUpdatedColumn` method, which takes the column ordinal as an input parameter, to determine whether the column was updated.</span></span> <span data-ttu-id="e5e4c-148">Der Wert `True` gibt an, dass die Spalte aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-148">A `True` value indicates that the column has been updated.</span></span>  
  
 <span data-ttu-id="e5e4c-149">Der folgende Codeausschnitt (aus dem EmailAudit-Trigger, der später in diesem Thema behandelt wird) führt beispielsweise alle aktualisierten Spalten auf:</span><span class="sxs-lookup"><span data-stu-id="e5e4c-149">For example, this code snippet (from the EmailAudit trigger later in this topic) lists all of the columns updated:</span></span>  
  
 <span data-ttu-id="e5e4c-150">C#</span><span class="sxs-lookup"><span data-stu-id="e5e4c-150">C#</span></span>  
  
```  
reader = command.ExecuteReader();  
reader.Read();  
for (int columnNumber = 0; columnNumber < triggContext.ColumnCount; columnNumber++)  
{  
   pipe.Send("Updated column "  
      + reader.GetName(columnNumber) + "? "  
   + triggContext.IsUpdatedColumn(columnNumber).ToString());  
 }  
  
 reader.Close();  
```  
  
 <span data-ttu-id="e5e4c-151">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e5e4c-151">Visual Basic</span></span>  
  
```  
reader = command.ExecuteReader()  
reader.Read()  
Dim columnNumber As Integer  
  
For columnNumber=0 To triggContext.ColumnCount-1  
  
   pipe.Send("Updated column " & reader.GetName(columnNumber) & _  
   "? " & triggContext.IsUpdatedColumn(columnNumber).ToString() )  
  
Next  
  
reader.Close()  
```  
  
### <a name="accessing-eventdata-for-clr-ddl-triggers"></a><span data-ttu-id="e5e4c-152">Zugreifen auf EventData für CLR DDL-Trigger</span><span class="sxs-lookup"><span data-stu-id="e5e4c-152">Accessing EventData for CLR DDL Triggers</span></span>  
 <span data-ttu-id="e5e4c-153">Wie normale Trigger lösen auch DDL-Trigger gespeicherte Prozeduren als Antwort auf Ereignisse aus.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-153">DDL triggers, like regular triggers, fire stored procedures in response to an event.</span></span> <span data-ttu-id="e5e4c-154">Im Gegensatz zu DML-Triggern werden Sie jedoch nicht als Antwort auf Update-, INSERT-oder DELETE-Anweisungen für eine Tabelle oder Sicht ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-154">But unlike DML triggers, they do not fire in response to UPDATE, INSERT, or DELETE statements on a table or view.</span></span> <span data-ttu-id="e5e4c-155">DDL-Trigger lösen stattdessen gespeicherte Prozeduren als Reaktion auf verschiedene DDL-Anweisungen aus. Dies sind in erster Linie Anweisungen, die mit CREATE, ALTER und DROP beginnen.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-155">Instead, they fire in response to a variety of DDL statements, which are primarily statements that begin with CREATE, ALTER, and DROP.</span></span> <span data-ttu-id="e5e4c-156">DDL-Trigger können für Verwaltungsaufgaben verwendet werden, z. B. zum Überwachen von Datenbankvorgängen und Schemaänderungen.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-156">DDL triggers can be used for administrative tasks, such as auditing and monitoring of database operations and schema changes.</span></span>  
  
 <span data-ttu-id="e5e4c-157">Informationen über ein Ereignis, das einen DDL-Trigger auslöst, sind in der `EventData`-Eigenschaft der `SqlTriggerContext`-Klasse verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-157">Information about an event that fires a DDL trigger is available in the `EventData` property of the `SqlTriggerContext` class.</span></span> <span data-ttu-id="e5e4c-158">Diese Eigenschaft enthält einen `xml`-Wert.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-158">This property contains an `xml` value.</span></span> <span data-ttu-id="e5e4c-159">Das XML-Schema enthält Informationen zu:</span><span class="sxs-lookup"><span data-stu-id="e5e4c-159">The xml schema includes information about:</span></span>  
  
-   <span data-ttu-id="e5e4c-160">Zeitpunkt des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-160">The time of the event.</span></span>  
  
-   <span data-ttu-id="e5e4c-161">Die SPID (System Process ID) der Verbindung, bei der der Trigger ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-161">The System Process ID (SPID) of the connection during which the trigger executed.</span></span>  
  
-   <span data-ttu-id="e5e4c-162">Der Typ des Ereignisses, die den Trigger ausgelöst haben.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-162">The type of event that fired the trigger.</span></span>  
  
 <span data-ttu-id="e5e4c-163">Abhängig vom Ereignistyp schließt das Schema dann weitere Informationen ein, z. B. die Datenbank, in der das Ereignis aufgetreten ist, das Objekt, für das das Ereignis erfolgte, und den [!INCLUDE[tsql](../../includes/tsql-md.md)]-Befehl des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-163">Then, depending on the event type, the schema includes additional information, such as the database in which the event occurred, the object against which the event occurred, and the [!INCLUDE[tsql](../../includes/tsql-md.md)] command of the event.</span></span>  
  
 <span data-ttu-id="e5e4c-164">Im folgenden Beispiel gibt der DDL-Trigger die unformatierte `EventData`-Eigenschaft zurück.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-164">In the following example, the following DDL trigger returns the raw `EventData` property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e5e4c-165">Das Senden von Ereignissen und Meldungen über das `SqlPipe`-Objekt wird hier nur zur Veranschaulichung gezeigt. Es wird jedoch für den Produktionscode beim Programmieren von CLR-Trigger nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-165">Sending results and messages through the `SqlPipe` object is shown here for illustrative purposes only and is generally discouraged for production code when programming CLR triggers.</span></span> <span data-ttu-id="e5e4c-166">Weitere zurückgegebene Daten sind möglicherweise unerwartet und führen zu Anwendungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-166">Additional data returned may be unexpected and lead to application errors.</span></span>  
  
 <span data-ttu-id="e5e4c-167">C#</span><span class="sxs-lookup"><span data-stu-id="e5e4c-167">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.Sql;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Xml;  
using System.Text.RegularExpressions;  
  
public class CLRTriggers  
{  
   public static void DropTableTrigger()  
   {  
       SqlTriggerContext triggContext = SqlContext.TriggerContext;             
  
       switch(triggContext.TriggerAction)  
       {  
           case TriggerAction.DropTable:  
           SqlContext.Pipe.Send("Table dropped! Here's the EventData:");  
           SqlContext.Pipe.Send(triggContext.EventData.Value);  
           break;  
  
           default:  
           SqlContext.Pipe.Send("Something happened! Here's the EventData:");  
           SqlContext.Pipe.Send(triggContext.EventData.Value);  
           break;  
       }  
   }  
}  
```  
  
 <span data-ttu-id="e5e4c-168">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e5e4c-168">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class CLRTriggers   
  
    Public Shared Sub DropTableTrigger()  
        Dim triggContext As SqlTriggerContext  
        triggContext = SqlContext.TriggerContext  
  
        Select Case triggContext.TriggerAction  
           Case TriggerAction.DropTable  
              SqlContext.Pipe.Send("Table dropped! Here's the EventData:")  
              SqlContext.Pipe.Send(triggContext.EventData.Value)  
  
           Case Else  
              SqlContext.Pipe.Send("Something else happened! Here's the EventData:")  
              SqlContext.Pipe.Send(triggContext.EventData.Value)  
  
        End Select  
    End Sub  
End Class     
```  
  
 <span data-ttu-id="e5e4c-169">Die folgende Beispielausgabe ist der `EventData`-Eigenschaftswert, nachdem ein DDL-Trigger von einem `CREATE TABLE`-Ereignis ausgelöst wurde:</span><span class="sxs-lookup"><span data-stu-id="e5e4c-169">The following sample output is the `EventData` property value after a DDL trigger fired by a `CREATE TABLE` event:</span></span>  
  
 `<EVENT_INSTANCE><PostTime>2004-04-16T21:17:16.160</PostTime><SPID>58</SPID><EventType>CREATE_TABLE</EventType><ServerName>MACHINENAME</ServerName><LoginName>MYDOMAIN\myname</LoginName><UserName>MYDOMAIN\myname</UserName><DatabaseName>AdventureWorks</DatabaseName><SchemaName>dbo</SchemaName><ObjectName>UserName</ObjectName><ObjectType>TABLE</ObjectType><TSQLCommand><SetOptions ANSI_NULLS="ON" ANSI_NULL_DEFAULT="ON" ANSI_PADDING="ON" QUOTED_IDENTIFIER="ON" ENCRYPTED="FALSE" /><CommandText>create table dbo.UserName  
(  
 UserName varchar(50),  
 RealName varchar(50)  
)  
</CommandText></TSQLCommand></EVENT_INSTANCE>`  
  
 <span data-ttu-id="e5e4c-170">Neben den Informationen, auf die über die `SqlTriggerContext`-Klasse zugegriffen werden kann, können Abfragen dennoch auf `COLUMNS_UPDATED` und auf inserted/deleted innerhalb des Texts eines prozessintern ausgeführten Befehls verweisen.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-170">In addition to the information accessible through the `SqlTriggerContext` class, queries can still refer to `COLUMNS_UPDATED` and inserted/deleted within the text of a command executed in-process.</span></span>  
  
## <a name="sample-clr-trigger"></a><span data-ttu-id="e5e4c-171">Beispiel für einen CLR-Trigger</span><span class="sxs-lookup"><span data-stu-id="e5e4c-171">Sample CLR Trigger</span></span>  
 <span data-ttu-id="e5e4c-172">In diesem Beispiel wird das folgende Szenario veranschaulicht: Benutzer können eine beliebige ID auswählen. Sie möchten nun erfahren, welche Benutzer eine E-Mail-Adresse als ID eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-172">In this example, consider the scenario in which you let the user choose any ID they want, but you want to know the users that specifically entered an e-mail address as an ID.</span></span> <span data-ttu-id="e5e4c-173">Der folgende Trigger erkennt diese Informationen und protokolliert sie in einer Überwachungstabelle.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-173">The following trigger would detect that information and log it to an audit table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e5e4c-174">Das Senden von Ereignissen und Meldungen über das `SqlPipe`-Objekt wird hier nur zur Veranschaulichung gezeigt. Es wird jedoch für den Produktionscode nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-174">Sending results and messages through the `SqlPipe` object is shown here for illustrative purposes only and is generally discouraged for production code.</span></span> <span data-ttu-id="e5e4c-175">Zusätzliche zurückgegebene Daten sind möglicherweise unerwartet und können zu Anwendungsfehlern führen.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-175">Additional data returned may be unexpected and lead to application errors</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.Sql;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Xml;  
using System.Text.RegularExpressions;  
  
public class CLRTriggers  
{  
   [SqlTrigger(Name = @"EmailAudit", Target = "[dbo].[Users]", Event = "FOR INSERT, UPDATE, DELETE")]  
   public static void EmailAudit()  
   {  
      string userName;  
      string realName;  
      SqlCommand command;  
      SqlTriggerContext triggContext = SqlContext.TriggerContext;  
      SqlPipe pipe = SqlContext.Pipe;  
      SqlDataReader reader;  
  
      switch (triggContext.TriggerAction)  
      {  
         case TriggerAction.Insert:  
         // Retrieve the connection that the trigger is using  
         using (SqlConnection connection  
            = new SqlConnection(@"context connection=true"))  
         {  
            connection.Open();  
            command = new SqlCommand(@"SELECT * FROM INSERTED;",  
               connection);  
            reader = command.ExecuteReader();  
            reader.Read();  
            userName = (string)reader[0];  
            realName = (string)reader[1];  
            reader.Close();  
  
            if (IsValidEMailAddress(userName))  
            {  
               command = new SqlCommand(  
                  @"INSERT [dbo].[UserNameAudit] VALUES ('"  
                  + userName + @"', '" + realName + @"');",  
                  connection);  
               pipe.Send(command.CommandText);  
               command.ExecuteNonQuery();  
               pipe.Send("You inserted: " + userName);  
            }  
         }  
  
         break;  
  
         case TriggerAction.Update:  
         // Retrieve the connection that the trigger is using  
         using (SqlConnection connection  
            = new SqlConnection(@"context connection=true"))  
         {  
            connection.Open();  
            command = new SqlCommand(@"SELECT * FROM INSERTED;",  
               connection);  
            reader = command.ExecuteReader();  
            reader.Read();  
  
            userName = (string)reader[0];  
            realName = (string)reader[1];  
  
            pipe.Send(@"You updated: '" + userName + @"' - '"  
               + realName + @"'");  
  
            for (int columnNumber = 0; columnNumber < triggContext.ColumnCount; columnNumber++)  
            {  
               pipe.Send("Updated column "  
                  + reader.GetName(columnNumber) + "? "  
                  + triggContext.IsUpdatedColumn(columnNumber).ToString());  
            }  
  
            reader.Close();  
         }  
  
         break;  
  
         case TriggerAction.Delete:  
            using (SqlConnection connection  
               = new SqlConnection(@"context connection=true"))  
               {  
                  connection.Open();  
                  command = new SqlCommand(@"SELECT * FROM DELETED;",  
                     connection);  
                  reader = command.ExecuteReader();  
  
                  if (reader.HasRows)  
                  {  
                     pipe.Send(@"You deleted the following rows:");  
                     while (reader.Read())  
                     {  
                        pipe.Send(@"'" + reader.GetString(0)  
                        + @"', '" + reader.GetString(1) + @"'");  
                     }  
  
                     reader.Close();  
  
                     //alternately, to just send a tabular resultset back:  
                     //pipe.ExecuteAndSend(command);  
                  }  
                  else  
                  {  
                     pipe.Send("No rows affected.");  
                  }  
               }  
  
               break;  
            }  
        }  
  
     public static bool IsValidEMailAddress(string email)  
     {  
         return Regex.IsMatch(email, @"^([\w-]+\.)*?[\w-]+@[\w-]+\.([\w-]+\.)*?[\w]+$");  
     }  
}  
```  
  
 <span data-ttu-id="e5e4c-176">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e5e4c-176">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
Imports System.Text.RegularExpressions  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class CLRTriggers   
  
    <SqlTrigger(Name:="EmailAudit", Target:="[dbo].[Users]", Event:="FOR INSERT, UPDATE, DELETE")> _  
    Public Shared Sub EmailAudit()  
        Dim userName As String  
        Dim realName As String  
        Dim command As SqlCommand  
        Dim triggContext As SqlTriggerContext  
        Dim pipe As SqlPipe  
        Dim reader As SqlDataReader    
  
        triggContext = SqlContext.TriggerContext      
        pipe = SqlContext.Pipe    
  
        Select Case triggContext.TriggerAction  
           Case TriggerAction.Insert  
              Using connection As New SqlConnection("context connection=true")  
                 connection.Open()  
                 command = new SqlCommand("SELECT * FROM INSERTED;", connection)  
  
                 reader = command.ExecuteReader()  
                 reader.Read()  
  
                 userName = CType(reader(0), String)  
                 realName = CType(reader(1), String)  
  
                 reader.Close()  
  
                 If IsValidEmailAddress(userName) Then  
                     command = New SqlCommand("INSERT [dbo].[UserNameAudit] VALUES ('" & _  
                       userName & "', '" & realName & "');", connection)  
  
                    pipe.Send(command.CommandText)  
                    command.ExecuteNonQuery()  
                    pipe.Send("You inserted: " & userName)  
  
                 End If  
              End Using  
  
           Case TriggerAction.Update  
              Using connection As New SqlConnection("context connection=true")  
                 connection.Open()  
                 command = new SqlCommand("SELECT * FROM INSERTED;", connection)  
  
                 reader = command.ExecuteReader()  
                 reader.Read()  
  
                 userName = CType(reader(0), String)  
                 realName = CType(reader(1), String)  
  
                 pipe.Send("You updated: " & userName & " - " & realName)  
  
                 Dim columnNumber As Integer  
  
                 For columnNumber=0 To triggContext.ColumnCount-1  
  
                    pipe.Send("Updated column " & reader.GetName(columnNumber) & _  
                      "? " & triggContext.IsUpdatedColumn(columnNumber).ToString() )  
  
                 Next  
  
                 reader.Close()  
              End Using  
  
           Case TriggerAction.Delete  
              Using connection As New SqlConnection("context connection=true")  
                 connection.Open()  
                 command = new SqlCommand("SELECT * FROM DELETED;", connection)  
  
                 reader = command.ExecuteReader()  
  
                 If reader.HasRows Then  
                    pipe.Send("You deleted the following rows:")  
  
                    While reader.Read()  
  
                       pipe.Send( reader.GetString(0) & ", " & reader.GetString(1) )  
  
                    End While   
  
                    reader.Close()  
  
                    ' Alternately, just send a tabular resultset back:  
                    ' pipe.ExecuteAndSend(command)  
  
                 Else  
                   pipe.Send("No rows affected.")  
                 End If  
  
              End Using   
        End Select  
    End Sub  
  
    Public Shared Function IsValidEMailAddress(emailAddress As String) As Boolean  
  
       return Regex.IsMatch(emailAddress, "^([\w-]+\.)*?[\w-]+@[\w-]+\.([\w-]+\.)*?[\w]+$")  
    End Function      
End Class  
```  
  
 <span data-ttu-id="e5e4c-177">Angenommen, zwei Tabellen sind mit den folgenden Definitionen vorhanden:</span><span class="sxs-lookup"><span data-stu-id="e5e4c-177">Assuming two tables exist with the following definitions:</span></span>  
  
```  
CREATE TABLE Users  
(  
    UserName nvarchar(200) NOT NULL,  
    RealName nvarchar(200) NOT NULL  
);  
GO CREATE TABLE UserNameAudit  
(  
    UserName nvarchar(200) NOT NULL,  
    RealName nvarchar(200) NOT NULL  
)  
```  
  
 <span data-ttu-id="e5e4c-178">Die [!INCLUDE[tsql](../../includes/tsql-md.md)] Anweisung, mit der der-Parameter in erstellt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird, lautet wie folgt, und die Assembly **SQLCLRTest** ist bereits in der aktuellen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Datenbank registriert.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-178">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that creates the trigger in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is as follows, and assumes assembly **SQLCLRTest** is already registered in the current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
```  
CREATE TRIGGER EmailAudit  
ON Users  
FOR INSERT, UPDATE, DELETE  
AS  
EXTERNAL NAME SQLCLRTest.CLRTriggers.EmailAudit  
```  
  
## <a name="validating-and-canceling-invalid-transactions"></a><span data-ttu-id="e5e4c-179">Überprüfen und Abbrechen von ungültigen Transaktionen</span><span class="sxs-lookup"><span data-stu-id="e5e4c-179">Validating and Canceling Invalid Transactions</span></span>  
 <span data-ttu-id="e5e4c-180">Trigger werden üblicherweise zur Überprüfung und zum Abbrechen von ungültigen INSERT-, UPDATE- oder DELETE-Transaktionen oder zum Verhindern von Änderungen in Ihrem Datenbankschema verwendet.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-180">Using triggers to validate and cancel invalid INSERT, UPDATE, or DELETE transactions or to prevent changes to your database schema is common.</span></span> <span data-ttu-id="e5e4c-181">Dies lässt sich erreichen, indem Validierungslogik in den Trigger integriert wird und anschließend ein Rollback zur aktuellen Transaktion durchgeführt wird, wenn die Aktion nicht den Validierungskriterien entspricht.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-181">This can be accomplished by incorporating validation logic into your trigger and then rolling back the current transaction if the action does not meet the validation criteria.</span></span>  
  
 <span data-ttu-id="e5e4c-182">Beim Aufruf innerhalb eines Triggers löst die `Transaction.Rollback`-Methode oder ein SqlCommand-Befehl mit dem Befehlstext "TRANSACTION ROLLBACK" eine Ausnahme mit einer nicht eindeutigen Fehlermeldung aus und muss in einen try/catch-Block eingebunden werden.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-182">When called within a trigger, the `Transaction.Rollback` method or a SqlCommand with the command text "TRANSACTION ROLLBACK" throws an exception with an ambiguous error message and must be wrapped in a try/catch block.</span></span> <span data-ttu-id="e5e4c-183">Die Fehlermeldung, die angezeigt wird, ähnelt der folgenden:</span><span class="sxs-lookup"><span data-stu-id="e5e4c-183">The error message you see is similar to the following:</span></span>  
  
```  
Msg 6549, Level 16, State 1, Procedure trig_InsertValidator, Line 0  
A .NET Framework error occurred during execution of user defined routine or aggregate 'trig_InsertValidator':   
System.Data.SqlClient.SqlException: Transaction is not allowed to roll back inside a user defined routine, trigger or aggregate because the transaction is not started in that CLR level. Change application logic to enforce strict transaction nesting... User transaction, if any, will be rolled back.  
```  
  
 <span data-ttu-id="e5e4c-184">Diese Ausnahme wird erwartet und der try/catch-Block ist notwendig, damit die Codeausführung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-184">This exception is expected and the try/catch block is necessary for code execution to continue.</span></span> <span data-ttu-id="e5e4c-185">Wenn der Triggercode die Ausführung beendet, wird eine andere Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-185">When the trigger code finishes execution, another exception is raised</span></span>  
  
```  
Msg 3991, Level 16, State 1, Procedure trig_InsertValidator, Line 1   
The context transaction which was active before entering user defined routine, trigger or aggregate "trig_InsertValidator" has been ended inside of it, which is not allowed. Change application logic to enforce strict transaction nesting.  
The statement has been terminated.  
```  
  
 <span data-ttu-id="e5e4c-186">Diese Ausnahme ist ebenfalls zu erwarten und ein try/catch-Block um die [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung, die die den Trigger auslösenden Aktion ausführt, ist erforderlich, damit die Ausführung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-186">This exception is also expected, and a try/catch block around the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that performs the action that fires the trigger is necessary so that execution can continue.</span></span> <span data-ttu-id="e5e4c-187">Trotz der zwei ausgelösten Ausnahmen wird ein Rollback für die Transaktion ausgeführt, und für die Änderungen in der Tabelle wird kein Commit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-187">Despite the two exceptions thrown, the transaction is rolled back and the changes are not committed to the table.</span></span> <span data-ttu-id="e5e4c-188">Einer der Hauptunterschiede zwischen CLR-Trigger und [!INCLUDE[tsql](../../includes/tsql-md.md)]-Trigger besteht darin, dass [!INCLUDE[tsql](../../includes/tsql-md.md)]-Trigger nach dem Rollback der Transaktion weiterhin mehr Verarbeitungsleistung übernehmen können.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-188">A major difference between CLR triggers and [!INCLUDE[tsql](../../includes/tsql-md.md)] triggers is that [!INCLUDE[tsql](../../includes/tsql-md.md)] triggers can continue to perform more work after the transaction is rolled back.</span></span>  
  
### <a name="example"></a><span data-ttu-id="e5e4c-189">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e5e4c-189">Example</span></span>  
 <span data-ttu-id="e5e4c-190">Der folgende Trigger führt eine einfache Überprüfung von INSERT-Anweisungen in einer Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-190">The following trigger performs simple validation of INSERT statements on a table.</span></span> <span data-ttu-id="e5e4c-191">Wenn der eingefügte Ganzzahlwert gleich 1 ist, wird ein Rollback der Transaktion durchgeführt und der Wert wird nicht in die Tabelle eingefügt.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-191">If the inserted integer value is equal to one, the transaction is rolled back and the value is not inserted into the table.</span></span> <span data-ttu-id="e5e4c-192">Alle anderen Ganzzahlwerte werden in die Tabelle eingefügt.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-192">All other integer values are inserted into the table.</span></span> <span data-ttu-id="e5e4c-193">Beachten Sie den try/catch-Block um die `Transaction.Rollback`-Methode.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-193">Note the try/catch block around the `Transaction.Rollback` method.</span></span> <span data-ttu-id="e5e4c-194">Das [!INCLUDE[tsql](../../includes/tsql-md.md)]-Skript erstellt eine Testtabelle, Assembly und verwaltete gespeicherte Prozedur.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-194">The [!INCLUDE[tsql](../../includes/tsql-md.md)] script creates a test table, assembly, and managed stored procedure.</span></span> <span data-ttu-id="e5e4c-195">Beachten Sie, dass die beiden INSERT-Anweisungen in einen try/catch-Block eingebunden sind, sodass die Ausnahme erfasst wird, die ausgelöst wird, wenn der Trigger die Ausführung beendet.</span><span class="sxs-lookup"><span data-stu-id="e5e4c-195">Note that the two INSERT statements are wrapped in a try/catch block so that the exception thrown when the trigger finishes execution is caught.</span></span>  
  
 <span data-ttu-id="e5e4c-196">C#</span><span class="sxs-lookup"><span data-stu-id="e5e4c-196">C#</span></span>  
  
```  
using System;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;  
using System.Transactions;  
  
public partial class Triggers  
{  
    // Enter existing table or view for the target and uncomment the attribute line  
    // [Microsoft.SqlServer.Server.SqlTrigger (Name="trig_InsertValidator", Target="Table1", Event="FOR INSERT")]  
    public static void trig_InsertValidator()  
    {  
        using (SqlConnection connection = new SqlConnection(@"context connection=true"))  
        {  
            SqlCommand command;  
            SqlDataReader reader;  
            int value;  
  
            // Open the connection.  
            connection.Open();  
  
            // Get the inserted value.  
            command = new SqlCommand(@"SELECT * FROM INSERTED", connection);  
            reader = command.ExecuteReader();  
            reader.Read();  
            value = (int)reader[0];  
            reader.Close();  
  
            // Rollback the transaction if a value of 1 was inserted.  
            if (1 == value)  
            {  
                try  
                {  
                    // Get the current transaction and roll it back.  
                    Transaction trans = Transaction.Current;  
                    trans.Rollback();                      
                }  
                catch (SqlException ex)  
                {  
                    // Catch the expected exception.                      
                }  
            }  
            else  
            {  
                // Perform other actions here.  
            }  
  
            // Close the connection.  
            connection.Close();              
        }  
    }  
}  
```  
  
 <span data-ttu-id="e5e4c-197">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e5e4c-197">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Transactions  
  
Partial Public Class Triggers  
' Enter existing table or view for the target and uncomment the attribute line  
' <Microsoft.SqlServer.Server.SqlTrigger(Name:="trig_InsertValidator", Target:="Table1", Event:="FOR INSERT")> _  
Public Shared Sub  trig_InsertValidator ()  
    Using connection As New SqlConnection("context connection=true")  
  
        Dim command As SqlCommand  
        Dim reader As SqlDataReader  
        Dim value As Integer  
  
        ' Open the connection.  
        connection.Open()  
  
        ' Get the inserted value.  
        command = New SqlCommand("SELECT * FROM INSERTED", connection)  
        reader = command.ExecuteReader()  
        reader.Read()  
        value = CType(reader(0), Integer)  
        reader.Close()  
  
        ' Rollback the transaction if a value of 1 was inserted.  
        If value = 1 Then  
  
            Try  
                ' Get the current transaction and roll it back.  
                Dim trans As Transaction  
                trans = Transaction.Current  
                trans.Rollback()  
  
            Catch ex As SqlException  
  
                ' Catch the exception.                      
            End Try  
        Else  
  
            ' Perform other actions here.  
        End If  
  
        ' Close the connection.  
        connection.Close()  
    End Using  
End Sub  
End Class  
```  
  
 <span data-ttu-id="e5e4c-198">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e5e4c-198">Transact-SQL</span></span>  
  
```  
-- Create the test table, assembly, and trigger.  
CREATE TABLE Table1(c1 int);  
go  
  
CREATE ASSEMBLY ValidationTriggers from 'E:\programming\ ValidationTriggers.dll';  
go  
  
CREATE TRIGGER trig_InsertValidator  
ON Table1  
FOR INSERT  
AS EXTERNAL NAME ValidationTriggers.Triggers.trig_InsertValidator;  
go  
  
-- Use a Try/Catch block to catch the expected exception  
BEGIN TRY  
   INSERT INTO Table1 VALUES(42)  
   INSERT INTO Table1 VALUES(1)  
END TRY  
BEGIN CATCH  
  SELECT ERROR_NUMBER() AS ErrorNum, ERROR_MESSAGE() AS ErrorMessage  
END CATCH;  
  
-- Clean up.  
DROP TRIGGER trig_InsertValidator;  
DROP ASSEMBLY ValidationTriggers;  
DROP TABLE Table1;  
```  
  
## <a name="see-also"></a><span data-ttu-id="e5e4c-199">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e5e4c-199">See Also</span></span>  
 <span data-ttu-id="e5e4c-200">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-200">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="e5e4c-201">[DML-Trigger](../../relational-databases/triggers/dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-201">[DML Triggers](../../relational-databases/triggers/dml-triggers.md) </span></span>  
 <span data-ttu-id="e5e4c-202">[DDL-Trigger](../../relational-databases/triggers/ddl-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-202">[DDL Triggers](../../relational-databases/triggers/ddl-triggers.md) </span></span>  
 <span data-ttu-id="e5e4c-203">[TRY...CATCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/try-catch-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-203">[TRY...CATCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/try-catch-transact-sql) </span></span>  
 <span data-ttu-id="e5e4c-204">[Aufbauen von Datenbankobjekten mit CLR-&#41; Integration (Common Language Runtime) &#40;](../../relational-databases/clr-integration/database-objects/building-database-objects-with-common-language-runtime-clr-integration.md) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-204">[Building Database Objects with Common Language Runtime &#40;CLR&#41; Integration](../../relational-databases/clr-integration/database-objects/building-database-objects-with-common-language-runtime-clr-integration.md) </span></span>  
 [<span data-ttu-id="e5e4c-205">EVENTDATA &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e5e4c-205">EVENTDATA &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/eventdata-transact-sql)  
  
  
