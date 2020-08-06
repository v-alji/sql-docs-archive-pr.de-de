---
title: Inkrementelles Durchsuchen eines aktiven Dokuments
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- searches [SQL Server Management Studio], incremental
- Query Editor [SQL Server Management Studio], incremental search
- incremental searches [SQL Server Management Studio]
ms.assetid: 490bb36c-dd43-4219-9e2a-ff27046b9395
author: rothja
ms.author: jroth
ms.openlocfilehash: aefc2f0b7abff5992a8f4f7817e564ef1b72009d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609796"
---
# <a name="search-an-active-document-incrementally"></a><span data-ttu-id="b15f9-102">Inkrementelles Durchsuchen eines aktiven Dokuments</span><span class="sxs-lookup"><span data-stu-id="b15f9-102">Search an Active Document Incrementally</span></span>
  <span data-ttu-id="b15f9-103">Sie können ein einzelnes Dokument oder Fenster inkrementell durch Eingabe von Text durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="b15f9-103">You can search a single document or window incrementally by entering text.</span></span> <span data-ttu-id="b15f9-104">Beim Suchvorgang wird die erste Zeichenfolge hervorgehoben, die mit der eingegebenen Zeichenfolge für die inkrementelle Suche im Dokument bzw. Fenster übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="b15f9-104">The search operation highlights the first set of characters that matches the characters entered during the incremental search in the document or window.</span></span> <span data-ttu-id="b15f9-105">Bei der inkrementellen Suche wird automatisch der gesamte Text in einem Dokument bzw. Fenster durchsucht, ausgenommen ausgeblendeter Text.</span><span class="sxs-lookup"><span data-stu-id="b15f9-105">Incremental search automatically searches all of the text within a document or window except for text that has been hidden.</span></span>  
  
 <span data-ttu-id="b15f9-106">Bei der Option **Groß-/Kleinschreibung beachten** verwendet die inkrementelle Suche die Kriterien aus der vorherigen Suche.</span><span class="sxs-lookup"><span data-stu-id="b15f9-106">For the **Match case** option, incremental search uses the criteria from your previous search.</span></span> <span data-ttu-id="b15f9-107">Wenn Sie z. B. mit dem Dialogfeld **In Dateien suchen** eine Suche in mehreren Dateien ausgeführt haben, die Option **Groß-/Kleinschreibung beachten**aktivieren und jetzt einen inkrementellen Suchvorgang ausführen, wird bei der Suche die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="b15f9-107">For example, if you searched across multiple files using the **Find in Files** dialog box and select **Match Case**, and you next search incrementally, the search will be case-sensitive.</span></span>  
  
### <a name="to-search-incrementally"></a><span data-ttu-id="b15f9-108">So führen Sie einen inkrementellen Suchvorgang aus</span><span class="sxs-lookup"><span data-stu-id="b15f9-108">To search incrementally</span></span>  
  
1.  <span data-ttu-id="b15f9-109">Öffnen Sie die zu durchsuchende Datei bzw. das Fenster.</span><span class="sxs-lookup"><span data-stu-id="b15f9-109">Open the file or window to you want to search.</span></span>  
  
2.  <span data-ttu-id="b15f9-110">Zeigen Sie im Menü **Bearbeiten** auf **Erweitert**, und klicken Sie dann auf **Inkrementelle Suche**.</span><span class="sxs-lookup"><span data-stu-id="b15f9-110">On the **Edit** menu, point to **Advanced**, and then click **Incremental Search**.</span></span>  
  
     <span data-ttu-id="b15f9-111">Der Cursor wird jetzt als Fernglas mit einem Pfeil zur Anzeige der Suchrichtung dargestellt, und in der Statusleiste wird "Inkrementelle Suche" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b15f9-111">The cursor icon changes to a binocular with an arrow, indicating the search direction, and the status bar displays "Incremental Search."</span></span>  
  
3.  <span data-ttu-id="b15f9-112">Beginnen Sie mit der Eingabe der Textzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b15f9-112">Begin typing the text string.</span></span>  
  
     <span data-ttu-id="b15f9-113">In der Statusleiste wird der Text angezeigt, den Sie eingeben, und der Editor hebt die erste Übereinstimmung hervor.</span><span class="sxs-lookup"><span data-stu-id="b15f9-113">The status bar displays the text you are entering while the editor highlights the first occurrence that matches the text.</span></span> <span data-ttu-id="b15f9-114">Wenn Sie mit der Eingabe fortfahren, hebt der Editor die nächste Übereinstimmung hervor.</span><span class="sxs-lookup"><span data-stu-id="b15f9-114">As you continue typing, the editor moves to the next match and highlights it.</span></span> <span data-ttu-id="b15f9-115">Wenn es keine Übereinstimmungen gibt, wird in der Statusleiste Folgendes angezeigt:</span><span class="sxs-lookup"><span data-stu-id="b15f9-115">If no matches are available, the status bar displays the following.</span></span>  
  
    ```  
    Incremental Search: <text> (not found)  
    ```  
  
 <span data-ttu-id="b15f9-116">Inkrementelle Suchvorgänge werden abwärts von links nach rechts von der aktuellen Position im Dokument ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b15f9-116">Incremental searches are performed from the current location in the document downwards from left to right.</span></span> <span data-ttu-id="b15f9-117">Inkrementelle Suchvorgänge können mithilfe von Tastenkombinationen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b15f9-117">Incremental searches can be done using keyboard shortcut keys.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b15f9-118">Eine vollständige Liste der Tastenkombinationen finden Sie unter [Tastenkombinationen für SQL Server Management Studio](../../ssms/sql-server-management-studio-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="b15f9-118">For a complete list of keyboard shortcut keys, see [SQL Server Management Studio Keyboard Shortcuts](../../ssms/sql-server-management-studio-keyboard-shortcuts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b15f9-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b15f9-119">See Also</span></span>  
 <span data-ttu-id="b15f9-120">[Suchen und Ersetzen](search-and-replace.md) </span><span class="sxs-lookup"><span data-stu-id="b15f9-120">[Search and Replace](search-and-replace.md) </span></span>  
 <span data-ttu-id="b15f9-121">[Interaktives Durchsuchen von Dokumenten](search-documents-interactively.md) </span><span class="sxs-lookup"><span data-stu-id="b15f9-121">[Search Documents Interactively](search-documents-interactively.md) </span></span>  
 <span data-ttu-id="b15f9-122">[Durchsuchen von Dokumenten mithilfe von Ergebnislisten](search-documents-using-results-lists.md) </span><span class="sxs-lookup"><span data-stu-id="b15f9-122">[Search Documents Using Results Lists](search-documents-using-results-lists.md) </span></span>  
 <span data-ttu-id="b15f9-123">[Suchen von Text mit Platzhaltern](search-text-with-wildcards.md) </span><span class="sxs-lookup"><span data-stu-id="b15f9-123">[Search Text with Wildcards](search-text-with-wildcards.md) </span></span>  
 [<span data-ttu-id="b15f9-124">Suchen von Text mit regulären Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="b15f9-124">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
  
  
