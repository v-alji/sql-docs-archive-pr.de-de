---
title: Filtern von Ereignissen anhand der Ereignisstartzeit (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- event start times [SQL Server]
- filters [SQL Server], traces
- traces [SQL Server], filters
- traces [SQL Server], events
ms.assetid: e965579e-d006-41a3-89ec-cfd5398c67d2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7f652952ec6706580b876e3e9a20f96e62598f81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723246"
---
# <a name="filter-events-based-on-the-event-start-time-sql-server-profiler"></a><span data-ttu-id="36fee-102">Filtern von Ereignissen nach Ereignisstartzeit (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="36fee-102">Filter Events Based on the Event Start Time (SQL Server Profiler)</span></span>
  <span data-ttu-id="36fee-103">In diesem Thema wird beschrieben, wie Sie mithilfe von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]Ablaufverfolgungsereignisse basierend auf der Ereignisstartzeit filtern.</span><span class="sxs-lookup"><span data-stu-id="36fee-103">This topic describes how to filter trace events based on the event start time by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-filter-an-event-based-on-the-event-start-time"></a><span data-ttu-id="36fee-104">So filtern Sie ein Ereignis basierend auf der Ereignisstartzeit</span><span class="sxs-lookup"><span data-stu-id="36fee-104">To filter an event based on the event start time</span></span>  
  
1.  <span data-ttu-id="36fee-105">Klicken Sie im Menü **Datei** auf **Neue Ablaufverfolgung**, und stellen Sie dann eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="36fee-105">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="36fee-106">Das Dialogfeld **Ablaufverfolgungseigenschaften**wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="36fee-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="36fee-107">Bei der Auswahl von **Ablaufverfolgung sofort nach dem Herstellen der Verbindung starten**wird das Dialogfeld **Ablaufverfolgungseigenschaften**nicht angezeigt. Stattdessen beginnt die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="36fee-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear, and the trace begins instead.</span></span> <span data-ttu-id="36fee-108">Um diese Einstellung zu deaktivieren, klicken Sie im Menü **Extras**auf **Optionen**, und deaktivieren Sie das Kontrollkästchen **Ablaufverfolgung sofort nach dem Herstellen der Verbindung starten** .</span><span class="sxs-lookup"><span data-stu-id="36fee-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="36fee-109">Geben Sie im Feld **Ablaufverfolgungsname** einen Namen für die Ablaufverfolgung ein.</span><span class="sxs-lookup"><span data-stu-id="36fee-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="36fee-110">Geben Sie im Feld **Vorlage verwenden**eine Ablaufverfolgungsvorlage aus.</span><span class="sxs-lookup"><span data-stu-id="36fee-110">In the **Use the template**name list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="36fee-111">Geben Sie optional ein Ziel für die Ablaufverfolgungsergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="36fee-111">Optionally specify a destination for the trace results.</span></span>  
  
5.  <span data-ttu-id="36fee-112">Klicken Sie im Menü **Ereignisauswahl**auf die Spaltenüberschrift **StartTime** .</span><span class="sxs-lookup"><span data-stu-id="36fee-112">On the **Events Selection**tab, click the **StartTime** column heading.</span></span> <span data-ttu-id="36fee-113">Sie können auch mit der rechten Maustaste auf die Spaltenüberschrift klicken und dann auf **Spaltenfilter bearbeiten** klicken, um das Dialogfeld **Filter bearbeiten** zu starten.</span><span class="sxs-lookup"><span data-stu-id="36fee-113">You can also right-click the column heading, and then click **Edit Column Filter** to launch the **Edit Filter** dialog box.</span></span>  
  
6.  <span data-ttu-id="36fee-114">Erweitern Sie **größer als** oder **kleiner als**, und geben Sie dann einen `datetime` Wert in das Feld ein, das unterhalb des Vergleichs Operators angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="36fee-114">Expand **Greater than** or **Less than**, and then enter a `datetime` value in the field that appears beneath the comparison operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36fee-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="36fee-115">See Also</span></span>  
 [<span data-ttu-id="36fee-116">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="36fee-116">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
