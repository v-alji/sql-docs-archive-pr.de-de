---
title: Verwalten des Editors und des Ansichtsmodus
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Query Editor [SQL Server Management Studio], managing window behavior
- workbench view modes [SQL Server Management Studio]
- full screen mode [SQL Server Management Studio]
- fonts [SQL Server Management Studio]
- word wraps [SQL Server Management Studio]
- virtual space mode [SQL Server Management Studio]
- splitting document views
- displaying line numbers
- view modes [SQL Server Management Studio]
ms.assetid: 25c58a14-9f94-4296-9770-7d84c6bc3969
author: rothja
ms.author: jroth
ms.openlocfilehash: 36788b1fe831a6c15c4aa0668d1759c088fcaa73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621465"
---
# <a name="manage-the-editor-and-view-mode"></a><span data-ttu-id="9ac08-102">Verwalten des Editors und des Ansichtsmodus</span><span class="sxs-lookup"><span data-stu-id="9ac08-102">Manage the Editor and View Mode</span></span>
  <span data-ttu-id="9ac08-103">Der Editor bietet mehrere Möglichkeiten, die Ansicht des Codes zu steuern.</span><span class="sxs-lookup"><span data-stu-id="9ac08-103">The Editor gives you a number of ways to control the view of your code.</span></span>  
  
## <a name="changing-the-view-mode"></a><span data-ttu-id="9ac08-104">Ändern des Ansichtsmodus</span><span class="sxs-lookup"><span data-stu-id="9ac08-104">Changing the View Mode</span></span>  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="9ac08-105">verfügt über einen Ansichtsmodus namens **Dokumente im Registerformat**. In diesem Modus können Sie mehrere Editoren und Dokumente gleichzeitig öffnen und über Registerkarten am oberen Rand des Editors auf diese zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9ac08-105">features a view mode called **Tabbed Documents**, which allows you to open multiple editors and documents simultaneously and access them through tabs at the top of the Editor.</span></span> <span data-ttu-id="9ac08-106">Alternativ können Sie die [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] -Umgebung im Modus für eine mehrfache Dokumentschnittstelle (MDI, Multiple Document Interface) öffnen, bei dem Fenster ohne Registerkarten verknüpft werden und nebeneinander angezeigt, minimiert oder ähnlich behandelt werden können.</span><span class="sxs-lookup"><span data-stu-id="9ac08-106">You can alternatively open the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] environment in Multiple Document Interface (MDI) mode, which joins windows without the tabs, and allows each window to be tiled, minimized, and so on.</span></span>  
  
#### <a name="to-switch-between-view-modes"></a><span data-ttu-id="9ac08-107">So wechseln Sie den Ansichtsmodus</span><span class="sxs-lookup"><span data-stu-id="9ac08-107">To switch between view modes</span></span>  
  
1.  <span data-ttu-id="9ac08-108">Klicken Sie im Menü **Extras** auf **Optionen** .</span><span class="sxs-lookup"><span data-stu-id="9ac08-108">Click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="9ac08-109">Klicken Sie auf **Umgebung**.</span><span class="sxs-lookup"><span data-stu-id="9ac08-109">Click **Environment**.</span></span> <span data-ttu-id="9ac08-110">Klicken Sie auf **Allgemein**.</span><span class="sxs-lookup"><span data-stu-id="9ac08-110">Click **General**.</span></span>  
  
3.  <span data-ttu-id="9ac08-111">Klicken Sie auf **Dokumente im Registerformat** oder **MDI-Umgebung**.</span><span class="sxs-lookup"><span data-stu-id="9ac08-111">Click **Tabbed documents** or **MDI environment**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9ac08-112">Die Änderungen werden erst beim Neustart von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] wirksam.</span><span class="sxs-lookup"><span data-stu-id="9ac08-112">The changes will not take effect until [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is restarted.</span></span>  
  
## <a name="splitting-the-view"></a><span data-ttu-id="9ac08-113">Teilen der Ansicht</span><span class="sxs-lookup"><span data-stu-id="9ac08-113">Splitting the View</span></span>  
 <span data-ttu-id="9ac08-114">Ein Editor-Fenster kann zum einfacheren Bearbeiten in zwei Teile geteilt werden.</span><span class="sxs-lookup"><span data-stu-id="9ac08-114">An Editor window can be split into two separate parts for easier editing.</span></span>  
  
#### <a name="to-split-a-window"></a><span data-ttu-id="9ac08-115">So teilen Sie ein Fenster</span><span class="sxs-lookup"><span data-stu-id="9ac08-115">To split a window</span></span>  
  
1.  <span data-ttu-id="9ac08-116">Klicken Sie auf die Teilerleiste (über der Bildlaufleiste).</span><span class="sxs-lookup"><span data-stu-id="9ac08-116">Click the splitter bar (located above the scroll bar).</span></span>  
  
2.  <span data-ttu-id="9ac08-117">Ziehen Sie die Teilerleiste nach unten.</span><span class="sxs-lookup"><span data-stu-id="9ac08-117">Drag the splitter bar downward.</span></span>  
  
