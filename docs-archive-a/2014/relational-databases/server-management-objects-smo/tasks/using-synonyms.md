---
title: Verwenden von Synonymen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- synonyms [SMO]
ms.assetid: db0a9022-9549-43e5-b6b3-deb236f05fb8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5e8416dc3daea3b173fae92e5454a8a65c399e53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622509"
---
# <a name="using-synonyms"></a><span data-ttu-id="f42c9-102">Verwenden von Synonymen</span><span class="sxs-lookup"><span data-stu-id="f42c9-102">Using Synonyms</span></span>
  <span data-ttu-id="f42c9-103">Ein Synonym ist ein alternativer Name für ein Objekt mit Schemabereich.</span><span class="sxs-lookup"><span data-stu-id="f42c9-103">A synonym is an alternative name for a schema-scoped object.</span></span> <span data-ttu-id="f42c9-104">In SMO werden Synonyme durch das <xref:Microsoft.SqlServer.Management.Smo.Synonym>-Objekt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f42c9-104">In SMO, synonyms are represented by the <xref:Microsoft.SqlServer.Management.Smo.Synonym> object.</span></span> <span data-ttu-id="f42c9-105">Das <xref:Microsoft.SqlServer.Management.Smo.Synonym>-Objekt ist dem <xref:Microsoft.SqlServer.Management.Smo.Database>-Objekt untergeordnet.</span><span class="sxs-lookup"><span data-stu-id="f42c9-105">The <xref:Microsoft.SqlServer.Management.Smo.Synonym> object is a child of the <xref:Microsoft.SqlServer.Management.Smo.Database> object.</span></span> <span data-ttu-id="f42c9-106">Dies bedeutet, dass Synonyme nur in dem Kontext der Datenbank gültig sind, in der sie definiert sind.</span><span class="sxs-lookup"><span data-stu-id="f42c9-106">This means that synonyms are valid only within the scope of the database in which they are defined.</span></span> <span data-ttu-id="f42c9-107">Allerdings kann das Synonym auf Objekte einer anderen Datenbank oder auf eine Remoteinstanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]verweisen.</span><span class="sxs-lookup"><span data-stu-id="f42c9-107">However, the synonym can refer to objects on another database, or on a remote instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f42c9-108">Das Objekt, dem ein alternativer Name gegeben wird, wird als Basisobjekt bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f42c9-108">The object that is given an alternative name is known as the base object.</span></span> <span data-ttu-id="f42c9-109">Die Name-Eigenschaft des <xref:Microsoft.SqlServer.Management.Smo.Synonym>-Objekts ist ein alternativer Name, der an das Basisobjekt vergeben wird.</span><span class="sxs-lookup"><span data-stu-id="f42c9-109">The name property of the <xref:Microsoft.SqlServer.Management.Smo.Synonym> object is the alternative name given to the base object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f42c9-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f42c9-110">Example</span></span>  
 <span data-ttu-id="f42c9-111">Für das folgende Codebeispiel müssen Sie die Programmierungsumgebung, die Programmiervorlage und die Programmiersprache auswählen, um Ihre Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f42c9-111">For the following code example, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="f42c9-112">Weitere Informationen finden Sie unter [Erstellen eines Visual Basic SMO-Projekts in Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) und [Erstellen eines Visual C&#35; SMO-Projekts in Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="f42c9-112">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-synonym-in-visual-basic"></a><span data-ttu-id="f42c9-113">Erstellen eines Synonyms in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f42c9-113">Creating a Synonym in Visual Basic</span></span>  
 <span data-ttu-id="f42c9-114">Dieses Codebeispiel zeigt, wie ein Synonym oder ein alternativer Name für ein Objekt mit Schemabereich erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f42c9-114">The code example shows how to create a synonym or an alternate name for a schema scoped object.</span></span> <span data-ttu-id="f42c9-115">Clientanwendungen können einen einzelnen Verweis für das Basisobjekt über ein Synonym verwenden, anstatt einen mehrteiligen Namen zu verwenden, der auf das Basisobjekt verweist.</span><span class="sxs-lookup"><span data-stu-id="f42c9-115">Client applications can use a single reference for the base object via a synonym instead of using a multiple part name to reference the base object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBSynonyms1](SMO How to#SMO_VBSynonyms1)]  -->  
  
