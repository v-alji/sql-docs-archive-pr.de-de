---
title: Installieren Sie die eigenständige Version von Berichts-Generator (Berichts-Generator) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6b2291bb-1d20-4d08-81cb-a16dd8e01faf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2ba8c132125f56ad833a71a1c82221e2bf28d13e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619630"
---
# <a name="install-the-stand-alone-version-of-report-builder-report-builder"></a><span data-ttu-id="57edf-102">Installieren der eigenständigen Version des Berichts-Generators (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="57edf-102">Install the Stand-Alone Version of Report Builder (Report Builder)</span></span>
  <span data-ttu-id="57edf-103">Sie können Berichts-Generator [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] über das Feature Pack im [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53613) oder einen Speicherort installieren, z. b. den öffentlichen Ordner, in den die ReportBuilder3_x86.msi, das Windows Installer Paket für Berichts-Generator heruntergeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="57edf-103">You can install Report Builder from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] feature pack on the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53613) or a location such as public folder to which the ReportBuilder3_x86.msi, the Windows Installer Package for Report Builder, has been downloaded.</span></span>  
  
 <span data-ttu-id="57edf-104">Sie können auch eine Befehlszeileninstallation des Berichts-Generators ausführen und Argumente angeben, um die Installation anzupassen.</span><span class="sxs-lookup"><span data-stu-id="57edf-104">You can also perform a command line installation of Report Builder and provide arguments to customize the installation.</span></span> <span data-ttu-id="57edf-105">Neben den systeminternen MSI-Standardparametern können Sie die vom Berichts-Generator bereitgestellten benutzerdefinierten Parameter "RBINSTALLDIR" und "REPORTSERVERURL" verwenden.</span><span class="sxs-lookup"><span data-stu-id="57edf-105">In addition to the standard MSI intrinsic parameters, you can use the custom parameters that Report Builder provides: RBINSTALLDIR and REPORTSERVERURL.</span></span> <span data-ttu-id="57edf-106">"RBINSTALLDIR" dient zum Angeben des Stamminstallationsordners für den Berichts-Generator.</span><span class="sxs-lookup"><span data-stu-id="57edf-106">RBINSTALLDIR specifies the root installation folder for Report Builder.</span></span> <span data-ttu-id="57edf-107">Mit "REPORTSERVERURL" wird der Standardberichtsserver angegeben, der vom Berichts-Generator zum Speichern von Berichten auf dem Server verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="57edf-107">REPORTSERVERURL specifies the default report server that Report Builder uses to save reports on the server.</span></span>  
  
 <span data-ttu-id="57edf-108">Wenn Sie eine vollständig automatische Installation ohne Eingriff über die Benutzeroberfläche durchführen möchten, geben Sie die Option **/quiet** an.</span><span class="sxs-lookup"><span data-stu-id="57edf-108">If you want a completely silent installation, with no user interface interaction at all, specify the **/quiet** option.</span></span> <span data-ttu-id="57edf-109">Programmbedingt werden durch das Optionsflag "quiet" Installationsfehler unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="57edf-109">By design, the quiet option flag suppresses installation errors.</span></span> <span data-ttu-id="57edf-110">Deshalb wird bei Verwendung der Option „quiet“ die Angabe der Option **/l** empfohlen, die Protokollierung für diesen Fall angibt.</span><span class="sxs-lookup"><span data-stu-id="57edf-110">It is therefore recommended that you include the **/l** option, which specifies logging, when you use the quiet option.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="57edf-111">Die Sicherheitsfunktionen von Windows Vista und Windows 7 erfordern erweiterte Berechtigungen zum Ausführen von Befehlszeilenvorgängen. Auch wird die Angabe der Berechtigung zum Ausführen von Vorgängen über die Befehlszeile angefordert.</span><span class="sxs-lookup"><span data-stu-id="57edf-111">Windows Vista and Windows 7 security features require elevated permissions to run command line operations and will prompt for permission to run the command line.</span></span> <span data-ttu-id="57edf-112">Die Installation erfolgt nicht automatisch.</span><span class="sxs-lookup"><span data-stu-id="57edf-112">The installation is not silent.</span></span> <span data-ttu-id="57edf-113">Für eine unbeaufsichtigte Installation müssen Sie die Befehlszeile als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="57edf-113">To make the installation silent, you need to run the command line as an administrator.</span></span>  
  
### <a name="to-install-report-builder-from-the-download-site"></a><span data-ttu-id="57edf-114">So installieren Sie Berichts-Generator von der Downloadwebsite aus</span><span class="sxs-lookup"><span data-stu-id="57edf-114">To install Report Builder from the download site</span></span>  
  
