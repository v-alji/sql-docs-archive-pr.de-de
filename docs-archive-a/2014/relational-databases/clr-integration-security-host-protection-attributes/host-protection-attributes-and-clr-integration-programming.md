---
title: Host Schutz Attribute und Programmierung der CLR-Integration | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- host protection attributes [CLR integration]
- HostProtectionAttribute [CLR integration]
- common language runtime [SQL Server], host protection attributes
- disallowed types and members [CLR integration]
- common language runtime [SQL Server], disallowed types and members
- HPAs [CLR integration]
ms.assetid: 268078df-63ca-4c03-a8e7-7108bcea9697
author: rothja
ms.author: jroth
ms.openlocfilehash: 16ca1e4734e66b0eca85523764739e8f8b32634a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720083"
---
# <a name="host-protection-attributes-and-clr-integration-programming"></a><span data-ttu-id="dbadd-102">Hostschutzattribute und Programmierung der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="dbadd-102">Host Protection Attributes and CLR Integration Programming</span></span>
  <span data-ttu-id="dbadd-103">Die CLR (Common Language Runtime) stellt Mechanismen zur Verfügung, um verwaltete Anwendungsprogrammierschnittstellen (Application Programming Interfaces, APIs), die Teil von .NET Framework sind, mit Anmerkungen in Form von bestimmten Attributen zu versehen, die für einen Host der CLR, wie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ab [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], von Interesse sein können.</span><span class="sxs-lookup"><span data-stu-id="dbadd-103">The common language runtime (CLR) provides a mechanism to annotate managed application programming interfaces (APIs) that are part of the .NET Framework with certain attributes that may be of interest to a host of the CLR, such as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="dbadd-104">Beispiele für solche Hostschutzattribute sind:</span><span class="sxs-lookup"><span data-stu-id="dbadd-104">Examples of such host protection attributes (HPAs) include:</span></span>  
  
-   <span data-ttu-id="dbadd-105">`SharedState`, das angibt, ob die API die Fähigkeit zur Verfügung stellt, einen Freigabezustand (z. B. statische Klassenfelder) zu erstellen oder zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="dbadd-105">`SharedState`, which indicates whether the API exposes the ability to create or manage shared state (for example, static class fields).</span></span>  
  
-   <span data-ttu-id="dbadd-106">`Synchronization`, das angibt, ob die API die Fähigkeit zur Verfügung stellt, die Synchronisierung zwischen Threads auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dbadd-106">`Synchronization`, which indicates whether the API exposes the ability to perform synchronization between threads.</span></span>  
  
