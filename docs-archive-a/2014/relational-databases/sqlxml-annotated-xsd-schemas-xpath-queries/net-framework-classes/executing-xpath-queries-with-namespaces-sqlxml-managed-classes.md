---
title: Ausführen von XPath-Abfragen mit Namespaces (verwaltete SQLXML-Klassen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- namespaces property
- XPath queries [SQLXML], SQLXML Managed Classes
- queries [SQLXML], SQLXML Managed Classes
- XPath queries [SQLXML], namespaces
- Managed Classes [SQLXML], executing XPath queries
- SQLXML Managed Classes, executing XPath queries
- namespaces [SQLXML], XPath queries
ms.assetid: c6fc46d8-6b42-4992-a8f1-a8d4b8886e6e
author: rothja
ms.author: jroth
ms.openlocfilehash: a2d726de95929709c1ae958ee22388df3195bc84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607611"
---
# <a name="executing-xpath-queries-with-namespaces-sqlxml-managed-classes"></a><span data-ttu-id="7bb9a-102">Ausführen von XPath-Abfragen mit Namespaces (Verwaltete SQLXML-Klassen)</span><span class="sxs-lookup"><span data-stu-id="7bb9a-102">Executing XPath Queries with Namespaces (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="7bb9a-103">XPath-Abfragen können Namespaces enthalten.</span><span class="sxs-lookup"><span data-stu-id="7bb9a-103">XPath queries can include namespaces.</span></span> <span data-ttu-id="7bb9a-104">Wenn die Schemaelemente mit Namespace angegeben wurden (einen Zielnamespace verwenden), dann müssen mit diesem Schema ausgeführte XPath-Abfragen diesen Namespace angeben.</span><span class="sxs-lookup"><span data-stu-id="7bb9a-104">If the schema elements are namespace-qualified (use a target namespace), the XPath queries against the schema must specify the namespace.</span></span>  
  
 <span data-ttu-id="7bb9a-105">Weil die Verwendung des Platzhalterzeichens (\*) in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0 nicht unterstützt wird, müssen Sie die XPath-Abfrage mithilfe eines Namespacepräfixes angeben.</span><span class="sxs-lookup"><span data-stu-id="7bb9a-105">Because the wildcard character (\*) is not supported in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, you must specify the XPath query by using a namespace prefix.</span></span> <span data-ttu-id="7bb9a-106">Um das Präfix aufzulösen, geben Sie mit der Namespace-Eigenschaft die Namespace Bindung an.</span><span class="sxs-lookup"><span data-stu-id="7bb9a-106">To resolve the prefix, use the namespaces property to specify the namespace binding.</span></span>  
  
 <span data-ttu-id="7bb9a-107">Im folgenden Beispiel gibt die XPath-Abfrage Namespaces mit den Platzhalter Zeichen ( \* ) und den XPath-Funktionen local-Name () und Namespace-URI () an.</span><span class="sxs-lookup"><span data-stu-id="7bb9a-107">In the following example, the XPath query specifies namespaces by using the wildcard character (\*) and the local-name() and namespace-uri() XPath functions.</span></span> <span data-ttu-id="7bb9a-108">Diese XPath-Abfrage gibt alle Elemente zurück, bei denen der lokale Name `Employee` und der Namespace-URI `urn:myschema:Contacts` lautet:</span><span class="sxs-lookup"><span data-stu-id="7bb9a-108">This XPath query returns all the elements where the local name is `Employee` and the namespace URI is `urn:myschema:Contacts`:</span></span>  
  
```  
/*[local-name() = 'Contact' and namespace-uri() = 'urn:myschema:Contacts']  
```  
  
 <span data-ttu-id="7bb9a-109">Geben Sie in SQLXML 4.0 diese XPath-Abfrage mit einem Namespacepräfix an.</span><span class="sxs-lookup"><span data-stu-id="7bb9a-109">In SQLXML 4.0, specify this XPath query with a namespace prefix.</span></span> <span data-ttu-id="7bb9a-110">Ein Beispiel ist `x:Contact`, wobei `x` für das Namespacepräfix steht.</span><span class="sxs-lookup"><span data-stu-id="7bb9a-110">An example is `x:Contact`, where `x` is the namespace prefix.</span></span> <span data-ttu-id="7bb9a-111">Betrachten Sie folgendes XSD-Schema:</span><span class="sxs-lookup"><span data-stu-id="7bb9a-111">Consider the following XSD schema:</span></span>  
  
```  
<schema xmlns="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema"  
            xmlns:con="urn:myschema:Contacts"  
            targetNamespace="urn:myschema:Contacts">  
<complexType name="ContactType">  
  <attribute name="CID" sql:field="ContactID" type="ID"/>  
  <attribute name="FName" sql:field="FirstName" type="string"/>  
  <attribute name="LName" sql:field="LastName"/>   
</complexType>  
<element name="Contact" type="con:ContactType" sql:relation="Person.Contact"/>  
</schema>  
```  
  
 <span data-ttu-id="7bb9a-112">Da dieses Schema den Ziel Namespace definiert, muss eine XPath-Abfrage (z. b. "Employee") für dieses Schema den Namespace enthalten.</span><span class="sxs-lookup"><span data-stu-id="7bb9a-112">Because this schema defines the target namespace, an XPath query (such as "Employee") against this schema must include the namespace.</span></span>  
  
 <span data-ttu-id="7bb9a-113">Die folgende C#-Beispielanwendung führt mit dem angegebenen XSD-Schema (MySchema.xml) eine XPath-Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="7bb9a-113">The following C# sample application executes an XPath query against the preceding XSD schema (MySchema.xml).</span></span> <span data-ttu-id="7bb9a-114">Um das Präfix aufzulösen, geben Sie die Namespace Bindung mithilfe der Namespaces-Eigenschaft des SqlXmlCommand-Objekts an.</span><span class="sxs-lookup"><span data-stu-id="7bb9a-114">To resolve the prefix, specify the namespace binding by using the Namespaces property of the SqlXmlCommand object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7bb9a-115">Im Code müssen Sie den Namen der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in der Verbindungszeichenfolge bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="7bb9a-115">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
      public static int testXPath()  
      {  
         //Stream strm;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandText = "x:Contact[@CID='1']";  
         cmd.CommandType = SqlXmlCommandType.XPath;  
         cmd.RootTag = "ROOT";  
         cmd.Namespaces = "xmlns:x='urn:myschema:Contacts'";  
         cmd.SchemaPath = "MySchema.xml";  
         using (Stream strm = cmd.ExecuteStream()){  
            using (StreamReader sr = new StreamReader(strm)){  
               Console.WriteLine(sr.ReadToEnd());  
            }  
         }  
         return 0;  
      }  
      public static int Main(String[] args)  
      {  
         testXPath();  
         return 0;  
      }  
   }  
