---
title: Ändern der Standardübermittlungserweiterung für Reporting Services | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Report Manager [Reporting Services], default delivery extension
ms.assetid: 5f6fee72-01bf-4f6c-85d2-7863c46c136b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cc1b3af2a4fe3038b761d0b48030062da06d354e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719417"
---
# <a name="change-the-default-reporting-services-delivery-extension"></a><span data-ttu-id="8431e-102">Ändern der Standardübermittlungserweiterung für Reporting Services</span><span class="sxs-lookup"><span data-stu-id="8431e-102">Change the Default Reporting Services Delivery Extension</span></span>
  <span data-ttu-id="8431e-103">Sie können [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] -Konfigurationseinstellungen ändern, um die Standardübermittlungserweiterung in der Liste **Übermittelt von** einer Abonnementdefinitionsseite zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8431e-103">You can modify [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] configuration settings to change the default delivery extension that appears in the **Delivered by** list of a subscription definition page.</span></span> <span data-ttu-id="8431e-104">Sie können die Konfiguration z. B. so ändern, dass beim Erstellen eines neuen Abonnements durch den Benutzer standardmäßig eine Dateifreigabeübermittlung statt einer E-Mail-Übermittlung ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="8431e-104">For example you can modify the configuration so that when users create a new subscription, file share delivery is selected by default instead of e-mail delivery.</span></span> <span data-ttu-id="8431e-105">Sie können auch die Reihenfolge der in der Benutzeroberfläche aufgeführten Übermittlungserweiterungen ändern.</span><span class="sxs-lookup"><span data-stu-id="8431e-105">You can also change the order the delivery extensions are listed in the user interface.</span></span>

 <span data-ttu-id="8431e-106">**[!INCLUDE[applies](../../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Einheitlicher Modus | [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="8431e-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Native mode | [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>

 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="8431e-107">enthält E-Mail- und Windows-Dateifreigabe-Übermittlungserweiterungen.</span><span class="sxs-lookup"><span data-stu-id="8431e-107">includes E-mail and Windows File Share delivery are extensions.</span></span> <span data-ttu-id="8431e-108">Ihr Berichtsserver verfügt möglicherweise über zusätzliche Übermittlungserweiterungen, wenn Sie benutzerdefinierte Erweiterungen oder Drittanbietererweiterungen zur Unterstützung der benutzerdefinierten Übermittlung bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="8431e-108">Your report server might have additional delivery extensions if you have deployed custom or third-party extensions to support custom delivery.</span></span> <span data-ttu-id="8431e-109">Die Verfügbarkeit einer Übermittlungserweiterung hängt davon ab, ob sie auf einem Berichtsserver bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="8431e-109">The availability of a delivery extension depends on whether it is deployed on a report server.</span></span>

## <a name="default-native-mode-report-server-configuration"></a><span data-ttu-id="8431e-110">Standardkonfiguration für einen Berichtsserver im einheitlichen Modus</span><span class="sxs-lookup"><span data-stu-id="8431e-110">Default Native mode report server configuration</span></span>
 <span data-ttu-id="8431e-111">Die Reihenfolge der Übermittlungserweiterungen im Berichts-Manager in der Liste **Übermittelt von** basiert auf der Reihenfolge der Übermittlungserweiterungseinträge in der Datei **RSReportServer.config** .</span><span class="sxs-lookup"><span data-stu-id="8431e-111">The order of a delivery extension appears in Report Manager in the **Delivered by** list is based on the order of the delivery extension entries in the **RSReportServer.config** file.</span></span> <span data-ttu-id="8431e-112">Im folgenden Bild wird E-Mail zuerst in der Liste angezeigt und ist standardmäßig ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="8431e-112">For example the following image shows e-mail first in the list and it is selected by default.</span></span>

 <span data-ttu-id="8431e-113">![Standardliste der Übermittlungserweiterungen](../media/ssrs-default-delivery.png "Standardliste der Übermittlungserweiterungen")</span><span class="sxs-lookup"><span data-stu-id="8431e-113">![default list of delivery extensions](../media/ssrs-default-delivery.png "default list of delivery extensions")</span></span>

 <span data-ttu-id="8431e-114">Im Folgenden ist der Standardabschnitt von **RSReportServer.config** dargestellt, der die Standardübermittlungserweiterung und die Reihenfolge steuert, in der diese im Berichts-Manager angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8431e-114">The following is the default section of **RSReportServer.config** that controls the default delivery extension and the order they are displayed in Report Manager.</span></span> <span data-ttu-id="8431e-115">Beachten Sie, dass die E-Mail in der Datei zuerst angezeigt und als Standard festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="8431e-115">Note that email appears first in the file and it is set as the default.</span></span>

```xml
<DeliveryUI>
     <Extension Name="Report Server Email" Type="Microsoft.ReportingServices.EmailDeliveryProvider.EmailDeliveryProviderControl,ReportingServicesEmailDeliveryProvider">
          <DefaultDeliveryExtension>True</DefaultDeliveryExtension>
               <Configuration>
               <RSEmailDPConfiguration>
                    <DefaultRenderingExtension>MHTML</DefaultRenderingExtension>
               </RSEmailDPConfiguration>
               </Configuration>
     </Extension>
     <Extension Name="Report Server FileShare" Type="Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl,ReportingServicesFileShareDeliveryProvider"/>
</DeliveryUI>
```

#### <a name="configure-file-share-delivery-as-the-default-delivery-extension-in-report-manager"></a><span data-ttu-id="8431e-116">Konfigurieren der Dateifreigabeübermittlung als Standardübermittlungserweiterung im Berichts-Manager</span><span class="sxs-lookup"><span data-stu-id="8431e-116">Configure File Share Delivery as the default delivery extension in Report Manager</span></span>

1.  <span data-ttu-id="8431e-117">Mit den Schritten in diesem Verfahren können Sie die Konfiguration so ändern, dass die Dateifreigabe-Übermittlung als erste Option in der Benutzeroberfläche aufgeführt wird und Standardauswahl ist.</span><span class="sxs-lookup"><span data-stu-id="8431e-117">The steps in this procedure modify the configuration so that file share delivery is listed as the first option in the UI and it is the default selection.</span></span>

     <span data-ttu-id="8431e-118">Öffnen Sie die Datei RSReportServer.config in einem Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="8431e-118">Open the RSReportServer.config file in a text editor.</span></span> <span data-ttu-id="8431e-119">Weitere Informationen zur Konfigurationsdatei finden Sie unter [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="8431e-119">For more information on the configuration file, see [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span></span> <span data-ttu-id="8431e-120">Nach Änderung der Konfiguration sieht die Benutzeroberfläche wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="8431e-120">After the configuration changes, the UI will look like the following image:</span></span>

     <span data-ttu-id="8431e-121">![Geänderte Liste der Übermittlungserweiterungen](../media/ssrs-modified-delivery.png "Geänderte Liste der Übermittlungserweiterungen")</span><span class="sxs-lookup"><span data-stu-id="8431e-121">![modified list of delivery extensions](../media/ssrs-modified-delivery.png "modified list of delivery extensions")</span></span>

2.  <span data-ttu-id="8431e-122">Ändern Sie den Abschnitt DeliveryUI wie folgt und beachten Sie die wichtigsten Änderungen:</span><span class="sxs-lookup"><span data-stu-id="8431e-122">Modify the DeliveryUI section to look like the following sample and note the key changes of:</span></span>

    1.  <span data-ttu-id="8431e-123">Die FileShare-Erweiterung befindet sich vor der E-Mail-Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="8431e-123">The FileShare extension is before the email extension.</span></span> <span data-ttu-id="8431e-124">Dadurch wird die Reihenfolge geändert, in der die Erweiterungen im Berichts-Manager aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="8431e-124">This will change the order the extensions are listed in Report Manager.</span></span>

    2.  <span data-ttu-id="8431e-125">Die Dateifreigabeerweiterung enthält das DefaultExtension-Tag `<DefaultDeliveryExtension>True</DefaultDeliveryExtension>` , und das Extension-Tag wurde hinzugefügt `</Extension>`.</span><span class="sxs-lookup"><span data-stu-id="8431e-125">The File share extension contains DefaultExtension tag `<DefaultDeliveryExtension>True</DefaultDeliveryExtension>` and the extension end tag was added `</Extension>`.</span></span>

    3.  <span data-ttu-id="8431e-126">Die E-Mail-Erweiterung ist nicht mehr als Standard konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="8431e-126">The email extension is no longer configured as the default.</span></span> `<DefaultDeliveryExtension>False</DefaultDeliveryExtension>`

    ```
    <DeliveryUI>
         <Extension Name="Report Server FileShare" Type="Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl,ReportingServicesFileShareDeliveryProvider">
              <DefaultDeliveryExtension>True</DefaultDeliveryExtension>
         </Extension>
         <Extension Name="Report Server Email" Type="Microsoft.ReportingServices.EmailDeliveryProvider.EmailDeliveryProviderControl,ReportingServicesEmailDeliveryProvider">
         <DefaultDeliveryExtension>False</DefaultDeliveryExtension>
         <Configuration>
              <RSEmailDPConfiguration>
                   <DefaultRenderingExtension>MHTML</DefaultRenderingExtension>
              </RSEmailDPConfiguration>
         </Configuration>
         </Extension>
    </DeliveryUI>
    ```

3.  <span data-ttu-id="8431e-127">Speichern Sie die Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="8431e-127">Save the configuration file.</span></span>

4.  <span data-ttu-id="8431e-128">Innerhalb weniger Minuten wird der Berichtsserver die Konfigurationsdatei laden und die neuen Einstellungen übernehmen.</span><span class="sxs-lookup"><span data-stu-id="8431e-128">Within a few minutes the report server will reload the configuration file and the new settings will take effect.</span></span> <span data-ttu-id="8431e-129">Sie können den Berichtsserverdienst neu starten, um das Laden der Konfigurationsdatei zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="8431e-129">You can restart the report server service to force the loading of the configuration file.</span></span>

     <span data-ttu-id="8431e-130">Das folgende Ereignis wird beim Lesen der Konfiguration im Windows-Ereignisprotokoll geschrieben.</span><span class="sxs-lookup"><span data-stu-id="8431e-130">The following event is written to the windows event log when the configuration is read.</span></span>

     <span data-ttu-id="8431e-131">**Ereignis-ID:** 109</span><span class="sxs-lookup"><span data-stu-id="8431e-131">**Event ID:** 109</span></span>

     <span data-ttu-id="8431e-132">**Quelle:** Berichtsserver-Windows-Dienst (Instanzname)</span><span class="sxs-lookup"><span data-stu-id="8431e-132">**Source:** Report Server Windows Service (instance name)</span></span>

     <span data-ttu-id="8431e-133">Die Datei „RSReportServer.config“ wurde geändert.</span><span class="sxs-lookup"><span data-stu-id="8431e-133">The RSReportServer.config file has been modified</span></span>

## <a name="sharepoint-mode-report-servers"></a><span data-ttu-id="8431e-134">Berichtsserver im SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="8431e-134">SharePoint mode report servers</span></span>
 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="8431e-135">SharePoint-Modus speichert Erweiterungsinformationen in den SharePoint-Dienstanwendungsdatenbanken, und nicht in der Datei „RsrReportServer.config“.</span><span class="sxs-lookup"><span data-stu-id="8431e-135">SharePoint mode stores extensions information in the SharePoint service application databases and not in the RsrReportServer.config file.</span></span> <span data-ttu-id="8431e-136">Im SharePoint-Modus wird die Konfiguration für die Übermittlungserweiterung mit PowerShell geändert.</span><span class="sxs-lookup"><span data-stu-id="8431e-136">In SharePoint mode, delivery extension configuration is modified using PowerShell.</span></span>

#### <a name="configure-the-default-delivery-extension"></a><span data-ttu-id="8431e-137">Konfigurieren der Standardübermittlungserweiterung</span><span class="sxs-lookup"><span data-stu-id="8431e-137">Configure the default delivery extension</span></span>

1.  <span data-ttu-id="8431e-138">Öffnen Sie die **SharePoint-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="8431e-138">Open the **SharePoint Management Shell**.</span></span>

2.  <span data-ttu-id="8431e-139">Sie können diesen Schritt überspringen, wenn Sie den Namen Ihrer [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] -Dienstanwendung bereits kennen.</span><span class="sxs-lookup"><span data-stu-id="8431e-139">You can skip this step if you already know the name of your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="8431e-140">Verwenden Sie den folgende PowerShell-Befehl zum Auflisten der [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] -Dienstanwendungen in der SharePoint-Farm.</span><span class="sxs-lookup"><span data-stu-id="8431e-140">Use the following PowerShell to list the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service applications in your SharePoint farm.</span></span>

    ```powershell
    Get-SPRSServiceApplication | Format-List *
    ```

3.  <span data-ttu-id="8431e-141">Führen Sie den folgenden PowerShell-Befehl zum Überprüfen der aktuellen Standardübermittlungserweiterung für die [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] -Dienstanwendung „ssrsapp“ aus.</span><span class="sxs-lookup"><span data-stu-id="8431e-141">Run the following PowerShell to verify the current default delivery extension for the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service application "ssrsapp".</span></span>

    ```powershell
    $app = Get-SPRSServiceApplication | Where {$_.name -Like "ssrsapp*"};
    Get-SPRSExtension -Identity $app | Where {$_.ServerDirectivesXML -Like "<DefaultDelivery*"} | Format-List *
    ```

## <a name="see-also"></a><span data-ttu-id="8431e-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8431e-142">See Also</span></span>
 <span data-ttu-id="8431e-143">[RSReportServer-Konfigurationsdatei](../report-server/rsreportserver-config-configuration-file.md) [RSReportServer-Konfigurationsdatei](../report-server/rsreportserver-config-configuration-file.md) [Freigabe Übermittlung in Reporting Services](file-share-delivery-in-reporting-services.md) [e-Mail-Übermittlung in Reporting Services](e-mail-delivery-in-reporting-services.md) [Konfigurieren eines Berichts Servers für die e-Mail-Übermittlung &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md)</span><span class="sxs-lookup"><span data-stu-id="8431e-143">[RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md) [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md) [File Share Delivery in Reporting Services](file-share-delivery-in-reporting-services.md) [E-Mail Delivery in Reporting Services](e-mail-delivery-in-reporting-services.md) [Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md)</span></span>
