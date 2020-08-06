---
title: Authentifizierung in Reporting Services | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], authentication
- forms-based authentication [Reporting Services]
- authentication [Reporting Services]
- custom authentication [Reporting Services]
ms.assetid: 103ce1f9-31d8-44bb-b540-2752e4dcf60b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 59e97ba6ef849d8b4bfddfd6953c85826e351d6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618525"
---
# <a name="authentication-in-reporting-services"></a><span data-ttu-id="77d4e-102">Authentifizierung in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="77d4e-102">Authentication in Reporting Services</span></span>
  <span data-ttu-id="77d4e-103">Unter Authentifizierung versteht man den Prozess, Benutzerrechte für eine bestimmte Identität einzurichten.</span><span class="sxs-lookup"><span data-stu-id="77d4e-103">Authentication is the process of establishing a user's right to an identity.</span></span> <span data-ttu-id="77d4e-104">Es gibt viele Techniken, die Sie verwenden können, um einen Benutzer zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="77d4e-104">There are many techniques that you can use to authenticate a user.</span></span> <span data-ttu-id="77d4e-105">Die gängigste Methode ist die Verwendung von Kennwörtern.</span><span class="sxs-lookup"><span data-stu-id="77d4e-105">The most common way is to use passwords.</span></span> <span data-ttu-id="77d4e-106">Wenn Sie beispielsweise die Formularauthentifizierung implementieren, benötigen Sie eine Implementierung, bei der die Benutzer nach den Anmeldeinformationen durchsucht werden (normalerweise über eine Oberfläche, in der Anmeldename und Kennwort angefordert werden) und bei der die Benutzer mit einem Datenspeicher, z. B. einer Datenbanktabelle oder einer Konfigurationsdatei, abgeglichen werden.</span><span class="sxs-lookup"><span data-stu-id="77d4e-106">When you implement Forms Authentication, for example, you want an implementation that queries users for credentials (usually by some interface that requests a login name and password) and then validates users against a data store, such as a database table or configuration file.</span></span> <span data-ttu-id="77d4e-107">Wenn die Anmeldeinformationen nicht validiert werden können, schlägt der Authentifizierungsprozess fehl, und der Benutzer nimmt eine anonyme Identität an.</span><span class="sxs-lookup"><span data-stu-id="77d4e-107">If the credentials can't be validated, the authentication process fails and the user will assume an anonymous identity.</span></span>  
  
