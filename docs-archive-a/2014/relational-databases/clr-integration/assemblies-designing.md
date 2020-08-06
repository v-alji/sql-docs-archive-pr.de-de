---
title: Entwerfen von Assemblys Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- designing assemblies [SQL Server]
- assemblies [CLR integration], designing
ms.assetid: 9c07f706-6508-41aa-a4d7-56ce354f9061
author: rothja
ms.author: jroth
ms.openlocfilehash: 785ab80a529140a52ec18ef96ccaaeafd03698cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720074"
---
# <a name="designing-assemblies"></a><span data-ttu-id="cda63-102">Entwerfen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="cda63-102">Designing Assemblies</span></span>
  <span data-ttu-id="cda63-103">In diesem Thema werden die folgenden Faktoren beschrieben, die Sie beim Entwerfen von Assemblys berücksichtigen sollten:</span><span class="sxs-lookup"><span data-stu-id="cda63-103">This topic describes the following factors you should consider when you design assemblies:</span></span>  
  
-   <span data-ttu-id="cda63-104">Assemblys Verpacken</span><span class="sxs-lookup"><span data-stu-id="cda63-104">Packaging assemblies</span></span>  
  
-   <span data-ttu-id="cda63-105">Verwalten der Assembly-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="cda63-105">Managing assembly security</span></span>  
  
-   <span data-ttu-id="cda63-106">Einschränkungen für Assemblys</span><span class="sxs-lookup"><span data-stu-id="cda63-106">Restrictions on assemblies</span></span>  
  
