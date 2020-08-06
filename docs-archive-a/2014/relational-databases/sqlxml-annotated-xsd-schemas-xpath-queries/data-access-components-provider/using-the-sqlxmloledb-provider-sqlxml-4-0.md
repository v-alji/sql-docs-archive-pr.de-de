---
title: Verwenden des SQLXMLOLEDB-Anbieters (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- sample applications [SQLXML]
- SQLXMLOLEDB Provider, samples
- ClientSideXML property
ms.assetid: fbcefac5-29c9-478b-b0e0-d510b593f446
author: rothja
ms.author: jroth
ms.openlocfilehash: 74e3c53eecd657d610c2fe90e108e0290e9b05b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618603"
---
# <a name="using-the-sqlxmloledb-provider-sqlxml-40"></a><span data-ttu-id="38cd1-102">Verwenden des SQLXMLOLEDB-Anbieters (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="38cd1-102">Using the SQLXMLOLEDB Provider (SQLXML 4.0)</span></span>
  <span data-ttu-id="38cd1-103">Die Themen in diesem Abschnitt enthalten ADO-Beispielanwendungen, die die Verwendung SQLXMLOLEDB-Anbieter-spezifischer Eigenschaften veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="38cd1-103">The topics in this section provide ADO sample applications that illustrate the use of SQLXMLOLEDB Provider-specific properties.</span></span>  
  
## <a name="application-requirements-for-sqlxmloledb-40-provider"></a><span data-ttu-id="38cd1-104">Anwendungsanforderungen für SQLXMLOLEDB 4.0-Anbieter</span><span class="sxs-lookup"><span data-stu-id="38cd1-104">Application Requirements for SQLXMLOLEDB 4.0 Provider</span></span>  
 <span data-ttu-id="38cd1-105">Um funktionierende Beispiele, die SQLXMLOLEDB 4.0 verwenden, zu erstellen, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="38cd1-105">To create working samples that use SQLXMLOLEDB 4.0, you must do the following:</span></span>  
  
1.  <span data-ttu-id="38cd1-106">Erstellen Sie eine Microsoft Visual Basic .exe-Anwendung, und fügen Sie einen der folgenden Verweise hinzu:</span><span class="sxs-lookup"><span data-stu-id="38cd1-106">Create a Microsoft Visual Basic .exe application and add one of the following references:</span></span>  
  
    -   <span data-ttu-id="38cd1-107">Microsoft ActiveX Data Objects 2,6-Bibliothek</span><span class="sxs-lookup"><span data-stu-id="38cd1-107">Microsoft ActiveX Data Objects 2.6 Library</span></span>  
  
    -   <span data-ttu-id="38cd1-108">Microsoft ActiveX Data Objects 2,7-Bibliothek</span><span class="sxs-lookup"><span data-stu-id="38cd1-108">Microsoft ActiveX Data Objects 2.7 Library</span></span>  
  
    -   <span data-ttu-id="38cd1-109">Microsoft ActiveX Data Objects 2.8-Bibliothek</span><span class="sxs-lookup"><span data-stu-id="38cd1-109">Microsoft ActiveX Data Objects 2.8 Library</span></span>  
  
2.  <span data-ttu-id="38cd1-110">Stellen Sie SQLXML 4.0 und den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client bereit, und installieren Sie sie.</span><span class="sxs-lookup"><span data-stu-id="38cd1-110">Deploy and install SQLXML 4.0 and the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
     <span data-ttu-id="38cd1-111">Weitere Informationen finden Sie unter für die [Programmier Konzepte von SQLXML 4,0](../../sqlxml/sqlxml-4-0-programming-concepts.md) und [Installieren von SQL Server Native Client](../../native-client/applications/installing-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="38cd1-111">For more information, see on [SQLXML 4.0 Programming Concepts](../../sqlxml/sqlxml-4-0-programming-concepts.md) and [Installing SQL Server Native Client](../../native-client/applications/installing-sql-server-native-client.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="38cd1-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="38cd1-112">In This Section</span></span>  
 [<span data-ttu-id="38cd1-113">Ausführen von SQL-Abfragen &#40;SQLXMLOLEDB-Anbieters&#41;</span><span class="sxs-lookup"><span data-stu-id="38cd1-113">Executing SQL Queries &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-sql-queries-sqlxmloledb-provider.md)  
 <span data-ttu-id="38cd1-114">Veranschaulicht die Verwendung von ClientSideXML-und XML-Stamm Eigenschaften zum Ausführen von SQL-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="38cd1-114">Illustrates the use of the ClientSideXML and xml root properties to execute SQL queries.</span></span>  
  
 [<span data-ttu-id="38cd1-115">Ausführen von Vorlagen, die SQL-Abfragen &#40;SQLXMLOLEDB-Anbieter enthalten #d1</span><span class="sxs-lookup"><span data-stu-id="38cd1-115">Executing Templates That Contain SQL Queries &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-templates-that-contain-sql-queries-sqlxmloledb-provider.md)  
 <span data-ttu-id="38cd1-116">Veranschaulicht die Verwendung der ClientSideXML-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="38cd1-116">Illustrates the use of the ClientSideXML property.</span></span>  
  
 [<span data-ttu-id="38cd1-117">Ausführen von XPath-Abfragen &#40;SQLXMLOLEDB-Anbieters&#41;</span><span class="sxs-lookup"><span data-stu-id="38cd1-117">Executing XPath Queries &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-xpath-queries-sqlxmloledb-provider.md)  
 <span data-ttu-id="38cd1-118">Veranschaulicht die Verwendung der Eigenschaften ClientSideXML, Basispfad und Zuordnungsschema.</span><span class="sxs-lookup"><span data-stu-id="38cd1-118">Illustrates the use of the ClientSideXML, Base Path, and Mapping Schema properties.</span></span>  
  
 [<span data-ttu-id="38cd1-119">Ausführen von XPath-Abfragen mit Namespaces &#40;SQLXMLOLEDB-Anbieter&#41;</span><span class="sxs-lookup"><span data-stu-id="38cd1-119">Executing XPath Queries with Namespaces &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-xpath-queries-with-namespaces-sqlxmloledb-provider.md)  
 <span data-ttu-id="38cd1-120">Veranschaulicht, wie Namespace-qualifizierte Schemas abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="38cd1-120">Illustrates how to query against namespace-qualified schemas.</span></span>  
  
 [<span data-ttu-id="38cd1-121">Ausführen von Vorlagen, die XPath-Abfragen &#40;SQLXMLOLEDB-Anbieter enthalten #d1</span><span class="sxs-lookup"><span data-stu-id="38cd1-121">Executing Templates That Contain XPath Queries &#40;SQLXMLOLEDB Provider&#41;</span></span>](executing-templates-that-contain-xpath-queries-sqlxmloledb-provider.md)  
 <span data-ttu-id="38cd1-122">Veranschaulicht das Ausführen von Vorlagen mit SQL-Abfragen mithilfe der Eigenschaften ClientSideXML, Basispfad und Zuordnungsschema.</span><span class="sxs-lookup"><span data-stu-id="38cd1-122">Illustrates how to execute templates with SQL queries using the ClientSideXML, Base Path, and Mapping Schema properties.</span></span>  
  
 [<span data-ttu-id="38cd1-123">Anwenden einer XSL-Transformation &#40;SQLXMLOLEDB-Anbieters&#41;</span><span class="sxs-lookup"><span data-stu-id="38cd1-123">Applying an XSL Transformation &#40;SQLXMLOLEDB Provider&#41;</span></span>](applying-an-xsl-transformation-sqlxmloledb-provider.md)  
 <span data-ttu-id="38cd1-124">Veranschaulicht die Verwendung der Eigenschaften ClientSideXML und XSL beim Anwenden einer XSL-Transformation.</span><span class="sxs-lookup"><span data-stu-id="38cd1-124">Illustrates the use of the ClientSideXML and xsl properties in applying an XSL transformation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38cd1-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="38cd1-125">See Also</span></span>  
 [<span data-ttu-id="38cd1-126">Systemanforderungen für SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="38cd1-126">System Requirements for SQL Server Native Client</span></span>](../../native-client/system-requirements-for-sql-server-native-client.md)  
  
  
