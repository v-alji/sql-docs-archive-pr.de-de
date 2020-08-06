---
title: 'Beispiel: Angeben der XMLTEXT-Anweisung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XMLTEXT directive
ms.assetid: e78008ec-51e8-4fd1-b86f-1058a781de17
author: rothja
ms.author: jroth
ms.openlocfilehash: d14299ad3e989c6600434b857a650fbbddd7a590
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621386"
---
# <a name="example-specifying-the-xmltext-directive"></a><span data-ttu-id="98a1b-102">Beispiel: Angeben der XMLTEXT-Anweisung</span><span class="sxs-lookup"><span data-stu-id="98a1b-102">Example: Specifying the XMLTEXT Directive</span></span>
  <span data-ttu-id="98a1b-103">Dieses Beispiel veranschaulicht, wie Daten in der Überlaufspalte mithilfe der `XMLTEXT`-Direktive in einer `SELECT`-Anweisung im EXPLICIT-Modus verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="98a1b-103">This example illustrates how data in the overflow column is addressed by using the `XMLTEXT` directive in a `SELECT` statement using EXPLICIT mode.</span></span>  
  
 <span data-ttu-id="98a1b-104">Sie sehen hier die `Person` -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="98a1b-104">Consider the `Person` table.</span></span> <span data-ttu-id="98a1b-105">In dieser Tabelle speichert die `Overflow` -Spalte den unverbrauchten Teil des XML-Dokuments.</span><span class="sxs-lookup"><span data-stu-id="98a1b-105">This table has an `Overflow` column that stores the unconsumed part of the XML document.</span></span>  
  
```  
USE tempdb;  
GO  
CREATE TABLE Person(PersonID varchar(5), PersonName varchar(20), Overflow nvarchar(200));  
GO  
INSERT INTO Person VALUES   
    ('P1','Joe',N'<SomeTag attr1="data">content</SomeTag>')  
   ,('P2','Joe',N'<SomeTag attr2="data"/>')  
   ,('P3','Joe',N'<SomeTag attr3="data" PersonID="P">content</SomeTag>');  
```  
  
 <span data-ttu-id="98a1b-106">Diese Abfrage ruft Spalten aus der `Person` -Tabelle ab.</span><span class="sxs-lookup"><span data-stu-id="98a1b-106">This query retrieves columns from the `Person` table.</span></span> <span data-ttu-id="98a1b-107">`Overflow` AttributeName *ist für die* -Spalte nicht angegeben, *directive* ist jedoch auf den Wert `XMLTEXT` festgelegt, um einen Spaltennamen für die Universaltabelle bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="98a1b-107">For the `Overflow` column, *AttributeName* is not specified, but *directive* is set to `XMLTEXT` as part of providing a universal table column name.</span></span>  
  
```  
SELECT 1 as Tag, NULL as parent,  
       PersonID as [Parent!1!PersonID],  
       PersonName as [Parent!1!PersonName],  
       Overflow as [Parent!1!!XMLTEST] -- No AttributeName; XMLTEXT directive  
FROM Person  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="98a1b-108">Im resultierenden XML-Dokument:</span><span class="sxs-lookup"><span data-stu-id="98a1b-108">In the resulting XML document:</span></span>  
  
-   <span data-ttu-id="98a1b-109">Da für die `Overflow`-Spalte kein *AttributeName*, sondern die `xmltext`-Direktive angegeben ist, werden die Attribute des <`overflow`>-Elements der Attributliste des einschließenden <`Parent`>-Elements angehängt.</span><span class="sxs-lookup"><span data-stu-id="98a1b-109">Because *AttributeName* is not specified for the `Overflow` column and the `xmltext` directive is specified, the attributes in the <`overflow`> element are appended to the attribute list of the enclosing <`Parent`> element.</span></span>  
  
-   <span data-ttu-id="98a1b-110">Da das `PersonID`-Attribut des <`xmltext`>-Elements in Konflikt zu dem auf der gleichen Elementebene abgerufenen `PersonID`-Attribut steht, wird das Attribut des <`xmltext`>-Elements ignoriert, sogar wenn `PersonID` NULL ist.</span><span class="sxs-lookup"><span data-stu-id="98a1b-110">Because the `PersonID`attribute in the <`xmltext`> element conflicts with the `PersonID` attribute retrieved on the same element level, the attribute in the <`xmltext`> element is ignored, even if `PersonID` is NULL.</span></span> <span data-ttu-id="98a1b-111">Im Allgemeinen überschreibt ein Attribut ein Attribut mit demselben Namen in der Überlaufspalte.</span><span class="sxs-lookup"><span data-stu-id="98a1b-111">Generally, an attribute overrides an attribute of the same name in the overflow.</span></span>  
  
 <span data-ttu-id="98a1b-112">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="98a1b-112">This is the result:</span></span>  
  
 `<Parent PersonID="P1" PersonName="Joe" attr1="data">content</Parent>`  
  
 `<Parent PersonID="P2" PersonName="Joe" attr2="data"></Parent>`  
  
 `<Parent PersonID="P3" PersonName="Joe" attr3="data">content</Parent>`  
  
 <span data-ttu-id="98a1b-113">Wird dieselbe Abfrage angegeben, und die Überlaufdaten besitzen Unterelemente, werden die Unterelemente in der `Overflow`-Spalte als Unterelemente des einschließenden <`Parent`>-Elements hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="98a1b-113">If the overflow data has subelements and the same query is specified, the subelements in the `Overflow` column are added as the subelements of the enclosing <`Parent`> element.</span></span>  
  
 <span data-ttu-id="98a1b-114">So werden in diesem Beispiel die Daten in der `Person` -Tabelle so geändert, dass die `Overflow` -Spalte nun Unterelemente besitzt:</span><span class="sxs-lookup"><span data-stu-id="98a1b-114">For example, change the data in the `Person` table so that the `Overflow` column now has subelements.</span></span>  
  
```  
USE tempdb;  
GO  
TRUNCATE TABLE Person;  
GO  
INSERT INTO Person VALUES   
    ('P1','Joe',N'<SomeTag attr1="data">content</SomeTag>')  
   ,('P2','Joe',N'<SomeTag attr2="data"/>')  
    ,('P3','Joe',N'<SomeTag attr3="data" PersonID="P"><name>PersonName</name></SomeTag>');  
