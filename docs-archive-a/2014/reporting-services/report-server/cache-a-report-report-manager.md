---
title: Zwischenspeichern eines Berichts (Berichts-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report execution properties [Reporting Services]
- cache [Reporting Services]
- cached reports [Reporting Services]
- schedules [Reporting Services], report expiration
- expiration [Reporting Services]
ms.assetid: 723d1cb0-c2e7-4763-8690-a6a7a8bbbb90
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2e359e6c7a40b267979137ef2b3a285667a6fdb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619609"
---
# <a name="cache-a-report-report-manager"></a><span data-ttu-id="c4751-102">Zwischenspeichern eines Berichts (Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="c4751-102">Cache a Report (Report Manager)</span></span>
  <span data-ttu-id="c4751-103">Eine Möglichkeit, die Leistung zu verbessern, ist die Konfiguration von Zwischenspeichereigenschaften für einen Bericht.</span><span class="sxs-lookup"><span data-stu-id="c4751-103">One way to improve performance is to configure caching properties for a report.</span></span> <span data-ttu-id="c4751-104">Beim Zwischenspeichern eines Berichts wird eine Kopie des gerenderten Berichts für einen kurzen Zeitraum gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c4751-104">When a report is cached, a copy of the rendered report is saved for a short period of time.</span></span> <span data-ttu-id="c4751-105">Der erste Benutzer, der den Bericht anfordert, muss warten, bis die gesamte Verarbeitung abgeschlossen ist, bevor er den Bericht anzeigen kann.</span><span class="sxs-lookup"><span data-stu-id="c4751-105">The first user who requests the report must wait for all processing to complete before viewing the report.</span></span> <span data-ttu-id="c4751-106">Nachfolgende Benutzer, die den Bericht innerhalb des Zeitraums der Zwischenspeicherung anfordern, können ihn sofort anzeigen, da die Verarbeitung bereits durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="c4751-106">Subsequent users who request the report within the caching period can view it right away because processing has already occurred.</span></span>  
  
 <span data-ttu-id="c4751-107">Es gibt Einschränkungen in Bezug auf die Berichtstypen, die Sie zwischenspeichern können.</span><span class="sxs-lookup"><span data-stu-id="c4751-107">There are restrictions on the types of reports that you can cache.</span></span> <span data-ttu-id="c4751-108">Ein Bericht kann z. B. nicht zwischengespeichert werden, wenn die Berichtsausgabe je nach Benutzeridentität variiert oder wenn Daten mithilfe des Sicherheitstokens des Benutzers abgerufen werden, der den Bericht anfordert.</span><span class="sxs-lookup"><span data-stu-id="c4751-108">For example, a report cannot be cached if report output varies based on the user identity or if data is retrieved using the security token of the user who requests the report.</span></span> <span data-ttu-id="c4751-109">Weitere Informationen finden Sie unter [Zwischenspeichern von Berichten &#40;SSRS&#41;](caching-reports-ssrs.md)bestand darin die einzige Möglichkeit, den Cache vorab zu laden.</span><span class="sxs-lookup"><span data-stu-id="c4751-109">For more information, see [Caching Reports &#40;SSRS&#41;](caching-reports-ssrs.md).</span></span>  
  
### <a name="to-schedule-the-expiration-of-a-cached-report"></a><span data-ttu-id="c4751-110">So planen Sie den Ablauf eines zwischengespeicherten Berichts</span><span class="sxs-lookup"><span data-stu-id="c4751-110">To schedule the expiration of a cached report</span></span>  
  
1.  <span data-ttu-id="c4751-111">Starten Sie den [Berichts-Manager &#40;einheitlicher SSRS-Modus&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="c4751-111">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="c4751-112">Navigieren Sie im Berichts-Manager zur Seite **Inhalt** .</span><span class="sxs-lookup"><span data-stu-id="c4751-112">In Report Manager, navigate to the **Contents** page.</span></span> <span data-ttu-id="c4751-113">Navigieren Sie zum Bericht, für den Sie Zwischenspeichereigenschaften festlegen möchten, zeigen Sie auf das Element, und klicken Sie auf den Dropdownpfeil.</span><span class="sxs-lookup"><span data-stu-id="c4751-113">Navigate to the report for which you want to set caching properties, hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="c4751-114">Klicken Sie im Dropdownmenü auf **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="c4751-114">In the drop-down menu, click **Manage**.</span></span>  
  
4.  <span data-ttu-id="c4751-115">Klicken Sie im linken Bereich auf **Verarbeitungsoptionen**.</span><span class="sxs-lookup"><span data-stu-id="c4751-115">In the left frame, click the **Processing Options**.</span></span>  
  
5.  <span data-ttu-id="c4751-116">Wählen Sie auf der Seite die Option **Diesen Bericht immer mit den neuesten Daten ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c4751-116">On the page, select **Always run this report with the most recent data**.</span></span>  
  
6.  <span data-ttu-id="c4751-117">Wählen Sie eine der folgenden zwei Cacheoptionen aus, und konfigurieren Sie den Ablauf wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c4751-117">Select one of the following two cache options and configure expiration as follows:</span></span>  
  
    -   <span data-ttu-id="c4751-118">Wenn die zwischengespeicherte Kopie nach einem bestimmten Zeitraum ablaufen soll, klicken Sie auf **Eine temporäre Kopie des Berichts zwischenspeichern. Diese Kopie soll nach der folgenden Anzahl von Minuten ablaufen**.</span><span class="sxs-lookup"><span data-stu-id="c4751-118">To configure a cached copy to expire after a particular time period, click **Cache a temporary copy of the report. Expire copy of report after a number of minutes**.</span></span> <span data-ttu-id="c4751-119">Geben Sie die Anzahl von Minuten für den Berichtsablauf ein.</span><span class="sxs-lookup"><span data-stu-id="c4751-119">Type the number of minutes for report expiration.</span></span>  
  
    -   <span data-ttu-id="c4751-120">Wenn eine zwischengespeicherte Kopie nach einem bestimmten Zeitplan ablaufen soll, klicken Sie auf **Eine temporäre Kopie des Berichts zwischenspeichern. Diese Kopie soll gemäß dem folgenden Zeitplan ablaufen.**</span><span class="sxs-lookup"><span data-stu-id="c4751-120">To configure a cached copy to expire on a schedule, click **Cache a temporary copy of the report. Expire copy of report on the following schedule.**</span></span> <span data-ttu-id="c4751-121">Klicken Sie auf **Konfigurieren**, oder wählen Sie einen freigegebenen Zeitplan für die Steuerung des Berichtsablaufs aus.</span><span class="sxs-lookup"><span data-stu-id="c4751-121">Click **Configure**, or select a shared schedule to control report expiration</span></span>  
  
7.  <span data-ttu-id="c4751-122">Klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="c4751-122">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4751-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c4751-123">See Also</span></span>  
 <span data-ttu-id="c4751-124">[Festlegen von Berichtsverarbeitungseigenschaften](set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="c4751-124">[Set Report Processing Properties](set-report-processing-properties.md) </span></span>  
 [<span data-ttu-id="c4751-125">Zwischenspeichern von Berichten &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c4751-125">Caching Reports &#40;SSRS&#41;</span></span>](caching-reports-ssrs.md)  
  
  
