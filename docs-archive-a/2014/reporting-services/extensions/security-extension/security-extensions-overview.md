---
title: Übersicht über Sicherheitserweiterungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], extensions
ms.assetid: 24ccd795-6506-457c-93ac-6a9dd6bb9a46
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9cd6c2a1518b724a7faafecdb2926505694e9707
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618509"
---
# <a name="security-extensions-overview"></a><span data-ttu-id="a6273-102">Übersicht über Sicherheitserweiterungen</span><span class="sxs-lookup"><span data-stu-id="a6273-102">Security Extensions Overview</span></span>
  <span data-ttu-id="a6273-103">Eine [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] -Sicherheitserweiterung ermöglicht die Authentifizierung und Autorisierung von Benutzern oder Gruppen. Das heißt, verschiedene Benutzer können sich bei einem Berichtsserver anmelden und anhand ihrer Identitäten verschiedene Aufgaben oder Vorgänge ausführen.</span><span class="sxs-lookup"><span data-stu-id="a6273-103">A [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] security extension enables the authentication and authorization of users or groups; that is, it enables different users to log on to a report server and, based on their identities, perform different tasks or operations.</span></span> <span data-ttu-id="a6273-104">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] verwendet standardmäßig eine Windows-basierte Authentifizierungserweiterung, die mit Windows-Kontoprotokollen die Identitäten von Benutzern überprüft, die angeben, im System über Konten zu verfügen.</span><span class="sxs-lookup"><span data-stu-id="a6273-104">By default, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] uses a Windows-based authentication extension, which uses Windows account protocols to verify the identities of users who claim to have accounts on the system.</span></span> <span data-ttu-id="a6273-105">In [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] werden Benutzer mithilfe eines rollenbasierten Sicherheitssystems authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="a6273-105">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] uses a role-based security system to authorize users.</span></span> <span data-ttu-id="a6273-106">Das rollenbasierte Sicherheitsmodell von [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] ähnelt den rollenbasierten Sicherheitsmodellen anderer Technologien.</span><span class="sxs-lookup"><span data-stu-id="a6273-106">The [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] role-based security model is similar to the role-based security models of other technologies.</span></span>

 <span data-ttu-id="a6273-107">Da Sicherheitserweiterungen auf einer offenen und erweiterbaren API beruhen, können Sie neue Authentifizierungs- und Autorisierungserweiterungen in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] erstellen.</span><span class="sxs-lookup"><span data-stu-id="a6273-107">Because security extensions are based on an open and extensible API, you can create new authentication and authorization extensions in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="a6273-108">Im Folgenden sehen Sie ein Beispiel einer typischen Sicherheitserweiterungsimplementierung, die mit formularbasierter Authentifizierung und Autorisierung arbeitet:</span><span class="sxs-lookup"><span data-stu-id="a6273-108">The following is an example of a typical security extension implementation that uses Forms-based authentication and authorization:</span></span>

 <span data-ttu-id="a6273-109">![Reporting Services-Sicherheitserweiterungsprozess](../../media/rosettasecurityextensionflow.gif "Reporting Services-Sicherheitserweiterungsprozess")</span><span class="sxs-lookup"><span data-stu-id="a6273-109">![Reporting Services security extension process](../../media/rosettasecurityextensionflow.gif "Reporting Services security extension process")</span></span>

 <span data-ttu-id="a6273-110">Wie in der Abbildung dargestellt, treten Authentifizierung und Autorisierung folgendermaßen auf:</span><span class="sxs-lookup"><span data-stu-id="a6273-110">As shown in the illustration, authentication and authorization occur as follows:</span></span>

1.  <span data-ttu-id="a6273-111">Ein Benutzer versucht über eine URL auf den Berichts-Manager zuzugreifen und wird zu einem Formular umgeleitet, das Anmeldeinformationen von Benutzern für die Clientanwendung sammelt.</span><span class="sxs-lookup"><span data-stu-id="a6273-111">A user tries to access Report Manager by using a URL and is redirected to a form that collects user credentials for the client application.</span></span>

2.  <span data-ttu-id="a6273-112">Der Benutzer gibt die Anmeldeinformationen an das Formular.</span><span class="sxs-lookup"><span data-stu-id="a6273-112">The user submits credentials to the form.</span></span>

3.  <span data-ttu-id="a6273-113">Die Anmeldeinformationen des Benutzers werden mithilfe der <xref:ReportService2010.ReportingService2010.LogonUser%2A>-Methode an den Reporting Services-Webdienst übermittelt.</span><span class="sxs-lookup"><span data-stu-id="a6273-113">The user credentials are submitted to the Reporting Services Web service through the <xref:ReportService2010.ReportingService2010.LogonUser%2A> method.</span></span>

4.  <span data-ttu-id="a6273-114">Der Webdienst ruft die vom Benutzer angegebene Sicherheitserweiterung auf und überprüft, ob der Benutzername und das Kennwort in der benutzerdefinierten Sicherheitsinstanz vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="a6273-114">The Web service calls the customer-supplied security extension and verifies that the user name and password exist in the custom security authority.</span></span>

5.  <span data-ttu-id="a6273-115">Nach der Authentifizierung erstellt der Webdienst für die Startseite des Berichts-Managers ein Authentifizierungsticket (auch "Cookie" genannt), verwaltet das Ticket und überprüft die Rolle des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="a6273-115">After authentication, the Web service creates an authentication ticket (known as a "cookie"), manages the ticket, and verifies the user's role for the Home page of Report Manager.</span></span>

