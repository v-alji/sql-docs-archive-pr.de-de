---
title: Interaktives Durchsuchen von Dokumenten
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- interactive searches [SQL Server Management Studio]
- searches [SQL Server Management Studio], interactive
- Query Editor [SQL Server Management Studio], interactive search
ms.assetid: dae65ac5-67af-45c6-a6e0-952fea26d680
author: rothja
ms.author: jroth
ms.openlocfilehash: 5603db77ea4f58d4bb036635a23ec3cfa400a818
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622009"
---
# <a name="search-documents-interactively"></a><span data-ttu-id="b2758-102">Interaktives Durchsuchen von Dokumenten</span><span class="sxs-lookup"><span data-stu-id="b2758-102">Search Documents Interactively</span></span>
  <span data-ttu-id="b2758-103">Mithilfe des Dialogfelds **Suchen und Ersetzen** können Sie einzelne oder mehrere geöffnete Dateien oder Fenster durchsuchen und sich einzeln durch die Suchübereinstimmungen bewegen.</span><span class="sxs-lookup"><span data-stu-id="b2758-103">Using the **Find and Replace** dialog box, you can search one or more open files or windows and move through the search matches one by one.</span></span> <span data-ttu-id="b2758-104">Bei dieser Technik können Sie einzelne Suchübereinstimmungen im Kontext der jeweiligen Textpassage überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b2758-104">This technique allows you to review each individual search match in the context of the text around the match.</span></span> <span data-ttu-id="b2758-105">Außerdem können Sie Massensuchvorgänge ausführen und Suchübereinstimmungen über das Dialogfeld **Suchen und Ersetzen** im Berichtsformat überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b2758-105">You also have the option of performing bulk find operations and reviewing search matches in report format using the **Find and Replace** dialog box.</span></span>  
  
### <a name="to-search-all-open-documents"></a><span data-ttu-id="b2758-106">So durchsuchen Sie alle geöffneten Dokumente</span><span class="sxs-lookup"><span data-stu-id="b2758-106">To search all open documents</span></span>  
  
1.  <span data-ttu-id="b2758-107">Öffnen Sie die Elemente, die Sie durchsuchen möchten.</span><span class="sxs-lookup"><span data-stu-id="b2758-107">Open the items you wish to search.</span></span>  
  
2.  <span data-ttu-id="b2758-108">Zeigen Sie im Menü **Bearbeiten** auf **Suchen und Ersetzen** , und klicken Sie dann auf **Schnellsuche**.</span><span class="sxs-lookup"><span data-stu-id="b2758-108">On the **Edit** menu, point to **Find and Replace,** and then click **QuickFind**.</span></span>  
  
3.  <span data-ttu-id="b2758-109">Geben Sie in das Textfeld **Suchen und Ersetzen** den Text ein, nach dem Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="b2758-109">In the **Find and Replace** text box, enter the text to search for.</span></span>  
  
4.  <span data-ttu-id="b2758-110">Wählen Sie in der Liste **Suchen in** die Option **Alle geöffneten Dokumente**aus.</span><span class="sxs-lookup"><span data-stu-id="b2758-110">In the **Look in** list, select **All Open Documents**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b2758-111">Bestimmte geöffnete Dateien lassen sich möglicherweise nicht durchsuchen, wenn die Option **Alle geöffneten Dokumente** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="b2758-111">Certain open files might not be searched when **All Open Documents** is selected.</span></span> <span data-ttu-id="b2758-112">In die Suchvorgänge werden nur Dateien einbezogen, die zurzeit in einer Textansicht geöffnet sind, z. B. in der Codeansicht.</span><span class="sxs-lookup"><span data-stu-id="b2758-112">Only files currently open in a textual view, such as Code view, are included in searches.</span></span> <span data-ttu-id="b2758-113">Dateien in der Entwurfssicht werden nicht in Suchvorgänge einbezogen.</span><span class="sxs-lookup"><span data-stu-id="b2758-113">Files in Designer view are not included in searches.</span></span>  
  
5.  <span data-ttu-id="b2758-114">Wählen Sie weitere Suchoptionen aus, um die Genauigkeit des Suchvorgangs zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="b2758-114">Select additional search options to increase the accuracy of the search.</span></span>  
  
6.  <span data-ttu-id="b2758-115">Klicken Sie auf **Weitersuchen** , um die Suche zu starten, und klicken Sie wiederholt auf **Weitersuchen** , bis die letzte Datei durchsucht wurde.</span><span class="sxs-lookup"><span data-stu-id="b2758-115">Click **Find Next** to start the search, and continue clicking **Find Next** until the last file has been searched.</span></span>  
  
 <span data-ttu-id="b2758-116">Wenn der Suchvorgang am Anfang oder Ende des Dokuments angelangt, wird auf der Statusleiste eine Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b2758-116">When the search passes the beginning or end of the document, a message is displayed in the status bar.</span></span> <span data-ttu-id="b2758-117">Wenn der Suchvorgang am Anfangspunkt der Suche angelangt ist, wird ein Meldungsfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b2758-117">A message box appears when the search reaches the starting point of the search.</span></span>  
  