## <a name="custom-authentication-in-reporting-services"></a><span data-ttu-id="77d4e-108">Benutzerdefinierte Authentifizierung in den Reporting Services</span><span class="sxs-lookup"><span data-stu-id="77d4e-108">Custom Authentication in Reporting Services</span></span>  
 <span data-ttu-id="77d4e-109">In [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] behandelt das Windows-Betriebssystem die Benutzerauthentifizierung entweder über integrierte Sicherheitsfunktionen oder über die ausdrückliche Annahme und Validierung der Anmeldeinformationen des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="77d4e-109">In [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], the Windows operating system handles the authentication of users either through integrated security or through the explicit reception and validation of user credentials.</span></span> <span data-ttu-id="77d4e-110">Die benutzerdefinierte Authentifizierung kann in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] so entwickelt werden, dass zusätzliche Authentifizierungsschemen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="77d4e-110">Custom authentication can be developed in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] to support additional authentication schemes.</span></span> <span data-ttu-id="77d4e-111">Dies wird durch die Sicherheitserweiterungsschnittstelle <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension> ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="77d4e-111">This is made possible through the security extension interface <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension>.</span></span> <span data-ttu-id="77d4e-112">Alle Erweiterungen erben für jede vom Berichtsserver bereitgestellte und verwendete Erweiterung von der <xref:Microsoft.ReportingServices.Interfaces.IExtension>-Basisschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="77d4e-112">All extensions inherit from the <xref:Microsoft.ReportingServices.Interfaces.IExtension> base interface for any extension deployed and used by the report server.</span></span> <span data-ttu-id="77d4e-113"><xref:Microsoft.ReportingServices.Interfaces.IExtension> und <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension> sind Elemente des <xref:Microsoft.ReportingServices.Interfaces>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="77d4e-113"><xref:Microsoft.ReportingServices.Interfaces.IExtension>, as well as <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension>, are members of the <xref:Microsoft.ReportingServices.Interfaces> namespace.</span></span>  
  
 <span data-ttu-id="77d4e-114">Die primäre Möglichkeit, auf einem Berichtsserver in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] authentifiziert zu werden, ist die <xref:ReportService2010.ReportingService2010.LogonUser%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="77d4e-114">The primary way to authenticate against a report server in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] is the <xref:ReportService2010.ReportingService2010.LogonUser%2A> method.</span></span> <span data-ttu-id="77d4e-115">Dieses Element des Reporting Services-Webdiensts kann verwendet werden, um die Benutzeranmeldeinformationen zur Validierung an einen Berichtsserver zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="77d4e-115">This member of the Reporting Services Web service can be used to pass user credentials to a report server for validation.</span></span> <span data-ttu-id="77d4e-116">Die zugrunde liegende Sicherheits Erweiterung implementiert **IAuthenticationExtension. LogonUser** , das den benutzerdefinierten Authentifizierungscode enthält.</span><span class="sxs-lookup"><span data-stu-id="77d4e-116">Your underlying security extension implements **IAuthenticationExtension.LogonUser** which contains your custom authentication code.</span></span> <span data-ttu-id="77d4e-117">Im Beispiel zur Formularauthentifizierung wird mit **LogonUser** eine Authentifizierungsprüfung der angegebenen Anmeldeinformationen und eines benutzerdefinierten Benutzerspeichers in einer Datenbank durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="77d4e-117">In the Forms Authentication sample, **LogonUser**, which performs an authentication check against the supplied credentials and a custom user store in a database.</span></span> <span data-ttu-id="77d4e-118">Ein Beispiel für die Implementierung von **LogonUser** sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="77d4e-118">An example of an implementation of **LogonUser** looks like this:</span></span>  
  
```  
public bool LogonUser(string userName, string password, string authority)  
{  
   return AuthenticationUtilities.VerifyPassword(userName, password);  
}  
  
```  
  
 <span data-ttu-id="77d4e-119">Die folgende Beispielfunktion wird verwendet, um die angegebenen Anmeldeinformationen zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="77d4e-119">The following sample function is used to verify the supplied credentials:</span></span>  
  
```  
  
internal static bool VerifyPassword(string suppliedUserName,  
   string suppliedPassword)  
{   
   bool passwordMatch = false;  
   // Get the salt and pwd from the database based on the user name.  
   // See "How To: Use DPAPI (Machine Store) from ASP.NET," "How To:  
   // Use DPAPI (User Store) from Enterprise Services," and "How To:  
   // Create a DPAPI Library" for more information about how to use  
   // DPAPI to securely store connection strings.  
   SqlConnection conn = new SqlConnection(  
      "Server=localhost;" +   
      "Integrated Security=SSPI;" +  
      "database=UserAccounts");  
   SqlCommand cmd = new SqlCommand("LookupUser", conn);  
   cmd.CommandType = CommandType.StoredProcedure;  
  
   SqlParameter sqlParam = cmd.Parameters.Add("@userName",  
       SqlDbType.VarChar,  
       255);  
   sqlParam.Value = suppliedUserName;  
   try  
   {  
      conn.Open();  
      SqlDataReader reader = cmd.ExecuteReader();  
      reader.Read(); // Advance to the one and only row  
      // Return output parameters from returned data stream  
      string dbPasswordHash = reader.GetString(0);  
      string salt = reader.GetString(1);  
      reader.Close();  
      // Now take the salt and the password entered by the user  
      // and concatenate them together.  
      string passwordAndSalt = String.Concat(suppliedPassword, salt);  
      // Now hash them  
      string hashedPasswordAndSalt =  
         FormsAuthentication.HashPasswordForStoringInConfigFile(  
         passwordAndSalt,  
         "SHA1");  
      // Now verify them. Returns true if they are equal.  
      passwordMatch = hashedPasswordAndSalt.Equals(dbPasswordHash);  
   }  
   catch (Exception ex)  
   {  
       throw new Exception("Exception verifying password. " +  
          ex.Message);  
   }  
   finally  
   {  
       conn.Close();  
   }  
   return passwordMatch;  
}  
```  
  
