---
title: Verwenden von SQLXML-Massen laden in der .NET-Umgebung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, XML Bulk Load
- XML Bulk Load [SQLXML], .NET environment
- .NET Framework [SQLXML], XML Bulk Load
- bulk load [SQLXML], .NET environment
ms.assetid: b85df83b-ba56-43bf-bcdf-b2a6fca43276
author: rothja
ms.author: jroth
ms.openlocfilehash: 6bd1c44a8b56bc5129aeb9843ed9ba814d45742a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722678"
---
# <a name="using-sqlxml-bulk-load-in-the-net-environment"></a><span data-ttu-id="02b42-102">Verwenden von SQLXML-Massenladen in der .NET-Umgebung</span><span class="sxs-lookup"><span data-stu-id="02b42-102">Using SQLXML Bulk Load in the .NET Environment</span></span>
  <span data-ttu-id="02b42-103">In diesem Thema wird erklärt, wie die XML-Massenladefunktionalität in der .NET-Umgebung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="02b42-103">This topic explains how the XML Bulk Load functionality can be used in the .NET environment.</span></span> <span data-ttu-id="02b42-104">Ausführliche Informationen zum XML-Massen Laden finden Sie unter [Durchführen von Massen Laden von XML-Daten &#40;SQLXML 4,0&#41;](bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="02b42-104">For detailed information about XML Bulk Load, see [Performing Bulk Load of XML Data &#40;SQLXML 4.0&#41;](bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="02b42-105">Um das SQLXML-Massenladen-COM-Objekt in einer verwalteten Umgebung zu verwenden, müssen Sie diesem Objekt eine Projektreferenz hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="02b42-105">To use the SQLXML Bulk Load COM object from a managed environment, you need to add a project reference to this object.</span></span> <span data-ttu-id="02b42-106">Dies generiert eine verwaltete Wrapperschnittstelle um das Massenladen-COM-Objekt.</span><span class="sxs-lookup"><span data-stu-id="02b42-106">This generates a managed wrapper interface around the Bulk Load COM object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="02b42-107">Verwaltetes XML-Massenladen funktioniert nicht mit verwalteten Datenströmen und erfordert einen Wrapper um systemeigene Datenströme.</span><span class="sxs-lookup"><span data-stu-id="02b42-107">Managed XML Bulk load does not work with managed streams and requires a wrapper around native streams.</span></span> <span data-ttu-id="02b42-108">Die SQLXML-Massenladenkomponente wird nicht in einer Multithreadumgebung ('[MTAThread]'-Attribut) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="02b42-108">The SQLXML Bulk Load component will not run in a multi-threaded environment ('[MTAThread]' attribute).</span></span> <span data-ttu-id="02b42-109">Wenn Sie versuchen, die Massen Lade Komponente in einer Umgebung mit mehreren Threads auszuführen, erhalten Sie eine InvalidCastException-Ausnahme mit den folgenden zusätzlichen Informationen: "QueryInterface für die Schnittstelle SQLXMLBULKLOADLib. ISQLXMLBulkLoad ist fehlgeschlagen".</span><span class="sxs-lookup"><span data-stu-id="02b42-109">If you attempt to run the Bulk Load component in a multi-thread environment, you get an InvalidCastException exception with the following additional information: "QueryInterface for interface SQLXMLBULKLOADLib.ISQLXMLBulkLoad failed."</span></span> <span data-ttu-id="02b42-110">Die Problem Umgehung besteht darin, dass das Objekt, das das Massen Lade Objekt enthält, auf einen einzelnen Thread zugreifen kann (z. b. mithilfe des **[STAThread]** -Attributs, wie im Beispiel gezeigt).</span><span class="sxs-lookup"><span data-stu-id="02b42-110">The workaround is to make the object that contains the Bulk Load object single-thread accessible (for example, by using the **[STAThread]** attribute as shown in the sample).</span></span>  
  
 <span data-ttu-id="02b42-111">Dieses Thema stellt eine funktionierende C#-Beispielanwendung für das Massenladen von XML-Daten in der Datenbank bereit.</span><span class="sxs-lookup"><span data-stu-id="02b42-111">This topic provides a working C# sample application to bulk load XML data in the database.</span></span> <span data-ttu-id="02b42-112">Gehen Sie folgendermaßen vor, um ein funktionierendes Beispiel zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="02b42-112">To create a working sample, follow these steps:</span></span>  
  
1.  <span data-ttu-id="02b42-113">Erstellen Sie die folgenden Tabellen:</span><span class="sxs-lookup"><span data-stu-id="02b42-113">Create the following tables:</span></span>  
  
    ```  
    CREATE TABLE Ord (  
             OrderID     int identity(1,1)  PRIMARY KEY,  
             CustomerID  varchar(5))  
    GO  
    CREATE TABLE Product (  
             ProductID   int identity(1,1) PRIMARY KEY,  
             ProductName varchar(20))  
    GO  
    CREATE TABLE OrderDetail (  
           OrderID     int FOREIGN KEY REFERENCES Ord(OrderID),  
           ProductID   int FOREIGN KEY REFERENCES Product(ProductID),  
                       CONSTRAINT OD_key PRIMARY KEY (OrderID, ProductID))  
    GO  
    ```  
  
2.  <span data-ttu-id="02b42-114">Speichern Sie das folgende Schema in einer Datei (schema.xml):</span><span class="sxs-lookup"><span data-stu-id="02b42-114">Save the following schema in a file (schema.xml):</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
    <xsd:annotation>  
      <xsd:appinfo>  
        <sql:relationship name="OrderOD"  
              parent="Ord"  
              parent-key="OrderID"  
              child="OrderDetail"  
              child-key="OrderID" />  
  
        <sql:relationship name="ODProduct"  
              parent="OrderDetail"  
              parent-key="ProductID"  
              child="Product"  
              child-key="ProductID"   
              inverse="true"/>  
      </xsd:appinfo>  
    </xsd:annotation>  
  
      <xsd:element name="Order" sql:relation="Ord"   
                                sql:key-fields="OrderID" >  
       <xsd:complexType>  
         <xsd:sequence>  
            <xsd:element name="Product" sql:relation="Product"   
                         sql:key-fields="ProductID"  
                         sql:relationship="OrderOD ODProduct">  
              <xsd:complexType>  
                 <xsd:attribute name="ProductID" type="xsd:int" />  
                 <xsd:attribute name="ProductName" type="xsd:string" />  
              </xsd:complexType>  
            </xsd:element>  
         </xsd:sequence>  
            <xsd:attribute name="OrderID"   type="xsd:integer" />   
            <xsd:attribute name="CustomerID"   type="xsd:string" />  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="02b42-115">Speichern Sie das folgende Beispiel-XML-Dokument in einer Datei (data.xml):</span><span class="sxs-lookup"><span data-stu-id="02b42-115">Save the following sample XML document in a file (data.xml):</span></span>  
  
    ```  
    <ROOT>    
      <Order OrderID="11" CustomerID="ALFKI">  
        <Product ProductID="11" ProductName="Chai" />  
        <Product ProductID="22" ProductName="Chang" />  
      </Order>  
      <Order OrderID="22" CustomerID="ANATR">  
         <Product ProductID="33" ProductName="Aniseed Syrup" />  
        <Product ProductID="44" ProductName="Gumbo Mix" />  
      </Order>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="02b42-116">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="02b42-116">Start Visual Studio.</span></span>  
  
5.  <span data-ttu-id="02b42-117">Erstellen Sie eine C#- Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="02b42-117">Create a C# console application.</span></span>  
  
6.  <span data-ttu-id="02b42-118">Wählen Sie im Menü **Projekt** den Befehl **Verweis hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="02b42-118">From the **Project** menu, select **Add Reference**.</span></span>  
  
7.  <span data-ttu-id="02b42-119">Wählen Sie auf der Registerkarte **com** **Microsoft SQLXML Bulkload 4,0 Type Library** (xblkld4.dll) aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="02b42-119">In the **COM** tab, select **Microsoft SQLXML Bulkload 4.0 Type Library** (xblkld4.dll) and click **OK**.</span></span> <span data-ttu-id="02b42-120">Die im Projekt erstellte Assembly **Interop. SQLXMLBULKLOADLib** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="02b42-120">You will see the **Interop.SQLXMLBULKLOADLib** assembly created in the project.</span></span>  
  
8.  <span data-ttu-id="02b42-121">Ersetzen Sie die Main()-Methode durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="02b42-121">Replace the Main() method with the following code.</span></span> <span data-ttu-id="02b42-122">Aktualisieren Sie die **ConnectionString** -Eigenschaft und den Dateipfad zu den Schema-und Datendateien.</span><span class="sxs-lookup"><span data-stu-id="02b42-122">Update the **ConnectionString** property and the file path to the schema and data files.</span></span>  
  
    ```  
    [STAThread]  
       static void Main(string[] args)  
       {     
             try  
             {  
                SQLXMLBULKLOADLib.SQLXMLBulkLoad4Class objBL = new SQLXMLBULKLOADLib.SQLXMLBulkLoad4Class();  
                objBL.ConnectionString = "Provider=sqloledb;server=server;database=databaseName;integrated security=SSPI";  
                objBL.ErrorLogFile = "error.xml";  
                objBL.KeepIdentity = false;  
                objBL.Execute ("schema.xml","data.xml");  
             }  
             catch(Exception e)  
             {  
             Console.WriteLine(e.ToString());  
             }  
       }  
    ```  
  
9. <span data-ttu-id="02b42-123">Um das XML in die erstellte Tabelle zu laden, erstellen Sie das Projekt, und führen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="02b42-123">To load the XML in the table you created, build and run the project.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="02b42-124">Die Referenz zur Massenladenkomponente (xblkld4.dll) kann auch mithilfe des Tools tlbimp.exe hinzugefügt werden, das als Teil von .NET Framework zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="02b42-124">The reference to the Bulk Load component (xblkld4.dll) can also be added using the tlbimp.exe tool, which is available as part of .NET framework.</span></span> <span data-ttu-id="02b42-125">Dieses Tool erstellt einen verwalteten Wrapper für die systemeigene DLL (xblkld4.dll), der in allen .NET-Projekten verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="02b42-125">This tool creates a managed wrapper for the native DLL (xblkld4.dll), which can then be used in any .NET project.</span></span> <span data-ttu-id="02b42-126">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="02b42-126">For example:</span></span>  
  
    ```  
    c:\>tlbimp xblkld4.dll  
    ```  
  
     <span data-ttu-id="02b42-127">Dies erstellt die verwaltete Wrapper-DLL (SQLXMLBULKLOADLib.dll), die Sie im .NET Framework-Projekt verwenden können.</span><span class="sxs-lookup"><span data-stu-id="02b42-127">This creates the managed wrapper DLL (SQLXMLBULKLOADLib.dll) that you can use in the .NET Framework project.</span></span> <span data-ttu-id="02b42-128">In .NET Framework fügen Sie der neu erstellten DLL Projektverweise hinzu.</span><span class="sxs-lookup"><span data-stu-id="02b42-128">In the .NET Framework, you add project reference to the newly created DLL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02b42-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02b42-129">See Also</span></span>  
 [<span data-ttu-id="02b42-130">Ausführen von Massenladen von XML-Daten &#40;SQLXML 4.0&#41;</span><span class="sxs-lookup"><span data-stu-id="02b42-130">Performing Bulk Load of XML Data &#40;SQLXML 4.0&#41;</span></span>](bulk-load-xml/performing-bulk-load-of-xml-data-sqlxml-4-0.md)  
  
  
