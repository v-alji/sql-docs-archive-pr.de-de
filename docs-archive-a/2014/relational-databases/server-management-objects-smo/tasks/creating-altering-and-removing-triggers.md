---
title: Erstellen, ändern und Entfernen von Triggern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- triggers [SMO]
ms.assetid: 8ddbe23b-6e31-4f8e-8a70-17bd5072413e
author: stevestein
ms.author: sstein
ms.openlocfilehash: c2cdd1573c488fbe7b2309f656cd6bf42e82a527
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621980"
---
# <a name="creating-altering-and-removing-triggers"></a><span data-ttu-id="121a4-102">Erstellen, Ändern und Löschen von Trigger</span><span class="sxs-lookup"><span data-stu-id="121a4-102">Creating, Altering, and Removing Triggers</span></span>
  <span data-ttu-id="121a4-103">In SMO werden Trigger durch das <xref:Microsoft.SqlServer.Management.Smo.Trigger>-Objekt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="121a4-103">In SMO, triggers are represented by using the <xref:Microsoft.SqlServer.Management.Smo.Trigger> object.</span></span> <span data-ttu-id="121a4-104">Der [!INCLUDE[tsql](../../../includes/tsql-md.md)] Code, der ausgeführt wird, wenn der ausgelöste ausgelöste Wert durch die- <xref:Microsoft.SqlServer.Management.Smo.Trigger.TextBody%2A> Eigenschaft des triggerobjekts festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="121a4-104">The [!INCLUDE[tsql](../../../includes/tsql-md.md)] code that runs when the trigger that is fired is set by the <xref:Microsoft.SqlServer.Management.Smo.Trigger.TextBody%2A> property of the Trigger object.</span></span> <span data-ttu-id="121a4-105">Der Typ des Triggers wird über andere Eigenschaften des <xref:Microsoft.SqlServer.Management.Smo.Trigger>-Objekts gesetzt, beispielsweise durch die <xref:Microsoft.SqlServer.Management.Smo.Trigger.Update%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="121a4-105">The type of trigger is set by using other properties of the <xref:Microsoft.SqlServer.Management.Smo.Trigger> object, such as the <xref:Microsoft.SqlServer.Management.Smo.Trigger.Update%2A> property.</span></span> <span data-ttu-id="121a4-106">Hierbei handelt es sich um eine boolesche Eigenschaft, die angibt, ob der Trigger durch ein `UPDATE` von Datensätzen auf der übergeordneten Tabelle ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="121a4-106">This is a Boolean property that specifies whether the trigger is fired by an `UPDATE` of records on the parent table.</span></span>  
  
 <span data-ttu-id="121a4-107">Das <xref:Microsoft.SqlServer.Management.Smo.Trigger>-Objekt stellt herkömmlicherweise Datenbearbeitungssprachentrigger (DML) dar.</span><span class="sxs-lookup"><span data-stu-id="121a4-107">The <xref:Microsoft.SqlServer.Management.Smo.Trigger> object represents traditional, data manipulation language (DML) triggers.</span></span> <span data-ttu-id="121a4-108">In [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] und höheren Versionen werden auch DDL (Data Definition Language)-Trigger unterstützt.</span><span class="sxs-lookup"><span data-stu-id="121a4-108">In [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] and later versions, data definition language (DDL) triggers are also supported.</span></span> <span data-ttu-id="121a4-109">DDL-Trigger werden durch das <xref:Microsoft.SqlServer.Management.Smo.DatabaseDdlTrigger>-Objekt und das <xref:Microsoft.SqlServer.Management.Smo.ServerDdlTrigger>-Objekt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="121a4-109">DDL triggers are represented by the <xref:Microsoft.SqlServer.Management.Smo.DatabaseDdlTrigger> object and the <xref:Microsoft.SqlServer.Management.Smo.ServerDdlTrigger> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="121a4-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="121a4-110">Example</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="creating-altering-and-removing-a-trigger-in-visual-basic"></a><span data-ttu-id="121a4-111">Erstellen, Ändern und Löschen eines Triggers in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="121a4-111">Creating, Altering, and Removing a Trigger in Visual Basic</span></span>  
 <span data-ttu-id="121a4-112">Dieses Codebeispiel zeigt, wie ein UPDATE-Trigger für eine vorhandene Tabelle mit dem Namen `Sales`in der [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] -Datenbank erstellt und eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="121a4-112">This code example shows how to create and insert an update trigger on an existing table, named `Sales`, in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="121a4-113">Der Trigger sendet eine Erinnerungsmitteilung, wenn die Tabelle aktualisiert oder ein neuer Datensatz eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="121a4-113">The trigger sends a reminder message when the table is updated or a new record is inserted.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBTriggers1](SMO How to#SMO_VBTriggers1)]  -->  
  
## <a name="creating-altering-and-removing-a-trigger-in-visual-c"></a><span data-ttu-id="121a4-114">Erstellen, Ändern und Löschen eines Triggers in Visual C#</span><span class="sxs-lookup"><span data-stu-id="121a4-114">Creating, Altering, and Removing a Trigger in Visual C#</span></span>  
 <span data-ttu-id="121a4-115">Dieses Codebeispiel zeigt, wie ein UPDATE-Trigger für eine vorhandene Tabelle mit dem Namen `Sales`in der [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] -Datenbank erstellt und eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="121a4-115">This code example shows how to create and insert an update trigger on an existing table, named `Sales`, in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="121a4-116">Der Trigger sendet eine Erinnerungsmitteilung, wenn die Tabelle aktualisiert oder ein neuer Datensatz eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="121a4-116">The trigger sends a reminder message when the table is updated or a new record is inserted.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server mysrv;  
            mysrv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database mydb;  
            mydb = mysrv.Databases["AdventureWorks2012"];  
            //Declare a Table object variable and reference the Customer table.   
            Table mytab;  
            mytab = mydb.Tables["Customer", "Sales"];  
            //Define a Trigger object variable by supplying the parent table, schema ,and name in the constructor.   
            Trigger tr;  
            tr = new Trigger(mytab, "Sales");  
            //Set TextMode property to False, then set other properties to define the trigger.   
            tr.TextMode = false;  
            tr.Insert = true;  
            tr.Update = true;  
            tr.InsertOrder = ActivationOrder.First;  
            string stmt;  
            stmt = " RAISERROR('Notify Customer Relations',16,10) ";  
            tr.TextBody = stmt;  
            tr.ImplementationType = ImplementationType.TransactSql;  
            //Create the trigger on the instance of SQL Server.   
            tr.Create();  
            //Remove the trigger.   
            tr.Drop();  
        }  
