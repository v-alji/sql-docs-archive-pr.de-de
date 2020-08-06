---
title: Registrieren eines Dienstprinzipalnamens (SPN) für einen Berichtsserver | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: dda91d4f-77cc-4898-ad03-810ece5f8e74
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 502170f16aad66757e8f44419ccbac3017072449
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622431"
---
# <a name="register-a-service-principal-name-spn-for-a-report-server"></a><span data-ttu-id="9bafb-102">Registrieren eines Dienstprinzipalnamens (SPN) für einen Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="9bafb-102">Register a Service Principal Name (SPN) for a Report Server</span></span>
  <span data-ttu-id="9bafb-103">Wenn Sie [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in einem Netzwerk bereitstellen, in dem das Kerberos-Protokoll zur gegenseitigen Authentifizierung verwendet wird, müssen Sie einen Dienstprinzipalnamen (SPN) für den Berichtsserverdienst erstellen, wenn Sie diesen als Domänenbenutzerkonto konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9bafb-103">If you are deploying [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in a network that uses the Kerberos protocol for mutual authentication, you must create a Service Principal Name (SPN) for the Report Server service if you configure it to run as a domain user account.</span></span>  
  
## <a name="about-spns"></a><span data-ttu-id="9bafb-104">Informationen zu SPNs</span><span class="sxs-lookup"><span data-stu-id="9bafb-104">About SPNs</span></span>  
 <span data-ttu-id="9bafb-105">Ein SPN ist ein eindeutiger Bezeichner für einen Dienst in einem Netzwerk mit Kerberos-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9bafb-105">An SPN is a unique identifier for a service on a network that uses Kerberos authentication.</span></span> <span data-ttu-id="9bafb-106">SPNs bestehen aus einer Dienstklasse, einem Hostnamen und einem Port.</span><span class="sxs-lookup"><span data-stu-id="9bafb-106">It consists of a service class, a host name, and a port.</span></span> <span data-ttu-id="9bafb-107">In einem Netzwerk mit Kerberos-Authentifizierung muss ein SPN für den Server unter einem integrierten Computerkonto wie NetworkService oder LocalSystem oder unter einem Benutzerkonto registriert sein.</span><span class="sxs-lookup"><span data-stu-id="9bafb-107">On a network that uses Kerberos authentication, an SPN for the server must be registered under either a built-in computer account (such as NetworkService or LocalSystem) or user account.</span></span> <span data-ttu-id="9bafb-108">SPNs werden automatisch für integrierte Konten registriert.</span><span class="sxs-lookup"><span data-stu-id="9bafb-108">SPNs are registered for built-in accounts automatically.</span></span> <span data-ttu-id="9bafb-109">Wenn Sie einen Dienst unter einem Domänenbenutzerkonto ausführen, müssen Sie den SPN manuell für das Konto registrieren, das Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="9bafb-109">However, when you run a service under a domain user account, you must manually register the SPN for the account you want to use.</span></span>  
  
 <span data-ttu-id="9bafb-110">Um einen SPN zu erstellen, können Sie das Befehlszeilen-Hilfsprogramm **SetSPN** verwenden.</span><span class="sxs-lookup"><span data-stu-id="9bafb-110">To create an SPN, you can use the **SetSPN** command line utility.</span></span> <span data-ttu-id="9bafb-111">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="9bafb-111">For more information, see the following:</span></span>  
  
-   <span data-ttu-id="9bafb-112">[Setspn](https://technet.microsoft.com/library/cc731241\(WS.10\).aspx) ( https://technet.microsoft.com/library/cc731241(WS.10).aspx) .</span><span class="sxs-lookup"><span data-stu-id="9bafb-112">[Setspn](https://technet.microsoft.com/library/cc731241\(WS.10\).aspx) (https://technet.microsoft.com/library/cc731241(WS.10).aspx).</span></span>  
  
-   <span data-ttu-id="9bafb-113">[Setspn-Syntax für Dienst Prinzipal Namen (SPNs) (Setspn.exe)](https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx) ( https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx) .</span><span class="sxs-lookup"><span data-stu-id="9bafb-113">[Service Principal Names (SPNs) SetSPN Syntax (Setspn.exe)](https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx) (https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx).</span></span>  
  
 <span data-ttu-id="9bafb-114">Sie müssen Domänenadministrator sein, um das Hilfsprogramm auf dem Domänencontroller auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9bafb-114">You must be a domain administrator to run the utility on the domain controller.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bafb-115">Syntax</span><span class="sxs-lookup"><span data-stu-id="9bafb-115">Syntax</span></span>  
 <span data-ttu-id="9bafb-116">Die Befehlssyntax für die Verwendung des Hilfsprogramms SetSPN zum Erstellen eines SPN für den Berichtsserver kann z. B. wie folgt lauten:</span><span class="sxs-lookup"><span data-stu-id="9bafb-116">The command syntax for using SetSPN utility to create an SPN for the report server resembles the following:</span></span>  
  
```  
Setspn -s http/<computername>.<domainname>:<port> <domain-user-account>  
```  
  
 <span data-ttu-id="9bafb-117">**SetSPN** ist in Windows Server verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9bafb-117">**SetSPN** is available with Windows Server.</span></span> <span data-ttu-id="9bafb-118">Mit dem `-s`-Argument wird ein SPN hinzugefügt, nachdem überprüft wurde, dass kein doppelter Name vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="9bafb-118">The `-s` argument adds a SPN after validating no duplicate exists.</span></span> <span data-ttu-id="9bafb-119">**HINWEIS:** „-s“ ist in Windows Server ab Windows Server 2008 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9bafb-119">**NOTE:-s** is available in Windows Server starting with Windows Server 2008.</span></span>  
  
 <span data-ttu-id="9bafb-120">`HTTP` ist die Dienstklasse.</span><span class="sxs-lookup"><span data-stu-id="9bafb-120">`HTTP` is the service class.</span></span> <span data-ttu-id="9bafb-121">Der Report Server-Webdienst wird in HTTP.SYS ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9bafb-121">The Report Server Web service runs in HTTP.SYS.</span></span> <span data-ttu-id="9bafb-122">Wenn Sie einen SPN für HTTP erstellen, werden allen Webanwendungen auf dem gleichen Computer, die in HTTP.SYS ausgeführt werden (einschließlich der Anwendungen, die in IIS gehostet werden), Tickets auf der Basis des Domänenbenutzerkontos zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="9bafb-122">A by-product of creating an SPN for HTTP is that all Web applications on the same computer that run in HTTP.SYS (including applications hosted in IIS) will be granted tickets based on the domain user account.</span></span> <span data-ttu-id="9bafb-123">Wenn diese Dienste unter einem anderen Konto ausgeführt werden, können Authentifizierungsanforderungen nicht ordnungsgemäß verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="9bafb-123">If those services run under a different account, the authentication requests will fail.</span></span> <span data-ttu-id="9bafb-124">Konfigurieren Sie deshalb alle HTTP-Anwendungen zur Ausführung unter dem gleichen Konto, oder erstellen Sie Hostheader für jede Anwendung und anschließend je einen SPN pro Hostheader.</span><span class="sxs-lookup"><span data-stu-id="9bafb-124">To avoid this problem, be sure to configure all HTTP applications to run under the same account, or consider creating host headers for each application and then creating separate SPNs for each host header.</span></span> <span data-ttu-id="9bafb-125">Wenn Sie Hostheader konfigurieren, sind DNS-Änderungen unabhängig von der [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Konfiguration erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9bafb-125">When you configure host headers, DNS changes are required regardless of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] configuration.</span></span>  
  
 <span data-ttu-id="9bafb-126">Die Werte, die Sie für \<*computername*> , \<*domainname*> und angeben, \<*port*> identifizieren die eindeutige Netzwerkadresse des Computers, der den Berichts Server hostet.</span><span class="sxs-lookup"><span data-stu-id="9bafb-126">The values that you specify for \<*computername*>, \<*domainname*>, and \<*port*> identify the unique network address of the computer that hosts the report server.</span></span> <span data-ttu-id="9bafb-127">Dies kann ein lokaler Hostname oder ein vollqualifizierter Domänenname (FQDN) sein.</span><span class="sxs-lookup"><span data-stu-id="9bafb-127">This can be a local host name or a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="9bafb-128">Wenn Sie nur über eine Domäne verfügen und Port 80 verwenden, können Sie und in \<*domainname*> \<*port*> der Befehlszeile weglassen.</span><span class="sxs-lookup"><span data-stu-id="9bafb-128">If you only have one domain and are using port 80, you can omit \<*domainname*> and \<*port*> from your command line.</span></span> <span data-ttu-id="9bafb-129">\<*domain-user-account*>das Benutzerkonto, unter dem der Berichts Server Dienst ausgeführt wird und für das der SPN registriert werden muss.</span><span class="sxs-lookup"><span data-stu-id="9bafb-129">\<*domain-user-account*> is the user account under which the Report Server service runs and for which the SPN must be registered.</span></span>  
  
## <a name="register-an-spn-for-domain-user-account"></a><span data-ttu-id="9bafb-130">Registrieren eines SPNs für ein Domänenbenutzerkonto</span><span class="sxs-lookup"><span data-stu-id="9bafb-130">Register an SPN for Domain User Account</span></span>  
  
#### <a name="to-register-an-spn-for-a-report-server-service-running-as-a-domain-user"></a><span data-ttu-id="9bafb-131">So registrieren Sie einen SPN für einen Berichtsserverdienst, der als Domänenbenutzer ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="9bafb-131">To register an SPN for a Report Server service running as a domain user</span></span>  
  
1.  <span data-ttu-id="9bafb-132">Installieren Sie [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , und konfigurieren Sie den Berichtsserverdienst zur Ausführung als Domänenbenutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="9bafb-132">Install [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and configure the Report Server service to run as a domain user account.</span></span> <span data-ttu-id="9bafb-133">Erst wenn Sie die folgenden Schritte ausgeführt haben, können Benutzer eine Verbindung mit dem Berichtsserver herstellen.</span><span class="sxs-lookup"><span data-stu-id="9bafb-133">Note that users will not be able to connect to the report server until you complete the following steps.</span></span>  
  
2.  <span data-ttu-id="9bafb-134">Melden Sie sich als Domänenadministrator beim Domänencontroller an.</span><span class="sxs-lookup"><span data-stu-id="9bafb-134">Log on to the domain controller as domain administrator.</span></span>  
  
3.  <span data-ttu-id="9bafb-135">Öffnen Sie ein Eingabeaufforderungsfenster.</span><span class="sxs-lookup"><span data-stu-id="9bafb-135">Open a Command Prompt window.</span></span>  
  
4.  <span data-ttu-id="9bafb-136">Kopieren Sie den folgenden Befehl, um Platzhalterwerte durch gültige Werte für das Netzwerk zu ersetzen:</span><span class="sxs-lookup"><span data-stu-id="9bafb-136">Copy the following command, replacing placeholder values with actual values that are valid for your network:</span></span>  
  
    ```  
    Setspn -s http/<computer-name>.<domain-name>:<port> <domain-user-account>  
    ```  
  
     <span data-ttu-id="9bafb-137">Beispiel: `Setspn -s http/MyReportServer.MyDomain.com:80 MyDomainUser`</span><span class="sxs-lookup"><span data-stu-id="9bafb-137">For example: `Setspn -s http/MyReportServer.MyDomain.com:80 MyDomainUser`</span></span>  
  
5.  <span data-ttu-id="9bafb-138">Führen Sie den Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="9bafb-138">Run the command.</span></span>  
  
6.  <span data-ttu-id="9bafb-139">Öffnen Sie die Datei **RsReportServer.config** , und suchen Sie den Abschnitt `<AuthenticationTypes>` .</span><span class="sxs-lookup"><span data-stu-id="9bafb-139">Open the **RsReportServer.config** file and locate the `<AuthenticationTypes>` section.</span></span>  
  
7.  <span data-ttu-id="9bafb-140">Fügen Sie `<RSWindowsNegotiate/>` als ersten Eintrag in diesem Abschnitt hinzu, um NTLM zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9bafb-140">Add `<RSWindowsNegotiate/>` as the first entry in this section to enable NTLM.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bafb-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9bafb-141">See Also</span></span>  
 <span data-ttu-id="9bafb-142">[Konfigurieren eines Dienst Kontos &#40;SSRS-Configuration Manager&#41;](../../sql-server/install/configure-a-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="9bafb-142">[Configure a Service Account &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-service-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="9bafb-143">[Konfigurieren des Berichtsserver-Dienstkontos &#40;SSRS-Konfigurations-Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="9bafb-143">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 [<span data-ttu-id="9bafb-144">Manage a Reporting Services Native Mode Report Server (Verwalten eines Berichtsservers von Reporting Services im einheitlichen Modus)</span><span class="sxs-lookup"><span data-stu-id="9bafb-144">Manage a Reporting Services Native Mode Report Server</span></span>](manage-a-reporting-services-native-mode-report-server.md)  
  
  
