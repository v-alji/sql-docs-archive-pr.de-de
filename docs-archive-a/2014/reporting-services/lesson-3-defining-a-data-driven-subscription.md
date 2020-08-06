---
title: 'Lektion 3: Definieren eines datengesteuerten Abonnements | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 89197b9b-7502-4fe2-bea3-ed7943eebf3b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d1bbc25bdd08b369180e31378a6d25a595badbcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726581"
---
# <a name="lesson-3-defining-a-data-driven-subscription"></a><span data-ttu-id="511a1-102">Lesson 3: Defining a Data-Driven Subscription</span><span class="sxs-lookup"><span data-stu-id="511a1-102">Lesson 3: Defining a Data-Driven Subscription</span></span>
  <span data-ttu-id="511a1-103">In dieser Lektion verwenden Sie die datengesteuerten Abonnementseiten für folgende Zwecke: um eine Verbindung mit einer Abonnementdatenquelle herzustellen, um eine Abfrage zu erstellen, die Abonnementdaten abruft, und um das Resultset den Berichts- und Übermittlungsoptionen zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="511a1-103">In this lesson, you use the data-driven subscription pages to connect to a subscription data source, build a query that retrieves subscription data, and map the result set to report and delivery options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="511a1-104">Prüfen Sie vor dem Starten, dass der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Agent-Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="511a1-104">Before you start, verify that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service is running.</span></span> <span data-ttu-id="511a1-105">Ist dies nicht der Fall, können Sie das Abonnement nicht speichern.</span><span class="sxs-lookup"><span data-stu-id="511a1-105">If it is not running, you cannot save the subscription.</span></span>  
  
 <span data-ttu-id="511a1-106">In dieser Lektion wird davon ausgegangen, dass Sie Lektion 1 und Lektion 2 abgeschlossen haben und dass die Berichtsdatenquelle gespeicherte Anmeldeinformationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="511a1-106">This lesson assumes you completed Lesson 1 and Lesson 2 and that the report data source uses stored credentials.</span></span>  <span data-ttu-id="511a1-107">Weitere Informationen finden Sie unter [Lektion 2: Ändern der Eigenschaften der Berichtsdatenquelle](../reporting-services/lesson-2-modifying-the-report-data-source-properties.md).</span><span class="sxs-lookup"><span data-stu-id="511a1-107">For more information, see [Lesson 2: Modifying the Report Data Source Properties](../reporting-services/lesson-2-modifying-the-report-data-source-properties.md)</span></span>  
  
 <span data-ttu-id="511a1-108">Inhalte dieses Themas:</span><span class="sxs-lookup"><span data-stu-id="511a1-108">In this topic:</span></span>  
  
