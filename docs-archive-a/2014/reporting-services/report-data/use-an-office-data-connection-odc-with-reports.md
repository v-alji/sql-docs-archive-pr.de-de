---
title: Verwenden einer Office Data Connection (. ODC) mit Berichten (Reporting Services im integrierten SharePoint-Modus) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Office Data Connection (.odc) files
- SharePoint integration [Reporting Services], shared data sources
- .odc files
ms.assetid: e8d6896d-f886-4390-8b5d-96f0a50c250c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d795c46f46b45511079ac03add2d18214ac54489
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608309"
---
# <a name="use-an-office-data-connection-odc-with-reports-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="0f662-102">Verwenden einer Office Data Connection (.odc) für Berichte (Reporting Services im integrierten SharePoint-Modus)</span><span class="sxs-lookup"><span data-stu-id="0f662-102">Use an Office Data Connection (.odc) with Reports (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="0f662-103">Bei beschränkten Szenarien können Sie eine vorhandene Office Data Connection (.odc)-Datei verwenden, um Verbindungsinformationen für einen [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Bericht bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="0f662-103">For limited scenarios, you can use an existing Office Data Connection (.odc) file to provide connection information to a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report.</span></span> <span data-ttu-id="0f662-104">Sie können beim Erstellen einer freigegebenen Datenquelle eine ODC-Datei statt einer RSDS-Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="0f662-104">An .odc file can be used in place of an .rsds file when you create a shared data source.</span></span> <span data-ttu-id="0f662-105">Eine ODC-Datei wird vom Berichtsserver auf dieselbe Weise verwendet wie eine RSDS-Datei. Die Datei wird gelesen, um den Datenquellentyp, eine Verbindungszeichenfolge und Anmeldeinformationen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0f662-105">The report server uses an .odc file in the same way it uses an .rsds file; it reads the file for the data source type, a connection string, and credential information.</span></span>  
  
 <span data-ttu-id="0f662-106">Nicht alle ODC-Dateien können für einen [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Bericht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0f662-106">Not all .odc files can be used with a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report.</span></span> <span data-ttu-id="0f662-107">Anhand der Datenverarbeitungserweiterung und der Merkmale des Berichts und der ODC-Datei wird bestimmt, ob eine ODC-Datei verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="0f662-107">The data processing extension and characteristics of the report and .odc file determine whether an .odc can be used:</span></span>  
  
-   <span data-ttu-id="0f662-108">Der Bericht muss für die Verwendung mit einem OLE DB- oder ODBC-Datenanbieter entworfen sein.</span><span class="sxs-lookup"><span data-stu-id="0f662-108">The report must be designed to work with an OLE DB or ODBC data provider.</span></span> <span data-ttu-id="0f662-109">Wenn Sie den Bericht mithilfe einer anderen Datenverarbeitungserweiterung erstellt haben, enthält der Bericht oder enthalten dessen Dateien möglicherweise Funktionen, die nicht vom OLE DB- oder ODBC-Datenanbieter unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="0f662-109">If you used a different data processing extension to create the report, the report or its queries might include functionality that is not supported by the OLE DB or ODBC data provider.</span></span>  
  
-   <span data-ttu-id="0f662-110">Die ODC-Datei muss über die erwarteten Elemente und die erwartete Struktur verfügen.</span><span class="sxs-lookup"><span data-stu-id="0f662-110">The .odc file must have the expected elements and structure.</span></span> <span data-ttu-id="0f662-111">Der Datenanbieter und die Einstellungen für die Anmeldeinformationen müssen explizit in der Datei festgelegt sein, damit sie vom Berichtsserver gelesen werden können.</span><span class="sxs-lookup"><span data-stu-id="0f662-111">The data provider and credential settings must be set explicitly in the file so that they can be read by the report server.</span></span> <span data-ttu-id="0f662-112">Die einfachste Methode, diese Werte festzulegen, besteht darin, die ODC-Datei vor dem Hochladen in die SharePoint-Bibliothek zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="0f662-112">The best way to set these values is to export the .odc file before uploading it to the SharePoint library.</span></span>  
  
-   <span data-ttu-id="0f662-113">Die ODC-Datei muss den Verbindungstyp OLE DB oder ODBC angeben.</span><span class="sxs-lookup"><span data-stu-id="0f662-113">The .odc file must specify a connection type of OLE DB or ODBC.</span></span>  
  
-   <span data-ttu-id="0f662-114">In der ODC-Datei muss eine Verbindungszeichenfolge angegeben sein.</span><span class="sxs-lookup"><span data-stu-id="0f662-114">The .odc file must specify a connection string.</span></span>  
  
-   <span data-ttu-id="0f662-115">Die Anmeldeinformationen können auf `None`, `Stored` oder `Integrated` festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="0f662-115">Credentials can be set to `None`, `Stored`, or `Integrated`.</span></span> <span data-ttu-id="0f662-116">Wenn die Methode für die Anmeldeinformationen auf `Stored` festgelegt ist, wird der Benutzer vom Berichtsserver zur Eingabe seiner Anmeldeinformationen aufgefordert, und es werden nicht die gespeicherten Anmeldeinformationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="0f662-116">If the credentials method is set to `Stored`, the report server will prompt the user for credentials instead of using the stored credentials.</span></span> <span data-ttu-id="0f662-117">Vom Berichtsserver können wie in einer ODC-Datei definiert keine gespeicherten Anmeldeinformationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0f662-117">The report server cannot use stored credentials as defined in the .odc file.</span></span>  
  
-   <span data-ttu-id="0f662-118">Die Datenquelle muss über ein Schema verfügen, das mit dem zum Erstellen des Berichts verwendeten Schema identisch ist.</span><span class="sxs-lookup"><span data-stu-id="0f662-118">The data source must have schema that is identical to the one used to create the report.</span></span> <span data-ttu-id="0f662-119">Wenn die Datenstrukturen unterschiedlich sind, wird der Bericht nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0f662-119">If the data structures are different, the report will not run.</span></span>  
  
-   <span data-ttu-id="0f662-120">Die ODC-Datei muss in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Office 2007 erstellt werden. (Ältere Versionen von ODC-Dateien sind nicht kompatibel mit Berichtsdefinitionsdateien.)</span><span class="sxs-lookup"><span data-stu-id="0f662-120">The .odc file must be created in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Office 2007 (older versions of .odc are not compatible with report definition files).</span></span>  
  
 <span data-ttu-id="0f662-121">Sie können keine ODC-Dateien verwenden, in denen Verbindungen mit Datenquellen angegeben sind, die auf einem Berichtsserver nicht verarbeitet werden können. Dies gilt auch, wenn die Datenquellentypen der ODC-Datei unterstützen Datenquellentypen ähneln.</span><span class="sxs-lookup"><span data-stu-id="0f662-121">You cannot use .odc files that specify connections to data sources that cannot be processed on a report server, even if the .odc data source types look similar to supported data source types.</span></span> <span data-ttu-id="0f662-122">Insbesondere, wenn Sie eine ODC-Datei in Microsoft Excel 2007 erstellt haben, die Daten aus Microsoft Access, dem Web oder einer Textdatei abruft, können Sie mit dieser ODC-Datei keine Daten für einen Bericht bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0f662-122">Specifically, if you created an .odc file in Microsoft Excel 2007 that retrieves data from Microsoft Access, the Web, or a text file, you cannot use that .odc file to provide data to a report.</span></span>  
  
 <span data-ttu-id="0f662-123">Berichte und Modelle des Berichts-Generators werden für ODC-Dateien nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0f662-123">Report Builder reports and models do not work with .odc file.</span></span> <span data-ttu-id="0f662-124">Sie können eine ODC-Datei nicht zum Generieren eines Modells verwenden, und Sie können das Modell nicht so konfigurieren, dass eine freigegebene Datenquelle mit einem Link zu einer ODC-Datei verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0f662-124">You cannot use an .odc file to generate a model, and you cannot configure the model to use a shared data source that links to an .odc file.</span></span>  
  
 <span data-ttu-id="0f662-125">Wenn Sie nicht mit ODC-Dateien vertraut sind, können Sie die folgenden Anweisungen zum Erstellen und Exportieren einer ODC-Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="0f662-125">If you are not familiar with .odc files, you can use the following instructions to create and export one.</span></span> <span data-ttu-id="0f662-126">Eine einfache Möglichkeit, eine ODC-Datei für eine OLE DB-Datenquelle zu erstellen, besteht im Verwenden von Excel 2007 und dem Datenverbindungs-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="0f662-126">One easy way to create an .odc file for an OLE DB data source is to use Excel 2007 and the Data Connection Wizard.</span></span> <span data-ttu-id="0f662-127">Beachten Sie, dass vom Assistenten keine Datenquelle erstellt wird. Sie müssen über eine externe Datenquelle verfügen, die bereits definiert ist.</span><span class="sxs-lookup"><span data-stu-id="0f662-127">Note that the wizard does not create a data source; you must have an external data source that is already defined.</span></span>  
  
 <span data-ttu-id="0f662-128">Eine vorhandene ODC-Datei sollte nur verwendet werden, wenn sie vollständig mit dem Bericht und den Abfragen kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="0f662-128">An existing .odc file should only be used if it is fully compatible with the report and queries.</span></span> <span data-ttu-id="0f662-129">Wenn Fehler auftreten, die beträchtliche Änderungen am Bericht oder an der ODC-Datei erfordern, sollten Sie eine neue RSDS-Datei für den Bericht erstellen.</span><span class="sxs-lookup"><span data-stu-id="0f662-129">If you run into errors that require significant modifications to either the report or to the .odc file, you should create a new .rsds file for the report.</span></span> <span data-ttu-id="0f662-130">Weitere Informationen zum Erstellen einer freigegebenen Datenquelle, die eine RSDS-Datei verwendet, finden Sie unter [Erstellen und Verwalten von freigegebenen Datenquellen (Reporting Services im integrierten SharePoint-Modus)](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md).</span><span class="sxs-lookup"><span data-stu-id="0f662-130">For more information about how to create a shared data source that uses an .rsds file, see [Create and Manage Shared Data Sources &#40;Reporting Services in SharePoint Integrated Mode&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md).</span></span>  
  
### <a name="to-create-and-export-an-odc-file"></a><span data-ttu-id="0f662-131">So erstellen und exportieren Sie eine ODC-Datei</span><span class="sxs-lookup"><span data-stu-id="0f662-131">To create and export an .odc file</span></span>  
  
1.  <span data-ttu-id="0f662-132">Starten Sie Excel 2007.</span><span class="sxs-lookup"><span data-stu-id="0f662-132">Start Excel 2007.</span></span>  
  
2.  <span data-ttu-id="0f662-133">Klicken Sie auf der Registerkarte **Daten** in der Gruppe **Externe Daten** auf **Aus anderen Quellen**, und klicken Sie anschließend auf **Vom Datenverbindungs-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="0f662-133">On the **Data** tab, in the **Get External Data** group, click **From Other Sources**, and then click **From Data Connection Wizard**.</span></span>  
  
3.  <span data-ttu-id="0f662-134">Wählen Sie **Weitere/erweiterte**aus, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="0f662-134">Select **Other/Advanced**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="0f662-135">Wählen Sie **Microsoft OLE DB Provider for SQL Server**aus, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="0f662-135">Select **Microsoft OLE DB Provider for SQL Server**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="0f662-136">Geben Sie den Namen des Servers (standardmäßig der Netzwerkname des Computers) und ein Benutzerkonto ein, das über eine gültige Anmeldung und Datenbankberechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="0f662-136">Enter the name of the server (by default, it is the network name of the computer) and a user account that has a valid login and database permissions.</span></span> <span data-ttu-id="0f662-137">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="0f662-137">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="0f662-138">Wählen Sie eine Datenbank aus, und klicken Sie anschließend auf **OK** , um das Dialogfeld **Datenlinkeigenschaften** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="0f662-138">Select a database, and then click **OK** to close the **Data Link** dialog box.</span></span>  
  
7.  <span data-ttu-id="0f662-139">Das Kontrollkästchen **Mit einer ausgewählten Tabelle verbinden:** ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0f662-139">The **Connect to specific table** check box is selected by default.</span></span> <span data-ttu-id="0f662-140">Es wird zum Abrufen von Daten aus einer spezifischen Tabelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="0f662-140">It is used to retrieve data from a specific table.</span></span> <span data-ttu-id="0f662-141">Es werden alle Abfragen in einer ODC-Datei vom Berichtsserver ignoriert. Daher ist es nicht ausschlaggebend, ob Sie das Kontrollkästchen aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0f662-141">The report server ignores all queries in an .odc file, so it does not matter whether you select or clear the check box.</span></span> <span data-ttu-id="0f662-142">Abfragen, mit denen Daten für einen Bericht abgerufen werden, befinden sich in der Berichtsdefinitionsdatei, nicht in externen Dateien.</span><span class="sxs-lookup"><span data-stu-id="0f662-142">Queries that retrieve data for a report are included in a report definition file and not in external files.</span></span>  
  
8.  <span data-ttu-id="0f662-143">Während die Verbindung geöffnet ist, können Sie Eigenschaften bearbeiten und die Verbindungsdatei exportieren.</span><span class="sxs-lookup"><span data-stu-id="0f662-143">While the connection is open, you can edit properties and export it.</span></span> <span data-ttu-id="0f662-144">Klicken Sie auf der Registerkarte **Daten** in der Gruppe **Verbindungen** auf **Eigenschaften**, und klicken Sie anschließend neben dem Namen der Verbindung auf die Schaltfläche **Verbindungseigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="0f662-144">On the **Data** tab, in the **Connections** group, click **Properties**, and then click the **Connection Properties** button next to the connection name.</span></span>  
  
9. <span data-ttu-id="0f662-145">Klicken Sie auf der Registerkarte **Definition** auf **Verbindungsdatei exportieren**.</span><span class="sxs-lookup"><span data-stu-id="0f662-145">On the **Definition** tab, click **Export Connection File**.</span></span>  
  
10. <span data-ttu-id="0f662-146">Geben Sie einen Namen für die Datei ein, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="0f662-146">Enter a name for the file, and then click **Save**.</span></span> <span data-ttu-id="0f662-147">Schließen Sie die Anwendung und alle geöffneten Dateien.</span><span class="sxs-lookup"><span data-stu-id="0f662-147">Close the application and all open files.</span></span>  
  
### <a name="to-upload-and-use-an-odc-file"></a><span data-ttu-id="0f662-148">So laden Sie eine ODC-Datei hoch und verwenden Sie</span><span class="sxs-lookup"><span data-stu-id="0f662-148">To upload and use an .odc file</span></span>  
  
1.  <span data-ttu-id="0f662-149">Öffnen Sie die Bibliothek, in die Sie die Verbindungsdatei hochladen möchten.</span><span class="sxs-lookup"><span data-stu-id="0f662-149">Open the library into which you want to upload the connection file.</span></span>  
  
2.  <span data-ttu-id="0f662-150">Klicken Sie im Menü **Upload** auf **Dokumentupload**.</span><span class="sxs-lookup"><span data-stu-id="0f662-150">On the **Upload** menu, click **Upload document**.</span></span>  
  
3.  <span data-ttu-id="0f662-151">Klicken Sie auf **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="0f662-151">Click **Browse**.</span></span>  
  
4.  <span data-ttu-id="0f662-152">Wählen Sie die von Ihnen erstellte ODC-Datei aus.</span><span class="sxs-lookup"><span data-stu-id="0f662-152">Select the .odc file you created.</span></span> <span data-ttu-id="0f662-153">Die ODC-Datei befindet sich standardmäßig im Ordner Meine Dateien unter Meine Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="0f662-153">By default, the .odc file is in the My Documents folder, in My Data Sources.</span></span>  
  
5.  <span data-ttu-id="0f662-154">Klicken Sie auf **Öffnen** , um die Datei auszuwählen, und klicken Sie auf **OK** , um die Auswahl zu speichern.</span><span class="sxs-lookup"><span data-stu-id="0f662-154">Click **Open** to select the file, click **OK** to save the selection.</span></span> <span data-ttu-id="0f662-155">Die Eigenschaftenseite für das neue Element wird automatisch geöffnet.</span><span class="sxs-lookup"><span data-stu-id="0f662-155">The properties page for the new item opens automatically.</span></span>  
  
6.  <span data-ttu-id="0f662-156">Wählen Sie unter Inhaltstyp die Option **Berichtsdatenquelle**aus, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f662-156">In Content Type, select **Report Data Source**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="0f662-157">Zeigen Sie auf einen Bericht.</span><span class="sxs-lookup"><span data-stu-id="0f662-157">Point to a report.</span></span>  
  
8.  <span data-ttu-id="0f662-158">Klicken Sie auf den Pfeil nach unten, und wählen Sie **Datenquellen verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="0f662-158">Click the down arrow, and select **Manage Data Sources**.</span></span>  
  
9. <span data-ttu-id="0f662-159">KIicken Sie auf den Namen der Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="0f662-159">Click the data source name.</span></span>  
  
10. <span data-ttu-id="0f662-160">Wenn für den Bericht benutzerdefinierte Datenquelleninformationen verwendet werden, klicken Sie auf **Freigegeben**.</span><span class="sxs-lookup"><span data-stu-id="0f662-160">If the report uses custom data source information, click **Shared**.</span></span>  
  
11. <span data-ttu-id="0f662-161">Klicken Sie unter **Datenquellenlink**auf die Schaltfläche zum Durchsuchen ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="0f662-161">In **Data Source Link**, click the browse (**...**) button.</span></span>  
  
12. <span data-ttu-id="0f662-162">Wählen Sie die von Ihnen soeben hochgeladene ODC-Datei aus.</span><span class="sxs-lookup"><span data-stu-id="0f662-162">Select the .odc file you just uploaded.</span></span>  
  
13. <span data-ttu-id="0f662-163">Klicken Sie auf **OK** , um die Datei auszuwählen, und klicken Sie anschließend auf **OK** , um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="0f662-163">Click **OK** to select the file, and then click **OK** to save your changes.</span></span>  
  
     <span data-ttu-id="0f662-164">Wenn Sie versuchen, diese Schritte für die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Beispieldatenbank und -Beispielberichte auszuführen, sollten Sie beachten, dass nur der Bericht Company Sales sofort mit einer ODC-Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="0f662-164">If you are trying these steps with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database and sample reports, be aware that only the Company Sales report will work out-of-the-box with an .odc file.</span></span> <span data-ttu-id="0f662-165">Die anderen Beispielberichte enthalten Abfrageparameter und Funktionen, die den OLE DB-Anbieter nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="0f662-165">The other sample reports contain query parameters and features that do not work with the OLE DB provider.</span></span> <span data-ttu-id="0f662-166">Sie können die Berichte jedoch für den OLE DB-Anbieter aufbereiten, wenn Sie sie zuerst im Berichts-Designer ändern.</span><span class="sxs-lookup"><span data-stu-id="0f662-166">However, you can make the reports work with the OLE DB provider if you modify them first in Report Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f662-167">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0f662-167">See Also</span></span>  
 [<span data-ttu-id="0f662-168">Erstellen, Ändern und Löschen von freigegebenen Datenquellen &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0f662-168">Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;</span></span>](create-modify-and-delete-shared-data-sources-ssrs.md)  
  
  