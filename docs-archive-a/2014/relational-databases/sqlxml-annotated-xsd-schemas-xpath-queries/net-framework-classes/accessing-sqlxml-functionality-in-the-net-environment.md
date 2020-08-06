---
title: Zugreifen auf die SQLXML-Funktionalität in der .NET-Umgebung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- Managed Classes [SQLXML], accessing SQLXML functionality
- SQLXML Managed Classes, accessing SQLXML functionality
- DiffGrams [SQLXML], accessing SQLXML functionality
- .NET Framework [SQLXML], accessing SQLXML functionality
ms.assetid: 74744535-2945-414d-9a5b-7e8cc363953a
author: rothja
ms.author: jroth
ms.openlocfilehash: a2ba0a54310833c0a1a1315aa94d78fe5650d480
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618589"
---
# <a name="accessing-sqlxml-functionality-in-the-net-environment"></a><span data-ttu-id="f0a1b-102">Zugreifen auf die SQLXML-Funktionalität in der .NET-Umgebung</span><span class="sxs-lookup"><span data-stu-id="f0a1b-102">Accessing SQLXML Functionality in the .NET Environment</span></span>
  <span data-ttu-id="f0a1b-103">In diesem Beispiel wird Folgendes dargestellt:</span><span class="sxs-lookup"><span data-stu-id="f0a1b-103">This example shows:</span></span>  
  
-   <span data-ttu-id="f0a1b-104">Verwenden von [!INCLUDE[msCoName](../../../includes/msconame-md.md)] verwalteten SQLXML-Klassen (Microsoft. Data. SqlXml) für den Zugriff auf Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in der [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-104">How to use [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML Managed Classes (Microsoft.Data.SqlXml) to access Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework environment.</span></span>  
  
-   <span data-ttu-id="f0a1b-105">wie DiffGram-Objekte, die in der .NET Framework-Umgebung generiert werden, Datenupdates auf [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Tabellen anwenden können.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-105">How DiffGrams that are generated in the .NET Framework environment can apply data updates to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tables.</span></span>  
  
 <span data-ttu-id="f0a1b-106">In dieser Anwendung wird eine XPath-Abfrage für ein XSD-Schema ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-106">In this application, an XPath query is executed against an XSD schema.</span></span> <span data-ttu-id="f0a1b-107">Die Ausführung der XPath-Abfrage gibt ein XML-Dokument zurück, das aus Kontaktdaten (**FirstName**, **LastName**) besteht.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-107">The execution of the XPath query returns an XML document that consists of contact data (**FirstName**, **LastName**).</span></span> <span data-ttu-id="f0a1b-108">Die Anwendung lädt das XML-Dokument in das Dataset der .NET Framework-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-108">The application loads the XML document in the dataset in the .NET Framework environment.</span></span> <span data-ttu-id="f0a1b-109">Die Daten im Dataset werden bearbeitet: Der Vorname des ersten Kontakts im Dataset wird in "Susan" geändert.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-109">The data in the dataset is modified: the contact's first name is changed to "Susan" for the first contact in the dataset.</span></span> <span data-ttu-id="f0a1b-110">Das DiffGram-Objekt wird aus dem Dataset erstellt, und das im DiffGram-Objekt angegebene Update (die Änderung des Vornamens der Mitarbeiterin) auf die Person.Contact-Tabelle angewendet.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-110">The DiffGram is generated from the dataset, and the update that is specified in the DiffGram (the change in the employee's first name) is then applied to the Person.Contact table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f0a1b-111">Im Code müssen Sie den Namen der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in der Verbindungszeichenfolge bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-111">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using System.Data;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
   static string ConnString = "Provider=SQLOLEDB;Server=SqlServerName;database=AdventureWorks;Integrated Security=SSPI;";  
   public static int testParams()  
   {  
      DataRow row;  
      SqlXmlAdapter ad;  
      //need a memory stream to hold diff gram temporarily  
      MemoryStream ms = new MemoryStream();  
      SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
      cmd.RootTag = "ROOT";  
      cmd.CommandText = "Con";  
      cmd.CommandType = SqlXmlCommandType.XPath;  
      cmd.SchemaPath = "MySchema.xml";  
      //load data set  
      DataSet ds = new DataSet();  
      ad = new SqlXmlAdapter(cmd);  
      ad.Fill(ds);  
      row = ds.Tables["Con"].Rows[0];  
      row["FName"] = "Susan";  
      ad.Update(ds);  
      return 0;  
   }  
   public static int Main(String[] args)  
   {  
      testParams();  
      return 0;  
   }  
}  
```  
  
 <span data-ttu-id="f0a1b-112">**So testen Sie das Beispiel:**</span><span class="sxs-lookup"><span data-stu-id="f0a1b-112">**To test the example:**</span></span>  
  
 <span data-ttu-id="f0a1b-113">Um das Beispiel zu testen, muss auf dem Computer [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installiert sein.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-113">To test this example, you must have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
1.  <span data-ttu-id="f0a1b-114">Speichern Sie dieses XSD-Schema (MySchema.xml) in einem Ordner:</span><span class="sxs-lookup"><span data-stu-id="f0a1b-114">Save this XSD schema (MySchema.xml) in a folder:</span></span>  
  
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
  
2.  <span data-ttu-id="f0a1b-115">Speichern Sie den C#-Code (DocSample.cs) aus dem Beispiel im selben Ordner, in dem das Schema gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-115">Save the C# code (DocSample.cs) provided in this example in the same folder in which the schema is stored.</span></span> <span data-ttu-id="f0a1b-116">(Wenn Sie die Dateien in einem anderen Ordner speichern, müssen Sie den Code bearbeiten und den entsprechenden Verzeichnispfad für das Zuordnungsschema angeben.)</span><span class="sxs-lookup"><span data-stu-id="f0a1b-116">(If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.)</span></span>  
  
3.  <span data-ttu-id="f0a1b-117">Kompilieren Sie den Code.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-117">Compile the code.</span></span> <span data-ttu-id="f0a1b-118">Verwenden Sie zur Kompilierung des Codes an der Eingabeaufforderung die folgende Zeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="f0a1b-118">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="f0a1b-119">Dadurch wird eine ausführbare Datei (DocSample.exe) erstellt.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-119">This creates an executable (DocSample.exe).</span></span>  
  
 <span data-ttu-id="f0a1b-120">Führen Sie DocSample.exe an der Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="f0a1b-120">At the command prompt, execute DocSample.exe.</span></span>  
  
  
