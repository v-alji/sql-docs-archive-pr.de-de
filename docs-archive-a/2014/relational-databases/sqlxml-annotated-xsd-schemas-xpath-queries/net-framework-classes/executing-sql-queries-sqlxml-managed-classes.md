---
title: Ausführen von SQL-Abfragen (verwaltete SQLXML-Klassen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- queries [SQLXML], SQLXML Managed Classes
- SQLXML Managed Classes, executing SQL queries
- Managed Classes [SQLXML], executing SQL queries
- ExecuteToStream method
- SQL queries [SQLXML]
ms.assetid: a561ae83-a8b6-4b9b-a819-9b86839546b4
author: rothja
ms.author: jroth
ms.openlocfilehash: d869e45de359e602b2451b9f66fa3046f6823c1e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618571"
---
# <a name="executing-sql-queries-sqlxml-managed-classes"></a><span data-ttu-id="42997-102">Ausführen von SQL-Abfragen (verwaltete SQLXML-Klassen)</span><span class="sxs-lookup"><span data-stu-id="42997-102">Executing SQL Queries (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="42997-103">In diesem Beispiel wird Folgendes veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="42997-103">This example demonstrates:</span></span>  
  
-   <span data-ttu-id="42997-104">Erstellen von Parametern (SqlXmlParameter-Objekte).</span><span class="sxs-lookup"><span data-stu-id="42997-104">Creating parameters (SqlXmlParameter objects).</span></span>  
  
-   <span data-ttu-id="42997-105">Zuweisen von Werten zu den Eigenschaften (Name und Wert) von SqlXmlParameter-Objekten.</span><span class="sxs-lookup"><span data-stu-id="42997-105">Assigning values to the properties (Name and Value) of SqlXmlParameter objects.</span></span>  
  
 <span data-ttu-id="42997-106">In diesem Beispiel wird eine einfache SQL-Abfrage ausgeführt, um Vornamen, Nachnamen und Geburtsdatum des Mitarbeiters abzufragen, dessen Nachname als Parameterwert übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="42997-106">In this example, a simple SQL query is executed to retrieve the first name, last name, and birth date of the employee whose last name value is passed as a parameter.</span></span> <span data-ttu-id="42997-107">Bei Angabe des-Parameters (*LastName*) wird nur die Value-Eigenschaft festgelegt.</span><span class="sxs-lookup"><span data-stu-id="42997-107">In specifying the parameter (*LastName*), only the Value property is set.</span></span> <span data-ttu-id="42997-108">Die Name-Eigenschaft ist nicht festgelegt, da der-Parameter in dieser Abfrage positiontional ist und kein Name erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="42997-108">The Name property is not set, because in this query the parameter is positional and no name is required.</span></span>  
  
 <span data-ttu-id="42997-109">Die CommandType-Eigenschaft des SqlXmlCommand-Objekts ist standardmäßig **SQL**.</span><span class="sxs-lookup"><span data-stu-id="42997-109">The CommandType property of the SqlXmlCommand object by default is **Sql**.</span></span> <span data-ttu-id="42997-110">Deshalb wird die Eigenschaft nicht explizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="42997-110">Therefore, the property is not explicitly set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42997-111">Im Code müssen Sie den Namen der Instanz von Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in der Verbindungszeichenfolge bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="42997-111">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
 <span data-ttu-id="42997-112">Dies ist der C#-Code.</span><span class="sxs-lookup"><span data-stu-id="42997-112">This is the C# code:</span></span>  
  
```  
using System;  
  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
      public static int testParams()  
      {  
         Stream strm;  
         SqlXmlParameter p;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);        
         cmd.CommandText = "SELECT FirstName, LastName FROM Person.Contact WHERE LastName=? For XML Auto";  
         p = cmd.CreateParameter();  
         p.Value = "Achong";  
         string strResult;  
         try   
         {  
            strm = cmd.ExecuteStream();  
            strm.Position = 0;  
            using(StreamReader sr = new StreamReader(strm))  
            {  
               Console.WriteLine(sr.ReadToEnd());  
            }  
         }  
         catch (SqlXmlException e)  
         {  
            //in case of an error, this prints error returned.  
            e.ErrorStream.Position=0;  
            strResult=new StreamReader(e.ErrorStream).ReadToEnd();  
            System.Console.WriteLine(strResult);  
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
  
### <a name="to-test-the-application"></a><span data-ttu-id="42997-113">So testen Sie die Anwendung</span><span class="sxs-lookup"><span data-stu-id="42997-113">To test the application</span></span>  
  
1.  <span data-ttu-id="42997-114">Speichern Sie den in diesem Thema bereitgestellten C#-Code (DocSample.cs) in einem Ordner.</span><span class="sxs-lookup"><span data-stu-id="42997-114">Save the C# code (DocSample.cs) provided in this topic in a folder.</span></span>  
  
2.  <span data-ttu-id="42997-115">Kompilieren Sie den Code.</span><span class="sxs-lookup"><span data-stu-id="42997-115">Compile the code.</span></span> <span data-ttu-id="42997-116">Verwenden Sie zur Kompilierung des Codes an der Eingabeaufforderung die folgende Zeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="42997-116">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="42997-117">Dadurch wird eine ausführbare Datei (DocSample.exe) erstellt.</span><span class="sxs-lookup"><span data-stu-id="42997-117">This creates an executable (DocSample.exe).</span></span>  
  
3.  <span data-ttu-id="42997-118">Führen Sie DocSample.exe an der Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="42997-118">At the command prompt, execute DocSample.exe.</span></span>  
  
 <span data-ttu-id="42997-119">Um das Beispiel zu testen, muss auf dem Computer [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installiert sein.</span><span class="sxs-lookup"><span data-stu-id="42997-119">To test this example, you must have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
 <span data-ttu-id="42997-120">Statt die SQL-Abfragen als Befehlstext anzugeben, können Sie eine Vorlage festlegen (wie im folgenden Codefragment dargestellt), die ein Updategram ausführt (ebenfalls eine Vorlage), um einen Kundendatensatz einzufügen.</span><span class="sxs-lookup"><span data-stu-id="42997-120">Instead of specifying SQL queries as the command text, you can specify a template (as shown in the following code fragment) that executes an updategram (which is also a template) to insert a customer record.</span></span> <span data-ttu-id="42997-121">Sie können Vorlagen und Updategrams in Dateien angeben und Dateien ausführen.</span><span class="sxs-lookup"><span data-stu-id="42997-121">You can specify templates and updategrams in files and execute files.</span></span> <span data-ttu-id="42997-122">Weitere Informationen finden Sie unter [Ausführen von Vorlagen Dateien mit der CommandText-Eigenschaft](executing-template-files-by-using-the-commandtext-property.md).</span><span class="sxs-lookup"><span data-stu-id="42997-122">For more information, see [Executing Template Files by Using the CommandText Property](executing-template-files-by-using-the-commandtext-property.md).</span></span>  
  
```  
SqlXmlCommand cmd = new SqlXmlCommand("Provider=SQLOLEDB;Data Source=SqlServerName;Initial Catalog=Database; Integrated Security=SSPI;");  
Stream stm;  
cmd.CommandType = SqlXmlCommandType.UpdateGram;  
cmd.CommandText = "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql' xmlns:updg='urn:schemas-microsoft-com:xml-updategram'>" +  
      "<updg:sync>" +  
       "<updg:before/>" +  
       "<updg:after>" +  
         "<Customer CustomerID='aaaaa' CustomerName='Some Name' CustomerTitle='SomeTitle' />" +  
       "</updg:after>" +  
       "</updg:sync>" +  
       "</ROOT>";  
  
stm = cmd.ExecuteStream();  
stm = null;  
cmd = null;  
```  
  
## <a name="using-executetostream"></a><span data-ttu-id="42997-123">Verwenden von ExecuteToStream</span><span class="sxs-lookup"><span data-stu-id="42997-123">Using ExecuteToStream</span></span>  
 <span data-ttu-id="42997-124">Wenn Sie über einen vorhandenen Stream verfügen, können Sie die executedestream-Methode verwenden, anstatt ein Stream-Objekt zu erstellen und die Execute-Methode zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="42997-124">If you have an existing stream, you can use the ExecuteToStream method instead of creating a Stream object and using the Execute method.</span></span> <span data-ttu-id="42997-125">Der Code aus dem vorherigen Beispiel wird hier überarbeitet, um die executedestream-Methode zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="42997-125">The code from the preceding example is revised here to use the ExecuteToStream method:</span></span>  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
   static string ConnString = "Provider=SQLOLEDB;Server=SqlServerName;database=AdventureWorks;Integrated Security=SSPI;";  
   public static int testParams()  
   {  
      SqlXmlParameter p;  
      MemoryStream ms = new MemoryStream();  
      StreamReader sr = new StreamReader(ms);  
      ms.Position = 0;  
      SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
      cmd.CommandText = "select FirstName, LastName from Person.Contact where LastName = ? For XML Auto";  
      p = cmd.CreateParameter();  
      p.Value = "Achong";  
      cmd.ExecuteToStream(ms);  
      ms.Position = 0;  
      Console.WriteLine(sr.ReadToEnd());  
      return 0;        
   }  
   public static int Main(String[] args)  
   {  
      testParams();     
      return 0;  
   }  
}  
```  
  
> [!NOTE]  
>  <span data-ttu-id="42997-126">Sie können auch die executexmlreadermethod verwenden, die ein XmlReader-Objekt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="42997-126">You can also use the ExecuteXMLReadermethod that returns an XmlReader object.</span></span> <span data-ttu-id="42997-127">Weitere Informationen finden Sie unter [Ausführen von SQL-Abfragen mithilfe der ExecuteXmlReader-Methode](executing-sql-queries-by-using-the-executexmlreader-method.md).</span><span class="sxs-lookup"><span data-stu-id="42997-127">For more information, see [Executing SQL Queries by Using the ExecuteXMLReader Method](executing-sql-queries-by-using-the-executexmlreader-method.md).</span></span>  
  
  
