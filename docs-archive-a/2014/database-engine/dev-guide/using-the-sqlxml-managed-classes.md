---
title: Verwenden der verwalteten SQLXML-Klassen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- sample applications [SQLXML]
- SQLXML Managed Classes, sample applications
- examples [SQLXML], managed classes
- Managed Classes [SQLXML], samples
ms.assetid: 3f021290-00ee-44e1-af4b-33d3ba8c6302
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 634a0e4110b13931201edd026ee95028cb94e859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701678"
---
# <a name="using-the-sqlxml-managed-classes"></a><span data-ttu-id="e20d2-102">Verwenden der verwalteten SQLXML-Klassen</span><span class="sxs-lookup"><span data-stu-id="e20d2-102">Using the SQLXML Managed Classes</span></span>
  <span data-ttu-id="e20d2-103">Dieser Abschnitt stellt Beispielanwendungen zur Verfügung, die veranschaulichen, wie die verwalteten [!INCLUDE[msCoName](../../includes/msconame-md.md)]-SQLXML-Klassen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e20d2-103">This section provides sample applications that demonstrate how to use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] SQLXML Managed Classes.</span></span>  
  
 <span data-ttu-id="e20d2-104">Informationen zum Zugreifen auf und Ändern von Daten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] innerhalb des [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework sowie zum Verwenden von DiffGrams zum Aktualisieren von Daten in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Tabellen finden Sie unter [zugreifen auf die SQLXML-Funktionalität in der .NET-Umgebung](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/accessing-sqlxml-functionality-in-the-net-environment.md).</span><span class="sxs-lookup"><span data-stu-id="e20d2-104">For information about accessing and modifying data in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] within the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework, and about using DiffGrams to update data in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables, see [Accessing SQLXML Functionality in the .NET Environment](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/accessing-sqlxml-functionality-in-the-net-environment.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e20d2-105">Sie können außerdem [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio-Anwendungen schreiben, um einen Massenladenvorgang für XML-Dokumente mit XML-Massenladen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e20d2-105">You can also write [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio applications to bulk load XML documents by using XML Bulk Load.</span></span> <span data-ttu-id="e20d2-106">Weitere Informationen finden Sie unter [Ausführen von Massen Laden von XML-Daten &#40;SQLXML 4,0&#41;](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="e20d2-106">For more information, see [Performing Bulk Load of XML Data &#40;SQLXML 4.0&#41;](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md).</span></span> <span data-ttu-id="e20d2-107">Sie müssen einen Verweis auf die XML-Massenladen-DLL (Xblkld4.dll) in der Anwendung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e20d2-107">You must add a reference to the XML Bulk Load DLL (Xblkld4.dll) in your application.</span></span> <span data-ttu-id="e20d2-108">Dies ist eine COM-DLL, für das Visual Studio .NET die Wrapperbibliothek automatisch erstellt.</span><span class="sxs-lookup"><span data-stu-id="e20d2-108">This is a COM DLL for which Visual Studio .NET automatically creates the wrapper library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e20d2-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e20d2-109">In This Section</span></span>  
 [<span data-ttu-id="e20d2-110">Ausführen von SQL-Abfragen &#40;verwalteten SQLXML-Klassen&#41;</span><span class="sxs-lookup"><span data-stu-id="e20d2-110">Executing SQL Queries &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-4-0-net-framework-support-managed-classes.md)  
  [<span data-ttu-id="e20d2-111">Ausführen von SQL-Abfragen mithilfe der 'ExecuteXMLReader'-Methode</span><span class="sxs-lookup"><span data-stu-id="e20d2-111">Executing SQL Queries by Using the ExecuteXMLReader Method</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-sql-queries-by-using-the-executexmlreader-method.md)  
  [<span data-ttu-id="e20d2-112">Verarbeiten von XML auf der Client Seite &#40;verwalteten SQLXML-Klassen&#41;</span><span class="sxs-lookup"><span data-stu-id="e20d2-112">Processing XML on the Client Side &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/processing-xml-on-the-client-side-sqlxml-managed-classes.md)  
  [<span data-ttu-id="e20d2-113">Ausführen von XPath-Abfragen &#40;verwalteten SQLXML-Klassen&#41;</span><span class="sxs-lookup"><span data-stu-id="e20d2-113">Executing XPath Queries &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-xpath-queries-sqlxml-managed-classes.md)  
  [<span data-ttu-id="e20d2-114">Ausführen von XPath-Abfragen mit Namespaces &#40;verwalteten SQLXML-Klassen&#41;</span><span class="sxs-lookup"><span data-stu-id="e20d2-114">Executing XPath Queries with Namespaces &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-xpath-queries-with-namespaces-sqlxml-managed-classes.md)  
  [<span data-ttu-id="e20d2-115">Ausführen von Vorlagendateien mit der 'CommandText'-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e20d2-115">Executing Template Files by Using the CommandText Property</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-template-files-by-using-the-commandtext-property.md)  
  [<span data-ttu-id="e20d2-116">Ausführen von Vorlagendateien mit der 'CommandStream'-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e20d2-116">Executing Template Files by Using the CommandStream Property</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/executing-template-files-by-using-the-commandstream-property.md)  
  [<span data-ttu-id="e20d2-117">Anwenden einer XSL-Transformation &#40;verwalteten SQLXML-Klassen&#41;</span><span class="sxs-lookup"><span data-stu-id="e20d2-117">Applying an XSL Transformation &#40;SQLXML Managed Classes&#41;</span></span>](../../relational-databases/sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/applying-an-xsl-transformation-sqlxml-managed-classes.md)  
  
