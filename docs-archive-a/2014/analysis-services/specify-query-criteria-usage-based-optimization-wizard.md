---
title: Abfrage Kriterien angeben (Assistent für Verwendungs basierte Optimierung) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.usagebasedoptimizationwizard.specifyquerycriteria.f1
ms.assetid: 3193adc2-af9f-4234-a4cc-dea0c280a724
author: minewiskan
ms.author: owend
ms.openlocfilehash: f3b93034a089ff3121155e35de4cec96846824a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615618"
---
# <a name="specify-query-criteria-usage-based-optimization-wizard"></a><span data-ttu-id="c9e94-102">Abfragekriterien angeben (Assistent für verwendungsbasierte Optimierung)</span><span class="sxs-lookup"><span data-stu-id="c9e94-102">Specify Query Criteria (Usage-Based Optimization Wizard)</span></span>
  <span data-ttu-id="c9e94-103">Über die Seite **Abfragekriterien festlegen** können Sie ein oder mehrere Filteroptionen auswählen, um zu optimierende Abfragen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c9e94-103">Use the **Specify Query Criteria** page to choose one or more filter options in order to identify queries to optimize.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9e94-104">Diese Seite ist deaktiviert, wenn [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] keine Verbindung mit dem Abfrageprotokoll herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="c9e94-104">This page is disabled if [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cannot connect to the query log.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c9e94-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="c9e94-105">Options</span></span>  
 <span data-ttu-id="c9e94-106">**Abfrageprotokollstatistik**</span><span class="sxs-lookup"><span data-stu-id="c9e94-106">**Query log statistics**</span></span>  
 <span data-ttu-id="c9e94-107">Zeigt Informationen zu den Abfragen an, die in dem Abfrageprotokoll für die ausgewählten Partitionen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="c9e94-107">Displays information about the queries stored in the query log for the selected partitions.</span></span> <span data-ttu-id="c9e94-108">Folgende Elemente werden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="c9e94-108">The following items are displayed:</span></span>  
  
|<span data-ttu-id="c9e94-109">Begriff</span><span class="sxs-lookup"><span data-stu-id="c9e94-109">Term</span></span>|<span data-ttu-id="c9e94-110">Definition</span><span class="sxs-lookup"><span data-stu-id="c9e94-110">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="c9e94-111">**Abfragen gesamt**</span><span class="sxs-lookup"><span data-stu-id="c9e94-111">**Total queries**</span></span>|<span data-ttu-id="c9e94-112">Zeigt Informationen zur Gesamtzahl der Abfragen an, die in dem Abfrageprotokoll für die ausgewählten Partitionen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="c9e94-112">Displays the total number of queries stored in the query log for the selected partitions.</span></span>|  
|<span data-ttu-id="c9e94-113">**Unterschiedliche Abfragen**</span><span class="sxs-lookup"><span data-stu-id="c9e94-113">**Distinct queries**</span></span>|<span data-ttu-id="c9e94-114">Zeigt Informationen zur Gesamtzahl der unterschiedlichen Abfragen an, die in dem Abfrageprotokoll für die ausgewählten Partitionen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="c9e94-114">Displays the number of distinct queries stored in the query log for the selected partitions.</span></span>|  
|<span data-ttu-id="c9e94-115">**Unterschiedliche Benutzer**</span><span class="sxs-lookup"><span data-stu-id="c9e94-115">**Distinct users**</span></span>|<span data-ttu-id="c9e94-116">Zeigt Informationen zur Gesamtzahl der unterschiedlichen Benutzer an, die Abfragen zugeordnet sind, die in dem Abfrageprotokoll für die ausgewählten Partitionen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="c9e94-116">Displays the total number of distinct users associated with queries stored in the query log for the selected partitions.</span></span>|  
|<span data-ttu-id="c9e94-117">**Durchschnittliche Reaktionszeit**</span><span class="sxs-lookup"><span data-stu-id="c9e94-117">**Average response time**</span></span>|<span data-ttu-id="c9e94-118">Zeigt Informationen zur durchschnittlichen Antwortzeit für Abfragen an, die in dem Abfrageprotokoll für die ausgewählten Partitionen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="c9e94-118">Displays the average response time for queries stored in the query log for the selected partitions.</span></span>|  
  
 <span data-ttu-id="c9e94-119">**Startdatum**</span><span class="sxs-lookup"><span data-stu-id="c9e94-119">**Beginning date**</span></span>  
 <span data-ttu-id="c9e94-120">Filtert Abfragen im Abfrageprotokoll auf der Grundlage eines Startdatums und einer Startzeit.</span><span class="sxs-lookup"><span data-stu-id="c9e94-120">Filters queries in the query log based on a starting date and time.</span></span> <span data-ttu-id="c9e94-121">Wählen Sie ein Datum aus der Dropdownliste aus, oder geben Sie ein Datum ein.</span><span class="sxs-lookup"><span data-stu-id="c9e94-121">Choose or type a date in the dropdown list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9e94-122"> Wenn die Option **Enddatum** nicht ausgewählt ist, werden alle Abfragen im Abfrageprotokoll einbezogen, die am oder nach dem für diese Option angegebenen Datum protokolliert wurden.</span><span class="sxs-lookup"><span data-stu-id="c9e94-122">If **Ending date** is not selected, all queries in the query log on or after the date and time specified for this option are considered.</span></span>  
  
 <span data-ttu-id="c9e94-123">**Enddatum**</span><span class="sxs-lookup"><span data-stu-id="c9e94-123">**Ending date**</span></span>  
 <span data-ttu-id="c9e94-124">Filtert Abfragen im Abfrageprotokoll auf der Grundlage eines Enddatums und einer Beendigungszeit.</span><span class="sxs-lookup"><span data-stu-id="c9e94-124">Filters queries in the query log based on an ending date and time.</span></span> <span data-ttu-id="c9e94-125">Wählen Sie ein Datum aus der Dropdownliste aus, oder geben Sie ein Datum ein.</span><span class="sxs-lookup"><span data-stu-id="c9e94-125">Choose or type a date in the dropdown list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9e94-126"> Wenn die Option **Startdatum** nicht ausgewählt ist, werden alle Abfragen im Abfrageprotokoll einbezogen, die am oder vor dem für diese Option angegebenen Datum protokolliert wurden.</span><span class="sxs-lookup"><span data-stu-id="c9e94-126">If **Beginning date** is not selected, all queries in the query log on or before the date and time specified for this option are considered.</span></span>  
  
 <span data-ttu-id="c9e94-127">**Benutzer**</span><span class="sxs-lookup"><span data-stu-id="c9e94-127">**Users**</span></span>  
 <span data-ttu-id="c9e94-128">Filtert Abfragen im Abfrageprotokoll auf der Grundlage einer angegebenen Gruppe von Benutzern.</span><span class="sxs-lookup"><span data-stu-id="c9e94-128">Filters queries in the query log based on a specified set of users.</span></span> <span data-ttu-id="c9e94-129">Klicken Sie auf die Auslassungspunkte (**...**), um das Dialogfeld **Benutzerauswahl** anzuzeigen und Benutzer auszuwählen, nach denen die Abfragen gefiltert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c9e94-129">Click the ellipsis (**...**) button to display the **User Selection** dialog box and choose users on which to filter queries.</span></span> <span data-ttu-id="c9e94-130">Weitere Informationen zum Dialogfeld **Benutzerauswahl** finden Sie unter [Dialogfeld „Benutzerauswahl“ &#40;Analysis Services – Mehrdimensionale Daten&#41;](user-selection-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="c9e94-130">For more information about the **User Selection** dialog box, see [User Selection Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](user-selection-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="c9e94-131">**Häufigste Abfragen**</span><span class="sxs-lookup"><span data-stu-id="c9e94-131">**Most frequent queries**</span></span>  
 <span data-ttu-id="c9e94-132">Filtert die Abfragen im Abfrageprotokoll auf der Grundlage des höchsten Prozentanteils der am meisten ausgeführten unterschiedlichen Abfragen für die ausgewählten Partitionen.</span><span class="sxs-lookup"><span data-stu-id="c9e94-132">Filters queries in the query log based on the topmost percentage of the distinct queries most often run for the selected partitions.</span></span> <span data-ttu-id="c9e94-133">Wählen Sie einen Prozentwert im Textfeld aus, oder geben Sie einen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="c9e94-133">Choose or type a percent value in the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9e94-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c9e94-134">See Also</span></span>  
 <span data-ttu-id="c9e94-135">[Assistent für Verwendungs basierte Optimierung (F1-Hilfe)](usage-based-optimization-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="c9e94-135">[Usage-Based Optimization Wizard F1 Help](usage-based-optimization-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="c9e94-136">Analysis Services Assistenten &#40;Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="c9e94-136">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
