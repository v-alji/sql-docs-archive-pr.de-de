---
title: Einschränkungen für das CLR-Integrations Programmiermodell | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- common language runtime [SQL Server], programming model restrictions
- assemblies [CLR integration], CREATE ASSEMBLY checks
- programming model restrictions [CLR integration]
- assemblies [CLR integration], runtime checks
ms.assetid: 2446afc2-9d21-42d3-9847-7733d3074de9
author: rothja
ms.author: jroth
ms.openlocfilehash: 01a32e1460ad9c49061b39b1bdc419c7cd2f1342
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607835"
---
# <a name="clr-integration-programming-model-restrictions"></a><span data-ttu-id="493ae-102">Beschränkungen des Programmiermodells für die CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="493ae-102">CLR Integration Programming Model Restrictions</span></span>
  <span data-ttu-id="493ae-103">Wenn Sie eine verwaltete gespeicherte Prozedur oder ein anderes verwaltetes Datenbankobjekt entwickeln, werden von bestimmte Code Überprüfungen durchgeführt, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Wenn die Assembly mithilfe der-Anweisung zum ersten Mal in der Datenbank registriert wird, `CREATE ASSEMBLY` und auch zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="493ae-103">When you are building a managed stored procedure or other managed database object, there are certain code checks performed by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] performs checks on the managed code assembly when it is first registered in the database, using the `CREATE ASSEMBLY` statement, and also at runtime.</span></span> <span data-ttu-id="493ae-104">Der verwaltete Code wird außerdem zur Laufzeit überprüft, da in einer Assembly Codepfade vorhanden sein können, die zur Laufzeit eigentlich nicht erreicht werden.</span><span class="sxs-lookup"><span data-stu-id="493ae-104">The managed code is also checked at runtime because in an assembly there may be code paths that may never actually be reached at runtime.</span></span>  <span data-ttu-id="493ae-105">Dadurch wird Flexibilität für die Registrierung von Assemblys von Drittanbietern geschaffen, sodass eine Assembly nicht blockiert wird, wenn ein "Unsafe"-Code vorliegt, der in einer Clientumgebung ausgeführt werden soll, jedoch nie in der gehosteten CLR ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="493ae-105">This provides flexibility for registering third party assemblies, especially, so that an assembly wouldn't be blocked where there is 'unsafe' code designed to run in a client environment but would never be executed in the hosted CLR.</span></span> <span data-ttu-id="493ae-106">Welche Anforderungen der verwaltete Code erfüllen muss, hängt davon ab, ob die Assembly als, oder registriert ist, und ist im `SAFE` `EXTERNAL_ACCESS` `UNSAFE` `SAFE` folgenden aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="493ae-106">The requirements that the managed code must meet depend on whether the assembly is registered as `SAFE`, `EXTERNAL_ACCESS`, or `UNSAFE`, `SAFE` being the strictest, and are listed below.</span></span>  
  
 <span data-ttu-id="493ae-107">Neben den Einschränkungen, die für verwaltete Codeassemblys gelten, werden außerdem Sicherheitsberechtigungen für Code erteilt.</span><span class="sxs-lookup"><span data-stu-id="493ae-107">In addition to restrictions being placed on the managed code assemblies, there are also code security permissions that are granted.</span></span> <span data-ttu-id="493ae-108">Die CLR (Common Language Runtime) unterstützt ein Sicherheitsmodell, das als Codezugriffssicherheit für verwalteten Code bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="493ae-108">The common language runtime (CLR) supports a security model called code access security (CAS) for managed code.</span></span> <span data-ttu-id="493ae-109">In diesem Modell werden Assemblys Berechtigungen auf Grundlage der Identität des Codes gewährt.</span><span class="sxs-lookup"><span data-stu-id="493ae-109">In this model, permissions are granted to assemblies based on the identity of the code.</span></span> <span data-ttu-id="493ae-110">`SAFE`-, `EXTERNAL_ACCESS`- und `UNSAFE`-Assemblys verfügen über andere CAS-Berechtigungen (Code Access Security).</span><span class="sxs-lookup"><span data-stu-id="493ae-110">`SAFE`, `EXTERNAL_ACCESS`, and `UNSAFE` assemblies have different CAS permissions.</span></span> <span data-ttu-id="493ae-111">Weitere Informationen finden Sie unter [CLR-Integration Code Zugriffssicherheit](../security/clr-integration-code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="493ae-111">For more information, see [CLR Integration Code Access Security](../security/clr-integration-code-access-security.md).</span></span>  
  
## <a name="create-assembly-checks"></a><span data-ttu-id="493ae-112">CREATE ASSEMBLY-Überprüfungen</span><span class="sxs-lookup"><span data-stu-id="493ae-112">CREATE ASSEMBLY Checks</span></span>  
 <span data-ttu-id="493ae-113">Wenn die `CREATE ASSEMBLY`-Anweisung ausgeführt wird, werden die folgenden Überprüfungen für jede Sicherheitsebene vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="493ae-113">When the `CREATE ASSEMBLY` statement is run, the following checks are performed for each security level.</span></span>  <span data-ttu-id="493ae-114">Schlägt eine Überprüfung fehl, wird `CREATE ASSEMBLY` mit einer Fehlermeldung abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="493ae-114">If any check fails, `CREATE ASSEMBLY` will fail with an error message.</span></span>  
  
### <a name="global-any-security-level"></a><span data-ttu-id="493ae-115">Global (eine beliebige Sicherheitsebene)</span><span class="sxs-lookup"><span data-stu-id="493ae-115">Global (any security level)</span></span>  
 <span data-ttu-id="493ae-116">Alle Assemblys, auf die verwiesen wird, müssen ein oder mehrere der folgenden Kriterien erfüllen:</span><span class="sxs-lookup"><span data-stu-id="493ae-116">All referenced assemblies must meet one or more of the following criteria:</span></span>  
  
-   <span data-ttu-id="493ae-117">Die Assembly ist bereits in der Datenbank registriert.</span><span class="sxs-lookup"><span data-stu-id="493ae-117">The assembly is already registered in the database.</span></span>  
  
-   <span data-ttu-id="493ae-118">Die Assembly ist eine der unterstützten Assemblys.</span><span class="sxs-lookup"><span data-stu-id="493ae-118">The assembly is one of the supported assemblies.</span></span> <span data-ttu-id="493ae-119">Weitere Informationen finden Sie [unter Supported .NET Framework Libraries](supported-net-framework-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="493ae-119">For more information, see [Supported .NET Framework Libraries](supported-net-framework-libraries.md).</span></span>  
  
-   <span data-ttu-id="493ae-120">Sie verwenden `CREATE ASSEMBLY FROM` \* \<location> ,\* und alle referenzierten Assemblys und ihre Abhängigkeiten sind in verfügbar *\<location>* .</span><span class="sxs-lookup"><span data-stu-id="493ae-120">You are using `CREATE ASSEMBLY FROM`*\<location>,* and all the referenced assemblies and their dependencies are available in *\<location>*.</span></span>  
  
-   <span data-ttu-id="493ae-121">Sie verwenden `CREATE ASSEMBLY FROM` \* \<bytes ...> ,\* und alle Verweise werden mit durch Leerzeichen getrennten Bytes angegeben.</span><span class="sxs-lookup"><span data-stu-id="493ae-121">You are using `CREATE ASSEMBLY FROM`*\<bytes ...>,* and all the references are specified via space separated bytes.</span></span>  
  
### <a name="external_access"></a><span data-ttu-id="493ae-122">EXTERNAL_ACCESS</span><span class="sxs-lookup"><span data-stu-id="493ae-122">EXTERNAL_ACCESS</span></span>  
 <span data-ttu-id="493ae-123">Alle `EXTERNAL_ACCESS`-Assemblys müssen die folgenden Kriterien erfüllen:</span><span class="sxs-lookup"><span data-stu-id="493ae-123">All `EXTERNAL_ACCESS` assemblies must meet the following criteria:</span></span>  
  
-   <span data-ttu-id="493ae-124">Statische Felder werden nicht verwendet, um Informationen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="493ae-124">Static fields are not used to store information.</span></span> <span data-ttu-id="493ae-125">Schreibgeschützte statische Felder sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="493ae-125">Read-only static fields are allowed.</span></span>  
  
-   <span data-ttu-id="493ae-126">Der PEVerify-Test wird bestanden.</span><span class="sxs-lookup"><span data-stu-id="493ae-126">PEVerify test is passed.</span></span> <span data-ttu-id="493ae-127">Das PEVerify-Tool (peverify.exe), das überprüft, ob der MSIL-Code und die zugeordneten Metadaten den Anforderungen an die Typsicherheit entsprechen, wird mit .NET Framework SDK zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="493ae-127">The PEVerify tool (peverify.exe), which checks that the MSIL code and associated metadata meet type safety requirements, is provided with the .NET Framework SDK.</span></span>  
  
-   <span data-ttu-id="493ae-128">Die Synchronisierung, z. B. mit der `SynchronizationAttribute`-Klasse, wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="493ae-128">Synchronization, for example with the `SynchronizationAttribute` class, is not used.</span></span>  
  
-   <span data-ttu-id="493ae-129">Finalizer-Methoden werden nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="493ae-129">Finalizer methods are not used.</span></span>  
  
 <span data-ttu-id="493ae-130">Die folgenden benutzerdefinierten Attribute sind in `EXTERNAL_ACCESS`-Assemblys nicht zulässig:</span><span class="sxs-lookup"><span data-stu-id="493ae-130">The following custom attributes are disallowed in `EXTERNAL_ACCESS` assemblies:</span></span>  
  
-   <span data-ttu-id="493ae-131">System.ContextStaticAttribute</span><span class="sxs-lookup"><span data-stu-id="493ae-131">System.ContextStaticAttribute</span></span>  
  
-   <span data-ttu-id="493ae-132">System.MTAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="493ae-132">System.MTAThreadAttribute</span></span>  
  
-   <span data-ttu-id="493ae-133">System.Runtime.CompilerServices.MethodImplAttribute</span><span class="sxs-lookup"><span data-stu-id="493ae-133">System.Runtime.CompilerServices.MethodImplAttribute</span></span>  
  
-   <span data-ttu-id="493ae-134">System.Runtime.CompilerServices.CompilationRelaxationsAttribute</span><span class="sxs-lookup"><span data-stu-id="493ae-134">System.Runtime.CompilerServices.CompilationRelaxationsAttribute</span></span>  
  
-   <span data-ttu-id="493ae-135">System.Runtime.Remoting.Contexts.ContextAttribute</span><span class="sxs-lookup"><span data-stu-id="493ae-135">System.Runtime.Remoting.Contexts.ContextAttribute</span></span>  
  
-   <span data-ttu-id="493ae-136">System.Runtime.Remoting.Contexts.SynchronizationAttribute</span><span class="sxs-lookup"><span data-stu-id="493ae-136">System.Runtime.Remoting.Contexts.SynchronizationAttribute</span></span>  
  
-   <span data-ttu-id="493ae-137">System.Runtime.InteropServices.DllImportAttribute</span><span class="sxs-lookup"><span data-stu-id="493ae-137">System.Runtime.InteropServices.DllImportAttribute</span></span>  
  
-   <span data-ttu-id="493ae-138">System.Security.Permissions.CodeAccessSecurityAttribute</span><span class="sxs-lookup"><span data-stu-id="493ae-138">System.Security.Permissions.CodeAccessSecurityAttribute</span></span>  
  
-   <span data-ttu-id="493ae-139">System.Security.SuppressUnmanagedCodeSecurityAttribute</span><span class="sxs-lookup"><span data-stu-id="493ae-139">System.Security.SuppressUnmanagedCodeSecurityAttribute</span></span>  
  
-   <span data-ttu-id="493ae-140">System.Security.UnverifiableCodeAttribute</span><span class="sxs-lookup"><span data-stu-id="493ae-140">System.Security.UnverifiableCodeAttribute</span></span>  
  
-   <span data-ttu-id="493ae-141">System.STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="493ae-141">System.STAThreadAttribute</span></span>  
  
-   <span data-ttu-id="493ae-142">System.ThreadStaticAttribute</span><span class="sxs-lookup"><span data-stu-id="493ae-142">System.ThreadStaticAttribute</span></span>  
  
### <a name="safe"></a><span data-ttu-id="493ae-143">SAFE</span><span class="sxs-lookup"><span data-stu-id="493ae-143">SAFE</span></span>  
  
-   <span data-ttu-id="493ae-144">Alle `EXTERNAL_ACCESS`-Assemblybedingungen werden überprüft.</span><span class="sxs-lookup"><span data-stu-id="493ae-144">All `EXTERNAL_ACCESS` assembly conditions are checked.</span></span>  
  
## <a name="runtime-checks"></a><span data-ttu-id="493ae-145">Laufzeitüberprüfungen</span><span class="sxs-lookup"><span data-stu-id="493ae-145">Runtime Checks</span></span>  
 <span data-ttu-id="493ae-146">Zur Laufzeit wird die Codeassembly auf die folgenden Bedingungen überprüft.</span><span class="sxs-lookup"><span data-stu-id="493ae-146">At runtime, the code assembly is checked for the following conditions.</span></span> <span data-ttu-id="493ae-147">Wird eine dieser Bedingungen erkannt, darf der verwaltete Code nicht ausgeführt werden und es wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="493ae-147">If any of these conditions are found, the managed code will not be allowed to run and an exception will be thrown.</span></span>  
  
### <a name="unsafe"></a><span data-ttu-id="493ae-148">UNSAFE</span><span class="sxs-lookup"><span data-stu-id="493ae-148">UNSAFE</span></span>  
 <span data-ttu-id="493ae-149">Das Laden einer Assembly (explizit durch Aufrufen der- `System.Reflection.Assembly.Load()` Methode aus einem Bytearray oder implizit durch die Verwendung des `Reflection.Emit` -Namespace) ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="493ae-149">Loading an assembly-either explicitly by calling the `System.Reflection.Assembly.Load()` method from a byte array, or implicitly through the use of `Reflection.Emit` namespace-is not permitted.</span></span>  
  
### <a name="external_access"></a><span data-ttu-id="493ae-150">EXTERNAL_ACCESS</span><span class="sxs-lookup"><span data-stu-id="493ae-150">EXTERNAL_ACCESS</span></span>  
 <span data-ttu-id="493ae-151">Alle `UNSAFE`-Bedingungen werden überprüft.</span><span class="sxs-lookup"><span data-stu-id="493ae-151">All `UNSAFE` conditions are checked.</span></span>  
  
 <span data-ttu-id="493ae-152">Alle Typen und Methoden, die mit den folgenden Hostschutzattributwerten in der unterstützten Assemblyliste als Anmerkungen versehen sind, sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="493ae-152">All types and methods annotated with the following host protection attribute (HPA) values in the supported list of assemblies are disallowed.</span></span>  
  
-   <span data-ttu-id="493ae-153">SelfAffectingProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="493ae-153">SelfAffectingProcessMgmt</span></span>  
  
-   <span data-ttu-id="493ae-154">SelfAffectingThreading</span><span class="sxs-lookup"><span data-stu-id="493ae-154">SelfAffectingThreading</span></span>  
  
-   <span data-ttu-id="493ae-155">Synchronization</span><span class="sxs-lookup"><span data-stu-id="493ae-155">Synchronization</span></span>  
  
-   <span data-ttu-id="493ae-156">SharedState</span><span class="sxs-lookup"><span data-stu-id="493ae-156">SharedState</span></span>  
  
-   <span data-ttu-id="493ae-157">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="493ae-157">ExternalProcessMgmt</span></span>  
  
-   <span data-ttu-id="493ae-158">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="493ae-158">ExternalThreading</span></span>  
  
-   <span data-ttu-id="493ae-159">SecurityInfrastructure</span><span class="sxs-lookup"><span data-stu-id="493ae-159">SecurityInfrastructure</span></span>  
  
-   <span data-ttu-id="493ae-160">MayLeakOnAbort</span><span class="sxs-lookup"><span data-stu-id="493ae-160">MayLeakOnAbort</span></span>  
  
-   <span data-ttu-id="493ae-161">UI</span><span class="sxs-lookup"><span data-stu-id="493ae-161">UI</span></span>  
  
 <span data-ttu-id="493ae-162">Weitere Informationen zu HPAs und eine Liste der unzulässigen Typen und Member in den unterstützten Assemblys finden Sie unter [Host Schutz Attribute und CLR-Integrations Programmierung](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md).</span><span class="sxs-lookup"><span data-stu-id="493ae-162">For more information about HPAs and a list of disallowed types and members in the supported assemblies, see [Host Protection Attributes and CLR Integration Programming](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md).</span></span>  
  
### <a name="safe"></a><span data-ttu-id="493ae-163">SAFE</span><span class="sxs-lookup"><span data-stu-id="493ae-163">SAFE</span></span>  
 <span data-ttu-id="493ae-164">Alle `EXTERNAL_ACCESS`-Bedingungen werden überprüft.</span><span class="sxs-lookup"><span data-stu-id="493ae-164">All `EXTERNAL_ACCESS` conditions are checked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="493ae-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="493ae-165">See Also</span></span>  
 <span data-ttu-id="493ae-166">[Unterstützte .NET Framework-Bibliotheken](supported-net-framework-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="493ae-166">[Supported .NET Framework Libraries](supported-net-framework-libraries.md) </span></span>  
 <span data-ttu-id="493ae-167">[Code Zugriffssicherheit für die CLR-Integration](../security/clr-integration-code-access-security.md) </span><span class="sxs-lookup"><span data-stu-id="493ae-167">[CLR Integration Code Access Security](../security/clr-integration-code-access-security.md) </span></span>  
 <span data-ttu-id="493ae-168">[Host Schutz Attribute und Programmierung der CLR-Integration](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md) </span><span class="sxs-lookup"><span data-stu-id="493ae-168">[Host Protection Attributes and CLR Integration Programming](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md) </span></span>  
 [<span data-ttu-id="493ae-169">Erstellen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="493ae-169">Creating an Assembly</span></span>](../assemblies/creating-an-assembly.md)  
  
  
