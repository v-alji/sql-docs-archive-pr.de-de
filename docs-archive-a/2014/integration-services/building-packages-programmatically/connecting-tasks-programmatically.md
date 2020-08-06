---
title: Programmgesteuertes Verbinden von Tasks | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- tasks [Integration Services], precedence constraints
- precedence constraints [Integration Services], connecting tasks
- constraints [Integration Services]
ms.assetid: 23668e88-cef4-4009-a9cf-38e607eab7a2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5aeeb70ed5741cc7372fdfc63e637fd53d932f91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616643"
---
# <a name="connecting-tasks-programmatically"></a><span data-ttu-id="134c4-102">Programmgesteuertes Verbinden von Tasks</span><span class="sxs-lookup"><span data-stu-id="134c4-102">Connecting Tasks Programmatically</span></span>
  <span data-ttu-id="134c4-103">Eine Rangfolgeneinschränkung, die in dem Objektmodell durch die <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>-Klasse dargestellt wird, legt die Reihenfolge, in der die <xref:Microsoft.SqlServer.Dts.Runtime.Executable>-Objekte in einem Paket ausgeführt werden, fest.</span><span class="sxs-lookup"><span data-stu-id="134c4-103">A precedence constraint, represented in the object model by the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> class, establishes the order in which <xref:Microsoft.SqlServer.Dts.Runtime.Executable> objects run in a package.</span></span> <span data-ttu-id="134c4-104">Durch die Rangfolgeneinschränkung kann die Ausführung der Container und Tasks in einem Paket von dem Ergebnis der Ausführung eines vorherigen Tasks oder Containers abhängig gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="134c4-104">The precedence constraint allows the execution of the containers and tasks in a package to be dependent on the result of the execution of a previous task or container.</span></span> <span data-ttu-id="134c4-105">Rangfolgeneinschränkungen werden zwischen <xref:Microsoft.SqlServer.Dts.Runtime.Executable>-Objektpaaren durch Aufrufen der <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraints.Add%2A>-Methode der <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraints>-Auflistung für das Containerobjekt eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="134c4-105">Precedence constraints are established between pairs of <xref:Microsoft.SqlServer.Dts.Runtime.Executable> objects by calling the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraints.Add%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraints> collection on the container object.</span></span> <span data-ttu-id="134c4-106">Nachdem Sie eine Einschränkung zwischen zwei ausführbaren Objekten erstellt haben, legen Sie die <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A>-Eigenschaft fest, um die Kriterien für die Ausführung des zweiten ausführbaren in der Einschränkung definierten Objekts festzulegen.</span><span class="sxs-lookup"><span data-stu-id="134c4-106">After you create a constraint between two executable objects, you set the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> property to establish the criteria for executing the second executable defined in the constraint.</span></span>  
  
 <span data-ttu-id="134c4-107">Abhängig von dem Wert, den Sie, wie in der folgenden Tabelle beschrieben, für die <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.EvalOp%2A>-Eigenschaft festlegen, können Sie in einer einzigen Rangfolgeneinschränkung sowohl eine Einschränkung als auch einen Ausdruck verwenden:</span><span class="sxs-lookup"><span data-stu-id="134c4-107">You can use both a constraint and an expression in a single precedence constraint, depending on the value that you specify for the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.EvalOp%2A> property, as described in the following table:</span></span>  
  
