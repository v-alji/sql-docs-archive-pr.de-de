---
title: 'Vorgehensweise: Anzeigen eines Berichts des Upgrade Advisors | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- displaying reports
- viewing reports
- Upgrade Advisor [SQL Server], reports
- SQL Server Upgrade Advisor, reports
- reports [Upgrade Advisor], viewing
ms.assetid: d13b38af-0ac3-4030-83cd-e7d7825dd09f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9e6df35b869186a601458889c348153093ccbce4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621833"
---
# <a name="how-to-view-an-upgrade-advisor-report"></a><span data-ttu-id="3a548-102">Gewusst wie: Anzeigen eines Berichts des Upgrade Advisors</span><span class="sxs-lookup"><span data-stu-id="3a548-102">How to: View an Upgrade Advisor Report</span></span>
  <span data-ttu-id="3a548-103">Der Upgrade Advisor erstellt Berichte für alle Komponenten, die Sie zur Analyse auswählen.</span><span class="sxs-lookup"><span data-stu-id="3a548-103">Upgrade Advisor creates reports for each component that you select to analyze.</span></span> <span data-ttu-id="3a548-104">In diesem Thema wird beschrieben, wie Sie einen Bericht des Upgrade Advisors über die Startseite des Upgrade Advisors anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3a548-104">This topic describes how to view an Upgrade Advisor report from the Upgrade Advisor start page.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3a548-105">Der Berichts-Viewer lädt Dateien auf der Grundlage von Standarddateinamen.</span><span class="sxs-lookup"><span data-stu-id="3a548-105">The report viewer loads files based on standard file names.</span></span> <span data-ttu-id="3a548-106">Wenn die Dateien umbenannt wurden, werden sie vom Berichts-Viewer nicht geladen.</span><span class="sxs-lookup"><span data-stu-id="3a548-106">If the files have been renamed, the report viewer will not load them.</span></span>  
  
### <a name="to-view-a-report"></a><span data-ttu-id="3a548-107">So zeigen Sie einen Bericht an</span><span class="sxs-lookup"><span data-stu-id="3a548-107">To view a report</span></span>  
  
