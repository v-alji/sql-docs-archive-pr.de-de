---
title: Zuordnen von Dateierweiterungen zu einem Code-Editor
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- file extensions [SQL Server]
- associating file extensions [SQL Server]
- Query Editor [SQL Server Management Studio], associating file extensions
ms.assetid: 193630f4-93de-4950-8f36-68702531f925
author: rothja
ms.author: jroth
ms.openlocfilehash: 0e8cfbc89892a99971e985ffd3ff10b99f89fe53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616464"
---
# <a name="associate-file-extensions-to-a-code-editor"></a><span data-ttu-id="1f8ac-102">Zuordnen von Dateierweiterungen zu einem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="1f8ac-102">Associate File Extensions to a Code Editor</span></span>
  <span data-ttu-id="1f8ac-103">Wenn Sie Dateierweiterungen einem bestimmten Code-Editor zuordnen, werden entsprechende Dateien von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] mit dem jeweiligen Code-Editor geöffnet, wenn Sie in Windows-Explorer auf eine Datei doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="1f8ac-103">Associating file extensions to a specific code editor allows you to open a file with the appropriate [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] code editor when you double-click a file in Windows Explorer.</span></span> <span data-ttu-id="1f8ac-104">Für in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]häufig verwendete Erweiterungen, z. B. SQL und MDX, werden die Zuordnungen bei der Installation erstellt.</span><span class="sxs-lookup"><span data-stu-id="1f8ac-104">The extensions commonly used by [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], such as .sql and .mdx, are associated during installation.</span></span> <span data-ttu-id="1f8ac-105">Neue Dateierweiterungen müssen im Dateisystem auch [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="1f8ac-105">New file extensions must also be associated to [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] in the file system.</span></span> <span data-ttu-id="1f8ac-106">Sie können mit dieser Funktion auch Dateien öffnen, die mit anderen Editoren erstellt wurden. Das Gleiche gilt für Dateien, die Sie umbenannt haben, z. B. in BAK-Dateien umbenannte Sicherungen von SQL-Dateien.</span><span class="sxs-lookup"><span data-stu-id="1f8ac-106">You can use this feature to open files created with other editors, or to open files you have renamed, such as backups of .sql files that were renamed .bak.</span></span>  
  
 <span data-ttu-id="1f8ac-107">Für diesen Vorgang sind zwei Schritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1f8ac-107">There are two steps in the process.</span></span> <span data-ttu-id="1f8ac-108">Ordnen Sie die Erweiterung zunächst [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]und anschließend einem bestimmten Code-Editor zu.</span><span class="sxs-lookup"><span data-stu-id="1f8ac-108">First associate the extension with [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then associate the extension with a specific code editor.</span></span>  
  
### <a name="to-associate-a-new-file-extension-with-sql-server-management-studio"></a><span data-ttu-id="1f8ac-109">So ordnen Sie SQL Server Management Studio eine neue Dateierweiterung zu</span><span class="sxs-lookup"><span data-stu-id="1f8ac-109">To associate a new file extension with SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="1f8ac-110">Zeigen Sie im Menü **Start** auf **Alle Programme**, zeigen Sie auf **Zubehör**, und klicken Sie dann auf **Windows-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="1f8ac-110">On the **Start** menu, point to **All Programs**, point to **Accessories**, and then click **Windows Explorer**.</span></span>  
  
2.  <span data-ttu-id="1f8ac-111">Klicken Sie im Menü **Extras** von Windows-Explorer auf **Ordneroptionen**.</span><span class="sxs-lookup"><span data-stu-id="1f8ac-111">In Windows Explorer, on the **Tools** menu, click **Folder Options**.</span></span>  
  
3.  <span data-ttu-id="1f8ac-112">Klicken Sie auf der Registerkarte **Dateitypen** des Dialogfelds **Ordneroptionen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="1f8ac-112">In the **Folder Options** dialog box, on the **File Types** tab, click **New**.</span></span>  
  
4.  <span data-ttu-id="1f8ac-113">Geben Sie im Feld **Dateierweiterung** des Dialogfelds **Eine neue Erweiterung erstellen** die neue Dateierweiterung ein, für die Sie eine Verknüpfung erstellen möchten, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f8ac-113">In the **Create New Extension** dialog box, in the **File Extension** box, type the new file extension that you want to associate, and then click **OK**.</span></span> <span data-ttu-id="1f8ac-114">Lassen Sie den Punkt am Anfang der Erweiterung weg.</span><span class="sxs-lookup"><span data-stu-id="1f8ac-114">Do not start the extension with a period.</span></span>  
  
5.  <span data-ttu-id="1f8ac-115">Klicken Sie im Feld **Registrierte Dateitypen** auf die neue Erweiterung, und klicken Sie dann auf **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="1f8ac-115">In the **Registered file** types box, click on your new extension, and then click **Change**.</span></span>  
  
6.  <span data-ttu-id="1f8ac-116">Klicken Sie im Dialogfeld **Öffnen mit** auf **SSMS - SQL Server Management Studio**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f8ac-116">In the **Open With** dialog box, click **SSMS - SQL Server Management Studio**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="1f8ac-117">Klicken Sie auf **Schließen** , um das Dialogfeld **Ordneroptionen** zu schließen, und schließen Sie dann Windows-Explorer.</span><span class="sxs-lookup"><span data-stu-id="1f8ac-117">Click **Close** to close the **Folder Options** dialog box, and then close Windows Explorer.</span></span>  
  
### <a name="to-associate-a-new-file-extension-with-a-code-editor-in-sql-server-management-studio"></a><span data-ttu-id="1f8ac-118">So ordnen Sie einem Code-Editor in SQL Server Management Studio eine neue Dateierweiterung zu</span><span class="sxs-lookup"><span data-stu-id="1f8ac-118">To associate a new file extension with a code editor in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="1f8ac-119">Klicken Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]im Menü **Extras** auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="1f8ac-119">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], from the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="1f8ac-120">Klicken Sie im Dialogfeld **Optionen** auf **Text-Editor**, und klicken Sie dann auf **Dateierweiterung**.</span><span class="sxs-lookup"><span data-stu-id="1f8ac-120">In the **Options** dialog box, click **Text Editor**, and then click **File Extension**.</span></span>  
  
3.  <span data-ttu-id="1f8ac-121">Geben Sie im Feld **Erweiterung** die neue Dateierweiterung ein.</span><span class="sxs-lookup"><span data-stu-id="1f8ac-121">In the **Extension** box, type your new file extension.</span></span>  
  
4.  <span data-ttu-id="1f8ac-122">Klicken Sie im Feld **Editor** auf den Code-Editor, mit dem dieser Dateityp geöffnet werden soll, klicken Sie auf **Hinzufügen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f8ac-122">In the **Editor** box, click the code editor that you wish to use to open this file type, click **Add**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f8ac-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1f8ac-123">See Also</span></span>  
 [<span data-ttu-id="1f8ac-124">Ssms-Hilfsprogramm</span><span class="sxs-lookup"><span data-stu-id="1f8ac-124">Ssms Utility</span></span>](../../ssms/ssms-utility.md)  
  
  
