---
title: Benutzerdefinierte CLR-Typen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- validation [CLR integration]
- types [CLR integration]
- UserDefined serialization format [CLR integration]
- null values [CLR integration]
- serialization
- Native serialization format [CLR integration]
- databases [CLR integration]
- building database objects [CLR integration], user-defined types
- user-defined types [CLR integration]
- common language runtime [SQL Server], user-defined types
- UDTs [CLR integration]
- database objects [CLR integration], user-defined types
- turning on CLR functionality
- customizing UDT expression return types [CLR integration]
- UDTs [CLR integration], about UDTs
- comparing UDT values
- annotations [CLR integration]
- user-defined types [CLR integration], about UDTs
- variables [CLR integration]
- invoking UDT methods
- indexes [CLR integration]
ms.assetid: 27c4889b-c543-47a8-a630-ad06804f92df
author: rothja
ms.author: jroth
ms.openlocfilehash: e4e19323eeac9e0a1148924543f71aa7de5619b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622706"
---
# <a name="clr-user-defined-types"></a><span data-ttu-id="4a90c-102">Benutzerdefinierte CLR-Typen</span><span class="sxs-lookup"><span data-stu-id="4a90c-102">CLR User-Defined Types</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4a90c-103">ermöglicht das Erstellen von Datenbankobjekten, die für eine Assembly programmiert sind, die in der CLR (Common Language Runtime) von .NET Framework erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="4a90c-103">gives you the ability to create database objects that are programmed against an assembly created in the.NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="4a90c-104">Zu den Datenbankobjekten, die das umfangreiche Programmierungsmodell der CLR nutzen können, zählen Trigger, gespeicherte Prozeduren, Funktionen, Aggregatfunktionen und Typen.</span><span class="sxs-lookup"><span data-stu-id="4a90c-104">Database objects that can take advantage of the rich programming model provided by the CLR include triggers, stored procedures, functions, aggregate functions, and types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4a90c-105">Die Möglichkeit zum Ausführen von CLR-Code ist in standardmäßig auf OFF festgelegt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4a90c-105">The ability to execute CLR code is set to OFF by default in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4a90c-106">Die CLR kann mithilfe der gespeicherten System Prozedur **sp_configure** aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="4a90c-106">The CLR can be enabled by using the **sp_configure** system stored procedure.</span></span>  
  
 <span data-ttu-id="4a90c-107">Ab [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] können Sie benutzerdefinierte Typen (User-Defined Types, UDTs) verwenden, um das skalare Typsystem des Servers zu erweitern und so die Speicherung von CLR-Objekten in einer Datenbank zu ermöglichen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4a90c-107">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], you can use user-defined types (UDTs) to extend the scalar type system of the server, enabling storage of CLR objects in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="4a90c-108">UDTs können mehrere Elemente enthalten und Verhalten zeigen, das sie von den herkömmlichen Aliasdatentypen unterscheidet, die aus einem einzelnen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Systemdatentyp bestehen.</span><span class="sxs-lookup"><span data-stu-id="4a90c-108">UDTs can contain multiple elements and can have behaviors, differentiating them from the traditional alias data types which consist of a single [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system data type.</span></span>  
  
 <span data-ttu-id="4a90c-109">Da das System auf UDTs als Ganzes zugreift, kann sich ihre Verwendung für komplexe Datentypen negativ auf die Leistung auswirken.</span><span class="sxs-lookup"><span data-stu-id="4a90c-109">Because UDTs are accessed by the system as a whole, their use for complex data types may negatively impact performance.</span></span> <span data-ttu-id="4a90c-110">Komplexe Daten werden im Allgemeinen am besten mit herkömmlichen Zeilen und Tabellen modelliert.</span><span class="sxs-lookup"><span data-stu-id="4a90c-110">Complex data is generally best modeled using traditional rows and tables.</span></span> <span data-ttu-id="4a90c-111">UDTs sind in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] für folgende Zwecke geeignet:</span><span class="sxs-lookup"><span data-stu-id="4a90c-111">UDTs in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are well suited to the following:</span></span>  
  
-   <span data-ttu-id="4a90c-112">Datum, Zeit, Währung und erweiterte numerische Typen</span><span class="sxs-lookup"><span data-stu-id="4a90c-112">Date, time, currency, and extended numeric types</span></span>  
  
-   <span data-ttu-id="4a90c-113">Geospatial-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="4a90c-113">Geospatial applications</span></span>  
  
-   <span data-ttu-id="4a90c-114">Codierte oder verschlüsselte Daten</span><span class="sxs-lookup"><span data-stu-id="4a90c-114">Encoded or encrypted data</span></span>  
  
 <span data-ttu-id="4a90c-115">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] besteht der Prozess der UDTs-Entwicklung aus den folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="4a90c-115">The process of developing UDTs in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consists of the following steps:</span></span>  
  
1.  <span data-ttu-id="4a90c-116">**Codieren und erstellen Sie die Assembly, die den UDT definiert.**</span><span class="sxs-lookup"><span data-stu-id="4a90c-116">**Code and build the assembly that defines the UDT.**</span></span> <span data-ttu-id="4a90c-117">UDTs werden in einer beliebigen, von der .NET Framework-CLR (Common Language Runtime) unterstützten Sprache definiert, die überprüfbaren Code generiert.</span><span class="sxs-lookup"><span data-stu-id="4a90c-117">UDTs are defined using any of the languages supported by the.NET Framework common language runtime (CLR) that produce verifiable code.</span></span> <span data-ttu-id="4a90c-118">Dies umfasst Visual c# und Visual Basic .net.</span><span class="sxs-lookup"><span data-stu-id="4a90c-118">This includes Visual C# and Visual Basic .NET.</span></span> <span data-ttu-id="4a90c-119">Die Daten werden in Feldern und Eigenschaften einer .NET Framework-Klasse oder -Struktur verfügbar gemacht. Das Verhalten wird durch die Methoden der Klasse oder Struktur definiert.</span><span class="sxs-lookup"><span data-stu-id="4a90c-119">The data is exposed as fields and properties of a .NET Framework class or structure, and behaviors are defined by methods of the class or structure.</span></span>  
  
