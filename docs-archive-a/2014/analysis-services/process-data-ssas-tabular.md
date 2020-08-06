---
title: Verarbeiten von Daten (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d88f2dc9-2933-4be5-9bf3-48ffbc2d0a1a
author: minewiskan
ms.author: owend
ms.openlocfilehash: e2066cb6d871f43dda719cab3539253db97bfca7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725038"
---
# <a name="process-data-ssas-tabular"></a><span data-ttu-id="99293-102">Verarbeiten von Daten (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="99293-102">Process Data (SSAS Tabular)</span></span>
  <span data-ttu-id="99293-103">Wenn Sie Daten im Modus mit Zwischenspeicherung in ein Tabellenmodell importieren, zeichnen Sie eine Momentaufnahme der Daten zum Zeitpunkt des Imports auf.</span><span class="sxs-lookup"><span data-stu-id="99293-103">When you import data into a tabular model, in Cached mode, you are capturing a snapshot of that data at the time of import.</span></span> <span data-ttu-id="99293-104">In einigen Fällen ändern sich diese Daten möglicherweise nie und müssen im Modell nicht aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="99293-104">In some cases, that data may never change and it does not need to be updated in the model.</span></span> <span data-ttu-id="99293-105">Es ist jedoch wahrscheinlicher, dass sich die Daten, aus denen Daten importiert werden, regelmäßig ändern. Damit das Modell jedoch immer die neuesten Daten aus den Datenquellen widerspiegelt, ist es erforderlich, die Daten zu verarbeiten (zu aktualisieren) und berechnete Daten neu zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="99293-105">However, it is more likely that the data you are importing from changes regularly, and in order for your model to reflect the most recent data from the data sources, it is necessary to process (refresh) the data and re-calculate calculated data.</span></span> <span data-ttu-id="99293-106">Um die Daten im Modell zu aktualisieren, führen Sie eine Verarbeitungsaktion für alle Tabellen, eine einzelne Tabelle, eine Partition oder eine Datenquellenverbindung aus.</span><span class="sxs-lookup"><span data-stu-id="99293-106">To update the data in your model, you perform a process action on all tables, on an individual table, by a partition, or by a data source connection.</span></span>  
  
 <span data-ttu-id="99293-107">Beim Erstellen des Modellprojekts müssen alle Verarbeitungsaktionen manuell in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]initiiert werden.</span><span class="sxs-lookup"><span data-stu-id="99293-107">When authoring your model project, process actions must be initiated manually in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="99293-108">Nachdem ein Modell bereitgestellt wurde, können Verarbeitungsvorgänge mit [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] ausgeführt oder mit einem Skript geplant werden.</span><span class="sxs-lookup"><span data-stu-id="99293-108">After a model has been deployed, process operations can be performed by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or scheduled by using a script.</span></span> <span data-ttu-id="99293-109">Die hier beschriebenen Tasks beziehen sich auf Verarbeitungsaktionen, die Sie während der Modellerstellung in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]ausführen können.</span><span class="sxs-lookup"><span data-stu-id="99293-109">Tasks described here all pertain to process actions that you can do during model authoring in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="99293-110">Weitere Informationen zu Verarbeitungs Aktionen für ein bereitgestelltes Modell finden Sie unter [Verarbeiten von Datenbank, Tabelle oder Partition](tabular-models/process-database-table-or-partition-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="99293-110">For more information about process actions for a deployed model, see [Process Database, Table, or Partition](tabular-models/process-database-table-or-partition-analysis-services.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="99293-111">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="99293-111">Related Tasks</span></span>  
  
|<span data-ttu-id="99293-112">Thema</span><span class="sxs-lookup"><span data-stu-id="99293-112">Topic</span></span>|<span data-ttu-id="99293-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="99293-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="99293-114">Manuelle Verarbeitung von Daten &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="99293-114">Manually Process Data &#40;SSAS Tabular&#41;</span></span>](manually-process-data-ssas-tabular.md)|<span data-ttu-id="99293-115">Beschreibt, wie Arbeitsbereichsdaten eines Modells manuell verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="99293-115">Describes how to manually process model workspace data.</span></span>|  
|[<span data-ttu-id="99293-116">Problembehandlung von Verarbeitungsdaten &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="99293-116">Troubleshoot Process Data &#40;SSAS Tabular&#41;</span></span>](troubleshoot-process-data-ssas-tabular.md)|<span data-ttu-id="99293-117">Beschreibt die Problembehandlung für Verarbeitungsvorgänge.</span><span class="sxs-lookup"><span data-stu-id="99293-117">Describes how to troubleshoot process operations.</span></span>|  
  
  