3.  <span data-ttu-id="9ac08-118">Um wieder zu einem einzelnen Bereich zu wechseln, doppelklicken Sie auf die Teilerleiste zwischen den beiden Bereichen.</span><span class="sxs-lookup"><span data-stu-id="9ac08-118">To go back to a single pane, double-click the splitter bar dividing the two panes.</span></span>  
  
 <span data-ttu-id="9ac08-119">Der neue Bereich enthält dasselbe Dokument. Alle Änderungen in einem Bereich werden auch im anderen Bereich wiedergegeben, sofern dieser Bereich dieselbe Stelle im Dokument anzeigt.</span><span class="sxs-lookup"><span data-stu-id="9ac08-119">The new pane contains the same document, and any changes made to one pane are reflected in the other pane as long as that pane displays the same place in the document.</span></span>  
  
## <a name="word-wrap"></a><span data-ttu-id="9ac08-120">Zeilenumbruch</span><span class="sxs-lookup"><span data-stu-id="9ac08-120">Word Wrap</span></span>  
 <span data-ttu-id="9ac08-121">Wenn Sie den Zeilenumbruch aktivieren, wird die horizontale Bildlaufleiste entfernt, und Codezeilen, die die Breite des Editor-Fensters überschreiten, werden automatisch in die nächste angezeigte Zeile umgebrochen, während sie sonst durch einen Bildlauf nach rechts vollständig angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="9ac08-121">When you activate Word Wrap, the horizontal scrollbar is removed and lines of code that exceed the width of the Editor's window size automatically wraps to the next displayed line rather than scrolling off the side of the window.</span></span>  
  
#### <a name="to-activate-word-wrap"></a><span data-ttu-id="9ac08-122">So aktivieren Sie den Zeilenumbruch</span><span class="sxs-lookup"><span data-stu-id="9ac08-122">To activate word wrap</span></span>  
  
1.  <span data-ttu-id="9ac08-123">Klicken Sie im Menü **Extras** auf **Optionen** .</span><span class="sxs-lookup"><span data-stu-id="9ac08-123">Click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="9ac08-124">Klicken Sie auf **Text-Editor**.</span><span class="sxs-lookup"><span data-stu-id="9ac08-124">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="9ac08-125">Öffnen Sie den entsprechenden Sprachordner (oder **Alle Sprachen** , wenn alle Sprachen betroffen sein sollen).</span><span class="sxs-lookup"><span data-stu-id="9ac08-125">Open the appropriate language folder (or **All Languages** to affect all languages).</span></span>  
  
4.  <span data-ttu-id="9ac08-126">Wählen Sie **Zeilenumbruch**.</span><span class="sxs-lookup"><span data-stu-id="9ac08-126">Select **Word wrap**.</span></span>  
  
## <a name="enabling-virtual-space-mode"></a><span data-ttu-id="9ac08-127">Aktivieren des Modus des virtuellen Bereichs</span><span class="sxs-lookup"><span data-stu-id="9ac08-127">Enabling Virtual Space Mode</span></span>  
 <span data-ttu-id="9ac08-128">Im Modus des **virtuellen Bereichs** verhält sich der Editor, als ob der Bereich nach dem Zeilenende mit einer unendlichen Anzahl von Leerzeichen gefüllt wäre, sodass Codezeilen außerhalb des sichtbaren Bildschirmbereichs fortgesetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="9ac08-128">In **Virtual Space** mode, the Editor acts as if the space past the end of each line is filled with an infinite number of spaces, allowing code lines to continue off the side of the visible screen area.</span></span>  
  
#### <a name="to-enable-virtual-space-mode"></a><span data-ttu-id="9ac08-129">So aktivieren Sie den Modus des virtuellen Bereichs</span><span class="sxs-lookup"><span data-stu-id="9ac08-129">To enable Virtual Space mode</span></span>  
  
1.  <span data-ttu-id="9ac08-130">Klicken Sie im Menü **Extras** auf **Optionen** .</span><span class="sxs-lookup"><span data-stu-id="9ac08-130">Click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="9ac08-131">Klicken Sie auf **Text-Editor**.</span><span class="sxs-lookup"><span data-stu-id="9ac08-131">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="9ac08-132">Öffnen Sie den entsprechenden Sprachordner (oder **Alle Sprachen** , wenn alle Sprachen betroffen sein sollen).</span><span class="sxs-lookup"><span data-stu-id="9ac08-132">Open the appropriate language folder (or **All Languages** to affect all languages).</span></span>  
  
4.  <span data-ttu-id="9ac08-133">Wählen Sie **Virtuellen Bereich aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="9ac08-133">Select **Enable virtual space**.</span></span>  
  
 <span data-ttu-id="9ac08-134">Wenn der Modus des virtuellen Bereichs nicht aktiviert ist, bricht die Zeile am Ende mit dem ersten Zeichen der nächsten Zeile um und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="9ac08-134">When Virtual Space mode is not enabled, the cursor wraps from the end of one line to the first character of the next line and vice-versa.</span></span>  
  
