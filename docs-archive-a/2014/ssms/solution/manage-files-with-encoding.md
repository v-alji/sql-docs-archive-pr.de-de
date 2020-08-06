---
title: Verwalten von Dateien mit Codierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- files [SQL Server Management Studio]
- encoding [SQL Server Management Studio]
- files [SQL Server Management Studio], encoding
ms.assetid: 919544c9-59f0-4cc6-bb2a-f1ad671eb74b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9b0aaa123001fed3f6ad42ea9d642e4007e2640f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630453"
---
# <a name="manage-files-with-encoding"></a><span data-ttu-id="c3006-102">Verwalten von Dateien mit Codierung</span><span class="sxs-lookup"><span data-stu-id="c3006-102">Manage Files with Encoding</span></span>
  <span data-ttu-id="c3006-103">Um die Anzeige von Code in einer bestimmten Sprache und auf einer bestimmten Plattform zu vereinfachen, können Sie einer Datei eine bestimmte Zeichencodierung zuordnen.</span><span class="sxs-lookup"><span data-stu-id="c3006-103">To facilitate the display of your code in a particular language and on a particular platform, you can associate a particular character encoding with a file.</span></span>  
  
## <a name="opening-files"></a><span data-ttu-id="c3006-104">Öffnen von Dateien</span><span class="sxs-lookup"><span data-stu-id="c3006-104">Opening Files</span></span>  
 <span data-ttu-id="c3006-105">Sie können zum Bearbeiten der Datei einen Editor Ihrer Wahl verwenden.</span><span class="sxs-lookup"><span data-stu-id="c3006-105">You can choose the editor you want to use to edit the file.</span></span>  
  
#### <a name="to-open-a-file-with-a-specific-editor"></a><span data-ttu-id="c3006-106">So öffnen Sie eine Datei mit einem bestimmten Editor</span><span class="sxs-lookup"><span data-stu-id="c3006-106">To open a file with a specific editor</span></span>  
  
1.  <span data-ttu-id="c3006-107">Zeigen Sie im Menü **Datei** auf **Öffnen**, und klicken Sie dann auf **Datei**.</span><span class="sxs-lookup"><span data-stu-id="c3006-107">On the **File** menu, point to **Open**, and then click **File**.</span></span>  
  
2.  <span data-ttu-id="c3006-108">Wählen Sie im Dialogfeld **Datei öffnen** den Dateinamen aus.</span><span class="sxs-lookup"><span data-stu-id="c3006-108">In the **Open File** dialog box, select the file name.</span></span>  
  
3.  <span data-ttu-id="c3006-109">Klicken Sie auf den Pfeil neben der Schaltfläche **Öffnen** , und klicken Sie dann im angezeigten Menü auf**Öffnen mit** .</span><span class="sxs-lookup"><span data-stu-id="c3006-109">Click the arrow next to the **Open** button, and then click**Open With** from the menu that appears.</span></span>  
  
4.  <span data-ttu-id="c3006-110">Wählen Sie in der Liste **Wählen Sie das zu öffnende Programm aus** einen Editor aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="c3006-110">In the **Select a program to open** list, select an editor, and then click **Open**.</span></span> <span data-ttu-id="c3006-111">Wählen Sie zum Öffnen einer Datei mit einer bestimmten Codierung einen Editor mit Codierungsunterstützung aus, z. B. den SQL-Abfrage-Editor mit Codierung oder den XML-Editor mit Codierung.</span><span class="sxs-lookup"><span data-stu-id="c3006-111">To open the file with a particular encoding, select an editor with encoding support, such as SQL Query Editor with Encoding or XML Editor with Encoding.</span></span>  
  
## <a name="saving-files"></a><span data-ttu-id="c3006-112">Speichern von Dateien</span><span class="sxs-lookup"><span data-stu-id="c3006-112">Saving Files</span></span>  
 <span data-ttu-id="c3006-113">Sie können Code auch mit Unicode-Codierung oder einer anderen Codepage speichern, um verschiedene Sprachen zu unterstützen, z. B. Westeuropäisch oder Osteuropäisch.</span><span class="sxs-lookup"><span data-stu-id="c3006-113">You can also save your code with a Unicode encoding or a different code page to support various languages, such as Western European or Eastern European.</span></span> <span data-ttu-id="c3006-114">Sie können einer Datei eine bestimmte Zeichencodierung zuordnen, um die Anzeige von Code in dieser Sprache zu vereinfachen, sowie einen Zeilenendentyp zur Unterstützung eines bestimmten Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="c3006-114">You can associate a particular character encoding with a file to facilitate the display of your code in that language, as well as a line-ending type to support a particular operating system.</span></span> <span data-ttu-id="c3006-115">Darüber hinaus können einige Zeichen in Dateinamen nur gespeichert werden, wenn sie mit Unicode-Codierung gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="c3006-115">Also, some characters, when used in file names, cannot be saved unless they are saved with Unicode encoding.</span></span>  
  
