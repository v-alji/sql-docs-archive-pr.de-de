---
title: Servereigenschaften (Ausführungsseite) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.execution.f1
ms.assetid: 53b77db1-b013-4dac-82dd-30c0de276639
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f0ec8725a0cec9e15cb6d8402f8d654320c38471
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619013"
---
# <a name="server-properties-execution-page"></a><span data-ttu-id="9c053-102">Servereigenschaften (Seite Ausführung)</span><span class="sxs-lookup"><span data-stu-id="9c053-102">Server Properties (Execution Page)</span></span>
  <span data-ttu-id="9c053-103">Verwenden Sie diese Seite zum Festlegen eines Timeoutwertes für die Berichtsausführung.</span><span class="sxs-lookup"><span data-stu-id="9c053-103">Use this page to set a timeout value for report execution.</span></span> <span data-ttu-id="9c053-104">Dieser Wert gilt für alle Berichte, die von der aktuellen Berichtsserverinstanz verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="9c053-104">This value applies to all reports that are processed by the current report server instance.</span></span> <span data-ttu-id="9c053-105">Sie können diesen Wert für einzelne Berichte überschreiben.</span><span class="sxs-lookup"><span data-stu-id="9c053-105">You can override this value for individual reports.</span></span> <span data-ttu-id="9c053-106">Der von Ihnen angegebene Wert muss die gesamte Berichtsverarbeitung auf dem Berichtsserver berücksichtigen, plus der Abfrageverarbeitung, die auf dem Datenbankserver durchgeführt wird, wenn der Berichtsserver die im Bericht verwendeten Daten abruft.</span><span class="sxs-lookup"><span data-stu-id="9c053-106">The value you specify must accommodate all report processing that occurs on the report server, plus query processing performed on the database server when the report server retrieves data that is used in the report.</span></span>  
  
 <span data-ttu-id="9c053-107">Öffnen Sie diese Seite, indem Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]starten und eine Verbindung mit einer Berichtsserverinstanz herstellen. Klicken Sie mit der rechten Maustaste auf den Namen des Berichtsservers, und wählen Sie anschließend **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="9c053-107">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server instance, right-click the report server name, and select **Properties**.</span></span> <span data-ttu-id="9c053-108">Klicken Sie auf **Ausführung** , um diese Seite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9c053-108">Click **Execution** to open this page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9c053-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="9c053-109">Options</span></span>  
 <span data-ttu-id="9c053-110">**Kein Timeout für eine Berichtsausführung**</span><span class="sxs-lookup"><span data-stu-id="9c053-110">**Do not timeout report execution**</span></span>  
 <span data-ttu-id="9c053-111">Stellt einem Berichtsserver eine uneingeschränkte Zeitspanne für die Berichtsverarbeitung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="9c053-111">Allow a report server unlimited time to complete report processing.</span></span>  
  
 <span data-ttu-id="9c053-112">**Berichtsausführung auf die folgende Anzahl von Sekunden beschränken**</span><span class="sxs-lookup"><span data-stu-id="9c053-112">**Limit report execution to the following number of seconds**</span></span>  
 <span data-ttu-id="9c053-113">Legt eine Zeitbeschränkung für die Berichtsausführung fest.</span><span class="sxs-lookup"><span data-stu-id="9c053-113">Set a time constraint on report execution.</span></span> <span data-ttu-id="9c053-114">Diese Zeitspanne beginnt, wenn der Bericht angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="9c053-114">The time period starts when the report is requested.</span></span> <span data-ttu-id="9c053-115">Wenn diese Zeitspanne endet, bevor der Bericht vollständig verarbeitet wurde, bricht der Berichtsserver den Vorgang und alle in Bearbeitung befindlichen Abfragen externer Datenquellen ab.</span><span class="sxs-lookup"><span data-stu-id="9c053-115">If the time period ends before the report is fully processed, the report server cancels the process and any in-process queries to external data sources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c053-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9c053-116">See Also</span></span>  
 <span data-ttu-id="9c053-117">[Festlegen von Berichtsservereigenschaften &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="9c053-117">[Set Report Server Properties &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span></span>  
 <span data-ttu-id="9c053-118">[Vorgehensweise: Herstellen einer Verbindung mit einem Berichtsserver in Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="9c053-118">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="9c053-119">[Festlegen von Berichtsverarbeitungseigenschaften](../report-server/set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="9c053-119">[Set Report Processing Properties](../report-server/set-report-processing-properties.md) </span></span>  
 <span data-ttu-id="9c053-120">[Festlegen von Timeoutwerten für die Verarbeitung von Berichten und freigegebenen Datasets (SSRS)](../report-server/setting-time-out-values-for-report-and-shared-dataset-processing-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9c053-120">[Setting Time-out Values for Report and Shared Dataset Processing &#40;SSRS&#41;](../report-server/setting-time-out-values-for-report-and-shared-dataset-processing-ssrs.md) </span></span>  
 [<span data-ttu-id="9c053-121">Berichtsserver im Management Studio (F1-Hilfe)</span><span class="sxs-lookup"><span data-stu-id="9c053-121">Report Server in Management Studio F1 Help</span></span>](report-server-in-management-studio-f1-help.md)  
  
  
