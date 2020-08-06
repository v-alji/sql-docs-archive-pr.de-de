---
title: Aktualisieren der Pakete (SSIS-Paket Upgrade-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.is.upgradewizard.upgradingpackage.f1
ms.assetid: cdb842e3-2e59-4ede-b127-be4fde46875c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d13228dabc1566b592733da4afd8ebde3671ee0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609941"
---
# <a name="upgrading-the-packages-ssis-package-upgrade-wizard"></a><span data-ttu-id="d8f90-102">Pakete werden aktualisiert (SSIS Paketupgrade-Assistent)</span><span class="sxs-lookup"><span data-stu-id="d8f90-102">Upgrading the Packages (SSIS Package Upgrade Wizard)</span></span>
  <span data-ttu-id="d8f90-103">Verwenden Sie die Seite **Pakete werden aktualisiert** , um den Status der Paketaktualisierung anzuzeigen und um den Aktualisierungsprozess unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="d8f90-103">Use the **Upgrading the Packages** page to view the progress of package upgrade and to interrupt the upgrade process.</span></span> <span data-ttu-id="d8f90-104">Der [!INCLUDE[ssIS](../includes/ssis-md.md)] Paketaktualisierungs-Assistent aktualisiert die ausgewählten Pakete nacheinander.</span><span class="sxs-lookup"><span data-stu-id="d8f90-104">The [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard upgrades the selected packages one by one.</span></span>  
  
 <span data-ttu-id="d8f90-105">**So zeigen Sie aktualisierte Pakete an, die in einer SQL Server-Datenbank oder dem Paketspeicher gespeichert wurden**</span><span class="sxs-lookup"><span data-stu-id="d8f90-105">**To view upgraded packages that were saved to a SQL Server database or to the package store**</span></span>  
  
-   <span data-ttu-id="d8f90-106">Stellen Sie in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]im Objekt-Explorer eine Verbindung mit der lokalen Instanz von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]her, und erweitern Sie dann den Knoten **Gespeicherte Pakete** , um die aktualisierten Pakete anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d8f90-106">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], in Object Explorer, connect to the local instance of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], and then expand the **Stored Packages** node to see the packages that were upgraded.</span></span>  
  
 <span data-ttu-id="d8f90-107">**So zeigen Sie aktualisierte Pakete an, die in SQL Server-Datentools aktualisiert wurden**</span><span class="sxs-lookup"><span data-stu-id="d8f90-107">**To view upgraded packages that were upgraded from SQL Server Data Tools**</span></span>  
  
-   <span data-ttu-id="d8f90-108">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]im Projektmappen-Explorer das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt, und erweitern Sie dann den Knoten **SSIS-Pakete** , um die aktualisierten Pakete anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d8f90-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in Solution Explorer, open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, and then expand the **SSIS Packages** node to see the upgraded packages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d8f90-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="d8f90-109">Options</span></span>  
 <span data-ttu-id="d8f90-110">**Meldungs Bereich**</span><span class="sxs-lookup"><span data-stu-id="d8f90-110">**Message pane**</span></span>  
 <span data-ttu-id="d8f90-111">Zeigt während der Aktualisierung Statusmeldungen und Zusammenfassungsinformationen an.</span><span class="sxs-lookup"><span data-stu-id="d8f90-111">Displays progress messages and summary information during the upgrade process.</span></span>  
  
 <span data-ttu-id="d8f90-112">**Aktion**</span><span class="sxs-lookup"><span data-stu-id="d8f90-112">**Action**</span></span>  
 <span data-ttu-id="d8f90-113">Zeigen Sie die Aktionen in der Aktualisierung an.</span><span class="sxs-lookup"><span data-stu-id="d8f90-113">View the actions in the upgrade.</span></span>  
  
 <span data-ttu-id="d8f90-114">**Status**</span><span class="sxs-lookup"><span data-stu-id="d8f90-114">**Status**</span></span>  
 <span data-ttu-id="d8f90-115">Zeigen Sie das Ergebnis der einzelnen Aktionen an.</span><span class="sxs-lookup"><span data-stu-id="d8f90-115">View the result of each action.</span></span>  
  
 <span data-ttu-id="d8f90-116">**Meldung**</span><span class="sxs-lookup"><span data-stu-id="d8f90-116">**Message**</span></span>  
 <span data-ttu-id="d8f90-117">Zeigen Sie die Fehlermeldungen an, die die einzelnen Aktionen generieren.</span><span class="sxs-lookup"><span data-stu-id="d8f90-117">View the error messages that each action generates.</span></span>  
  
 <span data-ttu-id="d8f90-118">**Beenden**</span><span class="sxs-lookup"><span data-stu-id="d8f90-118">**Stop**</span></span>  
 <span data-ttu-id="d8f90-119">Beenden Sie die Paketaktualisierung.</span><span class="sxs-lookup"><span data-stu-id="d8f90-119">Stop the package upgrade.</span></span>  
  
 <span data-ttu-id="d8f90-120">**Report**</span><span class="sxs-lookup"><span data-stu-id="d8f90-120">**Report**</span></span>  
 <span data-ttu-id="d8f90-121">Wählen Sie aus, wie Sie mit dem Bericht, der die Ergebnisse der Paketaktualisierung enthält, verfahren möchten:</span><span class="sxs-lookup"><span data-stu-id="d8f90-121">Select what you want to do with the report that contains the results of the package upgrade:</span></span>  
  
-   <span data-ttu-id="d8f90-122">Den Bericht online anzeigen</span><span class="sxs-lookup"><span data-stu-id="d8f90-122">View the report online.</span></span>  
  
-   <span data-ttu-id="d8f90-123">Den Bericht in einer Datei speichern</span><span class="sxs-lookup"><span data-stu-id="d8f90-123">Save the report to a file.</span></span>  
  
-   <span data-ttu-id="d8f90-124">Den Bericht in die Zwischenablage speichern.</span><span class="sxs-lookup"><span data-stu-id="d8f90-124">Copy the report to the Clipboard</span></span>  
  
-   <span data-ttu-id="d8f90-125">Den Bericht als E-Mail-Nachricht versenden.</span><span class="sxs-lookup"><span data-stu-id="d8f90-125">Send the report as an e-mail message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8f90-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d8f90-126">See Also</span></span>  
 [<span data-ttu-id="d8f90-127">Aktualisieren von Integration Services-Paketen</span><span class="sxs-lookup"><span data-stu-id="d8f90-127">Upgrade Integration Services Packages</span></span>](install-windows/upgrade-integration-services-packages.md)  
  
  