## <a name="authentication-flow"></a><span data-ttu-id="77d4e-120">Authentifizierungsablauf</span><span class="sxs-lookup"><span data-stu-id="77d4e-120">Authentication Flow</span></span>  
 <span data-ttu-id="77d4e-121">Der Reporting Services-Webdienst verfügt über benutzerdefinierte Authentifizierungserweiterungen, um eine Formularauthentifizierung durch den Berichts-Manager und den Berichtsserver zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="77d4e-121">The Reporting Services Web service provides custom authentication extensions to enable Forms Authentication by Report Manager and the report server.</span></span>  
  
 <span data-ttu-id="77d4e-122">Mit der <xref:ReportService2010.ReportingService2010.LogonUser%2A>-Methode des Reporting Services Webdiensts werden dem Berichtsserver die Anmeldeinformationen zur Authentifizierung vorgelegt.</span><span class="sxs-lookup"><span data-stu-id="77d4e-122">The <xref:ReportService2010.ReportingService2010.LogonUser%2A> method of the Reporting Services Web service is used to submit credentials to the report server for authentication.</span></span> <span data-ttu-id="77d4e-123">Der Webdienst verwendet HTTP-Header, um für validierte Anmeldeanforderungen ein Authentifizierungsticket („Cookie“) vom Server an den Client zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="77d4e-123">The Web service uses HTTP headers to pass an authentication ticket (known as a "cookie") from the server to the client for validated logon requests.</span></span>  
  
 <span data-ttu-id="77d4e-124">In folgender Abbildung sehen Sie die Methode, wie Benutzer im Webdienst authentifiziert werden, wenn Ihre Anwendung mit einem Berichtsserver eingesetzt wird, der für die Verwendung einer benutzerdefinierten Authentifizierungserweiterung konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="77d4e-124">The following illustration depicts the method of authenticating users to the Web service when your application is deployed with a report server configured to use a custom authentication extension.</span></span>  
  
 <span data-ttu-id="77d4e-125">![Ablauf der Sicherheitsauthentifizierung von Reporting Services](../../media/rosettasecurityextensionauthenticationflow.gif "Ablauf der Sicherheitsauthentifizierung von Reporting Services")</span><span class="sxs-lookup"><span data-stu-id="77d4e-125">![Reporting Services security authentication flow](../../media/rosettasecurityextensionauthenticationflow.gif "Reporting Services security authentication flow")</span></span>  
  
 <span data-ttu-id="77d4e-126">Wie in Abbildung 2 gezeigt, sieht der Authentifizierungsprozess folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="77d4e-126">As shown in Figure 2, the authentication process is as follows:</span></span>  
  
1.  <span data-ttu-id="77d4e-127">Eine Clientanwendung ruft die Webdienstmethode <xref:ReportService2010.ReportingService2010.LogonUser%2A> auf, um einen Benutzer zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="77d4e-127">A client application calls the Web service <xref:ReportService2010.ReportingService2010.LogonUser%2A> method to authenticate a user.</span></span>  
  
2.  <span data-ttu-id="77d4e-128">Der-Webdienst ruft die- <xref:ReportService2010.ReportingService2010.LogonUser%2A> Methode Ihrer Sicherheits Erweiterung auf, insbesondere die-Klasse, die **IAuthenticationExtension**implementiert.</span><span class="sxs-lookup"><span data-stu-id="77d4e-128">The Web service makes a call to the <xref:ReportService2010.ReportingService2010.LogonUser%2A> method of your security extension, specifically, the class that implements **IAuthenticationExtension**.</span></span>  
  
