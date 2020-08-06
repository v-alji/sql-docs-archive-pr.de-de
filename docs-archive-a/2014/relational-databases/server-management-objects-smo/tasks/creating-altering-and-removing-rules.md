---
title: Erstellen, ändern und Löschen von Regeln | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- rules [SMO]
ms.assetid: 16981459-524e-4b39-a899-4370eaf763cc
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7742a9cb718bdde4f268d5226c45eba475f44ddd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620256"
---
# <a name="creating-altering-and-removing-rules"></a><span data-ttu-id="7fed9-102">Erstellen, Ändern und Löschen von Regeln</span><span class="sxs-lookup"><span data-stu-id="7fed9-102">Creating, Altering, and Removing Rules</span></span>
  <span data-ttu-id="7fed9-103">In SMO werden Regeln durch das <xref:Microsoft.SqlServer.Management.Smo.Rule>-Objekt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="7fed9-103">In SMO, rules are represented by the <xref:Microsoft.SqlServer.Management.Smo.Rule> object.</span></span> <span data-ttu-id="7fed9-104">Die Regel wird durch die <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A>-Eigenschaft definiert, wobei es sich um eine Textzeichenfolge handelt, die einen Bedingungsausdruck enthält, der Operatoren oder Prädikate wie IN, LIKE oder BETWEEN verwendet.</span><span class="sxs-lookup"><span data-stu-id="7fed9-104">The rule is defined by the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> property, which is a text string that contains a condition expression that uses operators or predicates, such as IN, LIKE, or BETWEEN.</span></span> <span data-ttu-id="7fed9-105">Eine Regel kann nicht auf Spalten oder andere Datenbankobjekte verweisen.</span><span class="sxs-lookup"><span data-stu-id="7fed9-105">A rule cannot reference columns or other database objects.</span></span> <span data-ttu-id="7fed9-106">Integrierte Funktionen, die nicht auf Datenbankobjekte verweisen, dürfen in einer Regel eingeschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="7fed9-106">Built-in functions that do not reference database objects can be included.</span></span>  
  
 <span data-ttu-id="7fed9-107">Die Definition in der <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A>-Eigenschaft muss eine Variable enthalten, die auf den eingegebenen Datenwert verweist.</span><span class="sxs-lookup"><span data-stu-id="7fed9-107">The definition in the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> property must contain a variable that refers to the data value entered.</span></span> <span data-ttu-id="7fed9-108">Ein beliebiger Name oder Symbol kann verwendet werden, um den Wert beim Erstellen der Regel darzustellen, aber das erste Zeichen muss das \@ Symbol sein.</span><span class="sxs-lookup"><span data-stu-id="7fed9-108">Any name or symbol can be used to represent the value when creating the rule, but the first character must be the \@ symbol.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fed9-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7fed9-109">Example</span></span>  
 <span data-ttu-id="7fed9-110">Zum Verwenden eines angegebenen Codebeispiels müssen Sie die Programmierumgebung, Programmiervorlage und die zu verwendende Programmiersprache auswählen, um Ihre Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7fed9-110">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="7fed9-111">Weitere Informationen finden Sie unter [Erstellen eines Visual Basic SMO-Projekts in Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) oder [Erstellen eines Visual C&#35; SMO-Projekts in Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="7fed9-111">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-altering-and-removing-a-rule-in-visual-basic"></a><span data-ttu-id="7fed9-112">Erstellen, Ändern und Entfernen einer Regel in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7fed9-112">Creating, Altering, and Removing a Rule in Visual Basic</span></span>  
 <span data-ttu-id="7fed9-113">Dieses Codebeispiel zeigt, wie eine Regel erstellt und an eine Spalte angefügt wird, wie Eigenschaften des <xref:Microsoft.SqlServer.Management.Smo.Rule>-Objekts geändert werden, die Regel von der Spalte getrennt und anschließend gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="7fed9-113">This code sample shows how to create a rule, attach it to a column, modify properties of the <xref:Microsoft.SqlServer.Management.Smo.Rule> object, detach it from the column, and then drop it.</span></span>  
  
 <span data-ttu-id="7fed9-114">Die `Dim`-Anweisung für das <xref:Microsoft.SqlServer.Management.Smo.Rule>-Objekt wird mit dem vollständigen Assemblypfad angegeben, um Mehrdeutigkeit in Bezug auf ein <xref:Microsoft.SqlServer.Management.Smo.Rule>-Objekt in der System.Data-Assembly zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="7fed9-114">The `Dim` statement for the <xref:Microsoft.SqlServer.Management.Smo.Rule> object is specified with the full assembly path to avoid ambiguity with a <xref:Microsoft.SqlServer.Management.Smo.Rule> object in the System.Data assembly.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBRules1](SMO How to#SMO_VBRules1)]  -->  
  
## <a name="creating-altering-and-removing-a-rule-in-visual-c"></a><span data-ttu-id="7fed9-115">Erstellen, Ändern und Löschen einer Regel in Visual C#</span><span class="sxs-lookup"><span data-stu-id="7fed9-115">Creating, Altering, and Removing a Rule in Visual C#</span></span>  
 <span data-ttu-id="7fed9-116">Dieses Codebeispiel zeigt, wie eine Regel erstellt und an eine Spalte angefügt wird, wie Eigenschaften des <xref:Microsoft.SqlServer.Management.Smo.Rule>-Objekts geändert werden, die Regel von der Spalte getrennt und anschließend gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="7fed9-116">This code sample shows how to create a rule, attach it to a column, modify properties of the <xref:Microsoft.SqlServer.Management.Smo.Rule> object, detach it from the column, and then drop it.</span></span>  
  
 <span data-ttu-id="7fed9-117">Die `Dim`-Anweisung für das <xref:Microsoft.SqlServer.Management.Smo.Rule>-Objekt wird mit dem vollständigen Assemblypfad angegeben, um Mehrdeutigkeit in Bezug auf ein <xref:Microsoft.SqlServer.Management.Smo.Rule>-Objekt in der System.Data-Assembly zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="7fed9-117">The `Dim` statement for the <xref:Microsoft.SqlServer.Management.Smo.Rule> object is specified with the full assembly path to avoid ambiguity with a <xref:Microsoft.SqlServer.Management.Smo.Rule> object in the System.Data assembly.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv;  
            srv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database db;  
            db = srv.Databases["AdventureWorks2012"];  
  
            //Define a Rule object variable by supplying the parent database, name and schema in the constructor.   
            //Note that the full namespace must be given for the Rule type to differentiate it from other Rule types.   
            Microsoft.SqlServer.Management.Smo.Rule ru;  
            ru = new Rule(db, "TestRule", "Production");  
            //Set the TextHeader and TextBody properties to define the rule.   
            ru.TextHeader = "CREATE RULE [Production].[TestRule] AS";  
            ru.TextBody = "@value BETWEEN GETDATE() AND DATEADD(year,4,GETDATE())";  
            //Create the rule on the instance of SQL Server.   
            ru.Create();  
            //Bind the rule to a column in the Product table by supplying the table, schema, and   
            //column as arguments in the BindToColumn method.   
            ru.BindToColumn("Product", "SellEndDate", "Production");  
            //Unbind from the column before removing the rule from the database.   
            ru.UnbindFromColumn("Product", "SellEndDate", "Production");  
            ru.Drop();  
  
        }  