## <a name="creating-a-synonym-in-visual-c"></a><span data-ttu-id="f42c9-116">Erstellen eines Synonyms in Visual C#</span><span class="sxs-lookup"><span data-stu-id="f42c9-116">Creating a Synonym in Visual C#</span></span>  
 <span data-ttu-id="f42c9-117">Dieses Codebeispiel zeigt, wie ein Synonym oder ein alternativer Name für ein Objekt mit Schemabereich erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f42c9-117">The code example shows how to create a synonym or an alternate name for a schema scoped object.</span></span> <span data-ttu-id="f42c9-118">Clientanwendungen können einen einzelnen Verweis für das Basisobjekt über ein Synonym verwenden, anstatt einen mehrteiligen Namen zu verwenden, der auf das Basisobjekt verweist.</span><span class="sxs-lookup"><span data-stu-id="f42c9-118">Client applications can use a single reference for the base object via a synonym instead of using a multiple part name to reference the base object.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv = new Server();  
  
            //Reference the AdventureWorks2012 database.   
            Database db = srv.Databases["AdventureWorks2012"];  
  
            //Define a Synonym object variable by supplying the   
            //parent database, name, and schema arguments in the constructor.   
            //The name is also a synonym of the name of the base object.   
            Synonym syn = new Synonym(db, "Shop", "Sales");  
  
            //Specify the base object, which is the object on which   
            //the synonym is based.   
            syn.BaseDatabase = "AdventureWorks2012";  
            syn.BaseSchema = "Sales";  
            syn.BaseObject = "Store";  
            syn.BaseServer = srv.Name;  
  
            //Create the synonym on the instance of SQL Server.   
            syn.Create();  
        }  
```  
  
## <a name="creating-a-synonym-in-powershell"></a><span data-ttu-id="f42c9-119">Erstellen eines Synonyms in PowerShell</span><span class="sxs-lookup"><span data-stu-id="f42c9-119">Creating a Synonym in PowerShell</span></span>  
 <span data-ttu-id="f42c9-120">Dieses Codebeispiel zeigt, wie ein Synonym oder ein alternativer Name für ein Objekt mit Schemabereich erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f42c9-120">The code example shows how to create a synonym or an alternate name for a schema scoped object.</span></span> <span data-ttu-id="f42c9-121">Clientanwendungen können einen einzelnen Verweis für das Basisobjekt über ein Synonym verwenden, anstatt einen mehrteiligen Namen zu verwenden, der auf das Basisobjekt verweist.</span><span class="sxs-lookup"><span data-stu-id="f42c9-121">Client applications can use a single reference for the base object via a synonym instead of using a multiple part name to reference the base object.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#And the database object corresponding to Adventureworks  
$db = $srv.Databases["AdventureWorks2012"]  
  
$syn = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Synonym -ArgumentList $db, "Shop", "Sales"  
  
#Specify the base object, which is the object on which the synonym is based.  
$syn.BaseDatabase = "AdventureWorks2012"  
$syn.BaseSchema = "Sales"  
$syn.BaseObject = "Store"  
$syn.BaseServer = $srv.Name  
  
#Create the synonym on the instance of SQL Server.  
$syn.Create()  
```  
  
## <a name="see-also"></a><span data-ttu-id="f42c9-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f42c9-122">See Also</span></span>  
 [<span data-ttu-id="f42c9-123">CREATE SYNONYM &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f42c9-123">CREATE SYNONYM &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-synonym-transact-sql)  
