---
title: Ausführen von Massen Laden von XML-Daten (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XML Bulk Load [SQLXML]
- bulk load [SQLXML]
- data insertions [SQLXML]
- SQLXML, bulk loading
- XSD schemas [SQLXML], XML Bulk Load
- XDR schemas [SQLXML], XML Bulk Load
- inserting data
ms.assetid: 3708b493-322e-4f3c-9b27-441d0c0ee346
author: rothja
ms.author: jroth
ms.openlocfilehash: ec540ff082b02fa43b9abd9f294752073eb68d5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695502"
---
# <a name="performing-bulk-load-of-xml-data-sqlxml-40"></a><span data-ttu-id="fb1dd-102">Ausführen von Massenladen von XML-Daten (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="fb1dd-102">Performing Bulk Load of XML Data (SQLXML 4.0)</span></span>
  <span data-ttu-id="fb1dd-103">XML-Massenladen ist ein eigenständiges COM-Objekt, mit dem Sie semistrukturierte XML-Daten in Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Tabellen laden können.</span><span class="sxs-lookup"><span data-stu-id="fb1dd-103">XML Bulk Load is a standalone COM object that allows you to load semistructured XML data into Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fb1dd-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="fb1dd-104">In This Section</span></span>  
 [<span data-ttu-id="fb1dd-105">Einführung in XML-Massen laden &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="fb1dd-105">Introduction to XML Bulk Load &#40;SQLXML 4.0&#41;</span></span>](introduction-to-xml-bulk-load-sqlxml-4-0.md)  
 <span data-ttu-id="fb1dd-106">Stellt allgemeine Informationen über das Massenladen von XML-Daten mit dem XML-Massenladen-Hilfsprogramm zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="fb1dd-106">Provides general information about bulk loading XML data with the XML Bulk Load utility.</span></span> <span data-ttu-id="fb1dd-107">Die Themen enthalten XML-Daten-Streaming und einen Vergleich zwischen transaktiv und nicht durchgeführten Massenladevorgängen.</span><span class="sxs-lookup"><span data-stu-id="fb1dd-107">Topics include XML data streaming and transacted vs. nontransacted bulk load operations.</span></span>  
  
 [<span data-ttu-id="fb1dd-108">Daten Satz Generierungsprozess &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="fb1dd-108">Record Generation Process &#40;SQLXML 4.0&#41;</span></span>](record-generation-process-sqlxml-4-0.md)  
 <span data-ttu-id="fb1dd-109">Beschreibt den Prozess und die Regeln, mit denen Datensätze für XML-Massenladen generiert werden.</span><span class="sxs-lookup"><span data-stu-id="fb1dd-109">Describes the process and rules by which records are generated for XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="fb1dd-110">Interpretation der Anmerkung &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="fb1dd-110">Annotation Interpretation &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sqlxml-4-0.md)  
 <span data-ttu-id="fb1dd-111">Beschreibt, wie XML-Massenladen Anmerkungen in XSD- und XDR-Schemas interpretiert.</span><span class="sxs-lookup"><span data-stu-id="fb1dd-111">Describes how XML Bulk Load interprets annotations in XSD and XDR schemas.</span></span>  
  
 [<span data-ttu-id="fb1dd-112">SQL Server XML-Massen laden-Objektmodell &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="fb1dd-112">SQL Server XML Bulk Load Object Model &#40;SQLXML 4.0&#41;</span></span>](sql-server-xml-bulk-load-object-model-sqlxml-4-0.md)  
 <span data-ttu-id="fb1dd-113">Beschreibt das SQLXMLBulkLoad-Objekt und dessen Methoden und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="fb1dd-113">Describes the SQLXMLBulkLoad object and its methods and properties.</span></span>  
  
 [<span data-ttu-id="fb1dd-114">Beispiele für XML-Massen laden &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="fb1dd-114">XML Bulk Load Examples &#40;SQLXML 4.0&#41;</span></span>](xml-bulk-load-examples-sqlxml-4-0.md)  
 <span data-ttu-id="fb1dd-115">Stellt Beispielcode bereit, der XML-Massenladen verwendet.</span><span class="sxs-lookup"><span data-stu-id="fb1dd-115">Provides example code that uses XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="fb1dd-116">Datentypen und XML-Massen Ladeverhalten &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="fb1dd-116">Data Types and XML Bulk Load Behavior &#40;SQLXML 4.0&#41;</span></span>](data-types-and-xml-bulk-load-behavior-sqlxml-4-0.md)  
 <span data-ttu-id="fb1dd-117">Beschreibt XML-Massenladenverhalten mit verschiedenen Typen in XSD und XDR.</span><span class="sxs-lookup"><span data-stu-id="fb1dd-117">Describes XML Bulk Load Behavior with different types in XSD and XDR.</span></span>  
  
 [<span data-ttu-id="fb1dd-118">Richtlinien und Einschränkungen von XML-Massen laden &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="fb1dd-118">Guidelines and Limitations of XML Bulk Load &#40;SQLXML 4.0&#41;</span></span>](guidelines-and-limitations-of-xml-bulk-load-sqlxml-4-0.md)  
 <span data-ttu-id="fb1dd-119">Führt einige Punkte auf, die beim Arbeiten mit XML-Massenladen zu beachten sind.</span><span class="sxs-lookup"><span data-stu-id="fb1dd-119">Lists some issues to be aware of when working with XML Bulk Load.</span></span>  
  
  
