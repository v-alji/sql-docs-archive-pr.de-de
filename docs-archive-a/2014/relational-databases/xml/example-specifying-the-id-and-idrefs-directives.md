---
title: 'Beispiel: Angeben der ID- und IDREFS-Anweisungen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- IDREFS directive
- ID directive
ms.assetid: 99b9f0d8-ecbb-4225-859f-881066c09785
author: rothja
ms.author: jroth
ms.openlocfilehash: c21ba1bd19691014f179801421322970a3dd6dd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621391"
---
# <a name="example-specifying-the-id-and-idrefs-directives"></a><span data-ttu-id="57096-102">Beispiel: Angeben der ID- und IDREFS-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="57096-102">Example: Specifying the ID and IDREFS Directives</span></span>
  <span data-ttu-id="57096-103">Ein Elementattribut kann als Attribut vom Typ `ID` angegeben werden, wobei das `IDREFS`-Attribut dann verwendet werden kann, um darauf zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="57096-103">An element attribute can be specified as an `ID` type attribute, and the `IDREFS` attribute can then be used to refer to it.</span></span> <span data-ttu-id="57096-104">Dies ermöglicht dokumentinterne Links. Das Verfahren ist der Beziehung zwischen Primärschlüssel und Fremdschlüssel in relationalen Datenbanken ähnlich.</span><span class="sxs-lookup"><span data-stu-id="57096-104">This enables intra-document links and is similar to the primary key and foreign key relationships in relational databases.</span></span>  
  
 <span data-ttu-id="57096-105">Dieses Beispiel veranschaulicht, wie die `ID`- und die `IDREFS`-Direktive zum Erstellen von Attributen vom Typ `ID` und `IDREFS` verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="57096-105">This example illustrates how the `ID` and `IDREFS` directives can be used to create attributes of `ID` and `IDREFS` types.</span></span> <span data-ttu-id="57096-106">Da IDs keine ganzzahligen Werte sein können, werden die ID-Werte in diesem Beispiel konvertiert,</span><span class="sxs-lookup"><span data-stu-id="57096-106">Because IDs cannot be integer values, the ID values in this example are converted.</span></span> <span data-ttu-id="57096-107">d. h. sie werden einer Typumwandlung unterzogen,</span><span class="sxs-lookup"><span data-stu-id="57096-107">In other words, they are type casted.</span></span> <span data-ttu-id="57096-108">und es werden Präfixe für die ID-Werte verwendet.</span><span class="sxs-lookup"><span data-stu-id="57096-108">Prefixes are used for the ID values.</span></span>  
  
 <span data-ttu-id="57096-109">Angenommen, Sie möchten folgende XML-Ausgabe generieren:</span><span class="sxs-lookup"><span data-stu-id="57096-109">Assume that you want to construct XML as shown in the following:</span></span>  
  
