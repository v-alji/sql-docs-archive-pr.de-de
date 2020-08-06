---
title: Ausführen von Vorlagen Dateien mit der CommandText-Eigenschaft | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- Managed Classes [SQLXML], executing template files
- SQLXML Managed Classes, executing template files
- templates [SQLXML], SQLXML Managed Classes
- executing template files [SQLXML]
- CommandText property
ms.assetid: f1b1278d-252d-4a06-836e-4ef77f338ef9
author: rothja
ms.author: jroth
ms.openlocfilehash: f5507e84daf57ca4646fae3efe78c6105af35700
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607613"
---
# <a name="executing-template-files-by-using-the-commandtext-property"></a><span data-ttu-id="d425f-102">Ausführen von Vorlagendateien mit der 'CommandText'-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="d425f-102">Executing Template Files by Using the CommandText Property</span></span>
  <span data-ttu-id="d425f-103">In diesem Beispiel wird veranschaulicht, wie Vorlagen Dateien, die aus SQL-oder XPath-Abfragen bestehen, mithilfe von commandtextproperty angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="d425f-103">This example illustrates how template files that consist of SQL or XPath queries can be specified by using the CommandTextproperty.</span></span> <span data-ttu-id="d425f-104">Anstatt die SQL-oder XPath-Abfrage als Wert von CommandText anzugeben, können Sie einen Dateinamen als Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="d425f-104">Instead of specifying the SQL or XPath query as the value of CommandText, you can specify a file name as the value.</span></span> <span data-ttu-id="d425f-105">Im folgenden Beispiel wird die CommandType-Eigenschaft als SqlXmlCommandType. TemplateFile angegeben.</span><span class="sxs-lookup"><span data-stu-id="d425f-105">In the following example, the CommandType property is specified as SqlXmlCommandType.TemplateFile.</span></span>  
  
 <span data-ttu-id="d425f-106">Diese Vorlage wird von der Beispielanwendung ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="d425f-106">The sample application executes this template:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>  
    SELECT TOP 2 ContactID, FirstName, LastName   
    FROM   Person.Contact  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="d425f-107">Dies ist die c#-Beispielanwendung.</span><span class="sxs-lookup"><span data-stu-id="d425f-107">This is the C# sample application.</span></span> <span data-ttu-id="d425f-108">Um die Anwendung zu testen, speichern Sie die Vorlage (TemplateFile.xml), und führen Sie dann die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="d425f-108">To test the application, save the template (TemplateFile.xml) and then execute the application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d425f-109">Im Code müssen Sie den Namen der Instanz von Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in der Verbindungszeichenfolge bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d425f-109">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
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
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandType = SqlXmlCommandType.TemplateFile;  
         cmd.CommandText = "TemplateFile.xml";  
         using (Stream strm = cmd.ExecuteStream()){  
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
  
### <a name="to-test-the-application"></a><span data-ttu-id="d425f-110">So testen Sie die Anwendung</span><span class="sxs-lookup"><span data-stu-id="d425f-110">To test the application</span></span>  
  
1.  <span data-ttu-id="d425f-111">Stellen Sie sicher, dass [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="d425f-111">Make sure that you have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
2.  <span data-ttu-id="d425f-112">Speichern Sie die in diesem Beispiel bereitgestellte XML-Vorlage in einem Ordner.</span><span class="sxs-lookup"><span data-stu-id="d425f-112">Save the XML template (TemplateFile.xml) that is provided in this example in a folder.</span></span>  
  
3.  <span data-ttu-id="d425f-113">Speichern Sie den c#-Code (DocSample.cs), der in diesem Beispiel bereitgestellt wird, im selben Ordner, in dem das Schema gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="d425f-113">Save the C# code (DocSample.cs) that is provided in this example in the same folder in which the schema is stored.</span></span> <span data-ttu-id="d425f-114">(Wenn Sie die Dateien in einem anderen Ordner speichern, müssen Sie den Code bearbeiten und den entsprechenden Verzeichnispfad für das Zuordnungsschema angeben.)</span><span class="sxs-lookup"><span data-stu-id="d425f-114">(If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.)</span></span>  
  
4.  <span data-ttu-id="d425f-115">Kompilieren Sie den Code.</span><span class="sxs-lookup"><span data-stu-id="d425f-115">Compile the code.</span></span> <span data-ttu-id="d425f-116">Verwenden Sie zur Kompilierung des Codes an der Eingabeaufforderung die folgende Zeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="d425f-116">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="d425f-117">Dadurch wird eine ausführbare Datei (DocSample.exe) erstellt.</span><span class="sxs-lookup"><span data-stu-id="d425f-117">This creates an executable (DocSample.exe).</span></span>  
  
5.  <span data-ttu-id="d425f-118">Führen Sie DocSample.exe an der Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="d425f-118">At the command prompt, execute DocSample.exe.</span></span>  
  
 <span data-ttu-id="d425f-119">Wenn Sie einen Parameter an eine Vorlage übergeben, muss der Parameter Name mit einem @-Zeichen (@) beginnen. beispielsweise p.Name = " @ContactID ", wobei p ein SqlXmlParameter-Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="d425f-119">If you pass a parameter to a template, the parameter name must begin with at sign (@); for example, p.Name="@ContactID", where p is a SqlXmlParameter object.</span></span>  
  
 <span data-ttu-id="d425f-120">Dies ist die aktualisierte Vorlage, die einen Parameter annimmt.</span><span class="sxs-lookup"><span data-stu-id="d425f-120">This is the updated template which takes one parameter.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:header>  
     <sql:param name='ContactID'>1</sql:param>    
  </sql:header>  
  <sql:query>  
    SELECT ContactID, FirstName, LastName  
    FROM   Person.Contact  
    WHERE  ContactID=@ContactID  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="d425f-121">Dies ist der aktualisierte Code, in dem ein Parameter übergeben wird, um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d425f-121">This is the updated code in which a parameter is passed in to execute the template.</span></span>  
  
```  
public static int testParams()  
{  
  
   Stream strm;  
   SqlXmlParameter p;  
  
   SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
   cmd.CommandType = SqlXmlCommandType.TemplateFile;  
   cmd.CommandText = "TemplateFile.xml";  
   p = cmd.CreateParameter();  
   p.Name="@ContactID";  
   p.Value = "1";  
   strm = cmd.ExecuteStream();  
   StreamReader sw = new StreamReader(strm);  
   Console.WriteLine(sw.ReadToEnd());  
   return 0;        
}  
```  
  
  
