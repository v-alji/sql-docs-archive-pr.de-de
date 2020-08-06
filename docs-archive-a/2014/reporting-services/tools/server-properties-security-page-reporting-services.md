---
title: Servereigenschaften (Seite „Sicherheit“) – Reporting Services | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.security.f1
ms.assetid: f49aedc6-f145-4df1-8f69-d5d910f492c6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f709d42bf593b4933d9fc1fdc423c195967df382
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619011"
---
# <a name="server-properties-security-page---reporting-services"></a><span data-ttu-id="eb1de-102">Servereigenschaften (Seite Sicherheit) – Reporting Services</span><span class="sxs-lookup"><span data-stu-id="eb1de-102">Server Properties (Security Page) - Reporting Services</span></span>
  <span data-ttu-id="eb1de-103">Verwenden Sie diese Seite, um Funktionen zu deaktivieren, die potenziell einen Berichtsserver gefährden können.</span><span class="sxs-lookup"><span data-stu-id="eb1de-103">Use this page to turn off features that can potentially compromise a report server.</span></span> <span data-ttu-id="eb1de-104">Die Deaktivierung dieser Funktionen führt zu einigen Funktionseinschränkungen, kann jedoch die Gesamtsicherheit durch Verringerung bestimmter Bedrohungen erhöhen.</span><span class="sxs-lookup"><span data-stu-id="eb1de-104">Turning off these features will limit some functionality, but can improve the overall security of the report server by mitigating specific threats.</span></span>  
  
 <span data-ttu-id="eb1de-105">Öffnen Sie diese Seite, indem Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]starten und eine Verbindung mit einer Berichtsserverinstanz herstellen. Klicken Sie mit der rechten Maustaste auf den Namen des Berichtsservers, und wählen Sie anschließend **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="eb1de-105">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server instance, right-click the report server name, and select **Properties**.</span></span> <span data-ttu-id="eb1de-106">Klicken Sie auf **Sicherheit** , um diese Seite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="eb1de-106">Click **Security** to open this page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="eb1de-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="eb1de-107">Options</span></span>  
 <span data-ttu-id="eb1de-108">**Integrierte Sicherheit von Windows für Berichtsdatenquellen-Verbindungen aktivieren**</span><span class="sxs-lookup"><span data-stu-id="eb1de-108">**Enable Windows integrated security for report data sources**</span></span>  
 <span data-ttu-id="eb1de-109">Geben Sie an, ob eine Verbindung mit einer Berichtsdatenquelle mithilfe des Windows-Sicherheitstokens des Benutzers hergestellt werden kann, der den Bericht angefordert hat.</span><span class="sxs-lookup"><span data-stu-id="eb1de-109">Specify whether a connection to a report data source can be made using the Windows security token of the user who requested the report.</span></span>  
  
 <span data-ttu-id="eb1de-110">Wenn Sie diese Funktion deaktivieren, ist die Funktion Integrierte Sicherheit von Windows in der Eigenschaftenseite der Berichtsdatenquelle nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="eb1de-110">If you turn off this feature, the Windows Integrated Security feature in the report data source property pages will be unavailable.</span></span> <span data-ttu-id="eb1de-111">Wenn Berichtsdatenquellen für die integrierte Sicherheit von Windows konfiguriert werden, und Sie dann diese Funktion deaktivieren, aktualisiert der Berichtsserver sofort die Datenverbindungseigenschaften aller Datenquellen so, dass sie Anmeldeinformationen anfordern.</span><span class="sxs-lookup"><span data-stu-id="eb1de-111">If report data sources are configured for Windows integrated security and you subsequently turn off this feature, the report server will immediately update all data source connection properties to prompt for credentials.</span></span>  
  
 <span data-ttu-id="eb1de-112">**Ad-hoc-Berichterstellung aktivieren**</span><span class="sxs-lookup"><span data-stu-id="eb1de-112">**Enable Ad Hoc Reporting**</span></span>  
 <span data-ttu-id="eb1de-113">Geben Sie an, ob Benutzer Ad-hoc-Abfragen von einem Bericht des Berichts-Generators ausführen können, wodurch automatisch neue Berichte generiert werden, sobald ein Benutzer auf die ihn interessierenden Daten klickt.</span><span class="sxs-lookup"><span data-stu-id="eb1de-113">Specify whether users can perform ad hoc queries from a Report Builder report, where new reports are automatically generated when a user clicks data of interest.</span></span>  
  
 <span data-ttu-id="eb1de-114">Durch Festlegen dieser Option wird bestimmt, ob der Wert der `EnableLoadReportDefinition`-Eigenschaft auf `True` oder `False` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="eb1de-114">Setting this option determines whether the `EnableLoadReportDefinition` property on the report server is set to `True` or `False`.</span></span> <span data-ttu-id="eb1de-115">Wenn Sie diese Option deaktivieren, wird die Eigenschaft auf `False` festgelegt, und der Berichtsserver generiert keine Berichte mit Durchklicken für Berichte, die während des Durchsuchens der Daten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="eb1de-115">If you clear this option, the property will be set to `False` and report server will not generate clickthrough reports that are created during data exploration.</span></span> <span data-ttu-id="eb1de-116">Alle Aufrufe der `LoadReportDefinition`-Methode werden blockiert.</span><span class="sxs-lookup"><span data-stu-id="eb1de-116">All calls to the `LoadReportDefinition` method will be blocked.</span></span>  
  
 <span data-ttu-id="eb1de-117">Die Deaktivierung dieser Option führt zu einem Sicherheitsrisiko, weil böswillige Benutzer einen Denial-of-Service-Angriff ausführen können, bei dem der Berichtsserver mit `LoadReportDefinition`-Anforderungen überlastet wird.</span><span class="sxs-lookup"><span data-stu-id="eb1de-117">Turning off this option mitigates a threat whereby a malicious user launches a denial of service attack by overloading the report server with `LoadReportDefinition` requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb1de-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb1de-118">See Also</span></span>  
 <span data-ttu-id="eb1de-119">[&#40;Management Studio Eigenschaften für Berichts Server festlegen&#41;](set-report-server-properties-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="eb1de-119">[Set Report Server Properties &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span></span>  
 <span data-ttu-id="eb1de-120">[Herstellen einer Verbindung mit einem Berichts Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="eb1de-120">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="eb1de-121">[Angeben von Anmelde Informationen und Verbindungsinformationen für Berichtsdaten Quellen] (.. /Report-Data/Specify-Credential-and-Connection-Information-for-Report-Data-Sources.MD [Report Server in Management Studio F1-Hilfe](report-server-in-management-studio-f1-help.md)</span><span class="sxs-lookup"><span data-stu-id="eb1de-121">[Specify Credential and Connection Information for Report Data Sources](../report-data/specify-credential-and-connection-information-for-report-data-sources.md [Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md)</span></span>  
  
  
