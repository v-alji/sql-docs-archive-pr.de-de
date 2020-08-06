---
title: Erstellen benutzerdefinierter Aggregate | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- aggregate functions [SQL Server], user-defined
- user-defined functions [CLR integration]
ms.assetid: c278b746-6323-4b32-b460-239915acc067
author: rothja
ms.author: jroth
ms.openlocfilehash: c91179cb194bbfb79e8e7a8476e9725877b88afa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724462"
---
# <a name="create-user-defined-aggregates"></a><span data-ttu-id="224d5-102">Erstellen benutzerdefinierter Aggregate</span><span class="sxs-lookup"><span data-stu-id="224d5-102">Create User-defined Aggregates</span></span>
  <span data-ttu-id="224d5-103">Sie können ein Datenbankobjekt in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] erstellen, das in einer CLR-Assembly programmiert wird.</span><span class="sxs-lookup"><span data-stu-id="224d5-103">You can create a database object inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is programmed in a CLR assembly.</span></span> <span data-ttu-id="224d5-104">Datenbankobjekte, die das reichhaltige Programmiermodell nutzen können, das von der CLR (Common Language Runtime) bereitgestellt wird, sind z. B. Trigger, gespeichert Prozeduren, Funktionen, Aggregatfunktionen und Typen.</span><span class="sxs-lookup"><span data-stu-id="224d5-104">Database objects that can leverage the rich programming model provided by the CLR include triggers, stored procedures, functions, aggregate functions, and types.</span></span>  
  
 <span data-ttu-id="224d5-105">Ebenso wie die integrierten Aggregatfunktionen, die in [!INCLUDE[tsql](../../includes/tsql-md.md)]bereitgestellt werden, führen benutzerdefinierte Aggregatfunktionen Berechnungen für eine Menge von Werten aus und geben einen einzelnen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="224d5-105">Like the built-in aggregate functions provided in [!INCLUDE[tsql](../../includes/tsql-md.md)], user-defined aggregate functions perform a calculation on a set of values and return a single value.</span></span>  
  
 <span data-ttu-id="224d5-106">Das Erstellen einer benutzerdefinierten Aggregatfunktion in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] umfasst die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="224d5-106">Creating a user-defined aggregate function in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] involves the following steps:</span></span>  
  
-   <span data-ttu-id="224d5-107">Definieren der benutzerdefinierten Aggregatfunktion als Klasse in einer von [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework unterstützten Sprache.</span><span class="sxs-lookup"><span data-stu-id="224d5-107">Define the user-defined aggregate function as a class in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework-supported language.</span></span> <span data-ttu-id="224d5-108">Weitere Informationen zum Programmieren benutzerdefinierter Aggregate in der CLR finden Sie unter [Benutzerdefinierte CLR-Aggregate](../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md).</span><span class="sxs-lookup"><span data-stu-id="224d5-108">For more information about how to program user-defined aggregates in the CLR, see [CLR User-Defined Aggregates](../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md).</span></span> <span data-ttu-id="224d5-109">Kompilieren dieser Klasse mithilfe des entsprechenden Sprachcompilers, um eine Assembly zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="224d5-109">Compile this class to build a CLR assembly using the appropriate language compiler.</span></span>  
  
-   <span data-ttu-id="224d5-110">Registrieren der Assembly in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe der CREATE ASSEMBLY-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="224d5-110">Register the assembly in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the CREATE ASSEMBLY statement.</span></span> <span data-ttu-id="224d5-111">Weitere Informationen zum Arbeiten mit Assemblys in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] finden Sie unter [Assemblys &#40;Datenbank-Engine&#41;](../clr-integration/assemblies-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="224d5-111">For more information about assemblies in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Assemblies &#40;Database Engine&#41;](../clr-integration/assemblies-database-engine.md).</span></span>  
  
-   <span data-ttu-id="224d5-112">Erstellen des benutzerdefinierten Aggregats, das auf die registrierte Assembly verweist, mithilfe der CREATE AGGREGATE-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="224d5-112">Create the user-defined aggregate that references the registered assembly using the CREATE AGGREGATE statement.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="224d5-113">Bei der Bereitstellung eines SQL Server-Projekts in [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] wird eine Assembly in der Datenbank registriert, die für das Projekt angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="224d5-113">Deploying a SQL Server Project in [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] registers an assembly in the database that was specified for the project.</span></span> <span data-ttu-id="224d5-114">Beim Bereitstellen des Projekts wird in der Datenbank auch ein benutzerdefiniertes Aggregat für alle Klassendefinitionen erstellt, die mit dem `SqlUserDefinedAggregate`-Attribut versehen sind.</span><span class="sxs-lookup"><span data-stu-id="224d5-114">Deploying the project also creates a user-defined aggregate in the database for all class definitions annotated with the `SqlUserDefinedAggregate` attribute.</span></span> <span data-ttu-id="224d5-115">Weitere Informationen finden Sie unter [Deploying CLR Database Objects](../clr-integration/deploying-clr-database-objects.md).</span><span class="sxs-lookup"><span data-stu-id="224d5-115">For more information, see [Deploying CLR Database Objects](../clr-integration/deploying-clr-database-objects.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="224d5-116">Die Funktion zum Ausführen von CLR-Code ist in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="224d5-116">The ability of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to execute CLR code is off by default.</span></span> <span data-ttu-id="224d5-117">Sie können Datenbankobjekte, die auf verwaltete Codemodule verweisen, erstellen, ändern oder löschen; diese Verweise werden jedoch nur dann in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgeführt, wenn die [clr enabled](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) -Option mithilfe von [sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="224d5-117">You can create, alter and drop database objects that reference managed code modules, but these references will not execute in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unless the [clr enabled Option](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) is enabled using [sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql).</span></span>  
  
 <span data-ttu-id="224d5-118">**So erstellen, ändern oder löschen Sie eine Assembly**</span><span class="sxs-lookup"><span data-stu-id="224d5-118">**To create, modify, or drop an assembly**</span></span>  
  
-   [<span data-ttu-id="224d5-119">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="224d5-119">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-assembly-transact-sql)  
  
-   [<span data-ttu-id="224d5-120">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="224d5-120">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-assembly-transact-sql)  
  
-   [<span data-ttu-id="224d5-121">DROP ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="224d5-121">DROP ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-assembly-transact-sql)  
  
 <span data-ttu-id="224d5-122">**So erstellen Sie ein benutzerdefiniertes Aggregat**</span><span class="sxs-lookup"><span data-stu-id="224d5-122">**To create a user-defined aggregate**</span></span>  
  
-   [<span data-ttu-id="224d5-123">CREATE AGGREGATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="224d5-123">CREATE AGGREGATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-aggregate-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="224d5-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="224d5-124">See Also</span></span>  
 [<span data-ttu-id="224d5-125">Programmierkonzepte für die Integration der Common Language Runtime &#40;CLR&#41;</span><span class="sxs-lookup"><span data-stu-id="224d5-125">Common Language Runtime &#40;CLR&#41; Integration Programming Concepts</span></span>](../clr-integration/common-language-runtime-clr-integration-programming-concepts.md)  
  
  