1.  <span data-ttu-id="57edf-115">Wechseln Sie zu [Microsoft SQL Server 2012 Berichts-Generator](https://go.microsoft.com/fwlink/?LinkID=219138) , und suchen Sie den Abschnitt Berichts-Generator der Webseite.</span><span class="sxs-lookup"><span data-stu-id="57edf-115">Go to [Microsoft SQL Server 2012 Report Builder](https://go.microsoft.com/fwlink/?LinkID=219138) and locate the Report Builder section of the Web page.</span></span>  
  
2.  <span data-ttu-id="57edf-116">Klicken Sie auf **x86-Paket**.</span><span class="sxs-lookup"><span data-stu-id="57edf-116">Click **X86 Package**.</span></span>  
  
3.  <span data-ttu-id="57edf-117">Klicken Sie im Dialogfeld **Datei Download** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="57edf-117">In the **File Download** dialog box, click **Run**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="57edf-118">Laden Sie nur Dateien aus vertrauenswürdigen Quellen herunter.</span><span class="sxs-lookup"><span data-stu-id="57edf-118">Download only files from trusted sources.</span></span>  
  
4.  <span data-ttu-id="57edf-119">Klicken Sie im Dialogfeld Internet Explorer auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="57edf-119">In the Internet Explorer dialog box, click **Run**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="57edf-120">Führen Sie nur Dateien aus vertrauenswürdigen Quellen aus.</span><span class="sxs-lookup"><span data-stu-id="57edf-120">Run only files from trusted sources.</span></span>  
  
5.  <span data-ttu-id="57edf-121">Der Assistent für Microsoft SQL Server Berichts-Generator wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="57edf-121">The Microsoft SQL Server Report Builder Wizard is launched.</span></span>  
  
6.  <span data-ttu-id="57edf-122">Klicken Sie auf der Seite **Willkommen** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="57edf-122">On the **Welcome to the Installation Wizard** page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="57edf-123">Lesen Sie auf der Seite **Lizenzvertrag** die Vereinbarung, und wählen Sie dann die Option **Ich stimme den Bedingungen des Lizenzvertrags** zu.</span><span class="sxs-lookup"><span data-stu-id="57edf-123">On the **License Agreement** page, read the agreement and then select the **I accept the terms in the license agreement** option.</span></span> <span data-ttu-id="57edf-124">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57edf-124">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="57edf-125">Geben Sie Ihren Namen und den Firmennamen an.</span><span class="sxs-lookup"><span data-stu-id="57edf-125">Provide your personal name and company name.</span></span> <span data-ttu-id="57edf-126">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57edf-126">Click **Next**.</span></span>  
  
9. <span data-ttu-id="57edf-127">Klicken Sie optional auf der Seite **Funktionsauswahl** auf **Durchsuchen** oder auf Datenträger **Kosten**.</span><span class="sxs-lookup"><span data-stu-id="57edf-127">On the **Feature Selection** page, optionally click **Browse** or **Disk Cost**.</span></span> <span data-ttu-id="57edf-128">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57edf-128">Click **Next**.</span></span>  
  
    -   <span data-ttu-id="57edf-129">Klicken Sie auf **Durchsuchen** , um den Standard Speicherort Berichts-Generator anzuzeigen und zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="57edf-129">Click **Browse** to see the default location of Report Builder and update it.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="57edf-130">Der Standard Installationsordner für Berichts-Generator ist \<drive> Programme\Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="57edf-130">The default installation folder for Report Builder is \<drive>Program Files\Microsoft SQL Server.</span></span>  
  
    -   <span data-ttu-id="57edf-131">Klicken Sie auf Datenträger **Kosten** , um zu erfahren, wie viel Speicherplatz Berichts-Generator beansprucht.</span><span class="sxs-lookup"><span data-stu-id="57edf-131">Click **Disk Cost** to learn how much disk space Report Builder consumes.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="57edf-132">Wenn ein Volume nicht genügend freien Speicherplatz hat, wird das Volume hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="57edf-132">If a volume does not have sufficient amount of free disk space, the volume is highlighted.</span></span>  
  
10. <span data-ttu-id="57edf-133">Geben Sie optional auf der Seite **Standardzielserver** die URL zu dem Zielberichtsserver an, wenn nicht der Standardserver verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="57edf-133">On the **Default Target Server** page, optionally provide the URL to the target report server if it is different from the default.</span></span> <span data-ttu-id="57edf-134">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57edf-134">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="57edf-135">Wenn Sie den Berichts-Generator mit einer Verbindung zu einem Berichtsserver verwenden möchten, geben Sie die URL zu dem Server jetzt an.</span><span class="sxs-lookup"><span data-stu-id="57edf-135">If you plan to work with Report Builder when it is connected to a report server, it is convenient to provide the URL to the server at this time.</span></span> <span data-ttu-id="57edf-136">Allerdings können Sie dies auch über das Dialogfeld **Optionen** tun, wenn Sie in Berichts-Generator arbeiten.</span><span class="sxs-lookup"><span data-stu-id="57edf-136">However, you can also do this from the **Options** dialog box when you are working in Report Builder.</span></span>  
  
11. <span data-ttu-id="57edf-137">Klicken Sie auf **Installieren** , um die Installation von Berichts-Generator abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="57edf-137">Click **Install** to complete the installation of Report Builder.</span></span>  
  
### <a name="to-install-report-builder-from-a-share"></a><span data-ttu-id="57edf-138">So installieren Sie Berichts-Generator von einer Freigabe aus</span><span class="sxs-lookup"><span data-stu-id="57edf-138">To install Report Builder from a share</span></span>  
  
1.  <span data-ttu-id="57edf-139">Informationen zum Speicherort der Datei "ReportBuilder3_x86.msi", die Sie zum Installieren des Berichts-Generators auf dem lokalen Computer ausführen müssen, erhalten Sie von Ihrem Administrator.</span><span class="sxs-lookup"><span data-stu-id="57edf-139">Contact your administrator for the location of ReportBuilder3_x86.msi.msi that you run to install Report Builder on your local computer.</span></span>  
  
2.  <span data-ttu-id="57edf-140">Suchen Sie nach dem Windows Installer-Paket (MSI) für den Berichts-Generator ("ReportBuilder3_x86.msi"), und klicken Sie darauf.</span><span class="sxs-lookup"><span data-stu-id="57edf-140">Browse to locate the ReportBuilder3_x86.msi.msi, the Windows Installer Package (MSI) for Report Builder, and click it.</span></span>  
  
     <span data-ttu-id="57edf-141">Der Assistent für Microsoft SQL Server Berichts-Generator wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="57edf-141">The Microsoft SQL Server Report Builder Wizard is launched.</span></span>  
  
3.  <span data-ttu-id="57edf-142">Klicken Sie auf der Seite **Willkommen** auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="57edf-142">On the **Welcome to the Installation Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="57edf-143">Lesen Sie auf der Seite **Lizenzvertrag** die Vereinbarung, und wählen Sie dann die Option **Ich stimme den Bedingungen des Lizenzvertrags** zu.</span><span class="sxs-lookup"><span data-stu-id="57edf-143">On the **License Agreement** page, read the agreement and then select the **I accept the terms in the license agreement** option.</span></span> <span data-ttu-id="57edf-144">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57edf-144">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="57edf-145">Geben Sie Ihren Namen und den Firmennamen an.</span><span class="sxs-lookup"><span data-stu-id="57edf-145">Provide your personal name and company name.</span></span> <span data-ttu-id="57edf-146">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57edf-146">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="57edf-147">Klicken Sie optional auf der Seite **Funktionsauswahl** auf **Durchsuchen** oder auf Datenträger **Kosten**.</span><span class="sxs-lookup"><span data-stu-id="57edf-147">On the **Feature Selection** page, optionally click **Browse** or **Disk Cost**.</span></span> <span data-ttu-id="57edf-148">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57edf-148">Click **Next**.</span></span>  
  
    -   <span data-ttu-id="57edf-149">Klicken Sie auf **Durchsuchen** , um den Standard Speicherort Berichts-Generator anzuzeigen und zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="57edf-149">Click **Browse** to see the default location of Report Builder and update it.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="57edf-150">Der Standard Installationsordner für Berichts-Generator ist \<drive> Programme\Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="57edf-150">The default installation folder for Report Builder is \<drive>Program Files\Microsoft SQL Server.</span></span>  
  
    -   <span data-ttu-id="57edf-151">Klicken Sie auf Datenträger **Kosten** , um zu erfahren, wie viel Speicherplatz Berichts-Generator beansprucht.</span><span class="sxs-lookup"><span data-stu-id="57edf-151">Click **Disk Cost** to learn how much disk space Report Builder consumes.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="57edf-152">Wenn ein Volume nicht genügend freien Speicherplatz hat, wird das Volume hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="57edf-152">If a volume does not have sufficient amount of free disk space, the volume is highlighted.</span></span>  
  
7.  <span data-ttu-id="57edf-153">Geben Sie optional auf der Seite **Standardzielserver** die URL zu dem Zielberichtsserver an, wenn nicht der Standardserver verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="57edf-153">On the **Default Target Server** page, optionally provide the URL to the target report server if it is different from the default.</span></span> <span data-ttu-id="57edf-154">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="57edf-154">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="57edf-155">Wenn Sie den Berichts-Generator mit einer Verbindung zu einem Berichtsserver verwenden möchten, geben Sie die URL zu dem Server jetzt an.</span><span class="sxs-lookup"><span data-stu-id="57edf-155">If you plan to work with Report Builder when it is connected to a report server, it is convenient to provide the URL to the server at this time.</span></span> <span data-ttu-id="57edf-156">Allerdings können Sie dies auch über das Dialogfeld **Optionen** tun, wenn Sie in Berichts-Generator arbeiten.</span><span class="sxs-lookup"><span data-stu-id="57edf-156">However, you can also do this from the **Options** dialog box when you are working in Report Builder.</span></span>  
  
8.  <span data-ttu-id="57edf-157">Klicken Sie auf **Installieren** , um die Installation von Berichts-Generator abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="57edf-157">Click **Install** to complete the installation of Report Builder.</span></span>  
  
### <a name="to-install-report-builder-from-the-command-line"></a><span data-ttu-id="57edf-158">So installieren Sie Berichts-Generator mithilfe der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="57edf-158">To install Report Builder from the command line</span></span>  
  
1.  <span data-ttu-id="57edf-159">Wechseln Sie zu [Microsoft SQL Server 2012 Berichts-Generator](https://go.microsoft.com/fwlink/?LinkID=219138) , und suchen Sie den Abschnitt Berichts-Generator.</span><span class="sxs-lookup"><span data-stu-id="57edf-159">Go to [Microsoft SQL Server 2012 Report Builder](https://go.microsoft.com/fwlink/?LinkID=219138) and locate the Report Builder section.</span></span>  
  
2.  <span data-ttu-id="57edf-160">Klicken Sie auf **x86-Paket**.</span><span class="sxs-lookup"><span data-stu-id="57edf-160">Click **X86 Package**.</span></span>  
  
3.  <span data-ttu-id="57edf-161">Klicken Sie auf „Speichern“.</span><span class="sxs-lookup"><span data-stu-id="57edf-161">Click Save.</span></span>  
  
4.  <span data-ttu-id="57edf-162">Navigieren Sie optional zum Speicherort, in dem gespeichert werden soll, überprüfen Sie, ob die Option **Speichern** unter **Windows Installer Paket**ist, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="57edf-162">Optionally, browse to the location to save to, verify the **Save as** option is **Windows Installer Package**, and then click **Save**.</span></span>  
  
5.  <span data-ttu-id="57edf-163">Klicken Sie im Menü **Start** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="57edf-163">On the **Start** menu, click **Run**.</span></span>  
  
6.  <span data-ttu-id="57edf-164">Geben Sie im Textfeld Öffnen den Befehl  ein.`cmd.`</span><span class="sxs-lookup"><span data-stu-id="57edf-164">In the Open text box, type `cmd.`</span></span>  
  
7.  <span data-ttu-id="57edf-165">Navigieren Sie im Eingabeaufforderungsfenster zu dem Ordner, in dem "ReportBuilder3_x86.msi" gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="57edf-165">In the Command Prompt window, navigate to the folder where you saved ReportBuilder3_x86.msi.</span></span>  
  
8.  <span data-ttu-id="57edf-166">Geben Sie einen Befehl mit dem folgenden Format ein:</span><span class="sxs-lookup"><span data-stu-id="57edf-166">Type a command with the following format:</span></span>  
  
     `msiexec/i ReportBuilder3_.msi /option [value] [/option [value]]`  
  
     <span data-ttu-id="57edf-167">Bei den beiden folgenden Optionen handelt es sich um spezifische Optionen für die Installation des Berichts-Generators: "RBINSTALLDIR" und "REPORTSERVERURL".</span><span class="sxs-lookup"><span data-stu-id="57edf-167">The two options specific to installing Report Builder are: RBINSTALLDIR and REPORTSERVERURL.</span></span> <span data-ttu-id="57edf-168">Diese Argumente müssen nicht unbedingt in der Befehlszeile angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="57edf-168">It not required that you include these arguments in the command line.</span></span> <span data-ttu-id="57edf-169">Der grundlegende Befehl lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="57edf-169">The following is the baseline command:</span></span>  
  
     `msiexec /i ReportBuilder3_x86.msi /quiet`  
  
9. <span data-ttu-id="57edf-170">Drücken Sie die EINGABETASTE, um den Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="57edf-170">To run the command, press Enter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57edf-171">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="57edf-171">See Also</span></span>  
 <span data-ttu-id="57edf-172">[Unterstützung für Installation, Deinstallation und Berichts-Generator](../install-uninstall-and-report-builder-support.md) </span><span class="sxs-lookup"><span data-stu-id="57edf-172">[Install, Uninstall, and Report Builder Support](../install-uninstall-and-report-builder-support.md) </span></span>  
 [<span data-ttu-id="57edf-173">Deinstallieren Sie die eigenständige Version von Berichts-Generator &#40;Berichts-Generator&#41;</span><span class="sxs-lookup"><span data-stu-id="57edf-173">Uninstall the Stand-Alone Version of Report Builder &#40;Report Builder&#41;</span></span>](install-report-builder.md)  
  
  
