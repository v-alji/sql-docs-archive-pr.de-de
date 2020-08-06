---
title: Verwenden von Datenbank-E-Mail | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- e-mail [SMO]
- Database Mail [SMO]
- mail [SMO]
ms.assetid: 7605390f-b485-48cc-8d97-e364a066067b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 86ceec7417638f53427ed5a62101f2fdb6d7440a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700917"
---
# <a name="using-database-mail"></a><span data-ttu-id="11eb9-102">Verwenden von Datenbank-E-Mail</span><span class="sxs-lookup"><span data-stu-id="11eb9-102">Using Database Mail</span></span>
  <span data-ttu-id="11eb9-103">In SMO wird das Datenbank-E-Mail-Subsystem durch das <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail>-Objekt dargestellt, auf das durch die <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A>-Eigenschaft verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="11eb9-103">In SMO, the Database Mail subsystem is represented by the <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object that is referenced by the <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> property.</span></span> <span data-ttu-id="11eb9-104">Durch die Verwendung des SMO-<xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail>-Objekts können Sie das Datenbank-E-Mail-Subsystem konfigurieren und Profile und E-Mail-Konten verwalten.</span><span class="sxs-lookup"><span data-stu-id="11eb9-104">By using the SMO <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object, you can configure the Database Mail subsystem and manage profiles and mail accounts.</span></span> <span data-ttu-id="11eb9-105">Das SMO-<xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail>-Objekt gehört zum `Server`-Objekt, d. h., der Bereich der E-Mail-Konten befindet sich auf Serverebene.</span><span class="sxs-lookup"><span data-stu-id="11eb9-105">The SMO <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object belongs to the `Server` object, meaning that scope of the mail accounts is at the server level.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="11eb9-106">Beispiele</span><span class="sxs-lookup"><span data-stu-id="11eb9-106">Examples</span></span>  
 <span data-ttu-id="11eb9-107">Zum Verwenden eines angegebenen Codebeispiels müssen Sie die Programmierumgebung, Programmiervorlage und die zu verwendende Programmiersprache auswählen, um Ihre Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="11eb9-107">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="11eb9-108">Weitere Informationen finden Sie unter [Erstellen eines Visual Basic SMO-Projekts in Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) oder [Erstellen eines Visual C&#35; SMO-Projekts in Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="11eb9-108">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
 <span data-ttu-id="11eb9-109">Für Programme, die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Datenbank-E-Mail verwenden, müssen Sie die-Anweisung einschließen, `Imports` um den e-Mail-Namespace zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="11eb9-109">For programs that use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Database Mail, you must include the `Imports` statement to qualify the Mail namespace.</span></span> <span data-ttu-id="11eb9-110">Fügen Sie die Anweisung nach den anderen `Imports`-Anweisungen und vor jeglichen Deklarationen in der Anwendung wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="11eb9-110">Insert the statement after the other `Imports` statements, before any declarations in the application, such as:</span></span>  
  
 `Imports Microsoft.SqlServer.Management.Smo`  
  
 `Imports Microsoft.SqlServer.Management.Common`  
  
 `Imports Microsoft.SqlServer.Management.Smo.Mail`  
  
## <a name="creating-a-database-mail-account-by-using-visual-basic"></a><span data-ttu-id="11eb9-111">Erstellen eines Datenbank-E-Mail-Kontos mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="11eb9-111">Creating a Database Mail Account by Using Visual Basic</span></span>  
 <span data-ttu-id="11eb9-112">In diesem Codebeispiel wird gezeigt, wie ein E-Mail-Konto in SMO erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="11eb9-112">This code example shows how to create an e-mail account in SMO.</span></span> <span data-ttu-id="11eb9-113">Datenbank-E-Mail wird durch das <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail>-Objekt dargestellt und durch die <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A>-Eigenschaft des <xref:Microsoft.SqlServer.Management.Smo.Server>-Objekts verwiesen.</span><span class="sxs-lookup"><span data-stu-id="11eb9-113">Database Mail is represented by the <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object and referenced by the <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="11eb9-114">SMO kann verwendet werden, um programmgesteuert Datenbank-E-Mails zu konfigurieren. Das Senden von E-Mails und die Behandlung empfangener E-Mails sind allerdings hierüber nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="11eb9-114">SMO can be used to programmatically configure Database Mail, but it cannot be used to send or handle received e-mail.</span></span>  
  
 <span data-ttu-id="11eb9-115">VB.NET</span><span class="sxs-lookup"><span data-stu-id="11eb9-115">VB.NET</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMail1](SMO How to#SMO_VBMail1)]  -->  
  
## <a name="creating-a-database-mail-account-by-using-visual-c"></a><span data-ttu-id="11eb9-116">Erstellen eines Datenbank-E-Mail-Kontos mit Visual C#</span><span class="sxs-lookup"><span data-stu-id="11eb9-116">Creating a Database Mail Account by Using Visual C#</span></span>  
 <span data-ttu-id="11eb9-117">In diesem Codebeispiel wird gezeigt, wie ein E-Mail-Konto in SMO erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="11eb9-117">This code example shows how to create an e-mail account in SMO.</span></span> <span data-ttu-id="11eb9-118">Datenbank-E-Mail wird durch das <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail>-Objekt dargestellt und durch die <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A>-Eigenschaft des <xref:Microsoft.SqlServer.Management.Smo.Server>-Objekts verwiesen.</span><span class="sxs-lookup"><span data-stu-id="11eb9-118">Database Mail is represented by the <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object and referenced by the <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="11eb9-119">SMO kann verwendet werden, um programmgesteuert Datenbank-E-Mails zu konfigurieren. Das Senden von E-Mails und die Behandlung empfangener E-Mails sind allerdings hierüber nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="11eb9-119">SMO can be used to programmatically configure Database Mail, but it cannot be used to send or handle received e-mail.</span></span>  
  
```csharp  
{  
         //Connect to the local, default instance of SQL Server.  
         Server srv = default(Server);   
           srv = new Server();   
           //Define the Database Mail service with a SqlMail object variable   
           //and reference it using the Server Mail property.   
           SqlMail sm;   
           sm = srv.Mail;   
           //Define and create a mail account by supplying the Database Mail  
           //service, name, description, display name, and email address  
           //arguments in the constructor.   
           MailAccount a = default(MailAccount);   
           a = new MailAccount(sm, "AdventureWorks2012 Administrator", "AdventureWorks2012 Automated Mailer", "Mail account for administrative e-mail.", "dba@Adventure-Works.com");   
           a.Create();    
}  
```  
  
## <a name="creating-a-database-mail-account-by-using-powershell"></a><span data-ttu-id="11eb9-120">Erstellen eines Datenbank-E-Mail-Kontos mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="11eb9-120">Creating a Database Mail Account by Using PowerShell</span></span>  
 <span data-ttu-id="11eb9-121">In diesem Codebeispiel wird gezeigt, wie ein E-Mail-Konto in SMO erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="11eb9-121">This code example shows how to create an e-mail account in SMO.</span></span> <span data-ttu-id="11eb9-122">Datenbank-E-Mail wird durch das <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail>-Objekt dargestellt und durch die <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A>-Eigenschaft des <xref:Microsoft.SqlServer.Management.Smo.Server>-Objekts verwiesen.</span><span class="sxs-lookup"><span data-stu-id="11eb9-122">Database Mail is represented by the <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object and referenced by the <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="11eb9-123">SMO kann verwendet werden, um programmgesteuert Datenbank-E-Mails zu konfigurieren. Das Senden von E-Mails und die Behandlung empfangener E-Mails sind allerdings hierüber nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="11eb9-123">SMO can be used to programmatically configure Database Mail, but it cannot be used to send or handle received e-mail.</span></span>
  
```powershell  
#Connect to the local, default instance of SQL Server.  
  
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#Define the Database Mail; reference it using the Server Mail property.  
$sm = $srv.Mail  
  
#Define and create a mail account by supplying the Database Mail service,  
#name, description, display name, and email address arguments in the constructor.  
$a = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Mail.MailAccount -ArgumentList $sm, `  
"Adventure Works Administrator", "Adventure Works Automated Mailer",`  
 "Mail account for administrative e-mail.", "dba@Adventure-Works.com"  
$a.Create()  
```  
