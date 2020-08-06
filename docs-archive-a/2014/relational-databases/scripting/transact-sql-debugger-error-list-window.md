---
title: Fehlerliste (Fenster)
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- error list window
- SQL Server Management Studio [SQL Server], error list window
ms.assetid: fae6327d-e268-44ae-a474-4a8f8f843129
author: rothja
ms.author: jroth
ms.openlocfilehash: 00455c339344b7b38a48500c49d139aa52df6116
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622005"
---
# <a name="error-list-window-management-studio"></a><span data-ttu-id="1aaef-102">Fenster 'Fehlerliste' (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="1aaef-102">Error List Window (Management Studio)</span></span>
  <span data-ttu-id="1aaef-103">In der [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]Fehlerliste**in** werden die vom IntelliSense-Code im [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Abfrage-Editor generierten Syntax- und Semantikfehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1aaef-103">The [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **Error List** displays the syntax and semantic errors that are generated from the IntelliSense code in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span>  
  
## <a name="features-of-the-error-list"></a><span data-ttu-id="1aaef-104">Funktionen der Fehlerliste</span><span class="sxs-lookup"><span data-stu-id="1aaef-104">Features of the Error List</span></span>  
 <span data-ttu-id="1aaef-105">Die **Fehlerliste** bietet die folgende Funktionalität:</span><span class="sxs-lookup"><span data-stu-id="1aaef-105">The **Error List** provides the following functionality:</span></span>  
  
-   <span data-ttu-id="1aaef-106">Beim Bearbeiten von Skripts werden in der **Fehlerliste** die von IntelliSense im [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor generierten Fehler und Warnungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1aaef-106">As you edit scripts, the **Error List** displays the errors and warnings produced by IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span>  
  
-   <span data-ttu-id="1aaef-107">Sie können auf eine beliebige Fehlermeldung doppelklicken, um den Fokus auf die Registerkarte für die Skriptdatei zu verschieben, die den Fehler generiert hat, und zur entsprechenden Stelle zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="1aaef-107">You can double-click any error message entry to focus on the tab for the script file that generated the error, and move to the error location.</span></span>  
  
-   <span data-ttu-id="1aaef-108">Sie können die anzuzeigenden Einträge und die Informationsspalten, die für jeden Eintrag angezeigt werden sollen, filtern.</span><span class="sxs-lookup"><span data-stu-id="1aaef-108">You can filter which entries you want to display, and which columns of information you want appear for each entry.</span></span>  
  
-   <span data-ttu-id="1aaef-109">Nachdem Sie einen Fehler behoben haben, wird der Fehlereintrag aus der **Fehlerliste** entfernt.</span><span class="sxs-lookup"><span data-stu-id="1aaef-109">After you fix an error, the error entry is removed from the **Error List**.</span></span>  
  
-   <span data-ttu-id="1aaef-110">Wenn Sie die Registerkarte für eine [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skriptdatei schließen, werden die Fehler in dieser Datei aus der **Fehlerliste**entfernt.</span><span class="sxs-lookup"><span data-stu-id="1aaef-110">When you close the tab for a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file, the errors for that file are removed from the **Error List**.</span></span>  
  
## <a name="working-with-the-error-list"></a><span data-ttu-id="1aaef-111">Arbeiten mit der Fehlerliste</span><span class="sxs-lookup"><span data-stu-id="1aaef-111">Working with the Error List</span></span>  
 <span data-ttu-id="1aaef-112">Führen Sie zum Anzeigen der **Fehlerliste** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="1aaef-112">To display the **Error List**, do one of the following:</span></span>  
  
-   <span data-ttu-id="1aaef-113">Klicken Sie im Menü **Ansicht** auf **Fehlerliste**.</span><span class="sxs-lookup"><span data-stu-id="1aaef-113">On the **View** menu, click **Error List**.</span></span>  
  
-   <span data-ttu-id="1aaef-114">Drücken Sie die Tastenkombination STRG+\\, STRG+E.</span><span class="sxs-lookup"><span data-stu-id="1aaef-114">Enter the keyboard shortcut CTRL+\\, CTRL+E.</span></span>  
  
 <span data-ttu-id="1aaef-115">Nachdem Sie die **Fehlerliste** geöffnet haben, können Sie die Sicht anpassen, indem Sie die folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="1aaef-115">After you open the **Error List**, you can customize your view by performing the following actions:</span></span>  
  
-   <span data-ttu-id="1aaef-116">Zum Sortieren der Liste klicken Sie auf einen beliebigen Spaltenheader.</span><span class="sxs-lookup"><span data-stu-id="1aaef-116">To sort the list, click any column header.</span></span> <span data-ttu-id="1aaef-117">Um erneut nach einer zusätzlichen Spalte zu sortieren, halten Sie die UMSCHALTTASTE gedrückt, und klicken Sie dann auf einen anderen Spaltenheader.</span><span class="sxs-lookup"><span data-stu-id="1aaef-117">To sort again by an additional column, press and hold the SHIFT key, and then click another column header.</span></span>  
  
-   <span data-ttu-id="1aaef-118">Um auszuwählen, welche Spalten angezeigt und welche ausgeblendet werden sollen, wählen Sie im Kontextmenü **Spalten anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="1aaef-118">To select which columns are displayed and which are hidden, select **Show Columns** from the shortcut menu.</span></span>  
  
-   <span data-ttu-id="1aaef-119">Zum Ändern der Reihenfolge, in der Spalten angezeigt werden, ziehen Sie einen beliebigen Spaltenheader nach links oder rechts.</span><span class="sxs-lookup"><span data-stu-id="1aaef-119">To change the order in which columns are displayed, drag any column header to the left or right.</span></span>  
  
 <span data-ttu-id="1aaef-120">Die **Fehlerliste** enthält keine Links zu weiteren Informationen zu bestimmten Fehlern.</span><span class="sxs-lookup"><span data-stu-id="1aaef-120">The **Error List** does not link to additional information about specific errors.</span></span>  
  
## <a name="transact-sql-errors-in-management-studio"></a><span data-ttu-id="1aaef-121">Transact-SQL-Fehler in Management Studio</span><span class="sxs-lookup"><span data-stu-id="1aaef-121">Transact-SQL Errors in Management Studio</span></span>  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="1aaef-122">werden Fehler bei [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skripts an den folgenden Speicherorten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1aaef-122">displays errors for [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts in the following locations:</span></span>  
  
-   <span data-ttu-id="1aaef-123">Die **Fehlerliste** enthält alle von IntelliSense im [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Editor gefundenen Syntax- und Semantikfehler.</span><span class="sxs-lookup"><span data-stu-id="1aaef-123">The **Error List** contains all syntax and semantic errors found by IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Editor.</span></span> <span data-ttu-id="1aaef-124">Die Fehlerliste wird dynamisch aktualisiert, während Sie [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skripts bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="1aaef-124">This list of errors is dynamically updated as you edit [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts.</span></span> <span data-ttu-id="1aaef-125">In der Liste sind alle Fehler aufgeführt, die in einem [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skript gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="1aaef-125">The list includes all errors that the editor has found in each [!INCLUDE[tsql](../../includes/tsql-md.md)] script.</span></span> <span data-ttu-id="1aaef-126">Die Analyse einer Datei wird nicht beendet, wenn Fehler in einem Skript gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="1aaef-126">The editor does not stop parsing a file after encountering errors in a script.</span></span> <span data-ttu-id="1aaef-127">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]unterstützt IntelliSense im [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Editor nicht alle [!INCLUDE[tsql](../../includes/tsql-md.md)] -Syntaxelemente.</span><span class="sxs-lookup"><span data-stu-id="1aaef-127">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], IntelliSense in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Editor does not support all [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax elements.</span></span> <span data-ttu-id="1aaef-128">Die **Fehlerliste** enthält nur Fehler in der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Syntax, die von IntelliSense unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="1aaef-128">The **Error List** contains only errors from the [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax that is supported by IntelliSense.</span></span>  
  
-   <span data-ttu-id="1aaef-129">Auf der Registerkarte **Meldungen** am unteren Rand des [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editorfensters werden alle Fehler und Warnungen angezeigt, die bei der Ausführung eines [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] -Skripts von [!INCLUDE[tsql](../../includes/tsql-md.md)] zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="1aaef-129">The **Messages** tab at the bottom of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window displays all errors and messages that are returned by the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] when a [!INCLUDE[tsql](../../includes/tsql-md.md)] script is executed.</span></span> <span data-ttu-id="1aaef-130">Diese Liste ändert sich nicht, bis Sie das Skript erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="1aaef-130">This list does not change until you execute the script again.</span></span> <span data-ttu-id="1aaef-131">[!INCLUDE[ssDE](../../includes/ssde-md.md)] beendet die Analyse eines Batchs, wenn ein oder zwei Kompilierungsfehler gefunden wurden. Daher werden auf der Registerkarte **Meldungen** möglicherweise nicht alle in einem Skript gefundenen Fehler aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="1aaef-131">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] stops parsing a batch after it finds one or two compile errors; therefore, the **Messages** tab might not list all errors in a script.</span></span>  
  
 <span data-ttu-id="1aaef-132">Manchmal werden Fehler an beiden Orten aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="1aaef-132">Sometimes errors are listed in both locations.</span></span> <span data-ttu-id="1aaef-133">Zum Beispiel könnte in einer Skriptdatei ein Syntaxfehler vorliegen, der in der **Fehlerliste** aufgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1aaef-133">For example, a script file might have a syntax error that is listed in the **Error List**.</span></span> <span data-ttu-id="1aaef-134">Wenn Sie das Skript ausführen, bevor Sie den Fehler behoben haben, findet der [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Parser möglicherweise denselben Fehler und gibt auf der Registerkarte **Meldungen** die Fehlermeldung erneut zurück.</span><span class="sxs-lookup"><span data-stu-id="1aaef-134">If you execute the script before you correct the error, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] parser can detect the same condition and return another copy of the error message in the **Messages** tab.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1aaef-135">In der **Fehlerliste** werden nur Fehler aus dem [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor angezeigt. Fehler aus dem MDX-, DMX- oder XML/A-Editor werden in der Liste nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1aaef-135">The **Error List** only displays errors from the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor; it does not display errors from the MDX, DMX, or XML/A Editors.</span></span> <span data-ttu-id="1aaef-136">Alle MDX-, DMX- und XML/A-Fehler werden in den entsprechenden Editoren auf der Registerkarte **Meldungen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1aaef-136">All MDX, DMX, and XML/A errors are displayed in the **Messages** tab in those editors.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="1aaef-137">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="1aaef-137">UI element list</span></span>  
 <span data-ttu-id="1aaef-138">Wenn die **Fehlerliste** geöffnet ist, werden die Informationen in den folgenden Spalten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1aaef-138">When the **Error List** is open, the information is displayed in the following columns:</span></span>  
  
 <span data-ttu-id="1aaef-139">**Standardreihenfolge**</span><span class="sxs-lookup"><span data-stu-id="1aaef-139">**Default Order**</span></span>  
 <span data-ttu-id="1aaef-140">Zeigt eine ganze Zahl an, die die Reihenfolge angibt, in der ein Eintrag generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="1aaef-140">Displays an integer that indicates the order in which an entry was generated.</span></span>  
  
 <span data-ttu-id="1aaef-141">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1aaef-141">**Description**</span></span>  
 <span data-ttu-id="1aaef-142">Zeigt den Text des Fehlereintrags an.</span><span class="sxs-lookup"><span data-stu-id="1aaef-142">Displays the text of the error entry.</span></span> <span data-ttu-id="1aaef-143">Lange Beschreibungen werden in zusätzliche Zeilen umbrochen.</span><span class="sxs-lookup"><span data-stu-id="1aaef-143">Lengthy descriptions wrap onto additional lines.</span></span>  
  
 <span data-ttu-id="1aaef-144">**File**</span><span class="sxs-lookup"><span data-stu-id="1aaef-144">**File**</span></span>  
 <span data-ttu-id="1aaef-145">Zeigt den Namen der Skriptdatei an, die den Fehler generiert hat.</span><span class="sxs-lookup"><span data-stu-id="1aaef-145">Displays the name of the script file that generated the error.</span></span>  
  
 <span data-ttu-id="1aaef-146">**Linie**</span><span class="sxs-lookup"><span data-stu-id="1aaef-146">**Line**</span></span>  
 <span data-ttu-id="1aaef-147">Zeigt eine ganze Zahl an, die angibt, in welcher Codezeile der Fehler enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="1aaef-147">Displays an integer that indicates which line of the code includes the error.</span></span>  
  
 <span data-ttu-id="1aaef-148">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="1aaef-148">**Column**</span></span>  
 <span data-ttu-id="1aaef-149">Zeigt eine ganze Zahl an, die die Position des Fehlers in der Codezeile angibt.</span><span class="sxs-lookup"><span data-stu-id="1aaef-149">Displays an integer that indicates the position of the error in the line of code.</span></span>  
  
 <span data-ttu-id="1aaef-150">**Projekt**</span><span class="sxs-lookup"><span data-stu-id="1aaef-150">**Project**</span></span>  
 <span data-ttu-id="1aaef-151">Zeigt den Namen des Projekts an, in dem die angegebene Skriptdatei enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="1aaef-151">Displays the name of the project that includes the script file.</span></span>  
