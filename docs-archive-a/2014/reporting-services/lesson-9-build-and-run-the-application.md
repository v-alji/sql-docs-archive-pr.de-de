---
title: 'Lektion 9: Erstellen und Ausführen der Anwendung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f52d3f3a-0b09-4b34-9112-0b3655271587
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 068deb075f0f60dde634ac29f6f8f934448dc6a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609707"
---
# <a name="lesson-9-build-and-run-the-application"></a><span data-ttu-id="db781-102">Lesson 9: Build and Run the Application</span><span class="sxs-lookup"><span data-stu-id="db781-102">Lesson 9: Build and Run the Application</span></span>
  <span data-ttu-id="db781-103">Nachdem Sie einen Datenfilter für die Datentabelle erstellt haben, erstellen Sie im nächsten Schritt eine Websiteanwendung und führen diese aus.</span><span class="sxs-lookup"><span data-stu-id="db781-103">After you create a data filter for the data table, your next step is to build and run the website application.</span></span>

### <a name="to-build-and-run-the-application"></a><span data-ttu-id="db781-104">So erstellen Sie die Anwendung und führen sie aus</span><span class="sxs-lookup"><span data-stu-id="db781-104">To build and run the application</span></span>

1.  <span data-ttu-id="db781-105">Drücken Sie **STRG+F5** , um die Seite Default.aspx ohne Debuggen auszuführen, oder drücken Sie F5, um die Seite mit Debuggen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="db781-105">Press **CTRL+F5** to run the Default.aspx page without debugging, or press F5 to run the page with debugging.</span></span>

     <span data-ttu-id="db781-106">Der Bericht wird im Rahmen des Erstellungsprozesses kompiliert und alle Fehler (z.B. Syntaxfehler in einem Berichtsausdruck) werden der **Aufgabenliste** unten im Visual Studio-Fenster hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="db781-106">As part of the build process, the report is compiled and any errors found (such as a syntax error in an expression used in the report) are added to the **Task List** that is located at the bottom of the Visual Studio window.</span></span>

     <span data-ttu-id="db781-107">Die Webseite wird im Browser geöffnet.</span><span class="sxs-lookup"><span data-stu-id="db781-107">The webpage appears in the browser.</span></span> <span data-ttu-id="db781-108">Der Bericht wird vom ReportViewer-Steuerelement angezeigt.</span><span class="sxs-lookup"><span data-stu-id="db781-108">The ReportViewer control displays the report.</span></span> <span data-ttu-id="db781-109">Sie können die Symbolleiste zum Navigieren, Zoomen und Exportieren des Berichts in Excel verwenden.</span><span class="sxs-lookup"><span data-stu-id="db781-109">You can use the toolbar to browse through the report, zoom, and export the report to Excel.</span></span>

2.  <span data-ttu-id="db781-110">Zeigen Sie mit der Maus auf eine der Zeilen unter der Spalte **Name** .</span><span class="sxs-lookup"><span data-stu-id="db781-110">Hover the mouse over any of the rows under **Name** column.</span></span> <span data-ttu-id="db781-111">Der Mauszeiger wird als Handsymbol angezeigt.</span><span class="sxs-lookup"><span data-stu-id="db781-111">The mouse cursor will display a Hand symbol.</span></span>

3.  <span data-ttu-id="db781-112">Klicken Sie auf einen Wert in der Spalte **Name** .</span><span class="sxs-lookup"><span data-stu-id="db781-112">Click a value in the **Name** column.</span></span> <span data-ttu-id="db781-113">Der untergeordnete Bericht wird mit den entsprechenden gefilterten Daten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="db781-113">The child report is shown with the corresponding filtered data.</span></span>

4.  <span data-ttu-id="db781-114">Klicken Sie in der **ReportViewer**-Symbolleiste auf das Symbol **Zurück zum übergeordneten Bericht** , um zurück zum **übergeordneten** Bericht zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="db781-114">Click the icon, **Go back to parent report**, in the **ReportViewer** tool bar to navigate back to the **Parent** report.</span></span>

     <span data-ttu-id="db781-115">![SSRS-Drillthrough mithilfe von Report Viewer](../../2014/tutorials/media/ssrs-drillthrough-report.png "SSRS-Drillthrough mithilfe von Report Viewer")</span><span class="sxs-lookup"><span data-stu-id="db781-115">![ssrs drill through using ReportViewer](../../2014/tutorials/media/ssrs-drillthrough-report.png "ssrs drill through using ReportViewer")</span></span>

5.  <span data-ttu-id="db781-116">Schließen Sie den Browser, um den Vorgang zu beenden.</span><span class="sxs-lookup"><span data-stu-id="db781-116">Close the browser to exit.</span></span>


