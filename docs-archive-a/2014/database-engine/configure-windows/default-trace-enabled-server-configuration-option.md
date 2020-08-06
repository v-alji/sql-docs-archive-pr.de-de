---
title: Standardablaufverfolgung aktiviert (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], traces
- traces [SQL Server], logs
- default trace enabled option
ms.assetid: 1322d668-44f4-469e-8fd6-e0d02a81c8f2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8d40305de7375f2ae10d563871fd40b7acfa463f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724177"
---
# <a name="default-trace-enabled-server-configuration-option"></a><span data-ttu-id="73a57-102">Standardablaufverfolgung aktiviert (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="73a57-102">default trace enabled Server Configuration Option</span></span>
  <span data-ttu-id="73a57-103">Mit der Option **Standardablaufverfolgung aktiviert** können Sie die standardmäßigen Ablaufverfolgungsprotokolldateien aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="73a57-103">Use the **default trace enabled** option to enable or disable the default trace log files.</span></span> <span data-ttu-id="73a57-104">Mit der Standardablaufverfolgung steht Ihnen ein umfassendes, persistentes Protokoll zu Aktivitäten und primär auf die Konfigurationsoptionen bezogenen Änderungen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="73a57-104">The default trace functionality provides a rich, persistent log of activity and changes primarily related to the configuration options.</span></span>  
  
> [!WARNING]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="73a57-105">Verwenden Sie stattdessen erweiterte Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="73a57-105">Use Extended Events instead.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="73a57-106">Zweck</span><span class="sxs-lookup"><span data-stu-id="73a57-106">Purpose</span></span>  
 <span data-ttu-id="73a57-107">Die Standardablaufverfolgung vereinfacht Datenbankadministratoren die Problembehandlung, indem die für die Diagnose von erstmalig auftretenden Problemen erforderlichen Protokolldaten zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="73a57-107">Default trace provides troubleshooting assistance to database administrators by ensuring that they have the log data necessary to diagnose problems the first time they occur.</span></span>  
  
## <a name="viewing"></a><span data-ttu-id="73a57-108">Anzeigen</span><span class="sxs-lookup"><span data-stu-id="73a57-108">Viewing</span></span>  
 <span data-ttu-id="73a57-109">Die Standardablaufverfolgungsprotokolle können in [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] geöffnet und überprüft werden oder mit [!INCLUDE[tsql](../../includes/tsql-md.md)] mithilfe der `fn_trace_gettable` -Systemfunktion abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="73a57-109">The default trace logs can be opened and examined by [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or queried with [!INCLUDE[tsql](../../includes/tsql-md.md)] by using the `fn_trace_gettable` system function.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="73a57-110">können die Standard-Ablaufverfolgungsprotokolldateien wie normale Ablaufverfolgungsausgabedateien geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="73a57-110">can open the default trace log files just as it does normal trace output files.</span></span> <span data-ttu-id="73a57-111">Das Protokoll für die Standardablaufverfolgung wird mithilfe einer Rollover-Ablaufverfolgungsdatei standardmäßig im Verzeichnis `\MSSQL\LOG` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="73a57-111">The default trace log is stored by default in the `\MSSQL\LOG` directory using a rollover trace file.</span></span> <span data-ttu-id="73a57-112">Der Basisdateiname für die Protokolldatei der Standardablaufverfolgung lautet `log.trc`.</span><span class="sxs-lookup"><span data-stu-id="73a57-112">The base file name for the default trace log file is `log.trc`.</span></span> <span data-ttu-id="73a57-113">In einer typischen Installation von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ist die Standardablaufverfolgung aktiviert und erhält so TraceID 1.</span><span class="sxs-lookup"><span data-stu-id="73a57-113">In a typical installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the default trace is enabled and thus becomes TraceID 1.</span></span> <span data-ttu-id="73a57-114">Wenn die Standardablaufverfolgung nach der Installation und dem Erstellen von anderen Ablaufverfolgungen aktiviert wird, kann die TraceID eine größere Zahl sein.</span><span class="sxs-lookup"><span data-stu-id="73a57-114">If enabled after installation and after creating other traces, the TraceID can become a larger number.</span></span>  
  
 <span data-ttu-id="73a57-115">Weitere Informationen zum Anzeigen dieser Ablaufverfolgungsdatei mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Profiler finden Sie unter [Öffnen einer Ablaufverfolgungsdatei &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="73a57-115">For more information about using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Profiler to view this trace file, see [Open a Trace File &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md)</span></span>  
  
### <a name="example"></a><span data-ttu-id="73a57-116">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="73a57-116">Example:</span></span>  
 <span data-ttu-id="73a57-117">Durch die folgende Anweisung wird das Protokoll für die Standardablaufverfolgung im standardmäßigen Speicherort geöffnet:</span><span class="sxs-lookup"><span data-stu-id="73a57-117">The following statement opens the default trace log in the default location:</span></span>  
  
```  
SELECT *   
FROM fn_trace_gettable  
('C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\LOG\log.trc', default);  
GO  
  
```  
  
## <a name="configuring"></a><span data-ttu-id="73a57-118">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="73a57-118">Configuring</span></span>  
 <span data-ttu-id="73a57-119">Wenn für die Option **Standardablaufverfolgung aktiviert** der Wert 1 festgelegt wird, ist die **Standardablaufverfolgung**aktiviert.</span><span class="sxs-lookup"><span data-stu-id="73a57-119">When set to 1, the **default trace enabled** option enables **Default Trace**.</span></span> <span data-ttu-id="73a57-120">Der Standardwert für diese Option ist 1 (EIN).</span><span class="sxs-lookup"><span data-stu-id="73a57-120">The default setting for this option is 1 (ON).</span></span> <span data-ttu-id="73a57-121">Durch den Wert 0 wird die Ablaufverfolgung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="73a57-121">A value of 0 turns off the trace.</span></span>  
  
 <span data-ttu-id="73a57-122">Bei der Option **Standardablaufverfolgung aktiviert** handelt es sich um eine erweiterte Option.</span><span class="sxs-lookup"><span data-stu-id="73a57-122">The **default trace enabled** option is an advanced option.</span></span> <span data-ttu-id="73a57-123">Wenn Sie die Einstellung mithilfe der gespeicherten Systemprozedur **sp_configure** ändern, können Sie die Option **Standardablaufverfolgung aktiviert** nur ändern, wenn für **Erweiterte Optionen anzeigen** der Wert 1 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="73a57-123">If you are using the **sp_configure** system stored procedure to change the setting, you can change the **default trace enabled** option only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="73a57-124">Die Einstellung tritt ohne Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="73a57-124">The setting takes effect immediately without a server restart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73a57-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="73a57-125">See Also</span></span>  
 <span data-ttu-id="73a57-126">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="73a57-126">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="73a57-127">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="73a57-127">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="73a57-128">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="73a57-128">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
