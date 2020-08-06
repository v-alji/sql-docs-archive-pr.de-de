---
title: Durchsuchen von Dokumenten mithilfe von Ergebnislisten
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- searches [SQL Server Management Studio], result lists
- result list searches [SQL Server Management Studio]
- searches [SQL Server Management Studio], multiple files
- Query Editor [SQL Server Management Studio], search multiple files
ms.assetid: 275e1b6c-fbd0-4408-af77-35903f90657c
author: rothja
ms.author: jroth
ms.openlocfilehash: 58ff3754bc1667de75426e52b3ddd855e7d1a348
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622004"
---
# <a name="search-documents-using-results-lists"></a><span data-ttu-id="9ad3e-102">Durchsuchen von Dokumenten mithilfe von Ergebnislisten</span><span class="sxs-lookup"><span data-stu-id="9ad3e-102">Search Documents Using Results Lists</span></span>
  <span data-ttu-id="9ad3e-103">Mit dem Dialogfeld **Suchen und Ersetzen** können Sie Text in allen Dateien innerhalb eines Projekts bzw. einer Projektmappe oder in einem Dateisystemordner durchsuchen und ersetzen, auch wenn diese nicht in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]geöffnet sind.</span><span class="sxs-lookup"><span data-stu-id="9ad3e-103">Using the **Find and Replace** dialog box, you can search and replace text in all files in a project or solution or in a file system folder, even when they are not open in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="9ad3e-104">Übereinstimmungen aus Suchvorgängen, die mit dem Dialogfeld **Suchen und Ersetzen** ausgeführt wurden, werden in den Fenstern Suchergebnisse 1 und Suchergebnisse 2 angezeigt. Im Fenster Suchergebnisse 2 können Sie den genauen Text aus der Zeile anzeigen, in der sich die Übereinstimmung befindet.</span><span class="sxs-lookup"><span data-stu-id="9ad3e-104">Matches from searches that were performed with the **Find and Replace** dialog box appear in the Find Results 1 and Find Results 2 windows, which allows you to view the exact text from the line containing the match.</span></span>  
  
### <a name="to-search-in-multiple-files"></a><span data-ttu-id="9ad3e-105">So durchsuchen Sie mehrere Dateien</span><span class="sxs-lookup"><span data-stu-id="9ad3e-105">To search in multiple files</span></span>  
  
1.  <span data-ttu-id="9ad3e-106">Zeigen Sie im Menü **Bearbeiten** auf **Suchen und Ersetzen** , und klicken Sie dann auf **In Dateien suchen**.</span><span class="sxs-lookup"><span data-stu-id="9ad3e-106">On the **Edit** menu, point to **Find and Replace,** and then click **Find in Files**.</span></span>  
  
2.  <span data-ttu-id="9ad3e-107">Geben Sie in das Textfeld **Suchen nach** den Text ein, nach dem Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="9ad3e-107">In the **Find what** text box, enter the text to search for.</span></span>  
  
3.  <span data-ttu-id="9ad3e-108">Klicken Sie in der Liste **Suchen in** auf **Alle geöffneten Dokumente**, **Aktuelles Projekt**, **Gesamte Projektmappe**, oder geben Sie einen Verzeichnispfad ein.</span><span class="sxs-lookup"><span data-stu-id="9ad3e-108">In the **Look in** list, click **All Open Documents**, **Current Project**, **Entire Solution**, or type a directory path.</span></span>  
  
4.  <span data-ttu-id="9ad3e-109">Wählen Sie in der Liste **Dateitypen** eine der aufgeführten Dateierweiterungsgruppen aus, oder geben Sie die Dateierweiterungen für die Dateitypen ein, nach denen gesucht werden soll, getrennt durch Semikolons.</span><span class="sxs-lookup"><span data-stu-id="9ad3e-109">In the **File types** list, select one of the listed sets of file extensions or enter the extensions for the types of files to be searched, separated by semicolons.</span></span> <span data-ttu-id="9ad3e-110">Verwenden Sie \*geöffnet sind.\* um alle Dateien in dem in der Dropdownliste **Suchen in** angegebenen Verzeichnis zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="9ad3e-110">Use \*.\* to search all files in the directory listed in the **Look in** drop-down list.</span></span>  
  
5.  <span data-ttu-id="9ad3e-111">Treffen Sie aus den übrigen Suchoptionen eine Auswahl, um die Genauigkeit der Suche zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="9ad3e-111">Select from the remaining search options to improve the accuracy of the search.</span></span>  
  
6.  <span data-ttu-id="9ad3e-112">Klicken Sie auf **Suchen** , um die Suche zu starten.</span><span class="sxs-lookup"><span data-stu-id="9ad3e-112">Click **Find** to begin the search.</span></span>  
  
 <span data-ttu-id="9ad3e-113">Standardmäßig werden die Übereinstimmungen für den Suchvorgang im Fenster Suchergebnisse 1 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9ad3e-113">The matches for the search appear in the Find Results 1 window by default.</span></span> <span data-ttu-id="9ad3e-114">Sie können die Suchübereinstimmungen durchsuchen, indem Sie im Fenster Suchergebnisse 1 auf die einzelnen Einträge doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="9ad3e-114">You can browse the search matches by double-clicking each entry in the Find Results 1 window.</span></span> <span data-ttu-id="9ad3e-115">Um die Suchergebnisse in einem neuen Fenster anzuzeigen, wählen Sie die Option zum **Anzeigen in Suche 2** aus.</span><span class="sxs-lookup"><span data-stu-id="9ad3e-115">To view the search results in a new window, select **Display in Find 2**.</span></span>  
  
