---
title: Fortschritt des Upgrade Advisors | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor [SQL Server], analysis progress status
- analyzing system [Upgrade Advisor], progress information
- SQL Server Upgrade Advisor, analysis progress status
- monitoring analysis progress
- progress information [Upgrade Advisor]
- status information [Upgrade Advisor]
ms.assetid: a9e3d1c8-d492-4beb-93c7-f1bc40d4a910
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b504b8f1c8392ad2cf55837dc65bbb2f019d6f48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617411"
---
# <a name="upgrade-advisor-progress"></a><span data-ttu-id="e5285-102">Upgrade Advisor-Status</span><span class="sxs-lookup"><span data-stu-id="e5285-102">Upgrade Advisor Progress</span></span>
  <span data-ttu-id="e5285-103">Die Analyse des Upgrade Advisor wird mit einem dedizierten Analyseprogramm gestartet, das eine Analyse jeder von Ihnen ausgewählten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Komponente durchführt.</span><span class="sxs-lookup"><span data-stu-id="e5285-103">Upgrade Advisor analysis starts with a dedicated analyzer that performs an analysis of each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component that you selected.</span></span> <span data-ttu-id="e5285-104">Wenn Komponenten analysiert werden, **wird der Fortschritt im** Dialogfeld "Status" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e5285-104">As components are analyzed, progress is reported in the **Progress** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e5285-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="e5285-105">Options</span></span>  
 <span data-ttu-id="e5285-106">**Aktion**</span><span class="sxs-lookup"><span data-stu-id="e5285-106">**Action**</span></span>  
 <span data-ttu-id="e5285-107">Gibt die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Komponente an, die für die Analyse ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="e5285-107">Specifies the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component that is selected for analysis.</span></span>  
  
 <span data-ttu-id="e5285-108">**Status**</span><span class="sxs-lookup"><span data-stu-id="e5285-108">**Status**</span></span>  
 <span data-ttu-id="e5285-109">Zeigt den von der Statusschnittstelle der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Komponente zurückgegebenen Statuswert an.</span><span class="sxs-lookup"><span data-stu-id="e5285-109">Displays the status value returned from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component progress interface.</span></span>  
  
 <span data-ttu-id="e5285-110">**Meldung**</span><span class="sxs-lookup"><span data-stu-id="e5285-110">**Message**</span></span>  
 <span data-ttu-id="e5285-111">Zeigt Meldungen zu Fehlern und über den Erfolg bzw. das Fehlschlagen von Vorgängen. Die Meldungen werden vom jeweiligen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Analyzer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e5285-111">Displays error, failure, or success messages returned from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] individual analyzer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e5285-112">Wenn die Analyse zu lange dauert, können Sie sie anhalten, den Analyse-Assistenten von Upgrade Advisor beenden und den Assistenten dann erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="e5285-112">If the analysis is taking too long, you can stop the analysis, exit the Upgrade Advisor Analysis Wizard, and then rerun the wizard.</span></span> <span data-ttu-id="e5285-113">Um die Analysezeit zu reduzieren, wählen Sie weniger Komponenten zum Scannen aus.</span><span class="sxs-lookup"><span data-stu-id="e5285-113">To reduce analysis time, select fewer components to scan.</span></span>  
  
 <span data-ttu-id="e5285-114">Wenn die Analyse abgeschlossen wurde, wird der Bericht in eine Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="e5285-114">When analysis is complete, the report is written to a file.</span></span> <span data-ttu-id="e5285-115">Sie können den Bericht anzeigen, indem Sie auf **Bericht starten** klicken, um den Berichts-Viewer auf dieser Seite zu starten.</span><span class="sxs-lookup"><span data-stu-id="e5285-115">You can view the report by clicking **Launch Report** to launch the report viewer from this page.</span></span> <span data-ttu-id="e5285-116">Wenn Sie den Bericht zu einem späteren Zeitpunkt anzeigen möchten, können Sie den **Berichts-Viewer des Upgrade Advisors** auf der Startseite des Upgrade Advisors öffnen.</span><span class="sxs-lookup"><span data-stu-id="e5285-116">If you want to view the report later, you can open the **Upgrade Advisor Report Viewer** from the Upgrade Advisor start page.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e5285-117">Vorherige Berichte werden jedes Mal gespeichert, wenn Sie einen Server analysieren.</span><span class="sxs-lookup"><span data-stu-id="e5285-117">Previous reports are saved every time you analyze a server.</span></span> <span data-ttu-id="e5285-118">Die Berichte werden mit dem Zeitstempel für den Dateinamen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e5285-118">The reports are saved using the timestamp for the file name.</span></span> <span data-ttu-id="e5285-119">Der Berichts-Viewer zeigt die letzten fünf gespeicherten Berichte an.</span><span class="sxs-lookup"><span data-stu-id="e5285-119">The report viewer displays the latest five saved reports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5285-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e5285-120">See Also</span></span>  
 <span data-ttu-id="e5285-121">[Vorgehensweise: Starten des Upgrade Advisors](../../../2014/sql-server/install/how-to-launch-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="e5285-121">[How to: Launch Upgrade Advisor](../../../2014/sql-server/install/how-to-launch-upgrade-advisor.md) </span></span>  
 <span data-ttu-id="e5285-122">[Vorgehensweise: Ausführen des Analyse-Assistenten des Upgrade Advisors](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="e5285-122">[How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span></span>  
 <span data-ttu-id="e5285-123">[SQL Server Komponenten](../../../2014/sql-server/install/sql-server-components.md) </span><span class="sxs-lookup"><span data-stu-id="e5285-123">[SQL Server Components](../../../2014/sql-server/install/sql-server-components.md) </span></span>  
 <span data-ttu-id="e5285-124">[Referenz zur Benutzeroberfläche des Upgrade Advisors](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md) </span><span class="sxs-lookup"><span data-stu-id="e5285-124">[Upgrade Advisor User Interface Reference](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md) </span></span>  
 [<span data-ttu-id="e5285-125">Arbeiten mit dem Upgrade Advisor</span><span class="sxs-lookup"><span data-stu-id="e5285-125">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
