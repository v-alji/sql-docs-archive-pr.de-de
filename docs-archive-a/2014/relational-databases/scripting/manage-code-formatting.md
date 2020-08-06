---
title: Verwalten der Codeformatierung
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- indenting code [SQL Server]
- displaying URLs
- code formatting [SQL Server Management Studio]
- collapsing text
- formats [SQL Server], code formatting in SQL Server Management Studio
- hiding text
- formats [SQL Server]
- text [SQL Server], code formats
- automatic indentation
- converting text to lower case
- Query Editor [SQL Server Management Studio], managing code formats
- URL displayed in code [SQL Server Management Studio]
- converting text to upper case
- text [SQL Server]
- unindenting code
ms.assetid: ddbac4d2-6bdc-4467-a352-e869ec880eed
author: rothja
ms.author: jroth
ms.openlocfilehash: 873848c8aee575b47f7a3d8c31d8392cba5ed12e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622523"
---
# <a name="manage-code-formatting"></a><span data-ttu-id="1779c-102">Verwalten der Codeformatierung</span><span class="sxs-lookup"><span data-stu-id="1779c-102">Manage Code Formatting</span></span>
  <span data-ttu-id="1779c-103">Mit dem Editor können Sie Code formatieren, z. B. mit Einzug, ausgeblendetem Text, URLs usw.</span><span class="sxs-lookup"><span data-stu-id="1779c-103">With the Editor you can format your code with indenting, hidden text, URLs, and so forth.</span></span> <span data-ttu-id="1779c-104">Außerdem können Sie mit dem intelligenten Einzug den Code automatisch bei der Eingabe formatieren.</span><span class="sxs-lookup"><span data-stu-id="1779c-104">You can also auto-format your code as you type by using Smart Indenting.</span></span>  
  
## <a name="indenting"></a><span data-ttu-id="1779c-105">Einzug</span><span class="sxs-lookup"><span data-stu-id="1779c-105">Indenting</span></span>  
 <span data-ttu-id="1779c-106">Für den Texteinzug stehen drei verschiedene Stile zur Auswahl.</span><span class="sxs-lookup"><span data-stu-id="1779c-106">You can choose three different styles of text indenting.</span></span> <span data-ttu-id="1779c-107">Außerdem können Sie angeben, aus wie vielen Leerzeichen ein Einzug oder Tabstopp besteht und ob der Editor für den Einzug Tabulatoren oder Leerzeichen verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="1779c-107">You can also specify how many spaces compose a single indentation or tab, and whether the Editor uses tabs or space characters when indenting.</span></span>  
  
#### <a name="to-choose-an-indenting-style"></a><span data-ttu-id="1779c-108">So wählen Sie einen Einzugsstil aus</span><span class="sxs-lookup"><span data-stu-id="1779c-108">To choose an indenting style</span></span>  
  
1.  <span data-ttu-id="1779c-109">Klicken Sie im Menü **Extras** auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="1779c-109">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="1779c-110">Klicken Sie auf **Text-Editor**.</span><span class="sxs-lookup"><span data-stu-id="1779c-110">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="1779c-111">Klicken Sie auf den Ordner, und wählen Sie die Option **Alle Sprachen** aus, um den Einzug für alle Sprachen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="1779c-111">Click the folder, and select **All Languages** to set indenting for all languages.</span></span>  
  
4.  <span data-ttu-id="1779c-112">Klicken Sie auf **Tabstopps**.</span><span class="sxs-lookup"><span data-stu-id="1779c-112">Click **Tabs**.</span></span>  
  
5.  <span data-ttu-id="1779c-113">Klicken Sie auf eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="1779c-113">Click one of the following options:</span></span>  
  
    -   <span data-ttu-id="1779c-114">**Keine**.</span><span class="sxs-lookup"><span data-stu-id="1779c-114">**None**.</span></span> <span data-ttu-id="1779c-115">Der Cursor wechselt zum Anfang der nächsten Zeile.</span><span class="sxs-lookup"><span data-stu-id="1779c-115">The cursor goes to the beginning of the next line.</span></span>  
  
    -   <span data-ttu-id="1779c-116">**Blockierung**:</span><span class="sxs-lookup"><span data-stu-id="1779c-116">**Block**.</span></span> <span data-ttu-id="1779c-117">Der Cursor richtet die nächste Zeile an der vorherigen Zeile aus.</span><span class="sxs-lookup"><span data-stu-id="1779c-117">The cursor aligns the next line with the previous line.</span></span>  
  
    -   <span data-ttu-id="1779c-118">**Intelligent** (Standard).</span><span class="sxs-lookup"><span data-stu-id="1779c-118">**Smart** (Default).</span></span> <span data-ttu-id="1779c-119">Der Sprachdienst bestimmt den passenden Einzugsstil.</span><span class="sxs-lookup"><span data-stu-id="1779c-119">The language service determines the appropriate indenting style to use.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1779c-120">Für einige Sprachen sind nicht alle drei Einzugsoptionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1779c-120">Some languages do not offer all three indenting options.</span></span>  
  
