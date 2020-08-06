---
title: Konfigurieren von E-Mail für eine Reporting Services-Dienst Anwendung (SharePoint 2010 und SharePoint 2013) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 38fc34a6-aae7-4dde-9ad2-f1eee0c42a9f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 628122289f8a9d83a307d70a369ab51f8f571c04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619631"
---
# <a name="configure-e-mail-for-a-reporting-services-service-application-sharepoint-2010-and-sharepoint-2013"></a><span data-ttu-id="df3c1-102">Konfigurieren von E-Mail für eine Reporting Services-Dienstanwendung (SharePoint 2010 und SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="df3c1-102">Configure E-mail for a Reporting Services Service Application (SharePoint 2010 and SharePoint 2013)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="df3c1-103">Datenwarnung sendet Warnungen in E-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="df3c1-103">data alerting sends alerts in e-mail messages.</span></span> <span data-ttu-id="df3c1-104">Um E-Mails übermitteln zu können, kann es notwendig sein, dass Sie Ihre [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Dienstanwendung konfigurieren und die E-Mail-Übermittlungserweiterung für die Dienstanwendung ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="df3c1-104">To send e-mail you may need to configure your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application and you may need to modify the e-mail delivery extension for the service application.</span></span> <span data-ttu-id="df3c1-105">Die E-Mail-Einstellungen sind ebenfalls notwendig, wenn Sie beabsichtigen, die E-Mail-Übermittlungserweiterung für die [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Abonnementfunktion zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="df3c1-105">The e-mail settings are also required if you plan to use the e-mail delivery extension for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] subscription feature.</span></span>  
  
||  
|-|  
|[!INCLUDE[applies](../../includes/applies-md.md)]<span data-ttu-id="df3c1-106">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]SharePoint-Modus &#124; SharePoint 2010 und SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="df3c1-106">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode &#124; SharePoint 2010 and SharePoint 2013.</span></span>|  
  
### <a name="to-configure-e-mail-for-the-shared-service"></a><span data-ttu-id="df3c1-107">So konfigurieren Sie E-Mail-Einstellungen für den freigegebenen Service</span><span class="sxs-lookup"><span data-stu-id="df3c1-107">To configure e-mail for the shared service</span></span>  
  
1.  <span data-ttu-id="df3c1-108">Klicken Sie in der SharePoint-Zentraladministration auf **Anwendungsverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="df3c1-108">In SharePoint Central Administration, click the **Application Management**.</span></span>  
  
2.  <span data-ttu-id="df3c1-109">Klicken Sie in der Gruppe **Dienstanwendungen** auf **Dienstanwendungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="df3c1-109">In the **Service Applications** group, click **Manage service applications**.</span></span>  
  