## <a name="packaging-assemblies"></a><span data-ttu-id="cda63-107">Verpacken von Assemblys</span><span class="sxs-lookup"><span data-stu-id="cda63-107">Packaging Assemblies</span></span>  
 <span data-ttu-id="cda63-108">Eine Assembly kann Funktionen für mehrere [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Routinen oder -Typen in ihren Klassen und Methoden enthalten.</span><span class="sxs-lookup"><span data-stu-id="cda63-108">An assembly can contain functionality for more than one [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] routine or type in its classes and methods.</span></span> <span data-ttu-id="cda63-109">In den meisten Fällen ist es sinnvoll, die Funktionen von Routinen, die verwandte Funktionen ausführen, in der gleichen Assembly zu verpacken, insbesondere, wenn diese Routinen Klassen gemeinsam verwenden, deren Methoden sich gegenseitig aufrufen.</span><span class="sxs-lookup"><span data-stu-id="cda63-109">Most of the time, it makes sense to package the functionality of routines that perform related functions within the same assembly, especially if these routines share classes whose methods call one another.</span></span> <span data-ttu-id="cda63-110">Klassen, die Dateneingabe-Verwaltungstasks für CLR-Trigger (Common Language Runtime) und CLR-gespeicherte Prozeduren ausführen, können z. B. in der gleichen Assembly verpackt werden.</span><span class="sxs-lookup"><span data-stu-id="cda63-110">For example, classes that perform data entry management tasks for common language runtime (CLR) triggers and CLR stored procedures can be packaged in the same assembly.</span></span> <span data-ttu-id="cda63-111">Dies hängt damit zusammen, dass sich die Methoden für diese Klassen mit größerer Wahrscheinlichkeit gegenseitig aufrufen als die Methoden anderer, weniger verwandter Tasks.</span><span class="sxs-lookup"><span data-stu-id="cda63-111">This is because the methods for these classes are more likely to call each other than those of less related tasks.</span></span>  
  
 <span data-ttu-id="cda63-112">Sie sollten Folgendes beachten, wenn Sie Code in einer Assembly verpacken:</span><span class="sxs-lookup"><span data-stu-id="cda63-112">When you are packaging code into assembly, you should consider the following:</span></span>  
  
-   <span data-ttu-id="cda63-113">CLR-benutzerdefinierte Typen und Indizes, die von CLR-benutzerdefinierten Funktionen abhängen, können bewirken, dass sich persistente Daten in der Datenbank befinden, die von der Assembly abhängen.</span><span class="sxs-lookup"><span data-stu-id="cda63-113">CLR user-defined types and indexes that depend on CLR user-defined functions can cause persisted data to be in the database that depends on the assembly.</span></span> <span data-ttu-id="cda63-114">Das Bearbeiten des Codes einer Assembly ist in der Regel komplexer, wenn persistente Daten vorhanden sind, die von der Assembly in der Datenbank abhängen.</span><span class="sxs-lookup"><span data-stu-id="cda63-114">Modifying the code of an assembly is frequently more complex when there is persisted data that depends on the assembly in the database.</span></span> <span data-ttu-id="cda63-115">Auf diesem Grund ist es im Allgemeinen besser, Code, von dem die Abhängigkeiten persistenter Daten abhängen (z. B. benutzerdefinierte Typen und Indizes, die benutzerdefinierte Funktionen verwenden), von Code zu trennen, der keine solchen Abhängigkeiten persistenter Daten aufweist.</span><span class="sxs-lookup"><span data-stu-id="cda63-115">Therefore, it is generally better to separate code on which persisted data dependencies rely (such as user-defined types and indexes using user-defined functions) from code that does not have such persisted data dependencies.</span></span> <span data-ttu-id="cda63-116">Weitere Informationen finden Sie unter [implementieren](assemblies-implementing.md) von Assemblys und [Alter Assembly &#40;Transact-SQL-&#41;](/sql/t-sql/statements/alter-assembly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cda63-116">For more information, see [Implementing Assemblies](assemblies-implementing.md) and [ALTER ASSEMBLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-assembly-transact-sql).</span></span>  
  
-   <span data-ttu-id="cda63-117">Wenn verwalteter Code höhere Berechtigungen verlangt, ist es besser, diesen Code in einer anderen Assembly als den Code zu speichern, für den die höheren Berechtigungen nicht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="cda63-117">If a piece of managed code requires higher permission, it is better to separate that code into a separate assembly from code that does not require higher permission.</span></span>  
  
## <a name="managing-assembly-security"></a><span data-ttu-id="cda63-118">Verwalten der Assemblysicherheit</span><span class="sxs-lookup"><span data-stu-id="cda63-118">Managing Assembly Security</span></span>  
 <span data-ttu-id="cda63-119">Sie können steuern, im welchem Umfang eine Assembly auf Ressourcen zugreifen kann, die durch .NET Code Access Security geschützt ist, wenn diese verwalteten Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="cda63-119">You can control how much an assembly can access resources protected by .NET Code Access Security when it runs managed code.</span></span> <span data-ttu-id="cda63-120">Sie geben zu diesem Zweck einen von drei Berechtigungssätzen an, wenn Sie eine Assembly erstellen oder ändern: SAFE, EXTERNAL_ACCESS oder UNSAFE.</span><span class="sxs-lookup"><span data-stu-id="cda63-120">You do this by specifying one of three permission sets when you create or modify an assembly: SAFE, EXTERNAL_ACCESS, or UNSAFE.</span></span>  
  
### <a name="safe"></a><span data-ttu-id="cda63-121">SAFE</span><span class="sxs-lookup"><span data-stu-id="cda63-121">SAFE</span></span>  
 <span data-ttu-id="cda63-122">SAFE ist der Standardberechtigungssatz und die restriktivste Einstellung.</span><span class="sxs-lookup"><span data-stu-id="cda63-122">SAFE is the default permission set and it is the most restrictive.</span></span> <span data-ttu-id="cda63-123">Code, der von einer Assembly mit SAFE-Berechtigungen ausgeführt wird, kann nicht auf externe Systemressourcen wie z. B. Dateien, das Netzwerk, Umgebungsvariablen oder die Registrierung zugreifen.</span><span class="sxs-lookup"><span data-stu-id="cda63-123">Code run by an assembly with SAFE permissions cannot access external system resources such as files, the network, environment variables, or the registry.</span></span> <span data-ttu-id="cda63-124">SAFE-Code kann auf Daten aus den lokalen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Datenbanken zugreifen oder Berechnungen und Geschäftslogik ausführen, für die kein Zugriff auf Ressourcen außerhalb der lokalen Datenbanken erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="cda63-124">SAFE code can access data from the local [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases or perform computations and business logic that do not involve accessing resources outside the local databases.</span></span>  
  
 <span data-ttu-id="cda63-125">Die meisten Assemblys führen Berechnungs- und Datenverwaltungsaufgaben aus, ohne dass ein Zugriff auf Ressourcen außerhalb von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="cda63-125">Most assemblies perform computation and data management tasks without having to access resources outside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cda63-126">Aus diesem Grund wird empfohlen, SAFE als Berechtigungssatz für die Assembly zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="cda63-126">Therefore, we recommend SAFE as the assembly permission set.</span></span>  
  
### <a name="external_access"></a><span data-ttu-id="cda63-127">EXTERNAL_ACCESS</span><span class="sxs-lookup"><span data-stu-id="cda63-127">EXTERNAL_ACCESS</span></span>  
 <span data-ttu-id="cda63-128">EXTERNAL_ACCESS ermöglicht Assemblys den Zugriff auf bestimmte externe Systemressourcen wie z. B. Dateien, Netzwerke, Webdienste, Umgebungsvariablen und die Registrierung.</span><span class="sxs-lookup"><span data-stu-id="cda63-128">EXTERNAL_ACCESS allows for assemblies to access certain external system resources such as files, networks, Web services, environmental variables, and the registry.</span></span> <span data-ttu-id="cda63-129">Nur [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Anmeldenamen mit EXTERNAL ACCESS-Berechtigungen können EXTERNAL_ACCESS-Assemblys erstellen.</span><span class="sxs-lookup"><span data-stu-id="cda63-129">Only [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins with EXTERNAL ACCESS permissions can create EXTERNAL_ACCESS assemblies.</span></span>  
  
 <span data-ttu-id="cda63-130">SAFE- und EXTERNAL_ACCESS-Assemblys können nur Code enthalten, der überprüfbar typsicher ist.</span><span class="sxs-lookup"><span data-stu-id="cda63-130">SAFE and EXTERNAL_ACCESS assemblies can contain only code that is verifiably type-safe.</span></span> <span data-ttu-id="cda63-131">Dies bedeutet, dass diese Assemblys auf Klassen nur über definierte Einstiegspunkte zugreifen können, die für die Typdefinition gültig sind.</span><span class="sxs-lookup"><span data-stu-id="cda63-131">This means that these assemblies can only access classes through well-defined entry points that are valid for the type definition.</span></span> <span data-ttu-id="cda63-132">Daher können sie nicht beliebig auf Speicherpuffer zugreifen, die sich nicht im Besitz des Codes befinden.</span><span class="sxs-lookup"><span data-stu-id="cda63-132">Therefore, they cannot arbitrarily access memory buffers not owned by the code.</span></span> <span data-ttu-id="cda63-133">Außerdem können sie keine Vorgänge durchführen, die nachteilige Auswirkungen auf die Robustheit des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Prozess besitzen könnten.</span><span class="sxs-lookup"><span data-stu-id="cda63-133">Additionally, they cannot perform operations that might have an adverse effect on the robustness of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] process.</span></span>  
  
### <a name="unsafe"></a><span data-ttu-id="cda63-134">UNSAFE</span><span class="sxs-lookup"><span data-stu-id="cda63-134">UNSAFE</span></span>  
 <span data-ttu-id="cda63-135">UNSAFE ermöglicht Assemblys den uneingeschränkten Zugriff auf Ressourcen innerhalb und außerhalb von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cda63-135">UNSAFE gives assemblies unrestricted access to resources, both within and outside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cda63-136">Code, der aus einer UNSAFE-Assembly ausgeführt wird, kann nicht verwalteten Code aufrufen.</span><span class="sxs-lookup"><span data-stu-id="cda63-136">Code that is running from within an UNSAFE assembly can call unmanaged code.</span></span>  
  
 <span data-ttu-id="cda63-137">Wenn Sie UNSAFE angeben, kann der Code in der Assembly außerdem Vorgänge ausführen, die von der CLR-Überprüfung als typunsicher betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="cda63-137">Also, specifying UNSAFE allows for the code in the assembly to perform operations that are considered type-unsafe by the CLR verifier.</span></span> <span data-ttu-id="cda63-138">Diese Vorgänge können potenziell auf unkontrollierte Weise auf Speicherpuffer im [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Prozessraum zugreifen.</span><span class="sxs-lookup"><span data-stu-id="cda63-138">These operations can potentially access memory buffers in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] process space in an uncontrolled manner.</span></span> <span data-ttu-id="cda63-139">UNSAFE-Assemblys können außerdem potenziell das Sicherheitssystem von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] oder der CLR unterlaufen.</span><span class="sxs-lookup"><span data-stu-id="cda63-139">UNSAFE assemblies can also potentially subvert the security system of either [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or the common language runtime.</span></span> <span data-ttu-id="cda63-140">UNSAFE-Berechtigungen sollten nur hochgradig vertrauenswürdigen Assemblys durch erfahrene Entwickler oder Administratoren erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="cda63-140">UNSAFE permissions should be granted only to highly trusted assemblies by experienced developers or administrators.</span></span> <span data-ttu-id="cda63-141">Nur Mitglieder der festen Server Rolle **sysadmin** können unsichere Assemblys erstellen.</span><span class="sxs-lookup"><span data-stu-id="cda63-141">Only members of the **sysadmin** fixed server role can create UNSAFE assemblies.</span></span>  
  
## <a name="restrictions-on-assemblies"></a><span data-ttu-id="cda63-142">Einschränkungen für Assemblys</span><span class="sxs-lookup"><span data-stu-id="cda63-142">Restrictions on Assemblies</span></span>  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="cda63-143">belegt verwalteten Code in Assemblys mit einigen Einschränkungen, damit sichergestellt wird, dass diese auf zuverlässige und skalierbare Weise ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="cda63-143">puts certain restrictions on managed code in assemblies to make sure that they can run in a reliable and scalable manner.</span></span> <span data-ttu-id="cda63-144">Dies bedeutet, dass bestimmte Vorgänge, die die Robustheit des Servers beeinträchtigen könnten, in SAFE- und EXTERNAL_ACCESS-Assemblys nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="cda63-144">This means that certain operations that can compromise the robustness of the server are not permitted in SAFE and EXTERNAL_ACCESS assemblies.</span></span>  
  
### <a name="disallowed-custom-attributes"></a><span data-ttu-id="cda63-145">Unzulässige benutzerdefinierte Attribute</span><span class="sxs-lookup"><span data-stu-id="cda63-145">Disallowed Custom Attributes</span></span>  
 <span data-ttu-id="cda63-146">Assemblys dürfen nicht mit den folgenden benutzerdefinierten Attributen mit Anmerkungen versehen werden:</span><span class="sxs-lookup"><span data-stu-id="cda63-146">Assemblies cannot be annotated with the following custom attributes:</span></span>  
  
```  
System.ContextStaticAttribute  
System.MTAThreadAttribute  
System.Runtime.CompilerServices.MethodImplAttribute  
System.Runtime.CompilerServices.CompilationRelaxationsAttribute  
System.Runtime.Remoting.Contexts.ContextAttribute  
System.Runtime.Remoting.Contexts.SynchronizationAttribute  
System.Runtime.InteropServices.DllImportAttribute   
System.Security.Permissions.CodeAccessSecurityAttribute  
System.STAThreadAttribute  
System.ThreadStaticAttribute  
```  
  
 <span data-ttu-id="cda63-147">Außerdem dürfen SAFE- und EXTERNAL_ACCESS-Assemblys nicht mit den folgenden benutzerdefinierten Attributen mit Anmerkungen versehen werden:</span><span class="sxs-lookup"><span data-stu-id="cda63-147">Additionally, SAFE and EXTERNAL_ACCESS assemblies cannot be annotated with the following custom attributes:</span></span>  
  
```  
System.Security.SuppressUnmanagedCodeSecurityAttribute  
System.Security.UnverifiableCodeAttribute  
```  
  
### <a name="disallowed-net-framework-apis"></a><span data-ttu-id="cda63-148">Unzulässige .NET Framework-APIs</span><span class="sxs-lookup"><span data-stu-id="cda63-148">Disallowed .NET Framework APIs</span></span>  
 <span data-ttu-id="cda63-149">Jede [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] API, die mit einem der unzulässigen **Hostschutzattribute** kommentiert wird, kann nicht von sicheren und EXTERNAL_ACCESS Assemblys aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="cda63-149">Any [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] API that is annotated with one of the disallowed **HostProtectionAttributes** cannot be called from SAFE and EXTERNAL_ACCESS assemblies.</span></span>  
  
```  
eSelfAffectingProcessMgmt  
eSelfAffectingThreading  
eSynchronization  
eSharedState   
eExternalProcessMgmt  
eExternalThreading  
eSecurityInfrastructure  
eMayLeakOnAbort  
eUI  
```  
  
### <a name="supported-net-framework-assemblies"></a><span data-ttu-id="cda63-150">Unterstützte .NET Framework-Assemblys</span><span class="sxs-lookup"><span data-stu-id="cda63-150">Supported .NET Framework Assemblies</span></span>  
 <span data-ttu-id="cda63-151">Jede Assembly, auf die durch die benutzerdefinierte Assembly verwiesen wird, muss mithilfe von CREATE ASSEMBLY in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] geladen werden.</span><span class="sxs-lookup"><span data-stu-id="cda63-151">Any assembly that is referenced by your custom assembly must be loaded into [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using CREATE ASSEMBLY.</span></span> <span data-ttu-id="cda63-152">Die folgenden [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]-Assemblys wurden bereits in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] geladen; daher kann durch benutzerdefinierte Assemblys auf sie verwiesen werden, ohne dass CREATE ASSEMBLY verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="cda63-152">The following [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] assemblies are already loaded into [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and, therefore, can be referenced by custom assemblies without having to use CREATE ASSEMBLY.</span></span>  
  
```  
custommarshallers.dll  
Microsoft.visualbasic.dll  
Microsoft.visualc.dll  
mscorlib.dll  
system.data.dll  
System.Data.SqlXml.dll  
system.dll  
system.security.dll  
system.web.services.dll  
system.xml.dll  
System.Transactions  
System.Data.OracleClient  
System.Configuration  
```  
  
## <a name="see-also"></a><span data-ttu-id="cda63-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cda63-153">See Also</span></span>  
 <span data-ttu-id="cda63-154">[Assemblys &#40;Datenbank-Engine&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="cda63-154">[Assemblies &#40;Database Engine&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span></span>  
 [<span data-ttu-id="cda63-155">Sicherheit der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="cda63-155">CLR Integration Security</span></span>](security/clr-integration-security.md)  
  
  
