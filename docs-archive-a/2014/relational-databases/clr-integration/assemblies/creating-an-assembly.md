---
title: Erstellen einer Assembly | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- creating assemblies
- UNSAFE assemblies
- CREATE ASSEMBLY statement
- SAFE assemblies
- EXTERNAL_ACCESS assemblies
- assemblies [CLR integration], creating
ms.assetid: a2bc503d-b6b2-4963-8beb-c11c323f18e0
author: rothja
ms.author: jroth
ms.openlocfilehash: 9dea1f8fe57691f05274cac353a1064420309e06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720038"
---
# <a name="creating-an-assembly"></a><span data-ttu-id="6b805-102">Erstellen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="6b805-102">Creating an Assembly</span></span>
  <span data-ttu-id="6b805-103">Verwaltete Datenbankobjekte wie beispielsweise gespeicherte Prozeduren und Trigger werden kompiliert und dann in so genannten Assemblys bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="6b805-103">Managed database objects, such as stored procedures or triggers, are compiled and then deployed in units called an assembly.</span></span> <span data-ttu-id="6b805-104">Verwaltete DLL-Assemblys müssen in [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] registriert werden, damit die von der Assembly bereitgestellte Funktion verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="6b805-104">Managed DLL assemblies must be registered in [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] before the functionality the assembly provides can be used.</span></span> <span data-ttu-id="6b805-105">Assemblys werden über die CREATE ASSEMBLY-Anweisung in einer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Datenbank registriert.</span><span class="sxs-lookup"><span data-stu-id="6b805-105">To register an assembly in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database, use the CREATE ASSEMBLY statement.</span></span> <span data-ttu-id="6b805-106">In diesem Thema wird erläutert, wie Sie eine Assembly mithilfe der CREATE ASSEMBLY-Anweisung in einer Datenbank registrieren und wie Sie die Sicherheitseinstellungen für die Assembly festlegen.</span><span class="sxs-lookup"><span data-stu-id="6b805-106">This topic discusses how to register an assembly in a database using the CREATE ASSEMBLY statement, and how to specify the security settings for the assembly.</span></span>  
  
## <a name="the-create-assembly-statement"></a><span data-ttu-id="6b805-107">Die CREATE ASSEMBLY-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6b805-107">The CREATE ASSEMBLY Statement</span></span>  
 <span data-ttu-id="6b805-108">Die CREATE ASSEMBLY-Anweisung dient zum Erstellen einer Assembly in einer Datenbank.</span><span class="sxs-lookup"><span data-stu-id="6b805-108">The CREATE ASSEMBLY statement is used to create an assembly in a database.</span></span> <span data-ttu-id="6b805-109">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6b805-109">Here is an example:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll';  