#### <a name="to-change-indent-tab-settings"></a><span data-ttu-id="1779c-121">So ändern Sie die Einstellungen für Tabulatoreinzug</span><span class="sxs-lookup"><span data-stu-id="1779c-121">To change indent tab settings</span></span>  
  
1.  <span data-ttu-id="1779c-122">Klicken Sie im Menü **Extras** auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="1779c-122">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="1779c-123">Klicken Sie auf **Text-Editor**.</span><span class="sxs-lookup"><span data-stu-id="1779c-123">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="1779c-124">Wählen Sie den Ordner für **Alle Sprachen** aus, um den Einzug für alle Sprachen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="1779c-124">Select the folder for **All Languages** to set indenting for all languages.</span></span>  
  
4.  <span data-ttu-id="1779c-125">Klicken Sie auf **Tabstopps**.</span><span class="sxs-lookup"><span data-stu-id="1779c-125">Click **Tabs**.</span></span>  
  
5.  <span data-ttu-id="1779c-126">Zum Angeben von Tabulatorzeichen beim Verwenden von Tabstopps und Einzügen klicken Sie auf **Tabulatoren beibehalten**.</span><span class="sxs-lookup"><span data-stu-id="1779c-126">To specify tab characters for tab and indent operations, click **Keep tabs**.</span></span> <span data-ttu-id="1779c-127">Zum Angeben von Leerzeichen wählen Sie die Option **Leerzeichen einfügen**aus.</span><span class="sxs-lookup"><span data-stu-id="1779c-127">To specify space characters, select **Insert spaces**.</span></span>  
  
     <span data-ttu-id="1779c-128">Wenn Sie **Leerzeichen einfügen**auswählen, geben Sie die Anzahl der Leerzeichen für die einzelnen Tabstopps oder Einzüge unter **Tabulatorgröße** bzw. **Einzugsgröße**an.</span><span class="sxs-lookup"><span data-stu-id="1779c-128">If you select **Insert Spaces**, enter the number of space characters each tab or indent represents under **Tab Size** or **Indent Size**, respectively.</span></span>  
  
#### <a name="to-indent-code"></a><span data-ttu-id="1779c-129">So ziehen Sie Code ein</span><span class="sxs-lookup"><span data-stu-id="1779c-129">To indent code</span></span>  
  
1.  <span data-ttu-id="1779c-130">Wählen Sie den Text aus, den Sie einziehen möchten.</span><span class="sxs-lookup"><span data-stu-id="1779c-130">Select the text you want to indent.</span></span>  
  
2.  <span data-ttu-id="1779c-131">Drücken Sie die TAB-TASTE, oder klicken Sie auf der Standardsymbolleiste auf die Schaltfläche **Einzug** .</span><span class="sxs-lookup"><span data-stu-id="1779c-131">Press TAB, or click the **Indent** button on the Standard toolbar.</span></span>  
  
#### <a name="to-unindent-code"></a><span data-ttu-id="1779c-132">So heben Sie den Einzug für Code auf</span><span class="sxs-lookup"><span data-stu-id="1779c-132">To unindent code</span></span>  
  
1.  <span data-ttu-id="1779c-133">Wählen Sie den Text aus, für den Sie den Einzug aufheben möchten.</span><span class="sxs-lookup"><span data-stu-id="1779c-133">Select the text you want to unindent.</span></span>  
  
2.  <span data-ttu-id="1779c-134">Drücken Sie UMSCHALT+TAB, oder klicken Sie auf der Standardsymbolleiste auf die Schaltfläche **Einzug aufheben** .</span><span class="sxs-lookup"><span data-stu-id="1779c-134">Press SHIFT+TAB, or click the **Unindent** button on the Standard toolbar.</span></span>  
  
