---
title: Ausführen von XPath-Abfragen (verwaltete SQLXML-Klassen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], SQLXML Managed Classes
- queries [SQLXML], SQLXML Managed Classes
- Managed Classes [SQLXML], executing XPath queries
- mapping schema [SQLXML], XPath queries
- SQLXML Managed Classes, executing XPath queries
ms.assetid: 8bef4c4d-bf0e-4236-a875-fd7d3e058396
author: rothja
ms.author: jroth
ms.openlocfilehash: d8f5fd2612a0992f18e0b7f32c749c352d29d2b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607612"
---
# <a name="executing-xpath-queries-sqlxml-managed-classes"></a><span data-ttu-id="e71a3-102">Ausführen von XPath-Abfragen (verwaltete SQLXML-Klassen)</span><span class="sxs-lookup"><span data-stu-id="e71a3-102">Executing XPath Queries (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="e71a3-103">In diesem Beispiel wird dargestellt, wie XPath-Abfragen für ein Zuordnungsschema ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e71a3-103">This example illustrates how XPath queries are executed against a mapping schema.</span></span>  
  
 <span data-ttu-id="e71a3-104">Betrachten wir das folgende Schema:</span><span class="sxs-lookup"><span data-stu-id="e71a3-104">Consider this schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Con" sql:relation="Person.Contact" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="FName"    
                     sql:field="FirstName"   
                     type="xsd:string" />   
        <xsd:element name="LName"    
                     sql:field="LastName"    
                     type="xsd:string" />  
     </xsd:sequence>  
     <xsd:attribute name="ContactID" type="xsd:integer" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="e71a3-105">Diese C#-Anwendung führt eine XPath-Abfrage für das Schema (MySchema.xml) aus.</span><span class="sxs-lookup"><span data-stu-id="e71a3-105">This C# application executes an XPath query against this schema (MySchema.xml).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e71a3-106">Im Code müssen Sie den Namen der Instanz von Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in der Verbindungszeichenfolge bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e71a3-106">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
  
      public static int testXPath()  
      {  
         Stream strm;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandText = "Con";  
         cmd.CommandType = SqlXmlCommandType.XPath;  
         cmd.RootTag = "ROOT";  
         cmd.SchemaPath = "MySchema.xml";  
         strm = cmd.ExecuteStream();  
         using (StreamReader sr = new StreamReader(strm)){  
            Console.WriteLine(sr.ReadToEnd());  
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
  
### <a name="to-test-the-application"></a><span data-ttu-id="e71a3-107">So testen Sie die Anwendung</span><span class="sxs-lookup"><span data-stu-id="e71a3-107">To test the application</span></span>  
  
1.  <span data-ttu-id="e71a3-108">Stellen Sie sicher, dass [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="e71a3-108">Make sure that you have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
2.  <span data-ttu-id="e71a3-109">Speichern Sie das oben in diesem Beispiel bereitgestellte XSD-Schema (MySchema.xml) in einem Ordner.</span><span class="sxs-lookup"><span data-stu-id="e71a3-109">Save the XSD schema (MySchema.xml) that is provided in this example in a folder.</span></span>  
  
3.  <span data-ttu-id="e71a3-110">Speichern Sie den c#-Code (DocSample.cs), der in diesem Beispiel bereitgestellt wird, im selben Ordner, in dem das Schema gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="e71a3-110">Save the C# code (DocSample.cs) that is provided in this example in the same folder in which the schema is stored.</span></span> <span data-ttu-id="e71a3-111">(Wenn Sie die Dateien in einem anderen Ordner speichern, müssen Sie den Code bearbeiten und den entsprechenden Verzeichnispfad für das Zuordnungsschema angeben.)</span><span class="sxs-lookup"><span data-stu-id="e71a3-111">(If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.)</span></span>  
  
4.  <span data-ttu-id="e71a3-112">Kompilieren Sie den Code.</span><span class="sxs-lookup"><span data-stu-id="e71a3-112">Compile the code.</span></span> <span data-ttu-id="e71a3-113">Verwenden Sie zur Kompilierung des Codes an der Eingabeaufforderung die folgende Zeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="e71a3-113">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="e71a3-114">Dadurch wird eine ausführbare Datei (DocSample.exe) erstellt.</span><span class="sxs-lookup"><span data-stu-id="e71a3-114">This creates an executable (DocSample.exe).</span></span>  
  
5.  <span data-ttu-id="e71a3-115">Führen Sie DocSample.exe an der Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="e71a3-115">At the command prompt, execute DocSample.exe.</span></span>  
  
  
