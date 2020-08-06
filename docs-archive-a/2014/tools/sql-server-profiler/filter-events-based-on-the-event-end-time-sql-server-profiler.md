---
title: Filtern von Ereignissen anhand der Ereignisendzeit (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- event end times [SQL Server]
- filters [SQL Server], traces
- traces [SQL Server], filters
- traces [SQL Server], events
ms.assetid: 74628f9e-2d39-496a-a443-0a3887db223d
author: stevestein
ms.author: sstein
ms.openlocfilehash: d25d8e1adbd95f48d88fd1516c48dcc0f8374a7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725170"
---
# <a name="filter-events-based-on-the-event-end-time-sql-server-profiler"></a><span data-ttu-id="6b5e0-102">Filtern von Ereignissen anhand der Ereignisendzeit (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="6b5e0-102">Filter Events Based on the Event End Time (SQL Server Profiler)</span></span>
  <span data-ttu-id="6b5e0-103">In diesem Thema wird beschrieben, wie Sie mithilfe von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]Ablaufverfolgungsereignisse basierend auf der Beendigungszeit des Ereignisses filtern.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-103">This topic describes how to filter trace events based on the event ending time by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-filter-events-based-on-the-event-end-time"></a><span data-ttu-id="6b5e0-104">So filtern Sie Ereignisse, die auf der Beendigungszeit des Ereignisses basieren</span><span class="sxs-lookup"><span data-stu-id="6b5e0-104">To filter events based on the event end time</span></span>  
  
1.  <span data-ttu-id="6b5e0-105">Klicken Sie im Menü **Datei** auf **Neue Ablaufverfolgung**, und stellen Sie dann eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-105">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="6b5e0-106">Das Dialogfeld **Ablaufverfolgungseigenschaften**wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6b5e0-107">Bei der Auswahl von **Ablaufverfolgung sofort nach dem Herstellen der Verbindung starten**wird das Dialogfeld **Ablaufverfolgungseigenschaften**nicht angezeigt. Stattdessen beginnt die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="6b5e0-108">Um diese Einstellung zu deaktivieren, klicken Sie im Menü **Extras**auf **Optionen**, und deaktivieren Sie das Kontrollkästchen **Ablaufverfolgung sofort nach dem Herstellen der Verbindung starten** .</span><span class="sxs-lookup"><span data-stu-id="6b5e0-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="6b5e0-109">Stellen Sie im Dialogfeld **Ablaufverfolgungseigenschaften** sicher, dass die Registerkarte **Allgemein** ausgewählt ist, und geben Sie in das Textfeld **Ablaufverfolgungsname** einen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-109">In the **Trace Properties** dialog box, make sure the **General** tab is selected, and enter a name in the **TraceName** text box.</span></span>  
  
3.  <span data-ttu-id="6b5e0-110">Wählen Sie in der Liste **Vorlage verwenden**eine Nachverfolgungsvorlage aus.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-110">From the **Use the template**list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="6b5e0-111">Sie können optional eine Zieldatei oder Zieltabelle angeben, in der die Ablaufverfolgungsergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-111">Optionally, specify a destination file or table in which to save the trace results.</span></span>  
  
5.  <span data-ttu-id="6b5e0-112">Klicken Sie auf der Registerkarte **Ereignisauswahl**auf die **EndTime** Datenspalte, um das Dialogfeld **Filter bearbeiten** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-112">On the **Events Selection**tab, click the **EndTime** data column to launch the **Edit Filter** dialog box.</span></span> <span data-ttu-id="6b5e0-113">Sie können auch mit der rechten Maustaste auf die Spaltenüberschrift klicken und **Spaltenfilter bearbeiten**auswählen.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-113">You can also right-click the column heading, and select **Edit Column Filter**.</span></span>  
  
6.  <span data-ttu-id="6b5e0-114">Erweitern Sie **größer als** oder **kleiner als**, und geben Sie einen `datetime` Wert in das Feld ein, das unterhalb des Vergleichs Operators angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6b5e0-114">Expand **Greater than** or **Less than**, and enter a `datetime`value in the field that appears beneath the comparison operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b5e0-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6b5e0-115">See Also</span></span>  
 <span data-ttu-id="6b5e0-116">[SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="6b5e0-116">[SQL Server Profiler](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="6b5e0-117">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="6b5e0-117">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
