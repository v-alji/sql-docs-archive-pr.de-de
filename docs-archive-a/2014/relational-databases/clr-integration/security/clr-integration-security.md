---
title: Sicherheit bei der CLR-Integration | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- security [CLR integration]
- authorization [CLR integration]
- common language runtime [SQL Server], security
- database objects [CLR integration], security
ms.assetid: 05d7a471-c5d5-4730-b903-e4edc8157bb4
author: rothja
ms.author: jroth
ms.openlocfilehash: 0d99d32a061d8fe78a8ac3642a503cceb45f3809
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616583"
---
# <a name="clr-integration-security"></a><span data-ttu-id="76416-102">Sicherheit der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="76416-102">CLR Integration Security</span></span>
  <span data-ttu-id="76416-103">Das Sicherheitsmodell des [!INCLUDE[ssNoVersion](../../../includes/dnprdnshort-md.md)] Common Language Runtime (CLR) verwaltet und schützt den Zugriff zwischen verschiedenen Typen von CLR-und nicht-CLR-Objekten, die innerhalb einer Anweisung ausgeführt werden, [!INCLUDE[ssNoVersion](../../../includes/tsql-md.md)] oder einem anderen CLR-Objekt, das auf dem Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="76416-103">The security model of the [!INCLUDE[ssNoVersion](../../../includes/dnprdnshort-md.md)] common language runtime (CLR) manages and secures access between different types of CLR and non-CLR objects running within [!INCLUDE[ssNoVersion](../../../includes/tsql-md.md)] statement or another CLR object running in the server.</span></span> <span data-ttu-id="76416-104">Die Aufrufe zwischen Objekten werden als Links bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="76416-104">The calls between objects are referred to as links.</span></span> <span data-ttu-id="76416-105">Die Typen von Sicherheitsüberprüfungen, die für diese Objekte ausgeführt werden, hängen von den betroffenen Linktypen ab.</span><span class="sxs-lookup"><span data-stu-id="76416-105">The types of security checks performed on these objects depend on the types of links involved.</span></span>  
  
 <span data-ttu-id="76416-106">Das Sicherheitsmodell der CLR Integration dient folgenden Zielen:</span><span class="sxs-lookup"><span data-stu-id="76416-106">The CLR integration security model has the following goals:</span></span>  
  
