---
title: Angeben von XPath-Variablen in XPath-Abfragen (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], XPath variables
- XPath variables [SQLXML]
ms.assetid: c11ab816-11b8-4131-8b77-c03fe500fa10
author: rothja
ms.author: jroth
ms.openlocfilehash: 5045831f627722f7dbb9a9189be5c48d830f2add
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608477"
---
# <a name="specifying-xpath-variables-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="314b8-102">Angeben von XPath-Variablen in XPath-Abfragen (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="314b8-102">Specifying XPath Variables in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="314b8-103">In den folgenden Beispielen wird gezeigt, wie XPath-Variablen in XPath-Abfragen übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="314b8-103">The following examples show how XPath variables are passed in XPath queries.</span></span> <span data-ttu-id="314b8-104">Die XPath-Abfragen in diesen Beispielen werden für das in SampleSchema1.xml enthaltene Zuordnungsschema angegeben.</span><span class="sxs-lookup"><span data-stu-id="314b8-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="314b8-105">Weitere Informationen zu diesem Beispiel Schema finden Sie unter [Beispiel: XSD-Schema mit Anmerkungen für XPath-Beispiele &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="314b8-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="314b8-106">Beispiele</span><span class="sxs-lookup"><span data-stu-id="314b8-106">Examples</span></span>  
  
### <a name="a-use-the-xpath-variables"></a><span data-ttu-id="314b8-107">A.</span><span class="sxs-lookup"><span data-stu-id="314b8-107">A.</span></span> <span data-ttu-id="314b8-108">Verwenden der XPath-Variablen</span><span class="sxs-lookup"><span data-stu-id="314b8-108">Use the XPath variables</span></span>  
 <span data-ttu-id="314b8-109">Eine Beispielvorlage besteht aus zwei XPath-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="314b8-109">A sample template consists of two XPath queries.</span></span> <span data-ttu-id="314b8-110">Jede der XPath-Abfragen verwendet einen Parameter.</span><span class="sxs-lookup"><span data-stu-id="314b8-110">Each of the XPath queries takes one parameter.</span></span> <span data-ttu-id="314b8-111">Die Vorlage gibt außerdem Standardwerte für diese Parameter an.</span><span class="sxs-lookup"><span data-stu-id="314b8-111">The template also specifies default values for these parameters.</span></span> <span data-ttu-id="314b8-112">Die Standardwerte werden verwendet, wenn keine Parameterwerte angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="314b8-112">The default values are used if parameter values are not specified.</span></span> <span data-ttu-id="314b8-113">In werden zwei Parameter mit Standardwerten angegeben **\<sql:header>** .</span><span class="sxs-lookup"><span data-stu-id="314b8-113">Two parameters with default values are specified in **\<sql:header>**.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:header>  
     <sql:param name='CustomerID'>1</sql:param>  
     <sql:param name='ContactID'>1</sql:param>   
  </sql:header>  
  <sql:xpath-query mapping-schema="SampleSchema1.xml">  
    Customer[@CustomerID=$CustomerID]   
  </sql:xpath-query >  
  <sql:xpath-query mapping-schema="SampleSchema1.xml">  
   Contact[@ContactID=$ContactID]   
  </sql:xpath-query>  
</ROOT>  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="314b8-114">So testen Sie die XPath-Abfrage mit dem Zuordnungsschema</span><span class="sxs-lookup"><span data-stu-id="314b8-114">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="314b8-115">Kopieren Sie den [Beispiel Schema Code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) , und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="314b8-115">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="314b8-116">Speichern Sie die Datei unter dem Dateinamen SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="314b8-116">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="314b8-117">Erstellen Sie die folgende Vorlage (XPathVariables.xml), und speichern Sie sie im folgenden Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="314b8-117">Create the following template (XPathVariables.xml) and save it in the directory where:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:header>  
         <sql:param name='CustomerID'>1</sql:param>  
         <sql:param name='ContactID'>1</sql:param>   
      </sql:header>  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        Customer[@CustomerID=$CustomerID]   
      </sql:xpath-query >  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
       Contact[@ContactID=$ContactID]   
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="314b8-118">Der für das Zuordnungsschema (SampleSchema1.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="314b8-118">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="314b8-119">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="314b8-119">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="314b8-120">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="314b8-120">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span> <span data-ttu-id="314b8-121">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="314b8-121">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="314b8-122">In diesem Beispiel werden keine Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="314b8-122">In this example, no parameters are passed.</span></span> <span data-ttu-id="314b8-123">Stattdessen werden die Standardparameterwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="314b8-123">Therefore, the default parameter values are used.</span></span>  
  
  
