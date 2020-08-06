---
title: Debugging von CLR-Datenbankobjekten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- database objects [CLR integration], debugging
- permissions [CLR integration]
- debugging [CLR integration]
- building database objects [CLR integration], debugging
- common language runtime [SQL Server], debugging
ms.assetid: 1332035c-d6ed-424d-8234-46ad21168319
author: rothja
ms.author: jroth
ms.openlocfilehash: 084b2494ec55b502f71154ca1f174a6de6d2ab70
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607829"
---
# <a name="debugging-clr-database-objects"></a><span data-ttu-id="a7a59-102">Debuggen von CLR-Datenbankobjekten</span><span class="sxs-lookup"><span data-stu-id="a7a59-102">Debugging CLR Database Objects</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="a7a59-103">unterstützt das Debuggen von [!INCLUDE[tsql](../../../includes/tsql-md.md)] und CLR (Common Language Runtime)-Objekten in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="a7a59-103">provides support for debugging [!INCLUDE[tsql](../../../includes/tsql-md.md)] and common language runtime (CLR) objects in the database.</span></span> <span data-ttu-id="a7a59-104">Die Hauptaspekte des Debuggens in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sind die leichte Einrichtung und Handhabung und die Integration des SQL Server-Debuggers in den Microsoft Visual Studio-Debugger.</span><span class="sxs-lookup"><span data-stu-id="a7a59-104">The key aspects of debugging in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] are the ease of setup and use, and the integration of the SQL Server debugger with the Microsoft Visual Studio debugger.</span></span> <span data-ttu-id="a7a59-105">Darüber hinaus ist das Debuggen sprachübergreifend.</span><span class="sxs-lookup"><span data-stu-id="a7a59-105">Furthermore, debugging works across languages.</span></span> <span data-ttu-id="a7a59-106">Benutzer können Einzelschritte in CLR-Objekte aus [!INCLUDE[tsql](../../../includes/tsql-md.md)] und umgekehrt ausführen.</span><span class="sxs-lookup"><span data-stu-id="a7a59-106">Users can step seamlessly into CLR objects from [!INCLUDE[tsql](../../../includes/tsql-md.md)], and vice versa.</span></span> <span data-ttu-id="a7a59-107">Der Transact-SQL-Debugger in SQL Server Management Studio kann nicht verwendet werden, um Datenbankobjekte zu debuggen, aber Sie können die Objekte debuggen, indem Sie die Debugger in Visual Studio verwenden.</span><span class="sxs-lookup"><span data-stu-id="a7a59-107">The Transact-SQL debugger in SQL Server Management Studio cannot be used to debug managed database objects, but you can debug the objects by using the debuggers in Visual Studio.</span></span> <span data-ttu-id="a7a59-108">Das Debuggen verwalteter Datenbankobjekte in Visual Studio unterstützt alle gängigen Debugfunktionen, wie z. B. „Einzelschritt“- und „Prozedurschritt“-Anweisungen innerhalb von Routinen, die auf dem Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a7a59-108">Managed database object debugging in Visual Studio supports all common debugging features, such as "step into" and "step over" statements within routines executing on the server.</span></span> <span data-ttu-id="a7a59-109">Debugger können während des Debuggens Breakpoints festlegen, Aufruflisten prüfen, Variablen prüfen und Variablenwerte ändern.</span><span class="sxs-lookup"><span data-stu-id="a7a59-109">Debuggers can set breakpoints, inspect the call stack, inspect variables, and modify variable values while debugging.</span></span> <span data-ttu-id="a7a59-110">Beachten Sie, dass Visual Studio .NET 2003 nicht für CLR-Integrationsprogrammierung oder das Debuggen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a7a59-110">Note that Visual Studio .NET 2003 cannot be used for CLR integration programming or debugging.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="a7a59-111">beinhaltet ein vorinstalliertes .NET Framework, und Visual Studio .NET 2003 kann nicht die .NET Framework 2.0-Assemblys verwenden.</span><span class="sxs-lookup"><span data-stu-id="a7a59-111">includes the .NET Framework pre-installed, and Visual Studio .NET 2003 cannot use the .NET Framework 2.0 assemblies.</span></span>  
  
 <span data-ttu-id="a7a59-112">Weitere Informationen zum Debuggen von verwaltetem Code mithilfe von Visual Studio finden Sie im Thema "[Debuggen von verwaltetem Code](https://go.microsoft.com/fwlink/?LinkId=120377)" in der Visual Studio-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="a7a59-112">For more information about debugging managed code using Visual Studio, see the "[Debugging Managed Code](https://go.microsoft.com/fwlink/?LinkId=120377)" topic in the Visual Studio documentation.</span></span>  
  
