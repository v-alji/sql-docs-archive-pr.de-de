---
title: Verarbeiten von XML auf der Client Seite (verwaltete SQLXML-Klassen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- processing XML on client side [SQLXML]
- client-side XML formatting
- Managed Classes [SQLXML], client-side XML formatting
- SQLXML Managed Classes, client-side XML formatting
- ClientSideXml property
ms.assetid: 5e7ecf18-66fc-49ff-bc50-83635cd7ac0b
author: rothja
ms.author: jroth
ms.openlocfilehash: fb90f7c5c823c750b64f47d0c9df9551b9f857b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608503"
---
# <a name="processing-xml-on-the-client-side-sqlxml-managed-classes"></a><span data-ttu-id="6efdc-102">Clientseitige Verarbeitung von XML (Verwaltete Klassen in SQLXML)</span><span class="sxs-lookup"><span data-stu-id="6efdc-102">Processing XML on the Client Side (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="6efdc-103">In diesem Beispiel wird die Verwendung der ClientSideXML-Eigenschaft veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6efdc-103">This example illustrates the use of the ClientSideXml property.</span></span> <span data-ttu-id="6efdc-104">Die Anwendung führt eine gespeicherte Prozedur auf dem Server aus.</span><span class="sxs-lookup"><span data-stu-id="6efdc-104">The application executes a stored procedure on the server.</span></span> <span data-ttu-id="6efdc-105">Das Ergebnis der gespeicherten Prozedur (ein Rowset mit zwei Spalten) wird auf der Clientseite verarbeitet und ein XML-Dokument produziert.</span><span class="sxs-lookup"><span data-stu-id="6efdc-105">The result of the stored procedure (a two-column rowset) is processed on the client side to produce an XML document.</span></span>  
  
 <span data-ttu-id="6efdc-106">Mit der folgenden gespeicherten Prozedur GetContacts werden **FirstName** und **LastName** von Mitarbeitern in der Person. Contact-Tabelle der AdventureWorks-Datenbank zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6efdc-106">The following GetContacts stored procedure returns **FirstName** and **LastName** of employees in the Person.Contact table in the AdventureWorks database.</span></span>  
  
```  
USE AdventureWorks  
CREATE PROCEDURE GetContacts @LastName varchar(20)  
AS  
SELECT FirstName, LastName  
FROM   Person.Contact  
WHERE LastName = @LastName  
Go  
```  
  
 <span data-ttu-id="6efdc-107">Diese c#-Anwendung führt die gespeicherte Prozedur aus und gibt die for XML Auto-Option in der Angabe des CommandText-Werts an.</span><span class="sxs-lookup"><span data-stu-id="6efdc-107">This C# application executes the stored procedure and specifies the FOR XML AUTO option in specifying the CommandText value.</span></span> <span data-ttu-id="6efdc-108">In der Anwendung ist die ClientSideXML-Eigenschaft des SqlXmlCommand-Objekts auf "true" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6efdc-108">In the application, the ClientSideXml property of the SqlXmlCommand object is set to true.</span></span> <span data-ttu-id="6efdc-109">Auf diese Weise können Sie bereits bestehende gespeicherte Prozeduren ausführen, die ein Rowset zurückgeben und auf dem Client eine XML-Transformation auf das Rowset anwenden.</span><span class="sxs-lookup"><span data-stu-id="6efdc-109">This allows you to execute preexisting stored procedures that return a rowset and apply an XML transformation to it on the client.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6efdc-110">Im Code müssen Sie den Namen der Instanz von Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in der Verbindungszeichenfolge bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6efdc-110">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
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
         SqlXmlParameter p;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.ClientSideXml = true;  
         cmd.CommandText = "EXEC GetContacts ? FOR XML NESTED";  
         p = cmd.CreateParameter();  
         p.Value = "Achong";  
         using (Stream strm = cmd.ExecuteStream())   
         {  
            using (StreamReader sr = new StreamReader(strm))  
                  {  
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
  
 <span data-ttu-id="6efdc-111">Um das Beispiel zu testen, muss auf dem Computer [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installiert sein.</span><span class="sxs-lookup"><span data-stu-id="6efdc-111">To test this example, you must have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="6efdc-112">So testen Sie die Anwendung</span><span class="sxs-lookup"><span data-stu-id="6efdc-112">To test the application</span></span>  
  
1.  <span data-ttu-id="6efdc-113">Erstellen Sie die gespeicherte Prozedur.</span><span class="sxs-lookup"><span data-stu-id="6efdc-113">Create the stored procedure.</span></span>  
  
2.  <span data-ttu-id="6efdc-114">Speichern Sie den in diesem Beispiel bereitgestellten C#-Code (DocSample.cs) in einem Ordner.</span><span class="sxs-lookup"><span data-stu-id="6efdc-114">Save the C# code (DocSample.cs) that is provided in this example in a folder.</span></span> <span data-ttu-id="6efdc-115">Bearbeiten Sie den Code, um entsprechende Anmelde- und Kennwortinformationen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6efdc-115">Edit the code to specify appropriate login and password information.</span></span>  
  
3.  <span data-ttu-id="6efdc-116">Kompilieren Sie den Code.</span><span class="sxs-lookup"><span data-stu-id="6efdc-116">Compile the code.</span></span> <span data-ttu-id="6efdc-117">Verwenden Sie zur Kompilierung des Codes an der Eingabeaufforderung die folgende Zeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="6efdc-117">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="6efdc-118">Dadurch wird eine ausführbare Datei (DocSample.exe) erstellt.</span><span class="sxs-lookup"><span data-stu-id="6efdc-118">This creates an executable (DocSample.exe).</span></span>  
  
4.  <span data-ttu-id="6efdc-119">Führen Sie DocSample.exe an der Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="6efdc-119">At the command prompt, execute DocSample.exe.</span></span>  
  
  
