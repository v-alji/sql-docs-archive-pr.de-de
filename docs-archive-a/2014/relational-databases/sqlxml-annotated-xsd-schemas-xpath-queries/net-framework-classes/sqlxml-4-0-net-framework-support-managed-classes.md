---
title: Verwaltete SQLXML-Klassen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- .NET Framework [SQLXML], Managed Classes
- SQL Server .NET Data Provider
- Managed Classes [SQLXML], about managed classes
- providers [SQLXML], SQL Server .NET Data Provider
- data providers [SQLXML], SQL Server .NET Data Provider
- Managed Classes [SQLXML]
- XML [SQLXML]
- SQLXML Managed Classes
- providers [SQLXML], SQLXML Managed Classes
- data providers [SQLXML], SQLXML Managed Classes
- SQLXML, Managed Classes
ms.assetid: 73a5faeb-dabf-4895-acb5-a9651b646065
author: rothja
ms.author: jroth
ms.openlocfilehash: bb8d2d4f2d2fc512901e4ad37f0e46cf696b9475
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607609"
---
# <a name="sqlxml-managed-classes"></a><span data-ttu-id="f8348-102">SQLXML, verwaltete Klassen</span><span class="sxs-lookup"><span data-stu-id="f8348-102">SQLXML Managed Classes</span></span>
  <span data-ttu-id="f8348-103">Verwaltete [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML-Klassen machen die Funktionalität von SQLXML 4.0 im [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f8348-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML Managed Classes exposes the functionality of SQLXML 4.0 inside the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span></span> <span data-ttu-id="f8348-104">Mit verwalteten SQLXML-Klassen können Sie eine Anwendung in C# schreiben, um von einer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Instanz auf XML-Daten zuzugreifen, die Daten in die .NET Framework-Umgebung einzubinden, die Daten zu verarbeiten und die Updates zur Anwendung als DiffGram an [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] zurückzusenden.</span><span class="sxs-lookup"><span data-stu-id="f8348-104">With SQLXML Managed Classes, you can write a C# application to access XML data from an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], bring the data into the .NET Framework environment, process the data, and send the updates back to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as a DiffGram to apply the updates.</span></span> <span data-ttu-id="f8348-105">Beim Anwenden von Updates auf eine [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Datenbank, die verwaltete SQLXML-Klassen verwendet, müssen Sie ein Zuordnungsschema verwenden.</span><span class="sxs-lookup"><span data-stu-id="f8348-105">You must use a mapping schema when applying updates to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database using SQLXML Managed Classes.</span></span> <span data-ttu-id="f8348-106">Ein funktionierendes Beispiel finden Sie unter [zugreifen auf die SQLXML-Funktionalität in der .NET-Umgebung](accessing-sqlxml-functionality-in-the-net-environment.md).</span><span class="sxs-lookup"><span data-stu-id="f8348-106">For a working sample, see [Accessing SQLXML Functionality in the .NET Environment](accessing-sqlxml-functionality-in-the-net-environment.md).</span></span>  
  
 <span data-ttu-id="f8348-107">Um die verwalteten SQLXML-Klassen mit SQLXML 4.0 zu verwenden, müssen Sie Microsoft Visual Studio installieren.</span><span class="sxs-lookup"><span data-stu-id="f8348-107">To use the SQLXML Managed Classes with SQLXML 4.0, you must install Microsoft Visual Studio.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f8348-108">.NET Framework umfasst den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .NET-Datenanbieter.</span><span class="sxs-lookup"><span data-stu-id="f8348-108">The .NET Framework includes the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .NET Data Provider.</span></span> <span data-ttu-id="f8348-109">Mit diesem Anbieter kann von der .NET-Umgebung auf [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] zugegriffen werden. Allerdings kann er nur herkömmliche SQL-Abfragen verarbeiten (d. h. Abfragen relationaler Datenbanken mit Ausnahme von FOR XML-Abfragen).</span><span class="sxs-lookup"><span data-stu-id="f8348-109">This provider can be used to access [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] from the .NET environment; however, it can handle only traditional SQL queries (that is, relational database queries with the exception of FOR XML queries).</span></span> <span data-ttu-id="f8348-110">Sie können weder XML-Vorlagen noch serverseitige XPath-Abfragen in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ausführen.</span><span class="sxs-lookup"><span data-stu-id="f8348-110">You cannot execute XML templates or the server-side XPath queries in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f8348-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f8348-111">In This Section</span></span>  
 [<span data-ttu-id="f8348-112">Objektmodell der verwalteten SQLXML-Klassen</span><span class="sxs-lookup"><span data-stu-id="f8348-112">SQLXML Managed Classes Object Model</span></span>](../../../database-engine/dev-guide/sqlxml-managed-classes-object-model.md)  
 <span data-ttu-id="f8348-113">Dokumentiert verwaltete SQLXML-Klassen und ihre Eigenschaften und Methoden.</span><span class="sxs-lookup"><span data-stu-id="f8348-113">Documents SQLXML Managed Classes and their properties and methods.</span></span>  
  
 [<span data-ttu-id="f8348-114">Verwenden der verwalteten SQLXML-Klassen</span><span class="sxs-lookup"><span data-stu-id="f8348-114">Using the SQLXML Managed Classes</span></span>](sqlxml-4-0-net-framework-support-managed-classes.md)  
 <span data-ttu-id="f8348-115">Liefert Beispiele für die Verwendung verwalteter SQLXML-Klassen.</span><span class="sxs-lookup"><span data-stu-id="f8348-115">Provides examples of using SQLXML Managed Classes.</span></span>  
  
  
