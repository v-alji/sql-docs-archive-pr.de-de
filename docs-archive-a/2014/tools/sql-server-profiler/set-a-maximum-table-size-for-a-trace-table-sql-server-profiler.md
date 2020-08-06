---
title: Festlegen der maximalen Tabellengröße für eine Ablaufverfolgungstabelle (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- size [SQL Server], trace tables
- maximum table size for traces
ms.assetid: d0ae83e5-1c88-4a2e-be05-2c341280b978
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5f48efbe02e300e06faf857ed0fb36ae340ad979
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694918"
---
# <a name="set-a-maximum-table-size-for-a-trace-table-sql-server-profiler"></a><span data-ttu-id="ce1a9-102">Festlegen der maximalen Tabellengröße für eine Ablaufverfolgungstabelle (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="ce1a9-102">Set a Maximum Table Size for a Trace Table (SQL Server Profiler)</span></span>
  <span data-ttu-id="ce1a9-103">In diesem Thema wird beschrieben, wie Sie mithilfe von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]die maximale Tabellengröße für Ablaufverfolgungstabellen festlegen.</span><span class="sxs-lookup"><span data-stu-id="ce1a9-103">This topic describes how to set a maximum table size for trace tables by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-set-a-maximum-table-size-for-a-trace-table"></a><span data-ttu-id="ce1a9-104">So legen Sie die maximale Tabellengröße für eine Ablaufverfolgungstabelle fest</span><span class="sxs-lookup"><span data-stu-id="ce1a9-104">To set a maximum table size for a trace table</span></span>  
  
1.  <span data-ttu-id="ce1a9-105">Klicken Sie im Menü **Datei** auf **Neue Ablaufverfolgung**, und stellen Sie dann eine Verbindung zu einer Instanz von SQL Server her.</span><span class="sxs-lookup"><span data-stu-id="ce1a9-105">On the **File** menu, click **New Trace**, and then connect to an instance of SQL Server.</span></span>  
  
     <span data-ttu-id="ce1a9-106">Das Dialogfeld **Ablaufverfolgungseigenschaften**wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ce1a9-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ce1a9-107">Bei der Auswahl von **Ablaufverfolgung sofort nach dem Herstellen der Verbindung starten**wird das Dialogfeld **Ablaufverfolgungseigenschaften**nicht angezeigt. Stattdessen beginnt die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="ce1a9-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="ce1a9-108">Um diese Einstellung zu deaktivieren, klicken Sie im Menü **Extras**auf **Optionen**, und deaktivieren Sie das Kontrollkästchen **Ablaufverfolgung sofort nach dem Herstellen der Verbindung starten** .</span><span class="sxs-lookup"><span data-stu-id="ce1a9-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="ce1a9-109">Geben Sie im Feld **Ablaufverfolgungsname** einen Namen für die Ablaufverfolgung ein.</span><span class="sxs-lookup"><span data-stu-id="ce1a9-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="ce1a9-110">Geben Sie im Feld **Vorlagenname**eine Ablaufverfolgungsvorlage aus.</span><span class="sxs-lookup"><span data-stu-id="ce1a9-110">In the **Template name**list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="ce1a9-111">Aktivieren Sie das Kontrollkästchen **In Tabelle speichern**.</span><span class="sxs-lookup"><span data-stu-id="ce1a9-111">Select the **Save to table**check box.</span></span>  
  
5.  <span data-ttu-id="ce1a9-112">Stellen Sie eine Verbindung mit dem Server her, auf dem Sie die Ablaufverfolgung speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="ce1a9-112">Connect to the server on which you want the trace to be stored.</span></span>  
  
     <span data-ttu-id="ce1a9-113">Das Dialogfeld **Zieltabelle** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="ce1a9-113">The **Destination Table** dialog box appears.</span></span>  
  
6.  <span data-ttu-id="ce1a9-114">Wählen Sie aus der Liste **Datenbank** eine Datenbank für die Ablaufverfolgung aus.</span><span class="sxs-lookup"><span data-stu-id="ce1a9-114">Select a database for the trace from the **Database** list.</span></span>  
  
7.  <span data-ttu-id="ce1a9-115">Geben Sie im Feld **Tabelle** einen Tabellennamen ein, oder wählen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="ce1a9-115">In the **Table** box, type or select a table name.</span></span>  
  
8.  <span data-ttu-id="ce1a9-116">Aktivieren Sie das Kontrollkästchen **Maximale Zeilenanzahl festlegen** , und geben Sie die maximale Zeilenanzahl für die Ablaufverfolgungstabelle an.</span><span class="sxs-lookup"><span data-stu-id="ce1a9-116">Select the **Set maximum rows** check box, and specify a maximum number of rows for the trace table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ce1a9-117">Überschreiten die Zeilen in der Tabelle die maximale Anzahl, die Sie angegeben haben, werden keine Ablaufverfolgungsereignisse mehr aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ce1a9-117">When the number of rows in the table exceeds the maximum that you have specified, the trace events are no longer recorded.</span></span> <span data-ttu-id="ce1a9-118">Die Ablaufverfolgung wird jedoch fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="ce1a9-118">However, tracing continues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce1a9-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ce1a9-119">See Also</span></span>  
 <span data-ttu-id="ce1a9-120">[SQL Server Profiler](sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="ce1a9-120">[SQL Server Profiler](sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="ce1a9-121">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="ce1a9-121">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