3.  <span data-ttu-id="77d4e-129">Die Implementierung von <xref:ReportService2010.ReportingService2010.LogonUser%2A> überprüft den Benutzernamen und das Kennwort im Benutzerspeicher oder in der Sicherheitsinstanz.</span><span class="sxs-lookup"><span data-stu-id="77d4e-129">Your implementation of <xref:ReportService2010.ReportingService2010.LogonUser%2A> validates the user name and password in the user store or security authority.</span></span>  
  
4.  <span data-ttu-id="77d4e-130">Nach der erfolgreichen Authentifizierung erstellt der Webdienst ein Cookie und verwaltet es für die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="77d4e-130">Upon successful authentication, the Web service creates a cookie and manages it for the session.</span></span>  
  
5.  <span data-ttu-id="77d4e-131">Der Webdienst gibt das Authentifizierungsticket an die aufrufende Anwendung im HTTP-Header zurück.</span><span class="sxs-lookup"><span data-stu-id="77d4e-131">The Web service returns the authentication ticket to the calling application on the HTTP header.</span></span>  
  
 <span data-ttu-id="77d4e-132">Hat der Webdienst einen Benutzer erfolgreich über die Sicherheitserweiterung authentifiziert, generiert er ein Cookie, das für nachfolgende Anforderungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="77d4e-132">When the Web service successfully authenticates a user through the security extension, it generates a cookie that is used for subsequent requests.</span></span> <span data-ttu-id="77d4e-133">Das Cookie wird möglicherweise nicht persistent mit der benutzerdefinierten Sicherheitsinstanz gespeichert, da der Berichtsserver über keine eigene Sicherheitsinstanz verfügt.</span><span class="sxs-lookup"><span data-stu-id="77d4e-133">The cookie may not persist within the custom security authority because the report server does not own the security authority.</span></span> <span data-ttu-id="77d4e-134">Das Cookie wird von der Webdienstmethode <xref:ReportService2010.ReportingService2010.LogonUser%2A> zurückgegeben und wird in Folgeaufrufen der Webdienstmethode und beim URL-Zugriff verwendet.</span><span class="sxs-lookup"><span data-stu-id="77d4e-134">The cookie is returned from the <xref:ReportService2010.ReportingService2010.LogonUser%2A> Web service method and is used in subsequent Web service method calls and in URL access.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="77d4e-135">Um zu verhindern, dass das Cookie während der Übertragung beschädigt wird, sollten Authentifizierungscookies, die von <xref:ReportService2010.ReportingService2010.LogonUser%2A> zurückgegeben werden, über SSL-Verschlüsselung (Secure Sockets Layer) verschlüsselt werden.</span><span class="sxs-lookup"><span data-stu-id="77d4e-135">In order to avoid compromising the cookie during transmission, authentication cookies returned from <xref:ReportService2010.ReportingService2010.LogonUser%2A> should be transmitted securely using Secure Sockets Layer (SSL) encryption.</span></span>  
  
 <span data-ttu-id="77d4e-136">Wenn Sie einen Berichtsserver über URL-Zugriff aufrufen, während eine benutzerdefinierte Sicherheitserweiterung installiert ist, verwalten IIS (Internet Information Services) und [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] die Übertragung des Authentifizierungstickets automatisch.</span><span class="sxs-lookup"><span data-stu-id="77d4e-136">If you access the report server through URL access when a custom security extension is installed, Internet Information Services (IIS) and [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] automatically manage the transmission of the authentication ticket.</span></span> <span data-ttu-id="77d4e-137">Wenn Sie über die SOAP-API auf den Berichtsserver zugreifen, muss Ihre Implementierung der Proxyklasse zusätzliche Unterstützung für die Verwaltung des Authentifizierungstickets enthalten.</span><span class="sxs-lookup"><span data-stu-id="77d4e-137">If you are accessing the report server through the SOAP API, your implementation of the proxy class must include additional support for managing the authentication ticket.</span></span> <span data-ttu-id="77d4e-138">Weitere Informationen zur Verwendung der SOAP-API und zur Verwendung des Authentifizierungstickets finden Sie unter „Verwenden des Webdiensts mit benutzerdefinierter Sicherheit“.</span><span class="sxs-lookup"><span data-stu-id="77d4e-138">For more information about using the SOAP API and managing the authentication ticket, see "Using the Web Service with Custom Security."</span></span>  
  
