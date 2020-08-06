---
title: Validieren von XML-Dokumenten mit dem XML-Task | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- XML validation
- XML, validating
ms.assetid: 224fc025-c21f-4d43-aa9d-5ffac337f9b0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 633a269f53c85353c956b33bff8fd3af518dad56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607906"
---
# <a name="validate-xml-with-the-xml-task"></a><span data-ttu-id="52d81-102">Validate XML with the XML Task</span><span class="sxs-lookup"><span data-stu-id="52d81-102">Validate XML with the XML Task</span></span>
  <span data-ttu-id="52d81-103">Validieren Sie XML-Dokumente und erhalten Sie eine umfangreiche Fehlerausgabe durch die Aktivierung der Eigenschaft `ValidationDetails` des XML-Tasks.</span><span class="sxs-lookup"><span data-stu-id="52d81-103">Validate XML documents and get rich error output by enabling the `ValidationDetails` property of the XML Task.</span></span>

 <span data-ttu-id="52d81-104">Die folgende Abbildung zeigt den **XML-Task-Editor** eingestellt für die XML-Validierung mit umfassender Fehlerausgabe.</span><span class="sxs-lookup"><span data-stu-id="52d81-104">The following screen shot shows the **XML Task Editor** with the settings required for XML validation with rich error output.</span></span>

 <span data-ttu-id="52d81-105">![XML-Taskeigenschaften im XML-Task-Editor](../media/xmltaskproperties.jpg "XML-Taskeigenschaften im XML-Task-Editor")</span><span class="sxs-lookup"><span data-stu-id="52d81-105">![XML task properties in the XML Task Editor](../media/xmltaskproperties.jpg "XML task properties in the XML Task Editor")</span></span>

 <span data-ttu-id="52d81-106">Bevor die Eigenschaft `ValidationDetails` verfügbar war, gab die XML-Validierung durch den XML-Task nur „true“ oder „false“ als Ergebnis zurück, ohne Informationen zu Fehlern oder wo diese auftraten.</span><span class="sxs-lookup"><span data-stu-id="52d81-106">Before the `ValidationDetails` property was available, XML validation by the XML Task returned only a true or false result, with no information about errors or their locations.</span></span> <span data-ttu-id="52d81-107">Wenn Sie jetzt die Eigenschaft `ValidationDetails` auf „true“ festlegen, enthält die Ausgabedatei ausführliche Informationen zu jedem Fehler, einschließlich der Zeilennummer und der Position.</span><span class="sxs-lookup"><span data-stu-id="52d81-107">Now, when you set `ValidationDetails` to true, the output file contains detailed information about every error including the line number and the position.</span></span> <span data-ttu-id="52d81-108">Sie können diese Informationen verwenden, um Fehler in XML-Dokumenten zu verstehen, zu finden und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="52d81-108">You can use this information to understand, locate, and fix errors in XML documents.</span></span>

 <span data-ttu-id="52d81-109">Die XML-Validierungsfunktion lässt sich problemlos auch für große XML-Dokumente und eine große Anzahl von Fehlern skalieren.</span><span class="sxs-lookup"><span data-stu-id="52d81-109">The XML validation functionality scales easily for large XML documents and large numbers of errors.</span></span> <span data-ttu-id="52d81-110">Da die Ausgabedatei selbst im XML-Format ist, können Sie die Ausgabe abfragen und analysieren.</span><span class="sxs-lookup"><span data-stu-id="52d81-110">Since the output file itself is in XML format, you can query and analyze the output.</span></span> <span data-ttu-id="52d81-111">Enthält die Ausgabe beispielsweise sehr viele Fehler, so können Sie diese, wie in diesem Thema beschrieben, mit einer [!INCLUDE[tsql](../../../includes/tsql-md.md)] -Abfrage gruppieren.</span><span class="sxs-lookup"><span data-stu-id="52d81-111">For example, if the output contains a large number of errors, you can group the errors by using a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query, as described in this topic.</span></span>

> [!NOTE]
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="52d81-112">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]( [!INCLUDE[ssIS](../../includes/ssis-md.md)] ) hat die- `ValidationDetails` Eigenschaft in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] Service Pack 2 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="52d81-112">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) introduced the `ValidationDetails` property in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] Service Pack 2.</span></span> <span data-ttu-id="52d81-113">Die-Eigenschaft ist auch in [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] und in SQL Server 2016 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="52d81-113">The property is also available in [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] and in SQL Server 2016.</span></span>

## <a name="sample-output-for-xml-thats-valid"></a><span data-ttu-id="52d81-114">Beispielausgabe für eine XML-Datei ohne Fehler</span><span class="sxs-lookup"><span data-stu-id="52d81-114">Sample output for XML that's valid</span></span>
 <span data-ttu-id="52d81-115">Hier ist eine Beispiel-Ausgabedatei mit Validierungsergebnissen für eine gültige XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="52d81-115">Here is a sample output file with validation results for a valid XML file.</span></span>

```xml

<root xmlns:ns="https://schemas.microsoft.com/xmltools/2002/xmlvalidation">
    <metadata>
        <result>true</result>
        <errors>0</errors>
        <warnings>0</warnings>
        <startTime>2015-05-28T10:27:22.087</startTime>
        <endTime>2015-05-28T10:29:07.007</endTime>
        <xmlFile>d:\Temp\TestData.xml</xmlFile>
        <xsdFile>d:\Temp\TestSchema.xsd</xsdFile>
    </metadata>
    <messages />
</root>
```