#### <a name="to-automatically-indent-all-of-your-code"></a><span data-ttu-id="1779c-135">So ziehen Sie den gesamten Code automatisch ein</span><span class="sxs-lookup"><span data-stu-id="1779c-135">To automatically indent all of your code</span></span>  
  
1.  <span data-ttu-id="1779c-136">Klicken Sie im Menü **Extras** auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="1779c-136">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="1779c-137">Klicken Sie auf **Text-Editor**.</span><span class="sxs-lookup"><span data-stu-id="1779c-137">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="1779c-138">Klicken Sie auf **Alle Sprachen**.</span><span class="sxs-lookup"><span data-stu-id="1779c-138">Click **All Languages**.</span></span>  
  
4.  <span data-ttu-id="1779c-139">Klicken Sie auf **Tabstopps**.</span><span class="sxs-lookup"><span data-stu-id="1779c-139">Click **Tabs**.</span></span>  
  
5.  <span data-ttu-id="1779c-140">Klicken Sie auf **Intelligent**.</span><span class="sxs-lookup"><span data-stu-id="1779c-140">Click **Smart**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1779c-141">Die Option **Intelligent** ist für einige Sprachen nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1779c-141">The **Smart** option is not available for some languages.</span></span>  
  
#### <a name="to-convert-white-space-to-tabs"></a><span data-ttu-id="1779c-142">So konvertieren Sie Leerzeichen in Tabstopps</span><span class="sxs-lookup"><span data-stu-id="1779c-142">To convert white space to tabs</span></span>  
  
1.  <span data-ttu-id="1779c-143">Wählen Sie den Text aus, dessen Leerzeichen in Tabstopps konvertiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1779c-143">Select the text whose white space you want to convert to tabs.</span></span>  
  
2.  <span data-ttu-id="1779c-144">Zeigen Sie im Menü **Bearbeiten** auf **Erweitert**, und klicken Sie dann auf **Auswahl mit Tabstopps versehen**.</span><span class="sxs-lookup"><span data-stu-id="1779c-144">On the **Edit** menu, point to **Advanced**, and click **Tabify Selection**.</span></span>  
  
#### <a name="to-convert-tabs-to-spaces"></a><span data-ttu-id="1779c-145">So konvertieren Sie Tabstopps in Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="1779c-145">To convert tabs to spaces</span></span>  
  
1.  <span data-ttu-id="1779c-146">Wählen Sie den Text aus, dessen Tabstopps in Leerzeichen konvertiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1779c-146">Select the text whose tabs you want to convert to spaces.</span></span>  
  
2.  <span data-ttu-id="1779c-147">Zeigen Sie im Menü **Bearbeiten** auf **Erweitert**, und klicken Sie dann auf **Tabstopps aus Auswahl entfernen**.</span><span class="sxs-lookup"><span data-stu-id="1779c-147">On the **Edit** menu, point to **Advanced**, and click **Untabify Selection**.</span></span>  
  
 <span data-ttu-id="1779c-148">Das Verhalten dieser Befehle hängt von den Tabulatoreinstellungen im Dialogfeld **Optionen** ab.</span><span class="sxs-lookup"><span data-stu-id="1779c-148">The behavior of these commands depends on the tab settings in the **Options** dialog box.</span></span> <span data-ttu-id="1779c-149">Wenn die Tabulatoreinstellung z. B. 4 lautet, wird durch den Befehl **Auswahl mit Tabstopps versehen** für jeweils vier aufeinander folgende Leerzeichen ein Tabstopp erstellt. Entsprechend werden durch den Befehl **Tabstopps aus Auswahl entfernen** für jeden Tabstopp vier Leerzeichen erstellt.</span><span class="sxs-lookup"><span data-stu-id="1779c-149">For example, if the tab setting is 4, **Tabify Selection** creates a tab for every 4 contiguous spaces, and **Untabify Selection** creates 4 spaces for every tab.</span></span>  
  
## <a name="converting-text-to-upper-and-lower-case"></a><span data-ttu-id="1779c-150">Konvertieren von Text in Groß- und Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="1779c-150">Converting Text to Upper and Lower Case</span></span>  
 <span data-ttu-id="1779c-151">Sie können Text mit den entsprechenden Befehlen vollständig in Groß- oder Kleinbuchstaben konvertieren.</span><span class="sxs-lookup"><span data-stu-id="1779c-151">You can use commands to convert text to all uppercase or lower case.</span></span>  
  
