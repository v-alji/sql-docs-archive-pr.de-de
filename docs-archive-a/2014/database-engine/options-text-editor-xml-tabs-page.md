---
title: 'Optionen (Text-Editor: XML: Seite "Registerkarten") | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.XML.Tabs
ms.assetid: 13bf5f8c-aba3-4c05-b8bb-eb475797c9bd
author: rothja
ms.author: jroth
ms.openlocfilehash: 3047d6c05ffb88d07a4bf2e5b1d4143412046c04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694681"
---
# <a name="options-text-editorxmltabs-page"></a><span data-ttu-id="5cb60-102">Optionen (Text-Editor: XML: Seite „Tabstopps“)</span><span class="sxs-lookup"><span data-stu-id="5cb60-102">Options (Text Editor:XML:Tabs Page)</span></span>
  <span data-ttu-id="5cb60-103">Mithilfe dieses Dialogfelds können Sie das Tabulatorverhalten des XML-Editors ändern, der für die Bearbeitung von XML-Dokumenten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5cb60-103">This dialog box lets you change the tabbing behavior of the XML Editor, which is used to edit XML documents.</span></span> <span data-ttu-id="5cb60-104">Zum Anzeigen dieser Einstellungen klicken Sie im Menü **Extras** auf **Optionen** , und erweitern Sie anschließend den Ordner **Text-Editor** , dann den Unterordner **XML** , und klicken Sie dann auf **Tabstopps**.</span><span class="sxs-lookup"><span data-stu-id="5cb60-104">To display these settings, click **Options** on the **Tools** menu, expand the **Text Editor** folder, expand the **XML** subfolder and then click **Tabs**.</span></span>  
  
## <a name="setting-options-in-multiple-locations"></a><span data-ttu-id="5cb60-105">Festlegen der Optionen an mehreren Stellen</span><span class="sxs-lookup"><span data-stu-id="5cb60-105">Setting Options in Multiple Locations</span></span>  
 <span data-ttu-id="5cb60-106">Optionen für den XML-Editor können auch im Dialogfeld **Alle Sprachen/Allgemein** festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="5cb60-106">Options for the XML Editor can also be set in the **All Languages General** dialog.</span></span> <span data-ttu-id="5cb60-107">Wenn Sie die Dialogfelder **alle Sprachen** verwenden, um verschiedene Optionen für die anderen [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] Editoren festzulegen, z. b. den DMX-oder MDX-Editoren, müssen Sie die XML-Editor-Optionen mithilfe dieses Dialog Felds zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="5cb60-107">If you use the **All Languages** dialogs to set different options for the other [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] editors, such as the DMX or MDX editors, you must reset the XML Editor options using this dialog.</span></span>  
  
## <a name="indenting"></a><span data-ttu-id="5cb60-108">Einzug</span><span class="sxs-lookup"><span data-stu-id="5cb60-108">Indenting</span></span>  
 <span data-ttu-id="5cb60-109">**None**</span><span class="sxs-lookup"><span data-stu-id="5cb60-109">**None**</span></span>  
 <span data-ttu-id="5cb60-110">Wenn diese Option ausgewählt ist, wird die neue Zeile, die nach dem Drücken der EINGABETASTE erstellt wird, nicht eingerückt.</span><span class="sxs-lookup"><span data-stu-id="5cb60-110">When this option is selected, the new line created when you press ENTER is not indented.</span></span> <span data-ttu-id="5cb60-111">Der Cursor wird in der ersten Spalte der neuen Zeile platziert.</span><span class="sxs-lookup"><span data-stu-id="5cb60-111">The cursor is placed at the first column of the new line.</span></span>  
  
 <span data-ttu-id="5cb60-112">**Blockieren**</span><span class="sxs-lookup"><span data-stu-id="5cb60-112">**Block**</span></span>  
 <span data-ttu-id="5cb60-113">Wenn diese Option ausgewählt ist, wird die nach dem Drücken der Eingabetaste erstellte Zeile automatisch so weit eingerückt wie die vorige Zeile.</span><span class="sxs-lookup"><span data-stu-id="5cb60-113">When this option is selected, the new line created when you press ENTER is automatically indented the same distance as the previous line.</span></span>  
  
 <span data-ttu-id="5cb60-114">**Intelligent**</span><span class="sxs-lookup"><span data-stu-id="5cb60-114">**Smart**</span></span>  
 <span data-ttu-id="5cb60-115">Wenn diese Option ausgewählt ist, wird die nach dem Drücken der Eingabetaste erstellte Zeile je nach Kontext eingerückt.</span><span class="sxs-lookup"><span data-stu-id="5cb60-115">When this option is selected, the new line created when you press ENTER is positioned according to the context.</span></span> <span data-ttu-id="5cb60-116">Nach einer öffnenden geschweiften Klammer ({) werden beispielsweise die eingeschlossenen Zeilen automatisch um einen zusätzlichen Tabstopp eingerückt.</span><span class="sxs-lookup"><span data-stu-id="5cb60-116">For example, after an opening brace ({), the included lines are automatically indented an extra tab stop.</span></span> <span data-ttu-id="5cb60-117">Die dazugehörige schließende geschweifte Klammer (}) wird wieder auf die öffnende Klammer ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="5cb60-117">The matching closing brace (}) is realigned with its opening brace.</span></span>  
  