|<span data-ttu-id="134c4-108">Wert der EvalOp-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="134c4-108">Value of the EvalOp property</span></span>|<span data-ttu-id="134c4-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="134c4-109">Description</span></span>|  
|----------------------------------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DTSPrecedenceEvalOp.Constraint>|<span data-ttu-id="134c4-110">Gibt an, dass das Ausführungsergebnis bestimmt, ob der eingeschränkte Container oder Task ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="134c4-110">Specifies that the execution outcome determines whether the constrained container or task runs.</span></span> <span data-ttu-id="134c4-111">Legen Sie für die <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A>-Eigenschaft von <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> den gewünschten Wert aus der <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>-Enumeration fest.</span><span class="sxs-lookup"><span data-stu-id="134c4-111">Set the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> to the desired value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeration.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DTSPrecedenceEvalOp.Expression>|<span data-ttu-id="134c4-112">Gibt an, dass der Wert eines Ausdrucks bestimmt, ob der eingeschränkte Container oder Task ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="134c4-112">Specifies that the value of an expression determines whether the constrained container or task runs.</span></span> <span data-ttu-id="134c4-113">Legen Sie die <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A>-Eigenschaft von <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> fest.</span><span class="sxs-lookup"><span data-stu-id="134c4-113">Set the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DTSPrecedenceEvalOp.ExpressionAndConstraint>|<span data-ttu-id="134c4-114">Gibt an, dass das Einschränkungsergebnis auftreten und der Ausdruck ausgewertet werden muss, damit der eingeschränkte Container oder Task ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="134c4-114">Specifies that the constraint outcome must occur and the expression must evaluate for the constrained container or task to run.</span></span> <span data-ttu-id="134c4-115">Legen Sie sowohl die <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A>- als auch die <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A>-Eigenschaften von <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> fest, und legen Sie die <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.LogicalAnd%2A>-Eigenschaft als `true` fest.</span><span class="sxs-lookup"><span data-stu-id="134c4-115">Set both the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> and the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> properties of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, and set its <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.LogicalAnd%2A> property to `true`.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DTSPrecedenceEvalOp.ExpressionOrConstraint>|<span data-ttu-id="134c4-116">Gibt an, dass entweder das Einschränkungsergebnis auftreten oder der Ausdruck ausgewertet werden muss, damit der eingeschränkte Container oder Task ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="134c4-116">Specifies that either the constraint outcome must occur, or the expression must evaluate, for the constrained container or task to run.</span></span> <span data-ttu-id="134c4-117">Legen Sie sowohl die <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A>- als auch die <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A>-Eigenschaften von <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> fest, und legen Sie die <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.LogicalAnd%2A>-Eigenschaft als `false` fest.</span><span class="sxs-lookup"><span data-stu-id="134c4-117">Set both the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> and the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> properties of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, and set its <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.LogicalAnd%2A> property to `false`.</span></span>|  
  
 <span data-ttu-id="134c4-118">Im folgenden Codebeispiel wird das Hinzufügen von zwei Tasks zu einem Paket veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="134c4-118">The following code sample demonstrates adding two tasks to a package.</span></span> <span data-ttu-id="134c4-119">Zwischen ihnen wird eine <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> erstellt, die verhindert, dass der zweite Task vor Beendung des ersten Tasks ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="134c4-119">A <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> is created between them that prevents the second task from running until the first task finishes.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
  
      // Add a File System task.  
      Executable eFileTask1 = p.Executables.Add("STOCK:FileSystemTask");  
      TaskHost thFileHost1 = eFileTask1 as TaskHost;  
  
      // Add a second File System task.  
      Executable eFileTask2 = p.Executables.Add("STOCK:FileSystemTask");  
      TaskHost thFileHost2 = eFileTask2 as TaskHost;  
  
      // Put a precedence constraint between the tasks.  
      // Set the constraint to specify that the second File System task cannot run  
      // until the first File System task finishes.  
      PrecedenceConstraint pcFileTasks =   
        p.PrecedenceConstraints.Add((Executable)thFileHost1, (Executable)thFileHost2);  
      pcFileTasks.Value = DTSExecResult.Completion;  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    ' Add a File System task.  
    Dim eFileTask1 As Executable = p.Executables.Add("STOCK:FileSystemTask")  
    Dim thFileHost1 As TaskHost = CType(eFileTask1, TaskHost)  
  
    ' Add a second File System task.  
    Dim eFileTask2 As Executable = p.Executables.Add("STOCK:FileSystemTask")  
    Dim thFileHost2 As TaskHost = CType(eFileTask2, TaskHost)  
  
    ' Put a precedence constraint between the tasks.  
    ' Set the constraint to specify that the second File System task cannot run  
    ' until the first File System task finishes.  
    Dim pcFileTasks As PrecedenceConstraint = _  
      p.PrecedenceConstraints.Add(CType(thFileHost1, Executable), CType(thFileHost2, Executable))  
    pcFileTasks.Value = DTSExecResult.Completion  
  
  End Sub  
  
End Module  
```  
  
<span data-ttu-id="134c4-120">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="134c4-120">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="134c4-121">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="134c4-121">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="134c4-122">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="134c4-122">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="134c4-123">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="134c4-123">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="134c4-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="134c4-124">See Also</span></span>  
 [<span data-ttu-id="134c4-125">Programmgesteuertes Hinzufügen des Datenflusstasks</span><span class="sxs-lookup"><span data-stu-id="134c4-125">Adding the Data Flow Task Programmatically</span></span>](../building-packages-programmatically/adding-the-data-flow-task-programmatically.md)  
  
  
