---
title: Berichts Verlauf (Seite) (Berichts-Manager) | Microsoft-Dokumentation
ms.prod: sql-server-2014
ms.technology: reporting-services-native
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 06/13/2017
ms.openlocfilehash: 4070be8c1d6b0633131e96c665d4551c1b676a9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617644"
---
# <a name="report-history-page-report-manager"></a><span data-ttu-id="98844-102">Berichtsverlauf (Seite, Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="98844-102">Report History Page (Report Manager)</span></span>

<span data-ttu-id="98844-103">Mithilfe der Seite Berichtsverlauf können Sie die im Laufe der Zeit generierten und gespeicherten Berichtsmomentaufnahmen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="98844-103">Use the Report History page to view report snapshots that are generated and stored over time.</span></span> <span data-ttu-id="98844-104">Abhängig von den für den Berichtsserver festgelegten Optionen enthält der Berichtsverlauf möglicherweise nur die neuesten Momentaufnahmen.</span><span class="sxs-lookup"><span data-stu-id="98844-104">Depending on options that are set on the report server, report history may contain only the more recent snapshots.</span></span>  
  

<span data-ttu-id="98844-105">Der Berichtsverlauf wird immer im Kontext des Berichts angezeigt, aus dem er stammt.</span><span class="sxs-lookup"><span data-stu-id="98844-105">Report history is always viewed within the context of the report from which it originates.</span></span> <span data-ttu-id="98844-106">Es ist nicht möglich, den Verlauf aller Berichte auf einem Berichtsserver zentral anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="98844-106">You cannot view the history of all reports on a report server in one place.</span></span>  
  
<span data-ttu-id="98844-107">Wenn Sie den Berichtsverlauf generieren möchten, muss der Bericht unbeaufsichtigt ausgeführt werden können, d. h., er muss gespeicherte Anmeldeinformationen verwenden, und parametrisierte Berichte müssen Standardparameterwerte für alle Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="98844-107">To generate report history, the report must be able to run unattended (that is, it must use stored credentials; parameterized reports must contain default parameter values for all parameters).</span></span> <span data-ttu-id="98844-108">Der Berichtsverlauf kann manuell oder als geplante Operation generiert werden.</span><span class="sxs-lookup"><span data-stu-id="98844-108">Report history can be generated manually or as a scheduled operation.</span></span> <span data-ttu-id="98844-109">Verlaufseigenschaften im Bericht bestimmen die Art und Weise, in der der Berichtsverlauf erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="98844-109">History properties on the report determine the ways in which report history can be created.</span></span>  
  
<span data-ttu-id="98844-110">Klicken Sie auf eine Momentaufnahme zum Berichtsverlauf, um diese anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="98844-110">You can click a report history snapshot to view it.</span></span> <span data-ttu-id="98844-111">Die im Berichtsverlauf angezeigten Momentaufnahmen unterscheiden sich nur durch das Datum und die Uhrzeit ihrer Erstellung.</span><span class="sxs-lookup"><span data-stu-id="98844-111">Snapshots that appear in report history are distinguished only by the date and time at which they were created.</span></span> <span data-ttu-id="98844-112">Es gibt keinen grafischen Hinweis, ob eine Momentaufnahme als Folge eines Zeitplans oder durch einen manuellen Vorgang generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="98844-112">There is no visual indication to distinguish whether a snapshot was generated in response to a schedule or a manual operation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98844-113">Diese Funktion ist nicht in jeder Edition von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]verfügbar.</span><span class="sxs-lookup"><span data-stu-id="98844-113">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="98844-114">Eine Liste der Funktionen, die von den Editionen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]unterstützt werden, finden Sie unter [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="98844-114">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="98844-115">Navigation</span><span class="sxs-lookup"><span data-stu-id="98844-115">Navigation</span></span>  
 <span data-ttu-id="98844-116">Verwenden Sie folgendes Verfahren, um zu dieser Position in der Benutzeroberfläche zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="98844-116">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-report-history-page"></a><span data-ttu-id="98844-117">So öffnen Sie die Seite 'Berichtsverlauf'</span><span class="sxs-lookup"><span data-stu-id="98844-117">To open the Report History page</span></span>  
  
1.  <span data-ttu-id="98844-118">Öffnen Sie den Berichts-Manager, und suchen Sie den Bericht, für den Sie Berichtsmomentaufnahmen anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="98844-118">Open Report Manager, and locate the report for which you want to view report snapshots.</span></span>  
  
