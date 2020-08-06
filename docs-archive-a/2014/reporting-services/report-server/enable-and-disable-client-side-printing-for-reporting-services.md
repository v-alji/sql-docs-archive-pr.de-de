---
title: Aktivieren und Deaktivieren des clientseitigen Drucks für Reporting Services | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0e709c96-7517-4547-8ef6-5632f8118524
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 031a7cd9b5da07b03b76b6bf49db63572a8fe546
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619578"
---
# <a name="enable-and-disable-client-side-printing-for-reporting-services"></a><span data-ttu-id="c1d2e-102">Aktivieren und Deaktivieren des clientseitige Drucks für Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c1d2e-102">Enable and Disable Client-Side Printing for Reporting Services</span></span>
  <span data-ttu-id="c1d2e-103">Das [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX-Steuerelement **RSClientPrint**bietet Client seitiges Drucken für Berichte, die in einem Browser angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX control, **RSClientPrint**, provides client-side printing for reports viewed in a browser.</span></span> <span data-ttu-id="c1d2e-104">Vom Steuerelement wird ein benutzerdefiniertes Dialogfeld zum Drucken angezeigt, das die Funktionen enthält, die in Druckdialogfeldern üblicherweise vorkommen.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-104">The control displays a custom print dialog box that supports features common to other print dialog boxes.</span></span> <span data-ttu-id="c1d2e-105">Dazu zählen Druckvorschau, Seitenauswahl zum Angeben bestimmter Seiten und Bereiche, Seitenränder und Ausrichtung.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-105">The features include print preview, page selections for specifying specific pages and ranges, page margins, and orientation.</span></span> <span data-ttu-id="c1d2e-106">Clientseitiges Drucken ist standardmäßig aktiviert, Sie können diese Funktion jedoch auf Wunsch deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-106">Although client-side printing is enabled by default, you can disable the feature to prevent it from being used.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c1d2e-107">Zum Herunterladen von ActiveX-Steuerelementen sind Administratorberechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-107">Downloading ActiveX controls requires administrator permissions.</span></span>  
  
## <a name="downloading-the-activex-control"></a><span data-ttu-id="c1d2e-108">Herunterladen des ActiveX-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="c1d2e-108">Downloading the ActiveX Control</span></span>  
 <span data-ttu-id="c1d2e-109">Benutzer, die die Druckfunktion verwenden möchten, müssen das ActiveX-Steuerelement, von dem die Clientdruckfunktionalität bereitgestellt wird, herunterladen und installieren.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-109">Each user who wants to use the print feature must download and install the ActiveX control that provides client print functionality.</span></span> <span data-ttu-id="c1d2e-110">Wenn ein Benutzer zum ersten Mal auf der Berichts Symbolleiste auf das **Drucker** Symbol klickt, wird das Microsoft-ActiveX-Steuerelement auf den Computer heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-110">The first time a user clicks the **Printer** icon on the report toolbar, the Microsoft ActiveX control is downloaded to the computer.</span></span> <span data-ttu-id="c1d2e-111">Nachdem das Steuerelement heruntergeladen wurde, wird das Dialogfeld **Drucken** angezeigt, wenn der Benutzer auf das **Drucker** Symbol klickt.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-111">After the control is downloaded, the **Print** dialog box displays whenever the user clicks the **Printer** icon.</span></span>  
  
 <span data-ttu-id="c1d2e-112">Abhängig von den Browsereinstellungen bestehen folgende Möglichkeiten: Der Benutzer wird zur Installation des Steuerelements aufgefordert, die Installation des Steuerelements wird verhindert, oder das Steuerelement wird unbeaufsichtigt im Hintergrund installiert.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-112">Depending on browser settings, the user may be prompted to install the control, be prevented from installing the control, or have the control install transparently in the background.</span></span>  
  
 <span data-ttu-id="c1d2e-113">Für [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer werden Einstellungen für das herunterladen und die Installation von ActiveX-Steuerelementen über den Knoten **ActiveX-Steuerelemente und Plug-ins** auf der Seite **Sicherheitseinstellungen** für die Webinhalts Zone angegeben.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-113">For [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer, settings that affect ActiveX control download and installation are specified through the **ActiveX controls and plug-ins** node in the **Security Settings** page for the Web content zone.</span></span> <span data-ttu-id="c1d2e-114">Von folgenden Einstellungen wird bestimmt, ob Benutzer das Druckensteuerelement herunterladen und ausführen können. Das Verhalten basiert auf Einstellungen der Webzonensicherheit:</span><span class="sxs-lookup"><span data-stu-id="c1d2e-114">The following settings determine whether users can download and run the print control, based on Web zone security preferences:</span></span>  
  
-   <span data-ttu-id="c1d2e-115">Download von signierten ActiveX-Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-115">Download signed ActiveX controls.</span></span>  
  
-   <span data-ttu-id="c1d2e-116">ActiveX-Steuerelemente ausführen, die für die Skripterstellung sicher sind.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-116">Script ActiveX controls marked safe for scripting.</span></span>  
  
-   <span data-ttu-id="c1d2e-117">ActiveX-Steuerelemente und Plug-Ins ausführen.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-117">Run ActiveX controls and plug-ins.</span></span>  
  
 <span data-ttu-id="c1d2e-118">Benutzer, die **RSClientPrint** zum Ausführen von Client seitigem Drucken verwenden möchten, müssen Folgendes aktivieren:</span><span class="sxs-lookup"><span data-stu-id="c1d2e-118">Users who want to use **RSClientPrint** to perform client-side printing must enable the following:</span></span>  
  
-   <span data-ttu-id="c1d2e-119">**Herunterladen von signierten ActiveX** -Steuerelementen und **Skript-ActiveX-Steuer** Element, das für die Installation als sicher</span><span class="sxs-lookup"><span data-stu-id="c1d2e-119">**Download signed ActiveX controls** and **Script ActiveX control marked safe for scripting** for installation purposes.</span></span>  
  
-   <span data-ttu-id="c1d2e-120">**Führen Sie ActiveX-Steuerelemente und Plug-ins** für fortlaufende Druckvorgänge aus.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-120">**Run ActiveX controls and plug-ins** for ongoing print operations.</span></span>  
  
 <span data-ttu-id="c1d2e-121">Das **RSClientPrint** -ActiveX-Steuerelement wird signiert, d. h., es enthält ein gültiges digitales Zertifikat aus [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c1d2e-121">The **RSClientPrint** ActiveX control is signed, meaning it contains a valid digital certificate from [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span></span>  
  
## <a name="enabling-and-disabling-client-side-printing"></a><span data-ttu-id="c1d2e-122">Aktivieren und Deaktivieren des clientseitigen Druckens</span><span class="sxs-lookup"><span data-stu-id="c1d2e-122">Enabling and Disabling Client-Side Printing</span></span>  
 <span data-ttu-id="c1d2e-123">Berichts Server Administratoren können die Druckfunktion deaktivieren, indem Sie die Berichts Server-System Eigenschaft **EnableClientPrinting** auf festlegen `false` .</span><span class="sxs-lookup"><span data-stu-id="c1d2e-123">Report server administrators have the option of disabling the print feature by setting the report server system property **EnableClientPrinting** to `false`.</span></span> <span data-ttu-id="c1d2e-124">Dadurch wird das clientseitige Drucken für alle von diesem Server verwalteten Berichte deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-124">This will disable client-side printing for all reports managed by that server.</span></span> <span data-ttu-id="c1d2e-125">Standardmäßig ist **EnableClientPrinting** auf festgelegt `true` .</span><span class="sxs-lookup"><span data-stu-id="c1d2e-125">By default, **EnableClientPrinting** is set to `true`.</span></span> <span data-ttu-id="c1d2e-126">Sie können das clientseitige Drucken folgendermaßen deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="c1d2e-126">You can disable client-side printing in the following ways:</span></span>  
  
-   <span data-ttu-id="c1d2e-127">Für einen **Berichtsserver im einheitlichen Modus**:</span><span class="sxs-lookup"><span data-stu-id="c1d2e-127">For a **Native mode report server**:</span></span>  
  
    1.  <span data-ttu-id="c1d2e-128">Starten Sie [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] mit Administratorrechten.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-128">Start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] with administrative privileges.</span></span>  
  
    2.  <span data-ttu-id="c1d2e-129">Stellen Sie eine Verbindung mit einer Berichtsserverinstanz in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-129">Connect to a report server instance in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
    3.  <span data-ttu-id="c1d2e-130">Klicken Sie mit der rechten Maustaste auf den Berichtsserverknoten, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-130">Right-click the report server node, and then click **Properties**.</span></span> <span data-ttu-id="c1d2e-131">Wenn die Option **Eigenschaften** deaktiviert ist, überprüfen Sie, ob [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] mit Administratorrechten gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-131">If the **Properties** option is disabled, verify you started [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] with administrative privileges.</span></span>  
  
    4.  <span data-ttu-id="c1d2e-132">Wählen Sie **Download aktivieren für das ActiveX-Client-Druck Steuerelement aus**.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-132">Select **Enable download for the ActiveX client print control**.</span></span>  
  
    5.  <span data-ttu-id="c1d2e-133">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-133">Click **OK**.</span></span>  
  
-   <span data-ttu-id="c1d2e-134">Für einen **Berichtsserver im SharePoint-Modus**:</span><span class="sxs-lookup"><span data-stu-id="c1d2e-134">For a **SharePoint mode report server**:</span></span>  
  
    1.  <span data-ttu-id="c1d2e-135">Klicken Sie in der SharePoint-Zentraladministration auf **Anwendungsverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-135">In SharePoint Central Administration, click **Application Management**.</span></span>  
  
    2.  <span data-ttu-id="c1d2e-136">Klicken Sie auf **Dienstanwendungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-136">Click **Manage service applications**.</span></span>  
  
    3.  <span data-ttu-id="c1d2e-137">Klicken Sie auf den Namen der [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Dienst Anwendung, und klicken Sie dann im SharePoint-Menüband auf **Verwalten** .</span><span class="sxs-lookup"><span data-stu-id="c1d2e-137">Click the name of your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application, and then click **Manage** in the SharePoint ribbon.</span></span>  
  
    4.  <span data-ttu-id="c1d2e-138">Klicken Sie auf **Systemeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-138">Click **System Settings**.</span></span>  
  
    5.  <span data-ttu-id="c1d2e-139">Wählen Sie **Clientdruck aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-139">Select **Enable Client Printing**.</span></span> <span data-ttu-id="c1d2e-140">Die Option **Clientdruck aktivieren** befindet sich weiter unten auf der Seite.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-140">The **Enable Client Printing** option is near the bottom of the page.</span></span>  
  
    6.  <span data-ttu-id="c1d2e-141">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-141">Click **OK**.</span></span>  
  
-   <span data-ttu-id="c1d2e-142">Schreiben Sie ein Skript oder einen Code, um die Berichts Server-System Eigenschaft **EnableClientPrinting** auf festzulegen.`false.`</span><span class="sxs-lookup"><span data-stu-id="c1d2e-142">Write script or code to set the report server system property **EnableClientPrinting** to `false.`</span></span>  
  
 <span data-ttu-id="c1d2e-143">Im folgenden Beispielskript wird eine Methode zum Deaktivieren des clientseitigen Druckens erläutert.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-143">The following sample script illustrates one approach for disabling client-side printing.</span></span> <span data-ttu-id="c1d2e-144">Kompilieren Sie den folgenden [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]-Code, und führen Sie ihn anschließend aus, um die Eigenschaft **EnableClientPrinting** auf **FALSE**festzulegen.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-144">Compile and then run the following [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] code to set the **EnableClientPrinting** property to **False**.</span></span> <span data-ttu-id="c1d2e-145">Führen Sie nach der Ausführung des Codes einen Neustart von IIS aus.</span><span class="sxs-lookup"><span data-stu-id="c1d2e-145">After you run the code, restart IIS.</span></span>  
  
### <a name="sample-script"></a><span data-ttu-id="c1d2e-146">Beispielskript</span><span class="sxs-lookup"><span data-stu-id="c1d2e-146">Sample Script</span></span>  
  
```  
Imports System  
Imports System.Web.Services.Protocols  
Class Sample  
   Public Shared Sub Main()  
Dim rs As New ReportingService()  
      rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
        Dim props(0) As [Property]  
        Dim setProp As New [Property]  
        setProp.Name = "EnableClientPrinting"  
        setProp.Value = "False"   
        props(0) = setProp  
        Try  
            rs.SetSystemProperties(props)  
        Catch ex As System.Web.Services.Protocols.SoapException  
            Console.Write(ex.Detail.InnerXml)  
        Catch e as Exception  
            Console.Write(e.Message)  
        End Try  
    End Sub 'Main  
End Class 'Sample  
```  
  
  