-   <span data-ttu-id="76416-107">Standardmäßig wird der verwaltete Benutzercode in ausgeführt [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76416-107">By default, running managed user code on [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="76416-108">Die Durchführung von Vorgängen, die die Stabilität von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] potenziell beeinträchtigen, sollte durch entsprechende Berechtigungen auf höherer Ebene geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="76416-108">Performing operations that potentially compromise the robustness of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] should be protected by appropriate high-level permissions.</span></span>  
  
-   <span data-ttu-id="76416-109">Verwalteter Benutzercode sollte keinen unbefugten Zugriff auf Benutzerdaten oder anderen in der Datenbank enthaltenen Benutzercode erhalten.</span><span class="sxs-lookup"><span data-stu-id="76416-109">Managed user code should not gain unauthorized access to user data or other user code in the database.</span></span> <span data-ttu-id="76416-110">Benutzerdefinierter Code sollte in dem Sicherheitskontext der Benutzersitzung, in der er aufgerufen wurde, und mit den richtigen Berechtigungen für diesen Sicherheitskontext ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="76416-110">User-defined code should run under the security context of the user-session that invoked it, and with the correct privileges for that security context.</span></span>  
  
-   <span data-ttu-id="76416-111">Der Benutzercode sollte durch geeignete Maßnahmen daran gehindert werden, auf Ressourcen außerhalb des Servers zuzugreifen, sodass er ausschließlich für den Zugriff auf lokale Daten und Berechnungen genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="76416-111">There should be controls for restricting user code from accessing any resources outside the server, using it strictly for local data access and computation.</span></span>  
  
-   <span data-ttu-id="76416-112">Benutzerdefinierter Code sollte nicht in der Lage sein, nur deshalb unbefugten Zugriff auf Systemressourcen zu erlangen, weil er im [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="76416-112">User-defined code should not be able to gain unauthorized access to system resources by virtue of running in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] process.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="76416-113">mit dem Code Zugriffs basierten Sicherheitsmodell der CLR.</span><span class="sxs-lookup"><span data-stu-id="76416-113">with the code access-based security model of the CLR.</span></span> <span data-ttu-id="76416-114">Einige Vorteile dieses kombinierten Sicherheitsansatzes werden in diesem Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="76416-114">Some of the advantages of this combined approach to security are discussed in this section.</span></span>  
  
 <span data-ttu-id="76416-115">In der folgenden Tabelle sind die Themen dieses Abschnitts aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="76416-115">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="76416-116">CLR-Integration und Codezugriffssicherheit</span><span class="sxs-lookup"><span data-stu-id="76416-116">CLR Integration Code Access Security</span></span>](clr-integration-code-access-security.md)  
 <span data-ttu-id="76416-117">Erläutert das Codezugriffssicherheitsmodell für verwalteten Code.</span><span class="sxs-lookup"><span data-stu-id="76416-117">Discusses the code access security (CAS) model for managed code.</span></span>  
  
 [<span data-ttu-id="76416-118">Hostschutzattribute und Programmierung der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="76416-118">Host Protection Attributes and CLR Integration Programming</span></span>](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md)  
 <span data-ttu-id="76416-119">Stellt Informationen zu den Hostschutzattributwerten bereit, die in SAFE-Assemblys und EXTERNAL_ACCESS-Assemblys nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="76416-119">Provides information about the host protection attribute (HPA) values that are disallowed in SAFE and EXTERNAL_ACCESS assemblies.</span></span>  
  
 [<span data-ttu-id="76416-120">Links in Sicherheit der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="76416-120">Links in CLR Integration Security</span></span>](../../../database-engine/dev-guide/links-in-clr-integration-security.md)  
 <span data-ttu-id="76416-121">Beschreibt, wie Teile von Benutzercode in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] einander aufrufen können.</span><span class="sxs-lookup"><span data-stu-id="76416-121">Describes how pieces of user-code can call each other in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="76416-122">Identitätswechsel und Sicherheit der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="76416-122">Impersonation and CLR Integration Security</span></span>](../../../database-engine/dev-guide/impersonation-and-clr-integration-security.md)  
 <span data-ttu-id="76416-123">Erläutert, wie verwalteter Code mithilfe des Identitätswechsels auf externe Ressourcen zugreift.</span><span class="sxs-lookup"><span data-stu-id="76416-123">Discusses how managed code accesses external resources using impersonation.</span></span>  
  
 [<span data-ttu-id="76416-124">Zulassen von teilweise vertrauenswürdigen Aufrufern</span><span class="sxs-lookup"><span data-stu-id="76416-124">Allowing Partially Trusted Callers</span></span>](../../../database-engine/dev-guide/allowing-partially-trusted-callers.md)  
 <span data-ttu-id="76416-125">Erläutert Probleme, die auftreten, wenn eine verwaltete Methode eine Methode in einer Klasse aufruft, die in einer anderen Assembly enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="76416-125">Discusses issues that arise when a managed method invokes a method in a class contained in another assembly.</span></span>  
  
 [<span data-ttu-id="76416-126">Anwendungsdomänen und Sicherheit der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="76416-126">Application Domains and CLR Integration Security</span></span>](../../../database-engine/dev-guide/application-domains-and-clr-integration-security.md)  
 <span data-ttu-id="76416-127">Beschreibt, wie Assemblys in Anwendungsdomänen geladen werden.</span><span class="sxs-lookup"><span data-stu-id="76416-127">Describes how assemblies are loaded into application domains.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76416-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76416-128">See Also</span></span>  
 [<span data-ttu-id="76416-129">Verwalten von CLR-Integrationsassemblys</span><span class="sxs-lookup"><span data-stu-id="76416-129">Managing CLR Integration Assemblies</span></span>](../assemblies/managing-clr-integration-assemblies.md)  
  
  
