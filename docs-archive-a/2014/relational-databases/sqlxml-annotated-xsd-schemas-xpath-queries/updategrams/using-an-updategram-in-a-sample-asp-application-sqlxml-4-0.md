---
title: Verwenden eines Update Grams in einer Beispiel-ASP-Anwendung (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- ASP applications [SQLXML]
- Active Server Pages
- updategrams [SQLXML], ASP applications
ms.assetid: 10eff799-4c39-4b52-8b38-7ea6f68454a8
author: rothja
ms.author: jroth
ms.openlocfilehash: 50dce61e5bd3111244defe9cc18e808580687185
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619732"
---
# <a name="using-an-updategram-in-a-sample-asp-application-sqlxml-40"></a><span data-ttu-id="4eee1-102">Verwenden eines Updategrams in einer Beispiel-ASP-Anwendung (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="4eee1-102">Using an Updategram in a Sample ASP Application (SQLXML 4.0)</span></span>
  <span data-ttu-id="4eee1-103">Diese ASP (Active Server Pages)-Anwendung ermöglicht es Ihnen, Kundendaten in der Tabelle Person.Contact der Beispieldatenbank AdventureWorks in Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4eee1-103">This Active Server Pages (ASP) application allows you to update customer information in the Person.Contact table in the AdventureWorks sample database in Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4eee1-104">Die Anwendung führt Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="4eee1-104">The application does the following:</span></span>  
  
-   <span data-ttu-id="4eee1-105">Sie fordert den Benutzer zur Eingabe einer Kontakt-ID auf.</span><span class="sxs-lookup"><span data-stu-id="4eee1-105">Asks the user to enter a contact ID.</span></span>  
  
-   <span data-ttu-id="4eee1-106">Verwendet diesen Kunden-ID-Wert, um eine Vorlage auszuführen, mit der Kontaktinformationen aus der Tabelle Person.Contact abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4eee1-106">Uses this customer ID value to execute a template to retrieve contact information from the Person.Contact table.</span></span>  
  
-   <span data-ttu-id="4eee1-107">Sie zeigt diese Informationen in einem HTML-Formular an.</span><span class="sxs-lookup"><span data-stu-id="4eee1-107">Displays this information by using an HTML form.</span></span>  
  
 <span data-ttu-id="4eee1-108">Der Benutzer kann die Kontaktinformationen außer der Kontakt-ID (weil die Spalte ContactID den Primärschlüssel darstellt) dann aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4eee1-108">The user can then update contact information but not the contact ID (because the ContactID is the primary key).</span></span> <span data-ttu-id="4eee1-109">Nachdem der Benutzer die Informationen übermittelt hat, wird ein Updategram ausgeführt, und alle Formularparameter werden dem Updategram übergeben.</span><span class="sxs-lookup"><span data-stu-id="4eee1-109">After the user submits the information, an updategram is executed and all the form parameters are passed to the updategram.</span></span>  
  
 <span data-ttu-id="4eee1-110">Die folgende Vorlage ist die erste Vorlage (GetContact.xml).</span><span class="sxs-lookup"><span data-stu-id="4eee1-110">The following template is the first template (GetContact.xml).</span></span> <span data-ttu-id="4eee1-111">Speichern Sie diese Vorlage in dem Verzeichnis, das dem virtuellen Namen des `template`-Typs zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="4eee1-111">Save this template in the directory that is associated with the virtual name of `template` type.</span></span>  
  
```  
<root xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
   <sql:header>  
      <sql:param name="cid"></sql:param>  
   </sql:header>  
   <sql:query>  
      SELECT  *   
      FROM    Person.Contact  
      WHERE   ContactID=@cid   
      FOR XML AUTO  
   </sql:query>  
</root>  
```  
  
 <span data-ttu-id="4eee1-112">Die folgende Vorlage ist die zweite Vorlage (UpdateContact.xml).</span><span class="sxs-lookup"><span data-stu-id="4eee1-112">The following template is the second template (UpdateContact.xml).</span></span> <span data-ttu-id="4eee1-113">Speichern Sie diese Vorlage in dem Verzeichnis, das dem virtuellen Namen des `template`-Typs zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="4eee1-113">Save this template in the directory that is associated with the virtual name of `template` type.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:header>  
   <updg:param name="cid"/>  
   <updg:param name="title" />  
   <updg:param name="firstname" />  
   <updg:param name="lastname" />  
   <updg:param name="emailaddress" />  
   <updg:param name="phone" />  
</updg:header>  
<updg:sync >  
   <updg:before>  
      <Person.Contact ContactID="$cid" />   
   </updg:before>  
   <updg:after>  
      <Person.Contact ContactID="$cid"   
       Title="$title"  
       FirstName="$firstname"  
       LastName="$lastname"  
       EmailAddress="$emailaddress"  
       Phone="$phone"/>  
   </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="4eee1-114">Der folgende Code stellt die ASP-Beispielanwendung (SampleASP.asp) dar.</span><span class="sxs-lookup"><span data-stu-id="4eee1-114">The following code is the ASP application (SampleASP.asp).</span></span> <span data-ttu-id="4eee1-115">Speichern Sie sie in dem Verzeichnis, das einem virtuellen Stammverzeichnis zugeordnet ist, welches Sie mit dem Hilfsprogramm Internetdienste-Manager erstellen.</span><span class="sxs-lookup"><span data-stu-id="4eee1-115">Save it in the directory that is associated with a virtual root that you create by using the Internet Services Manager utility.</span></span> <span data-ttu-id="4eee1-116">(Dieses virtuelle Stammverzeichnis wird nicht mit dem IIS-Hilfsprogramm Virtual Directory Management für [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] erstellt, weil das IIS-Hilfsprogramm Virtual Directory Management für [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] auf ASP-Anwendungen weder zugreifen noch diese identifizieren kann.)</span><span class="sxs-lookup"><span data-stu-id="4eee1-116">(This virtual root is not created by using the IIS Virtual Directory Management for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utility because IIS Virtual Directory Management for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] cannot access or identify ASP applications.).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4eee1-117">Im Code müssen Sie "ServerName" durch den Namen des Servers ersetzen, auf dem Microsoft Internet-Informationsdienste (IIS) ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4eee1-117">In the code, you must replace "ServerName" with the name of the server running Microsoft Internet Information Services (IIS).</span></span>  
  