#### <a name="to-replace-in-all-active-files-interactively"></a><span data-ttu-id="b2758-118">So können Sie Elemente in allen aktiven Dateien interaktiv ersetzen</span><span class="sxs-lookup"><span data-stu-id="b2758-118">To replace in all active files interactively</span></span>  
  
1.  <span data-ttu-id="b2758-119">Zeigen Sie im Menü **Bearbeiten** auf **Suchen und Ersetzen**, und klicken Sie dann auf **Schnellersetzung**.</span><span class="sxs-lookup"><span data-stu-id="b2758-119">On the **Edit** menu, point to **Find and Replace**, and then click **QuickReplace**.</span></span>  
  
2.  <span data-ttu-id="b2758-120">Geben Sie in das Feld **Suchen nach** den Text ein, nach dem Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="b2758-120">In the **Find what** box, enter the text to search for.</span></span>  
  
3.  <span data-ttu-id="b2758-121">Geben Sie in das Feld **Ersetzen durch** den Text ein, durch den der Suchtext ersetzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b2758-121">In the **Replace with** box, enter the text to replace the search text.</span></span>  
  
4.  <span data-ttu-id="b2758-122">Wählen Sie in der Liste **Suchen in** die Option **Alle geöffneten Dokumente**aus.</span><span class="sxs-lookup"><span data-stu-id="b2758-122">In the **Look in** list, select **All Open Documents**.</span></span>  
  
5.  <span data-ttu-id="b2758-123">Klicken Sie auf **Ersetzen**, und klicken Sie wiederholt auf **Ersetzen** , bis die letzte Übereinstimmung in der letzten Datei ersetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="b2758-123">Click **Replace**, and continue clicking **Replace** until the last match in the last file has been replaced.</span></span> <span data-ttu-id="b2758-124">Wenn Sie eine Übereinstimmung auslassen möchten, die nicht ersetzt werden soll, klicken Sie auf **Weitersuchen** .</span><span class="sxs-lookup"><span data-stu-id="b2758-124">Click **Find Next** to skip a match you do not want to replace.</span></span>  
  
     <span data-ttu-id="b2758-125">Oder</span><span class="sxs-lookup"><span data-stu-id="b2758-125">-or-</span></span>  
  
     <span data-ttu-id="b2758-126">Wählen Sie die Option **Alle ersetzen** aus, um alle Übereinstimmungen zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="b2758-126">Choose **Replace All** to replace all matches.</span></span> <span data-ttu-id="b2758-127">In einem Meldungsfeld wird die Gesamtanzahl der Ersetzungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b2758-127">A message box appears, listing the total number of replacements.</span></span>  
  
 <span data-ttu-id="b2758-128">Mit dem Befehl **Alle ersetzen** werden alle Suchübereinstimmungen ersetzt. Dazu gehören auch die Übereinstimmungen, die Sie zuvor mit der Schaltfläche **Weitersuchen** ausgelassen haben.</span><span class="sxs-lookup"><span data-stu-id="b2758-128">The **Replace All** command replaces all search matches, including those you have skipped with the **Find Next** button.</span></span> <span data-ttu-id="b2758-129">Um den Befehl **Alle ersetzen**abzubrechen, klicken Sie im Menü **Bearbeiten** auf **Rückgängig** , bevor Sie eine der Dateien schließen.</span><span class="sxs-lookup"><span data-stu-id="b2758-129">To cancel **Replace All**, click **Undo** from the **Edit** menu before closing any of the files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2758-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b2758-130">See Also</span></span>  
 <span data-ttu-id="b2758-131">[Inkrementelles Durchsuchen eines aktiven Dokuments](search-an-active-document-incrementally.md) </span><span class="sxs-lookup"><span data-stu-id="b2758-131">[Search an Active Document Incrementally](search-an-active-document-incrementally.md) </span></span>  
 <span data-ttu-id="b2758-132">[Suchen und Ersetzen](search-and-replace.md) </span><span class="sxs-lookup"><span data-stu-id="b2758-132">[Search and Replace](search-and-replace.md) </span></span>  
 <span data-ttu-id="b2758-133">[Durchsuchen von Dokumenten mithilfe von Ergebnislisten](search-documents-using-results-lists.md) </span><span class="sxs-lookup"><span data-stu-id="b2758-133">[Search Documents Using Results Lists](search-documents-using-results-lists.md) </span></span>  
 <span data-ttu-id="b2758-134">[Suchen von Text mit Platzhaltern](search-text-with-wildcards.md) </span><span class="sxs-lookup"><span data-stu-id="b2758-134">[Search Text with Wildcards](search-text-with-wildcards.md) </span></span>  
 [<span data-ttu-id="b2758-135">Suchen von Text mit regulären Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="b2758-135">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
  
  
