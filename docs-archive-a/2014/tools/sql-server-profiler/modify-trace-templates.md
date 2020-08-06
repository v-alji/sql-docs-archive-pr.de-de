---
title: Ändern von Ablauf Verfolgungs Vorlagen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- templates [SQL Server], SQL Server Profiler
- Profiler [SQL Server Profiler], templates
- trace templates [SQL Server]
- modifying trace templates
- SQL Server Profiler, templates
ms.assetid: 75b62a54-8d16-4599-bd2d-c42cfcc209f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a26d0a70f65b6ff60dcf42ffb98e67dc0d2b52d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608982"
---
# <a name="modify-trace-templates"></a><span data-ttu-id="4bfe1-102">Ändern von Ablaufverfolgungsvorlagen</span><span class="sxs-lookup"><span data-stu-id="4bfe1-102">Modify Trace Templates</span></span>
  <span data-ttu-id="4bfe1-103">Sie können Vorlagen ändern, wenn diese in einer Datei auf dem lokalen Computer gespeichert sind und auf dem Computer [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4bfe1-103">You can modify templates that are saved in a file on the local computer on which [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] is running.</span></span> <span data-ttu-id="4bfe1-104">Sie können auch Vorlagen ändern, die aus diesen Dateien abgeleitet wurden.</span><span class="sxs-lookup"><span data-stu-id="4bfe1-104">You can also modify templates derived from those files.</span></span> <span data-ttu-id="4bfe1-105">Beim Ändern vorhandener Vorlagen bearbeiten Sie die Eigenschaften der Vorlage, wie Ereignisklassen und Datenspalten, in derselben Reihenfolge, in der die Eigenschaften ursprünglich festgelegt wurden. Dies geschieht über die Registerkarte **Ereignisauswahl** im Dialogfeld **Ablaufverfolgungseigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="4bfe1-105">When you modify existing templates, you edit template properties such as event classes and data columns, in the same order that the properties were set originally, on the **Events Selection** tab of the **Trace Properties** dialog box.</span></span> <span data-ttu-id="4bfe1-106">Ereignisklassen und Datenspalten können hinzugefügt oder entfernt werden, und Filter können geändert werden.</span><span class="sxs-lookup"><span data-stu-id="4bfe1-106">Event classes and data columns can be added or removed, and filters can be changed.</span></span> <span data-ttu-id="4bfe1-107">Nach dem Ändern der Vorlage wird eine benutzerspezifische Vorlage erstellt, und die ursprüngliche Systemvorlage bleibt unverändert.</span><span class="sxs-lookup"><span data-stu-id="4bfe1-107">After the template is modified, a user-specific template is created and the original system template is left intact.</span></span> <span data-ttu-id="4bfe1-108">Weitere Informationen finden Sie unter [Speichern von Ablaufverfolgungen und Ablaufverfolgungsvorlagen](save-traces-and-trace-templates.md).</span><span class="sxs-lookup"><span data-stu-id="4bfe1-108">For more information, see [Save Traces and Trace Templates](save-traces-and-trace-templates.md).</span></span>  
  
 <span data-ttu-id="4bfe1-109">Möglicherweise müssen Sie eine Vorlage von einer vorhandenen Ablaufverfolgungsdatei ableiten, z. B. falls Sie vergessen haben, welche Vorlage ursprünglich zum Erstellen der Ablaufverfolgung verwendet wurde (oder wenn diese Datei nicht gespeichert wurde) oder falls Sie eine Ablaufverfolgung später erneut ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="4bfe1-109">You may need to derive a template from an existing trace file if you cannot remember (or have not saved) the original template that was used to create the trace, or if you want to run the same trace at a later date.</span></span> <span data-ttu-id="4bfe1-110">Bei vorhandenen Ablaufverfolgungen können Sie die Eigenschaften zwar anzeigen, aber nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="4bfe1-110">When working with existing traces, you can view the properties, but you cannot modify the properties.</span></span> <span data-ttu-id="4bfe1-111">Um die Eigenschaften zu ändern, müssen Sie die Ablaufverfolgung beenden oder anhalten.</span><span class="sxs-lookup"><span data-stu-id="4bfe1-111">To modify the properties, stop or pause the trace.</span></span> <span data-ttu-id="4bfe1-112">Weitere Informationen finden Sie unter [Ableiten einer Vorlage von einer Ablaufverfolgungsdatei oder Ablaufverfolgungstabelle &#40;SQL Server Profiler&#41;](sql-server-profiler.md) und [Ableiten einer Vorlage von einer zurzeit ausgeführten Ablaufverfolgung &#40;SQL Server Profiler&#41;](derive-a-template-from-a-running-trace-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="4bfe1-112">For more information, see [Derive a Template from a Trace File or Trace Table &#40;SQL Server Profiler&#41;](sql-server-profiler.md) and [Derive a Template from a Running Trace &#40;SQL Server Profiler&#41;](derive-a-template-from-a-running-trace-sql-server-profiler.md).</span></span>  
  
 <span data-ttu-id="4bfe1-113">**So erstellen Sie eine Ablaufverfolgungsvorlage**</span><span class="sxs-lookup"><span data-stu-id="4bfe1-113">**To create a trace template**</span></span>  
  
 [<span data-ttu-id="4bfe1-114">Erstellen einer Ablaufverfolgungsvorlage &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4bfe1-114">Create a Trace Template &#40;SQL Server Profiler&#41;</span></span>](create-a-trace-template-sql-server-profiler.md)  
  
 <span data-ttu-id="4bfe1-115">**So führen Sie eine Ablaufverfolgung mithilfe einer Ablaufverfolgungsvorlage aus**</span><span class="sxs-lookup"><span data-stu-id="4bfe1-115">**To run a trace from a trace template**</span></span>  
  
 [<span data-ttu-id="4bfe1-116">Erstellen einer Ablaufverfolgung &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="4bfe1-116">Create a Trace &#40;SQL Server Profiler&#41;</span></span>](create-a-trace-sql-server-profiler.md)  
  
 <span data-ttu-id="4bfe1-117">**So ändern Sie eine Ablaufverfolgungsvorlage**</span><span class="sxs-lookup"><span data-stu-id="4bfe1-117">**To modify a trace template**</span></span>  
  
 [<span data-ttu-id="4bfe1-118">Verwenden von SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="4bfe1-118">Using SQL Server Profiler</span></span>](../../database-engine/modify-a-trace-template-sql-server-profiler.md)  
  
 [<span data-ttu-id="4bfe1-119">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4bfe1-119">Using Transact-SQL</span></span>](../../relational-databases/sql-trace/modify-an-existing-trace-transact-sql.md)  
  
 <span data-ttu-id="4bfe1-120">**So fügen Sie zu einer Ablaufverfolgungsvorlage oder -datei Ereignisse hinzu bzw. entfernen sie**</span><span class="sxs-lookup"><span data-stu-id="4bfe1-120">**To add or remove events from a trace template or trace file**</span></span>  
  
 [<span data-ttu-id="4bfe1-121">Verwenden von SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="4bfe1-121">Using SQL Server Profiler</span></span>](specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md)  
  
 [<span data-ttu-id="4bfe1-122">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4bfe1-122">Using Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="4bfe1-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4bfe1-123">See Also</span></span>  
 [<span data-ttu-id="4bfe1-124">Starten einer Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="4bfe1-124">Start a Trace</span></span>](start-a-trace.md)  
  
  
