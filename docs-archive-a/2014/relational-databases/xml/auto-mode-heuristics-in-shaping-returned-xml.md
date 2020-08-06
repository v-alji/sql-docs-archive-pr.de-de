---
title: AUTO-Modus-Heuristik beim Ermitteln der Form des zurückgegebenen XML-Codes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- AUTO FOR XML mode, heuristics in shaping returned XML
ms.assetid: 6c5cb6c1-2921-4ba1-8100-0bf8074f9103
author: rothja
ms.author: jroth
ms.openlocfilehash: 7a64cda8989e1e45d4ad869f8883e1c9d65f4b7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608450"
---
# <a name="auto-mode-heuristics-in-shaping-returned-xml"></a><span data-ttu-id="0d7ef-102">AUTO-Modus-Heuristik beim Ermitteln der Form des zurückgegebenen XML-Codes</span><span class="sxs-lookup"><span data-stu-id="0d7ef-102">AUTO Mode Heuristics in Shaping Returned XML</span></span>
  <span data-ttu-id="0d7ef-103">Der AUTO-Modus ermittelt die Form des zurückgegebenen XML-Codes auf der Grundlage der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="0d7ef-103">AUTO mode determines the shape of returned XML based on the query.</span></span> <span data-ttu-id="0d7ef-104">Um zu ermitteln, wie die Elemente geschachtelt werden sollen, vergleicht die AUTO-Modus-Heuristik die Spaltenwerte in benachbarten Zeilen.</span><span class="sxs-lookup"><span data-stu-id="0d7ef-104">In determining how elements are to be nested, AUTO mode heuristics compare column values in adjacent rows.</span></span> <span data-ttu-id="0d7ef-105">Dabei werden Spalten aller Datentypen, mit Ausnahme von **ntext**, **text**, **image**und **xml**miteinander verglichen.</span><span class="sxs-lookup"><span data-stu-id="0d7ef-105">Columns of all types, except **ntext**, **text**, **image**, and **xml**, are compared.</span></span> <span data-ttu-id="0d7ef-106">Spalten des Datentyps **(n)varchar(max)** und **varbinary(max)** werden verglichen.</span><span class="sxs-lookup"><span data-stu-id="0d7ef-106">Columns of type **(n)varchar(max)** and **varbinary(max)** are compared.</span></span>  
  
 <span data-ttu-id="0d7ef-107">Das folgende Beispiel veranschaulicht die Heuristik des AUTO-Modus beim Ermitteln der Form des resultierenden XML-Codes:</span><span class="sxs-lookup"><span data-stu-id="0d7ef-107">The following example illustrates the AUTO mode heuristics that determine the shape of the resulting XML:</span></span>  
  
```  
SELECT T1.Id, T2.Id, T1.Name  
FROM   T1, T2  
WHERE ...  
FOR XML AUTO  
ORDER BY T1.Id  
```  
  
 <span data-ttu-id="0d7ef-108">Um zu ermitteln, wo ein neues <`T1`>-Element beginnt, werden alle Spaltenwerte von Tabelle T1 (außer **ntext**, **text**, **image** und **xml**) verglichen, wenn der Schlüssel für die Tabelle T1 nicht angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="0d7ef-108">To determine where a new <`T1`> element starts, all column values of T1, except **ntext**, **text**, **image** and **xml**, are compared if the key on the table T1 is not specified.</span></span> <span data-ttu-id="0d7ef-109">Nehmen wir als Nächstes an, dass die **Name** -Spalte den Typ **nvarchar(40)** aufweist und dass die SELECT-Anweisung das folgende Rowset zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="0d7ef-109">Next, assume that the **Name** column is **nvarchar(40)** and the SELECT statement returns this rowset:</span></span>  
  
```  
T1.Id  T1.Name  T2.Id  
-----------------------  
1       Andrew    2  
1       Andrew    3  
1       Nancy     4  
```  
  
 <span data-ttu-id="0d7ef-110">Die Heuristik des AUTO-Modus vergleicht alle Werte aus Tabelle T1, die Id- und die Name-Spalten.</span><span class="sxs-lookup"><span data-stu-id="0d7ef-110">The AUTO mode heuristics compare all the values of table T1, the Id and Name columns.</span></span> <span data-ttu-id="0d7ef-111">Da die ersten zwei Zeilen über die gleichen Werte für die Spalten „Id“ und „Name“ verfügen, wird ein \<T1>-Element, das über zwei untergeordnete \<T2>-Elemente verfügt, im Ergebnis hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0d7ef-111">Because the first two rows have the same values for the Id and Name columns, one \<T1> element having two \<T2> child elements is added in the result.</span></span>  
  
 <span data-ttu-id="0d7ef-112">Der folgende XML-Code wird zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="0d7ef-112">Following is the XML that is returned:</span></span>  
  
```  
<T1 Id="1" Name="Andrew">  
    <T2 Id="2" />  
    <T2 Id="3" />  
</T1>  
<T1 Id="1" Name="Nancy" >  
      <T2 Id="4" />  
</T>  
```  
  
 <span data-ttu-id="0d7ef-113">Nehmen wir jetzt an, dass die Name-Spalte den **text** -Datentyp aufweist.</span><span class="sxs-lookup"><span data-stu-id="0d7ef-113">Now assume that the Name column is of **text** type.</span></span> <span data-ttu-id="0d7ef-114">Die Heuristik des AUTO-Modus führt keinen Vergleich der Werte für diesen Datentyp durch.</span><span class="sxs-lookup"><span data-stu-id="0d7ef-114">The AUTO mode heuristics do not compare the values for this type.</span></span> <span data-ttu-id="0d7ef-115">Stattdessen wird angenommen, dass sich die Werte voneinander unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="0d7ef-115">Instead, it assumes that the values are not the same.</span></span> <span data-ttu-id="0d7ef-116">Dadurch wird der folgende XML-Code generiert:</span><span class="sxs-lookup"><span data-stu-id="0d7ef-116">This results in XML generation as shown in the following:</span></span>  
  
```  
<T1 Id="1" Name="Andrew" >  
  <T2 Id="2" />  
</T1>  
<T1 Id="1" Name="Andrew" >  
  <T2 Id="3" />  
</T1>  
<T1 Id="1" Name="Nancy" >  
  <T2 Id="4" />  
</T1>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0d7ef-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0d7ef-117">See Also</span></span>  
 [<span data-ttu-id="0d7ef-118">Verwenden des AUTO-Modus mit FOR XML</span><span class="sxs-lookup"><span data-stu-id="0d7ef-118">Use AUTO Mode with FOR XML</span></span>](use-auto-mode-with-for-xml.md)  
  
  