## <a name="sample-output-for-xml-thats-not-valid"></a><span data-ttu-id="52d81-116">Beispielausgabe für eine XML-Datei mit Fehlern</span><span class="sxs-lookup"><span data-stu-id="52d81-116">Sample output for XML that's not valid</span></span>
 <span data-ttu-id="52d81-117">Hier ist eine Beispiel-Ausgabedatei mit Validierungsergebnissen für eine XML-Datei mit einer geringen Anzahl an Fehlern.</span><span class="sxs-lookup"><span data-stu-id="52d81-117">Here is a sample output file with validation results for an XML file that contains a small number of errors.</span></span> <span data-ttu-id="52d81-118">Der Text der \<error>-Elemente wurde zur besseren Lesbarkeit umbrochen.</span><span class="sxs-lookup"><span data-stu-id="52d81-118">The text of the \<error> elements has been wrapped for readability.</span></span>

```xml

<root xmlns:ns="https://schemas.microsoft.com/xmltools/2002/xmlvalidation">
    <metadata>
        <result>false</result>
        <errors>2</errors>
        <warnings>0</warnings>
        <startTime>2015-05-28T10:45:09.538</startTime>
        <endTime>2015-05-28T10:45:09.558</endTime>
        <xmlFile>C:\Temp\TestData.xml</xmlFile>
        <xsdFile>C:\Temp\TestSchema.xsd</xsdFile>
    </metadata>
    <messages>
        <error line="5" position="26">The 'ApplicantRole' element is invalid - The value 'wer3' is invalid
    according to its datatype 'ApplicantRoleType' - The Enumeration constraint failed.</error>
        <error line="16" position="28">The 'Phone' element is invalid - The value 'we3056666666' is invalid
     according to its datatype 'phone' - The Pattern constraint failed.</error>
    </messages>
</root>
```

## <a name="analyze-xml-validation-output-with-a-transact-sql-query"></a><span data-ttu-id="52d81-119">Analysieren der XML-Validierungsausgabe mit einer Transact-SQL-Abfrage</span><span class="sxs-lookup"><span data-stu-id="52d81-119">Analyze XML validation output with a Transact-SQL query</span></span>
 <span data-ttu-id="52d81-120">Wenn die Ausgabe der XML-Validierung sehr viele Fehler enthält, können Sie die Ausgabe mit einer [!INCLUDE[tsql](../../../includes/tsql-md.md)] -Abfrage in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]laden.</span><span class="sxs-lookup"><span data-stu-id="52d81-120">If the output of XML validation contains a large number of errors, you can use a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query to load the output in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="52d81-121">Danach können Sie die Fehlerliste mit allen Funktionen der Programmiersprache T-SQL, einschließlich WHERE, GROUP BY, ORDER BY, JOIN usw. analysieren.</span><span class="sxs-lookup"><span data-stu-id="52d81-121">Then you can analyze the error list with all the capabilities of the T-SQL language including WHERE, GROUP BY, ORDER BY, JOIN, and so forth.</span></span>

```sql
DECLARE @xml XML;

SELECT @xml = XmlDoc   
FROM OPENROWSET (BULK N'C:\Temp\XMLValidation_2016-02-212T10-41-00.xml', SINGLE_BLOB) AS Tab(XmlDoc);

-- Query # 1, flat list of errors
-- convert to relational/rectangular
;WITH XMLNAMESPACES ('https://schemas.microsoft.com/xmltools/2002/xmlvalidation' AS ns), rs AS
(
SELECT col.value('@line','INT') AS line
     , col.value('@position','INT') AS position
     , col.value('.','VARCHAR(1024)') AS error
FROM @XML.nodes('/root/messages/error') AS tab(col)
)
SELECT * FROM rs;
-- WHERE error LIKE '%whatever_string%'

-- Query # 2, count of errors grouped by the error message
-- convert to relational/rectangular
;WITH XMLNAMESPACES ('https://schemas.microsoft.com/xmltools/2002/xmlvalidation' AS ns), rs AS
(
SELECT col.value('@line','INT') AS line
     , col.value('@position','INT') AS position
     , col.value('.','VARCHAR(1024)') AS error
FROM @XML.nodes('/root/messages/error') AS tab(col)
)
SELECT COALESCE(error,'Total # of errors:') AS [error], COUNT(*) AS [counter]
FROM rs
GROUP BY GROUPING SETS ((error), ())
ORDER BY 2 DESC, COALESCE(error, 'Z');

```

 <span data-ttu-id="52d81-122">Hier ist das Ergebnis in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] der zweiten Beispielabfrage aus dem vorangegangenen Text.</span><span class="sxs-lookup"><span data-stu-id="52d81-122">Here is the result in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] of the second sample query shown in the preceding text.</span></span>

 <span data-ttu-id="52d81-123">![Abfrage zum Gruppieren von XML-Fehlern in Management Studio](../media/queryforxmlerrors.jpg "Abfrage zum Gruppieren von XML-Fehlern in Management Studio")</span><span class="sxs-lookup"><span data-stu-id="52d81-123">![Query to group XML errors in Management Studio](../media/queryforxmlerrors.jpg "Query to group XML errors in Management Studio")</span></span>

## <a name="see-also"></a><span data-ttu-id="52d81-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="52d81-124">See Also</span></span>
 <span data-ttu-id="52d81-125">Editor für [den XML-](xml-task.md) Task- [Editor &#40;Seite Allgemein&#41;](../xml-task-editor-general-page.md)</span><span class="sxs-lookup"><span data-stu-id="52d81-125">[XML Task](xml-task.md) [XML Task Editor &#40;General Page&#41;](../xml-task-editor-general-page.md)</span></span>