```  
  
## <a name="creating-altering-and-removing-a-rule-in-powershell"></a><span data-ttu-id="7fed9-118">Erstellen, Ändern und Löschen einer Regel in PowerShell</span><span class="sxs-lookup"><span data-stu-id="7fed9-118">Creating, Altering, and Removing a Rule in PowerShell</span></span>  
 <span data-ttu-id="7fed9-119">Dieses Codebeispiel zeigt, wie eine Regel erstellt und an eine Spalte angefügt wird, wie Eigenschaften des <xref:Microsoft.SqlServer.Management.Smo.Rule>-Objekts geändert werden, die Regel von der Spalte getrennt und anschließend gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="7fed9-119">This code sample shows how to create a rule, attach it to a column, modify properties of the <xref:Microsoft.SqlServer.Management.Smo.Rule> object, detach it from the column, and then drop it.</span></span>  
  
 <span data-ttu-id="7fed9-120">Die `Dim`-Anweisung für das <xref:Microsoft.SqlServer.Management.Smo.Rule>-Objekt wird mit dem vollständigen Assemblypfad angegeben, um Mehrdeutigkeit in Bezug auf ein <xref:Microsoft.SqlServer.Management.Smo.Rule>-Objekt in der System.Data-Assembly zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="7fed9-120">The `Dim` statement for the <xref:Microsoft.SqlServer.Management.Smo.Rule> object is specified with the full assembly path to avoid ambiguity with a <xref:Microsoft.SqlServer.Management.Smo.Rule> object in the System.Data assembly.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = Get-Item Adventureworks2012  
  
# Define a Rule object variable by supplying the parent database, name and schema in the constructor.
$ru = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Rule -argumentlist $db, "TestRule", "Production"  
  
#Set the TextHeader and TextBody properties to define the rule.
$ru.TextHeader = "CREATE RULE [Production].[TestRule] AS"  
$ru.TextBody = "@value BETWEEN GETDATE() AND DATEADD(year,4,GETDATE())"  
  
#Create the rule on the instance of SQL Server.
$ru.Create()  
  
# Bind the rule to a column in the Product table by supplying the table, schema, and column as arguments in the BindToColumn method.
$ru.BindToColumn("Product", "SellEndDate", "Production")  
  
#Unbind from the column before removing the rule from the database.
$ru.UnbindFromColumn("Product", "SellEndDate", "Production")  
$ru.Drop()  
```  
  
## <a name="see-also"></a><span data-ttu-id="7fed9-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7fed9-121">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Rule>  
