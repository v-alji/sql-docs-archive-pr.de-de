---
title: Befehlsfenster
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Command Window [Transact-SQL]
ms.assetid: e567ebf9-0793-451b-92c7-26193a02d9da
author: rothja
ms.author: jroth
ms.openlocfilehash: c766ed5408de96b6a2305ce377f9031947618a7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621452"
---
# <a name="command-window"></a><span data-ttu-id="643ce-102">Befehlsfenster</span><span class="sxs-lookup"><span data-stu-id="643ce-102">Command Window</span></span>
  <span data-ttu-id="643ce-103">Im **Befehlsfenster** können Sie für den Code im gerade gedebuggten [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] -Abfrage-Editor-Fenster Befehle ausführen, wie z.B. Debug- und Bearbeitungsbefehle.</span><span class="sxs-lookup"><span data-stu-id="643ce-103">Use the **CommandWindow** to run commands, such as debug and edit commands, against the code in the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] Query Editor window that is currently being debugged.</span></span> <span data-ttu-id="643ce-104">Um das **Befehlsfenster**zu verwenden, müssen Sie sich im Debugmodus befinden.</span><span class="sxs-lookup"><span data-stu-id="643ce-104">You must be in debug mode to use the **Command Window**.</span></span> <span data-ttu-id="643ce-105">Der [!INCLUDE[tsql](../../includes/tsql-md.md)]-Debugger unterstützt zahlreiche Befehle, die auch im **Befehlsfenster** von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="643ce-105">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger supports many of the commands that are also supported in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] **Command** window.</span></span> <span data-ttu-id="643ce-106">Weitere Informationen finden Sie unter [Visual Studio-Befehlsfenster](https://go.microsoft.com/fwlink/?LinkId=112007).</span><span class="sxs-lookup"><span data-stu-id="643ce-106">For more information, see [Visual Studio Command Window](https://go.microsoft.com/fwlink/?LinkId=112007).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="643ce-107">Aufgabenliste</span><span class="sxs-lookup"><span data-stu-id="643ce-107">Task List</span></span>  
 <span data-ttu-id="643ce-108">**So greifen Sie auf das Befehlsfenster zu**</span><span class="sxs-lookup"><span data-stu-id="643ce-108">**To access the Command Window**</span></span>  
  
-   <span data-ttu-id="643ce-109">Klicken Sie im Menü **Debuggen** auf **Debuggen starten**.</span><span class="sxs-lookup"><span data-stu-id="643ce-109">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
 <span data-ttu-id="643ce-110">**So geben Sie den Wert einer Variablen aus**</span><span class="sxs-lookup"><span data-stu-id="643ce-110">**To print the value of a variable**</span></span>  
  
-   <span data-ttu-id="643ce-111">Geben Sie im **CommandWindow** \*\*Debug. Print \<VariableName> \*\*ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="643ce-111">In the **CommandWindow**, type **Debug.Print \<VariableName>**, and then press ENTER.</span></span>  
  
 <span data-ttu-id="643ce-112">**So listen Sie Informationen zum aktuellen Thread auf**</span><span class="sxs-lookup"><span data-stu-id="643ce-112">**To list information about the current thread**</span></span>  
  
-   <span data-ttu-id="643ce-113">Geben Sie in das **Befehlsfenster**ein `Debug.ListThread` , und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="643ce-113">In the **CommandWindow**, type `Debug.ListThread`, and then press ENTER.</span></span>  
  
 <span data-ttu-id="643ce-114">**So fügen Sie dem Fenster Schnellüberwachung eine Variable hinzu**</span><span class="sxs-lookup"><span data-stu-id="643ce-114">**To add a variable to the QuickWatch window**</span></span>  
  
-   <span data-ttu-id="643ce-115">Geben Sie im **CommandWindow** \*\*Debug. quickwatch \<VariableName> \*\*ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="643ce-115">In the **CommandWindow**, type **Debug.QuickWatch \<VariableName>**, and then press ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="643ce-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="643ce-116">See Also</span></span>  
 [<span data-ttu-id="643ce-117">Transact-SQL-Debugger</span><span class="sxs-lookup"><span data-stu-id="643ce-117">Transact-SQL Debugger</span></span>](transact-sql-debugger.md)  
