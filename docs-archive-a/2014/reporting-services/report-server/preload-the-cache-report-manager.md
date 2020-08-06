---
title: Vorabladen des Caches (Berichts-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- cache [Reporting Services]
- preloading cache
ms.assetid: 152a1051-8aa5-4c01-bc85-f8be8971b0cd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b60b74f7ab5c0c843b848c09ee574fd59a99c682
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700797"
---
# <a name="preload-the-cache-report-manager"></a><span data-ttu-id="a304b-102">Vorabladen des Caches (Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="a304b-102">Preload the Cache (Report Manager)</span></span>
  <span data-ttu-id="a304b-103">Sie können den Cache für ein freigegebenes Dataset vorab laden, indem Sie einen Cacheaktualisierungsplan für das freigegebene Dataset erstellen.</span><span class="sxs-lookup"><span data-stu-id="a304b-103">You can preload the cache for a shared dataset by creating a cache refresh plan for the shared dataset.</span></span>  
  
 <span data-ttu-id="a304b-104">Sie können den Cache für einen Bericht in die zwei Weisen vorab laden:</span><span class="sxs-lookup"><span data-stu-id="a304b-104">You can preload the cache for a report in two ways:</span></span>  
  
1.  <span data-ttu-id="a304b-105">Erstellen Sie einen Cacheaktualisierungsplan für den Bericht.</span><span class="sxs-lookup"><span data-stu-id="a304b-105">Create a cache refresh plan for the report.</span></span> <span data-ttu-id="a304b-106">Dies ist die bevorzugte Methode.</span><span class="sxs-lookup"><span data-stu-id="a304b-106">This is the preferred method.</span></span>  
  
2.  <span data-ttu-id="a304b-107">Verwenden Sie ein datengesteuertes Abonnement zum Vorabladen des Caches mit Instanzen parametrisierter Berichte.</span><span class="sxs-lookup"><span data-stu-id="a304b-107">Use a data-driven subscription to preload the cache with instances of parameterized reports.</span></span> <span data-ttu-id="a304b-108">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Versionen vor [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]bestand darin die einzige Möglichkeit, den Cache vorab zu laden.</span><span class="sxs-lookup"><span data-stu-id="a304b-108">This was the only way to preload the cache in versions of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] earlier than [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="a304b-109">Weitere Informationen finden Sie unter [Zwischenspeichern von Berichten &#40;SSRS&#41;](caching-reports-ssrs.md)bestand darin die einzige Möglichkeit, den Cache vorab zu laden.</span><span class="sxs-lookup"><span data-stu-id="a304b-109">For more information, see [Caching Reports &#40;SSRS&#41;](caching-reports-ssrs.md).</span></span>  
  
 <span data-ttu-id="a304b-110">Die folgenden Bedingungen müssen erfüllt sein, bevor Sie einen Bericht oder ein freigegebenes Dataset zwischenspeichern können:</span><span class="sxs-lookup"><span data-stu-id="a304b-110">The following conditions must be met before you can cache a report or a shared dataset:</span></span>  
  
-   <span data-ttu-id="a304b-111">Für das freigegebene Dataset oder den Bericht muss die Zwischenspeicherung aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="a304b-111">The shared dataset or the report must have caching enabled.</span></span>  
  
-   <span data-ttu-id="a304b-112">Die freigegebenen Datenquellen für das freigegebene Dataset oder den Bericht müssen für die Verwendung gespeicherter Anmeldeinformationen oder keiner Anmeldeinformationen konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="a304b-112">The shared data sources for the shared dataset or the report must be configured to use stored credentials or no credentials.</span></span>  
  
-   <span data-ttu-id="a304b-113">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst muss ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a304b-113">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service must be running.</span></span>  
  
### <a name="to-preload-the-cache-by-creating-a-cache-refresh-plan"></a><span data-ttu-id="a304b-114">So laden Sie den Cache vorab, indem Sie einen Cacheaktualisierungsplan erstellen</span><span class="sxs-lookup"><span data-stu-id="a304b-114">To preload the cache by creating a cache refresh plan</span></span>  
  
1.  <span data-ttu-id="a304b-115">Starten Sie den [Berichts-Manager &#40;einheitlicher SSRS-Modus&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="a304b-115">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="a304b-116">Navigieren Sie im Berichts-Manager zur Seite **Inhalt** und dann zu dem Element, das zwischengespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="a304b-116">In Report Manager, navigate to the **Contents** page, and then navigate to the item that you want to cache.</span></span>  
  
3.  <span data-ttu-id="a304b-117">Zeigen Sie auf das Element, und klicken Sie auf die Dropdownliste und anschließend auf **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="a304b-117">Hover over the item, click the drop-down list, and then click **Manage**.</span></span>  
  
4.  <span data-ttu-id="a304b-118">Klicken Sie auf die Registerkarte **Optionen zur Cacheaktualisierung** .</span><span class="sxs-lookup"><span data-stu-id="a304b-118">Click the **Cache Refresh Options** tab.</span></span>  
  
5.  <span data-ttu-id="a304b-119">Klicken Sie auf der Symbolleiste auf **Neuer Cacheaktualisierungsplan**.</span><span class="sxs-lookup"><span data-stu-id="a304b-119">On the toolbar, click **New Cache Refresh Plan**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a304b-120">Wenn für das Element keine Zwischenspeicherung aktiviert ist, werden Sie aufgefordert, das Zwischenspeichern zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a304b-120">If the item does not have caching enabled, you will be prompted to enable caching.</span></span> <span data-ttu-id="a304b-121">Um das Zwischenspeichern zu aktivieren, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a304b-121">To enable caching, click **OK**.</span></span>  
  
     <span data-ttu-id="a304b-122">Die Seite Cacheaktualisierungsplan wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a304b-122">The Cache Refresh Plan page opens.</span></span>  
  
6.  <span data-ttu-id="a304b-123">Geben Sie optional eine Beschreibung für den Aktualisierungsplan ein.</span><span class="sxs-lookup"><span data-stu-id="a304b-123">Optionally type a description for the refresh plan.</span></span>  
  
7.  <span data-ttu-id="a304b-124">Klicken Sie für einen freigegebenen Zeitplan auf **Freigegebener Zeitplan**, und wählen Sie dann den Namen des zu verwendenden Zeitplans aus.</span><span class="sxs-lookup"><span data-stu-id="a304b-124">For a shared schedule, click **Shared schedule**, and then select the name of the schedule to use.</span></span>  
  
     <span data-ttu-id="a304b-125">Klicken Sie für einen benutzerdefinierten Zeitplan auf **Elementspezifischer Zeitplan**und anschließend auf **Konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="a304b-125">For a custom schedule, click **Item-specific schedule**, and then click **Configure**.</span></span>  
  
8.  <span data-ttu-id="a304b-126">Konfigurieren des Zeitplans</span><span class="sxs-lookup"><span data-stu-id="a304b-126">Configure the schedule</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-preload-the-cache-with-a-user-specific-report-by-using-a-data-driven-subscription"></a><span data-ttu-id="a304b-127">So laden Sie den Cache mit einem benutzerspezifischen Bericht vorab, indem Sie ein datengesteuertes Abonnement verwenden</span><span class="sxs-lookup"><span data-stu-id="a304b-127">To preload the cache with a user-specific report by using a data-driven subscription</span></span>  
  
1.  <span data-ttu-id="a304b-128">Starten Sie den [Berichts-Manager &#40;einheitlicher SSRS-Modus&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="a304b-128">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="a304b-129">Navigieren Sie im Berichts-Manager zur Seite **Inhalt** und dann zum Bericht, für den Sie ein Abonnement erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="a304b-129">In Report Manager, navigate to the **Contents** page, and then navigate to the report you want to create a subscription for.</span></span>  
  
3.  <span data-ttu-id="a304b-130">Klicken Sie auf den Bericht und auf die Registerkarte **Abonnements** , und klicken Sie anschließend auf **Neues datengesteuertes Abonnement**.</span><span class="sxs-lookup"><span data-stu-id="a304b-130">Click the report, click the **Subscriptions** tab, and then click **New Data-Driven Subscription**.</span></span>  
  
4.  <span data-ttu-id="a304b-131">Optional geben Sie eine Beschreibung für das Abonnement ein.</span><span class="sxs-lookup"><span data-stu-id="a304b-131">Optionally type a description for the subscription.</span></span>  
  
5.  <span data-ttu-id="a304b-132">Wählen Sie in der Liste **Geben Sie an, wie Empfänger benachrichtigt werden** die Option **NULL-Übermittlungsanbieter**.</span><span class="sxs-lookup"><span data-stu-id="a304b-132">From the **Specify how recipients are notified** list, select **Null Delivery Provider**.</span></span>  
  
6.  <span data-ttu-id="a304b-133">Geben Sie einen Datenquellentyp an, und klicken Sie auf **Weiter** , um die Datenquelle zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a304b-133">Specify a data source type and then click **Next** to configure the data source.</span></span>  
  
7.  <span data-ttu-id="a304b-134">Geben Sie den Verbindungstyp, die Verbindungszeichenfolge und die Anmeldeinformationen für den Zugriff auf die Datenquelle mit Abonnentendaten an.</span><span class="sxs-lookup"><span data-stu-id="a304b-134">Specify the connection type, connection string, and credentials for accessing the data source that contains subscriber data.</span></span> <span data-ttu-id="a304b-135">Im folgenden Beispiel wird eine Verbindungszeichenfolge erläutert, die für die Verbindung zur Subscribers-Datenbank von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="a304b-135">The following example illustrates a connection string used to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database called Subscribers:</span></span>  
  
    ```  
    data source=<servername>; initial catalog=Subscribers  
    ```  
  
8.  <span data-ttu-id="a304b-136">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a304b-136">Click **Next**.</span></span>  
  
9. <span data-ttu-id="a304b-137">Geben Sie die Abfrage oder den Befehl an, die bzw. der Abonnentendaten abruft.</span><span class="sxs-lookup"><span data-stu-id="a304b-137">Specify the query or command that retrieves subscriber data.</span></span> <span data-ttu-id="a304b-138">Sie können auch den Timeoutzeitraum für Abfragen erhöhen, deren Verarbeitung lange dauert.</span><span class="sxs-lookup"><span data-stu-id="a304b-138">Optionally increase the time-out period for queries that take a long time to process.</span></span> <span data-ttu-id="a304b-139">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a304b-139">For example:</span></span>  
  
    ```  
    Select * from UserInfo  
    ```  
  
10. <span data-ttu-id="a304b-140">Klicken Sie auf **Überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="a304b-140">Click **Validate**.</span></span> <span data-ttu-id="a304b-141">Die Abfrage muss überprüft werden, bevor der Vorgang fortgesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a304b-141">The query must be validated before you continue.</span></span> <span data-ttu-id="a304b-142">Wenn die Meldung **Die Abfrage wurde erfolgreich überprüft** angezeigt wird, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a304b-142">When the **Query validated successfully** message appears, click **Next**.</span></span>  
  
11. <span data-ttu-id="a304b-143">Da für den NULL-Übermittlungsanbieter keine Einstellungen für die Übermittlungserweiterung konfiguriert werden können, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a304b-143">Because you cannot configure delivery extension settings for the null delivery provider, click **Next**.</span></span>  
  
12. <span data-ttu-id="a304b-144">Geben Sie Berichtsparameterwerte für das Abonnement an, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a304b-144">Specify report parameter values for the subscription, and click **Next**.</span></span>  
  
13. <span data-ttu-id="a304b-145">Geben Sie an, wann das Abonnement verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="a304b-145">Specify when the subscription is processed.</span></span> <span data-ttu-id="a304b-146">Wählen Sie nicht **Wenn die Berichtsdaten auf dem Berichtsserver aktualisiert werden**.</span><span class="sxs-lookup"><span data-stu-id="a304b-146">Do not choose **When the report data is updated on the report server**.</span></span> <span data-ttu-id="a304b-147">Diese Option ist nur für Berichtsmomentaufnahmen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a304b-147">That setting is for snapshots only.</span></span> <span data-ttu-id="a304b-148">Wenn Sie einen vorhandenen Zeitplan verwenden möchten, wählen Sie **Nach einem freigegebenen Zeitplan**.</span><span class="sxs-lookup"><span data-stu-id="a304b-148">If want to use a pre-existing schedule, select **On a shared schedule**.</span></span>  
  
     <span data-ttu-id="a304b-149">Oder klicken Sie zum Erstellen eines benutzerdefinierten Zeitplans auf **Nach einem Zeitplan, der für dieses Abonnement erstellt wurde** , und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a304b-149">Or, to create a custom schedule, click **On a schedule created for this subscription** and then click **Next**.</span></span> <span data-ttu-id="a304b-150">Konfigurieren Sie den Zeitplan, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="a304b-150">Configure the schedule and then click **Finish**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a304b-151">Die Abonnenten empfangen nur dann den neuesten Bericht, wenn der von Ihnen konfigurierte Zeitplan konsistent mit dem Zeitplan für die Berichtsübermittlung ist, den Sie für die Abonnenten definiert haben.</span><span class="sxs-lookup"><span data-stu-id="a304b-151">In order for the subscribers to receive the newest report, the schedule that you configure should be consistent with the report delivery schedule that you have defined for the subscribers.</span></span> <span data-ttu-id="a304b-152">Weitere Informationen finden Sie unter [Berichts-Manager (einheitlicher SSRS-Modus)](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="a304b-152">For more information, see [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
14. <span data-ttu-id="a304b-153">Konfigurieren Sie die Ausführungsoptionen für den Bericht wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a304b-153">Configure the Execution options for the report as follows.</span></span> <span data-ttu-id="a304b-154">Klicken Sie auf der Berichtsseite auf die Registerkarte **Eigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="a304b-154">On the report page, click the **Properties** tab.</span></span>  
  
15. <span data-ttu-id="a304b-155">Klicken Sie im linken Bereich auf die Registerkarte **Ausführung** .</span><span class="sxs-lookup"><span data-stu-id="a304b-155">In the left frame, click the **Execution** tab.</span></span>  
  
16. <span data-ttu-id="a304b-156">Wählen Sie auf der Seite die Option **Diesen Bericht mit den neuesten Daten rendern**.</span><span class="sxs-lookup"><span data-stu-id="a304b-156">On the page, select **Render this report with the most recent data**.</span></span>  
  
17. <span data-ttu-id="a304b-157">Wählen Sie eine der folgenden zwei Cacheoptionen aus, und konfigurieren Sie die Ablaufzeit wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a304b-157">Choose one of the following two cache options and configure the expiration as follows:</span></span>  
  
    -   <span data-ttu-id="a304b-158">Wenn die zwischengespeicherte Kopie nach einem bestimmten Zeitraum ablaufen soll, klicken Sie auf **Eine temporäre Kopie des Berichts zwischenspeichern. Diese Kopie soll nach der folgenden Anzahl von Minuten ablaufen.**</span><span class="sxs-lookup"><span data-stu-id="a304b-158">To make the cached copy expire after a particular time period, click **Cache a temporary copy of the report. Expire copy of report after a number of minutes.**</span></span> <span data-ttu-id="a304b-159">Geben Sie die Anzahl von Minuten für den Berichtsablauf ein.</span><span class="sxs-lookup"><span data-stu-id="a304b-159">Type the number of minutes for report expiration.</span></span>  
  
    -   <span data-ttu-id="a304b-160">Wenn die zwischengespeicherte Kopie nach einem Zeitplan ablaufen soll, klicken Sie auf **Eine temporäre Kopie des Berichts zwischenspeichern. Diese Kopie soll gemäß dem folgenden Zeitplan ablaufen.**</span><span class="sxs-lookup"><span data-stu-id="a304b-160">To make the cached copy expire on a schedule, click **Cache a temporary copy of the report. Expire copy of report on the following schedule.**</span></span> <span data-ttu-id="a304b-161">Klicken Sie auf **Konfigurieren**, oder wählen Sie einen freigegebenen Zeitplan aus, um einen Zeitplan für den Berichtsablauf festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a304b-161">Click **Configure**, or select a shared schedule to set a schedule for report expiration.</span></span>  
  
18. <span data-ttu-id="a304b-162">Klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="a304b-162">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a304b-163">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a304b-163">See Also</span></span>  
 <span data-ttu-id="a304b-164">[Data-Driven Subscriptions](../subscriptions/data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="a304b-164">[Data-Driven Subscriptions](../subscriptions/data-driven-subscriptions.md) </span></span>  
 <span data-ttu-id="a304b-165">[Erstellen eines datengesteuerten Abonnements &#40;SSRS-Tutorial&#41;](../create-a-data-driven-subscription-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="a304b-165">[Create a Data-Driven Subscription &#40;SSRS Tutorial&#41;](../create-a-data-driven-subscription-ssrs-tutorial.md) </span></span>  
 <span data-ttu-id="a304b-166">[Leistung, Momentaufnahmen, Zwischenspeichern &#40;Reporting Services&#41;](performance-snapshots-caching-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="a304b-166">[Performance, Snapshots, Caching &#40;Reporting Services&#41;](performance-snapshots-caching-reporting-services.md) </span></span>  
 <span data-ttu-id="a304b-167">[Festlegen von Berichts Verarbeitungseigenschaften](set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="a304b-167">[Set Report Processing Properties](set-report-processing-properties.md) </span></span>  
 [<span data-ttu-id="a304b-168">Zwischenspeichern von Berichten &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a304b-168">Caching Reports &#40;SSRS&#41;</span></span>](caching-reports-ssrs.md)  
  
  
