---
title: Spalten, die standardmäßig einen NULL-Wert enthalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- columns [XML in SQL Server], null default value
ms.assetid: 9381c07f-6887-4a62-9730-32661f9aa87c
author: rothja
ms.author: jroth
ms.openlocfilehash: 92ea51101f73695be2075a1b41deb62ca021f496
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608436"
---
# <a name="columns-that-contain-a-null-value-by-default"></a><span data-ttu-id="2541d-102">Spalten, die standardmäßig einen NULL-Wert enthalten</span><span class="sxs-lookup"><span data-stu-id="2541d-102">Columns that Contain a Null Value By Default</span></span>
  <span data-ttu-id="2541d-103">In der Standardeinstellung wird ein NULL-Wert in einer Spalte der Abwesenheit des Attributs, Knotens oder Elements zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="2541d-103">By default, a null value in a column maps to the absence of the attribute, node, or element.</span></span> <span data-ttu-id="2541d-104">Dieses Standardverhalten kann durch das Anfordern eines elementzentrierten XML-Codes mithilfe der ELEMENTS-Direktive und der Angabe von XSINIL zum Hinzufügen von Elementen für NULL-Werte überschrieben werden, wie in der folgenden Abfrage gezeigt:</span><span class="sxs-lookup"><span data-stu-id="2541d-104">This default behavior can be overwritten by requesting element-centric XML using the ELEMENTS directive and specifying XSINIL to request adding elements for NULL values, as shown in the following query:</span></span>  
  
```  
SELECT EmployeeID as "@EmpID",   
       FirstName  as "EmpName/First",   
       MiddleName as "EmpName/Middle",   
       LastName   as "EmpName/Last"  
FROM   HumanResources.Employee E, Person.Contact C  
WHERE  E.EmployeeID = C.ContactID  
AND    E.EmployeeID=1  
FOR XML PATH, ELEMENTS XSINIL  
```  
  
 <span data-ttu-id="2541d-105">Im Folgenden wird das Ergebnis gezeigt.</span><span class="sxs-lookup"><span data-stu-id="2541d-105">The following shows the result.</span></span> <span data-ttu-id="2541d-106">Beachten Sie, dass das <`Middle`>-Element abwesend sein wird, wenn XSINIL nicht angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2541d-106">Note that if XSINIL is not specified, the <`Middle`> element will be absent.</span></span>  
  
```  
<row xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" EmpID="1">  
  <EmpName>  
    <First>Gustavo</First>  
    <Middle xsi:nil="true" />  
    <Last>Achong</Last>  
  </EmpName>  
</row>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2541d-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2541d-107">See Also</span></span>  
 [<span data-ttu-id="2541d-108">Verwenden des PATH-Modus mit FOR XML</span><span class="sxs-lookup"><span data-stu-id="2541d-108">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
