---
title: Hinzufügen von Geschäftslogik zu XML-Daten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- business logic [XML]
ms.assetid: 0877fb38-f1a2-43d8-86cf-4754be224dc1
author: rothja
ms.author: jroth
ms.openlocfilehash: 5bf8e9edc36e9c420faa92f2db1a92c311194e99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615875"
---
# <a name="add-business-logic-to-xml-data"></a><span data-ttu-id="ad2ff-102">Hinzufügen von Geschäftslogik zu XML-Daten</span><span class="sxs-lookup"><span data-stu-id="ad2ff-102">Add Business Logic to XML Data</span></span>
  <span data-ttu-id="ad2ff-103">Ihre Geschäftslogik kann auf verschiedene Art und Weise den XML-Daten hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="ad2ff-103">Your business logic can be added to XML data in several ways:</span></span>  
  
-   <span data-ttu-id="ad2ff-104">Sie können Zeilen- oder Spalteneinschränkungen schreiben, um beim Einfügen und Bearbeiten von XML-Daten domänenspezifische Einschränkungen zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-104">You can write row or column constraints to enforce domain-specific constraints during insertion and modification of XML data.</span></span>  
  
-   <span data-ttu-id="ad2ff-105">Sie können einen Trigger für die XML-Spalte schreiben, der ausgelöst wird, wenn Sie Werte in die Spalte einfügen oder aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-105">You can write a trigger on the XML column that fires when you insert or update values in the column.</span></span> <span data-ttu-id="ad2ff-106">Der Trigger kann domänenspezifische Überprüfungsregeln enthalten oder Eigenschaftentabellen auffüllen.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-106">The trigger can contain domain-specific validation rules or populate property tables.</span></span>  
  
-   <span data-ttu-id="ad2ff-107">Die Datenbank-Engine ist in der Lage, verwalteten Code auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-107">The Database Engine includes the ability execute managed code.</span></span> <span data-ttu-id="ad2ff-108">Sie können diese CLR-Integration (Common Language Runtime) nutzen, um verwalteten Code zu schreiben, an den Sie XML-Werte übergeben, und die vom System.Xml-Namespace bereitgestellten Möglichkeiten zur XML-Verarbeitung verwenden.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-108">You can use this common language runtime (CLR) integration to write functions in managed code to which you pass XML values, and use XML processing capabilities provided by the System.Xml namespace.</span></span> <span data-ttu-id="ad2ff-109">Ein Beispiel hierfür ist die Anwendung der XSL-Transformation auf XML-Daten.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-109">An example is to apply XSL transformation to XML data.</span></span> <span data-ttu-id="ad2ff-110">Alternativ können Sie den XML-Code in eine oder mehrere verwaltete Klassen deserialisieren und diese mithilfe von verwaltetem Code verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-110">Alternatively, you can deserialize the XML into one or more managed classes and operate on them by using managed code.</span></span>  
  
-   <span data-ttu-id="ad2ff-111">Sie können gespeicherte Transact-SQL-Prozeduren und -Funktionen schreiben, mit denen das Verarbeiten der XML-Spalte für Ihre Unternehmensanforderungen gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-111">You can write Transact-SQL stored procedures and functions that start the processing on the XML column for your business needs.</span></span>  
  
## <a name="example-applying-xsl-transformation"></a><span data-ttu-id="ad2ff-112">Beispiel: Anwenden von XSL-Transformationen</span><span class="sxs-lookup"><span data-stu-id="ad2ff-112">Example: Applying XSL Transformation</span></span>  
 <span data-ttu-id="ad2ff-113">Angenommen, eine CLR-Funktion **TransformXML ()** nimmt eine `xml` -Datentyp Instanz und eine in einer Datei gespeicherte XSL-Transformation an, wendet die Transformation auf die XML-Daten an und gibt dann den transformierten XML-Code im Ergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-113">Consider a CLR function **TransformXml()** that accepts an `xml` data type instance and an XSL transformation stored in a file, applies the transformation to the XML data, and then returns the transformed XML in the result.</span></span> <span data-ttu-id="ad2ff-114">Es folgt eine Skeleton-Funktion, die in C# geschrieben ist:</span><span class="sxs-lookup"><span data-stu-id="ad2ff-114">Following is a skeleton function that is written in C#:</span></span>  
  
```  
public static SqlXml TransformXml (SqlXml XmlData, string xslPath) {  
   // Load XSL transformation  
   XslCompiledTransform xform = new XslCompiledTransform();  
   XPathDocument xslDoc = new XPathDocument (xslPath);  
   xform.Load(xslDoc);  
  
   // Load XML data   
   XPathDocument xDoc = new XPathDocument (XmlData.CreateReader());  
  
   // Return the transformed value  
   MemoryStream xsltResult = new MemoryStream();  
   xform.Transform(xDoc, null, xsltResult);  
   SqlXml retSqlXml = new SqlXml(xsltResult);  
   return (retSqlXml);  
}   
```  
  
 <span data-ttu-id="ad2ff-115">Nachdem die Assembly registriert und eine benutzerdefinierte [!INCLUDE[tsql](../../includes/tsql-md.md)] -Funktion erstellt wurde ( **SqlXslTransform()** entsprechend **TransformXml()** ), kann die Funktion von Transact-SQL aus aufgerufen werden, wie in der folgenden Abfrage gezeigt:</span><span class="sxs-lookup"><span data-stu-id="ad2ff-115">After the assembly is registered and a user-defined [!INCLUDE[tsql](../../includes/tsql-md.md)] function is created, **SqlXslTransform()** corresponding to **TransformXml()**, the function can be invoked from Transact-SQL as shown in the following query:</span></span>  
  
```  
SELECT SqlXslTransform (xCol, 'C:\MyFile\xsltransform.xsl')  
FROM    T  
WHERE  xCol.exist('/book/title/text()[contains(.,"custom")]') =1;  
```  
  
 <span data-ttu-id="ad2ff-116">Das Abfrageergebnis enthält ein Rowset der transformierten XML-Daten.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-116">The query result contains a rowset of the transformed XML.</span></span>  
  
 <span data-ttu-id="ad2ff-117">Die CLR-Integration in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] erweitert die Möglichkeiten zum Zerlegen der XML-Daten in Tabellen oder zum Höherstufen von Eigenschaften sowie die Möglichkeiten zum Abfragen von XML-Daten durch Verwenden von verwalteten Klassen im System.Xml-Namespace.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-117">The CLR integration into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] expands the possibilities for decomposing XML data into tables or property promotion, and querying XML data by using managed classes in the System.Xml namespace.</span></span> <span data-ttu-id="ad2ff-118">Weitere Informationen finden Sie unter [XML-Daten &#40;SQL Server&#41;](xml-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ad2ff-118">For more information, see [XML Data &#40;SQL Server&#41;](xml-data-sql-server.md).</span></span>  
  
  
