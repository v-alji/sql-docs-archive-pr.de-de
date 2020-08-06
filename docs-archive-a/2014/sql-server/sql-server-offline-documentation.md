---
title: Offline Dokumentation für SQL Server 2014
description: Erfahren Sie, wie Sie die Offline Dokumentation für SQL Server 2014 installieren. Verwenden Sie SQL Server Management Studio (SSMS) zum Anzeigen der Offlineinhalte.
ms.prod: sql
ms.technology: install
ms.topic: conceptual
ms.assetid: 51f8a08c-51d0-41d8-8bc5-1cb4d42622fb
author: markingmyname
ms.author: maghan
ms.reviewer: carlrab
ms.date: 07/19/2020
ms.openlocfilehash: bfd4adc658a203f8e2d22ef77ce0381084e36363
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617372"
---
# <a name="install-sql-server-2014-offline-documentation"></a><span data-ttu-id="0882f-104">Installieren von SQL Server 2014-Offline Dokumentation</span><span class="sxs-lookup"><span data-stu-id="0882f-104">Install SQL Server 2014 offline documentation</span></span>

<span data-ttu-id="0882f-105">In diesem Artikel wird beschrieben, wie Sie den Inhalt von Offline SQL Server 2014 herunterladen und anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0882f-105">This article describes how to download and view offline SQL Server 2014 content.</span></span> <span data-ttu-id="0882f-106">Mithilfe von Offlineinhalten können Sie ohne bestehende Internetverbindung auf die Dokumentation zugreifen (allerdings ist für den Download anfangs eine Internetverbindung erforderlich).</span><span class="sxs-lookup"><span data-stu-id="0882f-106">Offline content enables you to access the documentation without an internet connection (although an internet connection is initially required to download it).</span></span>

<span data-ttu-id="0882f-107">Das Verfahren umfasst die Verwendung des **Hilfe** Menüs von SQL Server Management Studio (SSMS), um auf das Help Viewer-Hilfsprogramm (HlpViewer.exe) zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="0882f-107">The technique involves using the **Help** menu of SQL Server Management Studio (SSMS), to access the Help Viewer utility (HlpViewer.exe).</span></span>

<span data-ttu-id="0882f-108">Die Offline Dokumentation ist für Versionen von SQL Server im Bereich von 2012-2019 und möglicherweise auch für weitere spätere Versionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0882f-108">Offline documentation is available for versions of SQL Server in the range of 2012-2019, and perhaps for additional later versions too.</span></span> <span data-ttu-id="0882f-109">Zwar lassen sich [Inhalte für frühere Versionen online](https://docs.microsoft.com/previous-versions/sql/) anzeigen, eine Offlineoption bietet jedoch ein komfortables Zugriffsverfahren für die älteren Inhalte.</span><span class="sxs-lookup"><span data-stu-id="0882f-109">Although you can view content for [previous versions online](https://docs.microsoft.com/previous-versions/sql/), an offline option provides a convenient way to access the older content.</span></span>

