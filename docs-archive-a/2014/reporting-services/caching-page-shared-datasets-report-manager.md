---
title: Zwischenspeichern (Seite), freigegebene Datasets (Berichts-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eac372e9-d2a1-48a8-bbe5-09d101df16ea
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62d899964911a6f2d35e59d49d925ff80013af42
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617810"
---
# <a name="caching-page-shared-datasets-report-manager"></a><span data-ttu-id="a2ec0-102">Zwischenspeichern (Seite), Freigegebene Datasets (Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="a2ec0-102">Caching Page, Shared Datasets (Report Manager)</span></span>
  <span data-ttu-id="a2ec0-103">Verwenden Sie die Eigenschaftenseite Zwischenspeichern, um die Cacheoptionen für ein freigegebenes Dataset festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-103">Use the Caching properties page to set the cache options for a shared dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a2ec0-104">Diese Funktion ist nicht in jeder Edition von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-104">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a2ec0-105">Eine Liste der Funktionen, die von den Editionen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]unterstützt werden, finden Sie unter [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="a2ec0-105">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="a2ec0-106">Navigation</span><span class="sxs-lookup"><span data-stu-id="a2ec0-106">Navigation</span></span>  
 <span data-ttu-id="a2ec0-107">Verwenden Sie folgendes Verfahren, um zu dieser Position in der Benutzeroberfläche zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-107">Use the following procedure to navigate to this location in the user interface.</span></span>  
  
### <a name="to-open-the-caching-properties-page-for-a-shared-dataset"></a><span data-ttu-id="a2ec0-108">So öffnen Sie die Eigenschaftenseite "Zwischenspeichern" für ein freigegebenes Dataset</span><span class="sxs-lookup"><span data-stu-id="a2ec0-108">To open the Caching properties page for a shared dataset</span></span>  
  
1.  <span data-ttu-id="a2ec0-109">Öffnen Sie den Berichts-Manager, und suchen Sie den Bericht, für den Sie Eigenschaften freigegebener Datasets konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-109">Open Report Manager, and locate the report for which you want to configure shared dataset properties.</span></span>  
  
2.  <span data-ttu-id="a2ec0-110">Zeigen Sie auf das freigegebene Dataset, und klicken Sie auf den Dropdownpfeil.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-110">Point to the shared dataset, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="a2ec0-111">Klicken Sie in der Dropdownliste auf **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-111">In the drop-down list, click **Manage**.</span></span> <span data-ttu-id="a2ec0-112">Die Seite Allgemeine Eigenschaften für den Bericht wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-112">The General properties page for the report opens.</span></span>  
  
4.  <span data-ttu-id="a2ec0-113">Klicken Sie auf die Registerkarte **Zwischenspeichern** .</span><span class="sxs-lookup"><span data-stu-id="a2ec0-113">Click the **Caching** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a2ec0-114">Tastatur</span><span class="sxs-lookup"><span data-stu-id="a2ec0-114">Options</span></span>  
 <span data-ttu-id="a2ec0-115">**Freigegebenes Dataset zwischenspeichern**</span><span class="sxs-lookup"><span data-stu-id="a2ec0-115">**Cache shared dataset**</span></span>  
 <span data-ttu-id="a2ec0-116">Speichert eine temporäre Kopie der Daten in einem Cache, sobald ein Benutzer erstmalig einen Bericht öffnet, der das freigegebene Dataset verwendet.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-116">Places a temporary copy of the data in a cache when a user first opens a report that uses this shared dataset.</span></span> <span data-ttu-id="a2ec0-117">Nachfolgende Benutzer, die den Bericht innerhalb des Zeitraums der Zwischenspeicherung ausführen, erhalten die zwischengespeicherte Kopie der Daten.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-117">Subsequent users who run the report within the caching period receive the cached copy of the data.</span></span> <span data-ttu-id="a2ec0-118">Die Zwischenspeicherung erhöht in der Regel die Leistung, da die Daten aus dem Cache zurückgegeben werden und die Datasetabfrage nicht erneut ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-118">Caching usually improves performance because the data is returned from the cache instead of running the dataset query again.</span></span>  
  
 <span data-ttu-id="a2ec0-119">**Cacheablauf nach dieser Anzahl von Minuten**</span><span class="sxs-lookup"><span data-stu-id="a2ec0-119">**Expire the cache after a number of minutes**</span></span>  
 <span data-ttu-id="a2ec0-120">Geben Sie die Zeitdauer in Minuten an, während derer die zwischengespeicherte Kopie der Daten erhalten bleibt.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-120">Specify the number of minutes to save the cached copy of the data.</span></span> <span data-ttu-id="a2ec0-121">Sobald eine temporäre Kopie abgelaufen ist, werden die Daten nicht mehr aus dem Cache zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-121">As soon as a temporary copy expires, the data is no longer returned from the cache.</span></span> <span data-ttu-id="a2ec0-122">Wenn ein Benutzer einen Bericht, der dieses freigegebene Dataset verwendet, das nächste Mal öffnet, wird die Datasetabfrage ausgeführt, und der Berichtsserver fügt wieder eine Kopie der aktualisierten Daten in den Cache ein.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-122">The next time a user opens a report that uses this shared dataset, the dataset query runs and the report server places a copy of the refreshed data back in the cache.</span></span>  
  
 <span data-ttu-id="a2ec0-123">**Cacheablauf nach folgendem Zeitplan**</span><span class="sxs-lookup"><span data-stu-id="a2ec0-123">**Expire the cache on the following schedule**</span></span>  
 <span data-ttu-id="a2ec0-124">Planen Sie den Zeitraum, nach dem die zwischengespeicherten Daten nicht mehr gültig sind und aus dem Cache entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-124">Schedule the time when the cached data is no longer valid and is removed from the cache.</span></span> <span data-ttu-id="a2ec0-125">Als Zeitplan kann ein freigegebener Zeitplan oder ein Plan verwendet werden, der nur auf das aktuelle freigegebene Dataset angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-125">The schedule can be a shared schedule or one that is specific for only the current shared dataset.</span></span>  
  
 <span data-ttu-id="a2ec0-126">**Datasetspezifischer Zeitplan**</span><span class="sxs-lookup"><span data-stu-id="a2ec0-126">**Dataset-specific schedule**</span></span>  
 <span data-ttu-id="a2ec0-127">Geben Sie einen Zeitplan an, der nur von diesem Dataset verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-127">Specify a schedule that is used only by this dataset.</span></span>  
  
 <span data-ttu-id="a2ec0-128">**Frei gegebener Zeitplan**</span><span class="sxs-lookup"><span data-stu-id="a2ec0-128">**Shared schedule**</span></span>  
 <span data-ttu-id="a2ec0-129">Geben Sie einen Zeitplan an, der für Berichte, Abonnements und andere freigegebene Datasets gemeinsam verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-129">Specify a schedule that is shared among reports, subscriptions, and other shared datasets.</span></span>  
  
 <span data-ttu-id="a2ec0-130">**Anwenden**</span><span class="sxs-lookup"><span data-stu-id="a2ec0-130">**Apply**</span></span>  
 <span data-ttu-id="a2ec0-131">Speichern Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-131">Save your changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2ec0-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a2ec0-132">See Also</span></span>  
 <span data-ttu-id="a2ec0-133">[Berichts-Manager &#40;einheitlicher SSRS-Modus&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="a2ec0-133">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="a2ec0-134">[Berichts-Manager F1-Hilfe](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="a2ec0-134">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 <span data-ttu-id="a2ec0-135">[Zwischenspeichern von freigegebenen Datasets &#40;SSRS-&#41;](report-server/cache-shared-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a2ec0-135">[Cache Shared Datasets &#40;SSRS&#41;](report-server/cache-shared-datasets-ssrs.md) </span></span>  
 [<span data-ttu-id="a2ec0-136">Zeitpläne</span><span class="sxs-lookup"><span data-stu-id="a2ec0-136">Schedules</span></span>](subscriptions/schedules.md)  
  
  
