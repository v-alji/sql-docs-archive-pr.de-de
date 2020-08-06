---
title: Ändern der Größe des Auftragsverlaufsprotokolls | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], history
- resizing job history log
- size [SQL Server], job history log
- logs [SQL Server], jobs
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
ms.assetid: ddee1ce8-9d1b-4017-9894-bf7256aed95d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4c25cc43295d47b2bc19d48b5b257dbbe6bcfe9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616325"
---
# <a name="resize-the-job-history-log"></a><span data-ttu-id="2f4ec-102">Resize the Job History Log</span><span class="sxs-lookup"><span data-stu-id="2f4ec-102">Resize the Job History Log</span></span>
  <span data-ttu-id="2f4ec-103">In diesem Thema wird beschrieben, wie Sie Größenbeschränkungen für-Agent-Auftragsverlaufs [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Protokolle in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von festlegen [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f4ec-103">This topic describes how to set size limits for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history logs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="2f4ec-104">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="2f4ec-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2f4ec-105">Security</span><span class="sxs-lookup"><span data-stu-id="2f4ec-105">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2f4ec-106">**So legen Sie Größenbeschränkungen für den Auftragsverlauf fest mit**</span><span class="sxs-lookup"><span data-stu-id="2f4ec-106">**To set size limits for job history logs, using:**</span></span>  
  
     [<span data-ttu-id="2f4ec-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2f4ec-107">SQL Server Management Studio</span></span>](#SSMS)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2f4ec-108">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="2f4ec-108">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2f4ec-109">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="2f4ec-109">Security</span></span>  
 <span data-ttu-id="2f4ec-110">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="2f4ec-110">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="2f4ec-111">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2f4ec-111">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-resize-the-job-history-log-based-on-raw-size"></a><span data-ttu-id="2f4ec-112">So ändern Sie die Größe des Auftragsverlaufsprotokolls basierend auf der Basisgröße</span><span class="sxs-lookup"><span data-stu-id="2f4ec-112">To resize the job history log based on raw size</span></span>  
  
1.  <span data-ttu-id="2f4ec-113">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="2f4ec-113">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="2f4ec-114">Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent**, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="2f4ec-114">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="2f4ec-115">Wählen Sie die Seite **Verlauf** aus und bestätigen Sie dann, dass **Größe des Auftragsverlaufsprotokolls beschränken**aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2f4ec-115">Select the **History** page, and then confirm that **Limit size of job history log**is checked.</span></span>  
  
4.  <span data-ttu-id="2f4ec-116">Geben Sie im Feld **Maximale Länge des Auftragsverlaufsprotokolls** die Anzahl von Zeilen ein, die maximal für das Auftragsverlaufsprotokoll zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="2f4ec-116">In the **Maximum job history log size** box, enter the maximum number of rows the job history log should allow.</span></span>  
  
5.  <span data-ttu-id="2f4ec-117">Geben Sie im Feld **Maximale Zeilenanzahl pro Auftrag in Auftragsverlauf** die Anzahl von Zeilen ein, die maximal für das Auftragsverlaufsprotokoll eines Auftrags zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="2f4ec-117">In the **Maximum job history rows per job** box, enter the maximum number of job history rows to allow for a job.</span></span>  
  
#### <a name="to-resize-the-job-history-log-based-on-time"></a><span data-ttu-id="2f4ec-118">So ändern Sie die Größe des Auftragsverlaufsprotokolls basierend auf der Zeit</span><span class="sxs-lookup"><span data-stu-id="2f4ec-118">To resize the job history log based on time</span></span>  
  
1.  <span data-ttu-id="2f4ec-119">Stellen Sie im **Objekt-Explorer**eine Verbindung zu einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="2f4ec-119">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="2f4ec-120">Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent**, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="2f4ec-120">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="2f4ec-121">Wählen Sie die Seite **Verlauf** aus, und klicken Sie dann auf **Agentverlauf automatisch entfernen**.</span><span class="sxs-lookup"><span data-stu-id="2f4ec-121">Select the **History** page, and then click **Automatically remove agent history**.</span></span>  
  
4.  <span data-ttu-id="2f4ec-122">Wählen Sie die entsprechende Anzahl für **Tag(e)**, **Woche(n)** oder **Monat(e)** aus.</span><span class="sxs-lookup"><span data-stu-id="2f4ec-122">Select the appropriate number of **Days(s)**, **Week(s)**, or **Month(s)**.</span></span>  
  
  
