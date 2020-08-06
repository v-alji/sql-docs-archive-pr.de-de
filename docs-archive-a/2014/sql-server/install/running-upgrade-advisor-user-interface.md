---
title: Ausführen des Upgrade Advisors (Benutzeroberfläche) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor Report Viewer
- Upgrade Advisor [SQL Server], running
- launching Upgrade Advisor
- Upgrade Advisor Analysis Wizard
- starting Upgrade Advisor
- SQL Server Upgrade Advisor, running
ms.assetid: 7f47c9b3-88d3-43d6-837e-f157b49a55ac
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: a5e47ef2b8183823dff884e114adc420e371adf3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622386"
---
# <a name="running-upgrade-advisor-user-interface"></a><span data-ttu-id="cec0c-102">Ausführen des Upgrade Advisors (Benutzeroberfläche)</span><span class="sxs-lookup"><span data-stu-id="cec0c-102">Running Upgrade Advisor (User Interface)</span></span>
  <span data-ttu-id="cec0c-103">Sie können den Upgrade Advisor ausführen, um lokale oder Remotekomponenten während der Upgradeplanung zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="cec0c-103">You can run Upgrade Advisor to analyze local or remote components during upgrade planning.</span></span> <span data-ttu-id="cec0c-104">Der Upgrade Advisor erzeugt einen Bericht für jede Komponente und Instanz, die analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="cec0c-104">Upgrade Advisor produces a report for each component and instance that is analyzed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cec0c-105">Der Upgrade Advisor analysiert keine Remoteinstanzen von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cec0c-105">Upgrade Advisor does not analyze remote instances of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="cec0c-106">Um eine Instanz von [!INCLUDE[ssRS](../../includes/ssrs.md)] zu analysieren, muss der Upgrade Advisor auf dem Computer installiert sein, auf dem [!INCLUDE[ssRS](../../includes/ssrs.md)] installiert ist.</span><span class="sxs-lookup"><span data-stu-id="cec0c-106">To analyze an instance of [!INCLUDE[ssRS](../../includes/ssrs.md)], Upgrade Advisor must be installed on the computer where [!INCLUDE[ssRS](../../includes/ssrs.md)] is installed.</span></span>  
