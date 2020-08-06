---
title: Ausführen von Vorlagen Dateien mit der CommandStream-Eigenschaft | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- Managed Classes [SQLXML], executing template files
- SQLXML Managed Classes, executing template files
- templates [SQLXML], SQLXML Managed Classes
- CommandStream property
ms.assetid: 55c564e3-56d1-4d85-bcaa-703e2905dd57
author: rothja
ms.author: jroth
ms.openlocfilehash: c57a2ab2f3780a8bc75b53b0cceeee0799fcfcc2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607614"
---
# <a name="executing-template-files-by-using-the-commandstream-property"></a><span data-ttu-id="d4040-102">Ausführen von Vorlagendateien mit der 'CommandStream'-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="d4040-102">Executing Template Files by Using the CommandStream Property</span></span>
  <span data-ttu-id="d4040-103">In diesem Beispiel wird veranschaulicht, wie Vorlagen Dateien, die aus SQL-oder XPath-Abfragen bestehen, mithilfe der CommandStream-Eigenschaft des SqlXmlCommand-Objekts angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="d4040-103">This example illustrates how template files that consist of SQL or XPath queries can be specified by using the CommandStream property of the SqlXmlCommand object.</span></span> <span data-ttu-id="d4040-104">In dieser Anwendung wird ein filestreamobject für eine Befehlsdatei geöffnet, und der Dateistream wird als CommandStream zugewiesen, der ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d4040-104">In this application, a FileStreamobject is opened for a command file, and the file stream is assigned as the CommandStream that is executed.</span></span>  
  
 <span data-ttu-id="d4040-105">Im folgenden Beispiel wird die CommandType-Eigenschaft als SqlXmlCommandType. Template (nicht als TemplateFile) angegeben.</span><span class="sxs-lookup"><span data-stu-id="d4040-105">In the following example, the CommandType property is specified as SqlXmlCommandType.Template (not as TemplateFile).</span></span>  
  
 <span data-ttu-id="d4040-106">Es folgt die Beispiel-XML-Vorlage:</span><span class="sxs-lookup"><span data-stu-id="d4040-106">This is the sample XML template:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>  
    SELECT TOP 2 ContactID, FirstName, LastName   
    FROM   Person.Contact  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="d4040-107">Dies ist die C#-Beispielanwendung.</span><span class="sxs-lookup"><span data-stu-id="d4040-107">This is the sample C# application.</span></span> <span data-ttu-id="d4040-108">Um die Anwendung zu testen, speichern Sie die Vorlage (TemplateFile.xml), und führen Sie dann die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="d4040-108">To test the application, save the template (TemplateFile.xml) and then execute the application.</span></span> <span data-ttu-id="d4040-109">Die Anwendung führt die in der XML-Vorlage angegebene Abfrage aus und zeigt das daraufhin generierte XML-Dokument auf dem Bildschirm an.</span><span class="sxs-lookup"><span data-stu-id="d4040-109">The application executes the query that is specified in the XML template and displays the XML document that is generated on the screen.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d4040-110">Im Code müssen Sie den Namen der Instanz von Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in der Verbindungszeichenfolge bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d4040-110">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
  
class Test  
{  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
      public static int testParams()  
      {  
         //Stream strm;  
         MemoryStream ms = new MemoryStream();  
         StreamWriter sw = new StreamWriter(ms);  
         ms.Position = 0;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandStream = new FileStream("TemplateFile.xml", FileMode.Open, FileAccess.Read);  
         cmd.CommandType = SqlXmlCommandType.Template;  
         using (Stream strm = cmd.ExecuteStream())  
         {  
            using (StreamReader sr = new StreamReader(strm)){  
               Console.WriteLine(sr.ReadToEnd());  
            }  
         }  
         return 0;        
      }  
  
      public static int Main(String[] args)  
      {  
         testParams();     
         return 0;  
      }  
   }  
```  
  
### <a name="to-test-the-application"></a><span data-ttu-id="d4040-111">So testen Sie die Anwendung</span><span class="sxs-lookup"><span data-stu-id="d4040-111">To test the application</span></span>  
  
1.  <span data-ttu-id="d4040-112">Speichern Sie die in diesem Beispiel bereitgestellte XML-Vorlage in einem Ordner.</span><span class="sxs-lookup"><span data-stu-id="d4040-112">Save the XML template (TemplateFile.xml) that is provided in this example in a folder.</span></span>  
  
2.  <span data-ttu-id="d4040-113">Speichern Sie den c#-Code (DocSample.cs), der in diesem Beispiel bereitgestellt wird, im selben Ordner, in dem das Schema gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="d4040-113">Save the C# code (DocSample.cs) that is provided in this example in the same folder in which the schema is stored.</span></span> <span data-ttu-id="d4040-114">(Wenn Sie die Dateien in einem anderen Ordner speichern, müssen Sie den Code bearbeiten und den entsprechenden Verzeichnispfad für das Zuordnungsschema angeben.)</span><span class="sxs-lookup"><span data-stu-id="d4040-114">(If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.)</span></span>  
  
3.  <span data-ttu-id="d4040-115">Kompilieren Sie den Code.</span><span class="sxs-lookup"><span data-stu-id="d4040-115">Compile the code.</span></span> <span data-ttu-id="d4040-116">Verwenden Sie zur Kompilierung des Codes an der Eingabeaufforderung die folgende Zeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="d4040-116">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="d4040-117">Dadurch wird eine ausführbare Datei (DocSample.exe) erstellt.</span><span class="sxs-lookup"><span data-stu-id="d4040-117">This creates an executable (DocSample.exe).</span></span>  
  
4.  <span data-ttu-id="d4040-118">Führen Sie DocSample.exe an der Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="d4040-118">At the command prompt, execute DocSample.exe.</span></span>  
  
  
