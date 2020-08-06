---
title: Verwenden von XML-Schemas | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- XML [SMO]
ms.assetid: 9d04de01-efeb-4b2d-8c28-3234bc7ff2f3
author: stevestein
ms.author: sstein
ms.openlocfilehash: a0e5c58bb05da7025651a4e55e29541d694ba1ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725357"
---
# <a name="using-xml-schemas"></a><span data-ttu-id="ac18d-102">Verwenden von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="ac18d-102">Using XML Schemas</span></span>
  <span data-ttu-id="ac18d-103">Die XML-Programmierung in SMO ist auf die Bereitstellung von XML-Datentypen, XML-Namespaces und eine einfache Indizierung für XML-Datentypspalten beschränkt.</span><span class="sxs-lookup"><span data-stu-id="ac18d-103">XML programming in SMO is limited to providing XML data types, XML namespaces, and simple indexing on XML data type columns.</span></span>  
  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="ac18d-104">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]stellt systemeigenen Speicher für XML-Dokument Instanzen bereit.</span><span class="sxs-lookup"><span data-stu-id="ac18d-104">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provides native storage for XML document instances.</span></span> <span data-ttu-id="ac18d-105">Über XML-Schemas können Sie komplexe XML-Datentypen definieren, die für die Validierung von XML-Dokumenten verwendet werden können, um die Datenintegrität sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="ac18d-105">XML schemas let you define complex XML data types, which can be used to validate XML documents to ensure data integrity.</span></span> <span data-ttu-id="ac18d-106">Das XML-Schema wird im <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection>-Objekt definiert.</span><span class="sxs-lookup"><span data-stu-id="ac18d-106">The XML schema is defined in the <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac18d-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ac18d-107">Example</span></span>  
 <span data-ttu-id="ac18d-108">Zum Verwenden eines angegebenen Codebeispiels müssen Sie die Programmierumgebung, Programmiervorlage und die zu verwendende Programmiersprache auswählen, um Ihre Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ac18d-108">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="ac18d-109">Weitere Informationen finden Sie unter [Erstellen eines Visual Basic SMO-Projekts in Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) oder [Erstellen eines Visual C&#35; SMO-Projekts in Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="ac18d-109">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-an-xml-schema-in-visual-basic"></a><span data-ttu-id="ac18d-110">Erstellen eines XML-Schemas in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ac18d-110">Creating an XML Schema in Visual Basic</span></span>  
 <span data-ttu-id="ac18d-111">Dieses Codebeispiel zeigt, wie ein XML-Schema mithilfe des <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection>-Objekts erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ac18d-111">This code example shows how to create an XML schema by using the <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> object.</span></span> <span data-ttu-id="ac18d-112">Die <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A>-Eigenschaft, die die XML-Schemaauflistung definiert, enthält mehrere doppelte Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="ac18d-112">The <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A> property, which defines the XML schema collection, contains several double quotation marks.</span></span> <span data-ttu-id="ac18d-113">Diese werden durch die `chr(34)` -Zeichenfolge ersetzt.</span><span class="sxs-lookup"><span data-stu-id="ac18d-113">These are replaced by the `chr(34)` string.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBXMLSchema1](SMO How to#SMO_VBXMLSchema1)]  -->  
  
## <a name="creating-an-xml-schema-in-visual-c"></a><span data-ttu-id="ac18d-114">Erstellen eines XML-Schemas in Visual C#</span><span class="sxs-lookup"><span data-stu-id="ac18d-114">Creating an XML Schema in Visual C#</span></span>  
 <span data-ttu-id="ac18d-115">Dieses Codebeispiel zeigt, wie ein XML-Schema mithilfe des <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection>-Objekts erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ac18d-115">This code example shows how to create an XML schema by using the <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> object.</span></span> <span data-ttu-id="ac18d-116">Die <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A>-Eigenschaft, die die XML-Schemaauflistung definiert, enthält mehrere doppelte Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="ac18d-116">The <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A> property, which defines the XML schema collection, contains several double quotation marks.</span></span> <span data-ttu-id="ac18d-117">Diese werden durch die `chr(34)` -Zeichenfolge ersetzt.</span><span class="sxs-lookup"><span data-stu-id="ac18d-117">These are replaced by the `chr(34)` string.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv = default(Server);  
            srv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database db = default(Database);  
            db = srv.Databases["AdventureWorks2012"];  
            //Define an XmlSchemaCollection object by supplying the parent  
            // database and name arguments in the constructor.   
            XmlSchemaCollection xsc = default(XmlSchemaCollection);  
            xsc = new XmlSchemaCollection(db, "MySampleCollection");  
            xsc.Text = "<schema xmlns=" + Strings.Chr(34) + "http://www.w3.org/2001/XMLSchema" + Strings.Chr(34) + " xmlns:ns=" + Strings.Chr(34) + "http://ns" + Strings.Chr(34) + "><element name=" + Strings.Chr(34) + "e" + Strings.Chr(34) + " type=" + Strings.Chr(34) + "dateTime" + Strings.Chr(34) + "/></schema>";  
            //Create the XML schema collection on the instance of SQL Server.   
            xsc.Create();  
        }  
```  
  
## <a name="creating-an-xml-schema-in-powershell"></a><span data-ttu-id="ac18d-118">Erstellen eines XML-Schemas in PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac18d-118">Creating an XML Schema in PowerShell</span></span>  
 <span data-ttu-id="ac18d-119">Dieses Codebeispiel zeigt, wie ein XML-Schema mithilfe des <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection>-Objekts erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ac18d-119">This code example shows how to create an XML schema by using the <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> object.</span></span> <span data-ttu-id="ac18d-120">Die <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A>-Eigenschaft, die die XML-Schemaauflistung definiert, enthält mehrere doppelte Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="ac18d-120">The <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A> property, which defines the XML schema collection, contains several double quotation marks.</span></span> <span data-ttu-id="ac18d-121">Diese werden durch die `chr(34)` -Zeichenfolge ersetzt.</span><span class="sxs-lookup"><span data-stu-id="ac18d-121">These are replaced by the `chr(34)` string.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance replace LocalMachine with the physical server  
cd \sql\LocalHost  
$srv = Get-Item default  
  
#Reference the AdventureWorks database.  
$db = $srv.Databases["AdventureWorks2012"]  
  
#Create a new schema collection  
$xsc = New-Object -TypeName Microsoft.SqlServer.Management.SMO.XmlSchemaCollection `  
-argumentlist $db,"MySampleCollection"  
  
#Add the xml  
$dq = '"' # the double quote character  
$xsc.Text = "<schema xmlns=" + $dq + "http://www.w3.org/2001/XMLSchema" + $dq + `  
"  xmlns:ns=" + $dq + "http://ns" + $dq + "><element name=" + $dq + "e" + $dq +`  
 " type=" + $dq + "dateTime" + $dq + "/></schema>"  
  
#Create the XML schema collection on the instance of SQL Server.  
$xsc.Create()  
```  