>   
>  <span data-ttu-id="cec0c-107">Um Integration Services zu analysieren [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , muss [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] installiert und [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] auf dem gleichen Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="cec0c-107">To analyze [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Integration Services, you must have the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] installed and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed on the same computer.</span></span>  
  
## <a name="running-the-upgrade-advisor-analysis-wizard"></a><span data-ttu-id="cec0c-108">Ausführen des Analyse-Assistenten des Upgrade Advisors</span><span class="sxs-lookup"><span data-stu-id="cec0c-108">Running the Upgrade Advisor Analysis Wizard</span></span>  
 <span data-ttu-id="cec0c-109">Das Ausführen des Analyse-Assistenten des Upgrade Advisors erfolgt in sechs Schritten:</span><span class="sxs-lookup"><span data-stu-id="cec0c-109">Running the Upgrade Advisor Analysis Wizard has six steps:</span></span>  
  
1.  <span data-ttu-id="cec0c-110">Starten Sie den Assistenten von der Startseite des Upgrade Advisors.</span><span class="sxs-lookup"><span data-stu-id="cec0c-110">Launch the wizard from the Upgrade Advisor start page.</span></span>  
  
2.  <span data-ttu-id="cec0c-111">Identifizieren Sie die Server und Komponenten, die analysiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cec0c-111">Identify server and components to analyze.</span></span>  
  
3.  <span data-ttu-id="cec0c-112">Erfassen Sie Authentifizierungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="cec0c-112">Gather authentication information.</span></span>  
  
4.  <span data-ttu-id="cec0c-113">Sammeln Sie zusätzliche Parameter auf der Grundlage des Komponententyps.</span><span class="sxs-lookup"><span data-stu-id="cec0c-113">Gather additional parameters based on component type.</span></span>  
  
5.  <span data-ttu-id="cec0c-114">Analysieren Sie ausgewählte Komponenten.</span><span class="sxs-lookup"><span data-stu-id="cec0c-114">Analyze selected components.</span></span>  
  
6.  <span data-ttu-id="cec0c-115">Generieren Sie einen Bericht der Upgradeprobleme.</span><span class="sxs-lookup"><span data-stu-id="cec0c-115">Generate report of upgrade issues.</span></span>  
  
 <span data-ttu-id="cec0c-116">Weitere Informationen zum Analyse-Assistenten des Upgrade Advisors finden Sie unter Gewusst [wie: Ausführen des Analyse-Assistenten für den Upgrade Advisor](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="cec0c-116">For more information about the Upgrade Advisor Analysis Wizard, see [How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md).</span></span>  
  
 <span data-ttu-id="cec0c-117">Spezifische Informationen, die für die einzelnen Schritte erforderlich sind, finden Sie unter [Referenz zur Benutzeroberfläche des Upgrade Advisors](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md).</span><span class="sxs-lookup"><span data-stu-id="cec0c-117">For specific information that is required for each step, see [Upgrade Advisor User Interface Reference](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md).</span></span>  
  
## <a name="running-the-upgrade-advisor-report-viewer"></a><span data-ttu-id="cec0c-118">Ausführen des Berichts-Viewers des Upgrade Advisors</span><span class="sxs-lookup"><span data-stu-id="cec0c-118">Running the Upgrade Advisor Report Viewer</span></span>  
 <span data-ttu-id="cec0c-119">Mit dem Berichts-Viewer des Upgrade Advisors können Sie Berichte anzeigen, die vom Analyse-Assistenten des Upgrade Advisors generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="cec0c-119">You use the Upgrade Advisor Report Viewer to view reports generated by the Upgrade Advisor Analysis Wizard.</span></span> <span data-ttu-id="cec0c-120">Wenn der Bericht geladen wird, können Sie die Komponenten des Berichts nach den folgenden Kriterien filtern:</span><span class="sxs-lookup"><span data-stu-id="cec0c-120">When the report is loaded, you can filter the components of the report by the following factors:</span></span>  
  
-   <span data-ttu-id="cec0c-121">Alle Probleme</span><span class="sxs-lookup"><span data-stu-id="cec0c-121">All issues</span></span>  
  
-   <span data-ttu-id="cec0c-122">Alle Ugradeprobleme</span><span class="sxs-lookup"><span data-stu-id="cec0c-122">All upgrade issues</span></span>  
  
-   <span data-ttu-id="cec0c-123">Probleme vor dem Upgrade</span><span class="sxs-lookup"><span data-stu-id="cec0c-123">Pre-upgrade issues</span></span>  
  
-   <span data-ttu-id="cec0c-124">Alle Migrationsprobleme</span><span class="sxs-lookup"><span data-stu-id="cec0c-124">All migration issues</span></span>  
  
-   <span data-ttu-id="cec0c-125">Behobene Probleme</span><span class="sxs-lookup"><span data-stu-id="cec0c-125">Resolved issues</span></span>  
  
-   <span data-ttu-id="cec0c-126">Ungelöste Probleme</span><span class="sxs-lookup"><span data-stu-id="cec0c-126">Unresolved issues</span></span>  
  
 <span data-ttu-id="cec0c-127">Schrittweise Anweisungen zur Verwendung des Berichts-Viewers finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="cec0c-127">For step-by-step instructions for using the report viewer, see the following topics:</span></span>  
  
-   [<span data-ttu-id="cec0c-128">Gewusst wie: Anzeigen eines Berichts des Upgrade Advisors</span><span class="sxs-lookup"><span data-stu-id="cec0c-128">How to: View an Upgrade Advisor Report</span></span>](../../../2014/sql-server/install/how-to-view-an-upgrade-advisor-report.md)  
  
-   [<span data-ttu-id="cec0c-129">Gewusst wie: Filtern von Berichten</span><span class="sxs-lookup"><span data-stu-id="cec0c-129">How to: Filter Reports</span></span>](../../../2014/sql-server/install/how-to-filter-reports.md)  
  
-   [<span data-ttu-id="cec0c-130">Gewusst wie: Exportieren von Berichten</span><span class="sxs-lookup"><span data-stu-id="cec0c-130">How to: Export Reports</span></span>](../../../2014/sql-server/install/how-to-export-reports.md)  
  
## <a name="see-also"></a><span data-ttu-id="cec0c-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cec0c-131">See Also</span></span>  
 <span data-ttu-id="cec0c-132">[Vorgehensweise: Ausführen des Analyse-Assistenten des Upgrade Advisors](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="cec0c-132">[How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span></span>  
 <span data-ttu-id="cec0c-133">[Referenz zur Benutzeroberfläche des Upgrade Advisors](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md) </span><span class="sxs-lookup"><span data-stu-id="cec0c-133">[Upgrade Advisor User Interface Reference](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md) </span></span>  
 <span data-ttu-id="cec0c-134">[Beheben von Upgradeproblemen](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="cec0c-134">[Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="cec0c-135">Arbeiten mit dem Upgrade Advisor</span><span class="sxs-lookup"><span data-stu-id="cec0c-135">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