```  
  
 <span data-ttu-id="6b805-110">Die FROM-Klausel legt den Pfadnamen der zu erstellenden Assembly fest.</span><span class="sxs-lookup"><span data-stu-id="6b805-110">The FROM clause specifies the pathname of the assembly to create.</span></span> <span data-ttu-id="6b805-111">Bei diesem Pfad kann es sich entweder um einen UNC-Pfad (Universal Naming Convention) oder einen physischen Dateipfad handeln, der sich lokal auf dem Rechner befindet.</span><span class="sxs-lookup"><span data-stu-id="6b805-111">This path can either be a Universal Naming Convention (UNC) path or a physical file path that is local to the machine.</span></span>  
  
 <span data-ttu-id="6b805-112">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ist es nicht zulässig, verschiedene Versionen einer Assembly mit demselben Namen, derselben Kultur und demselben öffentlichen Schlüssel zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="6b805-112">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not allow registering different versions of an assembly with the same name, culture and public key.</span></span>  
  
 <span data-ttu-id="6b805-113">Es ist möglich, Assemblys zu erstellen, die auf andere Assemblys verweisen.</span><span class="sxs-lookup"><span data-stu-id="6b805-113">It is possible to create assemblies that reference other assemblies.</span></span> <span data-ttu-id="6b805-114">Wenn eine Assembly in erstellt wird [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , erstellt auch die Assemblys, auf die von der Assembly auf Stamm Ebene verwiesen wird, wenn die referenzierten Assemblys nicht bereits in der Datenbank erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="6b805-114">When an assembly is created in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] also creates the assemblies referenced by the root-level assembly, if the referenced assemblies are not already created into the database.</span></span>  
  
 <span data-ttu-id="6b805-115">Datenbankbenutzer oder Benutzerrollen erhalten Berechtigungen zum Erstellen von Assemblys in einer Datenbank, deren Besitzer sie dann sind.</span><span class="sxs-lookup"><span data-stu-id="6b805-115">Database users or user roles are given permissions to create, and thereby own, assemblies in a database.</span></span> <span data-ttu-id="6b805-116">Um Assemblys zu erstellen, benötigt der Datenbankbenutzer oder die Rolle die CREATE ASSEMBLY-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="6b805-116">In order to create assemblies, the database user or role should have the CREATE ASSEMBLY permission.</span></span>  
  
 <span data-ttu-id="6b805-117">Eine Assembly kann nur unter folgenden Voraussetzungen erfolgreich auf andere Assemblys verweisen:</span><span class="sxs-lookup"><span data-stu-id="6b805-117">An assembly can only succeed in referencing other assemblies if:</span></span>  
  
-   <span data-ttu-id="6b805-118">Die Assembly, die aufgerufen wird oder auf die verwiesen wird, gehört dem gleichen Benutzer oder der Rolle.</span><span class="sxs-lookup"><span data-stu-id="6b805-118">The assembly that is called or referenced is owned by the same user or role.</span></span>  
  
-   <span data-ttu-id="6b805-119">Die Assembly, die aufgerufen wird oder auf die verwiesen wird, wurde in derselben Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="6b805-119">The assembly that is called or referenced was created in the same database.</span></span>  
  
## <a name="specifying-security-when-creating-assemblies"></a><span data-ttu-id="6b805-120">Festlegen der Sicherheit beim Erstellen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="6b805-120">Specifying Security When Creating Assemblies</span></span>  
 <span data-ttu-id="6b805-121">Wenn Sie eine Assembly in einer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Datenbank erstellen, können Sie eine von drei verschiedenen Sicherheitsstufen festlegen, mit der der Code ausgeführt werden soll: `SAFE`, `EXTERNAL_ACCESS` oder `UNSAFE`.</span><span class="sxs-lookup"><span data-stu-id="6b805-121">When creating an assembly into a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database, you can specify one of three different levels of security in which your code can run: `SAFE`, `EXTERNAL_ACCESS`, or `UNSAFE`.</span></span> <span data-ttu-id="6b805-122">Beim Ausführen der `CREATE ASSEMBLY`-Anweisung werden bestimmte Überprüfungen für die Code-Assembly durchgeführt, aufgrund derer die Assembly möglicherweise nicht beim Server registriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="6b805-122">When the `CREATE ASSEMBLY` statement is run, certain checks are performed on the code assembly which may cause the assembly to fail to register on the server.</span></span> <span data-ttu-id="6b805-123">Weitere Informationen finden Sie unter dem Beispiel für den Identitätswechsel auf [CodePlex](https://msftengprodsamples.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="6b805-123">For more information, see the Impersonation sample on [CodePlex](https://msftengprodsamples.codeplex.com/).</span></span>  
  
 <span data-ttu-id="6b805-124">`SAFE` ist der Standardberechtigungssatz und funktioniert für die meisten Szenarien.</span><span class="sxs-lookup"><span data-stu-id="6b805-124">`SAFE` is the default permission set and works for the majority of scenarios.</span></span> <span data-ttu-id="6b805-125">Um eine bestimmte Sicherheitsstufe anzugeben, ändern Sie die Syntax der CREATE ASSEMBLY-Anweisung wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6b805-125">To specify a given security level, you modify the syntax of the CREATE ASSEMBLY statement as follows:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll'  
WITH PERMISSION_SET = SAFE;  
```  
  
 <span data-ttu-id="6b805-126">Sie können eine Assembly mit eingestellter `SAFE`-Berechtigung auch erstellen, indem Sie einfach die dritte Zeile des oben angegeben Codes auslassen:</span><span class="sxs-lookup"><span data-stu-id="6b805-126">It is also possible to create an assembly with the `SAFE` permission set by simply omitting the third line of code above:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll';  
