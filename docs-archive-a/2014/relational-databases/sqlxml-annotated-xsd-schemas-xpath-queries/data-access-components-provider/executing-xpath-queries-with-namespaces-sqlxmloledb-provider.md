---
title: Ausführen von XPath-Abfragen mit Namespaces (SQLXMLOLEDB-Anbieter) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXMLOLEDB Provider, executing XPath queries
- namespaces property
- queries [SQLXML], SQLXMLOLEDB Provider
- XPath queries [SQLXML], namespaces
- XPath queries [SQLXML], SQLXMLOLEDB Provider
- namespaces [SQLXML], XPath queries
ms.assetid: 024a4b7d-435d-47ba-9e80-2c2f640108f5
author: rothja
ms.author: jroth
ms.openlocfilehash: ff692b49a4c32c14655af3a9eb07071dc60ba2a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700893"
---
# <a name="executing-xpath-queries-with-namespaces-sqlxmloledb-provider"></a><span data-ttu-id="96a20-102">Ausführen von XPath-Abfragen mit Namespaces (SQLXMLOLEDB-Anbieter)</span><span class="sxs-lookup"><span data-stu-id="96a20-102">Executing XPath Queries with Namespaces (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="96a20-103">XPath-Abfragen können Namespaces enthalten.</span><span class="sxs-lookup"><span data-stu-id="96a20-103">XPath queries can include namespaces.</span></span> <span data-ttu-id="96a20-104">Wenn die Schemaelemente mit Namespace angegeben wurden (d. h. wenn Sie einen Zielnamespace enthalten), dann müssen mit diesem Schema ausgeführte XPath-Abfragen diesen Namespace angeben.</span><span class="sxs-lookup"><span data-stu-id="96a20-104">If the schema elements are namespace qualified (that is, if they include a target namespace), XPath queries against the schema must specify this namespace.</span></span>  
  
 <span data-ttu-id="96a20-105">Weil die Verwendung des Platzhalterzeichens (\*) in SQLXML 4.0 nicht unterstützt wird, müssen Sie die XPath-Abfrage mithilfe eines Namespacepräfix angeben.</span><span class="sxs-lookup"><span data-stu-id="96a20-105">Because using the wildcard character (\*) is not supported in SQLXML 4.0, you must specify the XPath query by using a namespace prefix.</span></span> <span data-ttu-id="96a20-106">Um dieses Präfix aufzulösen, geben Sie mit der Namespace-Eigenschaft die Namespace Bindung an.</span><span class="sxs-lookup"><span data-stu-id="96a20-106">To resolve this prefix, use the namespaces property to specify the namespace binding.</span></span>  
  
 <span data-ttu-id="96a20-107">Im folgenden Beispiel gibt die XPath-Abfrage Namespaces mit den Platzhalter Zeichen ( \* ) und den XPath-Funktionen local-Name () und Namespace-URI () an.</span><span class="sxs-lookup"><span data-stu-id="96a20-107">In the following example, the XPath query specifies namespaces by using the wildcard character (\*) and the local-name() and namespace-uri() XPath functions.</span></span> <span data-ttu-id="96a20-108">Diese XPath-Abfrage gibt alle Elemente zurück, bei denen der lokale Name `Contact` und der Namespace-URI `urn:myschema:Contacts` lautet.</span><span class="sxs-lookup"><span data-stu-id="96a20-108">This XPath query returns all the elements where the local name is `Contact` and the namespace URI is `urn:myschema:Contacts`.</span></span>  
  