```  
  
 <span data-ttu-id="7bb9a-116">Um das Beispiel zu testen, muss auf dem Computer [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installiert sein.</span><span class="sxs-lookup"><span data-stu-id="7bb9a-116">To test this example, you must have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="7bb9a-117">So testen Sie die Anwendung</span><span class="sxs-lookup"><span data-stu-id="7bb9a-117">To test the application</span></span>  
  
1.  <span data-ttu-id="7bb9a-118">Speichern Sie das oben in diesem Beispiel bereitgestellte XSD-Schema (MySchema.xml) in einem Ordner.</span><span class="sxs-lookup"><span data-stu-id="7bb9a-118">Save the XSD schema (MySchema.xml) that is provided in this example in a folder.</span></span>  
  
2.  <span data-ttu-id="7bb9a-119">Speichern Sie den c#-Code (DocSample.cs), der in diesem Beispiel bereitgestellt wird, im selben Ordner, in dem das Schema gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="7bb9a-119">Save the C# code (DocSample.cs) that is provided in this example in the same folder in which the schema is stored.</span></span> <span data-ttu-id="7bb9a-120">(Wenn Sie die Dateien in einem anderen Ordner speichern, müssen Sie den Code bearbeiten und den entsprechenden Verzeichnispfad für das Zuordnungsschema angeben.)</span><span class="sxs-lookup"><span data-stu-id="7bb9a-120">(If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.)</span></span>  
  
3.  <span data-ttu-id="7bb9a-121">Kompilieren Sie den Code.</span><span class="sxs-lookup"><span data-stu-id="7bb9a-121">Compile the code.</span></span> <span data-ttu-id="7bb9a-122">Verwenden Sie zur Kompilierung des Codes an der Eingabeaufforderung die folgende Zeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="7bb9a-122">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="7bb9a-123">Dadurch wird eine ausführbare Datei (DocSample.exe) erstellt.</span><span class="sxs-lookup"><span data-stu-id="7bb9a-123">This creates an executable (DocSample.exe).</span></span>  
  
4.  <span data-ttu-id="7bb9a-124">Führen Sie DocSample.exe an der Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="7bb9a-124">At the command prompt, execute DocSample.exe.</span></span>  
  
  