```  
  
 <span data-ttu-id="6b805-127">Wird der Code in einer Assembly mit eingestellter `SAFE`-Berechtigung ausgeführt, können Berechnungen und Datenzugriffe im Server ausschließlich über den prozessinternen verwalteten Anbieter erfolgen.</span><span class="sxs-lookup"><span data-stu-id="6b805-127">When code in an assembly runs under the `SAFE` permission set, it can only do computation and data access within the server through the in-process managed provider.</span></span>  
  
### <a name="creating-external_access-and-unsafe-assemblies"></a><span data-ttu-id="6b805-128">Erstellen von EXTERNAL_ACCESS- und UNSAFE-Assemblys</span><span class="sxs-lookup"><span data-stu-id="6b805-128">Creating EXTERNAL_ACCESS and UNSAFE Assemblies</span></span>  
 <span data-ttu-id="6b805-129">`EXTERNAL_ACCESS` wird für Szenarien verwendet, in denen der Code auf Ressourcen außerhalb des Servers zugreift, z. B. Datei-, Netzwerk-, Registrierungs- und Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="6b805-129">`EXTERNAL_ACCESS` addresses scenarios in which the code needs to access resources outside the server, such as files, network, registry, and environment variables.</span></span> <span data-ttu-id="6b805-130">Immer wenn der Server auf eine externe Ressource zugreift, verwendet er den Sicherheitskontext des Benutzers, der den verwalteten Code aufruft.</span><span class="sxs-lookup"><span data-stu-id="6b805-130">Whenever the server accesses an external resource, it impersonates the security context of the user calling the managed code.</span></span>  
  
 <span data-ttu-id="6b805-131">Die Codeberechtigung `UNSAFE` wird für Situationen verwendet, in denen eine Assembly nicht eindeutig als sicher eingestuft werden kann oder zusätzlichen Zugriff auf beschränkte Ressourcen benötigt, z. B. die [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Win32-API.</span><span class="sxs-lookup"><span data-stu-id="6b805-131">`UNSAFE` code permission is for those situations in which an assembly is not verifiably safe or requires additional access to restricted resources, such as the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Win32 API.</span></span>  
  
 <span data-ttu-id="6b805-132">Zum Erstellen einer `EXTERNAL_ACCESS`- oder `UNSAFE`-Assembly in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] muss eine der folgenden Bedingungen zutreffen:</span><span class="sxs-lookup"><span data-stu-id="6b805-132">To create an `EXTERNAL_ACCESS` or `UNSAFE` assembly in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], one of the following two conditions must be met:</span></span>  
  
1.  <span data-ttu-id="6b805-133">Die Assembly wurde mit einem starken Namen oder Authenticode mit Zertifikat signiert.</span><span class="sxs-lookup"><span data-stu-id="6b805-133">The assembly is strong name signed or Authenticode signed with a certificate.</span></span> <span data-ttu-id="6b805-134">Der starke Name (oder das Zertifikat) wird in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] als asymmetrischer Schlüssel (oder Zertifikat) erstellt und verfügt über eine zugehörige Anmeldung mit `EXTERNAL ACCESS ASSEMBLY`-Berechtigung (für Assemblys mit externem Zugriff) oder `UNSAFE ASSEMBLY`-Berechtigung (für unsichere Assemblys).</span><span class="sxs-lookup"><span data-stu-id="6b805-134">This strong name (or certificate) is created inside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as an asymmetric key (or certificate), and has a corresponding login with `EXTERNAL ACCESS ASSEMBLY` permission (for external access assemblies) or `UNSAFE ASSEMBLY` permission (for unsafe assemblies).</span></span>  
  
2.  <span data-ttu-id="6b805-135">Der Datenbankbesitzer (dbo) verfügt über `EXTERNAL ACCESS ASSEMBLY` die Berechtigung (für Assemblys `EXTERNAL ACCESS` ) oder (für Assemblys `UNSAFE ASSEMBLY` `UNSAFE` ), und für die Datenbank ist die [Eigenschaft vertrauenswürdige Datenbank](../../security/trustworthy-database-property.md) auf festgelegt `ON` .</span><span class="sxs-lookup"><span data-stu-id="6b805-135">The database owner (DBO) has `EXTERNAL ACCESS ASSEMBLY` (for `EXTERNAL ACCESS` assemblies) or `UNSAFE ASSEMBLY` (for `UNSAFE` assemblies) permission, and the database has the [TRUSTWORTHY Database Property](../../security/trustworthy-database-property.md) set to `ON`.</span></span>  
  
 <span data-ttu-id="6b805-136">Die beiden oben aufgeführten Bedingungen werden auch zur Assemblyladezeit (dazu gehört auch die Ausführung) überprüft.</span><span class="sxs-lookup"><span data-stu-id="6b805-136">The two conditions listed above are also checked at assembly load time (which includes execution).</span></span> <span data-ttu-id="6b805-137">Mindestens eine der Bedingungen muss erfüllt sein, um die Assembly zu laden.</span><span class="sxs-lookup"><span data-stu-id="6b805-137">At least one of the conditions must be met in order to load the assembly.</span></span>  
  
 <span data-ttu-id="6b805-138">Es wird empfohlen, dass die [Eigenschaft vertrauenswürdige Datenbank](../../security/trustworthy-database-property.md) für eine Datenbank nicht auf festgelegt ist, um `ON` Common Language Runtime (CLR)-Code im Server Prozess auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6b805-138">We recommend that the [TRUSTWORTHY Database Property](../../security/trustworthy-database-property.md) on a database not be set to `ON` only to run common language runtime (CLR) code in the server process.</span></span> <span data-ttu-id="6b805-139">Stattdessen empfiehlt es sich, dass ein asymmetrischer Schlüssel aus der Assemblydatei in der Masterdatenbank erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="6b805-139">Instead, we recommend that an asymmetric key be created from the assembly file in the master database.</span></span> <span data-ttu-id="6b805-140">Anschließend muss eine Anmeldung für diesen asymmetrischen Schlüssel erstellt werden, und die Anmeldung muss eine `EXTERNAL ACCESS ASSEMBLY`- oder `UNSAFE ASSEMBLY`-Berechtigung erhalten.</span><span class="sxs-lookup"><span data-stu-id="6b805-140">A login mapped to this asymmetric key must then be created, and the login must be granted `EXTERNAL ACCESS ASSEMBLY` or `UNSAFE ASSEMBLY` permission.</span></span>  
  
 <span data-ttu-id="6b805-141">Die folgenden [!INCLUDE[tsql](../../../includes/tsql-md.md)] Anweisungen vor dem Ausführen der Create Assembly-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="6b805-141">The following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements before running the CREATE ASSEMBLY statement.</span></span>  
  
```  
USE master;   
GO    
  
