---
title: Autorisierung in Reporting Services | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- authorization [Reporting Services]
ms.assetid: 15fc1c7b-560c-4737-b126-e0d428a1b530
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7420b45175ca0b0a5fc66da4a7939b07b79c75b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618516"
---
# <a name="authorization-in-reporting-services"></a><span data-ttu-id="8a743-102">Autorisierung in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="8a743-102">Authorization in Reporting Services</span></span>
  <span data-ttu-id="8a743-103">Unter Autorisierung versteht man den Prozess der Beurteilung, ob einer Identität die angeforderte Zugriffsart auf eine bestimmte Ressource in der Berichtsserver-Datenbank erteilt wird.</span><span class="sxs-lookup"><span data-stu-id="8a743-103">Authorization is the process of determining whether an identity should be granted the requested type of access to a given resource in the report server database.</span></span> [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="8a743-104">verwendet eine Autorisierungarchitektur auf Rollenbasis, bei der ein Benutzer Zugriff auf eine bestimmte Rolle ausgehend von der Rollenzuweisung für die Anwendung erhält.</span><span class="sxs-lookup"><span data-stu-id="8a743-104">uses a role-based authorization architecture that grants a user access to a given resource based on the user's role assignment for the application.</span></span> <span data-ttu-id="8a743-105">Sicherheitserweiterungen für [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] enthalten eine Implementierung einer Autorisierungskomponente, über die ein Benutzer Zugriff erhält, sobald er sich auf dem Berichtsserver authentifiziert hat.</span><span class="sxs-lookup"><span data-stu-id="8a743-105">Security extensions for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] contain an implementation of an authorization component that is used to grant access to users once they are authenticated on the report server.</span></span> <span data-ttu-id="8a743-106">Die Autorisierung wird gestartet, wenn ein Benutzer versucht, einen Vorgang im System oder auf einem Berichtsserverelement über die SOAP-API und den URL-Zugriff auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8a743-106">Authorization is invoked when a user attempts to perform an operation on the system or a report server item through the SOAP API and via URL access.</span></span> <span data-ttu-id="8a743-107">Dies wird durch die Sicherheitserweiterungsschnittstelle **IAuthorizationExtension**ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="8a743-107">This is made possible through the security extension interface **IAuthorizationExtension**.</span></span> <span data-ttu-id="8a743-108">Wie vorher angegeben, erben alle Erweiterungen von **IExtension** die Basisschnittstelle für jede Erweiterung, die Sie bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8a743-108">As stated previously, all extensions inherit from **IExtension** the base interface for any extension that you deploy.</span></span> <span data-ttu-id="8a743-109">**IExtension** und **IAuthorizationExtension** sind Elemente des **Microsoft.ReportingServices.Interfaces** -Namespace.</span><span class="sxs-lookup"><span data-stu-id="8a743-109">**IExtension** and **IAuthorizationExtension** are members of the **Microsoft.ReportingServices.Interfaces** namespace.</span></span>

## <a name="checking-access"></a><span data-ttu-id="8a743-110">Zugriffsprüfung</span><span class="sxs-lookup"><span data-stu-id="8a743-110">Checking Access</span></span>
 <span data-ttu-id="8a743-111">Bei der Autorisierung ist der Schlüssel für jede benutzerdefinierte Implementierung der Sicherheit die in der <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A>-Methode implementierte Zugriffsüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="8a743-111">In authorization, the key to any custom security implementation is the access check, which is implemented in the <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> method.</span></span> <span data-ttu-id="8a743-112"><xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> wird immer aufgerufen, wenn ein Benutzer versucht, auf dem Berichtsserver einen Vorgang auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8a743-112"><xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> is called each time a user attempts an operation on the report server.</span></span> <span data-ttu-id="8a743-113">Die Methode <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> wird für jeden Vorgangstyp überladen.</span><span class="sxs-lookup"><span data-stu-id="8a743-113">The <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> method is overloaded for each operation type.</span></span> <span data-ttu-id="8a743-114">Für Ordnervorgänge könnte ein Beispiel für eine Zugriffsprüfung folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="8a743-114">For folder operations, an example of an access check might look like the following:</span></span>

```
// Overload for Folder operations
public bool CheckAccess(
   string userName, 
   IntPtr userToken, 
   byte[] secDesc, 
   FolderOperation requiredOperation)
{
   // If the user is the administrator, allow unrestricted access.
   if (userName == m_adminUserName) 
      return true;

   AceCollection acl = DeserializeAcl(secDesc);
   foreach(AceStruct ace in acl)
   {
         if (userName == ace.PrincipalName)
         {
            foreach(FolderOperation aclOperation in 
               ace.FolderOperations)
            {
               if (aclOperation == requiredOperation)
                     return true;
            }
         }
   }
   return false;
}
```

 <span data-ttu-id="8a743-115">Der Berichtsserver ruft die Methode <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> auf, indem der Name des angemeldeten Benutzers, ein Benutzertoken, die Sicherheitsbeschreibung für das Element und der angeforderte Vorgang übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="8a743-115">The report server calls the <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> method by passing in the name of the logged-on user, a user token, the security descriptor for the item, and the requested operation.</span></span> <span data-ttu-id="8a743-116">Hier würden Sie die Sicherheitsbeschreibung auf den Benutzernamen und die entsprechende Berechtigung zur Durchführung der Anforderung überprüfen, dann würden Sie mit `true` anzeigen, dass der Zugriff erteilt wird, oder mit `false`, dass der Zugriff verweigert wird.</span><span class="sxs-lookup"><span data-stu-id="8a743-116">Here you would check the security descriptor for the user name and the appropriate permission to complete the request, then return `true` to signify that access is granted or `false` to signify access is denied.</span></span>

## <a name="security-descriptors"></a><span data-ttu-id="8a743-117">Sicherheitsbeschreibungen</span><span class="sxs-lookup"><span data-stu-id="8a743-117">Security Descriptors</span></span>
 <span data-ttu-id="8a743-118">Wenn Sie Autorisierungsrichtlinien für Elemente in der Berichtsserver-Datenbank festlegen, gibt eine Clientanwendung (z. B. der Berichts-Manager) die Benutzerinformationen an die Sicherheitserweiterung weiter, zusammen mit einer Sicherheitsrichtlinie für das Element.</span><span class="sxs-lookup"><span data-stu-id="8a743-118">When setting authorization policies on items in the report server database, a client application (such as Report Manager) submits the user information to the security extension along with a security policy for the item.</span></span> <span data-ttu-id="8a743-119">Die Sicherheitsrichtlinie und die Benutzerinformationen werden zusammen als Sicherheitsbeschreibung bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="8a743-119">This security policy and user information are known collectively as a security descriptor.</span></span> <span data-ttu-id="8a743-120">Eine Sicherheitsbeschreibung enthält die folgenden Informationen für ein Element in der Berichtsserver-Datenbank:</span><span class="sxs-lookup"><span data-stu-id="8a743-120">A security descriptor contains the following information for an item in the report server database:</span></span>

-   <span data-ttu-id="8a743-121">Gruppe oder Benutzer, der eine bestimmte Berechtigung hat, Vorgänge in dem Element auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8a743-121">The group or user that has some type of permission to perform operations on the item.</span></span>

-   <span data-ttu-id="8a743-122">Elementtyp.</span><span class="sxs-lookup"><span data-stu-id="8a743-122">The item's type.</span></span>

-   <span data-ttu-id="8a743-123">Eine freigegebene Zugriffssteuerungsliste, die den Zugriff auf das Element kontrolliert.</span><span class="sxs-lookup"><span data-stu-id="8a743-123">A discretionary access control list controlling access to the item.</span></span>

 <span data-ttu-id="8a743-124">Sicherheitsbeschreibungen werden mit den Webdienstmethoden <xref:ReportService2010.ReportingService2010.SetPolicies%2A> und <xref:ReportService2010.ReportingService2010.SetSystemPolicies%2A> erstellt.</span><span class="sxs-lookup"><span data-stu-id="8a743-124">Security descriptors are created using the Web service <xref:ReportService2010.ReportingService2010.SetPolicies%2A> and <xref:ReportService2010.ReportingService2010.SetSystemPolicies%2A> methods.</span></span>

### <a name="authorization-flow"></a><span data-ttu-id="8a743-125">Autorisierungsablauf</span><span class="sxs-lookup"><span data-stu-id="8a743-125">Authorization Flow</span></span>
 <span data-ttu-id="8a743-126">Die [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Autorisierung wird von der Sicherheitserweiterung gesteuert, die derzeit für die Ausführung auf dem Server konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="8a743-126">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] authorization is controlled by the security extension currently configured to run on the server.</span></span> <span data-ttu-id="8a743-127">Die Autorisierung ist rollenbasiert und auf die Berechtigungen und Vorgänge beschränkt, die von der [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Sicherheitsarchitektur bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8a743-127">Authorization is role-based and limited to the permissions and operations supplied by the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] security architecture.</span></span> <span data-ttu-id="8a743-128">Das folgende Diagramm veranschaulicht den Prozess der Autorisierung von Benutzern für die Bearbeitung von Elementen in der Berichtsserver-Datenbank:</span><span class="sxs-lookup"><span data-stu-id="8a743-128">The following diagram depicts the process of authorizing users to operate on items in the report server database:</span></span>

 <span data-ttu-id="8a743-129">![Ablauf der Sicherheitsautorisierung von Reporting Services](../../media/rosettasecurityextensionauthorizationflow.gif "Ablauf der Sicherheitsautorisierung von Reporting Services")</span><span class="sxs-lookup"><span data-stu-id="8a743-129">![Reporting Services security authorization flow](../../media/rosettasecurityextensionauthorizationflow.gif "Reporting Services security authorization flow")</span></span>

 <span data-ttu-id="8a743-130">Wie in diesem Diagramm angezeigt, befolgt die Autorisierung diese Reihenfolge:</span><span class="sxs-lookup"><span data-stu-id="8a743-130">As shown in this diagram, authorization follows this sequence:</span></span>

1.  <span data-ttu-id="8a743-131">Sobald die Clientanwendungen authentifiziert sind, stellen sie über die Webdienstmethoden der Reporting Services Anforderungen an den Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="8a743-131">Once authenticated, client applications make requests to the report server through the Reporting Services Web service methods.</span></span> <span data-ttu-id="8a743-132">Ein Authentifizierungsticket wird in Form eines Cookies im HTTP-Header jeder Webanforderung weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="8a743-132">An authentication ticket is passed to the report server in the form of a cookie in the HTTP header of each Web request.</span></span>

2.  <span data-ttu-id="8a743-133">Das Cookie wird vor jeder Zugriffsprüfung überprüft.</span><span class="sxs-lookup"><span data-stu-id="8a743-133">The cookie is validated prior to any access check.</span></span>

3.  <span data-ttu-id="8a743-134">Sobald das Cookie überprüft wird, ruft der Berichtsserver <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension.GetUserInfo%2A> auf, und dem Benutzer wird eine Identität gegeben.</span><span class="sxs-lookup"><span data-stu-id="8a743-134">Once the cookie is validated, the report server calls <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension.GetUserInfo%2A> and the user is given an identity.</span></span>

4.  <span data-ttu-id="8a743-135">Der Benutzer versucht, einen Vorgang über den Reporting Services-Webdienst auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8a743-135">The user attempts an operation through the Reporting Services Web service.</span></span>

5.  <span data-ttu-id="8a743-136">Der Berichtsserver ruft die Methode <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> auf.</span><span class="sxs-lookup"><span data-stu-id="8a743-136">The report server calls the <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> method.</span></span>

6.  <span data-ttu-id="8a743-137">Die Sicherheitsbeschreibung wird abgerufen und an eine benutzerdefinierte Sicherheitserweiterungsimplementierung von <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> übergeben.</span><span class="sxs-lookup"><span data-stu-id="8a743-137">The security descriptor is retrieved and passed to a custom security extension implementation of <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A>.</span></span> <span data-ttu-id="8a743-138">Zu diesem Zeitpunkt wird der Benutzer, die Gruppe oder der Computer mit der Sicherheitsbeschreibung des Elements verglichen, auf das gerade ein Zugriff erfolgt. Danach erfolgt die Autorisierung zur Durchführung des angeforderten Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="8a743-138">At this point, the user, group, or computer is compared to the security descriptor of the item being accessed and is authorized to perform the requested operation.</span></span>

7.  <span data-ttu-id="8a743-139">Wenn der Benutzer autorisiert ist, führt der Webdienst den Vorgang durch und gibt eine Antwort an die aufrufende Anwendung zurück.</span><span class="sxs-lookup"><span data-stu-id="8a743-139">If the user is authorized, the Web service performs the operation and returns a response to the calling application.</span></span>