## <a name="forms-authentication"></a><span data-ttu-id="77d4e-139">Formularauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="77d4e-139">Forms Authentication</span></span>  
 <span data-ttu-id="77d4e-140">Die Formularauthentifizierung ist eine Art der [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]-Authentifizierung, bei der ein authentifizierter Benutzer zu einem HTML-Formular geleitet wird.</span><span class="sxs-lookup"><span data-stu-id="77d4e-140">Forms Authentication is a type of [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] authentication in which an unauthenticated user is directed to an HTML form.</span></span> <span data-ttu-id="77d4e-141">Sobald der Benutzer seine Anmeldeinformationen angibt, gibt das System ein Cookie aus, das ein Authentifizierungsticket enthält.</span><span class="sxs-lookup"><span data-stu-id="77d4e-141">Once the user provides credentials, the system issues a cookie containing an authentication ticket.</span></span> <span data-ttu-id="77d4e-142">Bei späteren Anforderungen prüft das System zuerst das Cookie, um festzustellen, ob der Benutzer bereits durch den Berichtsserver authentifiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="77d4e-142">On later requests, the system first checks the cookie to see if the user was already authenticated by the report server.</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="77d4e-143">kann so erweitert werden, dass die Formularauthentifizierung unterstützt wird. Hierzu werden Sicherheitserweiterungsschnittstellen verwendet, die über die Reporting Services-API zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="77d4e-143">can be extended to support Forms Authentication using the security extensibility interfaces available through the Reporting Services API.</span></span> <span data-ttu-id="77d4e-144">Wenn Sie [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] so erweitern, dass die Formularauthentifizierung verwendet wird, verwenden Sie für die gesamte Kommunikation mit dem Berichtsserver SSL (Secure Sockets Layer), damit sich unberechtigte Benutzer keinen Zugang auf das Cookie eines anderen Benutzers verschaffen können.</span><span class="sxs-lookup"><span data-stu-id="77d4e-144">If you extend [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] to use Forms Authentication, use Secure Sockets Layer (SSL) for all communications with the report server to prevent malicious users from gaining access to another user's cookie.</span></span> <span data-ttu-id="77d4e-145">SSL ermöglicht Clients und dem Berichtsserver eine gegenseitige Authentifizierung, um sicherzustellen, dass keine anderen Computer den Inhalt der Kommunikation zwischen zwei Computern lesen können.</span><span class="sxs-lookup"><span data-stu-id="77d4e-145">SSL enables clients and a report server to authenticate each other and to ensure that no other computers can read the contents of communications between the two computers.</span></span> <span data-ttu-id="77d4e-146">Alle Daten, die über SSL-Verbindung von einem Client versendet werden, sind verschlüsselt, sodass unberechtigte Benutzer an den Berichtsserver gesandte Kennwörter und Daten nicht abfangen können.</span><span class="sxs-lookup"><span data-stu-id="77d4e-146">All data sent from a client through an SSL connection is encrypted so that malicious users cannot intercept passwords or data sent to a report server.</span></span>  
  
 <span data-ttu-id="77d4e-147">Die Formularauthentifizierung wird normalerweise implementiert, um Konten und die Authentifizierung für Nicht-Windows-Plattformen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="77d4e-147">Forms Authentication is generally implemented to support accounts and authentication for platforms other than Windows.</span></span> <span data-ttu-id="77d4e-148">Einem Benutzer, der auf einen Berichtsserver zugreifen möchte, wird eine grafische Oberfläche angezeigt, und die angegebenen Anmeldeinformationen werden zur Authentifizierung an eine Sicherheitsinstanz übergeben.</span><span class="sxs-lookup"><span data-stu-id="77d4e-148">A graphical interface is presented to a user who requests access to a report server, and the supplied credentials are submitted to a security authority for authentication.</span></span>  
  
 <span data-ttu-id="77d4e-149">Bei der Formularauthentifizierung muss eine Person anwesend sein, um die Anmeldeinformationen einzugeben.</span><span class="sxs-lookup"><span data-stu-id="77d4e-149">Forms Authentication requires that a person is present to enter credentials.</span></span> <span data-ttu-id="77d4e-150">Bei unbeaufsichtigten Anwendungen, die direkt mit dem Reporting Services-Webdienst kommunizieren, muss die Formularauthentifizierung mit einem benutzerdefinierten Authentifizierungsschema kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="77d4e-150">For unattended applications that communicate directly with the Reporting Services Web service, Forms Authentication must be combined with a custom authentication scheme.</span></span>  
  
 <span data-ttu-id="77d4e-151">Die Formularauthentifizierung ist für [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] in folgenden Fällen geeignet:</span><span class="sxs-lookup"><span data-stu-id="77d4e-151">Forms Authentication is appropriate for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] when:</span></span>  
  