2.  <span data-ttu-id="4a90c-120">**Registrieren Sie die Assembly.**</span><span class="sxs-lookup"><span data-stu-id="4a90c-120">**Register the assembly.**</span></span> <span data-ttu-id="4a90c-121">UDTs können über die Visual Studio-Benutzeroberfläche in einem Datenbankprojekt oder mit der[!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung CREATE ASSEMBLY bereitgestellt werden, die die Assembly, die die Klasse oder Struktur enthält, in eine Datenbank kopiert.</span><span class="sxs-lookup"><span data-stu-id="4a90c-121">UDTs can be deployed through the Visual Studio user interface in a database project, or by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE ASSEMBLY statement, which copies the assembly containing the class or structure into a database.</span></span>  
  
3.  <span data-ttu-id="4a90c-122">**Erstellen Sie den UDT in SQL Server.**</span><span class="sxs-lookup"><span data-stu-id="4a90c-122">**Create the UDT in SQL Server.**</span></span> <span data-ttu-id="4a90c-123">Sobald eine Assembly in eine Hostdatenbank geladen wurde, erstellen Sie einen UDT mit der  [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung CREATE TYPE, und machen die Elemente der Klasse oder Struktur als Elemente des UDT verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4a90c-123">Once an assembly is loaded into a host database, you use the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TYPE statement to create a UDT and expose the members of the class or structure as members of the UDT.</span></span> <span data-ttu-id="4a90c-124">UDTs sind nur im Kontext einer einzelnen Datenbank vorhanden und weisen nach der Registrierung keine Abhängigkeiten mehr von den externen Dateien auf, aus denen sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="4a90c-124">UDTs exist only in the context of a single database, and, once registered, have no dependencies on the external files from which they were created.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4a90c-125">Vor [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] wurden aus .NET Framework-Assemblys erstellte UDTs nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4a90c-125">Before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], UDTs created from .NET Framework assemblies were not supported.</span></span> <span data-ttu-id="4a90c-126">Sie können jedoch weiterhin [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Alias Datentypen verwenden, indem Sie **sp_addtype**verwenden.</span><span class="sxs-lookup"><span data-stu-id="4a90c-126">However, you can still use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alias data types by using **sp_addtype**.</span></span> <span data-ttu-id="4a90c-127">Die CREATE TYPE-Syntax kann zum Erstellen sowohl von systemeigenen, benutzerdefinierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datentypen als auch UDTs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4a90c-127">The CREATE TYPE syntax can be used for creating both native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user-defined data types and UDTs.</span></span>  
  
4.  <span data-ttu-id="4a90c-128">**Erstellen von Tabellen, Variablen oder Parametern mit dem UDT** Ab [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] kann ein benutzerdefinierter Typ als Spaltendefinition einer Tabelle, als Variable in einem [!INCLUDE[tsql](../../includes/tsql-md.md)] Batch oder als Argument einer [!INCLUDE[tsql](../../includes/tsql-md.md)] Funktion oder gespeicherten Prozedur verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4a90c-128">**Create tables, variables, or parameters using the UDT** Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], a user-defined type can be used as the column definition of a table, as a variable in a [!INCLUDE[tsql](../../includes/tsql-md.md)] batch, or as an argument of a [!INCLUDE[tsql](../../includes/tsql-md.md)] function or stored procedure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4a90c-129">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4a90c-129">In This Section</span></span>  
 [<span data-ttu-id="4a90c-130">Erstellen eines benutzerdefinierten Typs</span><span class="sxs-lookup"><span data-stu-id="4a90c-130">Creating a User-Defined Type</span></span>](creating-user-defined-types.md)  
 <span data-ttu-id="4a90c-131">Beschreibt das Erstellen von UDTs.</span><span class="sxs-lookup"><span data-stu-id="4a90c-131">Describes how to create UDTs.</span></span>  
  
 [<span data-ttu-id="4a90c-132">Registrieren benutzerdefinierter Typen in SQL Server</span><span class="sxs-lookup"><span data-stu-id="4a90c-132">Registering User-Defined Types in SQL Server</span></span>](registering-user-defined-types-in-sql-server.md)  
 <span data-ttu-id="4a90c-133">Beschreibt, wie UDTs in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] registriert und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="4a90c-133">Describes how to register and manage UDTs in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="4a90c-134">Arbeiten mit benutzerdefinierten Typen in SQL Server</span><span class="sxs-lookup"><span data-stu-id="4a90c-134">Working with User-Defined Types in SQL Server</span></span>](working-with-user-defined-types-in-sql-server.md)  
 <span data-ttu-id="4a90c-135">Beschreibt das Erstellen von Abfragen mit UDTs.</span><span class="sxs-lookup"><span data-stu-id="4a90c-135">Describes how to create queries using UDTs.</span></span>  
  
 [<span data-ttu-id="4a90c-136">Zugreifen auf benutzerdefinierte Typen in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4a90c-136">Accessing User-Defined Types in ADO.NET</span></span>](accessing-user-defined-types-in-ado-net.md)  
 <span data-ttu-id="4a90c-137">Beschreibt die Verwendung von UDTs mit dem .NET Framework-Datenanbieter für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="4a90c-137">Describes how to work with UDTs using the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in ADO.NET.</span></span>  
  
  
