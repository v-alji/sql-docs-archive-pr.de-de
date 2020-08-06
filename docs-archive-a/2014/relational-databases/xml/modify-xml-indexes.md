---
title: Ändern von XML-Indizes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XML indexes [SQL Server], modifying
- modifying indexes
ms.assetid: 24d50fe1-c6ec-49e6-91a3-9791851ba53d
author: rothja
ms.author: jroth
ms.openlocfilehash: c5c67470fc9aaaeefe49e5ccb1a8602e082c4054
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696514"
---
# <a name="modify-xml-indexes"></a><span data-ttu-id="fc3c5-102">Ändern von XML-Indizes</span><span class="sxs-lookup"><span data-stu-id="fc3c5-102">Modify XML Indexes</span></span>
  <span data-ttu-id="fc3c5-103">Die [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)]-DDL-Anweisung kann zum Ändern vorhandener XML-Indizes und Nicht-XML-Indizes verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fc3c5-103">The [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statement can be used to modify existing XML and non-XML indexes.</span></span> <span data-ttu-id="fc3c5-104">Nicht alle ALTER INDEX-Optionen sind jedoch für XML-Indizes verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fc3c5-104">However, not all the ALTER INDEX options are available to XML indexes.</span></span> <span data-ttu-id="fc3c5-105">Die folgenden Optionen sind beim Ändern von XML-Indizes nicht zulässig:</span><span class="sxs-lookup"><span data-stu-id="fc3c5-105">The following options are not valid when modifying XML indexes:</span></span>  
  
-   <span data-ttu-id="fc3c5-106">Die REBUILD- und SET-Option IGNORE_DUP_KEY ist für XML-Indizes nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="fc3c5-106">The rebuild and set option IGNORE_DUP_KEY is not valid for XML indexes.</span></span> <span data-ttu-id="fc3c5-107">Die REBUILD-Option ONLINE muss für sekundäre XML-Indizes auf OFF festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fc3c5-107">The rebuild option ONLINE must be set to OFF for secondary XML indexes.</span></span> <span data-ttu-id="fc3c5-108">Die Option DROP_EXISTING ist in der ALTER INDEX-Anweisung nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="fc3c5-108">The option DROP_EXISTING is not permitted in the ALTER INDEX statement.</span></span>  
  
-   <span data-ttu-id="fc3c5-109">Die Änderungen der primary key-Einschränkung in der user-Tabelle werden nicht automatisch an XML-Indizes weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="fc3c5-109">The modifications of the primary key constraint in the user table are not automatically propagated to XML indexes.</span></span> <span data-ttu-id="fc3c5-110">Der Benutzer muss die XML-Indizes zuerst löschen und dann neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fc3c5-110">The user must drop the XML indexes first and then re-create them.</span></span>  
  
-   <span data-ttu-id="fc3c5-111">Wenn ALTER INDEX ALL angegeben wird, gilt dies für Nicht-XML- und XML-Indizes.</span><span class="sxs-lookup"><span data-stu-id="fc3c5-111">If ALTER INDEX ALL is specified, it applies to both non-XML and XML indexes.</span></span> <span data-ttu-id="fc3c5-112">Möglicherweise werden Indizierungsoptionen angegeben, die nicht für beide Indextypen zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="fc3c5-112">Indexing options may be specified that are not valid for both types of indexes.</span></span> <span data-ttu-id="fc3c5-113">In diesem Fall schlägt die gesamte Anweisung fehl.</span><span class="sxs-lookup"><span data-stu-id="fc3c5-113">In this case, the whole statement fails.</span></span>  
  
## <a name="example-modifying-an-xml-index"></a><span data-ttu-id="fc3c5-114">Beispiel: Ändern eines XML-Index</span><span class="sxs-lookup"><span data-stu-id="fc3c5-114">Example: Modifying an XML Index</span></span>  
 <span data-ttu-id="fc3c5-115">Im folgenden Beispiel wird ein XML-Index erstellt und dann durch Festlegen der Option `ALLOW_ROW_LOCKS` auf `OFF`geändert.</span><span class="sxs-lookup"><span data-stu-id="fc3c5-115">In the following example, an XML index is created and then modified by setting the option `ALLOW_ROW_LOCKS` to `OFF`.</span></span> <span data-ttu-id="fc3c5-116">Wenn `ALLOW_ROW_LOCKS` auf `OFF`festgelegt wurde, sind die Zeilen gesperrt, und der Zugriff auf die angegebenen Indizes erfolgt über die Sperren auf Seiten- und Tabellenebene.</span><span class="sxs-lookup"><span data-stu-id="fc3c5-116">When `ALLOW_ROW_LOCKS` is `OFF`, rows are not locked and access to the specified indexes is obtained by using page-and table-level locks.</span></span>  
  
```  
CREATE TABLE T (Col1 INT PRIMARY KEY, XmlCol XML)  
GO  
-- Create primary XML index.   
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlCol)  
GO  
-- Note the type 3 is index on XML type.  
SELECT *  
FROM sys.xml_indexes  
WHERE object_id = object_id('T')  
AND name='PIdx_T_XmlCol'  
  
-- Modify and set an index option.  
ALTER INDEX PIdx_T_XmlCol on T   
SET (ALLOW_ROW_LOCKS = OFF)  
```  
  
## <a name="example-disabling-and-enabling-an-xml-index"></a><span data-ttu-id="fc3c5-117">Beispiel: Deaktivieren und Aktivieren eines XML-Index</span><span class="sxs-lookup"><span data-stu-id="fc3c5-117">Example: Disabling and Enabling an XML Index</span></span>  
 <span data-ttu-id="fc3c5-118">Standardmäßig ist ein XML-Index aktiviert.</span><span class="sxs-lookup"><span data-stu-id="fc3c5-118">By default, an XML index is enabled.</span></span> <span data-ttu-id="fc3c5-119">Wenn ein XML-Index deaktiviert ist, verwenden die Abfragen, die für eine XML-Spalte ausgeführt werden, den XML-Index nicht.</span><span class="sxs-lookup"><span data-stu-id="fc3c5-119">If an XML index is disabled, the queries running against the XML column do not use the XML index.</span></span> <span data-ttu-id="fc3c5-120">Verwenden Sie `ALTER INDEX` mit der Option `REBUILD` , um einen XML-Index zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fc3c5-120">To enable an XML index, use `ALTER INDEX` with the `REBUILD` option.</span></span>  
  
```  
CREATE TABLE T (Col1 INT PRIMARY KEY, XmlCol XML)  
GO  
CREATE PRIMARY XML INDEX PIdx_T_XmlCol ON T(XmlCol)  
GO  
ALTER INDEX PIdx_T_XmlCol on T DISABLE  
Go  
-- Verify index is disabled.  
SELECT *  
FROM sys.xml_indexes  
WHERE object_id = object_id('T')  
AND name='PIdx_T_XmlCol'  
-- Rebuild the index.  
ALTER INDEX PIdx_T_XmlCol on T REBUILD  
Go  
```  
  
## <a name="see-also"></a><span data-ttu-id="fc3c5-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fc3c5-121">See Also</span></span>  
 [<span data-ttu-id="fc3c5-122">XML-Indizes &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fc3c5-122">XML Indexes &#40;SQL Server&#41;</span></span>](xml-indexes-sql-server.md)  
  
  
