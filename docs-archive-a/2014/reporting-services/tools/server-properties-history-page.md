---
title: Servereigenschaften (Seite „Verlauf“)|Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.history.f1
ms.assetid: be9d8018-a46f-4625-9ae1-138ebe6b38ba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: df5ff9dc7a94431f8feec112d460938aa1631ef2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619010"
---
# <a name="server-properties-history-page"></a><span data-ttu-id="6f2fe-102">Servereigenschaften (Seite Verlauf)</span><span class="sxs-lookup"><span data-stu-id="6f2fe-102">Server Properties (History Page)</span></span>
  <span data-ttu-id="6f2fe-103">Verwenden Sie diese Seite als Standardwert für die Anzahl von Kopien der Berichtsverläufe, die Sie beibehalten möchten.</span><span class="sxs-lookup"><span data-stu-id="6f2fe-103">Use this page to set a default value for the number of copies of report history to retain.</span></span> <span data-ttu-id="6f2fe-104">Mithilfe eines Standardwertes werden erste Grenzwerte für den Berichtsverlauf für alle Berichte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6f2fe-104">The default value provides an initial setting that establishes report history limits for all reports.</span></span> <span data-ttu-id="6f2fe-105">Sie können diese Werte für die jeweiligen Berichte anpassen.</span><span class="sxs-lookup"><span data-stu-id="6f2fe-105">You can vary these settings for individual reports.</span></span>  
  
 <span data-ttu-id="6f2fe-106">Der Berichtsverlauf ist eine Auflistung von Berichtsmomentaufnahmen, die die zum Zeitpunkt der Erstellung der Momentaufnahme aktuellen Berichtsdaten und die Layouts enthalten.</span><span class="sxs-lookup"><span data-stu-id="6f2fe-106">Report history is a collection of report snapshots that include report data and layout that is current for the report at the time the snapshot is created.</span></span> <span data-ttu-id="6f2fe-107">Mithilfe des Berichtsverlaufs können Sie die Kopie eines Berichts, so wie er zu einem bestimmten Zeitpunkt erstellt wurde, aufbewahren.</span><span class="sxs-lookup"><span data-stu-id="6f2fe-107">You can use report history to keep a copy of a report as it was on a specific date or time.</span></span> <span data-ttu-id="6f2fe-108">Sie können den Berichtsverlauf für einzelne Berichte erstellen und verwalten, die auf einem Berichtsserver ausgeführt werden, der für den einheitlichen Modus oder den integrierten SharePoint-Modus konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="6f2fe-108">You can create and manage report history for individual reports that run on a native mode report server or a report server that is configured for SharePoint integrated mode.</span></span>  
  
 <span data-ttu-id="6f2fe-109">Die Momentaufnahmen des Berichtsverlaufs werden in der Berichtsserverdatenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="6f2fe-109">Report history snapshots are stored in the report server database.</span></span> <span data-ttu-id="6f2fe-110">Wenn Sie eine unbegrenzte Zahl von Momentaufnahmen speichern, müssen Sie regelmäßig die Größe der Datenbank überprüfen, um sicherzustellen, dass ihre Größe nicht allzu schnell wächst oder zu viel Speicherplatz belegt wird.</span><span class="sxs-lookup"><span data-stu-id="6f2fe-110">If you keep an unlimited number of snapshots, be sure to periodically check the database size to ensure it is not growing too fast or consuming too much disk space.</span></span>  
  
 <span data-ttu-id="6f2fe-111">Öffnen Sie diese Seite, indem Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]starten und eine Verbindung mit einer Berichtsserverinstanz herstellen. Klicken Sie mit der rechten Maustaste auf den Namen des Berichtsservers, und wählen Sie anschließend **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="6f2fe-111">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server instance, right-click the report server name, and select **Properties**.</span></span> <span data-ttu-id="6f2fe-112">Klicken Sie auf **Verlauf** , um diese Seite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6f2fe-112">Click **History** to open this page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6f2fe-113">Tastatur</span><span class="sxs-lookup"><span data-stu-id="6f2fe-113">Options</span></span>  
 <span data-ttu-id="6f2fe-114">**Beliebig viele Momentaufnahmen im Berichtsverlauf speichern**</span><span class="sxs-lookup"><span data-stu-id="6f2fe-114">**Keep an unlimited number of snapshots in report history**</span></span>  
 <span data-ttu-id="6f2fe-115">Alle Berichtsverlaufs-Momentaufnahmen werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="6f2fe-115">Retain all report history snapshots.</span></span> <span data-ttu-id="6f2fe-116">Sie müssen die Momentaufnahmen manuell löschen, um die Größe des Berichtsverlaufs zu verringern.</span><span class="sxs-lookup"><span data-stu-id="6f2fe-116">You must manually delete snapshots to reduce the size of report history.</span></span>  
  
 <span data-ttu-id="6f2fe-117">**Max. Anzahl von Kopien des Berichtsverlaufs**</span><span class="sxs-lookup"><span data-stu-id="6f2fe-117">**Limit the copies of report history**</span></span>  
 <span data-ttu-id="6f2fe-118">Es wird eine festgelegte Anzahl von Berichtsverlaufs-Momentaufnahmen beibehalten.</span><span class="sxs-lookup"><span data-stu-id="6f2fe-118">Retain a set number of report history snapshots.</span></span> <span data-ttu-id="6f2fe-119">Wenn der Grenzwert erreicht ist, werden ältere Kopien aus dem Berichtsverlauf entfernt, um Platz für neue Kopien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6f2fe-119">When the limit is reached, older copies are removed from report history to make room for newer copies.</span></span>  
  
 <span data-ttu-id="6f2fe-120">Wenn Sie den Berichtsverlauf zu einem späteren Zeitpunkt einschränken und der vorhandene Berichtsverlauf den angegebenen Grenzwert übersteigt, verringert der Berichtsserver den vorhandenen Berichtsverlauf auf den neuen Grenzwert.</span><span class="sxs-lookup"><span data-stu-id="6f2fe-120">If you limit report history later, when the existing report history exceeds the limit you specify, the report server reduces the existing report history to the new limit.</span></span> <span data-ttu-id="6f2fe-121">Die ältesten Berichtsmomentaufnahmen werden zuerst gelöscht.</span><span class="sxs-lookup"><span data-stu-id="6f2fe-121">The oldest report snapshots are deleted first.</span></span> <span data-ttu-id="6f2fe-122">Falls der Berichtsverlauf leer ist oder unter dem Grenzwert liegt, werden neue Berichtsmomentaufnahmen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6f2fe-122">If report history is empty or below the limit, new report snapshots are added.</span></span> <span data-ttu-id="6f2fe-123">Ist der Grenzwert erreicht, wird die älteste Momentaufnahme gelöscht, sobald eine neue Berichtsmomentaufnahme hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="6f2fe-123">When the limit is reached, the oldest snapshot is deleted when a new report snapshot is added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f2fe-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f2fe-124">See Also</span></span>  
 <span data-ttu-id="6f2fe-125">[&#40;Management Studio Eigenschaften für Berichts Server festlegen&#41;](set-report-server-properties-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="6f2fe-125">[Set Report Server Properties &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span></span>  
 <span data-ttu-id="6f2fe-126">[Herstellen einer Verbindung mit einem Berichts Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="6f2fe-126">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 [<span data-ttu-id="6f2fe-127">Berichtsserver im Management Studio (F1-Hilfe)</span><span class="sxs-lookup"><span data-stu-id="6f2fe-127">Report Server in Management Studio F1 Help</span></span>](report-server-in-management-studio-f1-help.md)  
  
  
