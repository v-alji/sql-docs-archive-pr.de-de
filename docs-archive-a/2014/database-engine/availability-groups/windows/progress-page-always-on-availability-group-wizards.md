---
title: Fortschritts Seite (AlwaysOn-Verfügbarkeits Gruppen-Assistenten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.addreplicawizard.progress.f1
- sql12.swb.newagwizard.progress.f1
- sql11.swb.failoverwizard.progress.f1
- sql11.swb.adddatabasewizard.progress.f1
- sql11.swb.addreplicawizard.progress.f1
- sql11.swb.newagwizard.progress.f1
- sql12.swb.adddatabasewizard.progress.f1
- sql12.swb.failoverwixard.progress.f1
ms.assetid: bd3b0306-8384-4120-a1c9-03825f0ae26a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7de8df6906d930215d71a0adc562bd7cef961ebb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724225"
---
# <a name="progress-page-alwayson-availability-group-wizards"></a><span data-ttu-id="142a5-102">Seite 'Status' (AlwaysOn-Verfügbarkeitsgruppen-Assistenten)</span><span class="sxs-lookup"><span data-stu-id="142a5-102">Progress Page (AlwaysOn Availability Group Wizards)</span></span>
  <span data-ttu-id="142a5-103">Mithilfe dieses Dialogfelds können Sie den Status eines [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] -Assistenten anzuzeigen, den Sie in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]ausführen.</span><span class="sxs-lookup"><span data-stu-id="142a5-103">Use this dialog box to view the progress of a [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] wizard that you are running in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="142a5-104">Die Statusanzeige gibt den relativen Status der Schritte an, die der Assistent ausführt.</span><span class="sxs-lookup"><span data-stu-id="142a5-104">The progress bar indicates the relative progress of the steps that the wizard is performing.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="142a5-105">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="142a5-105">UI element list</span></span>  
 <span data-ttu-id="142a5-106">**Weitere Informationen**</span><span class="sxs-lookup"><span data-stu-id="142a5-106">**More details**</span></span>  
 <span data-ttu-id="142a5-107">Klicken Sie auf den Pfeil nach unten, um ein Statusraster anzuzeigen, in der alle ausgeführten Schritte in der entsprechenden Reihenfolge aufgeführt sind, gefolgt vom derzeit laufenden Vorgang.</span><span class="sxs-lookup"><span data-stu-id="142a5-107">Click the down arrow to display a progress grid that lists any completed steps, in order, followed by the current in-progress operation.</span></span> <span data-ttu-id="142a5-108">Das Raster enthält die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="142a5-108">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="142a5-109">**Name**</span><span class="sxs-lookup"><span data-stu-id="142a5-109">**Name**</span></span>  
 <span data-ttu-id="142a5-110">Zeigt einen Ausdruck an, der einen bestimmten Schritt beschreibt.</span><span class="sxs-lookup"><span data-stu-id="142a5-110">Displays a phrase that describes a specific step.</span></span>  
  
 <span data-ttu-id="142a5-111">**Status**</span><span class="sxs-lookup"><span data-stu-id="142a5-111">**Status**</span></span>  
 <span data-ttu-id="142a5-112">Gibt das Ergebnis ausgeführter Schritte und den Prozentsatz des Abschlusses des aktuellen Schritts wie folgt an:</span><span class="sxs-lookup"><span data-stu-id="142a5-112">Indicates the outcome of completed steps and the percentage of completion of the current step, as follows:</span></span>  
  
|<span data-ttu-id="142a5-113">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="142a5-113">Result</span></span>|<span data-ttu-id="142a5-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="142a5-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="142a5-115">**Fehler**</span><span class="sxs-lookup"><span data-stu-id="142a5-115">**Error**</span></span>|<span data-ttu-id="142a5-116">Gibt an, dass beim Vorgang für diesen Schritt ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="142a5-116">Indicates the operation for this step experienced an error.</span></span> <span data-ttu-id="142a5-117">Klicken Sie auf den Link, um ein Meldungsdialogfeld anzuzeigen, das den Fehler beschreibt.</span><span class="sxs-lookup"><span data-stu-id="142a5-117">Click the link to display a message dialog box that describes the error.</span></span>|  
|<span data-ttu-id="142a5-118">**In Bearbeitung (** *abgeschlossener Prozentsatz* **)**</span><span class="sxs-lookup"><span data-stu-id="142a5-118">**In Progress (** *percentage-completed* **)**</span></span>|<span data-ttu-id="142a5-119">Gibt an, dass der Vorgang jetzt auftritt, und schätzt den Prozentsatz dieses Schritts, der abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="142a5-119">Indicates that the operation is occurring now and estimates the percentage of this step that has completed.</span></span>|  
|<span data-ttu-id="142a5-120">**Erfolgreich**</span><span class="sxs-lookup"><span data-stu-id="142a5-120">**Success**</span></span>|<span data-ttu-id="142a5-121">Gibt an, dass der Vorgang für diesen Schritt erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="142a5-121">Indicates the operation for this step completed successfully.</span></span>|  
  
 <span data-ttu-id="142a5-122">**Weniger Details**</span><span class="sxs-lookup"><span data-stu-id="142a5-122">**Fewer Details**</span></span>  
 <span data-ttu-id="142a5-123">Klicken Sie, um das Statusraster auszublenden.</span><span class="sxs-lookup"><span data-stu-id="142a5-123">Click to hide the progress grid.</span></span>  
  
 <span data-ttu-id="142a5-124">**Abbrechen**</span><span class="sxs-lookup"><span data-stu-id="142a5-124">**Cancel**</span></span>  
 <span data-ttu-id="142a5-125">Klicken Sie, um verbleibende Vorgänge zu überspringen, und beenden Sie dann den Assistenten.</span><span class="sxs-lookup"><span data-stu-id="142a5-125">Click to skip any remaining operations and then exit the wizard.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="142a5-126">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="142a5-126">Related Tasks</span></span>  
  
-   [<span data-ttu-id="142a5-127">Verwenden des Dialogfelds Neue Verfügbarkeitsgruppe &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="142a5-127">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="142a5-128">Verwenden des Assistenten zum Hinzufügen von Replikaten zu Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="142a5-128">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="142a5-129">Verwenden des Assistenten zum Hinzufügen von Datenbanken zu Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="142a5-129">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
-   [<span data-ttu-id="142a5-130">Verwenden des Assistenten für Failover-Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="142a5-130">Use the Fail Over Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-fail-over-availability-group-wizard-sql-server-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="142a5-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="142a5-131">See Also</span></span>  
 [<span data-ttu-id="142a5-132">Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="142a5-132">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
