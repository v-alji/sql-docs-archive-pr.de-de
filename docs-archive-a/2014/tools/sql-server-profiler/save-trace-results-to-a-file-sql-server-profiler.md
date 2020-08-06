---
title: Speichern von Ablaufverfolgungsergebnissen in einer Datei (SQL Server Profiler) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- saving traces
- traces [SQL Server], saving
ms.assetid: ac528747-0c19-4f3d-96f5-44c762a4abed
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9644751cda3689cf7b7cb00ec25310bc700ca1c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722042"
---
# <a name="save-trace-results-to-a-file-sql-server-profiler"></a><span data-ttu-id="20374-102">Speichern von Ablaufverfolgungsergebnissen in einer Datei (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="20374-102">Save Trace Results to a File (SQL Server Profiler)</span></span>
  <span data-ttu-id="20374-103">In diesem Thema wird beschrieben, wie Ablaufverfolgungsergebnisse mithilfe von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]in einer Datei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="20374-103">This topic describes how to save trace results to a file by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-save-trace-results-to-a-file"></a><span data-ttu-id="20374-104">So speichern Sie Ablaufverfolgungsergebnisse in einer Datei</span><span class="sxs-lookup"><span data-stu-id="20374-104">To save trace results to a file</span></span>  
  
1.  <span data-ttu-id="20374-105">Klicken Sie im Menü **Datei** auf **Neue Ablaufverfolgung**, und stellen Sie dann eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="20374-105">On the **File** menu, click **New Trace**, and then connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="20374-106">Das Dialogfeld **Ablaufverfolgungseigenschaften**wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="20374-106">The **Trace Properties**dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="20374-107">Bei der Auswahl von **Ablaufverfolgung sofort nach dem Herstellen der Verbindung starten**wird das Dialogfeld **Ablaufverfolgungseigenschaften**nicht angezeigt. Stattdessen beginnt die Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="20374-107">If **Start tracing immediately after making connection**is selected, the **Trace Properties**dialog box fails to appear and the trace begins instead.</span></span> <span data-ttu-id="20374-108">Um diese Einstellung zu deaktivieren, klicken Sie im Menü **Extras**auf **Optionen**, und deaktivieren Sie das Kontrollkästchen **Ablaufverfolgung sofort nach dem Herstellen der Verbindung starten** .</span><span class="sxs-lookup"><span data-stu-id="20374-108">To turn off this setting, on the **Tools**menu, click **Options**, and clear the **Start tracing immediately after making connection** check box.</span></span>  
  
2.  <span data-ttu-id="20374-109">Geben Sie im Feld **Ablaufverfolgungsname** einen Namen für die Ablaufverfolgung ein.</span><span class="sxs-lookup"><span data-stu-id="20374-109">In the **Trace name** box, type a name for the trace.</span></span>  
  
3.  <span data-ttu-id="20374-110">Aktivieren Sie das Kontrollkästchen **In Datei speichern** .</span><span class="sxs-lookup"><span data-stu-id="20374-110">Select the **Save to file** check box.</span></span>  
  
     <span data-ttu-id="20374-111">Das Dialogfeld **Speichern unter**wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="20374-111">The **Save As**dialog box appears.</span></span>  
  
4.  <span data-ttu-id="20374-112">Geben Sie im Dialogfeld **Speichern unter**den Pfad und den Dateinamen an.</span><span class="sxs-lookup"><span data-stu-id="20374-112">Specify a path and filename in the **Save As**dialog box.</span></span> <span data-ttu-id="20374-113">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="20374-113">Click **Save.**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="20374-114">Stellen Sie sicher, dass der SQL Server-Dienst die entsprechenden Berechtigungen hat, um in eine Datei im angegebenen Verzeichnis zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="20374-114">Ensure that the SQL Server service has sufficient permissions to write to a file in the directory specified.</span></span>  
  
5.  <span data-ttu-id="20374-115">Geben Sie im Dialogfeld **Ablaufverfolgungseigenschaften** die maximale Dateigröße in das Textfeld **Maximale Dateigröße festlegen (MB)** ein.</span><span class="sxs-lookup"><span data-stu-id="20374-115">In the **Trace Properties** dialog box, enter the maximum file size in the **Set maximum file size (MB)** text box.</span></span> <span data-ttu-id="20374-116">Der Standardwert ist 5 MB.</span><span class="sxs-lookup"><span data-stu-id="20374-116">The default value is 5 megabytes (MB).</span></span>  
  
6.  <span data-ttu-id="20374-117">Geben Sie optional die folgenden Optionen an:</span><span class="sxs-lookup"><span data-stu-id="20374-117">Optionally, specify the following options:</span></span>  
  
    -   <span data-ttu-id="20374-118">Aktivieren Sie das Kontrollkästchen **Dateirollover aktivieren** , damit [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] neue Dateien für Ablaufverfolgungsdaten erstellt, wenn die maximale Dateigröße erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="20374-118">Select the **Enable file rollover** check box to have [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] create new files for trace data once the maximum file size is reached.</span></span> <span data-ttu-id="20374-119">Diese Option ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="20374-119">This option is selected by default.</span></span>  
  
    -   <span data-ttu-id="20374-120">Aktivieren Sie das Kontrollkästchen **Ablaufverfolgungsdaten von Serverprozessen** , um sicherzustellen, dass der Server jedes Ablaufverfolgungsereignis aufzeichnet.</span><span class="sxs-lookup"><span data-stu-id="20374-120">Select the **Server processes trace data** check box to ensure that the server records each trace event.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="20374-121">Wenn **Ablaufverfolgungsdaten von Serverprozessen**deaktiviert ist, zeichnet der Server keine Ereignisse auf, falls dadurch die Leistung erheblich beeinträchtigt wird.</span><span class="sxs-lookup"><span data-stu-id="20374-121">When **Server processes trace data**is cleared, the server does not record events if recording events significantly degrades performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20374-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="20374-122">See Also</span></span>  
 [<span data-ttu-id="20374-123">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="20374-123">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