3.  <span data-ttu-id="df3c1-110">Klicken Sie in der Liste **Name** auf den Namen Ihrer [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Dienstanwendung.</span><span class="sxs-lookup"><span data-stu-id="df3c1-110">In the **Name** list, click the name of your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span>  
  
4.  <span data-ttu-id="df3c1-111">Klicken Sie auf der Seite **Reporting Services-Anwendung verwalten** auf **E-Mail-Einstellungen** .</span><span class="sxs-lookup"><span data-stu-id="df3c1-111">Click **E-mail Settings** on the **Manage Reporting Services Application** page.</span></span>  
  
5.  <span data-ttu-id="df3c1-112">Wählen Sie **SMTP-Server verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="df3c1-112">Select **Use SMTP server**.</span></span>  
  
6.  <span data-ttu-id="df3c1-113">Geben Sie im Feld **SMTP-Server für ausgehende Nachrichten** den Namen eines SMTP-Servers ein.</span><span class="sxs-lookup"><span data-stu-id="df3c1-113">In the **Outbound SMTP server** box, type the name of an SMTP server.</span></span>  
  
7.  <span data-ttu-id="df3c1-114">Geben Sie im Feld **Absenderadresse** eine E-Mail-Adresse ein.</span><span class="sxs-lookup"><span data-stu-id="df3c1-114">In the **From address** box, type an e-mail address.</span></span>  
  
     <span data-ttu-id="df3c1-115">Diese Adresse wird als Absender für alle Warnungs-E-Mail-Nachrichten verwendet.</span><span class="sxs-lookup"><span data-stu-id="df3c1-115">This address is the sender of all alert e-mail messages.</span></span>  
  
     <span data-ttu-id="df3c1-116">Das Konto des in **Absenderadresse** angegebenen Benutzers muss ein verwaltetes Konto sein, das Sie bei der Konfiguration des Anwendungspools für die [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Dienstanwendung angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="df3c1-116">The account of the user specified in **From address** must be a managed account that you specified when you configured the application pool for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="df3c1-117">Wenn Sie die entsprechenden Rechte besitzen, können Sie eine Liste aller vorhandenen verwalteten Konten auf der Seite Dienstkonten in der SharePoint-Zentraladministration anzeigen.</span><span class="sxs-lookup"><span data-stu-id="df3c1-117">If you have permission, you can view a list of existing managed accounts on the Service Accounts page in SharePoint Central Administration.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="ntlm-authentication"></a><span data-ttu-id="df3c1-118">NTLM-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="df3c1-118">NTLM Authentication</span></span>  
  
1.  <span data-ttu-id="df3c1-119">Wenn Ihre E-Mail-Umgebung NTLM-Authentifizierung erfordert und keinen anonymen Zugriff zulässt, müssen Sie die Konfiguration der E-Mail-Übermittlungserweiterung für die [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Dienstanwendungen ändern.</span><span class="sxs-lookup"><span data-stu-id="df3c1-119">If your email environment requires NTLM authentication and does not allow anonymous access, you need to modify the e-mail delivery extension configuration for your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service applications.</span></span> <span data-ttu-id="df3c1-120">Ändern Sie **SMTPAuthenticate** so, dass der Wert "2" verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="df3c1-120">Change the **SMTPAuthenticate** to use a value of "2".</span></span> <span data-ttu-id="df3c1-121">Dieser Wert kann nicht über die Benutzeroberfläche geändert werden.</span><span class="sxs-lookup"><span data-stu-id="df3c1-121">This value cannot be changed from the user interface.</span></span> <span data-ttu-id="df3c1-122">Das folgende beispielhafte PowerShell-Skript aktualisiert die vollständige Konfiguration für die Berichtsserver-E-Mail-Übermittlungserweiterung für die Dienstanwendung mit dem Namen „SSRS_TESTAPPLICATION“.</span><span class="sxs-lookup"><span data-stu-id="df3c1-122">The following PowerShell script example, updates the full configuration for the report server e-mail delivery extension for the service application named "SSRS_TESTAPPLICATION".</span></span> <span data-ttu-id="df3c1-123">Beachten Sie, dass einige der im Skript aufgeführten Knoten, wie z. B. die Absenderadresse, über die Benutzeroberfläche festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="df3c1-123">Note some of the nodes listed in the script can also be set from the user interface, for example the "From" address.</span></span>  
  
    ```powershell
    $app = Get-SPRSServiceApplication | Where {$_.name -like "SSRS_TESTAPPLICATION *"}  
    $emailCfg = Get-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml
    $emailXml = [xml]$emailCfg
    $emailXml.SelectSingleNode("//SMTPServer").InnerText = "your email server name"  
    $emailXml.SelectSingleNode("//SendUsing").InnerText = "2"  
    $emailXml.SelectSingleNode("//SMTPAuthenticate").InnerText = "2"  
    $emailXml.SelectSingleNode("//From").InnerText = "your FROM email address"  
    Set-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" -ExtensionConfiguration $emailXml.OuterXml  
    ```  
  
2.  <span data-ttu-id="df3c1-124">Wenn Sie den Namen ihrer Dienst Anwendung überprüfen müssen, führen Sie das Cmdlet **Get-sprsserviceapplication** aus.</span><span class="sxs-lookup"><span data-stu-id="df3c1-124">If you need to verify the name of your service application, run the **Get-SPRSServiceApplication** cmdlet.</span></span>  
  
    ```powershell
    Get-SPRSServiceApplication  
    ```  
  
3.  <span data-ttu-id="df3c1-125">Im folgenden Beispiel wird der aktuelle Wert der E-Mail-Erweiterung für die Dienstanwendung mit dem Namen „SSRS_TESTAPPLICATION“ abgerufen.</span><span class="sxs-lookup"><span data-stu-id="df3c1-125">The following example will return the current values of the e-mail extension for the service application named "SSRS_TESTAPPLICATION".</span></span>  
  
    ```powershell
    $app = get-sprsserviceapplication | Where {$_.name -like "SSRSTEST_APPLICATION*"}  
    Get-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml  
    ```  
  
4.  <span data-ttu-id="df3c1-126">Im folgenden Beispiel wird eine neue Datei mit dem Namen „emailconfig.txt“ mit den aktuellen Werten der E-Mail-Erweiterung für die Dienstanwendung mit dem Namen „SSRS_TESTAPPLICATION“ erstellt.</span><span class="sxs-lookup"><span data-stu-id="df3c1-126">The following example will create a new file named "emailconfig.txt" with the current values of the e-mail extension for the service application named "SSRS_TESTAPPLICATION"</span></span>  
  
    ```powershell
    $app = Get-SPRSServiceApplication | Where {$_.name -like "SSRS_TESTAPPLICATION*"}  
    Get-SPRSExtension -identity $app -ExtensionType "Delivery" -name "Report Server Email" | Select -ExpandProperty ConfigurationXml | Out-File c:\emailconfig.txt  
    ```
