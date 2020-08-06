---
title: Erstellen, Ändern und Löschen sekundärer, selektiver XML-Indizes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
ms.assetid: 45128105-833b-40a9-9cc9-1ae03ac0b52b
author: rothja
ms.author: jroth
ms.openlocfilehash: e6f7296896b6421db5329565403cdcbaf10b26a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697610"
---
# <a name="create-alter-and-drop-secondary-selective-xml-indexes"></a><span data-ttu-id="ea806-102">Erstellen, Ändern und Löschen sekundärer, selektiver XML-Indizes</span><span class="sxs-lookup"><span data-stu-id="ea806-102">Create, Alter, and Drop Secondary Selective XML Indexes</span></span>
  <span data-ttu-id="ea806-103">Beschreibt, wie ein neuer sekundärer, selektiver XML-Index erstellt bzw. ein vorhandener sekundärer, selektiver XML-Index geändert oder gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="ea806-103">Describes how to create a new secondary selective XML index, or alter or drop an existing secondary selective XML index.</span></span>  
  
##  <a name="creating-a-secondary-selective-xml-index"></a><a name="create"></a> <span data-ttu-id="ea806-104">Erstellen eines sekundären, selektiven XML-Indexes</span><span class="sxs-lookup"><span data-stu-id="ea806-104">Creating a Secondary Selective XML Index</span></span>  
  