-   <span data-ttu-id="77d4e-152">Sie müssen Benutzer speichern und authentifizieren, die keine [!INCLUDE[msCoName](../../../includes/msconame-md.md)]-Windows-Konten haben, und</span><span class="sxs-lookup"><span data-stu-id="77d4e-152">You need to store and authenticate users that do not have [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows accounts, and</span></span>  
  
-   <span data-ttu-id="77d4e-153">Sie müssen Ihr eigenes Benutzeroberflächenformular als Anmeldeseite zwischen den verschiedenen Seiten auf einer Website angeben.</span><span class="sxs-lookup"><span data-stu-id="77d4e-153">You need to provide your own user interface form as a logon page between different pages on a Web site.</span></span>  
  
 <span data-ttu-id="77d4e-154">Beachten Sie Folgendes, wenn Sie eine benutzerdefinierte Sicherheitserweiterung schreiben, die die Formularauthentifizierung unterstützt:</span><span class="sxs-lookup"><span data-stu-id="77d4e-154">Consider the following when writing a custom security extension that supports Forms Authentication:</span></span>  
  
-   <span data-ttu-id="77d4e-155">Wenn Sie die Formularauthentifizierung verwenden, muss der anonyme Zugriff auf dem virtuellen Verzeichnis des Berichtsservers in IIS (Internet Information Services) aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="77d4e-155">If you use Forms Authentication, anonymous access must be enabled on the report server virtual directory in Internet Information Services (IIS).</span></span>  
  
-   <span data-ttu-id="77d4e-156">Die [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]-Authentifizierung muss auf „Formular“ eingestellt sein.</span><span class="sxs-lookup"><span data-stu-id="77d4e-156">[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] authentication must be set to Forms.</span></span> <span data-ttu-id="77d4e-157">Sie konfigurieren die [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]-Authentifizierung für den Berichtsserver in der Datei Web.config.</span><span class="sxs-lookup"><span data-stu-id="77d4e-157">You configure [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] authentication in the Web.config file for the report server.</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="77d4e-158">kann Benutzer entweder über die Windows-Authentifizierung oder die benutzerdefinierte Authentifizierung authentifizieren, jedoch nicht über beide.</span><span class="sxs-lookup"><span data-stu-id="77d4e-158">can authenticate and authorize users with either Windows Authentication or custom authentication, but not both.</span></span> [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="77d4e-159">unterstützt nicht die gleichzeitige Verwendung von mehreren Sicherheitserweiterungen.</span><span class="sxs-lookup"><span data-stu-id="77d4e-159">does not support simultaneous use of multiple security extensions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77d4e-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="77d4e-160">See Also</span></span>  
 [<span data-ttu-id="77d4e-161">Implementieren von Sicherheitserweiterungen</span><span class="sxs-lookup"><span data-stu-id="77d4e-161">Implementing a Security Extension</span></span>](../security-extension/implementing-a-security-extension.md)  
  
  
