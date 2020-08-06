---
title: SqlContext-Objekt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- Windows identity [CLR integration]
- SqlContext object
- context [CLR integration]
ms.assetid: 67437853-8a55-44d9-9337-90689ebba730
author: rothja
ms.author: jroth
ms.openlocfilehash: 10f036e274925f7b28b79f619f8e24b3e8804140
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718268"
---
# <a name="sqlcontext-object"></a><span data-ttu-id="a8f39-102">SqlContext-Objekt</span><span class="sxs-lookup"><span data-stu-id="a8f39-102">SqlContext Object</span></span>
  <span data-ttu-id="a8f39-103">Sie rufen verwalteten Code auf dem Server auf, wenn Sie eine Prozedur oder Funktion aufrufen, eine Methode für einen benutzerdefinierten CLR (Common Language Runtime)-Typ aufrufen oder wenn Ihre Aktion einen in einer beliebigen [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework-Sprache definierten Trigger auslöst.</span><span class="sxs-lookup"><span data-stu-id="a8f39-103">You invoke managed code in the server when you call a procedure or function, when you call a method on a common language runtime (CLR) user-defined type, or when your action fires a trigger defined in any of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework languages.</span></span> <span data-ttu-id="a8f39-104">Da die Ausführung dieses Codes im Rahmen einer Benutzerverbindung erforderlich ist, wird ein Zugriff auf den Kontext des aufrufenden Codes vonseiten des auf dem Server ausgeführten Code benötigt.</span><span class="sxs-lookup"><span data-stu-id="a8f39-104">Because execution of this code is requested as part of a user connection, access to the context of the caller from the code running in the server is required.</span></span> <span data-ttu-id="a8f39-105">Zusätzlich dazu sind bestimmte Datenzugriffsvorgänge unter Umständen nur gültig, wenn sie im Kontext des aufrufenden Programms ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a8f39-105">In addition, certain data access operations may only be valid if run under the context of the caller.</span></span> <span data-ttu-id="a8f39-106">Beispielsweise ist der Zugriff auf in Triggervorgängen verwendete eingefügte und gelöschte Pseudotabellen nur im Kontext des aufrufenden Codes gültig.</span><span class="sxs-lookup"><span data-stu-id="a8f39-106">For example, access to inserted and deleted pseudo-tables used in trigger operations is only valid under the context of the caller.</span></span>  
  
 <span data-ttu-id="a8f39-107">Der Kontext des aufrufenden Codes wird in einem `SqlContext`-Objekt abstrahiert.</span><span class="sxs-lookup"><span data-stu-id="a8f39-107">The context of the caller is abstracted in a `SqlContext` object.</span></span> <span data-ttu-id="a8f39-108">Weitere Informationen zu `SqlTriggerContext`-Methoden und -Eigenschaften finden Sie in der Referenzdokumentation zur `Microsoft.SqlServer.Server.SqlTriggerContext`-Klasse im [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-SDK.</span><span class="sxs-lookup"><span data-stu-id="a8f39-108">For more information about the `SqlTriggerContext` methods and properties, see the `Microsoft.SqlServer.Server.SqlTriggerContext` class reference documentation in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
 <span data-ttu-id="a8f39-109">`SqlContext` stellt den Zugriff auf folgende Komponenten bereit:</span><span class="sxs-lookup"><span data-stu-id="a8f39-109">`SqlContext` provides access to the following components:</span></span>  
  
-   <span data-ttu-id="a8f39-110">`SqlPipe`: Das `SqlPipe`-Objekt stellt die "Pipe" dar, d. h. den Kanal, durch den die Ergebnisse den Client erreichen.</span><span class="sxs-lookup"><span data-stu-id="a8f39-110">`SqlPipe`: The `SqlPipe` object represents the "pipe" through which results flow to the client.</span></span> <span data-ttu-id="a8f39-111">Weitere Informationen zum- `SqlPipe` Objekt finden Sie unter [SqlPipe-Objekt](sqlpipe-object.md).</span><span class="sxs-lookup"><span data-stu-id="a8f39-111">For more information about the `SqlPipe` object, see [SqlPipe Object](sqlpipe-object.md).</span></span>  
  
-   <span data-ttu-id="a8f39-112">`SqlTriggerContext`: Das `SqlTriggerContext`-Objekt kann nur innerhalb eines CLR-Triggers abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a8f39-112">`SqlTriggerContext`: The `SqlTriggerContext` object can only be retrieved from within a CLR trigger.</span></span> <span data-ttu-id="a8f39-113">Es stellt Informationen über den Vorgang bereit, durch den der Trigger ausgelöst wurde, sowie eine Übersicht der aktualisierten Spalten.</span><span class="sxs-lookup"><span data-stu-id="a8f39-113">It provides information about the operation that caused the trigger to fire and a map of the columns that were updated.</span></span> <span data-ttu-id="a8f39-114">Weitere Informationen zum- `SqlTriggerContext` Objekt finden Sie unter [SqlTriggerContext-Objekt](sqltriggercontext-object.md).</span><span class="sxs-lookup"><span data-stu-id="a8f39-114">For more information about the `SqlTriggerContext` object, see [SqlTriggerContext Object](sqltriggercontext-object.md).</span></span>  
  
-   <span data-ttu-id="a8f39-115">`IsAvailable`: Die `IsAvailable`-Eigenschaft wird verwendet, um die Verfügbarkeit des Kontexts zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="a8f39-115">`IsAvailable`: The `IsAvailable` property is used to determine context availability.</span></span>  
  
-   <span data-ttu-id="a8f39-116">`WindowsIdentity`: Die `WindowsIdentity`-Eigenschaft wird verwendet, um die Windows-Identität des aufrufenden Programms abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a8f39-116">`WindowsIdentity`: The `WindowsIdentity` property is used to retrieve the Windows identity of the caller.</span></span>  
  
## <a name="determining-context-availability"></a><span data-ttu-id="a8f39-117">Bestimmen der Kontextverfügbarkeit</span><span class="sxs-lookup"><span data-stu-id="a8f39-117">Determining Context Availability</span></span>  
 <span data-ttu-id="a8f39-118">Fragen Sie die `SqlContext`-Klasse ab, um zu ermitteln, ob der gerade ausgeführte Code prozessintern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a8f39-118">Query the `SqlContext` class to see if the currently executing code is running in-process.</span></span> <span data-ttu-id="a8f39-119">Überprüfen Sie dazu die `IsAvailable`-Eigenschaft des `SqlContext`-Objekts.</span><span class="sxs-lookup"><span data-stu-id="a8f39-119">To do this, check the `IsAvailable` property of the `SqlContext` object.</span></span> <span data-ttu-id="a8f39-120">Die `IsAvailable`-Eigenschaft ist schreibgeschützt und gibt `True` zurück, wenn der aufrufende Code innerhalb von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgeführt wird und auf andere `SqlContext`-Elemente zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="a8f39-120">The `IsAvailable` property is read-only, and returns `True` if the calling code is running inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and if other `SqlContext` members can be accessed.</span></span> <span data-ttu-id="a8f39-121">Wenn die `IsAvailable`-Eigenschaft `False` zurückgibt, lösen alle anderen `SqlContext`-Elemente eine `InvalidOperationException`-Ausnahme aus, falls sie verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a8f39-121">If the `IsAvailable` property returns `False`, all the other `SqlContext` members throw an `InvalidOperationException`, if used.</span></span> <span data-ttu-id="a8f39-122">Wenn `IsAvailable``False` zurückgibt, schlagen alle Versuche, ein Verbindungsobjekt zu öffnen, bei denen "context connection=true" festgelegt ist, fehl.</span><span class="sxs-lookup"><span data-stu-id="a8f39-122">If `IsAvailable` returns `False`, any attempt to open a connection object that has "context connection=true" in the connection string fails.</span></span>  
  
## <a name="retrieving-windows-identity"></a><span data-ttu-id="a8f39-123">Abrufen der Windows-Identität</span><span class="sxs-lookup"><span data-stu-id="a8f39-123">Retrieving Windows Identity</span></span>  
 <span data-ttu-id="a8f39-124">Innerhalb von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgeführter CLR-Code wird immer im Kontext des Prozesskontos aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="a8f39-124">CLR code executing inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is always invoked in the context of the process account.</span></span> <span data-ttu-id="a8f39-125">Wenn der Code bestimmte Aktionen mit der Identität des aufrufenden Benutzers anstelle der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Prozessidentität ausführen soll, sollte mithilfe der `WindowsIdentity`-Eigenschaft des `SqlContext`-Objekts ein Identitätstoken abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a8f39-125">If the code should perform certain actions using the identity of the calling user, instead of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process identity, then an impersonation token should be obtained through the `WindowsIdentity` property of the `SqlContext` object.</span></span> <span data-ttu-id="a8f39-126">Die `WindowsIdentity`-Eigenschaft gibt eine `WindowsIdentity`-Instanz zurück, die die [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Identität des aufrufenden Benutzers darstellt, bzw. NULL, wenn der Client über die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Authentifizierung identifiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="a8f39-126">The `WindowsIdentity` property returns a `WindowsIdentity` instance representing the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows identity of the caller, or null if the client was authenticated using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="a8f39-127">Nur mit der `EXTERNAL_ACCESS`-Berechtigung oder `UNSAFE`-Berechtigung markierte Assemblys können auf diese Eigenschaft zugreifen.</span><span class="sxs-lookup"><span data-stu-id="a8f39-127">Only assemblies marked with `EXTERNAL_ACCESS` or `UNSAFE` permissions can access this property.</span></span>  
  
 <span data-ttu-id="a8f39-128">Nach dem Erhalt des `WindowsIdentity`-Objekts können aufrufende Benutzer einen Identitätswechsel für das Clientkonto durchführen und Aktionen mit der neuen Identität ausführen.</span><span class="sxs-lookup"><span data-stu-id="a8f39-128">After obtaining the `WindowsIdentity` object, callers can impersonate the client account and perform actions on their behalf.</span></span>  
  
 <span data-ttu-id="a8f39-129">Die Identität des aufrufenden Benutzers ist nur über `SqlContext.WindowsIdentity` verfügbar, wenn der Client, der die Ausführung der gespeicherten Prozedur oder der Funktion initiiert hat, mithilfe der Windows-Authentifizierung eine Verbindung mit dem Server hergestellt hat.</span><span class="sxs-lookup"><span data-stu-id="a8f39-129">The identity of the caller is only available through `SqlContext.WindowsIdentity` if the client that initiated execution of the stored-procedure or function connected to the server using Windows Authentication.</span></span> <span data-ttu-id="a8f39-130">Wenn stattdessen die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Authentifizierung verwendet wurde, ist diese Eigenschaft NULL, und der Code kann die Identität des aufrufenden Benutzers nicht feststellen.</span><span class="sxs-lookup"><span data-stu-id="a8f39-130">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication was used instead, this property is null and the code is unable to impersonate the caller.</span></span>  
  
### <a name="example"></a><span data-ttu-id="a8f39-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a8f39-131">Example</span></span>  
 <span data-ttu-id="a8f39-132">Im folgenden Beispiel wird das Abrufen der Windows-Identität des aufrufenden Clients und der Identitätswechsel des Clients veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a8f39-132">The following example shows how to get the Windows identity of the calling client and impersonate the client.</span></span>  
  
 <span data-ttu-id="a8f39-133">C#</span><span class="sxs-lookup"><span data-stu-id="a8f39-133">C#</span></span>  
  
```  
[Microsoft.SqlServer.Server.SqlProcedure]  
public static void WindowsIDTestProc()  
{  
    WindowsIdentity clientId = null;  
    WindowsImpersonationContext impersonatedUser = null;  
  
    // Get the client ID.  
    clientId = SqlContext.WindowsIdentity;  
  
    // This outer try block is used to thwart exception filter   
    // attacks which would prevent the inner finally   
    // block from executing and resetting the impersonation.  
    try  
    {  
        try  
        {  
            impersonatedUser = clientId.Impersonate();  
            if (impersonatedUser != null)  
            {  
                // Perform some action using impersonation.  
            }  
        }  
        finally  
        {  
            // Undo impersonation.  
            if (impersonatedUser != null)  
                impersonatedUser.Undo();  
        }  
    }  
    catch  
    {  
        throw;  
    }  
}  
```  
  
 <span data-ttu-id="a8f39-134">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8f39-134">Visual Basic</span></span>  
  
```  
<Microsoft.SqlServer.Server.SqlProcedure()> _  
Public Shared Sub  WindowsIDTestProcVB ()  
    Dim clientId As WindowsIdentity  
    Dim impersonatedUser As WindowsImpersonationContext  
  
    ' Get the client ID.  
    clientId = SqlContext.WindowsIdentity  
  
    ' This outer try block is used to thwart exception filter   
    ' attacks which would prevent the inner finally   
    ' block from executing and resetting the impersonation.  
  
    Try  
        Try  
  
            impersonatedUser = clientId.Impersonate()  
  
            If impersonatedUser IsNot Nothing Then  
                ' Perform some action using impersonation.  
            End If  
  
        Finally  
            ' Undo impersonation.  
            If impersonatedUser IsNot Nothing Then  
                impersonatedUser.Undo()  
            End If  
        End Try  
  
    Catch e As Exception  
  
        Throw e  
  
    End Try  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="a8f39-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a8f39-135">See Also</span></span>  
 <span data-ttu-id="a8f39-136">[SqlPipe-Objekt](sqlpipe-object.md) </span><span class="sxs-lookup"><span data-stu-id="a8f39-136">[SqlPipe Object](sqlpipe-object.md) </span></span>  
 <span data-ttu-id="a8f39-137">[SqlTriggerContext-Objekt](sqltriggercontext-object.md) </span><span class="sxs-lookup"><span data-stu-id="a8f39-137">[SqlTriggerContext Object](sqltriggercontext-object.md) </span></span>  
 <span data-ttu-id="a8f39-138">[CLR-Trigger](../../database-engine/dev-guide/clr-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="a8f39-138">[CLR Triggers](../../database-engine/dev-guide/clr-triggers.md) </span></span>  
 [<span data-ttu-id="a8f39-139">Von SQL Server verwendete prozessinterne spezifische Erweiterungen für ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a8f39-139">SQL Server In-Process Specific Extensions to ADO.NET</span></span>](sql-server-in-process-specific-extensions-to-ado-net.md)  
  
  