CREATE ASYMMETRIC KEY SQLCLRTestKey FROM EXECUTABLE FILE = 'C:\MyDBApp\SQLCLRTest.dll'     
CREATE LOGIN SQLCLRTestLogin FROM ASYMMETRIC KEY SQLCLRTestKey     
GRANT EXTERNAL ACCESS ASSEMBLY TO SQLCLRTestLogin;   
GO   
```  
  
> [!NOTE]  
>  <span data-ttu-id="6b805-142">Sie müssen eine neue Anmeldung erstellen, die dem asymmetrischen Schlüssel zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="6b805-142">You must create a new login to associate with the asymmetric key.</span></span> <span data-ttu-id="6b805-143">Diese Anmeldung dient nur zum Erteilen von Berechtigungen. Sie muss weder einem Benutzer zugeordnet noch innerhalb der Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6b805-143">This login is only used to grant permissions; it does not have to be associated with a user, or used within the application.</span></span>  
  
 <span data-ttu-id="6b805-144">Um eine `EXTERNAL ACCESS`-Assembly zu erstellen, muss der Ersteller die `EXTERNAL ACCESS`-Berechtigung haben.</span><span class="sxs-lookup"><span data-stu-id="6b805-144">To create an `EXTERNAL ACCESS` assembly, the creator needs to have `EXTERNAL ACCESS` permission.</span></span> <span data-ttu-id="6b805-145">Diese wird beim Erstellen der Assembly angegeben:</span><span class="sxs-lookup"><span data-stu-id="6b805-145">This is specified when creating the assembly:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll'  
WITH PERMISSION_SET = EXTERNAL_ACCESS;  
```  
  
 <span data-ttu-id="6b805-146">Die folgenden [!INCLUDE[tsql](../../../includes/tsql-md.md)] Anweisungen vor dem Ausführen der Create Assembly-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="6b805-146">The following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements before running the CREATE ASSEMBLY statement.</span></span>  
  