## <a name="tabs"></a><span data-ttu-id="5cb60-118">Registerkarten</span><span class="sxs-lookup"><span data-stu-id="5cb60-118">Tabs</span></span>  
 <span data-ttu-id="5cb60-119">**Tabulatorgröße**</span><span class="sxs-lookup"><span data-stu-id="5cb60-119">**Tab size**</span></span>  
 <span data-ttu-id="5cb60-120">Legt den Abstand zwischen den Tabstopps fest.</span><span class="sxs-lookup"><span data-stu-id="5cb60-120">Sets the distance in spaces between tab stops.</span></span> <span data-ttu-id="5cb60-121">Der Standardwert ist vier Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="5cb60-121">The default is four spaces.</span></span>  
  
 <span data-ttu-id="5cb60-122">**Einzugsgröße**</span><span class="sxs-lookup"><span data-stu-id="5cb60-122">**Indent size**</span></span>  
 <span data-ttu-id="5cb60-123">Legt die Größe des automatischen Einzugs in Leerzeichen fest.</span><span class="sxs-lookup"><span data-stu-id="5cb60-123">Sets the size in spaces of an automatic indentation.</span></span> <span data-ttu-id="5cb60-124">Der Standardwert ist vier Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="5cb60-124">The default is four spaces.</span></span> <span data-ttu-id="5cb60-125">Es werden entweder Tabstopps, Leerzeichen oder beide verwendet, um den angegebenen Raum zu füllen.</span><span class="sxs-lookup"><span data-stu-id="5cb60-125">Tab characters, space characters, or both are inserted to fill the specified size.</span></span>  
  
 <span data-ttu-id="5cb60-126">**Leerzeichen einfügen**</span><span class="sxs-lookup"><span data-stu-id="5cb60-126">**Insert spaces**</span></span>  
 <span data-ttu-id="5cb60-127">Wenn diese Option ausgewählt ist, werden bei Einzugsfunktionen nur Leerzeichen eingefügt, keine Tabulatorzeichen.</span><span class="sxs-lookup"><span data-stu-id="5cb60-127">When this option is selected, indent operations insert only space characters, not tab characters.</span></span> <span data-ttu-id="5cb60-128">Wenn die Einzugs **Größe** z. b. auf 5 festgelegt ist, werden fünf Leerzeichen eingefügt, wenn Sie die Tab-Taste drücken oder auf der Symbolleiste im Hauptfenster auf die Schaltfläche **Einzug vergrößern** klicken [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5cb60-128">If **Indent size** is set to 5, for example, then five space characters are inserted whenever you press the TAB key or click the **Increase Indent** button on the toolbar in the main [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] window.</span></span>  
  
 <span data-ttu-id="5cb60-129">**Tabulatoren beibehalten**</span><span class="sxs-lookup"><span data-stu-id="5cb60-129">**Keep tabs**</span></span>  
 <span data-ttu-id="5cb60-130">Wenn diese Option ausgewählt ist, werden bei Einzugsfunktionen so viele Tabulatorzeichen wie möglich eingefügt.</span><span class="sxs-lookup"><span data-stu-id="5cb60-130">When this option is selected, indent operations insert as many tab characters as possible.</span></span> <span data-ttu-id="5cb60-131">Jedes Tabulatorzeichen nimmt den Platz so vieler Leerzeichen ein, wie im Feld **Tabulatorgröße**definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="5cb60-131">Each tab character fills the number of spaces specified in **Tab size**.</span></span> <span data-ttu-id="5cb60-132">Wenn die **Einzugsgröße** kein ganzes Vielfaches der **Tabulatorgröße**ist, werden zum Auffüllen der Differenz Leerzeichen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5cb60-132">If **Indent size** is not an even multiple of **Tab size**, space characters are added to fill in the difference.</span></span>  
  
  