```  
/*[local-name() = 'Contact' and namespace-uri() = 'urn:myschema:Contacts']  
```  
  
 <span data-ttu-id="96a20-109">In SQLXML 4.0 muss diese XPath-Abfrage mit einem Namespacepräfix angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="96a20-109">In SQLXML 4.0, this XPath query must be specified with a namespace prefix.</span></span> <span data-ttu-id="96a20-110">Ein Beispiel ist `x:Contact`, wobei `x` für das Namespacepräfix steht.</span><span class="sxs-lookup"><span data-stu-id="96a20-110">An example is `x:Contact`, where `x` is the namespace prefix.</span></span> <span data-ttu-id="96a20-111">Betrachten Sie folgendes XSD-Schema:</span><span class="sxs-lookup"><span data-stu-id="96a20-111">Consider the following XSD schema:</span></span>  
  
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
  
 <span data-ttu-id="96a20-112">Weil dieses Schema einen Zielnamespace definiert, müssen XPath-Abfragen (beispielsweise "Employee"), die mit diesem Schema ausgeführt werden, einen Namespace enthalten.</span><span class="sxs-lookup"><span data-stu-id="96a20-112">Because this schema defines the target namespace, an XPath query (such as "Employee") against the schema must include the namespace.</span></span>  
  
 <span data-ttu-id="96a20-113">Dies ist eine [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic-Beispielanwendung, die eine XPath-Abfrage (x:Employee) mit dem vorstehenden XSD-Schema ausführt.</span><span class="sxs-lookup"><span data-stu-id="96a20-113">This is a sample [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic application that executes an XPath query (x:Employee) against the preceding XSD schema.</span></span> <span data-ttu-id="96a20-114">Um das Präfix aufzulösen, wird die Namespace Bindung mithilfe der Namespace-Eigenschaft angegeben.</span><span class="sxs-lookup"><span data-stu-id="96a20-114">To resolve the prefix, the namespace binding is specified by using the namespaces property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="96a20-115">Im Code müssen Sie den Namen der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in der Verbindungszeichenfolge bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="96a20-115">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="96a20-116">In diesem Beispiel wird überdies die Verwendung von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) als Datenanbieter angegeben, was die Installation zusätzlicher Netzwerkclientsoftware erforderlich macht.</span><span class="sxs-lookup"><span data-stu-id="96a20-116">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) for the data provider, which requires additional network client software to be installed.</span></span> <span data-ttu-id="96a20-117">Weitere Informationen finden Sie unter [System Anforderungen für SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="96a20-117">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
Private Sub Form_Load()  
    Dim con As New ADODB.Connection  
    Dim cmd As New ADODB.Command  
    Dim stm As New ADODB.Stream  
    con.Open "provider=SQLXMLOLEDB.4.0;Data Provider=SQLNCLI11;Data Source=SqlServerName;Initial Catalog=AdventureWorks;Integrated Security=SSPI;"  
    Set cmd.ActiveConnection = con  
    stm.Open  
    cmd.Properties("Output Stream").Value = stm  
    cmd.Properties("Output Encoding") = "utf-8"  
    cmd.Properties("Mapping schema") = "C:\DirectoryPath\con-ex.xml"  
    cmd.Properties("namespaces") = "xmlns:x='urn:myschema:Contacts'"  
    '  Debug.Print "Set Command Dialect to DBGUID_XPATH"  
    cmd.Dialect = "{ec2a4293-e898-11d2-b1b7-00c04f680c56}"  
    cmd.CommandText = "x:Contact"  
    cmd.Execute , , adExecuteStream   
    stm.Position = 0  
    Debug.Print stm.ReadText(adReadAll)  
End Sub  
```  
  
### <a name="to-test-this-application"></a><span data-ttu-id="96a20-118">So testen Sie diese Anwendung</span><span class="sxs-lookup"><span data-stu-id="96a20-118">To test this application</span></span>  
  
1.  <span data-ttu-id="96a20-119">Speichern Sie das XSD-Beispielschema in einem Ordner.</span><span class="sxs-lookup"><span data-stu-id="96a20-119">Save the sample XSD schema in a folder.</span></span>  
  
2.  <span data-ttu-id="96a20-120">Erstellen Sie ein Visual Basic-Projekt für eine ausführbare Anwendung, und kopieren Sie den Code dort hinein.</span><span class="sxs-lookup"><span data-stu-id="96a20-120">Create a Visual Basic executable project, and copy the code into it.</span></span> <span data-ttu-id="96a20-121">Ändern Sie, falls erforderlich, den angegebenen Verzeichnispfad.</span><span class="sxs-lookup"><span data-stu-id="96a20-121">Change the specified directory path as appropriate.</span></span>  
  
3.  <span data-ttu-id="96a20-122">Fügen Sie den folgenden Projektverweis hinzu.</span><span class="sxs-lookup"><span data-stu-id="96a20-122">Add the following project reference:</span></span>  
  
    ```  
    "Microsoft ActiveX Data Objects 2.8 Library"  
    ```  
  
4.  <span data-ttu-id="96a20-123">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="96a20-123">Execute the application.</span></span>  
  
 <span data-ttu-id="96a20-124">Dies ist das Teilergebnis:</span><span class="sxs-lookup"><span data-stu-id="96a20-124">This is the partial result:</span></span>  
  
```  
<y0:Employee xmlns:y0="urn:myschema:Contacts"   
             LName="Achong" CID="1" FName="Gustavo"/>  
<y0:Employee xmlns:y0="urn:myschema:Employees"   
             LName="Abel" CID="2" FName="Catherine"/>  
```  
  
 <span data-ttu-id="96a20-125">Die im XML-Dokument generierten Präfixe sind zwar zufällig gewählt, jedoch dem gleichen Namespace zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="96a20-125">The prefixes that are generated in the XML document are arbitrary, but they map to the same namespace.</span></span>  
  
  
