---
title: Programmier Konzepte von SQLXML 4,0 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, about SQLXML
- SQLXML
ms.assetid: 5a11cda2-b8a3-4453-848f-641afdaa7024
author: rothja
ms.author: jroth
ms.openlocfilehash: 90a383d2a12e073f262d24a94abe1b094509713c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619705"
---
# <a name="sqlxml-40-programming-concepts"></a><span data-ttu-id="66c7e-102">SQLXML 4.0-Programmierkonzepte</span><span class="sxs-lookup"><span data-stu-id="66c7e-102">SQLXML 4.0 Programming Concepts</span></span>
  <span data-ttu-id="66c7e-103">SQLXML 3.0 wurde als Webversion angeboten, um zusätzliche clientseitige XML-Funktionalitäten und Erweiterungen zu bestehenden Funktionen wie XSD-Schemas mit Anmerkungen, XML-Massenladen, Unterstützung für Webdienste (SOAP) und Updategrams bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="66c7e-103">SQLXML 3.0 was offered as a Web release to provide additional client-side XML functionality and enhancements to existing features, such as annotated XSD schemas, XML bulk load, Web services (SOAP) support, and updategrams.</span></span>  
  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="66c7e-104">führt Version 4.0 von SQLXML ein, die dieselbe Funktionalität wie SQLXML 3.0 bereitstellt. Darüber hinaus bietet sie zusätzliche Updates, um mit neuen Funktionen, die in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] eingeführt wurden, zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="66c7e-104">introduced SQLXML 4.0, which continues to deliver the same functionality as SQLXML 3.0 plus additional updates provided to accommodate new features introduced with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="66c7e-105">Dieser Abschnitt enthält Informationen zur SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="66c7e-105">This section provides information about SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="66c7e-106">SQLXML ist in SQL Server nicht installiert</span><span class="sxs-lookup"><span data-stu-id="66c7e-106">SQLXML Is Not Installed in SQL Server</span></span>](sqlxml-is-not-installed-in-sql-server.md)  
 <span data-ttu-id="66c7e-107">Beschreibt die Installation von SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="66c7e-107">Describes how to install SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="66c7e-108">Neues in SQLXML 4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="66c7e-108">What's New in SQLXML 4.0 SP1</span></span>](what-s-new-in-sqlxml-4-0-sp1.md)  
 <span data-ttu-id="66c7e-109">Beschreibt die Updates und die Erweiterungen in SQLXML 4.0 und stellt Links zu relevanten Themen in dieser Dokumentation bereit.</span><span class="sxs-lookup"><span data-stu-id="66c7e-109">Describes the updates and enhancements in SQLXML 4.0, and provides links to relevant topics in this documentation.</span></span>  
  
 [<span data-ttu-id="66c7e-110">Verwenden von ADO zum Ausführen von SQLXML 4.0-Abfragen</span><span class="sxs-lookup"><span data-stu-id="66c7e-110">Using ADO to Execute SQLXML 4.0 Queries</span></span>](using-ado-to-execute-sqlxml-4-0-queries.md)  
 <span data-ttu-id="66c7e-111">Beschreibt, wie ADO für SQLXML-Abfragen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="66c7e-111">Describes how to use ADO for SQLXML queries.</span></span> <span data-ttu-id="66c7e-112">ADO nimmt in SQLXML 4.0 einen wichtigeren Platz ein als in vorherigen Versionen.</span><span class="sxs-lookup"><span data-stu-id="66c7e-112">ADO is more prominent in SQLXML 4.0 than in previous versions.</span></span>  
  
 [<span data-ttu-id="66c7e-113">XML-Datentypunterstützung für SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="66c7e-113">xml Data Type Support in SQLXML 4.0</span></span>](xml-data-type-support-in-sqlxml-4-0.md)  
 <span data-ttu-id="66c7e-114">Beschreibt die Unterstützung für den XML-Datentyp, der in SQLXML 4.0 hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="66c7e-114">Describes the support for the xml data type that has been added for SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="66c7e-115">Anforderungen zum Ausführen von SQLXML-Beispielen</span><span class="sxs-lookup"><span data-stu-id="66c7e-115">Requirements for Running SQLXML Examples</span></span>](requirements-for-running-sqlxml-examples.md)  
 <span data-ttu-id="66c7e-116">Beschreibt die Anforderungen zum Erstellen von funktionstüchtigen Beispielen aus den bereitgestellten SQLXML-Beispielen.</span><span class="sxs-lookup"><span data-stu-id="66c7e-116">Describe the requirements for creating working samples from the SQLXML examples provided.</span></span>  
  
 [<span data-ttu-id="66c7e-117">Client seitige und Server seitige Formatierung &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="66c7e-117">Client-side and Server-side Formatting &#40;SQLXML 4.0&#41;</span></span>](formatting/client-side-and-server-side-formatting-sqlxml-4-0.md)  
 <span data-ttu-id="66c7e-118">Liefert Informationen über die clientseitige Formatierung im Vergleich zur serverseitigen Formatierung sowie den FOR XML-Befehl zum Konstruieren von XML-Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="66c7e-118">Provides information about and comparisons of client-side and server-side formatting, including the FOR XML command for constructing XML documents.</span></span>  
  
 [<span data-ttu-id="66c7e-119">XSD-Schemas mit Anmerkungen in SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="66c7e-119">Annotated XSD Schemas in SQLXML 4.0</span></span>](annotated-xsd-schemas/annotated-xsd-schemas-in-sqlxml-4-0.md)  
 <span data-ttu-id="66c7e-120">Enthält Informationen zum Verwenden von XSD-Schemas mit Anmerkungen in SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="66c7e-120">Provides information about using annotated XSD schemas in SQLXML 4.0.</span></span> <span data-ttu-id="66c7e-121">Stellt außerdem Informationen über XDR-Schemas mit Anmerkungen zur Verwendung in älteren Anwendungen bereit.</span><span class="sxs-lookup"><span data-stu-id="66c7e-121">Also provides information about annotated XDR schemas for use in legacy applications.</span></span>  
  
 [<span data-ttu-id="66c7e-122">Verwenden von XPath-Abfragen in SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="66c7e-122">Using XPath Queries in SQLXML 4.0</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/using-xpath-queries-in-sqlxml-4-0.md)  
 <span data-ttu-id="66c7e-123">Beschreibt, wie mit einer Teilmenge der Xpath-Sprache die von dem mit Anmerkungen versehenen XSD-Schema erstellten XML-Sichten abgefragt werden können und liefert Beispiele dazu.</span><span class="sxs-lookup"><span data-stu-id="66c7e-123">Describes how to use a subset of the XPath language to query the XML views created by an annotated XSD schema, and provides examples.</span></span>  
  
 [<span data-ttu-id="66c7e-124">Verwenden von Updategrams zum Ändern von Daten in SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="66c7e-124">Using Updategrams to Modify Data in SQLXML 4.0</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/using-updategrams-to-modify-data-in-sqlxml-4-0.md)  
 <span data-ttu-id="66c7e-125">Stellt Informationen über Updategrams bereit, die Daten in einer Datenbank ändern, indem sie mit den XML-Sichten verwendet werden, die von den mit Anmerkungen versehenen XSD- oder XDR-Schemas erzeugt wurden.</span><span class="sxs-lookup"><span data-stu-id="66c7e-125">Provides information about updategrams, which modify data in a database by working against the XML views provided by XSD (or XDR) annotated schemas.</span></span>  
  
 [<span data-ttu-id="66c7e-126">Ausführen von Massenladen von XML-Daten &#40;SQLXML 4.0&#41;</span><span class="sxs-lookup"><span data-stu-id="66c7e-126">Performing Bulk Load of XML Data &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md)  
 <span data-ttu-id="66c7e-127">Beschreibt den XML-Massenladevorgang in SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="66c7e-127">Describes how to bulk load XML in SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="66c7e-128">SQLXML 4.0 Data Access Components</span><span class="sxs-lookup"><span data-stu-id="66c7e-128">SQLXML 4.0 Data Access Components</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/data-access-components-provider/sqlxml-4-0-data-access-components-sqlxmloledb-provider.md)  
 <span data-ttu-id="66c7e-129">Dokumentiert den SQLXMLOLEDB-Anbieter und stellt Links zu anderen SQLXML 4.0-Datenzugriffskomponenten bereit.</span><span class="sxs-lookup"><span data-stu-id="66c7e-129">Documents the SQLXMLOLEDB Provider and provides links to other SQLXML 4.0 data access components.</span></span>  
  
 [<span data-ttu-id="66c7e-130">SQLXML 4.0 .NET Framework-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="66c7e-130">SQLXML 4.0 .NET Framework Support</span></span>](../../database-engine/dev-guide/sqlxml-4-0-net-framework-support.md)  
 <span data-ttu-id="66c7e-131">Beschreibt die SQLXML 4.0-Unterstützung für .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="66c7e-131">Describes the SQLXML 4.0 support for the .NET Framework.</span></span>  
  
 [<span data-ttu-id="66c7e-132">Zwischenspeichern von Vorlagen, XSL und Schemas &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="66c7e-132">Caching Templates, XSL, and Schemas &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/caching-templates-xml-schemas/caching-templates-xsl-and-schemas-sqlxml-4-0.md)  
 <span data-ttu-id="66c7e-133">Beschreibt die in SQLXML zum Optimieren der Leistung bereitgestellte Zwischenspeicherfunktionalität.</span><span class="sxs-lookup"><span data-stu-id="66c7e-133">Describes the caching functionality provided in SQLXML to improve performance.</span></span>  
  
 [<span data-ttu-id="66c7e-134">Sicherheitsüberlegungen zu SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="66c7e-134">SQLXML 4.0 Security Considerations</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/security/sqlxml-4-0-security-considerations.md)  
 <span data-ttu-id="66c7e-135">Erläutert Sicherheitsprobleme in Bezug auf SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="66c7e-135">Discusses security issues relevant to SQLXML 4.0.</span></span>  
  
 [<span data-ttu-id="66c7e-136">Richtlinien und Einschränkungen von SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="66c7e-136">Guidelines and Limitations of SQLXML 4.0</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/guidelines-and-limitations-of-sqlxml-4-0.md)  
 <span data-ttu-id="66c7e-137">Listet Punkte auf, die bei der Arbeit mit SQLXML 4.0 berücksichtigt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="66c7e-137">Lists issues to remember when working with SQLXML 4.0.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66c7e-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="66c7e-138">See Also</span></span>  
 [<span data-ttu-id="66c7e-139">XML-Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="66c7e-139">XML Data &#40;SQL Server&#41;</span></span>](../xml/xml-data-sql-server.md)  
  
  
