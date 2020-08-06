---
title: Erstellen, Ändern und Löschen selektiver XML-Indizes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
ms.assetid: c398f396-f630-4a2d-a264-f243c5346de1
author: rothja
ms.author: jroth
ms.openlocfilehash: bf4123a46cc13359c936e6f9cfc0db3dcfdaa175
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697609"
---
# <a name="create-alter-and-drop-selective-xml-indexes"></a><span data-ttu-id="44141-102">Erstellen, Ändern und Löschen selektiver XML-Indizes</span><span class="sxs-lookup"><span data-stu-id="44141-102">Create, Alter, and Drop Selective XML Indexes</span></span>
  <span data-ttu-id="44141-103">Beschreibt, wie ein neuer selektiver XML-Index erstellt bzw. ein vorhandener selektiver XML-Index geändert oder gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="44141-103">Describes how to create a new selective XML index, or alter or drop an existing selective XML index.</span></span>  
  
 <span data-ttu-id="44141-104">Weitere Informationen über selektive XML-Indizes finden Sie unter [Selektive XML-Indizes &#40;SXI&#41;](selective-xml-indexes-sxi.md).</span><span class="sxs-lookup"><span data-stu-id="44141-104">For more information about selective XML indexes, see [Selective XML Indexes &#40;SXI&#41;](selective-xml-indexes-sxi.md).</span></span>  
  
##  <a name="creating-a-selective-xml-index"></a><a name="create"></a> <span data-ttu-id="44141-105">Erstellen eine selektiven XML-Indexes</span><span class="sxs-lookup"><span data-stu-id="44141-105">Creating a Selective XML Index</span></span>  
  
### <a name="how-to-create-a-selective-xml-index"></a><span data-ttu-id="44141-106">Gewusst wie: Erstellen eines selektiven XML-Index</span><span class="sxs-lookup"><span data-stu-id="44141-106">How to: Create a Selective XML Index</span></span>  
 <span data-ttu-id="44141-107">**Erstellen eines selektiven XML-Indexes mit Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="44141-107">**Create a Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="44141-108">Erstellen Sie einen selektiven XML-Index, indem Sie die CREATE SELECTIVE XML INDEX-Anweisung aufrufen.</span><span class="sxs-lookup"><span data-stu-id="44141-108">Create a selective XML index by calling the CREATE SELECTIVE XML INDEX statement.</span></span> <span data-ttu-id="44141-109">Weitere Informationen finden Sie unter [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="44141-109">For more information, see [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span></span>  
  
 <span data-ttu-id="44141-110">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="44141-110">**Example**</span></span>  
  
 <span data-ttu-id="44141-111">Im folgenden Beispiel wird die Syntax zum Erstellen eines selektiven XML-Indexes veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="44141-111">The following example shows the syntax for creating a selective XML index.</span></span> <span data-ttu-id="44141-112">Zudem werden mehrere Variationen der Syntax, die die zu indizierenden Pfade beschreibt, mit optionalen Optimierungshinweisen angegeben.</span><span class="sxs-lookup"><span data-stu-id="44141-112">It also shows several variations of the syntax for describing the paths to be indexed, with optional optimization hints.</span></span>  
  
```sql  
CREATE SELECTIVE XML INDEX sxi_index  
ON Tbl(xmlcol)  
  
FOR(  
    pathab   = '/a/b' as XQUERY 'node()'  
    pathabc  = '/a/b/c' as XQUERY 'xs:double',   
    pathdtext = '/a/b/d/text()' as XQUERY 'xs:string' MAXLENGTH(200) SINGLETON  
    pathabe = '/a/b/e' as SQL NVARCHAR(100)  
)  
```  
  
  
  
##  <a name="altering-a-selective-xml-index"></a><a name="alter"></a> <span data-ttu-id="44141-113">Ändern eines selektiven XML-Indexes</span><span class="sxs-lookup"><span data-stu-id="44141-113">Altering a Selective XML Index</span></span>  
  
### <a name="how-to-alter-a-selective-xml-index"></a><span data-ttu-id="44141-114">Gewusst wie: Ändern eines selektiven XML-Index</span><span class="sxs-lookup"><span data-stu-id="44141-114">How to: Alter a Selective XML Index</span></span>  
 <span data-ttu-id="44141-115">**Ändern eines selektiven XML-Indexes mit Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="44141-115">**Alter a Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="44141-116">Ändern Sie einen vorhandenen selektiven XML-Index, indem Sie die ALTER INDEX-Anweisung aufrufen.</span><span class="sxs-lookup"><span data-stu-id="44141-116">Alter an existing selective XML index by calling the ALTER INDEX statement.</span></span> <span data-ttu-id="44141-117">Weitere Informationen finden Sie unter [ALTER INDEX &#40;selektive XML-Indizes&#41;](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="44141-117">For more information, see [ALTER INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span></span>  
  
 <span data-ttu-id="44141-118">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="44141-118">**Example**</span></span>  
  
 <span data-ttu-id="44141-119">Im folgenden Beispiel wird eine ALTER INDEX-Anweisung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="44141-119">The following example shows an ALTER INDEX statement.</span></span> <span data-ttu-id="44141-120">Mit dieser Anweisung wird der Pfad `'/a/b/m'` dem XQuery-Teil des Indexes hinzugefügt und der Pfad `'/a/b/e'` vom SQL-Teil des Indexes, der im Beispiel im Thema [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql) erstellt wurde, gelöscht.</span><span class="sxs-lookup"><span data-stu-id="44141-120">This statement adds the path `'/a/b/m'` to the XQuery part of the index and deletes the path `'/a/b/e'` from the SQL part of the index created in the example in the topic [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span></span> <span data-ttu-id="44141-121">Der zu löschende Pfad ist anhand des Namens zu erkennen, der ihm bei der Erstellung zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="44141-121">The path to delete is identified by the name that was given to it when it was created.</span></span>  
  
```sql  
ALTER INDEX sxi_index  
ON Tbl  
FOR   
(  
    ADD pathm = '/a/b/m' as XQUERY 'node()' ,  
    REMOVE pathabe  
)  
```  
  
  
  
##  <a name="dropping-a-selective-xml-index"></a><a name="drop"></a> <span data-ttu-id="44141-122">Löschen eines selektiven XML-Indexes</span><span class="sxs-lookup"><span data-stu-id="44141-122">Dropping a Selective XML Index</span></span>  
  
### <a name="how-to-drop-a-selective-xml-index"></a><span data-ttu-id="44141-123">Gewusst wie: Löschen eines selektiven XML-Index</span><span class="sxs-lookup"><span data-stu-id="44141-123">How to: Drop a Selective XML Index</span></span>  
 <span data-ttu-id="44141-124">**Löschen eines selektiven XML-Indexes mit Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="44141-124">**Drop a Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="44141-125">Löschen Sie einen selektiven XML-Index, indem Sie die DROP INDEX-Anweisung aufrufen.</span><span class="sxs-lookup"><span data-stu-id="44141-125">Drop a selective XML index by calling the DROP INDEX statement.</span></span> <span data-ttu-id="44141-126">Weitere Informationen finden Sie unter [DROP INDEX &#40;selektive XML-Indizes&#41;](/sql/t-sql/statements/drop-index-selective-xml-indexes).</span><span class="sxs-lookup"><span data-stu-id="44141-126">For more information, see [DROP INDEX &#40;Selective XML Indexes&#41;](/sql/t-sql/statements/drop-index-selective-xml-indexes).</span></span>  
  
 <span data-ttu-id="44141-127">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="44141-127">**Example**</span></span>  
  
 <span data-ttu-id="44141-128">Im folgenden Beispiel wird eine DROP INDEX-Anweisung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="44141-128">The following example shows a DROP INDEX statement.</span></span>  
  
```sql  
DROP INDEX sxi_index ON tbl  
```  
  
 
  
  