#### <a name="to-switch-text-to-upper-or-lower-case"></a><span data-ttu-id="1779c-152">So wandeln Sie Text in Groß- oder Kleinbuchstaben um</span><span class="sxs-lookup"><span data-stu-id="1779c-152">To switch text to upper or lower case</span></span>  
  
1.  <span data-ttu-id="1779c-153">Wählen Sie den Text aus, den Sie konvertieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1779c-153">Select the text you want to convert.</span></span>  
  
2.  <span data-ttu-id="1779c-154">Zum Konvertieren von Text in Großbuchstaben drücken Sie STRG+UMSCHALT+U, oder klicken Sie im Menü **Bearbeiten** im Untermenü **Erweitert** auf **In Großbuchstaben umwandeln** .</span><span class="sxs-lookup"><span data-stu-id="1779c-154">To convert text to uppercase, press CTRL+SHIFT+U, or click **Make Uppercase** on the **Advanced** submenu of the **Edit** menu.</span></span>  
  
3.  <span data-ttu-id="1779c-155">Zum Konvertieren von Text in Kleinbuchstaben drücken Sie STRG+UMSCHALT+L, oder klicken Sie im Menü **Bearbeiten** im Untermenü **Erweitert** auf **In Kleinbuchstaben umwandeln** .</span><span class="sxs-lookup"><span data-stu-id="1779c-155">To convert text to lowercase, press CTRL+SHIFT+L, or click **Make Lowercase** on the **Advanced** submenu of the **Edit** menu.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1779c-156">Eine vollständige Liste der Tastenkombinationen finden Sie unter [Tastenkombinationen für SQL Server Management Studio](../../ssms/sql-server-management-studio-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="1779c-156">For a complete list of keyboard shortcut keys, see [SQL Server Management Studio Keyboard Shortcuts](../../ssms/sql-server-management-studio-keyboard-shortcuts.md).</span></span>  
  
## <a name="displaying-and-linking-to-urls"></a><span data-ttu-id="1779c-157">Anzeigen von und Verknüpfen mit URLs</span><span class="sxs-lookup"><span data-stu-id="1779c-157">Displaying and Linking to URLs</span></span>  
 <span data-ttu-id="1779c-158">Sie können im Code klickbare URLs erstellen und anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1779c-158">You can create and display clickable URLs in your code.</span></span> <span data-ttu-id="1779c-159">Standardmäßig haben die URLs folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="1779c-159">By default, the URLs:</span></span>  
  
-   <span data-ttu-id="1779c-160">Sie sind unterstrichen.</span><span class="sxs-lookup"><span data-stu-id="1779c-160">Are underlined.</span></span>  
  
-   <span data-ttu-id="1779c-161">Der Mauszeiger nimmt die Form einer Hand an, wenn Sie ihn über eine URL bewegen.</span><span class="sxs-lookup"><span data-stu-id="1779c-161">Change the mouse pointer to a hand when you move over them.</span></span>  
  
-   <span data-ttu-id="1779c-162">Wenn die URL gültig ist, wird sie geöffnet, wenn Sie darauf klicken.</span><span class="sxs-lookup"><span data-stu-id="1779c-162">Open the URL when clicked, if the URL is valid.</span></span>  
  
#### <a name="to-display-a-clickable-url"></a><span data-ttu-id="1779c-163">So zeigen Sie eine klickbare URL an</span><span class="sxs-lookup"><span data-stu-id="1779c-163">To display a clickable URL</span></span>  
  
1.  <span data-ttu-id="1779c-164">Klicken Sie im Menü **Extras** auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="1779c-164">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="1779c-165">Klicken Sie auf **Text-Editor**.</span><span class="sxs-lookup"><span data-stu-id="1779c-165">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="1779c-166">Zum Ändern der Option für nur eine Sprache klicken Sie auf den entsprechenden Sprachordner, und klicken Sie dann auf **Allgemein**.</span><span class="sxs-lookup"><span data-stu-id="1779c-166">To change the option for only one language, click that language folder and then click **General**.</span></span> <span data-ttu-id="1779c-167">Zum Ändern der Option für alle Sprachen klicken Sie auf **Alle Sprachen** , und klicken Sie dann auf **Allgemein**.</span><span class="sxs-lookup"><span data-stu-id="1779c-167">To change the option for all languages, click **All Languages** and then click **General**.</span></span>  
  
4.  <span data-ttu-id="1779c-168">Wählen Sie die Option **Einfaches Klicken für URLs aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="1779c-168">Select **Enable single-click URL navigation**.</span></span>  
  
  
