---
title: Ändern einer Ablauf Verfolgungs Vorlage (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- templates [SQL Server], traces
- trace templates [SQL Server]
- modifying traces
ms.assetid: b81df2a1-e202-43d8-92b0-0beb145f0116
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2a93baedb1875ac740e74065ae7188f9b576e083
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609392"
---
# <a name="modify-a-trace-template-sql-server-profiler"></a><span data-ttu-id="5d8ea-102">Ändern einer Ablaufverfolgungsvorlage (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="5d8ea-102">Modify a Trace Template (SQL Server Profiler)</span></span>
  <span data-ttu-id="5d8ea-103">In diesem Thema wird beschrieben, wie mit [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]eine Ablaufverfolgungsvorlage geändert wird.</span><span class="sxs-lookup"><span data-stu-id="5d8ea-103">This topic describes how to modify a trace template by using [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-modify-a-trace-template"></a><span data-ttu-id="5d8ea-104">So ändern Sie eine Ablaufverfolgungsvorlage</span><span class="sxs-lookup"><span data-stu-id="5d8ea-104">To modify a trace template</span></span>  
  
1.  <span data-ttu-id="5d8ea-105">Zeigen Sie im Menü **Datei** auf **Vorlagen**, und klicken Sie dann auf **Vorlage bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="5d8ea-105">On the **File** menu, point to **Templates**, and then click **Edit Template**.</span></span>  
  
2.  <span data-ttu-id="5d8ea-106">Im Dialogfeld **Eigenschaften der Ablaufverfolgungsvorlage** können Sie auf der Registerkarte **Allgemein** den Servertyp und den Vorlagennamen ändern oder eine Standardvorlage für den Servertyp auswählen.</span><span class="sxs-lookup"><span data-stu-id="5d8ea-106">In the **Trace Template Properties** dialog box, on the **General** tab, you can modify the server type and template name, or choose to use a default template for the server type.</span></span>  
  
3.  <span data-ttu-id="5d8ea-107">Zeigen Sie im Menü **Ereignisauswahl**können Sie mit dem Rastersteuerelement Ereignisse und Datenspalten in der Ablaufverfolgungsdatei wie folgt hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="5d8ea-107">On the **Events Selection**tab, use the grid control to add or remove events and data columns from the trace file as follows.</span></span>  
  
    -   <span data-ttu-id="5d8ea-108">Um ein Ereignis hinzuzufügen, erweitern Sie die entsprechende Ereigniskategorie in der **Ereignisse** -Spalte und wählen dann den Ereignisnamen aus.</span><span class="sxs-lookup"><span data-stu-id="5d8ea-108">To add an event, expand the appropriate event category in the **Events** column, and then select the event name.</span></span>  
  
    -   <span data-ttu-id="5d8ea-109">Wenn Sie ein Ereignis hinzufügen, werden standardmäßig alle relevanten Datenspalten eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5d8ea-109">When you add an event, all relevant data columns are included by default.</span></span> <span data-ttu-id="5d8ea-110">Um eine Datenspalte für ein Ereignis aus einer Ablaufverfolgung zu entfernen, deaktivieren Sie das Kontrollkästchen in der Datenspalte für das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="5d8ea-110">To remove a data column for an event from a trace, clear the check box in the data column for the event.</span></span>  
  
    -   <span data-ttu-id="5d8ea-111">Um Filter hinzuzufügen, klicken Sie auf den Namen der Datenspalte, und geben Sie die Filterkriterien im Dialogfeld **Filter bearbeiten** an.</span><span class="sxs-lookup"><span data-stu-id="5d8ea-111">To add filters, click the data column name and specify the filter criteria in the **Edit Filter** dialog box.</span></span> <span data-ttu-id="5d8ea-112">Sie können auch mit der rechten Maustaste auf den Namen der Datenspalte und anschließend auf **Spaltenfilter bearbeiten** klicken, um das Dialogfeld **Filter bearbeiten** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5d8ea-112">You can also right-click the data column name, and click **Edit Column Filter** to launch the **Edit Filter** dialog box.</span></span> <span data-ttu-id="5d8ea-113">Klicken Sie auf **OK** , um den Filter hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="5d8ea-113">Click **OK** to add the filter.</span></span>  
  
4.  <span data-ttu-id="5d8ea-114">Klicken Sie auf **Speichern**, oder klicken Sie auf **Speichern As**, um die Ablaufverfolgungsvorlage unter einem anderen Namen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="5d8ea-114">Click **Save**, or click **Save As**to save the trace template under another name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d8ea-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5d8ea-115">See Also</span></span>  
 <span data-ttu-id="5d8ea-116">[Angeben von Ereignissen und Datenspalten für eine Ablauf Verfolgungs Datei &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="5d8ea-116">[Specify Events and Data Columns for a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="5d8ea-117">[Ableiten einer Vorlage von einer zurzeit ausgeführten Ablaufverfolgung &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/derive-a-template-from-a-running-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="5d8ea-117">[Derive a Template from a Running Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/derive-a-template-from-a-running-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="5d8ea-118">[Ableiten einer Vorlage von einer Ablaufverfolgungsdatei oder Ablaufverfolgungstabelle &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="5d8ea-118">[Derive a Template from a Trace File or Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/derive-a-template-from-a-trace-file-or-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="5d8ea-119">[Vorlagen und Berechtigungen in SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="5d8ea-119">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="5d8ea-120">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="5d8ea-120">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
