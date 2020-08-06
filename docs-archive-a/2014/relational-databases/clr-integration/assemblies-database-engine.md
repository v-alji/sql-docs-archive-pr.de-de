---
title: Assemblys (Datenbank-Engine) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- assemblies [CLR integration]
- assemblies [CLR integration], about assemblies
- managed code [SQL Server], assemblies
ms.assetid: 4b146437-3061-47f6-9e8c-26eeea10b54e
author: rothja
ms.author: jroth
ms.openlocfilehash: 7edb18ccfa9954fe52093f87948f956c2eacc1b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720080"
---
# <a name="assemblies-database-engine"></a><span data-ttu-id="4a896-102">Assemblys (Database Engine)</span><span class="sxs-lookup"><span data-stu-id="4a896-102">Assemblies (Database Engine)</span></span>
  <span data-ttu-id="4a896-103">Die Themen in diesem Abschnitt enthalten Informationen, damit Sie Assemblys verstehen, entwerfen und implementieren können.</span><span class="sxs-lookup"><span data-stu-id="4a896-103">The topics in this section provide information to help you understand, design, and implement assemblies.</span></span>  
  
 <span data-ttu-id="4a896-104">Assemblys sind dll-Dateien, die in einer Instanz von verwendet werden, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] um Funktionen, gespeicherte Prozeduren, Trigger, benutzerdefinierte Aggregate und benutzerdefinierte Typen bereitzustellen, die in einer der verwalteten Code Sprachen geschrieben werden, die von der [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Common Language Runtime (CLR) gehostet werden, statt in [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4a896-104">Assemblies are DLL files used in an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to deploy functions, stored procedures, triggers, user-defined aggregates, and user-defined types that are written in one of the managed code languages hosted by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] common language runtime (CLR), instead of in [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4a896-105">Eine Assembly in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ist ein Objekt, das auf ein verwaltetes Anwendungsmodul (DLL-Datei) verweist, das in der [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]-CLR erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="4a896-105">An assembly in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is an object that references a managed application module (.dll file) that was created in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] common language runtime.</span></span> <span data-ttu-id="4a896-106">Eine Assembly enthält Klassenmetadaten und verwalteten Code.</span><span class="sxs-lookup"><span data-stu-id="4a896-106">An assembly contains class metadata and managed code.</span></span> <span data-ttu-id="4a896-107">Das Hochladen einer Assembly in eine Instanz von SQL Server ist der erste Schritt beim Erstellen eines der folgenden Datenbankobjekte:</span><span class="sxs-lookup"><span data-stu-id="4a896-107">Uploading an assembly to an instance of SQL Server is the first step toward creating any of the following database objects:</span></span>  
  
-   <span data-ttu-id="4a896-108">CLR-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="4a896-108">CLR functions.</span></span> <span data-ttu-id="4a896-109">Weitere Informationen finden Sie unter [Erstellen von CLR-Funktionen](../user-defined-functions/create-clr-functions.md).</span><span class="sxs-lookup"><span data-stu-id="4a896-109">For more information, see [Create CLR Functions](../user-defined-functions/create-clr-functions.md).</span></span>  
  
-   <span data-ttu-id="4a896-110">CLR-gespeicherte Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="4a896-110">CLR stored procedures.</span></span> <span data-ttu-id="4a896-111">Weitere Informationen finden Sie unter [gespeicherte CLR-Prozeduren](../../database-engine/dev-guide/clr-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="4a896-111">For more information, see [CLR Stored Procedures](../../database-engine/dev-guide/clr-stored-procedures.md).</span></span>  
  
-   <span data-ttu-id="4a896-112">CLR-Trigger.</span><span class="sxs-lookup"><span data-stu-id="4a896-112">CLR triggers.</span></span> <span data-ttu-id="4a896-113">Weitere Informationen finden Sie unter [Erstellen von CLR-Triggern](../triggers/create-clr-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="4a896-113">For more information, see [Create CLR Triggers](../triggers/create-clr-triggers.md).</span></span>  
  
-   <span data-ttu-id="4a896-114">Benutzerdefinierte Aggregatfunktionen.</span><span class="sxs-lookup"><span data-stu-id="4a896-114">User-defined aggregate functions.</span></span> <span data-ttu-id="4a896-115">Weitere Informationen finden Sie unter [Erstellen von benutzerdefinierten Aggregaten](../user-defined-functions/create-user-defined-aggregates.md).</span><span class="sxs-lookup"><span data-stu-id="4a896-115">For more information, see [Create User-defined Aggregates](../user-defined-functions/create-user-defined-aggregates.md).</span></span>  
  
-   <span data-ttu-id="4a896-116">Benutzerdefinierte Typen.</span><span class="sxs-lookup"><span data-stu-id="4a896-116">User-defined types.</span></span> <span data-ttu-id="4a896-117">Weitere Informationen finden Sie unter [Verwenden von benutzerdefinierten Typen](../native-client/features/using-user-defined-types.md).</span><span class="sxs-lookup"><span data-stu-id="4a896-117">For more information, see [Using User-Defined Types](../native-client/features/using-user-defined-types.md).</span></span>  
  
 <span data-ttu-id="4a896-118">Assemblys besitzen in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="4a896-118">Assemblies perform the following functions in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="4a896-119">Aufnehmen des verwalteten Codes, der die Funktionen eines oder mehrerer der CLR-Datenbankobjekte ausführt, die oben aufgelistet wurden.</span><span class="sxs-lookup"><span data-stu-id="4a896-119">Contain the managed code that runs the functionality of one or more of the CLR database objects previously listed.</span></span>  
  
-   <span data-ttu-id="4a896-120">Aufnehmen von Metadaten, die z. B. die Versionsnummer und Kultur der Assembly, einen optionalen öffentlichen Schlüssel zum eindeutigen Identifizieren der Liste der Klassen der Assembly, die in der Assembly definierten Methoden und die Prozessorarchitektur der Assembly umfassen.</span><span class="sxs-lookup"><span data-stu-id="4a896-120">Contain metadata that includes the version number and culture of the assembly, an optional public key that uniquely identifies the list of classes of the assembly, the methods that are defined in the assembly, and the processor architecture of the assembly.</span></span>  
  
-   <span data-ttu-id="4a896-121">Verwalten des Grades, bis zu dem verwalteter Code auf externe Ressourcen zugreifen kann, durch Steuern der Codezugriffsberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="4a896-121">Manage the degree to which managed code can access outside resources by regulating code access permissions.</span></span>  
  
-   <span data-ttu-id="4a896-122">Aufnehmen von Metadaten zu Abhängigkeiten von anderen Assemblys, auf die durch die Assembly verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="4a896-122">Contain metadata about dependencies on other assemblies that are referenced by the assembly.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4a896-123">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4a896-123">In This Section</span></span>  
  
|<span data-ttu-id="4a896-124">Thema</span><span class="sxs-lookup"><span data-stu-id="4a896-124">Topic</span></span>|<span data-ttu-id="4a896-125">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4a896-125">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="4a896-126">Entwerfen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="4a896-126">Designing Assemblies</span></span>](assemblies-designing.md)|<span data-ttu-id="4a896-127">Erläutert, was vor dem Erstellen einer Assembly berücksichtigt werden muss.</span><span class="sxs-lookup"><span data-stu-id="4a896-127">Explains what you have to consider before creating an assembly.</span></span> <span data-ttu-id="4a896-128">Dazu zählen das Verpacken von Assemblys, Codezugriffsberechtigungen und andere Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="4a896-128">This includes packaging assemblies, code access permissions, and other restrictions.</span></span>|  
|[<span data-ttu-id="4a896-129">Implementieren von Assemblys</span><span class="sxs-lookup"><span data-stu-id="4a896-129">Implementing Assemblies</span></span>](assemblies-implementing.md)|<span data-ttu-id="4a896-130">Beschreibt das Erstellen und Löschen von Assemblys, wie und wann Assemblys geändert werden und wie Metadaten zu Assemblys abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4a896-130">Explains how to create and drop assemblies, how and when to modify assemblies, and how to retrieve metadata about assemblies.</span></span>|  
|[<span data-ttu-id="4a896-131">Abrufen von Informationen zu Assemblys</span><span class="sxs-lookup"><span data-stu-id="4a896-131">Getting Information About Assemblies</span></span>](assemblies-getting-information.md)|<span data-ttu-id="4a896-132">Stellt eine Liste der Katalogsichten und Funktionen zur Verfügung, die für Metadaten zu Assemblys abgefragt werden können.</span><span class="sxs-lookup"><span data-stu-id="4a896-132">Lists the catalog views and functions that can be queried for metadata about assemblies.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4a896-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4a896-133">See Also</span></span>  
 [<span data-ttu-id="4a896-134">Programmierkonzepte für die Integration der Common Language Runtime &#40;CLR&#41;</span><span class="sxs-lookup"><span data-stu-id="4a896-134">Common Language Runtime &#40;CLR&#41; Integration Programming Concepts</span></span>](common-language-runtime-clr-integration-programming-concepts.md)  
  
  
