---
title: Einrichten des Auftragsverlaufsprotokolls | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], history
- logs [SQL Server], jobs
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
ms.assetid: 018e5c49-d3a0-4504-851a-f70996a34bb7
author: stevestein
ms.author: sstein
ms.openlocfilehash: cb42e1daaee8a3a9e5ae9cc3c09a8cc42dcbff56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695250"
---
# <a name="set-up-the-job-history-log"></a><span data-ttu-id="5b6aa-102">Set Up the Job History Log</span><span class="sxs-lookup"><span data-stu-id="5b6aa-102">Set Up the Job History Log</span></span>
  <span data-ttu-id="5b6aa-103">In diesem Thema wird beschrieben, wie Sie das Auftragsverlaufs Protokoll des- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agents einrichten.</span><span class="sxs-lookup"><span data-stu-id="5b6aa-103">This topic describes how to set up the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history log.</span></span>  
  
-   <span data-ttu-id="5b6aa-104">**Vorbereitungen:**  [Sicherheit](#Security)</span><span class="sxs-lookup"><span data-stu-id="5b6aa-104">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="5b6aa-105">**Einrichten des Auftragsverlaufsprotokolls mit:**  [SQL Server Management Studio](#SSMS)</span><span class="sxs-lookup"><span data-stu-id="5b6aa-105">**To setup the job history log, using:**  [SQL Server Management Studio](#SSMS)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5b6aa-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="5b6aa-106">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5b6aa-107">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="5b6aa-107">Security</span></span>  
 <span data-ttu-id="5b6aa-108">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="5b6aa-108">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="5b6aa-109">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5b6aa-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="5b6aa-110">**So richten Sie das Auftragsverlaufsprotokoll ein**</span><span class="sxs-lookup"><span data-stu-id="5b6aa-110">**To set up the job history log**</span></span>  
  
1.  <span data-ttu-id="5b6aa-111">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="5b6aa-111">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="5b6aa-112">Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent**, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="5b6aa-112">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="5b6aa-113">Wählen Sie im Dialogfeld **Eigenschaften des SQL Server-Agents** die Seite **Verlauf** aus.</span><span class="sxs-lookup"><span data-stu-id="5b6aa-113">In the **SQL Server Agent Properties** dialog box, select the **History** page.</span></span>  
  
4.  <span data-ttu-id="5b6aa-114">Sie können zwischen folgenden Optionen wählen:</span><span class="sxs-lookup"><span data-stu-id="5b6aa-114">Choose from the following options:</span></span>  
  
    1.  <span data-ttu-id="5b6aa-115">Aktivieren Sie die Option **Größe des Auftragsverlaufsprotokolls beschränken**, und geben Sie dann die maximale Anzahl von Zeilen für das Auftragsverlaufsprotokoll sowie die maximale Anzahl von Zeilen je Auftrag ein.</span><span class="sxs-lookup"><span data-stu-id="5b6aa-115">Check **Limit size of job history log**, and then type the maximum number of rows for the job history log, and the maximum number of rows per job.</span></span>  
  
    2.  <span data-ttu-id="5b6aa-116">Aktivieren Sie die Option **Agentverlauf automatisch entfernen**, und geben Sie den Zeitraum an, nach dem ältere Verlaufsdaten aus dem Protokoll gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="5b6aa-116">Check **Automatically remove agent history**, and specify a time period, such that history older than this period will be purged from the log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b6aa-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b6aa-117">See Also</span></span>  
 <span data-ttu-id="5b6aa-118">[Implementieren von Aufträgen](implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="5b6aa-118">[Implement Jobs](implement-jobs.md) </span></span>  
 <span data-ttu-id="5b6aa-119">[Überwachen der Auftrags Aktivität](monitor-job-activity.md) </span><span class="sxs-lookup"><span data-stu-id="5b6aa-119">[Monitor Job Activity](monitor-job-activity.md) </span></span>  
 [<span data-ttu-id="5b6aa-120">Erstellen von Aufträgen</span><span class="sxs-lookup"><span data-stu-id="5b6aa-120">Create Jobs</span></span>](create-jobs.md)  
  
  
