---
title: Erstellen einer Ablauf Verfolgungs Vorlage (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- templates [SQL Server], traces
- trace templates [SQL Server]
- saving trace template
ms.assetid: 025868b0-3790-4cda-8757-5a58327bfba0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 355f97c7fecd8a9e31f10de881d1ae6df3b8f122
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694938"
---
# <a name="create-a-trace-template-sql-server-profiler"></a><span data-ttu-id="0810a-102">Erstellen einer Ablaufverfolgungsvorlage (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="0810a-102">Create a Trace Template (SQL Server Profiler)</span></span>
  <span data-ttu-id="0810a-103">In diesem Thema wird beschrieben, wie Sie mithilfe von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]eine neue Ablaufverfolgungsvorlage erstellen.</span><span class="sxs-lookup"><span data-stu-id="0810a-103">This topic describes how to create a new trace template by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-create-a-trace-template"></a><span data-ttu-id="0810a-104">So erstellen Sie eine Ablaufverfolgungsvorlage</span><span class="sxs-lookup"><span data-stu-id="0810a-104">To create a trace template</span></span>  
  
1.  <span data-ttu-id="0810a-105">Zeigen Sie im Menü **Datei** auf **Vorlagen**, und klicken Sie dann auf **Neue Vorlage**.</span><span class="sxs-lookup"><span data-stu-id="0810a-105">On the **File** menu, point to **Templates**, and then click **New Template**.</span></span>  
  
2.  <span data-ttu-id="0810a-106">Wählen Sie in der Liste **Servertyp auswählen** des Dialogfelds **Eigenschaften der Ablaufverfolgungsvorlage**einen Servertyp aus.</span><span class="sxs-lookup"><span data-stu-id="0810a-106">In the **Trace Template Properties** dialog box, select a server type from the **Select server type**list.</span></span>  
  
3.  <span data-ttu-id="0810a-107">Geben Sie im Feld **Name der neuen Vorlage** den Vorlagennamen ein.</span><span class="sxs-lookup"><span data-stu-id="0810a-107">In the **New template name** box, enter a template name.</span></span>  
  
4.  <span data-ttu-id="0810a-108">Wahlweise können Sie auch auf **Neue Vorlage auf vorhandener basieren**klicken und anschließend eine Vorlage aus der Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="0810a-108">Optionally, click **Base new template on existing one**, and then select a template from the list.</span></span>  
  
     <span data-ttu-id="0810a-109">Alle Ereignisse, Datenspalten und Filter werden anfänglich so festgelegt, wie in der ausgewählten Vorlage angegeben.</span><span class="sxs-lookup"><span data-stu-id="0810a-109">All events, data columns, and filters are initially set as specified in the selected template.</span></span>  
  
5.  <span data-ttu-id="0810a-110">Wahlweise können Sie auch auf **Als Standardvorlage für den ausgewählten Servertyp verwenden**klicken.</span><span class="sxs-lookup"><span data-stu-id="0810a-110">Optionally, click **Use as a default template for selected server type**.</span></span>  
  
6.  <span data-ttu-id="0810a-111">Auf der Registerkarte **Ereignisauswahl** können Sie Ereignisse, Datenspalten und Filter hinzufügen, entfernen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="0810a-111">On the **Events Selection** tab, add, remove, or modify events, data columns, or filters.</span></span>  
  
7.  <span data-ttu-id="0810a-112">Zeigen Sie im Menü **Ereignisauswahl**können Sie mit dem Rastersteuerelement Ereignisse und Datenspalten in der Ablaufverfolgungsdatei wie folgt hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="0810a-112">On the **Events Selection**tab, use the grid control to add or remove events and data columns from the trace file as follows:</span></span>  
  
    -   <span data-ttu-id="0810a-113">Um ein Ereignis hinzuzufügen, erweitern Sie die entsprechende Ereigniskategorie in der **Ereignisse** -Spalte und wählen dann den Ereignisnamen aus.</span><span class="sxs-lookup"><span data-stu-id="0810a-113">To add an event, expand the appropriate event category in the **Events** column, and then select the event name.</span></span>  
  
    -   <span data-ttu-id="0810a-114">Wenn Sie ein Ereignis hinzufügen, werden standardmäßig alle relevanten Datenspalten eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="0810a-114">When you add an event, all relevant data columns are included by default.</span></span> <span data-ttu-id="0810a-115">Um eine Datenspalte für ein Ereignis aus einer Ablaufverfolgung zu entfernen, deaktivieren Sie das Kontrollkästchen in der Datenspalte für das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="0810a-115">To remove a data column for an event from a trace, clear the check box in the data column for the event.</span></span>  
  
    -   <span data-ttu-id="0810a-116">Um Filter hinzuzufügen, klicken Sie auf den Namen der Datenspalte, und geben Sie die Filterkriterien im Dialogfeld **Filter bearbeiten** an.</span><span class="sxs-lookup"><span data-stu-id="0810a-116">To add filters, click the data column name and specify the filter criteria in the **Edit Filter** dialog box.</span></span> <span data-ttu-id="0810a-117">Sie können auch mit der rechten Maustaste auf den Namen der Datenspalte und anschließend auf **Spaltenfilter bearbeiten** klicken, um das Dialogfeld **Filter bearbeiten** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0810a-117">You can also right-click the data column name, and click **Edit Column Filter** to launch the **Edit Filter** dialog box.</span></span> <span data-ttu-id="0810a-118">Klicken Sie auf **OK** , um den Filter hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0810a-118">Click **OK** to add the filter.</span></span>  
  
8.  <span data-ttu-id="0810a-119">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="0810a-119">Click **Save.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0810a-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0810a-120">See Also</span></span>  
 <span data-ttu-id="0810a-121">[Angeben von Ereignissen und Datenspalten für eine Ablaufverfolgungsdatei &#40;SQL Server Profiler&#41;](specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="0810a-121">[Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="0810a-122">[Ableiten einer Vorlage von einer zurzeit ausgeführten Ablaufverfolgung &#40;SQL Server Profiler&#41;](derive-a-template-from-a-running-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="0810a-122">[Derive a Template from a Running Trace &#40;SQL Server Profiler&#41;](derive-a-template-from-a-running-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="0810a-123">[Ableiten einer Vorlage von einer Ablaufverfolgungsdatei oder Ablaufverfolgungstabelle &#40;SQL Server Profiler&#41;](derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="0810a-123">[Derive a Template from a Trace File or Trace Table &#40;SQL Server Profiler&#41;](derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="0810a-124">[Vorlagen und Berechtigungen in SQL Server Profiler](sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="0810a-124">[SQL Server Profiler Templates and Permissions](sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="0810a-125">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="0810a-125">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