-   <span data-ttu-id="dbadd-107">`ExternalProcessMgmt`, das angibt, ob die API eine Möglichkeit zur Kontrolle des Hostprozesses zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="dbadd-107">`ExternalProcessMgmt`, which indicates whether the API exposes a way to control the host process.</span></span>  
  
 <span data-ttu-id="dbadd-108">Anhand dieser Attribute gibt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eine Liste mit Hostschutzattributen an, die in der gehosteten Umgebung von der Codezugriffssicherheit (CAS) nicht zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="dbadd-108">Given these attributes, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] specifies a list of HPAs that are disallowed in the hosted environment through code access security (CAS).</span></span> <span data-ttu-id="dbadd-109">Die CAS-Anforderungen werden von einem von drei [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Berechtigungssätzen angegeben: `SAFE`, `EXTERNAL_ACCESS` oder `UNSAFE`.</span><span class="sxs-lookup"><span data-stu-id="dbadd-109">The CAS requirements are specified by one of three [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permission sets: `SAFE`, `EXTERNAL_ACCESS`, or `UNSAFE`.</span></span> <span data-ttu-id="dbadd-110">Eine dieser drei Sicherheitsebenen wird beim Registrieren der Asssembly auf dem Server mit der `CREATE ASSEMBLY`-Anweisung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="dbadd-110">One of these three security levels is specified when the assembly is registered on the server, using the `CREATE ASSEMBLY` statement.</span></span> <span data-ttu-id="dbadd-111">Bei der Codeausführung innerhalb der Berechtigungssätze `SAFE` oder `EXTERNAL_ACCESS` müssen bestimmte Typen oder Elemente, auf die das `System.Security.Permissions.HostProtectionAttribute`-Attribut angewendet wurde, vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="dbadd-111">Code executing within the `SAFE` or `EXTERNAL_ACCESS` permission sets must avoid certain types or members that have the `System.Security.Permissions.HostProtectionAttribute` attribute applied.</span></span> <span data-ttu-id="dbadd-112">Weitere Informationen finden Sie unter [Erstellen einer Assembly](../clr-integration/assemblies/creating-an-assembly.md) und [Einschränkungen für das Programmiermodell von CLR-Integration](../clr-integration/database-objects/clr-integration-programming-model-restrictions.md).</span><span class="sxs-lookup"><span data-stu-id="dbadd-112">For more information, see [Creating an Assembly](../clr-integration/assemblies/creating-an-assembly.md) and [CLR Integration Programming Model Restrictions](../clr-integration/database-objects/clr-integration-programming-model-restrictions.md).</span></span>  
  
 <span data-ttu-id="dbadd-113">Das `HostProtectionAttribute` ist keine Sicherheitsberechtigung, sondern eher eine Möglichkeit zur Verbesserung der Zuverlässigkeit, da es bestimmte Codekonstrukte (Typen oder Methoden) erkennt, die für den Host möglicherweise nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="dbadd-113">The `HostProtectionAttribute` is not a security permission as much as a way to improve reliability, in that it identifies specific code constructs, either types or methods, that the host may disallow.</span></span> <span data-ttu-id="dbadd-114">Die Verwendung des `HostProtectionAttribute` erzwingt ein Programmiermodell, mit dem die Stabilität des Hosts besser geschützt werden kann.</span><span class="sxs-lookup"><span data-stu-id="dbadd-114">The use of the `HostProtectionAttribute` enforces a programming model that helps protect the stability of the host.</span></span>  
  
## <a name="host-protection-attributes"></a><span data-ttu-id="dbadd-115">Hostschutzattribute</span><span class="sxs-lookup"><span data-stu-id="dbadd-115">Host Protection Attributes</span></span>  
 <span data-ttu-id="dbadd-116">Hostschutzattribute geben die Typen oder Elemente an, die sich nicht für das Hostprogrammiermodell eignen und die folgenden Zuverlässigkeitsrisiken darstellen (ansteigende Gefährdung):</span><span class="sxs-lookup"><span data-stu-id="dbadd-116">HPAs identify types or members that do not fit the host programming model and represent the following increasing levels of reliability threat:</span></span>  
  
-   <span data-ttu-id="dbadd-117">Sie sind andernfalls ohne Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="dbadd-117">Are otherwise benign.</span></span>  
  
-   <span data-ttu-id="dbadd-118">Sie können zur Destabilisierung von serververwaltetem Benutzercode führen.</span><span class="sxs-lookup"><span data-stu-id="dbadd-118">Could lead to destabilization of server-managed user code.</span></span>  
  
-   <span data-ttu-id="dbadd-119">Sie können zur Destabilisierung des Serverprozesses führen.</span><span class="sxs-lookup"><span data-stu-id="dbadd-119">Could lead to destabilization of the server process itself.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="dbadd-120">lässt die Verwendung eines Typs oder Members mit einem nicht zu, das eine- `HostProtectionAttribute` `System.Security.Permissions.HostProtectionResource` Enumeration mit dem Wert `ExternalProcessMgmt` , `ExternalThreading` , `MayLeakOnAbort` , `SecurityInfrastructure` , `SelfAffectingProcessMgmnt` , `SelfAffectingThreading` , `SharedState` , oder angibt `Synchronization` `UI` .</span><span class="sxs-lookup"><span data-stu-id="dbadd-120">disallows the use of a type or member that has a `HostProtectionAttribute` that specifies a `System.Security.Permissions.HostProtectionResource` enumeration with a value of `ExternalProcessMgmt`, `ExternalThreading`, `MayLeakOnAbort`, `SecurityInfrastructure`, `SelfAffectingProcessMgmnt`, `SelfAffectingThreading`, `SharedState`, `Synchronization`, or `UI`.</span></span> <span data-ttu-id="dbadd-121">Dies verhindert, dass Assemblys Elemente aufrufen, die die Freigabe des Zustands aktivieren, Synchronisierungen durchführen, einen Ressourcenverlust bei der Beendigung hervorrufen oder die Integrität des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Prozesses beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="dbadd-121">This prevents the assemblies from calling members that enable sharing state, perform synchronization, might cause a resource leak on termination, or affect the integrity of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span>  
  
### <a name="disallowed-types-and-members"></a><span data-ttu-id="dbadd-122">Unzulässige Typen und Member</span><span class="sxs-lookup"><span data-stu-id="dbadd-122">Disallowed Types and Members</span></span>  
 <span data-ttu-id="dbadd-123">In den folgenden Themen sind Typen und Elemente aufgeführt, deren `HostProtectionResource`-Werte in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="dbadd-123">The following topics identify types and members whose `HostProtectionResource` values are disallowed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dbadd-124">Die Listen in diesen Themen wurden von den unterstützten Assemblys generiert.</span><span class="sxs-lookup"><span data-stu-id="dbadd-124">The lists in these topics were generated from the supported assemblies.</span></span>  <span data-ttu-id="dbadd-125">Weitere Informationen finden Sie [unter Supported .NET Framework Libraries](../clr-integration/database-objects/supported-net-framework-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="dbadd-125">For more information, see [Supported .NET Framework Libraries](../clr-integration/database-objects/supported-net-framework-libraries.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dbadd-126">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="dbadd-126">In This Section</span></span>  
 [<span data-ttu-id="dbadd-127">Unzulässige Typen und Elemente in "Microsoft.VisualBasic.dll"</span><span class="sxs-lookup"><span data-stu-id="dbadd-127">Disallowed Types and Members in Microsoft.VisualBasic.dll</span></span>](disallowed-types-and-members-in-microsoft-visualbasic-dll.md)  
 <span data-ttu-id="dbadd-128">Listet die Typen und Elemente in Microsoft.VisualBasic.dll auf, deren Hostschutzattributwerte nicht zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="dbadd-128">Lists the types and members in Microsoft.VisualBasic.dll whose HPA values are disallowed.</span></span>  
  
 [<span data-ttu-id="dbadd-129">Unzulässige Typen und Elemente in "mscorlib.dll"</span><span class="sxs-lookup"><span data-stu-id="dbadd-129">Disallowed Types and Members in mscorlib.dll</span></span>](disallowed-types-and-members-in-mscorlib-dll.md)  
 <span data-ttu-id="dbadd-130">Listet die Typen und Elemente in mscorlib.dll auf, deren Hostschutzattributwerte nicht zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="dbadd-130">Lists the types and members in mscorlib.dll whose HPA values are disallowed.</span></span>  
  
 [<span data-ttu-id="dbadd-131">Unzulässige Typen und Elemente in "System.dll"</span><span class="sxs-lookup"><span data-stu-id="dbadd-131">Disallowed Types and Members in System.dll</span></span>](disallowed-types-and-members-in-system-dll.md)  
 <span data-ttu-id="dbadd-132">Listet die Typen und Elemente in System.dll auf, deren Hostschutzattributwerte nicht zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="dbadd-132">Lists the types and members in System.dll whose HPA values are disallowed.</span></span>  
  
 [<span data-ttu-id="dbadd-133">Unzulässige Typen und Elemente in "System.Data.dll"</span><span class="sxs-lookup"><span data-stu-id="dbadd-133">Disallowed Types and Members in System.Data.dll</span></span>](disallowed-types-and-members-in-system-data-dll.md)  
 <span data-ttu-id="dbadd-134">Listet die Typen und Elemente in System.Data.dll auf, deren Hostschutzattributwerte nicht zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="dbadd-134">Lists the types and members in System.Data.dll whose HPA values are disallowed.</span></span>  
  
 [<span data-ttu-id="dbadd-135">Unzulässige Typen und Elemente in 'System.Core.dll'</span><span class="sxs-lookup"><span data-stu-id="dbadd-135">Disallowed Types and Members in System.Core.dll</span></span>](disallowed-types-and-members-in-system-core-dll.md)  
 <span data-ttu-id="dbadd-136">Listet die Typen und Elemente in System.Core.dll auf, deren Hostschutzattributwerte nicht zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="dbadd-136">Lists the types and members in System.Core.dll whose HPA values are disallowed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbadd-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dbadd-137">See Also</span></span>  
 <span data-ttu-id="dbadd-138">[Code Zugriffssicherheit für die CLR-Integration](../clr-integration/security/clr-integration-code-access-security.md) </span><span class="sxs-lookup"><span data-stu-id="dbadd-138">[CLR Integration Code Access Security](../clr-integration/security/clr-integration-code-access-security.md) </span></span>  
 <span data-ttu-id="dbadd-139">[Einschränkungen für das Programmiermodell von CLR-Integration](../clr-integration/database-objects/clr-integration-programming-model-restrictions.md) </span><span class="sxs-lookup"><span data-stu-id="dbadd-139">[CLR Integration Programming Model Restrictions](../clr-integration/database-objects/clr-integration-programming-model-restrictions.md) </span></span>  
 [<span data-ttu-id="dbadd-140">Erstellen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="dbadd-140">Creating an Assembly</span></span>](../clr-integration/assemblies/creating-an-assembly.md)  
  
  