```  
USE master;   
GO    
  
CREATE ASYMMETRIC KEY SQLCLRTestKey FROM EXECUTABLE FILE = 'C:\MyDBApp\SQLCLRTest.dll';     
CREATE LOGIN SQLCLRTestLogin FROM ASYMMETRIC KEY SQLCLRTestKey ;    
GRANT UNSAFE ASSEMBLY TO SQLCLRTestLogin ;  
GO  
```  
  
 <span data-ttu-id="6b805-147">Um festzulegen, dass eine Assembly mit `UNSAFE`-Berechtigung geladen wird, geben Sie die `UNSAFE`-Berechtigung beim Laden der Assembly auf den Server an:</span><span class="sxs-lookup"><span data-stu-id="6b805-147">To specify that an assembly loads with `UNSAFE` permission, you specify the `UNSAFE` permission set when loading the assembly into the server:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll'  
WITH PERMISSION_SET = UNSAFE;  
```  
  
 <span data-ttu-id="6b805-148">Weitere Informationen zu den Berechtigungen für die verschiedenen Einstellungen finden Sie unter [CLR Integration Security](../security/clr-integration-security.md).</span><span class="sxs-lookup"><span data-stu-id="6b805-148">For more details about the permissions for each of the settings, see [CLR Integration Security](../security/clr-integration-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b805-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6b805-149">See Also</span></span>  
 <span data-ttu-id="6b805-150">[Verwalten von CLR Integration](managing-clr-integration-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="6b805-150">[Managing CLR Integration Assemblies](managing-clr-integration-assemblies.md) </span></span>  
 <span data-ttu-id="6b805-151">[Ändern einer Assembly](altering-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="6b805-151">[Altering an Assembly](altering-an-assembly.md) </span></span>  
 <span data-ttu-id="6b805-152">[Löschen einer Assembly](dropping-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="6b805-152">[Dropping an Assembly](dropping-an-assembly.md) </span></span>  
 <span data-ttu-id="6b805-153">[Code Zugriffssicherheit für die CLR-Integration](../security/clr-integration-code-access-security.md) </span><span class="sxs-lookup"><span data-stu-id="6b805-153">[CLR Integration Code Access Security](../security/clr-integration-code-access-security.md) </span></span>  
 <span data-ttu-id="6b805-154">[TRUSTWORTHY-Datenbankeigenschaft](../../security/trustworthy-database-property.md) </span><span class="sxs-lookup"><span data-stu-id="6b805-154">[TRUSTWORTHY Database Property](../../security/trustworthy-database-property.md) </span></span>  
 [<span data-ttu-id="6b805-155">Zulassen von teilweise vertrauenswürdigen Aufrufern</span><span class="sxs-lookup"><span data-stu-id="6b805-155">Allowing Partially Trusted Callers</span></span>](../../../database-engine/dev-guide/allowing-partially-trusted-callers.md)  
  