### <a name="how-to-create-a-secondary-selective-xml-index"></a><span data-ttu-id="ea806-105">Gewusst wie: Erstellen eines sekundären, selektiven XML-Index</span><span class="sxs-lookup"><span data-stu-id="ea806-105">How to: Create a Secondary Selective XML Index</span></span>  
 <span data-ttu-id="ea806-106">**Erstellen eines sekundären, selektiven XML-Indexes mit Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="ea806-106">**Create a Secondary Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="ea806-107">Erstellen Sie einen sekundären, selektiven XML-Index, indem Sie die CREATE XML INDEX-Anweisung aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ea806-107">Create a secondary selective XML index by calling the CREATE XML INDEX statement.</span></span> <span data-ttu-id="ea806-108">Weitere Informationen finden Sie unter [CREATE XML Index &#40;Selective XML Indexes&#41;] (~/t-SQL/Statements/CREATE-XML-Index-Selective-XML-Indexes.</span><span class="sxs-lookup"><span data-stu-id="ea806-108">For more information, see [CREATE XML INDEX &#40;Selective XML Indexes&#41;](~/t-sql/statements/create-xml-index-selective-xml-indexes.</span></span>  
  
 <span data-ttu-id="ea806-109">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="ea806-109">**Example**</span></span>  
  
 <span data-ttu-id="ea806-110">Im folgenden Beispiel wird ein sekundärer selektiver XML-Index für den Pfad `'pathabc'`erstellt.</span><span class="sxs-lookup"><span data-stu-id="ea806-110">The following example creates a secondary selective XML index on the path `'pathabc'`.</span></span> <span data-ttu-id="ea806-111">Der zu indizierende Pfad wird anhand des Namens identifiziert, der ihm bei der Erstellung durch die CREATE SELECTIVE XML INDEX-Anweisung zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="ea806-111">The path to index is identified by the name that was given to it when it was created with the CREATE SELECTIVE XML INDEX statement.</span></span> <span data-ttu-id="ea806-112">Weitere Informationen finden Sie unter [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ea806-112">For more information, see [CREATE SELECTIVE XML INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-selective-xml-index-transact-sql).</span></span>  
  
```sql  
CREATE XML INDEX filt_sxi_index_c  
ON Tbl(xmlcol)  
USING XML INDEX sxi_index  
FOR  
(  
    pathabc  
)  
```  
  
  
##  <a name="altering-a-secondary-selective-xml-index"></a><a name="alter"></a> <span data-ttu-id="ea806-113">Ändern eines sekundären, selektiven XML-Indexes</span><span class="sxs-lookup"><span data-stu-id="ea806-113">Altering a Secondary Selective XML Index</span></span>  
 <span data-ttu-id="ea806-114">Die ALTER-Anweisung wird für sekundäre, selektive XML-Indizes nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ea806-114">The ALTER statement is not supported for secondary selective XML indexes.</span></span> <span data-ttu-id="ea806-115">Um einen sekundären, selektiven XML-Index zu ändern, löschen Sie den vorhandenen Index und erstellen ihn erneut.</span><span class="sxs-lookup"><span data-stu-id="ea806-115">To change a secondary selective XML index, drop the existing index and recreate it.</span></span>  
  
### <a name="how-to-alter-a-secondary-selective-xml-index"></a><span data-ttu-id="ea806-116">Gewusst wie: Ändern eines sekundären, selektiven XML-Indexes</span><span class="sxs-lookup"><span data-stu-id="ea806-116">How to: Alter a Secondary Selective XML Index</span></span>  
 <span data-ttu-id="ea806-117">**Ändern eines sekundären, selektiven XML-Indexes mit Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="ea806-117">**Alter a Secondary Selective XML Index by Using Transact-SQL**</span></span>  
 1.  <span data-ttu-id="ea806-118">Löschen Sie den vorhandenen sekundären, selektiven XML-Index, indem Sie die DROP INDEX-Anweisung aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ea806-118">Drop the existing secondary selective XML index by calling the DROP INDEX statement.</span></span> <span data-ttu-id="ea806-119">Weitere Informationen finden Sie unter [DROP INDEX &#40;selektive XML-Indizes&#41;](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="ea806-119">For more information, see [DROP INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span></span>  
  
2.  <span data-ttu-id="ea806-120">Erstellen Sie den Index mit den gewünschten Optionen neu, indem Sie die CREATE XML INDEX-Anweisung aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ea806-120">Recreate the index with the desired options by calling the CREATE XML INDEX statement.</span></span> <span data-ttu-id="ea806-121">Weitere Informationen finden Sie unter [CREATE XML Index &#40;Selective XML Indexes&#41;] (~/t-SQL/Statements/CREATE-XML-Index-Selective-XML-Indexes.</span><span class="sxs-lookup"><span data-stu-id="ea806-121">For more information, see [CREATE XML INDEX &#40;Selective XML Indexes&#41;](~/t-sql/statements/create-xml-index-selective-xml-indexes.</span></span>  
  
 <span data-ttu-id="ea806-122">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="ea806-122">**Example**</span></span>  
  
 <span data-ttu-id="ea806-123">Im folgenden Beispiel wird ein sekundärer, selektiver XML-Index geändert, indem er gelöscht und neu erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ea806-123">The following example changes a secondary selective XML index by dropping it and recreating it.</span></span>  
  
```sql  
DROP INDEX filt_sxi_index_c  
  
CREATE XML INDEX filt_sxi_index_c  
ON Tbl(xmlcol)  
USING XML INDEX sxi_index  
FOR  
(  
    pathabc  
)  
```  
  
  
##  <a name="dropping-a-secondary-selective-xml-index"></a><a name="drop"></a> <span data-ttu-id="ea806-124">Löschen eines sekundären, selektiven XML-Indexes</span><span class="sxs-lookup"><span data-stu-id="ea806-124">Dropping a Secondary Selective XML Index</span></span>  
  
### <a name="how-to-drop-a-secondary-selective-xml-index"></a><span data-ttu-id="ea806-125">Gewusst wie: Löschen eines sekundären, selektiven XML-Index</span><span class="sxs-lookup"><span data-stu-id="ea806-125">How to: Drop a Secondary Selective XML Index</span></span>  
 <span data-ttu-id="ea806-126">**Löschen eines sekundären, selektiven XML-Indexes mit Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="ea806-126">**Drop a Secondary Selective XML Index by Using Transact-SQL**</span></span>  
 <span data-ttu-id="ea806-127">Löschen Sie einen sekundären, selektiven XML-Index, indem Sie die DROP INDEX-Anweisung aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ea806-127">Drop a secondary selective XML index by calling the DROP INDEX statement.</span></span> <span data-ttu-id="ea806-128">Weitere Informationen finden Sie unter [DROP INDEX &#40;selektive XML-Indizes&#41;](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="ea806-128">For more information, see [DROP INDEX &#40;Selective XML Indexes&#41;](../indexes/indexes.md).</span></span>  
  
 <span data-ttu-id="ea806-129">**Beispiel**</span><span class="sxs-lookup"><span data-stu-id="ea806-129">**Example**</span></span>  
  
 <span data-ttu-id="ea806-130">Im folgenden Beispiel wird eine DROP INDEX-Anweisung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ea806-130">The following example shows a DROP INDEX statement.</span></span>  
  
```sql  
DROP INDEX ssxi_index  
ON tbl  
```  
  
  
## <a name="see-also"></a><span data-ttu-id="ea806-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ea806-131">See Also</span></span>  
 [<span data-ttu-id="ea806-132">Selektive XML-Indizes &#40;SXI&#41;</span><span class="sxs-lookup"><span data-stu-id="ea806-132">Selective XML Indexes &#40;SXI&#41;</span></span>](selective-xml-indexes-sxi.md)  
  
  
