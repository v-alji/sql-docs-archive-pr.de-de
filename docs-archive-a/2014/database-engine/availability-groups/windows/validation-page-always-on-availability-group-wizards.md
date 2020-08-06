---
title: Validierungs Seite (AlwaysOn-Verfügbarkeits Gruppen-Assistenten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.newagwizard.validation.f1
- sql12.swb.addreplicawizard.validation.f1
- sql12.swb.adddatabasewizard.validation.f1
helpviewer_keywords:
- ', listeners'
ms.assetid: c8971556-240c-491a-bc86-9cc72f71a3dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f2010074a357932f8af7358a05ee6ed16f5c0881
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608864"
---
# <a name="validation-page-alwayson-availability-group-wizards"></a><span data-ttu-id="2315e-102">Seite 'Überprüfung' (AlwaysOn-Verfügbarkeitsgruppen-Assistenten)</span><span class="sxs-lookup"><span data-stu-id="2315e-102">Validation Page (AlwaysOn Availability Group Wizards)</span></span>
  <span data-ttu-id="2315e-103">In diesem Hilfethema werden die Optionen der Seite **Überprüfung** beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2315e-103">This help topic describes the options of the **Validation** page.</span></span> <span data-ttu-id="2315e-104">Dieses Thema gilt für [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)], [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)]und [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2315e-104">This topic applies to the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)], [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)], and [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="2315e-105">Verwenden Sie diese Seite, um zu überprüfen, ob die Umgebung alle auf vorherigen Seiten des Assistenten festgelegte Konfigurationsoptionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2315e-105">Use this page to validate that your environment supports all the configuration choices you made on previous pages of the wizard.</span></span>  
  
##  <a name="validation-page-options"></a><a name="PageOptions"></a><span data-ttu-id="2315e-106">Optionen für die Validierungs Seite</span><span class="sxs-lookup"><span data-stu-id="2315e-106">Validation Page Options</span></span>  
 <span data-ttu-id="2315e-107">**Ergebnisse der Verfügbarkeitsgruppenüberprüfung.**</span><span class="sxs-lookup"><span data-stu-id="2315e-107">**Results of availability group validation.**</span></span>  
 <span data-ttu-id="2315e-108">Dieses Raster zeigt die Ergebnisse jedes ausgeführten Überprüfungsschritts an.</span><span class="sxs-lookup"><span data-stu-id="2315e-108">This grid displays the results of each completed validation step.</span></span> <span data-ttu-id="2315e-109">Es gibt folgende Rasterspalten:</span><span class="sxs-lookup"><span data-stu-id="2315e-109">The grid columns are as follows:</span></span>  
  
 <span data-ttu-id="2315e-110">**Name**</span><span class="sxs-lookup"><span data-stu-id="2315e-110">**Name**</span></span>  
 <span data-ttu-id="2315e-111">Zeigt einen Ausdruck an, der einen bestimmten Schritt beschreibt.</span><span class="sxs-lookup"><span data-stu-id="2315e-111">Displays a phrase that describes a specific step.</span></span>  
  
 <span data-ttu-id="2315e-112">**Ergebnis**</span><span class="sxs-lookup"><span data-stu-id="2315e-112">**Result**</span></span>  
 <span data-ttu-id="2315e-113">Zeigt einen der folgenden Linktexte an.</span><span class="sxs-lookup"><span data-stu-id="2315e-113">Displays one of the following hyperlink texts.</span></span> <span data-ttu-id="2315e-114">Klicken Sie auf den Link, um weitere Informationen zum Ergebnis eines bestimmten Überprüfungsschritts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2315e-114">For more information about the result of given validation step, click the hyperlink.</span></span>  
  
|<span data-ttu-id="2315e-115">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="2315e-115">Result</span></span>|<span data-ttu-id="2315e-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2315e-116">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2315e-117">**Fehler**</span><span class="sxs-lookup"><span data-stu-id="2315e-117">**Error**</span></span>|<span data-ttu-id="2315e-118">Gibt an, dass der Überprüfungsschritt fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="2315e-118">Indicates that the validation step failed.</span></span> <span data-ttu-id="2315e-119">Klicken Sie auf den Link, um die Fehlermeldung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2315e-119">Click the link to view the error message.</span></span>|  
|<span data-ttu-id="2315e-120">**Übersprungen**</span><span class="sxs-lookup"><span data-stu-id="2315e-120">**Skipped**</span></span>|<span data-ttu-id="2315e-121">Gibt an, dass der Überprüfungsschritt ausgelassen wurde, da er für die Optionen nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="2315e-121">Indicates that the validation step was skipped because it is not required by your selections.</span></span> <span data-ttu-id="2315e-122">Klicken Sie auf den Link, um die Ursache für das Auslassen eines Schritts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2315e-122">Click the link to view the reason that a step was skipped.</span></span>|  
|<span data-ttu-id="2315e-123">**Erfolgreich**</span><span class="sxs-lookup"><span data-stu-id="2315e-123">**Success**</span></span>|<span data-ttu-id="2315e-124">Gibt an, dass der Überprüfungsschritt erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="2315e-124">Indicates that the validation step completed successfully</span></span>|  
|<span data-ttu-id="2315e-125">**Warnung**</span><span class="sxs-lookup"><span data-stu-id="2315e-125">**Warning**</span></span>|<span data-ttu-id="2315e-126">Zeigt ein potenzielles Problem mit der Verfügbarkeitsgruppenkonfiguration an.</span><span class="sxs-lookup"><span data-stu-id="2315e-126">Indicates a potential issue with the availability group configuration.</span></span>  <span data-ttu-id="2315e-127">Klicken Sie auf den Link, um die Warnmeldung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2315e-127">Click the link to view the warning message.</span></span>|  
  
 <span data-ttu-id="2315e-128">**Überprüfung erneut ausführen**</span><span class="sxs-lookup"><span data-stu-id="2315e-128">**Re-run Validation**</span></span>  
 <span data-ttu-id="2315e-129">Klicken Sie, um die Überprüfungsschritte zu wiederholen, wenn Sie außerhalb des Assistenten als Reaktion auf einen Überprüfungsfehler eine Änderung vornehmen.</span><span class="sxs-lookup"><span data-stu-id="2315e-129">Click to repeat the validation steps if you make a change outside of the wizard in response to a validation error.</span></span>  
  

  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="2315e-130">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="2315e-130">Related Tasks</span></span>  
  
-   [<span data-ttu-id="2315e-131">Verwenden des Dialogfelds Neue Verfügbarkeitsgruppe &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2315e-131">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="2315e-132">Verwenden des Assistenten zum Hinzufügen von Replikaten zu Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2315e-132">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="2315e-133">Verwenden des Assistenten zum Hinzufügen von Datenbanken zu Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2315e-133">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
 
  
## <a name="see-also"></a><span data-ttu-id="2315e-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2315e-134">See Also</span></span>  
 [<span data-ttu-id="2315e-135">Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2315e-135">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