1.  <span data-ttu-id="3a548-108">Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]** , und klicken Sie dann auf \*\* [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor\*\*.</span><span class="sxs-lookup"><span data-stu-id="3a548-108">Click **Start**, click **All Programs**, click **[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]**, and then click **[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor**.</span></span>  
  
2.  <span data-ttu-id="3a548-109">Klicken Sie auf der Startseite des Upgrade Advisors auf **Berichts-Viewer des Upgrade Advisors starten**.</span><span class="sxs-lookup"><span data-stu-id="3a548-109">On the Upgrade Advisor start page, click **Launch Upgrade Advisor Report Viewer**.</span></span>  
  
3.  <span data-ttu-id="3a548-110">So wählen Sie am Standardspeicherort auf dem Computer einen Bericht aus:</span><span class="sxs-lookup"><span data-stu-id="3a548-110">To select a report in the default location on your computer:</span></span>  
  
    1.  <span data-ttu-id="3a548-111">Wählen Sie in der Liste **Server** einen Server aus.</span><span class="sxs-lookup"><span data-stu-id="3a548-111">In the **Server** list, select a server.</span></span>  
  
    2.  <span data-ttu-id="3a548-112">Wählen Sie in der Liste **Instanz oder Komponente** eine Kombination aus Komponente oder Komponenten/Instanz aus.</span><span class="sxs-lookup"><span data-stu-id="3a548-112">In the **Instance or component** list, select a component or component/instance combination.</span></span>  
  
     <span data-ttu-id="3a548-113">So wählen Sie an einem anderen Speicherort einen Bericht aus:</span><span class="sxs-lookup"><span data-stu-id="3a548-113">To select a report at another location:</span></span>  
  
    1.  <span data-ttu-id="3a548-114">Klicken Sie auf den Link **Bericht öffnen** .</span><span class="sxs-lookup"><span data-stu-id="3a548-114">Click the **Open Report** link.</span></span>  
  
    2.  <span data-ttu-id="3a548-115">Navigieren Sie zum Speicherort des Berichts, und doppelklicken Sie dann auf die XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="3a548-115">Browse to the report location and then double-click the XML file.</span></span>  
  
     <span data-ttu-id="3a548-116">Der Upgrade Advisor speichert bis zu fünf Berichte früherer Analysen als Verlauf.</span><span class="sxs-lookup"><span data-stu-id="3a548-116">Upgrade Advisor stores up to five reports from previous analysis as history.</span></span> <span data-ttu-id="3a548-117">Um diese Berichte anzuzeigen, klicken Sie auf das Dropdown-Listenfeld **Bericht** , und wählen Sie einen Bericht aus.</span><span class="sxs-lookup"><span data-stu-id="3a548-117">To view these reports, click the **Report** drop-down list box, and select a report.</span></span> <span data-ttu-id="3a548-118">Die Berichte werden nach dem Zeitstempel für ihren Generierungszeitpunkt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="3a548-118">The reports are listed by the timestamp from when they were generated.</span></span>  
  
     <span data-ttu-id="3a548-119">Der Bericht enthält die folgenden Details für alle erkannten Probleme:</span><span class="sxs-lookup"><span data-stu-id="3a548-119">The report contains the following details for all detected issues:</span></span>  
  
    -   <span data-ttu-id="3a548-120">**Wichtigkeit**gibt an, wie wichtig es ist, das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="3a548-120">**Importance**, which indicates how important it is to fix the issue.</span></span>  
  
    -   <span data-ttu-id="3a548-121">Wenn Sie den Fehler **beheben möchten**, gibt dies an, ob Sie das Problem vor oder nach dem Upgrade auf [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , vor oder nach der Migration der Anwendung oder der Daten oder jederzeit beheben sollten.</span><span class="sxs-lookup"><span data-stu-id="3a548-121">**When to fix**, which indicates if you should (or must) fix the issue before or after upgrading to [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], before or after migrating the application or data, or anytime.</span></span>  
  
    -   <span data-ttu-id="3a548-122">Eine kurze Beschreibung des Problems.</span><span class="sxs-lookup"><span data-stu-id="3a548-122">A brief description of the issue.</span></span>  
  
4.  <span data-ttu-id="3a548-123">Wenn der Bericht mehr als 20 Einträge enthält, klicken Sie auf den grünen Vorwärtspfeil am Anfang oder am Ende des Berichts, um die nächste Elementgruppe anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3a548-123">If the report contains more than 20 items, click the green forward arrow at the top or bottom of the report to view the next set of items.</span></span> <span data-ttu-id="3a548-124">Klicken Sie auf die grüne Zurück-Schaltfläche, um die vorhergehenden 20 Elemente anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3a548-124">Click the green back button to view the previous 20 items.</span></span>  
  
5.  <span data-ttu-id="3a548-125">Klicken Sie auf eine Spaltenüberschrift, um den Bericht zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="3a548-125">To sort the report, click a column heading.</span></span>  
  
6.  <span data-ttu-id="3a548-126">Um Details für ein bestimmtes Element anzuzeigen, klicken Sie auf das gewünschte Element.</span><span class="sxs-lookup"><span data-stu-id="3a548-126">To view details for a specific item, click the item.</span></span> <span data-ttu-id="3a548-127">Eine Beschreibung des Problems wird angezeigt, zusammen mit zusätzlichen Optionen:</span><span class="sxs-lookup"><span data-stu-id="3a548-127">A description of the issue appears, along with additional options:</span></span>  
  
    -   <span data-ttu-id="3a548-128">Um die Objekte anzuzeigen, bei denen dieses Problem gefunden wurde, klicken Sie auf **Betroffene Objekte anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="3a548-128">To view the objects where this issue was found, click **Show affected objects**.</span></span>  
  
    -   <span data-ttu-id="3a548-129">Wenn Sie Hilfe zu diesem Problem anzeigen möchten, klicken Sie auf **Weitere Informationen zu diesem Problem und zu dessen Lösung**.</span><span class="sxs-lookup"><span data-stu-id="3a548-129">To view help for the issue, click **Tell me more about this issue and how to resolve it**.</span></span>  
  
    -   <span data-ttu-id="3a548-130">Um das Problem als aufgelöst zu markieren, das beim erneuten Anzeigen des Berichts das Problem verbirgt, wählen Sie **dieses Problem wurde gelöst**aus.</span><span class="sxs-lookup"><span data-stu-id="3a548-130">To mark the issue as resolved, which hides the issue when you view the report again, select **This issue has been resolved**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3a548-131">Der Bericht enthält möglicherweise ein Element für nicht zu erkennende Probleme.</span><span class="sxs-lookup"><span data-stu-id="3a548-131">The report may contain an item for undetectable issues.</span></span> <span data-ttu-id="3a548-132">Dies sind Probleme, die nicht erkannt werden können oder zu viele falsche positive Ergebnisse generieren würden.</span><span class="sxs-lookup"><span data-stu-id="3a548-132">These are issues that cannot be detected or that would generate too many false-positive results.</span></span> <span data-ttu-id="3a548-133">Klicken Sie auf den Link **Weitere Informationen zu diesem Problem und zum Beheben des Problems** , um eine Liste der nicht erkennbaren Probleme für die Komponente anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3a548-133">Click the **Tell me more about this issue and how to resolve it** link to see a list of undetectable issues for the component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a548-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3a548-134">See Also</span></span>  
 <span data-ttu-id="3a548-135">[Vorgehensweise: Exportieren von Berichten](../../../2014/sql-server/install/how-to-export-reports.md) </span><span class="sxs-lookup"><span data-stu-id="3a548-135">[How to: Export Reports](../../../2014/sql-server/install/how-to-export-reports.md) </span></span>  
 <span data-ttu-id="3a548-136">[Vorgehensweise: Ausführen des Analyse-Assistenten des Upgrade Advisors](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="3a548-136">[How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span></span>  
 <span data-ttu-id="3a548-137">[Beheben von Upgradeproblemen](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="3a548-137">[Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span></span>  
 <span data-ttu-id="3a548-138">[Gewusst-wie-Themen zum Upgrade Advisor](../../../2014/sql-server/install/upgrade-advisor-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="3a548-138">[Upgrade Advisor How-to Topics](../../../2014/sql-server/install/upgrade-advisor-how-to-topics.md) </span></span>  
 [<span data-ttu-id="3a548-139">Arbeiten mit dem Upgrade Advisor</span><span class="sxs-lookup"><span data-stu-id="3a548-139">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
