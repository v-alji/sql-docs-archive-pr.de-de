---
title: Speichern von Ablaufverfolgungsergebnissen in einer Tabelle (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- saving traces
- traces [SQL Server], saving
ms.assetid: edbecf74-683b-4e43-a1ef-7a3d5f5e27f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 08acfb4e7136f8b28d1c990d508b8578f96a57b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722021"
---
# <a name="save-trace-results-to-a-table-sql-server-profiler"></a><span data-ttu-id="0cec8-102">Speichern von Ablaufverfolgungsergebnissen in einer Tabelle (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="0cec8-102">Save Trace Results to a Table (SQL Server Profiler)</span></span>
  <span data-ttu-id="0cec8-103">In diesem Thema wird beschrieben, wie Ablaufverfolgungsergebnisse mithilfe von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]in einer Datenbanktabelle gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="0cec8-103">This topic describes how to save trace results to a database table by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-save-trace-results-to-a-table"></a><span data-ttu-id="0cec8-104">So speichern Sie Ablaufverfolgungsergebnisse in einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="0cec8-104">To save trace results to a table</span></span>  
  
1.  <span data-ttu-id="0cec8-105">Klicken Sie im Menü **Datei** auf **Neue Ablaufverfolgung**, und stellen Sie dann eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="0cec8-105">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="0cec8-106">Das Dialogfeld **Ablaufverfolgungseigenschaften**wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0cec8-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0cec8-107">Bei der Auswahl von **Ablaufverfolgung sofort nach dem Herstellen der Verbindung starten**wird das Dialogfeld **Ablaufverfolgungseigenschaften**nicht angezeigt. Stattdessen beginnt die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="0cec8-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="0cec8-108">Um diese Einstellung zu deaktivieren, klicken Sie im Menü **Extras**auf **Optionen**, und deaktivieren Sie das Kontrollkästchen **Ablaufverfolgung sofort nach dem Herstellen der Verbindung starten** .</span><span class="sxs-lookup"><span data-stu-id="0cec8-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="0cec8-109">Geben Sie im Feld **Ablaufverfolgungsname** einen Namen für die Ablaufverfolgung ein, und klicken Sie dann auf **In Tabelle speichern**.</span><span class="sxs-lookup"><span data-stu-id="0cec8-109">In the **Trace name** box, type a name for the trace, and then click **Save to table**.</span></span>  
  
3.  <span data-ttu-id="0cec8-110">Stellen Sie im Dialogfeld **Verbindung mit Server herstellen** eine Verbindung mit der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank her, die die Ablaufverfolgungstabelle enthalten wird.</span><span class="sxs-lookup"><span data-stu-id="0cec8-110">In the **Connect to server** dialog box, connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that will contain the trace table.</span></span>  
  
4.  <span data-ttu-id="0cec8-111">Geben Sie im Feld **Zieltabelle** in der Liste **Datenbank**eine Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="0cec8-111">In the **Destination Table** dialog box, select a database from the **Database**list.</span></span>  
  
5.  <span data-ttu-id="0cec8-112">Wählen Sie in der Liste **Besitzer** den Besitzer für die Ablaufverfolgung aus.</span><span class="sxs-lookup"><span data-stu-id="0cec8-112">In the **Owner** list, select the owner for the trace.</span></span>  
  
6.  <span data-ttu-id="0cec8-113">Geben Sie im Feld **Tabelle** den Tabellennamen für die Ablaufverfolgungsergebnisse ein, oder wählen Sie den Namen aus.</span><span class="sxs-lookup"><span data-stu-id="0cec8-113">In the **Table** list, type or select the table name for the trace results.</span></span> <span data-ttu-id="0cec8-114">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0cec8-114">Click **OK.**</span></span>  
  
7.  <span data-ttu-id="0cec8-115">Aktivieren Sie im Dialogfeld Ablauf **Verfolgungs Eigenschaften** das Kontrollkästchen **maximale Zeilenzahl festlegen (in Tausend)** , um die maximale Anzahl von Zeilen anzugeben, die gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0cec8-115">In the **Trace Properties** dialog box, select the **Set maximum rows (in thousands)** check box to specify the maximum number of rows to save.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cec8-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0cec8-116">See Also</span></span>  
 [<span data-ttu-id="0cec8-117">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="0cec8-117">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