```  
  
 <span data-ttu-id="98a1b-115">Beim Ausführen derselben Abfrage werden die Unterelemente des <`xmltext`>-Elements als Unterelemente des einschließenden <`Parent`>-Elements hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="98a1b-115">If the same query is executed, the subelements in the <`xmltext`> element are added as subelements of the enclosing <`Parent`> element:</span></span>  
  
```  
SELECT 1 as Tag, NULL as parent,  
       PersonID as [Parent!1!PersonID],  
       PersonName as [Parent!1!PersonName],  
       Overflow as [Parent!1!!XMLTEXT] -- no AttributeName, XMLTEXT directive  
FROM Person  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="98a1b-116">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="98a1b-116">This is the result:</span></span>  
  
 `<Parent PersonID="P1" PersonName="Joe" attr1="data">content</Parent>`  
  
 `<Parent PersonID="P2" PersonName="Joe" attr2="data"></Parent>`  
  
 `<Parent PersonID="P3" PersonName="Joe" attr3="data">`  
  
 `<name>PersonName</name>`  
  
 `</Parent>`  
  
 <span data-ttu-id="98a1b-117">Wird *AttributeName* mit der `xmltext`-Direktive angegeben, werden die Attribute des <`overflow`>-Elements als Attribute der Unterelemente des einschließenden <`Parent`>-Elements hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="98a1b-117">If *AttributeName* is specified with the `xmltext` directive, the attributes of the <`overflow`> element are added as attributes of the subelements of the enclosing <`Parent`> element.</span></span> <span data-ttu-id="98a1b-118">Der für *attributeName* angegebene Name wird zum Namen des unter Elements.</span><span class="sxs-lookup"><span data-stu-id="98a1b-118">The name specified for *AttributeName* becomes the name of the subelement.</span></span>  
  
 <span data-ttu-id="98a1b-119">In dieser Abfrage wird *attributeName*, <`overflow`>, mit der- `xmltext` Direktive angegeben:</span><span class="sxs-lookup"><span data-stu-id="98a1b-119">In this query, *AttributeName*, <`overflow`>, is specified together with the `xmltext` directive:</span></span>  
  