```  
  
## <a name="creating-altering-and-removing-a-trigger-in-powershell"></a><span data-ttu-id="121a4-117">Erstellen, Ändern und Löschen eines Triggers in PowerShell</span><span class="sxs-lookup"><span data-stu-id="121a4-117">Creating, Altering, and Removing a Trigger in PowerShell</span></span>  
 <span data-ttu-id="121a4-118">Dieses Codebeispiel zeigt, wie ein UPDATE-Trigger für eine vorhandene Tabelle mit dem Namen `Sales`in der [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] -Datenbank erstellt und eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="121a4-118">This code example shows how to create and insert an update trigger on an existing table, named `Sales`, in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="121a4-119">Der Trigger sendet eine Erinnerungsmitteilung, wenn die Tabelle aktualisiert oder ein neuer Datensatz eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="121a4-119">The trigger sends a reminder message when the table is updated or a new record is inserted.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and to the  
#database tables in Adventureworks2012  
CD \sql\localhost\default\databases\AdventureWorks2012\Tables\  
  
#Get reference to the trigger's target table  
$mytab = Get-Item Sales.Customer  
  
# Define a Trigger object variable by supplying the parent table, schema ,and name in the constructor.  
$tr = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Trigger -argumentlist $mytab, "Sales"  
  
# Set TextMode property to False, then set other properties to define the trigger.
$tr.TextMode = $false  
$tr.Insert = $true  
$tr.Update = $true  
$tr.InsertOrder = [Microsoft.SqlServer.Management.SMO.Agent.ActivationOrder]::First  
$tr.TextBody = " RAISERROR('Notify Customer Relations',16,10) "  
$tr.ImplementationType = [Microsoft.SqlServer.Management.SMO.ImplementationType]::TransactSql  
  
# Create the trigger on the instance of SQL Server.
$tr.Create()  
  
#Remove the trigger.
$tr.Drop()  
```  
