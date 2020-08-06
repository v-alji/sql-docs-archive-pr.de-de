---
title: Suchen und Ersetzen
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- match case [SQL Server]
- undo operations
- searches [SQL Server Management Studio]
- replacing text
- quick search and replaces [SQL Server Management Studio]
- Query Editor [SQL Server Management Studio], undo
- Query Editor [SQL Server Management Studio], searching
- regular expressions [SQL Server Management Studio]
- finding text [SQL Server Management Studio]
- text [SQL Server], search and replace operations
- finding [SQL Server Management Studio]
- locating text
- Query Editor [SQL Server Management Studio], replacing text
- Find and Replace dialog box
- wildcard options [SQL Server Management Studio]
- match whole word [SQL Server]
- searches [SQL Server Management Studio], replacing
ms.assetid: 3641c7b3-3e3e-4ddd-af82-c15b50004f94
author: rothja
ms.author: jroth
ms.openlocfilehash: 55422fa7201213477426c7bc25c45ff05acf8945
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609793"
---
# <a name="search-and-replace"></a><span data-ttu-id="1997e-102">Suchen und Ersetzen</span><span class="sxs-lookup"><span data-stu-id="1997e-102">Search and Replace</span></span>
  <span data-ttu-id="1997e-103">Es gibt mehrere verschiedene Möglichkeiten, Text zu suchen und zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="1997e-103">There are several different ways to find and replace text.</span></span> <span data-ttu-id="1997e-104">Im Menü **Bearbeiten** stehen unter **Suchen und Ersetzen** vier Auswahlmöglichkeiten zur Verfügung: **Schnellsuche**, **Schnellersetzung**, **In Dateien suchen**oder **In Dateien ersetzen**.</span><span class="sxs-lookup"><span data-stu-id="1997e-104">On the **Edit** menu, **Find and Replace** offers four choices: **Quick Find**, **Quick Replace**, **Find in Files**, or **Replace in Files**.</span></span> <span data-ttu-id="1997e-105">Durch jede dieser Optionen wird eine entsprechende Version des Dialogfelds **Suchen und Ersetzen** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1997e-105">Each of these opens versions of the **Find and Replace** dialog box.</span></span> <span data-ttu-id="1997e-106">Mit Tastenkombinationen zur inkrementellen Suche können Sie auch einen Suchvorgang ohne Dialogfeld ausführen.</span><span class="sxs-lookup"><span data-stu-id="1997e-106">You can also search without a dialog box by using incremental search keyboard shortcut keys.</span></span> <span data-ttu-id="1997e-107">Mit diesen Techniken können Sie den Bereich für den Such- und Ersetzungsvorgang steuern und die Methode zum Überprüfen von Suchübereinstimmungen und Ersetzungen auswählen.</span><span class="sxs-lookup"><span data-stu-id="1997e-107">These techniques allow you to control the scope of find and replace, and choose the method of reviewing search matches and replacements.</span></span>  
  
 <span data-ttu-id="1997e-108">Beim Suchen und Ersetzen von Text müssen Sie die folgenden Punkte beachten:</span><span class="sxs-lookup"><span data-stu-id="1997e-108">You should consider the following when you search and replace text:</span></span>  
  
-   <span data-ttu-id="1997e-109">Die im Dialogfeld **Suchen und Ersetzen** festgelegten Optionen betreffen alle Suchvorgänge.</span><span class="sxs-lookup"><span data-stu-id="1997e-109">Options set in the **Find and Replace** dialog box affect all the searches.</span></span> <span data-ttu-id="1997e-110">Zu diesen Optionen zählen **Groß-/Kleinschreibung beachten**, **Nur ganzes Wort suchen**, **Suchrichtung nach oben**, **Ausgeblendeten Text durchsuchen**, **Platzhalter**, **Reguläre Ausdrücke**, die Option zum **Suchen in allen geöffneten Dokumenten** und die Option zum **Suchen im aktuellen Projekt**.</span><span class="sxs-lookup"><span data-stu-id="1997e-110">These options include **Match case**, **Match whole word**, **Search up**, **Search hidden text**, **Wildcards**, **Regular Expressions**, **Look in All Open Documents**, and **Look in Current Project**.</span></span> <span data-ttu-id="1997e-111">Diese Optionen sind nicht in allen Versionen des Dialogfelds **Suchen und Ersetzen** vollständig verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1997e-111">All options are not available in all versions of the **Find and Replace** dialog box.</span></span>  
  
-   <span data-ttu-id="1997e-112">**Rückgängig** ist nur für Dokumente verfügbar, die nach einem Ersetzungsvorgang geöffnet bleiben.</span><span class="sxs-lookup"><span data-stu-id="1997e-112">**Undo** is available only for documents left open after a replace operation.</span></span>  
  
-   <span data-ttu-id="1997e-113">Wenn beim Vorgang**Alle ersetzen** , der sich über mehr als eine Datei erstreckt, die Option **Rückgängig** verwendet wird, wird sie als eine einzelne gesammelte Aktion über die betroffenen Dateien hinweg betrachtet.</span><span class="sxs-lookup"><span data-stu-id="1997e-113">**Undo** for a **Replace All** operation that spans more than one file is considered a single, bulk action across all the affected files.</span></span> <span data-ttu-id="1997e-114">Das bedeutet, dass es nicht möglich ist, die Änderungen in einigen Dateien rückgängig zu machen und in anderen Dateien beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="1997e-114">That is, you cannot undo the change in some files while retaining the change in other files.</span></span>  
  
 <span data-ttu-id="1997e-115">Im Allgemeinen können Sie keine Elemente mit grafischen Ansichten durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="1997e-115">Generally, you cannot search items with graphical views.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1997e-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1997e-116">See Also</span></span>  
 <span data-ttu-id="1997e-117">[Inkrementelles Durchsuchen eines aktiven Dokuments](search-an-active-document-incrementally.md) </span><span class="sxs-lookup"><span data-stu-id="1997e-117">[Search an Active Document Incrementally](search-an-active-document-incrementally.md) </span></span>  
 <span data-ttu-id="1997e-118">[Interaktives Durchsuchen von Dokumenten](search-documents-interactively.md) </span><span class="sxs-lookup"><span data-stu-id="1997e-118">[Search Documents Interactively](search-documents-interactively.md) </span></span>  
 <span data-ttu-id="1997e-119">[Durchsuchen von Dokumenten mithilfe von Ergebnislisten](search-documents-using-results-lists.md) </span><span class="sxs-lookup"><span data-stu-id="1997e-119">[Search Documents Using Results Lists](search-documents-using-results-lists.md) </span></span>  
 <span data-ttu-id="1997e-120">[Suchen von Text mit Platzhaltern](search-text-with-wildcards.md) </span><span class="sxs-lookup"><span data-stu-id="1997e-120">[Search Text with Wildcards](search-text-with-wildcards.md) </span></span>  
 [<span data-ttu-id="1997e-121">Suchen von Text mit regulären Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="1997e-121">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
  
  