```  
SELECT 1 as Tag, NULL as parent,  
       PersonID as [Parent!1!PersonID],  
       PersonName as [Parent!1!PersonName],  
       Overflow as [Parent!1!overflow!XMLTEXT] -- Overflow is AttributeName  
                      -- XMLTEXT is a directive  
FROM Person  
FOR XML EXPLICIT  
```  
  
 <span data-ttu-id="98a1b-120">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="98a1b-120">This is the result:</span></span>  
  
 `<Parent PersonID="P1" PersonName="Joe">`  
  
 `<overflow attr1="data">content</overflow>`  
  
 `</Parent>`  
  
 `<Parent PersonID="P2" PersonName="Joe">`  
  
 `<overflow attr2="data" />`  
  
 `</Parent>`  
  
 `<Parent PersonID="P3" PersonName="Joe">`  
  
 `<overflow attr3="data" PersonID="P">`  
  
 `<name>PersonName</name>`  
  
 `</overflow>`  
  
 `</Parent>`  
  
 <span data-ttu-id="98a1b-121">In diesem Abfrageelement wird *-Direktive angegeben* für das `PersonName` -Attribut angegeben.</span><span class="sxs-lookup"><span data-stu-id="98a1b-121">In this query element, *directive* is specified for `PersonName` attribute.</span></span> <span data-ttu-id="98a1b-122">Dadurch wird `PersonName` als Unterelement des einschließenden <`Parent`>-Elements hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="98a1b-122">This results in `PersonName` being added as a subelement of the enclosing <`Parent`> element.</span></span> <span data-ttu-id="98a1b-123">Die Attribute von <`xmltext`> werden weiterhin an das einschließende <`Parent`>-Element angefügt.</span><span class="sxs-lookup"><span data-stu-id="98a1b-123">The attributes of the <`xmltext`> are still appended to the enclosing <`Parent`> element.</span></span> <span data-ttu-id="98a1b-124">Der Inhalt des <`overflow`>-Elements (Unterelemente usw.) wird den anderen Unterelementen der einschließenden <`Parent`>-Elemente vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="98a1b-124">The contents of the <`overflow`> element, subelements, are prepended to the other subelements of the enclosing <`Parent`> elements.</span></span>  
  
```  
SELECT 1      AS Tag, NULL as parent,  
       PersonID   AS [Parent!1!PersonID],  
       PersonName AS [Parent!1!PersonName!element], -- element directive  
       Overflow   AS [Parent!1!!XMLTEXT]  
FROM Person  
FOR XML EXPLICIT;  
```  
  
 <span data-ttu-id="98a1b-125">Dies ist das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="98a1b-125">This is the result:</span></span>  
  
 `<Parent PersonID="P1" attr1="data">content<PersonName>Joe</PersonName>`  
  
 `</Parent>`  
  
 `<Parent PersonID="P2" attr2="data">`  
  
 `<PersonName>Joe</PersonName>`  
  
 `</Parent>`  
  
 `<Parent PersonID="P3" attr3="data">`  
  
 `<name>PersonName</name>`  
  
 `<PersonName>Joe</PersonName>`  
  
 `</Parent>`  
  
 <span data-ttu-id="98a1b-126">Wenn die Daten der `XMLTEXT` -Spalte Attribute für das Stammelement enthalten, werden diese Attribute nicht im XML-Datenschema angezeigt, und der MSXML-Parser führt keine Überprüfung des resultierenden XML-Dokumentfragments aus.</span><span class="sxs-lookup"><span data-stu-id="98a1b-126">If the `XMLTEXT` column data contains attributes on the root element, these attributes are not shown in the XML data schema and the MSXML parser does not validate the resulting XML document fragment.</span></span> <span data-ttu-id="98a1b-127">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="98a1b-127">For example:</span></span>  
  
```  
SELECT 1 AS Tag,  
       0 ASParent,  
       N'<overflow a="1"/>' AS 'overflow!1!!xmltext'  
FOR XML EXPLICIT, xmldata;  
```  
  
 <span data-ttu-id="98a1b-128">Dies ist das Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="98a1b-128">This is the result.</span></span> <span data-ttu-id="98a1b-129">Beachten Sie, dass das overflow-Attribut `a` im zurückgegebenen Schema fehlt:</span><span class="sxs-lookup"><span data-stu-id="98a1b-129">Note that in the returned schema, the overflow attribute `a` is missing from the schema:</span></span>  
  
 `<Schema name="Schema2"`  
  
 `xmlns="urn:schemas-microsoft-com:xml-data"`  
  
 `xmlns:dt="urn:schemas-microsoft-com:datatypes">`  
  
 `<ElementType name="overflow" content="mixed" model="open">`  
  
 `</ElementType>`  
  
 `</Schema>`  
  
 `<overflow xmlns="x-schema:#Schema2" a="1">`  
  
 `</overflow>`  
  
## <a name="see-also"></a><span data-ttu-id="98a1b-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="98a1b-130">See Also</span></span>  
 [<span data-ttu-id="98a1b-131">Verwenden des EXPLICIT-Modus mit FOR XML</span><span class="sxs-lookup"><span data-stu-id="98a1b-131">Use EXPLICIT Mode with FOR XML</span></span>](use-explicit-mode-with-for-xml.md)  
  
  