-   [<span data-ttu-id="511a1-109">Starten des Assistenten für datengesteuerte Abonnements</span><span class="sxs-lookup"><span data-stu-id="511a1-109">Start the Data-Driven Subscription Wizard</span></span>](#bkmk_startwizard)  
  
-   [<span data-ttu-id="511a1-110">Schritt 1 - Beschreibung definieren</span><span class="sxs-lookup"><span data-stu-id="511a1-110">Step 1 - Define a description</span></span>](#bkmk_definesubscription)  
  
-   [<span data-ttu-id="511a1-111">Schritt 2 - Verbindung mit der Abonnentendatenquelle definieren</span><span class="sxs-lookup"><span data-stu-id="511a1-111">Step 2 - Define a Connection to the Subscriber Data Source</span></span>](#bkmk_defineconnectiontosubscriber)  
  
-   [<span data-ttu-id="511a1-112">Schritt 3 - Abfrage für das Abrufen von Abonnentendaten definieren</span><span class="sxs-lookup"><span data-stu-id="511a1-112">Step 3 - Define a Query to Retrieve Subscriber data</span></span>](#bkmk_definequery)  
  
-   [<span data-ttu-id="511a1-113">Schritt 4 - Übermittlungsoptionen festlegen</span><span class="sxs-lookup"><span data-stu-id="511a1-113">Step 4 - Set Delivery Options</span></span>](#bkmk_set_deliveryoptions)  
  
-   [<span data-ttu-id="511a1-114">Schritt 5 - Parameterwert zum Variieren der Berichtsausgabe konfigurieren</span><span class="sxs-lookup"><span data-stu-id="511a1-114">Step 5 - Configure a Parameter Value to Very Report Output</span></span>](#bkmk_configure_parameter)  
  
-   [<span data-ttu-id="511a1-115">Schritt 6 - Abonnement planen</span><span class="sxs-lookup"><span data-stu-id="511a1-115">Step 6 - To Schedule a Subscription</span></span>](#bkmk_schedule_subscription)  
  
##  <a name="start-the-data-driven-subscription-wizard"></a><a name="bkmk_startwizard"></a><span data-ttu-id="511a1-116">Starten des Assistenten für datengesteuerte Abonnements</span><span class="sxs-lookup"><span data-stu-id="511a1-116">Start the Data-Driven Subscription Wizard</span></span>  
  
1.  <span data-ttu-id="511a1-117">Klicken Sie im Berichts-Manager auf **Home**, und navigieren Sie zum Ordner mit dem Bericht **Sales Orders** .</span><span class="sxs-lookup"><span data-stu-id="511a1-117">In Report Manager, click **Home**, and navigate to the folder containing the **Sales Orders** report.</span></span>  
  
2.  <span data-ttu-id="511a1-118">Klicken Sie im Kontextmenü des Berichts auf **Verwalten**und dann auf die Registerkarte **Abonnements** .</span><span class="sxs-lookup"><span data-stu-id="511a1-118">In the context menu of the report, click **Manage**, and then click the **Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="511a1-119">Klicken Sie auf **Neues datengesteuertes Abonnement**.</span><span class="sxs-lookup"><span data-stu-id="511a1-119">Click **New Data-driven Subscription**.</span></span> <span data-ttu-id="511a1-120">Wenn diese Schaltfläche nicht angezeigt wird, verfügen Sie möglicherweise nicht über Inhalts-Manager-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="511a1-120">If you do not see this button, you do not have Content Manager permissions.</span></span>  
  
##  <a name="step-1---define-a-description"></a><a name="bkmk_definesubscription"></a><span data-ttu-id="511a1-121">Schritt 1: Definieren einer Beschreibung</span><span class="sxs-lookup"><span data-stu-id="511a1-121">Step 1 - Define a description</span></span>  
  
1.  <span data-ttu-id="511a1-122">Geben Sie **Lieferung Verkaufsauftrag** bei Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="511a1-122">Type **Sales Order delivery** in description.</span></span>  
  
2.  <span data-ttu-id="511a1-123">Wählen Sie **Windows-Dateifreigabe** für **Angeben, wie die Empfänger benachrichtigt werden**.</span><span class="sxs-lookup"><span data-stu-id="511a1-123">Select **Windows FileShare** for **Specify how recipients are notified**.</span></span>  
  
3.  <span data-ttu-id="511a1-124">Wählen Sie **Nur für dieses Abonnement angeben**und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="511a1-124">Select **Specify for this subscription only**, and then click **Next**.</span></span>  
  
##  <a name="step-2---define-a-connection-to-the-subscriber-data-source"></a><a name="bkmk_defineconnectiontosubscriber"></a><span data-ttu-id="511a1-125">Schritt 2: Definieren einer Verbindung mit der Abonnentendaten Quelle</span><span class="sxs-lookup"><span data-stu-id="511a1-125">Step 2 - Define a Connection to the Subscriber Data Source</span></span>  
  
1.  <span data-ttu-id="511a1-126">Wählen Sie **Microsoft SQL Server** als Quelldatentyp aus.</span><span class="sxs-lookup"><span data-stu-id="511a1-126">Select **Microsoft SQL Server** as the data source type.</span></span>  
  
2.  <span data-ttu-id="511a1-127">Geben Sie unter Verbindungszeichenfolge die folgende Verbindungszeichenfolge ein:</span><span class="sxs-lookup"><span data-stu-id="511a1-127">In Connection string, type the following connection string:</span></span>  
  
    ```  
    data source=localhost; initial catalog=Subscribers  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="511a1-128">"Abonnenten" ist die Datenbank, die Sie in Lektion 1 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="511a1-128">Subscribers is the database you created in lesson 1.</span></span>  
  
3.  <span data-ttu-id="511a1-129">Klicken Sie auf **Anmeldeinformationen, die sicher im Berichtsserver gespeichert sind**.</span><span class="sxs-lookup"><span data-stu-id="511a1-129">Click **Credentials stored securely in the report server**.</span></span>  
  
4.  <span data-ttu-id="511a1-130">Geben Sie unter **Benutzername** und **Kennwort**Ihren Benutzernamen und Ihr Kennwort für die Domäne ein.</span><span class="sxs-lookup"><span data-stu-id="511a1-130">In **User Name** and **Password**, type your domain user name and password.</span></span> <span data-ttu-id="511a1-131">Geben Sie unter **Benutzername**sowohl die Domäne als auch das Benutzerkonto an.</span><span class="sxs-lookup"><span data-stu-id="511a1-131">Include both the domain and user account when specifying **User Name**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="511a1-132">Die Anmeldeinformationen, die für die Verbindung mit einer Abonnentendatenquelle verwendet werden, werden nicht an [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="511a1-132">Credentials used to connect to a subscriber data source are not passed back to [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="511a1-133">Wenn Sie das Abonnement später ändern, müssen Sie das Kennwort zum Herstellen der Verbindung mit der Datenquelle erneut eingeben.</span><span class="sxs-lookup"><span data-stu-id="511a1-133">If you modify the subscription later, you must retype the password used to connect to the data source.</span></span>  
  
5.  <span data-ttu-id="511a1-134">Wählen Sie **Als Windows-Anmeldeinformationen verwenden, wenn eine Verbindung zur Datenquelle hergestellt wird**aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="511a1-134">Select **Use as windows credentials when connecting to the data source**, and then click **Next**.</span></span>  
  
##  <a name="step-3---define-a-query-to-retrieve-subscriber-data"></a><a name="bkmk_definequery"></a><span data-ttu-id="511a1-135">Schritt 3: Definieren einer Abfrage zum Abrufen von Abonnentendaten</span><span class="sxs-lookup"><span data-stu-id="511a1-135">Step 3 - Define a Query to Retrieve Subscriber data</span></span>  
  
1.  <span data-ttu-id="511a1-136">Geben Sie im Abfragefeld folgende Abfrage ein:</span><span class="sxs-lookup"><span data-stu-id="511a1-136">In the query box, type the following query:</span></span>  
  
    ```  
    Select * from OrderInfo  
    ```  
  
2.  <span data-ttu-id="511a1-137">Geben Sie ein Timeout von 30 Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="511a1-137">Specify a time-out of 30 seconds.</span></span>  
  
3.  <span data-ttu-id="511a1-138">Klicken Sie auf **Überprüfen**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="511a1-138">Click **Validate**, and then click **Next**.</span></span>  
  
##  <a name="step-4---set-delivery-options"></a><a name="bkmk_set_deliveryoptions"></a><span data-ttu-id="511a1-139">Schritt 4: Festlegen von Übermittlungs Optionen</span><span class="sxs-lookup"><span data-stu-id="511a1-139">Step 4 - Set Delivery Options</span></span>  
  
1.  <span data-ttu-id="511a1-140">Wählen Sie für **Dateiname**die Option **Rufen Sie den Wert aus der Datenbank ab**aus.</span><span class="sxs-lookup"><span data-stu-id="511a1-140">For **File name**, select **Get the value from the database**.</span></span> <span data-ttu-id="511a1-141">Wählen Sie das Feld **Reihenfolge**aus.</span><span class="sxs-lookup"><span data-stu-id="511a1-141">Select the field **Order**.</span></span>  
  
2.  <span data-ttu-id="511a1-142">Wählen Sie für **Pfad**die Option **Geben Sie einen statischen Wert an**aus.</span><span class="sxs-lookup"><span data-stu-id="511a1-142">For **Path**, select **Specify a static value**.</span></span> <span data-ttu-id="511a1-143">Geben Sie in "Wert festlegen" den Namen einer öffentlichen Dateifreigabe ein, für die Sie Schreibberechtigungen besitzen (z. B. `\\mycomputer\public\myreports`).</span><span class="sxs-lookup"><span data-stu-id="511a1-143">In Setting Value, type the name of a public file share for which you have write permissions (for example, `\\mycomputer\public\myreports`).</span></span>  
  
3.  <span data-ttu-id="511a1-144">Wählen Sie für **Renderformat**die Option **Rufen Sie den Wert aus der Datenbank ab**aus.</span><span class="sxs-lookup"><span data-stu-id="511a1-144">For **Render Format**, select **Get the value from the database**.</span></span> <span data-ttu-id="511a1-145">Wählen Sie **Format**aus.</span><span class="sxs-lookup"><span data-stu-id="511a1-145">Select **Format**.</span></span>  
  
4.  <span data-ttu-id="511a1-146">Wählen Sie für den **Schreibmodus**die Option **Geben Sie einen statischen Wert an** aus, und wählen Sie **AutoIncrement**aus.</span><span class="sxs-lookup"><span data-stu-id="511a1-146">For **Write mode**, select **Specify a static value** and select **AutoIncrement**.</span></span>  
  
5.  <span data-ttu-id="511a1-147">Wählen Sie für **Dateierweiterung**die Option **Geben Sie einen statischen Wert an** aus, und wählen Sie **True**aus.</span><span class="sxs-lookup"><span data-stu-id="511a1-147">For **File Extension**, select **Specify a static value** and select **True**.</span></span>  
  
6.  <span data-ttu-id="511a1-148">Wählen Sie für **Benutzernamen**die Option **Geben Sie einen statischen Wert an**aus.</span><span class="sxs-lookup"><span data-stu-id="511a1-148">For **User name**, select **Specify a static value**.</span></span> <span data-ttu-id="511a1-149">Geben Sie Ihr Domänenbenutzerkonto an.</span><span class="sxs-lookup"><span data-stu-id="511a1-149">Type your domain user account.</span></span> <span data-ttu-id="511a1-150">Geben Sie ihn in folgendem Format ein: `<domain>\<account>`.</span><span class="sxs-lookup"><span data-stu-id="511a1-150">Enter it in this format: `<domain>\<account>`.</span></span> <span data-ttu-id="511a1-151">Das Benutzerkonto muss über Berechtigungen zum Pfad verfügen, den Sie in den vorherigen Schritten konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="511a1-151">The user account needs to have permissions to the path you configured in the previous steps.</span></span>  
  
7.  <span data-ttu-id="511a1-152">Wählen Sie für **Kennwort**die Option **Geben Sie einen statischen Wert an**aus.</span><span class="sxs-lookup"><span data-stu-id="511a1-152">For **Password**, select **Specify a static value**.</span></span> <span data-ttu-id="511a1-153">Geben Sie Ihr Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="511a1-153">Type your password.</span></span> <span data-ttu-id="511a1-154">Achten Sie darauf, dass Sie das Kennwort richtig eingeben.</span><span class="sxs-lookup"><span data-stu-id="511a1-154">Be sure that you type the password carefully.</span></span> <span data-ttu-id="511a1-155">Das Kennwort wird nicht durch den Assistenten überprüft.</span><span class="sxs-lookup"><span data-stu-id="511a1-155">The wizard does not validate the password.</span></span>  
  
8.  <span data-ttu-id="511a1-156">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="511a1-156">Click **Next.**</span></span>  
  
##  <a name="step-5---configure-a-parameter-value-to-very-report-output"></a><a name="bkmk_configure_parameter"></a><span data-ttu-id="511a1-157">Schritt 5: Konfigurieren eines Parameter Werts, um die Ausgabe zu melden</span><span class="sxs-lookup"><span data-stu-id="511a1-157">Step 5 - Configure a Parameter Value to Very Report Output</span></span>  
  
1.  <span data-ttu-id="511a1-158">Wählen Sie für **OrderNumber**die Option **Rufen Sie den Wert aus der Datenbank ab**aus.</span><span class="sxs-lookup"><span data-stu-id="511a1-158">For **OrderNumber**, select **Get the value from the database**.</span></span> <span data-ttu-id="511a1-159">Wählen Sie in "Wert" die Option **Reihenfolge**aus.</span><span class="sxs-lookup"><span data-stu-id="511a1-159">In Value, select **Order**.</span></span> <span data-ttu-id="511a1-160">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="511a1-160">Click **Next.**</span></span>  
  
##  <a name="step-6---to-schedule-a-subscription"></a><a name="bkmk_schedule_subscription"></a><span data-ttu-id="511a1-161">Schritt 6: Planen eines Abonnements</span><span class="sxs-lookup"><span data-stu-id="511a1-161">Step 6 - To Schedule a Subscription</span></span>  
  
1.  <span data-ttu-id="511a1-162">Klicken Sie auf **Nach einem Zeitplan, der für dieses Abonnement erstellt wurde**und dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="511a1-162">Click **On a schedule created for this subscription**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="511a1-163">Klicken Sie in **Zeitplandetails**auf **Einmal**.</span><span class="sxs-lookup"><span data-stu-id="511a1-163">In **Schedule Details**, click **Once**.</span></span>  
  
3.  <span data-ttu-id="511a1-164">Geben Sie eine Startzeit an, die ein paar Minuten nach der aktuellen Zeit liegt.</span><span class="sxs-lookup"><span data-stu-id="511a1-164">Specify a start time that is a few minutes ahead of the current time.</span></span>  
  
4.  <span data-ttu-id="511a1-165">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="511a1-165">Click **Finish**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="511a1-166">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="511a1-166">Next Steps</span></span>  
 <span data-ttu-id="511a1-167">Beim Ausführen des Abonnements werden vier Berichtsdateien an die von Ihnen angegebene Dateifreigabe übermittelt, eine für jeden Auftrag in der *Abonnenten* -Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="511a1-167">When the subscription runs, four report files will be delivered to the file share you specified, one for each order in the *Subscribers* data source.</span></span> <span data-ttu-id="511a1-168">Jede Übermittlung muss im Hinblick auf die Daten (sie müssen sich auf einen bestimmten Auftrag beziehen), das Renderingformat und das Dateiformat eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="511a1-168">Each delivery should be unique in terms of data (the data should be order-specific), rendering format, and file format.</span></span> <span data-ttu-id="511a1-169">Sie können jeden Bericht von dem freigegebenen Ordner aus öffnen, um sicherzustellen, dass jede Version entsprechend den von Ihnen festgelegten Abonnementoptionen angepasst wurde.</span><span class="sxs-lookup"><span data-stu-id="511a1-169">You can open each report from the shared folder to verify that each version is customized based on the subscription options you defined.</span></span>  
  
 <span data-ttu-id="511a1-170">![Liste der vom Abonnement erstellten Dateien](../../2014/tutorials/media/ssrs-tutorial-datadriven-subscription-filelist.gif "Liste der vom Abonnement erstellten Dateien")</span><span class="sxs-lookup"><span data-stu-id="511a1-170">![List of files created by the subscription](../../2014/tutorials/media/ssrs-tutorial-datadriven-subscription-filelist.gif "List of files created by the subscription")</span></span>  
  
 <span data-ttu-id="511a1-171">Die Abonnementseite im Berichts-Manager enthält das **Letzte Ausführungsdatum** und den **Status** des Abonnements.</span><span class="sxs-lookup"><span data-stu-id="511a1-171">The subscription page in Report Manager will contain the **Last Run** date and **Status** of the subscription.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="511a1-172">Aktualisieren Sie die Seite, nachdem das Abonnement ausgeführt wurde, um die aktualisierten Informationen zu sehen.</span><span class="sxs-lookup"><span data-stu-id="511a1-172">Refresh the page after the subscription runs to see the updated information.</span></span>  
  
 <span data-ttu-id="511a1-173">![Abonnementergebnisse im Berichts-Manager](../../2014/tutorials/media/ssrs-tutorial-datadriven-subscription-status-reportmanager.gif "Abonnementergebnisse im Berichts-Manager")</span><span class="sxs-lookup"><span data-stu-id="511a1-173">![Subscription results in Report Manager](../../2014/tutorials/media/ssrs-tutorial-datadriven-subscription-status-reportmanager.gif "Subscription results in Report Manager")</span></span>  
  
 <span data-ttu-id="511a1-174">Dies ist der letzte Schritt im Lernprogramm "Definieren eines datengesteuerten Abonnements".</span><span class="sxs-lookup"><span data-stu-id="511a1-174">This step concludes the tutorial "Defining a Data-Driven Subscription".</span></span> <span data-ttu-id="511a1-175">Weitere Informationen zu anderen [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Tutorials finden Sie unter [Reporting Services Tutorials &#40;SSRS&#41;](../reporting-services/reporting-services-tutorials-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="511a1-175">To learn more about other [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] tutorials, see [Reporting Services Tutorials &#40;SSRS&#41;](../reporting-services/reporting-services-tutorials-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="511a1-176">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="511a1-176">See Also</span></span>  
 <span data-ttu-id="511a1-177">[Erstellen eines datengesteuerten Abonnements &#40;SSRS-Tutorial&#41;](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="511a1-177">[Create a Data-Driven Subscription &#40;SSRS Tutorial&#41;](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md) </span></span>  
 <span data-ttu-id="511a1-178">[Abonnements und Übermittlung &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="511a1-178">[Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md) </span></span>  
 <span data-ttu-id="511a1-179">[Data-Driven Subscriptions](subscriptions/data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="511a1-179">[Data-Driven Subscriptions](subscriptions/data-driven-subscriptions.md) </span></span>  
 <span data-ttu-id="511a1-180">[Erstellen, ändern und Löschen eines datengesteuerten Abonnements](subscriptions/create-modify-and-delete-data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="511a1-180">[Create, Modify, and Delete a Data-Driven Subscription](subscriptions/create-modify-and-delete-data-driven-subscriptions.md) </span></span>  
 [<span data-ttu-id="511a1-181">Verwenden einer externen Datenquelle für Abonnentendaten &#40;datengesteuertes Abonnement&#41;</span><span class="sxs-lookup"><span data-stu-id="511a1-181">Use an External Data Source for Subscriber Data &#40;Data-Driven Subscription&#41;</span></span>](subscriptions/use-an-external-data-source-for-subscriber-data-data-driven-subscription.md)  
  
  
