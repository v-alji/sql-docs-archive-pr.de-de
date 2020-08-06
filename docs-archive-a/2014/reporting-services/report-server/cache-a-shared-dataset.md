---
title: Zwischenspeichern von freigegebenen Datasets | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c2d8c81a-da1e-4a8a-9845-fff9a0903d24
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d4757d82425368efcb6a0a555c6cfe1deacf48c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619608"
---
# <a name="cache-a-shared-dataset"></a><span data-ttu-id="b9f5e-102">Zwischenspeichern eines freigegebenen Datasets</span><span class="sxs-lookup"><span data-stu-id="b9f5e-102">Cache a Shared Dataset</span></span>
  <span data-ttu-id="b9f5e-103">Eine Möglichkeit, die Leistung zu verbessern, ist die Konfiguration von Zwischenspeichereigenschaften für ein freigegebenes Dataset.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-103">One way to improve performance is to configure caching properties for a shared dataset.</span></span> <span data-ttu-id="b9f5e-104">Wenn ein freigegebenes Dataset zwischengespeichert wird, wird eine Kopie der Abfrageergebnisse für einen angegebenen Zeitraum gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-104">When a shared dataset is cached, a copy of the query results is saved for a specified period of time.</span></span> <span data-ttu-id="b9f5e-105">Der erste Benutzer, der einen Bericht anfordert, der das freigegebene Dataset verwendet, muss auf die Abfrageergebnisse und alle Verarbeitungschritte warten, bevor er den bericht anzeigen kann.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-105">The first user who requests a report that uses the shared dataset must wait for the query results and all processing to complete before viewing the report.</span></span> <span data-ttu-id="b9f5e-106">Nachfolgende Benutzer, die den Bericht innerhalb des Zeitraums der Zwischenspeicherung anfordern, erfahren eine verbesserte Leistung, da die Abfrage und die Verarbeitung bereits durchgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-106">Subsequent users who request the report within the caching period will experience improved performance because the query and processing has already occurred.</span></span> <span data-ttu-id="b9f5e-107">Sie können auch einen Cacheaktualisierungsplan angeben, um die Abfrage auszuführen und die Ergebnisse bis zur angegebenen Ablaufzeit für den Cache zwischenzuspeichern.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-107">You can also specify a cache refresh plan to run the query and cache the results until the specified cache expiration.</span></span>  
  
 <span data-ttu-id="b9f5e-108">Benutzer, die Berichte auf Grundlage eines freigegebenen Datasets oder eines Cacheaktualisierungsplans durchführen, erstellen den Abfragezwischenspeicher; in beiden Fällen ist der Zwischenspeicher auf der Grundlage der Optionen für den Zwischenspeicherablauf verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-108">Users running reports based on a shared dataset or cache refresh plans create the query cache and in both cases, the cache is available based on the cache expiration options.</span></span>  
  
 <span data-ttu-id="b9f5e-109">Es gibt Einschränkungen hinsichtlich der Arten freigegebener Datasets, die Sie zwischenspeichern können.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-109">There are restrictions on the types of shared datasets that you can cache.</span></span> <span data-ttu-id="b9f5e-110">Beispiel: Die Abfrageergebnisse können nicht zwischengespeichert werden, wenn die Daten je nach Benutzeridentität variieren oder wenn Daten mithilfe des Sicherheitstokens des Benutzers abgerufen werden, der den Bericht anfordert.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-110">For example, the query results cannot be cached if the data varies based on the user identity or if data is retrieved using the security token of the user who requests the report.</span></span> <span data-ttu-id="b9f5e-111">Weitere Informationen finden Sie unter [Zwischenspeichern von freigegebenen Datasets (SSRS)](cache-shared-datasets-ssrs.md) und [Zwischenspeichern von Berichten (SSRS)](caching-reports-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b9f5e-111">For more information, see [Cache Shared Datasets &#40;SSRS&#41;](cache-shared-datasets-ssrs.md) and [Caching Reports &#40;SSRS&#41;](caching-reports-ssrs.md).</span></span>  
  
### <a name="to-schedule-the-expiration-of-a-cached-report"></a><span data-ttu-id="b9f5e-112">So planen Sie den Ablauf eines zwischengespeicherten Berichts</span><span class="sxs-lookup"><span data-stu-id="b9f5e-112">To schedule the expiration of a cached report</span></span>  
  
1.  <span data-ttu-id="b9f5e-113">Starten Sie den [Berichts-Manager &#40;einheitlicher SSRS-Modus&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="b9f5e-113">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="b9f5e-114">Navigieren Sie im Berichts-Manager zu dem freigegebenen Dataset, für das Sie Zwischenspeichereigenschaften festlegen möchten. Zeigen Sie auf das Element, und klicken Sie auf den Dropdownpfeil.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-114">In Report Manager, navigate to the shared dataset for which you want to set caching properties, hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="b9f5e-115">Klicken Sie im Dropdownmenü auf **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-115">In the drop-down menu, click **Manage**.</span></span>  
  
4.  <span data-ttu-id="b9f5e-116">Klicken Sie im linken Bereich auf die Registerkarte **Zwischenspeichern**.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-116">In the left frame, click **Caching**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b9f5e-117">Wenn Sie die Fehlermeldung **Die für die Ausführung des freigegebenen Datasets verwendeten Anmeldeinformationen sind nicht gespeichert**sehen, wird die Option für die Zwischenspeicherung freigegebener Datasets deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-117">If you see the error **Credentials used to run the shared dataset are not stored**, the cache shared dataset option will be disabled.</span></span> <span data-ttu-id="b9f5e-118">Sie müssen die Datenquelle ändern, damit Anmeldeinformationen gespeichert werden oder das freigegebene Dataset ändern, damit es eine andere Datenquelle verwendet, die Anmeldeinformationen speichert.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-118">You need modify the data source to store credentials or modify the shared dataset to use a different data source that does store credentials.</span></span>  
  
5.  <span data-ttu-id="b9f5e-119">Wählen Sie **Freigegebenes Dataset zwischenspeichern**aus.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-119">Select **Cache share dataset**.</span></span>  
  
6.  <span data-ttu-id="b9f5e-120">Wählen Sie die Option, nach der der Zwischenspeicher nach 30 Minuten abläuft.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-120">Select the option to expire the cache after 30 minutes.</span></span> <span data-ttu-id="b9f5e-121">Sie können auch wählen, dass der Zwischenspeicher nach einem bestimmten Zeitplan abläuft.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-121">You can also choose for the cache to expire on a specified schedule.</span></span>  
  
7.  <span data-ttu-id="b9f5e-122">Klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="b9f5e-122">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9f5e-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b9f5e-123">See Also</span></span>  
 [<span data-ttu-id="b9f5e-124">Verwalten von freigegebenen Datasets</span><span class="sxs-lookup"><span data-stu-id="b9f5e-124">Manage Shared Datasets</span></span>](../report-data/manage-shared-datasets.md)  
  
  
