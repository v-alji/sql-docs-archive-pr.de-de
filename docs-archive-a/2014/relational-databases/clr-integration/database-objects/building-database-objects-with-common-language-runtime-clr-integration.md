---
title: Aufbauen von Datenbankobjekten mit CLR (Common Language Runtime)-Integration | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- routines [CLR integration]
- database objects [CLR integration], building
- common language runtime [SQL Server], building database objects
- managed code [SQL Server], database objects
- building database objects [CLR integration]
- .NET Framework routines [SQL Server]
ms.assetid: ce34132c-bfa3-447b-9131-b6e17c672efe
author: rothja
ms.author: jroth
ms.openlocfilehash: 3c849c095a3be1c590e6fcb3ce87a0725eb795c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619160"
---
# <a name="building-database-objects-with-common-language-runtime-clr-integration"></a><span data-ttu-id="1721d-102">Erstellen von Datenbankobjekten mit CLR-Integration (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="1721d-102">Building Database Objects with Common Language Runtime (CLR) Integration</span></span>
  <span data-ttu-id="1721d-103">Sie können Datenbankobjekte mithilfe [!INCLUDE[ssNoVersion](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] von erstellen, die als "CLR-Routine" bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="1721d-103">You can build database objects using the [!INCLUDE[ssNoVersion](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is referred to as a "CLR routine."</span></span> <span data-ttu-id="1721d-104">Es gibt folgende Routinen:</span><span class="sxs-lookup"><span data-stu-id="1721d-104">These routines include:</span></span>  
  
-   <span data-ttu-id="1721d-105">Benutzerdefinierte Skalarwertfunktionen (Skalar-UDFs)</span><span class="sxs-lookup"><span data-stu-id="1721d-105">Scalar-valued user-defined functions (scalar UDFs)</span></span>  
  
-   <span data-ttu-id="1721d-106">Benutzerdefinierte Tabellenwertfunktionen (TVFs)</span><span class="sxs-lookup"><span data-stu-id="1721d-106">Table-valued user-defined functions (TVFs)</span></span>  
  
-   <span data-ttu-id="1721d-107">Benutzerdefinierte Prozeduren (UDPs)</span><span class="sxs-lookup"><span data-stu-id="1721d-107">User-defined procedures (UDPs)</span></span>  
  
-   <span data-ttu-id="1721d-108">Benutzerdefinierte Trigger</span><span class="sxs-lookup"><span data-stu-id="1721d-108">User-defined triggers</span></span>  
  
 <span data-ttu-id="1721d-109">CLR-Routinen haben in verwaltetem Code dieselbe Struktur.</span><span class="sxs-lookup"><span data-stu-id="1721d-109">CLR routines have the same structure in managed code.</span></span> <span data-ttu-id="1721d-110">Sie werden öffentlichen, statischen (freigegeben in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET) Methoden einer Klasse zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="1721d-110">They are mapped to public, static (shared in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET) methods of a class.</span></span> <span data-ttu-id="1721d-111">Außer Routinen können auch benutzerdefinierte Typen (UDTs) und benutzerdefinierte Aggregatfunktionen mithilfe von .NET Framework definiert werden.</span><span class="sxs-lookup"><span data-stu-id="1721d-111">In addition to routines, user-defined types (UDTs) and user-defined aggregate functions can also be defined using the .NET Framework.</span></span> <span data-ttu-id="1721d-112">UDTs und benutzerdefinierte Aggregatfunktionen werden ganzen .NET Framework-Klassen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="1721d-112">UDTs and user-defined aggregates are mapped to entire .NET Framework classes.</span></span>  
  
 <span data-ttu-id="1721d-113">Jeder Typ .NET Framework Routine verfügt über einen [!INCLUDE[tsql](../../../includes/ssnoversion-md.md)] , der [!INCLUDE[tsql](../../../includes/tsql-md.md)] verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1721d-113">Each type of .NET Framework routine has a [!INCLUDE[tsql](../../../includes/ssnoversion-md.md)] that the [!INCLUDE[tsql](../../../includes/tsql-md.md)] equivalent can be used.</span></span> <span data-ttu-id="1721d-114">Skalar-UDFs können beispielsweise in jedem Skalarausdruck verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1721d-114">For instance, scalar UDFs can be used in any scalar expression.</span></span> <span data-ttu-id="1721d-115">Eine TVF kann in jeder FROM-Klausel verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1721d-115">A TVF can be used in any FROM clause.</span></span> <span data-ttu-id="1721d-116">Eine Prozedur kann in einer EXEC-Anweisung oder von einer Clientanwendung aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1721d-116">A procedure can be invoked in an EXEC statement or invoked from a client application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1721d-117">CLR-Objekte (benutzerdefinierte Funktion, benutzerdefinierter Typ oder Trigger)können auf der Common Language Runtime auf mehreren Threads (paralleler Plan) ausgeführt werden, wenn der Abfrageoptimierer feststellt, dass dies vorteilhaft ist.</span><span class="sxs-lookup"><span data-stu-id="1721d-117">Execution of a CLR object (user-defined function, user-defined type, or trigger) on the common language runtime can take place on multiple threads (parallel plan), if the query optimizer decides it is beneficial.</span></span> <span data-ttu-id="1721d-118">Benutzerdefinierte Funktionen, die auf Daten zugreifen, werden jedoch auf einem seriellen Plan ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1721d-118">However, if a user-defined function accesses data, execution will be  on a serial plan.</span></span> <span data-ttu-id="1721d-119">Bei Ausführung auf einer Serverversion vor [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] müssen benutzerdefinierte Funktionen, die LOB-Parameter oder Rückgabewerte enthalten, ebenfalls nach einem seriellen Plan ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1721d-119">When executed on a server version prior to [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)], if a user-defined function contains LOB parameters or return values, execution also must be on a serial plan.</span></span>  
  
 <span data-ttu-id="1721d-120">In der folgenden Tabelle sind die in diesem Abschnitt behandelten Themen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="1721d-120">The following table lists the topics covered in this section.</span></span>  
  
 [<span data-ttu-id="1721d-121">Erste Schritte mit der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="1721d-121">Getting Started with CLR Integration</span></span>](getting-started-with-clr-integration.md)  
 <span data-ttu-id="1721d-122">Enthält eine kurze Übersicht über die Bibliotheken und Namespaces, die benötigt werden, um Objekte mithilfe der CLR-Integration in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="1721d-122">Provides a brief overview of the libraries and namespaces required to compile object using CLR integration with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1721d-123">Enthält das Beispiel "Hello World" für eine CLR-gespeicherte Prozedur.</span><span class="sxs-lookup"><span data-stu-id="1721d-123">Includes an example "Hello World" CLR stored procedure.</span></span>  
  
 [<span data-ttu-id="1721d-124">Unterstützte .NET Framework-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="1721d-124">Supported .NET Framework Libraries</span></span>](supported-net-framework-libraries.md)  
 <span data-ttu-id="1721d-125">Enthält Informationen zu den durch die CLR-Integration unterstützten .NET Framework-Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="1721d-125">Provides information on the .NET Framework libraries supported by CLR integration.</span></span>  
  
 [<span data-ttu-id="1721d-126">Beschränkungen des Programmiermodells für die CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="1721d-126">CLR Integration Programming Model Restrictions</span></span>](clr-integration-programming-model-restrictions.md)  
 <span data-ttu-id="1721d-127">Enthält Informationen zu Beschränkungen des Programmiermodells für die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="1721d-127">Provides information about CLR integration programming model restrictions.</span></span>  
  
 [<span data-ttu-id="1721d-128">SQL Server-Datentypen in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1721d-128">SQL Server Data Types in the .NET Framework</span></span>](../../clr-integration-database-objects-types-net-framework/sql-server-data-types-in-the-net-framework.md)  
 <span data-ttu-id="1721d-129">Eine Übersicht über [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Datentypen und die .NET Framework-Entsprechungen.</span><span class="sxs-lookup"><span data-stu-id="1721d-129">An overview of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types and their .NET Framework equivalents.</span></span>  
  
 [<span data-ttu-id="1721d-130">Übersicht über benutzerdefinierte Attribute der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="1721d-130">Overview of CLR Integration Custom Attributes</span></span>](../../../database-engine/dev-guide/overview-of-clr-integration-custom-attributes.md)  
 <span data-ttu-id="1721d-131">Enthält Informationen zu benutzerdefinierten Attributen der CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="1721d-131">Provides information about CLR integration custom attributes.</span></span>  
  
 [<span data-ttu-id="1721d-132">CLR-benutzerdefinierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="1721d-132">CLR User-Defined Functions</span></span>](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md)  
 <span data-ttu-id="1721d-133">Beschreibt die Implementierung und Verwendung der unterschiedlichen CLR-Funktionstypen: Tabellenwertfunktionen, Skalarfunktionen und benutzerdefinierte Aggregatfunktionen.</span><span class="sxs-lookup"><span data-stu-id="1721d-133">Describes how to implement and use the various types of CLR functions: table-valued, scalar, and user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="1721d-134">Benutzerdefinierte CLR-Typen</span><span class="sxs-lookup"><span data-stu-id="1721d-134">CLR User-Defined Types</span></span>](../../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md)  
 <span data-ttu-id="1721d-135">Beschreibt die Implementierung und Verwendung von CLR-benutzerdefinierten Typen.</span><span class="sxs-lookup"><span data-stu-id="1721d-135">Describes how to implement and use CLR user-defined types.</span></span>  
  
 [<span data-ttu-id="1721d-136">CLR-gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="1721d-136">CLR Stored Procedures</span></span>](../../../database-engine/dev-guide/clr-stored-procedures.md)  
 <span data-ttu-id="1721d-137">Beschreibt die Implementierung und Verwendung von CLR-gespeicherten Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="1721d-137">Describes how to implement and use CLR stored procedures.</span></span>  
  
 [<span data-ttu-id="1721d-138">CLR-Trigger</span><span class="sxs-lookup"><span data-stu-id="1721d-138">CLR Triggers</span></span>](../../../database-engine/dev-guide/clr-triggers.md)  
 <span data-ttu-id="1721d-139">Beschreibt die Implementierung und Verwendung von CLR-Triggern.</span><span class="sxs-lookup"><span data-stu-id="1721d-139">Describes how to implement and use CLR triggers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1721d-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1721d-140">See Also</span></span>  
 [<span data-ttu-id="1721d-141">Übersicht über die CLR-&#41; Integration in Common Language Runtime &#40;</span><span class="sxs-lookup"><span data-stu-id="1721d-141">Common Language Runtime &#40;CLR&#41; Integration Overview</span></span>](../common-language-runtime-integration-overview.md)  
  
  
