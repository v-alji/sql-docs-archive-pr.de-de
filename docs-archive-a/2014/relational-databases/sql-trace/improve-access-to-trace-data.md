---
title: Verbessern des Zugriffs auf Ablaufverfolgungsdaten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Profiler [SQL Server Profiler], space
- SQL Server Profiler, space
- space [SQL Server], SQL Server Profiler
ms.assetid: c260c000-fd53-4831-993f-df6894f3228b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 60e01ad04ddd9f7fe6d858c399abb552716f2bea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697654"
---
# <a name="improve-access-to-trace-data"></a><span data-ttu-id="0b8a5-102">Verbessern des Zugriffs auf Ablaufverfolgungsdaten</span><span class="sxs-lookup"><span data-stu-id="0b8a5-102">Improve Access to Trace Data</span></span>
  [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="0b8a5-103">verwendet Leerzeichen im Verzeichnis **temp** , um den Zugriff auf Ablaufverfolgungsdaten zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="0b8a5-103">uses space in the **temp** directory to improve access to trace data.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="0b8a5-104">erfordert mindestens 10 MB freien Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="0b8a5-104">requires at least 10 megabytes (MB) of free space.</span></span> <span data-ttu-id="0b8a5-105">Wenn der verfügbare Speicherplatz beim Verwenden von [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]weniger als 10 MB beträgt, werden alle [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] -Funktionen beendet.</span><span class="sxs-lookup"><span data-stu-id="0b8a5-105">If free space drops below 10 MB while you are using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], all [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] functions stop.</span></span>  
  
 <span data-ttu-id="0b8a5-106">Wenn [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] Speicherplatz im **temp** -Verzeichnis verwendet, kann das **temp** -Verzeichnis durch diese Speicherverwendung schnell anwachsen.</span><span class="sxs-lookup"><span data-stu-id="0b8a5-106">When [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] uses space in the **temp** directory, this space usage may cause the **temp** directory to grow rapidly.</span></span> <span data-ttu-id="0b8a5-107">Um Probleme mit der Dateivergrößerung zu vermeiden, können Sie das **temp** -Verzeichnis auf einem Laufwerk platzieren, das kein Systemlaufwerk ist. Ändern Sie dazu den Wert für die TEMP-Umgebungsvariable.</span><span class="sxs-lookup"><span data-stu-id="0b8a5-107">To avoid file-growth problems, you can place the **temp** directory on a drive that is not a system drive by changing the value for the TEMP environment variable.</span></span>  
  
 <span data-ttu-id="0b8a5-108">Im folgenden Verfahren wird beschrieben, wie der Wert für die TEMP-Umgebungsvariable bei den meisten Microsoft Windows-Betriebssystemen geändert wird.</span><span class="sxs-lookup"><span data-stu-id="0b8a5-108">The following procedure describes how to change the value for the TEMP environment variable in most Microsoft Windows operating systems.</span></span> <span data-ttu-id="0b8a5-109">Weitere Informationen zum Festlegen von Umgebungsvariablen finden Sie in der Dokumentation des Windows-Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="0b8a5-109">For more information about setting environment variables, see your Windows operating system documentation.</span></span>  
  
### <a name="to-change-the-temp-environment-variable-in-windows-operating-systems"></a><span data-ttu-id="0b8a5-110">So ändern Sie die TEMP-Umgebungsvariable in Windows-Betriebssystemen</span><span class="sxs-lookup"><span data-stu-id="0b8a5-110">To change the TEMP environment variable in Windows operating systems</span></span>  
  
1.  <span data-ttu-id="0b8a5-111">Wählen Sie im Menü **Start** die Option **Systemsteuerung**aus, und klicken Sie dann auf **System**.</span><span class="sxs-lookup"><span data-stu-id="0b8a5-111">On the **Start** menu, choose **Control Panel**, and then click **System**.</span></span>  
  
2.  <span data-ttu-id="0b8a5-112">Klicken Sie im Dialogfeld **Systemeigenschaften** auf die Registerkarte **Erweitert** , und klicken Sie dann auf **Umgebungsvariablen**.</span><span class="sxs-lookup"><span data-stu-id="0b8a5-112">In the **System Properties** dialog box, click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
3.  <span data-ttu-id="0b8a5-113">Führen Sie in der Liste **Systemvariablen**einen Bildlauf nach unten durch, wählen Sie die Zeile für die **TEMP** -Variable aus, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="0b8a5-113">Scroll down the list of **System Variables**, select the row that corresponds to the **TEMP** variable, and click **Edit**.</span></span>  
  
4.  <span data-ttu-id="0b8a5-114">Geben Sie im Dialogfeld **Systemvariable bearbeiten** den Pfad und den Namen des Laufwerks und des Verzeichnisses für das **temp** -Verzeichnis ein.</span><span class="sxs-lookup"><span data-stu-id="0b8a5-114">In the **Edit System Variable** dialog box, enter the path and name of the drive and directory where you want the **temp** directory to be located.</span></span>  
  
5.  <span data-ttu-id="0b8a5-115">Klicken Sie auf **OK** , um die Änderung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="0b8a5-115">Click **OK** to save the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b8a5-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0b8a5-116">See Also</span></span>  
 <span data-ttu-id="0b8a5-117">[Starten von SQL Server Profiler](../../tools/sql-server-profiler/start-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="0b8a5-117">[Start SQL Server Profiler](../../tools/sql-server-profiler/start-sql-server-profiler.md) </span></span>  
 [<span data-ttu-id="0b8a5-118">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="0b8a5-118">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
