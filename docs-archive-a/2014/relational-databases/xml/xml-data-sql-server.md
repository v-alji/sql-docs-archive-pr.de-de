---
title: XML-Daten (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XML [SQL Server]
- XML [SQL Server], about XML
ms.assetid: 6a1793c9-9856-485c-aac5-88fda62f61a8
author: rothja
ms.author: jroth
ms.openlocfilehash: 48ddec1de8492c86aecfd80ea960c4a01673c24f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609751"
---
# <a name="xml-data-sql-server"></a><span data-ttu-id="83cde-102">XML-Daten (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="83cde-102">XML Data (SQL Server)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="83cde-103">bietet eine leistungsstarke Plattform zum Entwickeln umfassender Anwendungen zur Verwaltung halbstrukturierter Daten.</span><span class="sxs-lookup"><span data-stu-id="83cde-103">provides a powerful platform for developing rich applications for semi-structured data management.</span></span> <span data-ttu-id="83cde-104">Alle Komponenten in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bieten XML-Unterstützung in folgenden Punkten:</span><span class="sxs-lookup"><span data-stu-id="83cde-104">Support for XML is integrated into all the components in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and includes the following:</span></span>  
  
-   <span data-ttu-id="83cde-105">Der `xml`-Datentyp.</span><span class="sxs-lookup"><span data-stu-id="83cde-105">The `xml` data type.</span></span> <span data-ttu-id="83cde-106">XML-Werte können systemeigen in einer `xml`-Datentypspalte gespeichert werden, die gemäß einer Auflistung von XML-Schemas typisiert oder nicht typisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="83cde-106">XML values can be stored natively in an `xml` data type column that can be typed according to a collection of XML schemas, or left untyped.</span></span> <span data-ttu-id="83cde-107">Sie können die XML-Spalte indizieren.</span><span class="sxs-lookup"><span data-stu-id="83cde-107">You can index the XML column.</span></span>  
  
-   <span data-ttu-id="83cde-108">Die Möglichkeit, XQuery-Abfragen für in Spalten und Variablen gespeicherte XML-Daten vom `xml`-Typ anzugeben.</span><span class="sxs-lookup"><span data-stu-id="83cde-108">The ability to specify an XQuery query against XML data stored in columns and variables of the `xml` type.</span></span>  
  
-   <span data-ttu-id="83cde-109">Erweiterungen zu OPENROWSET, um das Massenladen von XML-Daten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="83cde-109">Enhancements to OPENROWSET to allow bulk loading of XML data.</span></span>  
  
-   <span data-ttu-id="83cde-110">Die FOR XML-Klausel zum Abrufen relationaler Daten im XML-Format.</span><span class="sxs-lookup"><span data-stu-id="83cde-110">The FOR XML clause, to retrieve relational data in XML format.</span></span>  
  
-   <span data-ttu-id="83cde-111">Die OPENXML-Funktion zum Abrufen von XML-Daten im relationalen Format.</span><span class="sxs-lookup"><span data-stu-id="83cde-111">The OPENXML function, to retrieve XML data in relational format.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="83cde-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="83cde-112">In This Section</span></span>  
 [<span data-ttu-id="83cde-113">XML-Datentyp und -Spalten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="83cde-113">XML Data Type and Columns &#40;SQL Server&#41;</span></span>](xml-data-type-and-columns-sql-server.md)  
 [<span data-ttu-id="83cde-114">XML-Indizes &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="83cde-114">XML Indexes &#40;SQL Server&#41;</span></span>](xml-indexes-sql-server.md)  
 [<span data-ttu-id="83cde-115">XML-Schemaauflistungen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="83cde-115">XML Schema Collections &#40;SQL Server&#41;</span></span>](xml-schema-collections-sql-server.md)  
 [<span data-ttu-id="83cde-116">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="83cde-116">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
 [<span data-ttu-id="83cde-117">OPENXML &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="83cde-117">OPENXML &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/openxml-transact-sql)  
  
## <a name="related-content"></a><span data-ttu-id="83cde-118">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="83cde-118">Related Content</span></span>  
 [<span data-ttu-id="83cde-119">Beispiele für den Massenimport und -export von XML-Dokumenten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="83cde-119">Examples of Bulk Import and Export of XML Documents &#40;SQL Server&#41;</span></span>](../import-export/examples-of-bulk-import-and-export-of-xml-documents-sql-server.md)  
 [<span data-ttu-id="83cde-120">XQuery-Sprachreferenz &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="83cde-120">XQuery Language Reference &#40;SQL Server&#41;</span></span>](/sql/xquery/xquery-language-reference-sql-server)  
  