- [<span data-ttu-id="0882f-110">SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="0882f-110">SQL Server 2014</span></span>](#sql-server-2014-offline-content)
- [<span data-ttu-id="0882f-111">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="0882f-111">SQL Server 2012</span></span>](#sql-server-2012-offline-content)

<span data-ttu-id="0882f-112">Informationen zu den SQL Server 2016 und höheren Versionen finden Sie in der Versions spezifischen Dokumentation, um zu erfahren, wie diese Versionen Ihre Offline Dokumentation verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0882f-112">For SQL Server 2016 and later versions, see their version-specific documentation to learn how those versions handle their offline documentation.</span></span>

## <a name="sql-server-2014-offline-content"></a><span data-ttu-id="0882f-113">Offlineinhalte für SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="0882f-113">SQL Server 2014 offline content</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0882f-114">SQL 2014 Transact-SQL-Inhalte sind nur offline verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0882f-114">SQL 2014 Transact-SQL content is only available offline.</span></span>

<span data-ttu-id="0882f-115">In den folgenden Schritten wird erläutert, wie Offlineinhalte für SQL Server 2014 geladen werden.</span><span class="sxs-lookup"><span data-stu-id="0882f-115">The following steps explain how to load offline content for SQL Server 2014.</span></span>

1. <span data-ttu-id="0882f-116">Laden Sie den Inhalt [Produktdokumentation für Microsoft SQL Server 2014 für firewall- und proxygeschützte Umgebungen](https://www.microsoft.com/download/details.aspx?id=42557) aus dem Downloadcenter herunter, und speichern Sie ihn in einem Ordner.</span><span class="sxs-lookup"><span data-stu-id="0882f-116">Download the [Product Documentation for Microsoft SQL Server 2014 for firewall and proxy restricted environments](https://www.microsoft.com/download/details.aspx?id=42557) content from the download center and save it to a folder.</span></span>

2. <span data-ttu-id="0882f-117">Entzippen Sie die Datei, um die *MSHA* -Datei anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0882f-117">Unzip the file to view the *.msha* file.</span></span>

   ![Setupdatei der SQL Server 2014-Hilfedokumentation](../sql-server/media/sql-server-offline-documentation/sql-2014-help-content-setup-msha.png)

3. <span data-ttu-id="0882f-119">Wählen Sie in SSMS im Menü „Hilfe“ **Hilfeinhalt hinzufügen und entfernen** aus.</span><span class="sxs-lookup"><span data-stu-id="0882f-119">In SSMS, select **Add and Remove Help Content** on the Help menu.</span></span>

   ![Hinzufügen und Entfernen von Inhalten in Help Viewer](../sql-server/media/sql-server-offline-documentation/add-remove-content.png)

   <span data-ttu-id="0882f-121">Help Viewer öffnet die Registerkarte „Inhalt verwalten“.</span><span class="sxs-lookup"><span data-stu-id="0882f-121">The Help Viewer opens to the Manage Content tab.</span></span>

4. <span data-ttu-id="0882f-122">Wählen Sie unter „Installationsquelle“ **Datenträger**, um die neuesten Hilfeinhalte zu installieren, und anschließend die Auslassungspunkte (...) aus.</span><span class="sxs-lookup"><span data-stu-id="0882f-122">To install the latest help content, choose **Disk** under Installation source and then the ellipses (...).</span></span>

   ![Quelle „Datenträger“ in Help Viewer – Inhalte verwalten](../sql-server/media/sql-server-offline-documentation/install-source-disk.png)

   > [!NOTE]
   > <span data-ttu-id="0882f-124">Der lokale Speicherpfad auf der Registerkarte „Inhalt verwalten“ zeigt an, wo sich der Inhalt auf dem lokalen Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="0882f-124">The Local store path on the Manage Content tab shows where on the local computer the content is located.</span></span> <span data-ttu-id="0882f-125">Wenn Sie den Speicherort ändern möchten, wählen Sie **Verschieben** aus, geben Sie einen anderen Ordnerpfad im Feld **Nach** ein, und wählen Sie anschließend **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="0882f-125">To change the location, select **Move**, enter a different folder path in the **To** field, and then select **OK**.</span></span>
   <span data-ttu-id="0882f-126">Wenn die Installation der Hilfe nach dem Ändern des lokalen Speicherpfads fehlschlägt, müssen Sie Help Viewer schließen und anschließend wieder öffnen.</span><span class="sxs-lookup"><span data-stu-id="0882f-126">If the help installation fails after changing the Local store path, close and reopen the Help Viewer.</span></span> <span data-ttu-id="0882f-127">Stellen Sie sicher, dass der neue Speicherort im lokalen Speicherpfad angezeigt wird, und versuchen Sie dann noch mal, die Installation durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="0882f-127">Ensure the new location appears in the Local store path and then try the installation again.</span></span>

5. <span data-ttu-id="0882f-128">Navigieren Sie zu dem Ordner, in dem Sie die Inhalte entzippt haben.</span><span class="sxs-lookup"><span data-stu-id="0882f-128">Locate the folder where you unzipped the content.</span></span> <span data-ttu-id="0882f-129">Wählen Sie die Datei **HelpContentSetup.msha** im Ordner und anschließend **Öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="0882f-129">Select the **HelpContentSetup.msha** file in the folder then select **Open**.</span></span>

   ![Öffnen der Datei „SQL Server 2014 Help Content Setup.msha“](../sql-server/media/sql-server-offline-documentation/sql-2014-open-msha.png)

6. <span data-ttu-id="0882f-131">Geben Sie in der Suchleiste *sql server 2014* ein.</span><span class="sxs-lookup"><span data-stu-id="0882f-131">Type in *sql server 2014* in the search bar.</span></span> <span data-ttu-id="0882f-132">Wenn Sie die verfügbaren 2014-Inhalte sehen, wählen Sie neben jedem einzelnen Inhaltspaket (Buch), das Sie in Help Viewer installieren möchten, **Hinzufügen**, und wählen Sie dann **Aktualisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="0882f-132">Once you see the 2014 content available, select **Add** next to each content package (book) that you want to install to Help Viewer and then select **Update**.</span></span>

   ![Suche nach SQL Server 2014-Büchern in Help Viewer](../sql-server/media/sql-server-offline-documentation/sql-2014-search.png)

   ![Hinzufügen und Aktualisieren von SQL Server 2014-Büchern in Help Viewer](../sql-server/media/sql-server-offline-documentation/sql-2014-add-update.png)

    > [!NOTE]
    > <span data-ttu-id="0882f-135">Wenn der Help Viewer während des Hinzufügens von Inhalt einfriert (reagiert), ändern Sie die Zeile Cache LastRefreshed = " \<mm/dd/yyyy> 00:00:00" in der Datei "%LocalAppData%\microsoft\helpviewer2.x\ HlpViewer_SSMSx_en-US. Settings" oder "HlpViewer_VisualStudiox_en-US. Settings" in ein Datum in der Zukunft.</span><span class="sxs-lookup"><span data-stu-id="0882f-135">If the Help Viewer freezes (hangs) while adding content, change the Cache LastRefreshed="\<mm/dd/yyyy> 00:00:00" line in the %LOCALAPPDATA%\Microsoft\HelpViewer2.x\HlpViewer_SSMSx_en-US.settings or HlpViewer_VisualStudiox_en-US.settings file to some date in the future.</span></span> <span data-ttu-id="0882f-136">Weitere Informationen zu diesem Problem finden Sie unter [Visual Studio Help Viewer friert beim Begrüßungsbildschirm ein](/visualstudio/welcome-to-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="0882f-136">For more information about this issue, see [Visual Studio Help Viewer freezes](/visualstudio/welcome-to-visual-studio).</span></span>

7. <span data-ttu-id="0882f-137">Sie können überprüfen, ob die SQL Server 2014-Inhalte installiert wurden, indem Sie im Inhaltsbereich links nach *sql server 2014* suchen.</span><span class="sxs-lookup"><span data-stu-id="0882f-137">You can verify that the SQL Server 2014 content installed by searching under the content pane on the left for *sql server 2014*.</span></span>

   ![Automatische Aktualisierung von SQL Server 2014-Büchern](../sql-server/media/sql-server-offline-documentation/sql-2014-content.png)

## <a name="sql-server-2012-offline-content"></a><span data-ttu-id="0882f-139">Offlineinhalte für SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="0882f-139">SQL Server 2012 offline content</span></span>

<span data-ttu-id="0882f-140">In den folgenden Schritten wird erläutert, wie Offlineinhalte für SQL Server 2012 geladen werden.</span><span class="sxs-lookup"><span data-stu-id="0882f-140">The following steps explain how to load offline content for SQL Server 2012</span></span>

1. <span data-ttu-id="0882f-141">Laden Sie den Inhalt [Produktdokumentation für Microsoft SQL Server 2012 für firewall- und proxygeschützte Umgebungen](https://www.microsoft.com/download/details.aspx?id=35750) aus dem Downloadcenter herunter, und speichern Sie ihn in einem Ordner.</span><span class="sxs-lookup"><span data-stu-id="0882f-141">Download the [Product Documentation for Microsoft SQL Server 2012 for firewall and proxy restricted environments](https://www.microsoft.com/download/details.aspx?id=35750) content from the download center and save it to a folder.</span></span>

2. <span data-ttu-id="0882f-142">Entzippen Sie die Datei, um die *MSHA* -Datei anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0882f-142">Unzip the file to view the *.msha* file.</span></span>

   ![Setupdatei für SQL Server 2012-Hilfeinhalte](../sql-server/media/sql-server-offline-documentation/sql-2012-help-content-setup-msha.png)

3. <span data-ttu-id="0882f-144">Wählen Sie in SSMS im Menü „Hilfe“ **Hilfeinhalt hinzufügen und entfernen** aus.</span><span class="sxs-lookup"><span data-stu-id="0882f-144">In SSMS, select **Add and Remove Help Content** on the Help menu.</span></span>

   ![Hinzufügen und Entfernen von Inhalten in Help Viewer](../sql-server/media/sql-server-offline-documentation/add-remove-content.png)

   <span data-ttu-id="0882f-146">Help Viewer öffnet die Registerkarte „Inhalt verwalten“.</span><span class="sxs-lookup"><span data-stu-id="0882f-146">The Help Viewer opens to the Manage Content tab.</span></span>

4. <span data-ttu-id="0882f-147">Wählen Sie unter „Installationsquelle“ **Datenträger**, um die neuesten Hilfeinhalte zu installieren, und anschließend die Auslassungspunkte (...) aus.</span><span class="sxs-lookup"><span data-stu-id="0882f-147">To install the latest help content, choose **Disk** under Installation source and then the ellipses (...).</span></span>

   ![Quelle „Datenträger“ in Help Viewer – Inhalte verwalten](../sql-server/media/sql-server-offline-documentation/install-source-disk.png)

   > [!NOTE]
   > <span data-ttu-id="0882f-149">Der lokale Speicherpfad auf der Registerkarte „Inhalt verwalten“ zeigt an, wo sich der Inhalt auf dem lokalen Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="0882f-149">The Local store path on the Manage Content tab shows where on the local computer the content is located.</span></span> <span data-ttu-id="0882f-150">Wenn Sie den Speicherort ändern möchten, wählen Sie **Verschieben** aus, geben Sie einen anderen Ordnerpfad im Feld **Nach** ein, und wählen Sie anschließend **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="0882f-150">To change the location, select **Move**, enter a different folder path in the **To** field, and then select **OK**.</span></span>
   <span data-ttu-id="0882f-151">Wenn die Installation der Hilfe nach dem Ändern des lokalen Speicherpfads fehlschlägt, müssen Sie Help Viewer schließen und anschließend wieder öffnen.</span><span class="sxs-lookup"><span data-stu-id="0882f-151">If the help installation fails after changing the Local store path, close and reopen the Help Viewer.</span></span> <span data-ttu-id="0882f-152">Stellen Sie sicher, dass der neue Speicherort im lokalen Speicherpfad angezeigt wird, und versuchen Sie dann noch mal, die Installation durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="0882f-152">Ensure the new location appears in the Local store path and then try the installation again.</span></span>

5. <span data-ttu-id="0882f-153">Navigieren Sie zu dem Ordner, in dem Sie die Inhalte entzippt haben.</span><span class="sxs-lookup"><span data-stu-id="0882f-153">Locate the folder where you unzipped the content.</span></span> <span data-ttu-id="0882f-154">Wählen Sie die Datei **HelpContentSetup.msha** im Ordner und anschließend **Öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="0882f-154">Select the **HelpContentSetup.msha** file in the folder then select **Open**.</span></span>

   ![Öffnen der Datei „SQL Server 2012 Help Content Setup.msha“](../sql-server/media/sql-server-offline-documentation/sql-2012-open-msha.png)

6. <span data-ttu-id="0882f-156">Geben Sie in der Suchleiste *sql server 2012* ein.</span><span class="sxs-lookup"><span data-stu-id="0882f-156">Type in *sql server 2012* in the search bar.</span></span> <span data-ttu-id="0882f-157">Wenn Sie die verfügbaren 2012-Inhalte sehen, wählen Sie neben jedem einzelnen Inhaltspaket (Buch), das Sie in Help Viewer installieren möchten, **Hinzufügen**, und wählen Sie dann **Aktualisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="0882f-157">Once you see the 2012 content available, select **Add** next to each content package (book) that you want to install to Help Viewer and then select **Update**.</span></span>

   ![Suche nach SQL Server 2012-Büchern in Help Viewer](../sql-server/media/sql-server-offline-documentation/sql-2012-search.png)

   ![Hinzufügen und Aktualisieren von SQL Server 2012-Büchern in Help Viewer](../sql-server/media/sql-server-offline-documentation/sql-2012-add-update.png)

    > [!NOTE]
    > <span data-ttu-id="0882f-160">Wenn der Help Viewer während des Hinzufügens von Inhalt einfriert (reagiert), ändern Sie die Zeile Cache LastRefreshed = " \<mm/dd/yyyy> 00:00:00" in der Datei "%LocalAppData%\microsoft\helpviewer2.x\ HlpViewer_SSMSx_en-US. Settings" oder "HlpViewer_VisualStudiox_en-US. Settings" in ein Datum in der Zukunft.</span><span class="sxs-lookup"><span data-stu-id="0882f-160">If the Help Viewer freezes (hangs) while adding content, change the Cache LastRefreshed="\<mm/dd/yyyy> 00:00:00" line in the %LOCALAPPDATA%\Microsoft\HelpViewer2.x\HlpViewer_SSMSx_en-US.settings or HlpViewer_VisualStudiox_en-US.settings file to some date in the future.</span></span> <span data-ttu-id="0882f-161">Weitere Informationen zu diesem Problem finden Sie unter [Visual Studio Help Viewer friert beim Begrüßungsbildschirm ein](/visualstudio/welcome-to-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="0882f-161">For more information about this issue, see [Visual Studio Help Viewer freezes](/visualstudio/welcome-to-visual-studio).</span></span>

7. <span data-ttu-id="0882f-162">Sie können überprüfen, ob die SQL Server 2012-Inhalte geladen wurden, indem Sie im Inhaltsbereich links nach *sql server 2012* suchen.</span><span class="sxs-lookup"><span data-stu-id="0882f-162">You can verify that the SQL Server 2012 content is loaded by searching under the content pane on the left for *sql server 2012*.</span></span>

   ![Automatisch aktualisierte SQL Server 2012-Dokumentation](../sql-server/media/sql-server-offline-documentation/sql-2012-content.png)

## <a name="view-offline-documentation"></a><span data-ttu-id="0882f-164">Anzeigen der Offlinedokumentation</span><span class="sxs-lookup"><span data-stu-id="0882f-164">View offline documentation</span></span>

<span data-ttu-id="0882f-165">Sie können SQL Server Hilfe Inhalt mithilfe des Menüs **Hilfe** in der aktuellen Version von SQL Server Management Studio (SSMS) anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0882f-165">You can view SQL Server help content using the **HELP** menu in the latest version of SQL Server Management Studio (SSMS).</span></span>

### <a name="view-offline-help-content-in-ssms"></a><span data-ttu-id="0882f-166">Anzeigen von Offline-Hilfeinhalten in SSMS</span><span class="sxs-lookup"><span data-stu-id="0882f-166">View offline help content in SSMS</span></span>

<span data-ttu-id="0882f-167">Um die installierte Hilfe in SSMS anzuzeigen, wählen Sie im Menü „Hilfe“ **In Help Viewer starten** aus, um den Help Viewer zu starten.</span><span class="sxs-lookup"><span data-stu-id="0882f-167">To view the installed help in SSMS, select **Launch in Help Viewer** from the Help menu, to launch the Help Viewer.</span></span>

   ![In Help Viewer starten](../sql-server/media/sql-server-offline-documentation/helpviewer-view-offline.png)  

<span data-ttu-id="0882f-169">Help Viewer öffnet sich auf der Registerkarte „Inhalt verwalten“ mit dem installierten Inhaltsverzeichnis für die Hilfe im linken Bereich.</span><span class="sxs-lookup"><span data-stu-id="0882f-169">Help Viewer opens to the Manage Content tab, with the installed help table of contents in the left pane.</span></span> <span data-ttu-id="0882f-170">Wählen Sie im Inhaltsverzeichnis Artikel aus, um diese auf der rechten Seite anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0882f-170">select articles in the table of contents to display them in the right pane.</span></span>

> [!Important]
> <span data-ttu-id="0882f-171">Wenn der Inhaltsbereich nicht angezeigt wird, wählen Sie auf der linken Seite „Inhalt“ aus.</span><span class="sxs-lookup"><span data-stu-id="0882f-171">If the contents pane is not visible, select Contents on the left margin.</span></span> <span data-ttu-id="0882f-172">Wählen Sie das Reißzweckensymbol aus, damit der Inhaltsbereich geöffnet bleibt.</span><span class="sxs-lookup"><span data-stu-id="0882f-172">select the pushpin icon to keep the contents pane open.</span></span>  

   ![Help Viewer mit Inhalt](../sql-server/media/sql-server-offline-documentation/view-offline-all.png)