2.  <span data-ttu-id="98844-119">Zeigen Sie auf den Bericht, und klicken Sie auf den Dropdownpfeil.</span><span class="sxs-lookup"><span data-stu-id="98844-119">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="98844-120">Klicken Sie im Dropdownmenü auf **Berichtsverlauf anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="98844-120">In the drop-down menu, click **View Report History**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="98844-121">Tastatur</span><span class="sxs-lookup"><span data-stu-id="98844-121">Options</span></span>  
 <span data-ttu-id="98844-122">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="98844-122">**Delete**</span></span>  
 <span data-ttu-id="98844-123">Klicken Sie auf diese Schaltfläche, um eine oder mehrere Momentaufnahmen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="98844-123">Click to delete one or more snapshots.</span></span> <span data-ttu-id="98844-124">Bevor Sie auf **Löschen**klicken, aktivieren Sie das Kontrollkästchen neben den zu löschenden Momentaufnahmen.</span><span class="sxs-lookup"><span data-stu-id="98844-124">Before clicking **Delete**, select the check box next to the snapshot that you want to delete.</span></span>  
  
 <span data-ttu-id="98844-125">**Neue Momentaufnahme**</span><span class="sxs-lookup"><span data-stu-id="98844-125">**New Snapshot**</span></span>  
 <span data-ttu-id="98844-126">Klicken Sie auf diese Schaltfläche, um eine Momentaufnahme zum Berichtsverlauf hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="98844-126">Click to add a snapshot to report history.</span></span> <span data-ttu-id="98844-127">Diese Schaltfläche ist verfügbar, wenn Sie auf der Seite mit den Verlaufseigenschaften des Berichts die Option **Berichtsverlauf kann manuell erstellt werden** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="98844-127">This button is available when you choose the option **Allow history to be created manually** on the History properties page of the report.</span></span>  
  
 <span data-ttu-id="98844-128">**Zuletzt ausgeführt**</span><span class="sxs-lookup"><span data-stu-id="98844-128">**Last Run**</span></span>  
 <span data-ttu-id="98844-129">Zeigt das Datum und die Uhrzeit der Erstellung der Momentaufnahme an.</span><span class="sxs-lookup"><span data-stu-id="98844-129">Displays the date and time at which the snapshot was created.</span></span> <span data-ttu-id="98844-130">Klicken Sie auf eine Beschreibung, um eine bestimmten Momentaufnahme anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="98844-130">Click a description to view a particular snapshot.</span></span>  
  
 <span data-ttu-id="98844-131">**Größe**</span><span class="sxs-lookup"><span data-stu-id="98844-131">**Size**</span></span>  
 <span data-ttu-id="98844-132">Zeigt die Größe der Berichtsdefinition und der Daten im Bericht an.</span><span class="sxs-lookup"><span data-stu-id="98844-132">Displays the size of the report definition plus the data in the report.</span></span> <span data-ttu-id="98844-133">Dieser Wert gibt an, wie viel Speicherplatz in der Berichtsserver-Datenbank durch die Berichtsdefinition und Daten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="98844-133">This value indicates how much space in the report server database is used by the report definition and data.</span></span> <span data-ttu-id="98844-134">Die Größe des dargestellten Berichts einschließlich der Formatierung ist tatsächlich höher.</span><span class="sxs-lookup"><span data-stu-id="98844-134">The size of the rendered report, which includes formatting, is actually larger.</span></span> <span data-ttu-id="98844-135">Die in Klammern angegebene Gesamtgröße enthält die Summe der Größe aller Momentaufnahmen im Berichtsverlauf des aktuellen Berichts.</span><span class="sxs-lookup"><span data-stu-id="98844-135">The total size, indicated in parentheses, sums the sizes of all snapshots in the report history for the current report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98844-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="98844-136">See Also</span></span>  
 <span data-ttu-id="98844-137">[Berichts Verlauf &#40;Berichts-Manager anzeigen oder löschen&#41;](../../2014/reporting-services/view-or-delete-report-history-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="98844-137">[View or Delete Report History &#40;Report Manager&#41;](../../2014/reporting-services/view-or-delete-report-history-report-manager.md) </span></span>  
 <span data-ttu-id="98844-138">[Hinzufügen einer Momentaufnahme zum Berichts Verlauf &#40;Berichts-Manager&#41;](report-server/add-a-snapshot-to-report-history-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="98844-138">[Add a Snapshot to Report History &#40;Report Manager&#41;](report-server/add-a-snapshot-to-report-history-report-manager.md) </span></span>  
 <span data-ttu-id="98844-139">[Allgemeine Eigenschaften (Seite), Berichte &#40;Berichts-Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="98844-139">[General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span></span>  
 <span data-ttu-id="98844-140">[Berichts-Manager F1-Hilfe](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="98844-140">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 [<span data-ttu-id="98844-141">Die Eigenschaften Seite "Momentaufnahme Optionen" &#40;Berichts-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="98844-141">Snapshot Options Properties Page &#40;Report Manager&#41;</span></span>](../../2014/reporting-services/snapshot-options-properties-page-report-manager.md)