## <a name="displaying-line-numbers"></a><span data-ttu-id="9ac08-135">Anzeigen von Zeilennummern</span><span class="sxs-lookup"><span data-stu-id="9ac08-135">Displaying Line Numbers</span></span>  
 <span data-ttu-id="9ac08-136">Sie können Zeilennummerierung für den Code aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9ac08-136">You can turn on line numbering in your code.</span></span> <span data-ttu-id="9ac08-137">Zeilennummern sind hilfreich zum Navigieren im Code.</span><span class="sxs-lookup"><span data-stu-id="9ac08-137">Line numbers are useful for navigating code.</span></span> <span data-ttu-id="9ac08-138">Weitere Informationen finden Sie unter [Navigieren in Code und Text](navigate-code-and-text.md).</span><span class="sxs-lookup"><span data-stu-id="9ac08-138">For more information, see [Navigate Code and Text](navigate-code-and-text.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9ac08-139">Das Aktivieren der Zeilennummerierung bedeutet nicht, dass das Dokument mit Zeilennummern gedruckt wird.</span><span class="sxs-lookup"><span data-stu-id="9ac08-139">Turning on line numbering does not mean that the document will print with line numbers.</span></span> <span data-ttu-id="9ac08-140">Zum Drucken von Zeilennummern müssen Sie im Menü **Datei** im Befehl **Seite einrichten** das Kontrollkästchen **Zeilennummern** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9ac08-140">For line numbers to print, you must select the **Line numbers** check box in the **Page Setup** command on the **File** menu.</span></span>  
  
#### <a name="to-display-line-numbers-in-code"></a><span data-ttu-id="9ac08-141">So zeigen Sie Code mit Zeilennummern an</span><span class="sxs-lookup"><span data-stu-id="9ac08-141">To display line numbers in code</span></span>  
  
1.  <span data-ttu-id="9ac08-142">Klicken Sie im Menü **Extras** auf **Optionen** .</span><span class="sxs-lookup"><span data-stu-id="9ac08-142">Click **Options** on the **Tools** menu.</span></span>  
  
2.  <span data-ttu-id="9ac08-143">Klicken Sie auf **Text-Editor**.</span><span class="sxs-lookup"><span data-stu-id="9ac08-143">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="9ac08-144">Klicken Sie auf **Alle Sprachen**.</span><span class="sxs-lookup"><span data-stu-id="9ac08-144">Click **All Languages**.</span></span>  
  
4.  <span data-ttu-id="9ac08-145">Klicken Sie auf **Allgemein**.</span><span class="sxs-lookup"><span data-stu-id="9ac08-145">Click **General**.</span></span>  
  
5.  <span data-ttu-id="9ac08-146">Wählen Sie **Zeilennummern**aus.</span><span class="sxs-lookup"><span data-stu-id="9ac08-146">Select **Line numbers**.</span></span>  
  
 <span data-ttu-id="9ac08-147">Wenn Sie die Zeilennummerierung nur für einige Programmiersprachen angeben möchten, wählen Sie **Zeilennummern** nur in bestimmten Ordnern aus.</span><span class="sxs-lookup"><span data-stu-id="9ac08-147">To specify line numbering for only some programming languages, select **Line Numbers** in the appropriate folder.</span></span>  
  
## <a name="enabling-full-screen-mode"></a><span data-ttu-id="9ac08-148">Aktivieren des Vollbildmodus</span><span class="sxs-lookup"><span data-stu-id="9ac08-148">Enabling Full Screen Mode</span></span>  
 <span data-ttu-id="9ac08-149">Durch Aktivieren des Vollbildmodus können Sie alle Toolfenster ausblenden und nur Dokumentfenster anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9ac08-149">You can choose to hide all tool windows and view only document windows by enabling Full Screen mode.</span></span>  
  
#### <a name="to-enable-full-screen-mode"></a><span data-ttu-id="9ac08-150">So aktivieren Sie den Vollbildmodus</span><span class="sxs-lookup"><span data-stu-id="9ac08-150">To enable Full Screen mode</span></span>  
  
1.  <span data-ttu-id="9ac08-151">Drücken Sie ALT+UMSCHALT+EINGABE, um den Vollbildmodus umzuschalten.</span><span class="sxs-lookup"><span data-stu-id="9ac08-151">Press ALT+SHIFT+ENTER to toggle Full Screen mode.</span></span>  
  
## <a name="using-auto-hide-all"></a><span data-ttu-id="9ac08-152">Verwenden der automatischen Ausblendung</span><span class="sxs-lookup"><span data-stu-id="9ac08-152">Using Auto Hide All</span></span>  
  
#### <a name="to-hide-all-the-tool-windows-at-once"></a><span data-ttu-id="9ac08-153">So blenden Sie alle Toolfenster gleichzeitig aus</span><span class="sxs-lookup"><span data-stu-id="9ac08-153">To hide all the tool windows at once</span></span>  
  
1.  <span data-ttu-id="9ac08-154">Wählen Sie im Menü **Fenster** die Option **Alle automatisch ausblenden** .</span><span class="sxs-lookup"><span data-stu-id="9ac08-154">Select **Auto Hide All** on the **Window** menu.</span></span>  
  
  