#### <a name="to-replace-across-multiple-files-or-folders"></a><span data-ttu-id="9ad3e-116">So ersetzen Sie Elemente in mehreren Dateien oder Ordnern</span><span class="sxs-lookup"><span data-stu-id="9ad3e-116">To replace across multiple files or folders</span></span>  
  
1.  <span data-ttu-id="9ad3e-117">Zeigen Sie im Menü **Bearbeiten** auf **Suchen und Ersetzen** , und klicken Sie dann auf **In Dateien ersetzen**.</span><span class="sxs-lookup"><span data-stu-id="9ad3e-117">On the **Edit** menu, point to **Find and Replace,** and then click **Replace in Files**.</span></span>  
  
2.  <span data-ttu-id="9ad3e-118">Geben Sie in das Textfeld **Suchen nach** den Text ein, nach dem Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="9ad3e-118">In the **Find what** text box, enter the text to search for.</span></span>  
  
3.  <span data-ttu-id="9ad3e-119">Geben Sie in das Feld **Ersetzen durch** den Text ein, durch den der Suchtext ersetzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ad3e-119">In the **Replace with** box, enter the text to replace the search text.</span></span>  
  
4.  <span data-ttu-id="9ad3e-120">Klicken Sie in der Liste **Suchen in** auf **Alle geöffneten Dokumente**, **Aktuelles Projekt**, **Gesamte Projektmappe**, oder geben Sie einen Verzeichnispfad ein.</span><span class="sxs-lookup"><span data-stu-id="9ad3e-120">In the **Look in** list, click **All Open Documents**, **Current Project**, **Entire Solution**, or type a directory path.</span></span>  
  
5.  <span data-ttu-id="9ad3e-121">Klicken Sie auf **Ersetzen** , um die gefundene Suchübereinstimmung durch den Text im Feld **Ersetzen durch** zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="9ad3e-121">Click **Replace** to replace the current search match with the text in the **Replace with** box.</span></span> <span data-ttu-id="9ad3e-122">Wenn Sie auf **Weitersuchen** klicken, können Sie einzelne Übereinstimmungen auslassen. Wenn Sie auf **Datei überspringen**klicken, können Sie eine Datei auslassen.</span><span class="sxs-lookup"><span data-stu-id="9ad3e-122">You can skip a single match by clicking **Find Next** or skip an entire file clicking **Skip File**.</span></span>  
  
     <span data-ttu-id="9ad3e-123">\- oder –</span><span class="sxs-lookup"><span data-stu-id="9ad3e-123">\- or -</span></span>  
  
     <span data-ttu-id="9ad3e-124">Klicken Sie auf **Alle ersetzen** , um alle gefundenen Suchübereinstimmungen durch den Text im Feld **Ersetzen durch** zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="9ad3e-124">Choose **Replace all** to replace all search matches with the text in the **Replace with** box.</span></span> <span data-ttu-id="9ad3e-125">Wählen Sie **Nach dem Ersetzen, geänderte Dateien geöffnet lassen** aus, wenn Sie einige der vorgenommenen Ersetzungen zu einem späteren Zeitpunkt rückgängig machen möchten.</span><span class="sxs-lookup"><span data-stu-id="9ad3e-125">Select **Keep modified files open after Replace All** if you want to undo some of the replacements at another time.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9ad3e-126">Durch**Alle ersetzen** werden alle gefundenen Suchübereinstimmungen ersetzt, einschließlich jener in den Dateien, die Sie mit **Datei überspringen** oder **Weitersuchen**ausgelassen haben.</span><span class="sxs-lookup"><span data-stu-id="9ad3e-126">**Replace all** replaces all search matches, including those in files you have skipped with **Skip File** or **Find Next**.</span></span> <span data-ttu-id="9ad3e-127">Sie können die Option **Rückgängig** nur für Ersetzungen verwenden, die in Dateien vorgenommen wurden, die nach dem Ersetzungsvorgang geöffnet bleiben.</span><span class="sxs-lookup"><span data-stu-id="9ad3e-127">You can only use **Undo** for replacements made in files that remain open after the replacement operation.</span></span>  
  
 <span data-ttu-id="9ad3e-128">Standardmäßig werden die Ersetzungsinformationen im Fenster Suchergebnisse 1 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9ad3e-128">Replacement information appears in the Find Results 1 window by default.</span></span> <span data-ttu-id="9ad3e-129">Sie können die Ersetzungen durchsuchen, indem Sie im Fenster Suchergebnisse 1 auf die einzelnen Einträge doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="9ad3e-129">You can browse replacements by double-clicking each entry in the Find Results 1 window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ad3e-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9ad3e-130">See Also</span></span>  
 <span data-ttu-id="9ad3e-131">[Suchen und Ersetzen](search-and-replace.md) </span><span class="sxs-lookup"><span data-stu-id="9ad3e-131">[Search and Replace](search-and-replace.md) </span></span>  
 <span data-ttu-id="9ad3e-132">[Interaktives Durchsuchen von Dokumenten](search-documents-interactively.md) </span><span class="sxs-lookup"><span data-stu-id="9ad3e-132">[Search Documents Interactively](search-documents-interactively.md) </span></span>  
 <span data-ttu-id="9ad3e-133">[Suchen von Text mit Platzhaltern](search-text-with-wildcards.md) </span><span class="sxs-lookup"><span data-stu-id="9ad3e-133">[Search Text with Wildcards](search-text-with-wildcards.md) </span></span>  
 [<span data-ttu-id="9ad3e-134">Suchen von Text mit regulären Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="9ad3e-134">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
  
  
