---
title: Filtern von Server-Prozess-IDs (SPIDs) in einer Ablaufverfolgung (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], traces
- filters [SQL Server], SPIDs
- traces [SQL Server], filters
ms.assetid: f5945c39-be6b-4632-91cb-92066c80e188
author: stevestein
ms.author: sstein
ms.openlocfilehash: 99ae7eac6f19bd942a04f97b0a7da580eadc9dbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723242"
---
# <a name="filter-server-process-ids-spids-in-a-trace-sql-server-profiler"></a><span data-ttu-id="db84b-102">Filtern von Server-Prozess-IDs (SPIDs) in einer Ablaufverfolgung (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="db84b-102">Filter Server Process IDs (SPIDs) in a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="db84b-103">In diesem Thema wird das Filtern von Server-Prozess-IDs (SPIDs) in einer Ablaufverfolgung mithilfe von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]erläutert.</span><span class="sxs-lookup"><span data-stu-id="db84b-103">This topic describes how to filter server process identifiers (SPIDs) in a trace by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-filter-system-ids-in-a-trace"></a><span data-ttu-id="db84b-104">So filtern Sie System-IDs in einer Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="db84b-104">To filter system IDs in a trace</span></span>  
  
1.  <span data-ttu-id="db84b-105">Klicken Sie im Menü **Datei** auf **Neue Ablaufverfolgung**, und stellen Sie dann eine Verbindung zu einer Instanz von SQL Server her.</span><span class="sxs-lookup"><span data-stu-id="db84b-105">On the **File** menu, click **New Trace**, and then connect to an instance of SQL Server.</span></span>  
  
     <span data-ttu-id="db84b-106">Das Dialogfeld **Ablaufverfolgungseigenschaften**wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="db84b-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="db84b-107">Wenn die Option Ablauf **Verfolgung sofort nach dem Herstellen der Verbindung starten**ausgewählt ist, wird das Dialogfeld Ablauf Verfolgungs **Eigenschaften**nicht angezeigt. stattdessen beginnt die Ablauf Verfolgung.</span><span class="sxs-lookup"><span data-stu-id="db84b-107">if **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear, and the trace begins instead.</span></span> <span data-ttu-id="db84b-108">Um diese Einstellung zu deaktivieren, klicken Sie im Menü **Extras**auf **Optionen**, und deaktivieren Sie das Kontrollkästchen **Ablaufverfolgung sofort nach dem Herstellen der Verbindung starten** .</span><span class="sxs-lookup"><span data-stu-id="db84b-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="db84b-109">Geben Sie im Feld **Ablaufverfolgungsname** einen Namen für die Ablaufverfolgung ein.</span><span class="sxs-lookup"><span data-stu-id="db84b-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="db84b-110">Geben Sie im Feld **Vorlage verwenden**eine Ablaufverfolgungsvorlage aus.</span><span class="sxs-lookup"><span data-stu-id="db84b-110">In the **Use the template**name list, select a trace template.</span></span>  
  
4.  <span data-ttu-id="db84b-111">Sie können optional eine Zieldatei oder Zieltabelle angeben, in der die Ablaufverfolgungsergebnisse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="db84b-111">Optionally, specify a destination file or table in which to save the trace results.</span></span>  
  
5.  <span data-ttu-id="db84b-112">Klicken Sie auf der Registerkarte **Ereignisauswahl**auf die Spaltenüberschrift **SPID**, um das Dialogfeld **Filter bearbeiten** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="db84b-112">On the **Events Selection**tab, click the **SPID**column heading to launch the **Edit Filter** dialog box.</span></span> <span data-ttu-id="db84b-113">Sie können auch mit der rechten Maustaste auf die Spaltenüberschrift klicken und **Spaltenfilter bearbeiten**auswählen.</span><span class="sxs-lookup"><span data-stu-id="db84b-113">You can also right-click the column heading and choose **Edit Column Filter**.</span></span> <span data-ttu-id="db84b-114">Wenn die **SPID** -Spalte nicht angezeigt wird, überprüfen Sie das Feld **Alle Spalten anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="db84b-114">If the **SPID** column does not appear, check the **Show all columns** box.</span></span>  
  
6.  <span data-ttu-id="db84b-115">Erweitern Sie im Dialogfeld **Filter bearbeiten** den entsprechenden Vergleichsoperator, und geben Sie eine SPID als Wert für den Vergleich ein.</span><span class="sxs-lookup"><span data-stu-id="db84b-115">In the **Edit Filter** dialog box, expand the appropriate comparison operator, and enter a SPID as a value for the comparison.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db84b-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="db84b-116">See Also</span></span>  
 [<span data-ttu-id="db84b-117">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="db84b-117">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