#### <a name="to-save-a-file-with-a-different-encoding-or-line-ending-type"></a><span data-ttu-id="c3006-116">So speichern Sie eine Datei mit einer anderen Codierung oder einem anderen Zeilenendentyp</span><span class="sxs-lookup"><span data-stu-id="c3006-116">To save a file with a different encoding or line ending type</span></span>  
  
1.  <span data-ttu-id="c3006-117">Zeigen Sie im Menü **Datei** auf **Speichern \<filename> unter**.</span><span class="sxs-lookup"><span data-stu-id="c3006-117">On the **File** menu, click **Save \<filename> As**.</span></span>  
  
2.  <span data-ttu-id="c3006-118">Erweitern Sie im Dialogfeld **Datei speichern unter** die Schaltfläche **Speichern** , und klicken Sie dann auf **Mit Codierung speichern**.</span><span class="sxs-lookup"><span data-stu-id="c3006-118">In the **Save File As** dialog, expand the **Save** button, and then click **Save with Encoding**.</span></span>  
  
3.  <span data-ttu-id="c3006-119">Wählen Sie im Dialogfeld **Erweiterte Speicheroptionen** in der Liste **Codierung** die gewünschte Codierung aus.</span><span class="sxs-lookup"><span data-stu-id="c3006-119">In the **Advanced Save Options** dialog box, select the encoding you want from the **Encoding** list.</span></span>  
  
4.  <span data-ttu-id="c3006-120">Wählen Sie in der Liste **Zeilenenden**den gewünschten Zeilenendentyp aus.</span><span class="sxs-lookup"><span data-stu-id="c3006-120">From the **Line Endings**list, select the type of line ending you want.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c3006-121">Wenn Sie die Datei mit Unicode-Codierung speichern, muss die Datei in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual SourceSafe als Binärdatei eingecheckt werden, da Visual SourceSafe keine Unterstützung für das Zusammenführen, Vergleichen und Anzeigen von Unterschieden zwischen Dateien bietet, die mit Unicode-Codierung gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="c3006-121">If you save your file your file with Unicode encoding, the file should be checked into [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual SourceSafe as a binary file because Visual SourceSafe does not support merging, comparing, and showing differences between files that are saved as Unicode.</span></span>  
  
 <span data-ttu-id="c3006-122">Wenn Sie mit Visual SourceSafe Dateien mit ANSI-, UTF8- oder Unicode-Codierung speichern, beachten Sie die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="c3006-122">If you are using Visual SourceSafe to store files with ANSI, UTF8, or Unicode, be aware of the following limitations for each:</span></span>  
  
-   <span data-ttu-id="c3006-123">Bei ANSI-Dateien sind nur Zeichen zulässig, die in der aktuellen Codepage unterstützt werden, wodurch die internationale Verwendung eingeschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="c3006-123">ANSI files allow only characters that are supported in the current code page, which limits international use.</span></span>  
  
-   <span data-ttu-id="c3006-124">Bei Unicode-Dateien können die Funktionen zum freigegebenen Auschecken, Überprüfen von Unterschieden oder Zusammenführen nicht verwendet werden, da sie als Binärdateien behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="c3006-124">Unicode files cannot use shared checkout, difference checking, or merging functionality because they are handled as binary files.</span></span> <span data-ttu-id="c3006-125">Sie können dieses Format in internationalen Dateien verwenden.</span><span class="sxs-lookup"><span data-stu-id="c3006-125">You can use this format in international files.</span></span>  
  
-   <span data-ttu-id="c3006-126">UTF8-Dateien funktionieren nicht sicher mit Visual SourceSafe, da Änderungen, die für Editoren von UTF8-Dateien Probleme verursachen, beim Einchecken, Auschecken, Überprüfen von Unterschieden und Zusammenführen vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="c3006-126">UTF8 files do not work safely with Visual SourceSafe because changes that cause problems for UTF8 file editors are made during check in, check out, difference checking, and merging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3006-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c3006-127">See Also</span></span>  
 <span data-ttu-id="c3006-128">[Dateien zum Verwalten von Projektmappen und Projekten](files-that-manage-solutions-and-projects.md) </span><span class="sxs-lookup"><span data-stu-id="c3006-128">[Files That Manage Solutions and Projects](files-that-manage-solutions-and-projects.md) </span></span>  
 [<span data-ttu-id="c3006-129">Zuordnen von Dateierweiterungen zu einem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="c3006-129">Associate File Extensions to a Code Editor</span></span>](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md)  
  
  
