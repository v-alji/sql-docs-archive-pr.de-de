---
title: Verwenden der Option BINARY BASE64 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- AUTO FOR XML mode, BINARY BASE64 option
ms.assetid: 86a7bb85-7f83-412a-b775-d2c379702fe9
author: rothja
ms.author: jroth
ms.openlocfilehash: 090d6a91ee56707a4eb1d545aa5a05bc25999fab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722586"
---
# <a name="use-the-binary-base64-option"></a><span data-ttu-id="006c1-102">Verwenden der Option BINARY BASE64</span><span class="sxs-lookup"><span data-stu-id="006c1-102">Use the BINARY BASE64 Option</span></span>
  <span data-ttu-id="006c1-103">Wenn die Option BINARY BASE64 in der Abfrage angegeben ist, werden die Binärdaten im Base64-codierten Format zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="006c1-103">If the BINARY BASE64 option is specified in the query, the binary data is returned in base64 encoding format.</span></span> <span data-ttu-id="006c1-104">Der AUTO-Modus unterstützt die URL-Codierung von Binärdaten standardmäßig (sofern die Option BINARY BASE64 nicht angegeben wurde).</span><span class="sxs-lookup"><span data-stu-id="006c1-104">By default, if the BINARY BASE64 option is not specified, AUTO mode supports URL encoding of binary data.</span></span> <span data-ttu-id="006c1-105">Das heißt, anstelle von Binärdaten wird ein Verweis (eine relative URL auf das virtuelle Stammverzeichnis der Datenbank, in der die Abfrage ausgeführt wird) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="006c1-105">That is, instead of binary data, a reference to a relative URL to the virtual root of the database where the query was executed is returned.</span></span> <span data-ttu-id="006c1-106">Dieser Verweis kann für den Zugriff auf die Binärdaten in nachfolgenden Vorgängen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="006c1-106">This reference can be used to access the actual binary data in subsequent operations by using the SQLXML ISAPI dbobject query.</span></span> <span data-ttu-id="006c1-107">Die Abfrage muss ausreichend Informationen, wie etwa Primärschlüsselspalten, bereitstellen, damit Teile des Images später im XML-Dokument identifiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="006c1-107">The query must provide enough information, such as primary key columns, to identify the image.</span></span>  
  
 <span data-ttu-id="006c1-108">Wenn beim Angeben einer Abfrage ein Alias für die Binärspalte der Sicht verwendet wird, wird der Alias in der URL-Codierung der Binärdaten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="006c1-108">In specifying a query, if an alias is used for the binary column of the view, the alias is returned in the URL encoding of the binary data.</span></span> <span data-ttu-id="006c1-109">In nachfolgenden Vorgängen ist der Alias bedeutungslos, und die URL-Codierung kann nicht zum Abrufen des Images verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="006c1-109">In subsequent operations, the alias is meaningless, and the URL encoding cannot be used to retrieve the image.</span></span> <span data-ttu-id="006c1-110">Sie sollten somit keine Aliasse bei der Abfrage einer Sicht mithilfe des FOR XML AUTO-Modus verwenden.</span><span class="sxs-lookup"><span data-stu-id="006c1-110">Therefore, do not use aliases when querying a view using FOR XML AUTO mode.</span></span>  
  
 <span data-ttu-id="006c1-111">In einer SELECT-Abfrage werden beispielsweise Spalten durch Konvertieren in ein BLOB (Binary Large Object) insofern zu einer temporären Entität, als sie den zugehörigen Tabellen- und Spaltennamen verlieren.</span><span class="sxs-lookup"><span data-stu-id="006c1-111">For example, in a SELECT query, casting any column to a binary large object (BLOB) makes it a temporary entity in that it loses its associated table name and column name.</span></span> <span data-ttu-id="006c1-112">Abfragen im AUTO-Modus geben daher einen Fehler aus, da der Wert nicht in der XML-Hierarchie eingeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="006c1-112">This causes AUTO mode queries to generate an error, because it does not know where to put this value in the XML hierarchy.</span></span> <span data-ttu-id="006c1-113">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="006c1-113">For example:</span></span>  
  
```  
CREATE TABLE MyTable (Col1 int PRIMARY KEY, Col2 binary)  
INSERT INTO MyTable VALUES (1, 0x7);  
```  
  
 <span data-ttu-id="006c1-114">Diese Abfrage führt wegen der Konvertierung in BLOB (Binary Large Object) zu einem Fehler:</span><span class="sxs-lookup"><span data-stu-id="006c1-114">This query produces an error, because of the casting to a binary large object (BLOB):</span></span>  
  
```  
SELECT Col1,  
CAST(Col2 as image) as Col2  
FROM MyTable  
FOR XML AUTO;  
```  
  
 <span data-ttu-id="006c1-115">Die Lösung besteht im Hinzufügen der Option BINARY BASE64 zur FOR XML-Klausel.</span><span class="sxs-lookup"><span data-stu-id="006c1-115">The solution is to add the BINARY BASE64 option to the FOR XML clause.</span></span> <span data-ttu-id="006c1-116">Ohne die Konvertierung liefert die Abfrage die erwarteten Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="006c1-116">If you remove the casting, the query produces the results as expected:</span></span>  
  
```  
SELECT Col1,  
CAST(Col2 as image) as Col2  
FROM MyTable  
FOR XML AUTO, BINARY BASE64;  
```  
  
 <span data-ttu-id="006c1-117">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="006c1-117">This is the result:</span></span>  
  
```  
<MyTable Col1="1" Col2="Bw==" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="006c1-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="006c1-118">See Also</span></span>  
 [<span data-ttu-id="006c1-119">Verwenden des AUTO-Modus mit FOR XML</span><span class="sxs-lookup"><span data-stu-id="006c1-119">Use AUTO Mode with FOR XML</span></span>](use-auto-mode-with-for-xml.md)  
  
  