6.  <span data-ttu-id="a6273-116">Der Webdienst gibt das Cookie an den Browser zurück und zeigt die entsprechende Benutzeroberfläche im Berichts-Manager an.</span><span class="sxs-lookup"><span data-stu-id="a6273-116">The Web service returns the cookie to the browser and displays the appropriate user interface in Report Manager.</span></span>

7.  <span data-ttu-id="a6273-117">Nachdem der Benutzer authentifiziert wurde, sendet der Browser Anforderungen an den Berichts-Manager, während das Cookie im HTTP-Header übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="a6273-117">After the user is authenticated, the browser makes requests to Report Manager while transmitting the cookie in the HTTP header.</span></span> <span data-ttu-id="a6273-118">Diese Anforderungen sind Reaktionen auf Benutzeraktionen im Berichts-Manager.</span><span class="sxs-lookup"><span data-stu-id="a6273-118">These requests are in response to user actions within the Report Manager application.</span></span>

8.  <span data-ttu-id="a6273-119">Das Cookie wird zusammen mit der angeforderten Benutzeroperation im HTTP-Header an den Webdienst übertragen.</span><span class="sxs-lookup"><span data-stu-id="a6273-119">The cookie is transmitted in the HTTP header to the Web service along with the requested user operation.</span></span>

9. <span data-ttu-id="a6273-120">Das Cookie wird überprüft. Wenn es gültig ist, gibt der Berichtsserver die Sicherheitsbeschreibung und andere im Zusammenhang mit der angeforderten Operation stehende Informationen aus der Berichtsserver-Datenbank zurück.</span><span class="sxs-lookup"><span data-stu-id="a6273-120">The cookie is validated, and if it is valid, the report server returns the security descriptor and other information relating to the requested operation from the report server database.</span></span>

10. <span data-ttu-id="a6273-121">Wenn das Cookie gültig ist, ruft der Berichtsserver die Sicherheitserweiterung auf und überprüft, ob der Benutzer zur Ausführung der bestimmten Operation autorisiert ist.</span><span class="sxs-lookup"><span data-stu-id="a6273-121">If the cookie is valid, the report server makes a call to the security extension to check if the user is authorized to perform the specific operation.</span></span>

11. <span data-ttu-id="a6273-122">Wenn der Benutzer autorisiert ist, führt der Berichtsserver die angeforderte Operation aus und gibt die Steuerung an den Aufrufer zurück.</span><span class="sxs-lookup"><span data-stu-id="a6273-122">If the user is authorized, the report server performs the requested operation and returns control to the caller.</span></span>

12. <span data-ttu-id="a6273-123">Nach der Authentifizierung des Benutzers verwendet der URL-Zugriff des Berichtsservers dasselbe Cookie.</span><span class="sxs-lookup"><span data-stu-id="a6273-123">After the user is authenticated, URL access to the report server uses the same cookie.</span></span> <span data-ttu-id="a6273-124">Das Cookie wird im HTTP-Header übertragen.</span><span class="sxs-lookup"><span data-stu-id="a6273-124">The cookie is transmitted in the HTTP header.</span></span>

13. <span data-ttu-id="a6273-125">Der Benutzer fordert so lange Operationen auf dem Berichtsserver an, bis die Sitzung beendet ist.</span><span class="sxs-lookup"><span data-stu-id="a6273-125">The user continues to request operations on the report server until the session has ended.</span></span>

## <a name="when-to-implement-a-security-extension"></a><span data-ttu-id="a6273-126">Sinnvolles Implementieren von Sicherheitserweiterungen</span><span class="sxs-lookup"><span data-stu-id="a6273-126">When to Implement a Security Extension</span></span>
 <span data-ttu-id="a6273-127">Es wird empfohlen, immer die Windows-Authentifizierung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a6273-127">We recommend that you use Windows Authentication if at all possible.</span></span> <span data-ttu-id="a6273-128">In den folgenden Fällen ist jedoch möglicherweise eine benutzerdefinierte Authentifizierung und Autorisierung für [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] angemessener:</span><span class="sxs-lookup"><span data-stu-id="a6273-128">However, custom authentication and authorization for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] may be appropriate in the following two cases:</span></span>

-   <span data-ttu-id="a6273-129">Sie haben eine Internet- oder Extranetanwendung, die keine Windows-Konten nutzen kann.</span><span class="sxs-lookup"><span data-stu-id="a6273-129">You have an Internet or extranet application that cannot use Windows accounts.</span></span>

-   <span data-ttu-id="a6273-130">Sie haben benutzerdefinierte Benutzer und Rollen, die ein übereinstimmendes Autorisierungsschema in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]bereitstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="a6273-130">You have custom-defined users and roles and need to provide a matching authorization scheme in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="a6273-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a6273-131">See Also</span></span>
 <span data-ttu-id="a6273-132">[Implementieren einer Sicherheits Erweiterung](../security-extension/implementing-a-security-extension.md) [Konfigurieren Berichts-Manager für die Übergabe von benutzerdefinierten Authentifizierungs Cookies](../../security/configure-the-web-portal-to-pass-custom-authentication-cookies.md)</span><span class="sxs-lookup"><span data-stu-id="a6273-132">[Implementing a Security Extension](../security-extension/implementing-a-security-extension.md) [Configure Report Manager to Pass Custom Authentication Cookies](../../security/configure-the-web-portal-to-pass-custom-authentication-cookies.md)</span></span>