## <a name="debugging-permissions-and-restrictions"></a><span data-ttu-id="a7a59-113">Debuggen von Berechtigungen und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a7a59-113">Debugging Permissions and Restrictions</span></span>  
 <span data-ttu-id="a7a59-114">Das Debuggen ist ein stark privilegierter Vorgang, daher dürfen nur Mitglieder der festen Server Rolle **sysadmin** dies in tun [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a7a59-114">Debugging is a highly privileged operation, and therefore only members of the **sysadmin** fixed server role are allowed to do so in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a7a59-115">Während des Debuggens gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="a7a59-115">The following restrictions apply while debugging:</span></span>  
  
-   <span data-ttu-id="a7a59-116">Das Debuggen von CLR-Routinen kann nur von einer Debugger-Instanz gleichzeitig vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="a7a59-116">Debugging CLR routines is restricted to one debugger instance at a time.</span></span> <span data-ttu-id="a7a59-117">Diese Einschränkung ist vorhanden, da jegliche CLR-Codeausführung eingefroren wird, wenn der Breakpoint erreicht wird, und die Ausführung wird erst fortgesetzt, wenn sich der Debugger vom Breakpoint fortbewegt.</span><span class="sxs-lookup"><span data-stu-id="a7a59-117">This limitation applies because all CLR code execution freezes when a break point is hit and execution does not continue until the debugger advances from the break point.</span></span> <span data-ttu-id="a7a59-118">Allerdings können Sie das Debuggen von [!INCLUDE[tsql](../../../includes/tsql-md.md)] auf anderen Verbindungen fortführen.</span><span class="sxs-lookup"><span data-stu-id="a7a59-118">However, you can continue debugging [!INCLUDE[tsql](../../../includes/tsql-md.md)] in other connections.</span></span> <span data-ttu-id="a7a59-119">Obwohl das [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Debuggen keine anderen Ausführungen auf dem Server einfriert, könnte es dazu führen, dass durch Aufrechterhaltung einer Sperre andere Verbindungen warten.</span><span class="sxs-lookup"><span data-stu-id="a7a59-119">Although [!INCLUDE[tsql](../../../includes/tsql-md.md)] debugging does not freeze other executions on the server, it could cause other connections to wait by holding a lock.</span></span>  
  
-   <span data-ttu-id="a7a59-120">Für vorhandene Verbindungen kann kein Debuggen vorgenommen werden. Nur neue Verbindungen, wie [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], erfordern Informationen über die Client- und Debugger-Umgebung, bevor die Verbindung hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a7a59-120">Existing connections cannot be debugged, only new connections, as [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] requires information about the client and debugger environment before the connection can be made.</span></span>  
  
 <span data-ttu-id="a7a59-121">Aufgrund der oben genannten Einschränkungen empfehlen wir, dass [!INCLUDE[tsql](../../../includes/tsql-md.md)]- und CLR-Code auf einem Testserver und nicht auf einem Produktionsserver gedebuggt werden.</span><span class="sxs-lookup"><span data-stu-id="a7a59-121">Due to the above restrictions, we recommend that [!INCLUDE[tsql](../../../includes/tsql-md.md)] and CLR code be debugged on a test server, and not on a production server.</span></span>  
  
## <a name="overview-of-debugging-managed-database-objects"></a><span data-ttu-id="a7a59-122">Übersicht über das Debuggen von verwalteten Datenbankobjekten</span><span class="sxs-lookup"><span data-stu-id="a7a59-122">Overview of Debugging Managed Database Objects</span></span>  
 <span data-ttu-id="a7a59-123">Das Debuggen in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] erfolgt nach einem Pro-Verbindungsmodell.</span><span class="sxs-lookup"><span data-stu-id="a7a59-123">Debugging in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] follows a per-connection model.</span></span> <span data-ttu-id="a7a59-124">Ein Debugger kann nur Aktivitäten zu einer Clientverbindung erkennen und debuggen, mit der er verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="a7a59-124">A debugger can detect and debug activities only to the client connection to which it is attached.</span></span> <span data-ttu-id="a7a59-125">Da die Funktionalität eines Debuggers nicht durch den Verbindungstyp eingeschränkt wird, können sowohl TDS- (Tabular Data Stream) als auch HTTP-Verbindungen gedebuggt werden.</span><span class="sxs-lookup"><span data-stu-id="a7a59-125">Because the functionality of the debugger is not limited by the type of connection, both tabular data stream (TDS) and HTTP connections can be debugged.</span></span> <span data-ttu-id="a7a59-126">Allerdings ermöglicht [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nicht das Debuggen vorhandener Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="a7a59-126">However, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not allow debugging existing connections.</span></span> <span data-ttu-id="a7a59-127">Das Debuggen unterstützt alle üblichen Debugfunktionen innerhalb von Routinen, die auf dem Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a7a59-127">Debugging supports all common debugging features within routines executing on the server.</span></span> <span data-ttu-id="a7a59-128">Die Interaktion zwischen einem Debugger und [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] geschieht durch DCOM (Distributed Component Object Model).</span><span class="sxs-lookup"><span data-stu-id="a7a59-128">The interaction between a debugger and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] happens through distributed Component Object Model (COM).</span></span>  
  
 <span data-ttu-id="a7a59-129">Weitere Informationen und Szenarien zum Debuggen verwalteter gespeicherter Prozeduren, Funktionen, Trigger, benutzerdefinierter Typen und Aggregate finden Sie in der Visual Studio-Dokumentation im Thema "[SQL Server CLR-Integration Datenbank-Debuggen](https://go.microsoft.com/fwlink/?LinkId=120378)".</span><span class="sxs-lookup"><span data-stu-id="a7a59-129">For more information and scenarios about debugging managed stored procedures, functions, triggers, user-defined types, and aggregates, see the "[SQL Server CLR Integration Database Debugging](https://go.microsoft.com/fwlink/?LinkId=120378)" topic in the Visual Studio documentation.</span></span>  
  
 <span data-ttu-id="a7a59-130">Das TCP/IP-Netzwerkprotokoll muss in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Instanz aktiviert werden, damit Visual Studio von einem Remotecomputer aus zum Entwickeln, Debuggen und Bereitstellen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a7a59-130">The TCP/IP network protocol must be enabled on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance in order to use Visual Studio for remote development, debugging, and development.</span></span> <span data-ttu-id="a7a59-131">Weitere Informationen zum Aktivieren des TCP/IP-Protokolls auf dem Server finden Sie unter [Konfigurieren von Client Protokollen](../../database-engine/configure-windows/configure-client-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="a7a59-131">For more information about enabling TCP/IP protocol on the server, see [Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md).</span></span>  
  
#### <a name="to-debug-a-managed-database-object"></a><span data-ttu-id="a7a59-132">So debuggen Sie ein verwaltetes Datenbankobjekt</span><span class="sxs-lookup"><span data-stu-id="a7a59-132">To debug a managed database object</span></span>  
  
1.  <span data-ttu-id="a7a59-133">Öffnen Sie Microsoft Visual Studio, und erstellen Sie ein neues [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Projekt. Stellen Sie eine Verbindung zu einer Datenbank auf einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="a7a59-133">Open Microsoft Visual Studio, create a new [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] project, and establish a connection to a database on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="a7a59-134">Erstellen Sie einen neuen Typ.</span><span class="sxs-lookup"><span data-stu-id="a7a59-134">Create a new type.</span></span> <span data-ttu-id="a7a59-135">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen** und **Neues Element...** Wählen Sie im Fenster **Neues Element hinzufügen** die Option **gespeicherte Prozedur**, **benutzerdefinierte Funktion**, **benutzerdefinierter Typ**, **Triggern**, **Aggregat**oder **Klasse**aus.</span><span class="sxs-lookup"><span data-stu-id="a7a59-135">In **Solution Explorer**, right-click the project, select **Add** and **New Item...** From the **Add New Item** window, select **Stored Procedure**, **User-Defined Function**, **User-Defined Type**, **Trigger**, **Aggregate**, or **Class**.</span></span> <span data-ttu-id="a7a59-136">Geben Sie einen Namen für die Quelldatei des neuen Typs an, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a7a59-136">Specify a name for the source file of the new type and click **Add**.</span></span>  
  
3.  <span data-ttu-id="a7a59-137">Fügen Sie Code für den neuen Typ zum Texteditor hinzu.</span><span class="sxs-lookup"><span data-stu-id="a7a59-137">Add code for the new type to the text editor.</span></span> <span data-ttu-id="a7a59-138">Beispielcode für eine gespeicherte Prozedur finden Sie in einem späteren Abschnitt in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="a7a59-138">For sample code for an example stored procedure, see the section later in this topic.</span></span>  
  
4.  <span data-ttu-id="a7a59-139">Fügen Sie ein Skript hinzu, das den Typ testet.</span><span class="sxs-lookup"><span data-stu-id="a7a59-139">Add a script that tests the type.</span></span> <span data-ttu-id="a7a59-140">Erweitern Sie in **Projektmappen-Explorer**das Verzeichnis **TestScripts** , doppelklicken Sie auf **Test. SQL** , um die standardmäßige Test Skript Quelldatei zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a7a59-140">In **Solution Explorer**, expand the **TestScripts** directory double-click **Test.sql** to open the default test script source file.</span></span> <span data-ttu-id="a7a59-141">Fügen Sie das Testskript, das den Code dazu aufruft, zu debuggen, zum Texteditor hinzu.</span><span class="sxs-lookup"><span data-stu-id="a7a59-141">Add the test script, one that invokes the code to be debugged, to the text editor.</span></span> <span data-ttu-id="a7a59-142">Ein Beispielskript sehen Sie unten.</span><span class="sxs-lookup"><span data-stu-id="a7a59-142">See below for a sample script.</span></span>  
  
5.  <span data-ttu-id="a7a59-143">Platzieren Sie einen oder mehrere Breakpoints im Quellcode.</span><span class="sxs-lookup"><span data-stu-id="a7a59-143">Place one or more breakpoints in the source code.</span></span> <span data-ttu-id="a7a59-144">Klicken Sie mit der rechten Maustaste auf eine Codezeile im Text-Editor, in der Funktion oder der Routine, die Sie debuggen möchten, und wählen Sie **Breakpoint** und halte **Punkt einfügen**aus.</span><span class="sxs-lookup"><span data-stu-id="a7a59-144">Right-click on a line of code in the text editor, within the function or routine you want to debug, and select **Breakpoint** and **Insert Breakpoint**.</span></span> <span data-ttu-id="a7a59-145">Der Breakpoint wird hinzugefügt und hebt die Codezeile in Rot hervor.</span><span class="sxs-lookup"><span data-stu-id="a7a59-145">The breakpoint is added, highlighting the line of code in red.</span></span>  
  
6.  <span data-ttu-id="a7a59-146">Wählen Sie im Menü **Debuggen** die Option **Debugging starten** aus, um das Projekt zu kompilieren, bereitzustellen und zu testen.</span><span class="sxs-lookup"><span data-stu-id="a7a59-146">In the **Debug** menu, select **Start Debugging** to compile, deploy, and test the project.</span></span> <span data-ttu-id="a7a59-147">Das Testskript in Test.sql wird ausgeführt, und das verwaltete Datenbankobjekt wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="a7a59-147">The test script in Test.sql will be run and the managed database object will be invoked.</span></span>  
  
7.  <span data-ttu-id="a7a59-148">Wenn der gelbe Pfeil, der den Anweisungszeiger kennzeichnet, am Breakpoint angezeigt wird, pausiert die Codeausführung, und Sie können mit dem Debuggen Ihres verwalteten Datenbankobjekts beginnen.</span><span class="sxs-lookup"><span data-stu-id="a7a59-148">When the yellow arrow designating the instruction pointer appears at the breakpoint code execution pauses and you can begin debugging your managed database object.</span></span> <span data-ttu-id="a7a59-149">Sie können im Menü **Debuggen** einen Prozedur **Schritt** ausführen, um den Anweisungs Zeiger auf die nächste Codezeile zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="a7a59-149">You can **Step Over** from the **Debug** menu to advance the instruction pointer to the next line of code.</span></span> <span data-ttu-id="a7a59-150">Das **Fenster "** lokal" wird verwendet, um den Zustand der Objekte zu beobachten, die aktuell vom Anweisungs Zeiger hervorgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="a7a59-150">The **Locals** window is used to observe the state of the objects currently highlighted by the instruction pointer.</span></span> <span data-ttu-id="a7a59-151">Variablen können dem Fenster über **Wachen** hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="a7a59-151">Variables can be added to the **Watch** window.</span></span> <span data-ttu-id="a7a59-152">Der Zustand der überwachten Variablen kann während der gesamten Debuggingsitzung beobachtet werden und nicht nur, wenn die Variable sich in der Codezeile befindet, die aktuell vom Anweisungszeiger hervorgehoben wird.</span><span class="sxs-lookup"><span data-stu-id="a7a59-152">The state of watched variables can be observed throughout the entire debugging session, not only when the variable is in the line of code currently highlighted by instruction pointer.</span></span> <span data-ttu-id="a7a59-153">Wählen Sie im Menü Debuggen Weiter aus, um mit dem Anweisungszeiger zum nächsten Breakpoint zu springen oder um die Ausführung der Routine abzuschließen, wenn keine weiteren Breakpoints vorhanden sein sollten.</span><span class="sxs-lookup"><span data-stu-id="a7a59-153">Select Continue from the Debug menu to advance the instruction pointer to the next breakpoint or to complete execution of the routine if there are no more breakpoints.</span></span>  
  
### <a name="example"></a><span data-ttu-id="a7a59-154">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a7a59-154">Example</span></span>  
 <span data-ttu-id="a7a59-155">Das folgende Beispiel gibt die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Version an den Aufrufer zurück.</span><span class="sxs-lookup"><span data-stu-id="a7a59-155">The following example returns the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] version to the caller.</span></span>  
  
 <span data-ttu-id="a7a59-156">C#</span><span class="sxs-lookup"><span data-stu-id="a7a59-156">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void GetVersion()  
   {  
   using(SqlConnection connection = new SqlConnection("context connection=true"))   
   {  
      connection.Open();  
      SqlCommand command = new SqlCommand("select @@version",  
                                           connection);  
      SqlContext.Pipe.ExecuteAndSend(command);  
      }  
   }  
}  
```  
  
 <span data-ttu-id="a7a59-157">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a7a59-157">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
Partial Public Class StoredProcedures   
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub GetVersion()  
        Using connection As New SqlConnection("context connection=true")  
            connection.Open()  
            Dim command As New SqlCommand("SELECT @@VERSION", connection)  
            SqlContext.Pipe.ExecuteAndSend(command)  
        End Using  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="a7a59-158">Im Folgenden handelt es sich um ein Testskript, das die oben definierte gespeicherte Prozedur GetVersion aufruft.</span><span class="sxs-lookup"><span data-stu-id="a7a59-158">The following is a test script that invokes the GetVersion stored procedure defined above.</span></span>  
  
```  
EXEC GetVersion  
```  
  
## <a name="see-also"></a><span data-ttu-id="a7a59-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a7a59-159">See Also</span></span>  
 [<span data-ttu-id="a7a59-160">Programmierkonzepte für die Integration der Common Language Runtime &#40;CLR&#41;</span><span class="sxs-lookup"><span data-stu-id="a7a59-160">Common Language Runtime &#40;CLR&#41; Integration Programming Concepts</span></span>](common-language-runtime-clr-integration-programming-concepts.md)  
  
  
