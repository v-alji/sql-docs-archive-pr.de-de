---
title: Erstellen, ändern und Löschen von Datenbanken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- databases [SMO]
- databases [SMO], creating
- databases [SMO], modifying
- databases [SMO], deleting
ms.assetid: fcfb3ec2-7556-4f72-971a-501295892cb0
author: stevestein
ms.author: sstein
ms.openlocfilehash: e8bd34e939fcbc1ecfc5238f5fc4524d187d3f30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723662"
---
# <a name="creating-altering-and-removing-databases"></a><span data-ttu-id="1f404-102">Erstellen, Ändern und Löschen von Datenbanken</span><span class="sxs-lookup"><span data-stu-id="1f404-102">Creating, Altering, and Removing Databases</span></span>
  <span data-ttu-id="1f404-103">In SMO wird eine Datenbank durch das <xref:Microsoft.SqlServer.Management.Smo.Database>-Objekt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1f404-103">In SMO, a database is represented by the <xref:Microsoft.SqlServer.Management.Smo.Database> object.</span></span>  
  
 <span data-ttu-id="1f404-104">Um diese zu ändern oder zu löschen, ist es nicht erforderlich, ein <xref:Microsoft.SqlServer.Management.Smo.Database>-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1f404-104">It is not necessary to create a <xref:Microsoft.SqlServer.Management.Smo.Database> object to modify or remove it.</span></span> <span data-ttu-id="1f404-105">Auf die Datenbank kann mit einer Sammlung verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="1f404-105">The database can be referenced by using a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f404-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1f404-106">Example</span></span>  
 <span data-ttu-id="1f404-107">Zum Verwenden eines angegebenen Codebeispiels müssen Sie die Programmierumgebung, Programmiervorlage und die zu verwendende Programmiersprache auswählen, um Ihre Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1f404-107">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="1f404-108">Weitere Informationen finden Sie unter [Erstellen eines Visual Basic SMO-Projekts in Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) oder [Erstellen eines Visual C&#35; SMO-Projekts in Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="1f404-108">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-altering-and-removing-a-database-in-visual-basic"></a><span data-ttu-id="1f404-109">Erstellen, Ändern und Löschen einer Datenbank in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1f404-109">Creating, Altering, and Removing a Database in Visual Basic</span></span>  
 <span data-ttu-id="1f404-110">In diesem Codebeispiel wird eine neue Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="1f404-110">This code example creates a new database.</span></span> <span data-ttu-id="1f404-111">Dateien und Dateigruppen werden für die Datenbank automatisch erstellt.</span><span class="sxs-lookup"><span data-stu-id="1f404-111">Files and file groups are automatically created for the database.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDatabase1](SMO How to#SMO_VBDatabase1)]  -->  
  
## <a name="creating-altering-and-removing-a-database-in-visual-c"></a><span data-ttu-id="1f404-112">Erstellen, Ändern und Löschen einer Datenbank in Visual C#</span><span class="sxs-lookup"><span data-stu-id="1f404-112">Creating, Altering, and Removing a Database in Visual C#</span></span>  
 <span data-ttu-id="1f404-113">In diesem Codebeispiel wird eine neue Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="1f404-113">This code example creates a new database.</span></span> <span data-ttu-id="1f404-114">Dateien und Dateigruppen werden für die Datenbank automatisch erstellt.</span><span class="sxs-lookup"><span data-stu-id="1f404-114">Files and file groups are automatically created for the database.</span></span>  
  
```csharp
{  
                //Connect to the local, default instance of SQL Server.   
                Server srv;  
                srv = new Server();  
                //Define a Database object variable by supplying the server and the database name arguments in the constructor.   
                Database db;  
                db = new Database(srv, "Test_SMO_Database");  
                //Create the database on the instance of SQL Server.   
                db.Create();  
                //Reference the database and display the date when it was created.   
                db = srv.Databases["Test_SMO_Database"];  
                Console.WriteLine(db.CreateDate);  
                //Remove the database.   
                db.Drop();  
            }  
```  
  
## <a name="creating-altering-and-removing-a-database-in-powershell"></a><span data-ttu-id="1f404-115">Erstellen, Ändern und Löschen einer Datenbank in PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f404-115">Creating, Altering, and Removing a Database in PowerShell</span></span>  
 <span data-ttu-id="1f404-116">In diesem Codebeispiel wird eine neue Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="1f404-116">This code example creates a new database.</span></span> <span data-ttu-id="1f404-117">Dateien und Dateigruppen werden für die Datenbank automatisch erstellt.</span><span class="sxs-lookup"><span data-stu-id="1f404-117">Files and file groups are automatically created for the database.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance  
cd \sql\localhost\  
$srv = Get-Item default  
  
#Create a new database  
$db = New-Object -TypeName Microsoft.SqlServer.Management.Smo.Database -argumentlist $srv, "Test_SMO_Database"  
$db.Create()  
  
#Reference the database and display the date when it was created.
$db = $srv.Databases["Test_SMO_Database"]  
$db.CreateDate  
  
#Drop the database  
$db.Drop()  
```  
  
## <a name="see-also"></a><span data-ttu-id="1f404-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1f404-118">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Database>  
