---
title: Bearbeiten einer Breakpointposition
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoint location
ms.assetid: 5c28e411-0377-4210-a7ce-2a5c13dcdf74
author: rothja
ms.author: jroth
ms.openlocfilehash: 919e62d53d5c9e8898bf1d49c4b5e5aa4c0ed107
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607616"
---
# <a name="edit-a-breakpoint-location"></a><span data-ttu-id="a9804-102">Bearbeiten einer Breakpointposition</span><span class="sxs-lookup"><span data-stu-id="a9804-102">Edit a Breakpoint Location</span></span>
  <span data-ttu-id="a9804-103">Die Breakpointposition gibt die Zeile und das Zeichen an, wo sich der Breakpoint in einer [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skriptdatei befindet.</span><span class="sxs-lookup"><span data-stu-id="a9804-103">The breakpoint location specifies the line and character where the breakpoint resides in a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file.</span></span> <span data-ttu-id="a9804-104">Sie können die Position des Breakpoints bearbeiten, um diesen an eine andere Position im Skript oder in ein anderes Skript zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="a9804-104">You can edit the breakpoint location to move the breakpoint to another location in the script, or to a different script.</span></span>  
  
## <a name="editing-a-location"></a><span data-ttu-id="a9804-105">Bearbeiten einer Position</span><span class="sxs-lookup"><span data-stu-id="a9804-105">Editing a Location</span></span>  
 <span data-ttu-id="a9804-106">Wenn Sie die Position eines Breakpoints bearbeiten, wird dieser mitsamt aller vorhandenen Eigenschaften, z. B. der Trefferanzahl oder einer Bedingung, an die neue Position verschoben.</span><span class="sxs-lookup"><span data-stu-id="a9804-106">When you edit a breakpoint location, the breakpoint moves to the new location, carrying with it all of the existing properties, such as a hit count or condition.</span></span>  
  
#### <a name="to-edit-a-breakpoint-location"></a><span data-ttu-id="a9804-107">So bearbeiten Sie eine Breakpointposition</span><span class="sxs-lookup"><span data-stu-id="a9804-107">To Edit a Breakpoint Location</span></span>  
  
1.  <span data-ttu-id="a9804-108">Klicken Sie im Editor-Fenster mit der rechten Maustaste auf das Breakpointsymbol, und klicken Sie dann im Kontextmenü auf **Speicherort** .</span><span class="sxs-lookup"><span data-stu-id="a9804-108">In the editor window, right-click the breakpoint glyph, and then click **Location** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="a9804-109">Oder</span><span class="sxs-lookup"><span data-stu-id="a9804-109">-or-</span></span>  
  
     <span data-ttu-id="a9804-110">Klicken Sie im **Breakpointfenster** mit der rechten Maustaste auf das Breakpointsymbol, und klicken Sie dann im Kontextmenü auf **Speicherort**.</span><span class="sxs-lookup"><span data-stu-id="a9804-110">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Location** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="a9804-111">Bearbeiten Sie im Dialogfeld **Dateihaltepunkt** die Option **Datei** , um eine neue Datei anzugeben, **Zeile** , um eine neue Zeile anzugeben, oder **Zeichen** , um eine neue Position auf derselben Zeile anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a9804-111">In the **File Breakpoint** dialog box, edit **File** to specify a new file, **Line** to specify a new line, or **Character** to specify a new location within the line.</span></span> <span data-ttu-id="a9804-112">Wenn die angegebene neue Datei bereits in einem Abfrage-Editor-Fenster geöffnet ist, wird der Breakpoint in dieses Editorfenster verschoben.</span><span class="sxs-lookup"><span data-stu-id="a9804-112">If the new file you specify is already open in a query editor window, the breakpoint is moved to that editor window.</span></span> <span data-ttu-id="a9804-113">Wenn die Datei nicht geöffnet wird, wird ein neues Editorfenster geöffnet, die Datei darin geladen und der Breakpoint an die neue Position verschoben.</span><span class="sxs-lookup"><span data-stu-id="a9804-113">If the file is not opened, a new editor window is opened, the file is loaded in, and the breakpoint moved to the new location.</span></span>  
  
     <span data-ttu-id="a9804-114">Beim Debuggen von **hat die Option** Unterschiede zwischen Quellcode und Originalversion zulassen [!INCLUDE[tsql](../../includes/tsql-md.md)]keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="a9804-114">The **Allow the source code to be different from the original version** option has no effect when debugging [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9804-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a9804-115">See Also</span></span>  
 <span data-ttu-id="a9804-116">[Angeben einer Treffer Anzahl](specify-a-hit-count.md) </span><span class="sxs-lookup"><span data-stu-id="a9804-116">[Specify a Hit Count](specify-a-hit-count.md) </span></span>  
 <span data-ttu-id="a9804-117">[Haltepunkt Aktion angeben](specify-a-breakpoint-action.md) </span><span class="sxs-lookup"><span data-stu-id="a9804-117">[Specify a Breakpoint Action](specify-a-breakpoint-action.md) </span></span>  
 <span data-ttu-id="a9804-118">[Festlegen einer Haltepunkt Bedingung](specify-a-breakpoint-condition.md) </span><span class="sxs-lookup"><span data-stu-id="a9804-118">[Specify a Breakpoint Condition](specify-a-breakpoint-condition.md) </span></span>  
 [<span data-ttu-id="a9804-119">Angeben eines Breakpointfilters</span><span class="sxs-lookup"><span data-stu-id="a9804-119">Specify a Breakpoint Filter</span></span>](specify-a-breakpoint-filter.md)  