```  
<% LANGUAGE=VBSCRIPT %>  
<%  
  Dim ContactID  
  ContactID=Request.Form("cid")  
%>  
<html>  
<body>  
<%  
  'If a ContactID value is not yet provided, display this form.  
  if ContactID="" then  
%>  
<!-- If the ContactID has not been specified, display the form that allows users to enter an ID. -->  
<form action="AdventureWorksContacts.asp" method="POST">  
<br>  
Enter ContactID: <input type=text name="cid"><br>  
<input type=submit value="Submit this ID" ><br><br>  
<-- Otherwise, if a ContactID is entered, display the second part of the form where the user can change customer information. -->  
<%  
  else  
%>  
<form name="Contacts" action="http://localhost/AdventureWorks/Template/UpdateContact.xml" method="POST">  
You may update customer information below.<br><br>  
<!-- A comment goes here to separate the parts of the application or page. -->  
<br>  
<%  
  ' Load the document in the parser and extract the values to populate the form.  
    Set objXML=Server.CreateObject("MSXML2.DomDocument")  
    ObjXML.setProperty "ServerHTTPRequest", TRUE  
  
    objXML.async=False  
    objXML.Load("http://localhost/AdventureWorks/Template/GetContact.xml?cid=" & ContactID)  
    set objCustomer=objXML.documentElement.childNodes.Item(0)  
  
  ' In retrieving data from the database, if a value in the column is NULL there  
  '  is no attribute for the corresponding element. In this case,  
  ' skip the error generation and go to the next attribute.  
  
  On Error Resume Next  
  
  Response.Write "Contact ID: <input type=text readonly=true style='background-color:silver' name=cid value="""  
  Response.Write objCustomer.attributes(0).value  
  Response.Write """><br><br>"  
  
  Response.Write "Title: <input type=text name=title value="""  
  Response.Write objCustomer.attributes(1).value  
  Response.Write """><br><br>"  
  
  Response.Write "First Name: <input type=text name=firstname value="""  
  Response.Write objCustomer.attributes(2).value  
  Response.Write """><br>"  
  
  Response.Write "Last Name: <input type=text name=lastname value="""  
  Response.Write objCustomer.attributes(3).value  
  Response.Write """><br><br>"  
  
  Response.Write "Email Address: <input type=text name=emailaddress value="""  
  Response.Write objCustomer.attributes(4).value  
  Response.Write """><br><br>"  
  
  Response.Write "Phone: <input type=text name=phone value="""  
  Response.Write objCustomer.attributes(9).value  
  Response.Write """><br><br>"  
  
  set objCustomer=Nothing  
  Set objXML=Nothing  
%>  
<input type="submit" value="Submit this change" ><br><br>  
<input type=hidden name="contenttype" value="text/xml">  
<input type=hidden name="eeid" value="<%=ContactID%>"><br><br>  
<% end if %>  
  
</form>  
</body>  
</html>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4eee1-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4eee1-118">See Also</span></span>  
 [<span data-ttu-id="4eee1-119">Sicherheitsüberlegungen zu Update grams &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="4eee1-119">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
