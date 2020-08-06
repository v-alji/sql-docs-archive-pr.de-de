---
title: Verwalten von Benutzern, Rollen und Anmeldungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- logins [SMO]
- roles [SMO]
- users [SMO]
ms.assetid: 74e411fa-74ed-49ec-ab58-68c250f2280e
author: stevestein
ms.author: sstein
ms.openlocfilehash: bb53e7b4a5748e46c7cb147e1cda50652d8b8805
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620249"
---
# <a name="managing-users-roles-and-logins"></a><span data-ttu-id="76ab7-102">Verwalten von Benutzern, Rollen und Anmeldungen</span><span class="sxs-lookup"><span data-stu-id="76ab7-102">Managing Users, Roles, and Logins</span></span>
  <span data-ttu-id="76ab7-103">In SMO werden Anmeldungen durch das <xref:Microsoft.SqlServer.Management.Smo.Login>-Objekt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="76ab7-103">In SMO, logins are represented by the <xref:Microsoft.SqlServer.Management.Smo.Login> object.</span></span> <span data-ttu-id="76ab7-104">Wenn die Anmeldung in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]vorhanden ist, kann sie zu einer Serverrolle hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="76ab7-104">When the logon exists in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], it can be added to a server role.</span></span> <span data-ttu-id="76ab7-105">Die Serverrolle wird durch das <xref:Microsoft.SqlServer.Management.Smo.ServerRole>-Objekt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="76ab7-105">The server role is represented by the <xref:Microsoft.SqlServer.Management.Smo.ServerRole> object.</span></span> <span data-ttu-id="76ab7-106">Die Datenbankrolle wird durch das <xref:Microsoft.SqlServer.Management.Smo.DatabaseRole>-Objekt und die Anwendungsrolle durch das <xref:Microsoft.SqlServer.Management.Smo.ApplicationRole>-Objekt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="76ab7-106">The database role is represented by the <xref:Microsoft.SqlServer.Management.Smo.DatabaseRole> object and the application role is represented by the <xref:Microsoft.SqlServer.Management.Smo.ApplicationRole> object.</span></span>  
  
 <span data-ttu-id="76ab7-107">Der Serverebene zugeordnete Berechtigungen werden als Eigenschaften des <xref:Microsoft.SqlServer.Management.Smo.ServerPermission>-Objekts aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="76ab7-107">Privileges associated with the server level are listed as properties of the <xref:Microsoft.SqlServer.Management.Smo.ServerPermission> object.</span></span> <span data-ttu-id="76ab7-108">Berechtigungen können für einzelne Anmeldekonten gewährt, verweigert oder aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="76ab7-108">The server level privileges can be granted to, denied to, or revoked from individual logon accounts.</span></span>  
  
 <span data-ttu-id="76ab7-109">Jedes <xref:Microsoft.SqlServer.Management.Smo.Database>-Objekt verfügt über ein <xref:Microsoft.SqlServer.Management.Smo.UserCollection>-Objekt, das alle Benutzer in der Datenbank angibt.</span><span class="sxs-lookup"><span data-stu-id="76ab7-109">Every <xref:Microsoft.SqlServer.Management.Smo.Database> object has a <xref:Microsoft.SqlServer.Management.Smo.UserCollection> object that specifies all users in the database.</span></span> <span data-ttu-id="76ab7-110">Jeder Benutzer wird einer Anmeldung zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="76ab7-110">Each user is associated with a logon.</span></span> <span data-ttu-id="76ab7-111">Eine Anmeldung kann Benutzern in mehr als einer Datenbank zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="76ab7-111">One logon can be associated with users in more than one database.</span></span> <span data-ttu-id="76ab7-112">Die <xref:Microsoft.SqlServer.Management.Smo.Login>-Methode des <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A>-Objekts kann verwendet werden, um alle Benutzer in allen Datenbanken aufzulisten, die der Anmeldung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="76ab7-112">The <xref:Microsoft.SqlServer.Management.Smo.Login> object's <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> method can be used to list all users in every database that is associated with the logon.</span></span> <span data-ttu-id="76ab7-113">Alternativ legt die <xref:Microsoft.SqlServer.Management.Smo.User>-Eigenschaft des <xref:Microsoft.SqlServer.Management.Smo.Login>-Objekts die Anmeldung fest, die dem Benutzer zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="76ab7-113">Alternatively, the <xref:Microsoft.SqlServer.Management.Smo.User> object's <xref:Microsoft.SqlServer.Management.Smo.Login> property specifies the logon that is associated with the user.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="76ab7-114">-Datenbanken verfügen darüber hinaus über Rollen, die eine Gruppe von Berechtigungen auf Datenbankebene festlegen, über die Benutzer bestimmte Tasks durchführen können.</span><span class="sxs-lookup"><span data-stu-id="76ab7-114">databases also have roles that specify a set of database level privileges that let a user perform specific tasks.</span></span> <span data-ttu-id="76ab7-115">Im Gegensatz zu Serverrollen sind Datenbankrollen variabel.</span><span class="sxs-lookup"><span data-stu-id="76ab7-115">Unlike server roles, database roles are not fixed.</span></span> <span data-ttu-id="76ab7-116">Sie können erstellt, geändert und gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="76ab7-116">They can be created, modified, and removed.</span></span> <span data-ttu-id="76ab7-117">Einer Datenbankrolle können für die Massenverwaltung Berechtigungen und Benutzer zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="76ab7-117">Privileges and users can be assigned to a database role for bulk administration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76ab7-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="76ab7-118">Example</span></span>  
 <span data-ttu-id="76ab7-119">Für das folgende Codebeispiel müssen Sie die Programmierungsumgebung, die Programmiervorlage und die Programmiersprache auswählen, um Ihre Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="76ab7-119">For the following code example, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="76ab7-120">Weitere Informationen finden Sie unter [Erstellen eines Visual Basic SMO-Projekts in Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) und [Erstellen eines Visual C&#35; SMO-Projekts in Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="76ab7-120">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="enumerating-logins-and-associated-users-in-visual-basic"></a><span data-ttu-id="76ab7-121">Auflisten von Anmeldungen und zugeordneten Benutzern in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="76ab7-121">Enumerating Logins and Associated Users in Visual Basic</span></span>  
 <span data-ttu-id="76ab7-122">Jeder Benutzer in einer Datenbank ist einer Anmeldung zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="76ab7-122">Every user in a database is associated with a logon.</span></span> <span data-ttu-id="76ab7-123">Die Anmeldung kann Benutzern in mehreren Datenbanken zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="76ab7-123">The logon can be associated with users in more than one database.</span></span> <span data-ttu-id="76ab7-124">Das Codebeispiel zeigt, wie die <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A>-Methode des <xref:Microsoft.SqlServer.Management.Smo.Login>-Objekts aufgerufen wird, um alle Datenbankbenutzer aufzulisten, die der Anmeldung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="76ab7-124">The code example shows how to call the <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> method of the <xref:Microsoft.SqlServer.Management.Smo.Login> object to list all the database users who are associated with the logon.</span></span> <span data-ttu-id="76ab7-125">Im Beispiel werden eine Anmeldung und ein Benutzer in der [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] -Datenbank erstellt, um sicherzustellen, dass Zuordnungsinformationen vorliegen, die aufgelistet werden können.</span><span class="sxs-lookup"><span data-stu-id="76ab7-125">The example creates a logon and user in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database to make sure there is mapping information to enumerate.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBLogins1](SMO How to#SMO_VBLogins1)]  -->  
  
## <a name="enumerating-logins-and-associated-users-in-visual-c"></a><span data-ttu-id="76ab7-126">Auflisten von Anmeldungen und zugeordneten Benutzern in Visual C#</span><span class="sxs-lookup"><span data-stu-id="76ab7-126">Enumerating Logins and Associated Users in Visual C#</span></span>  
 <span data-ttu-id="76ab7-127">Jeder Benutzer in einer Datenbank ist einer Anmeldung zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="76ab7-127">Every user in a database is associated with a logon.</span></span> <span data-ttu-id="76ab7-128">Die Anmeldung kann Benutzern in mehreren Datenbanken zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="76ab7-128">The logon can be associated with users in more than one database.</span></span> <span data-ttu-id="76ab7-129">Das Codebeispiel zeigt, wie die <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A>-Methode des <xref:Microsoft.SqlServer.Management.Smo.Login>-Objekts aufgerufen wird, um alle Datenbankbenutzer aufzulisten, die der Anmeldung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="76ab7-129">The code example shows how to call the <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> method of the <xref:Microsoft.SqlServer.Management.Smo.Login> object to list all the database users who are associated with the logon.</span></span> <span data-ttu-id="76ab7-130">Im Beispiel werden eine Anmeldung und ein Benutzer in der [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] -Datenbank erstellt, um sicherzustellen, dass Zuordnungsinformationen vorliegen, die aufgelistet werden können.</span><span class="sxs-lookup"><span data-stu-id="76ab7-130">The example creates a logon and user in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database to make sure there is mapping information to enumerate.</span></span>  
  
```csharp
{   
Server srv = new Server();   
//Iterate through each database and display.   
  
foreach ( Database db in srv.Databases) {   
   Console.WriteLine("========");   
   Console.WriteLine("Login Mappings for the database: " + db.Name);   
   Console.WriteLine(" ");   
   //Run the EnumLoginMappings method and return details of database user-login mappings to a DataTable object variable.   
   DataTable d;  
   d = db.EnumLoginMappings();   
   //Display the mapping information.   
   foreach (DataRow r in d.Rows) {   
      foreach (DataColumn c in r.Table.Columns) {   
         Console.WriteLine(c.ColumnName + " = " + r[c]);   
      }   
      Console.WriteLine(" ");   
   }   
}   
}  
```  
  
## <a name="enumerating-logins-and-associated-users-in-powershell"></a><span data-ttu-id="76ab7-131">Auflisten von Anmeldungen und zugeordneten Benutzern in PowerShell</span><span class="sxs-lookup"><span data-stu-id="76ab7-131">Enumerating Logins and Associated Users in PowerShell</span></span>  
 <span data-ttu-id="76ab7-132">Jeder Benutzer in einer Datenbank ist einer Anmeldung zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="76ab7-132">Every user in a database is associated with a logon.</span></span> <span data-ttu-id="76ab7-133">Die Anmeldung kann Benutzern in mehreren Datenbanken zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="76ab7-133">The logon can be associated with users in more than one database.</span></span> <span data-ttu-id="76ab7-134">Das Codebeispiel zeigt, wie die <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A>-Methode des <xref:Microsoft.SqlServer.Management.Smo.Login>-Objekts aufgerufen wird, um alle Datenbankbenutzer aufzulisten, die der Anmeldung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="76ab7-134">The code example shows how to call the <xref:Microsoft.SqlServer.Management.Smo.Login.EnumDatabaseMappings%2A> method of the <xref:Microsoft.SqlServer.Management.Smo.Login> object to list all the database users who are associated with the logon.</span></span> <span data-ttu-id="76ab7-135">Im Beispiel werden eine Anmeldung und ein Benutzer in der [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] -Datenbank erstellt, um sicherzustellen, dass Zuordnungsinformationen vorliegen, die aufgelistet werden können.</span><span class="sxs-lookup"><span data-stu-id="76ab7-135">The example creates a logon and user in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database to make sure there is mapping information to enumerate.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\Default\Databases  
  
#Iterate through all databases  
 foreach ($db in Get-ChildItem)  
 {  
 "====="  
 "Login Mappings for the database: "+ $db.Name  
  
 #get the datatable containing the mapping from the smo database object  
 $dt = $db.EnumLoginMappings()  
  
 #display the results  
 foreach($row in $dt.Rows)  
     {  
        foreach($col in $row.Table.Columns)  
      {  
        $col.ColumnName + "=" + $row[$col]  
       }
     }  
 }  
```  
  
## <a name="managing-roles-and-users"></a><span data-ttu-id="76ab7-136">Verwalten von Rollen und Benutzern</span><span class="sxs-lookup"><span data-stu-id="76ab7-136">Managing Roles and Users</span></span>  
 <span data-ttu-id="76ab7-137">Im folgenden Beispiel wird die Verwaltung von Rollen und Benutzern gezeigt.</span><span class="sxs-lookup"><span data-stu-id="76ab7-137">This sample demonstrates how to how to manage roles and users.</span></span> <span data-ttu-id="76ab7-138">Im ersten Beispiel wird C#, im zweiten Beispiel Visual Basic verwendet.</span><span class="sxs-lookup"><span data-stu-id="76ab7-138">The first sample uses C#, the second Visual Basic.</span></span> <span data-ttu-id="76ab7-139">Die folgenden Codebeispiele erfordern einen Verweis auf folgende Assemblys:</span><span class="sxs-lookup"><span data-stu-id="76ab7-139">These samples need to reference the following assemblies:</span></span>  
  
-   <span data-ttu-id="76ab7-140">Microsoft.SqlServer.Smo.dll</span><span class="sxs-lookup"><span data-stu-id="76ab7-140">Microsoft.SqlServer.Smo.dll</span></span>  
  
-   <span data-ttu-id="76ab7-141">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span><span class="sxs-lookup"><span data-stu-id="76ab7-141">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span></span>  
  
-   <span data-ttu-id="76ab7-142">Microsoft.SqlServer.ConnectionInfo.dll</span><span class="sxs-lookup"><span data-stu-id="76ab7-142">Microsoft.SqlServer.ConnectionInfo.dll</span></span>  
  
-   <span data-ttu-id="76ab7-143">Microsoft.SqlServer.SqlEnum.dll</span><span class="sxs-lookup"><span data-stu-id="76ab7-143">Microsoft.SqlServer.SqlEnum.dll</span></span>  
  
```csharp
using Microsoft.SqlServer.Management.Smo;  
using System;  
  
public class A {  
   public static void Main() {  
      Server svr = new Server();  
      Database db = new Database(svr, "TESTDB");  
      db.Create();  
  
      // Creating Logins  
      Login login = new Login(svr, "Login1");  
      login.LoginType = LoginType.SqlLogin;  
      login.Create("password@1");  
  
      Login login2 = new Login(svr, "Login2");  
      login2.LoginType = LoginType.SqlLogin;  
      login2.Create("password@1");  
  
      // Creating Users in the database for the logins created  
      User user1 = new User(db, "User1");  
      user1.Login = "Login1";  
      user1.Create();  
  
      User user2 = new User(db, "User2");  
      user2.Login = "Login2";  
      user2.Create();  
  
      // Creating database permission Sets  
      DatabasePermissionSet dbPermSet = new DatabasePermissionSet(DatabasePermission.AlterAnySchema);  
      dbPermSet.Add(DatabasePermission.AlterAnyUser);  
  
      DatabasePermissionSet dbPermSet2 = new DatabasePermissionSet(DatabasePermission.CreateType);  
      dbPermSet2.Add(DatabasePermission.CreateSchema);  
      dbPermSet2.Add(DatabasePermission.CreateTable);  
  
      // Creating Database roles  
      DatabaseRole role1 = new DatabaseRole(db, "Role1");  
      role1.Create();  
  
      DatabaseRole role2 = new DatabaseRole(db, "Role2");  
      role2.Create();  
  
      // Granting Database Permission Sets to Roles  
      db.Grant(dbPermSet, role1.Name);  
      db.Grant(dbPermSet2, role2.Name);  
  
      // Adding members (Users / Roles) to Role  
      role1.AddMember("User1");  
  
      role2.AddMember("User2");  
  
      // Role1 becomes a member of Role2  
      role2.AddMember("Role1");  
  
      // Enumerating through explicit permissions granted to Role1  
      // enumerates all database permissions for the Grantee  
      DatabasePermissionInfo[] dbPermsRole1 = db.EnumDatabasePermissions("Role1");     
      foreach (DatabasePermissionInfo dbp in dbPermsRole1) {  
         Console.WriteLine(dbp.Grantee + " has " + dbp.PermissionType.ToString() + " permission.");  
      }  
      Console.WriteLine(" ");  
   }  
}  
```  
  
 <span data-ttu-id="76ab7-144">Das ist die Visual Basic-Version:</span><span class="sxs-lookup"><span data-stu-id="76ab7-144">This is the Visual Basic version:</span></span>  
  
```vb
Imports Microsoft.SqlServer.Management.Smo  
  
Public Class A  
   Public Shared Sub Main()  
      Dim svr As New Server()  
      Dim db As New Database(svr, "TESTDB")  
      db.Create()  
  
      ' Creating Logins  
      Dim login As New Login(svr, "Login1")  
      login.LoginType = LoginType.SqlLogin  
      login.Create("password@1")  
  
      Dim login2 As New Login(svr, "Login2")  
      login2.LoginType = LoginType.SqlLogin  
      login2.Create("password@1")  
  
      ' Creating Users in the database for the logins created  
      Dim user1 As New User(db, "User1")  
      user1.Login = "Login1"  
      user1.Create()  
  
      Dim user2 As New User(db, "User2")  
      user2.Login = "Login2"  
      user2.Create()  
  
      ' Creating database permission Sets  
      Dim dbPermSet As New DatabasePermissionSet(DatabasePermission.AlterAnySchema)  
      dbPermSet.Add(DatabasePermission.AlterAnyUser)  
  
      Dim dbPermSet2 As New DatabasePermissionSet(DatabasePermission.CreateType)  
      dbPermSet2.Add(DatabasePermission.CreateSchema)  
      dbPermSet2.Add(DatabasePermission.CreateTable)  
  
      ' Creating Database roles  
      Dim role1 As New DatabaseRole(db, "Role1")  
      role1.Create()  
  
      Dim role2 As New DatabaseRole(db, "Role2")  
      role2.Create()  
  
      ' Granting Database Permission Sets to Roles  
      db.Grant(dbPermSet, role1.Name)  
      db.Grant(dbPermSet2, role2.Name)  
  
      ' Adding members (Users / Roles) to Role  
      role1.AddMember("User1")  
  
      role2.AddMember("User2")  
  
      ' Role1 becomes a member of Role2  
      role2.AddMember("Role1")  
  
      ' Enumerating through explicit permissions granted to Role1  
      ' enumerates all database permissions for the Grantee  
      Dim dbPermsRole1 As DatabasePermissionInfo() = db.EnumDatabasePermissions("Role1")  
      For Each dbp As DatabasePermissionInfo In dbPermsRole1  
         Console.WriteLine(dbp.Grantee + " has " & dbp.PermissionType.ToString() & " permission.")  
      Next  
      Console.WriteLine(" ")  
   End Sub  
End Class  
```  