```  
<Customer CustomerID="C1" SalesOrderIDList=" O11 O22 O33..." >  
    <SalesOrder SalesOrderID="O11" OrderDate="..." />  
    <SalesOrder SalesOrderID="O22" OrderDate="..." />  
    <SalesOrder SalesOrderID="O33" OrderDate="..." />  
    ...  
</Customer>  
```  
  
 <span data-ttu-id="57096-110">Das `SalesOrderIDList`-Attribut des <`Customer`>-Elements ist ein mehrwertiges Attribut, das auf die `SalesOrderID`-Attribute des < `SalesOrder` >-Elements verweist.</span><span class="sxs-lookup"><span data-stu-id="57096-110">The `SalesOrderIDList` attribute of the < `Customer` > element is a multivalued attribute that refers to the `SalesOrderID` attribute of the < `SalesOrder` > element.</span></span> <span data-ttu-id="57096-111">Um diesen Link herzustellen, muss das `SalesOrderID`-Attribut als `ID`-Typ und das `SalesOrderIDList`-Attribut des < `Customer`>-Elements als `IDREFS`-Typ deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="57096-111">To establish this link, the `SalesOrderID` attribute must be declared of `ID` type, and the `SalesOrderIDList` attribute of the < `Customer`> element must be declared of `IDREFS` type.</span></span> <span data-ttu-id="57096-112">Da ein Kunde mehrere Bestellungen aufgeben kann, wird `IDREFS` verwendet.</span><span class="sxs-lookup"><span data-stu-id="57096-112">Because a customer can request several orders, the `IDREFS` type is used.</span></span>  
  
 <span data-ttu-id="57096-113">Elemente des `IDREFS`-Typs können zudem mehr als einen Wert annehmen.</span><span class="sxs-lookup"><span data-stu-id="57096-113">Elements of `IDREFS` type also have more than one value.</span></span> <span data-ttu-id="57096-114">Daher müssen Sie jeweils eine SELECT-Klausel verwenden, die dieselben Tag-, Parent- und Schlüsselspalteninformationen wiederverwendet.</span><span class="sxs-lookup"><span data-stu-id="57096-114">Therefore, you have to use a separate select clause that will reuse the same tag, parent, and key column information.</span></span> <span data-ttu-id="57096-115">Mit `ORDER BY` stellen Sie dann sicher, dass die Zeilensequenz, aus der die `IDREFS`-Werte bestehen, unter dem jeweiligen übergeordneten Element gruppiert wird.</span><span class="sxs-lookup"><span data-stu-id="57096-115">The `ORDER BY` then has to ensure that the sequence of rows that make up the `IDREFS` values appears grouped together under their parent element.</span></span>  
  
 <span data-ttu-id="57096-116">Im Folgenden wird die Abfrage gezeigt, die die gewünschte XML-Ausgabe erstellt.</span><span class="sxs-lookup"><span data-stu-id="57096-116">This is the query that produces the XML you want.</span></span> <span data-ttu-id="57096-117">Die Abfrage verwendet die `ID` -Direktive und die `IDREFS` -Direktive, um die Datentypen der Spaltennamen (`SalesOrder!2!SalesOrderID!ID`, `Customer!1!SalesOrderIDList!IDREFS`) zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="57096-117">The query uses the `ID` and `IDREFS` directives to overwrite the types in the column names (`SalesOrder!2!SalesOrderID!ID`, `Customer!1!SalesOrderIDList!IDREFS`).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT  1 as Tag,  
        0 as Parent,  
        C.CustomerID       [Customer!1!CustomerID],  
        NULL               [Customer!1!SalesOrderIDList!IDREFS],  
        NULL               [SalesOrder!2!SalesOrderID!ID],  
        NULL               [SalesOrder!2!OrderDate]  
FROM   Sales.Customer C   
UNION ALL   
SELECT  1 as Tag,  
        0 as Parent,  
        C.CustomerID,  
        'O-'+CAST(SalesOrderID as varchar(10)),   
        NULL,  
        NULL  
FROM   Sales.Customer AS C  
INNER JOIN Sales.SalesOrderHeader AS SOH  
    ON  C.CustomerID = SOH.CustomerID  
UNION ALL  
SELECT 2 as Tag,  
       1 as Parent,  
        C.CustomerID,  
        NULL,  
        'O-'+CAST(SalesOrderID as varchar(10)),  
        OrderDate  
FROM   Sales.Customer AS C  
INNER JOIN Sales.SalesOrderHeader AS SOH  
    ON  C.CustomerID = SOH.CustomerIDORDER BY [Customer!1!CustomerID] ,  
         [SalesOrder!2!SalesOrderID!ID],  
         [Customer!1!SalesOrderIDList!IDREFS]  
FOR XML EXPLICIT;  
```  
  
## <a name="see-also"></a><span data-ttu-id="57096-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="57096-118">See Also</span></span>  
 [<span data-ttu-id="57096-119">Verwenden des EXPLICIT-Modus mit FOR XML</span><span class="sxs-lookup"><span data-stu-id="57096-119">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
