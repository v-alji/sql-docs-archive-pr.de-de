---
title: Set the Polling Interval for Target Servers | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- interval for polling [SQL Server]
- target servers [SQL Server], polling interval
- polling interval [SQL Server]
ms.assetid: 4ffbbefa-77fb-442e-a77c-cb8c6cab9f3c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 36517f60a99a1a844f6d14d489587eef1de9cb13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726413"
---
# <a name="set-the-polling-interval-for-target-servers"></a><span data-ttu-id="68b12-102">Set the Polling Interval for Target Servers</span><span class="sxs-lookup"><span data-stu-id="68b12-102">Set the Polling Interval for Target Servers</span></span>
  <span data-ttu-id="68b12-103">In diesem Thema wird beschrieben, wie die Häufigkeit festgelegt wird, mit der- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Informationen von der Master-auf den Ziel Servern aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="68b12-103">This topic describes how to set the frequency that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent refreshes information from the master to the target servers.</span></span> <span data-ttu-id="68b12-104">Ein Auftrag ist eine festgelegte Reihe von Aktionen, die der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent ausführt.</span><span class="sxs-lookup"><span data-stu-id="68b12-104">A job is a specified series of actions that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent performs.</span></span> <span data-ttu-id="68b12-105">Ein Multiserverauftrag ist ein Auftrag, der von einem Masterserver auf mindestens einem Zielserver ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="68b12-105">A multiserver job is a job that a master server runs on one or more target servers.</span></span>  
  
-   <span data-ttu-id="68b12-106">**Vorbereitungen:**  [Sicherheit](#Security)</span><span class="sxs-lookup"><span data-stu-id="68b12-106">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="68b12-107">**Festlegen des Abrufintervalls für Zielserver mit:**  [SQL Server Management Studio](#SSMS), [Transact-SQL](#TSQL)</span><span class="sxs-lookup"><span data-stu-id="68b12-107">**To set the polling interval for target servers, using:**  [SQL Server Management Studio](#SSMS), [Transact-SQL](#TSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="68b12-108">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="68b12-108">Before You Begin</span></span>  
 <span data-ttu-id="68b12-109">Auf jedem Server kann gleichzeitig eine Instanz des gleichen Auftrags ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="68b12-109">Each target server can run one instance of the same job at the same time.</span></span> <span data-ttu-id="68b12-110">Jeder Zielserver ruft in regelmäßigen Abständen den Masterserver ab, lädt eine Kopie aller neuen Aufträge herunter, die dem Zielserver zugewiesen wurden, und trennt dann die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="68b12-110">Each target server periodically polls the master server, downloads a copy of any new jobs assigned to the target server, and then disconnects.</span></span> <span data-ttu-id="68b12-111">Der Zielserver führt den Auftrag lokal aus und stellt dann erneut eine Verbindung mit dem Masterserver her, um den Auftragsergebnisstatus hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="68b12-111">The target server runs the job locally and then reconnects to the master server to upload the job outcome status.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="68b12-112">Wenn der Zielserver versucht, den Auftragsstatus durch Hochladen zu übertragen, und dabei nicht auf den Masterserver zugreifen kann, bleibt der Auftragsstatus so lange im Spooler (in der Warteschlange), bis der Masterserver wieder zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="68b12-112">If the master server is inaccessible when the target server tries to upload job status, the job status is spooled until the master server can be accessed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="68b12-113">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="68b12-113">Security</span></span>  
 <span data-ttu-id="68b12-114">Ausführliche Informationen finden Sie unter [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) und [Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).</span><span class="sxs-lookup"><span data-stu-id="68b12-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) and [Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="68b12-115">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="68b12-115">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="68b12-116">**So legen Sie das Abrufintervall für Zielserver fest**</span><span class="sxs-lookup"><span data-stu-id="68b12-116">**To set the polling interval for target servers**</span></span>  
  
1.  <span data-ttu-id="68b12-117">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="68b12-117">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="68b12-118">Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent**, zeigen Sie auf **Multiserververwaltung**, und klicken Sie dann auf **Zielserver verwalten**.</span><span class="sxs-lookup"><span data-stu-id="68b12-118">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="68b12-119">Klicken Sie auf der Registerkarte **Status des Zielservers** auf **Anweisungen bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="68b12-119">On the **Target Server Status** tab, click **Post Instructions**.</span></span>  
  
4.  <span data-ttu-id="68b12-120">Wählen Sie in der Liste **Anweisungstyp** die Option **Abrufintervall festlegen**aus.</span><span class="sxs-lookup"><span data-stu-id="68b12-120">In the **Instruction type** list, select **Set polling interval**.</span></span>  
  
5.  <span data-ttu-id="68b12-121">Geben Sie im Feld **Abrufintervall** die Anzahl von Sekunden zwischen 10 und 28.800 ein, die verstreichen müssen, bevor der Zielserver den Masterserver abruft.</span><span class="sxs-lookup"><span data-stu-id="68b12-121">In the **Polling interval** box, enter the number of seconds from 10 through 28,800 that must pass before the target server polls the master server.</span></span>  
  
6.  <span data-ttu-id="68b12-122">Führen Sie unter **Empfänger**eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="68b12-122">Under **Recipients**, do one of the following:</span></span>  
  
    1.  <span data-ttu-id="68b12-123">Klicken Sie auf **Alle Zielserver** , wenn für alle Zielserver dasselbe Abrufintervall gilt.</span><span class="sxs-lookup"><span data-stu-id="68b12-123">Click **All target servers** if all target servers share the same polling interval.</span></span>  
  
    2.  <span data-ttu-id="68b12-124">Klicken Sie auf **Diese Zielserver** , wenn nicht für alle Zielserver dasselbe Abrufintervall gilt, und wählen Sie dann die Zielserver aus, für die dieses Abrufintervall verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="68b12-124">Click **These target servers** if not all target servers share the same polling interval, and then select each target server that will use this polling interval.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="68b12-125">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="68b12-125">Using Transact-SQL</span></span>  
 <span data-ttu-id="68b12-126">**So legen Sie das Abrufintervall für Zielserver fest**</span><span class="sxs-lookup"><span data-stu-id="68b12-126">**To set the polling interval for target servers**</span></span>  
  
1.  <span data-ttu-id="68b12-127">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz von Database Engine (Datenbankmodul) her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="68b12-127">In Object Explorer, connect to an instance of the Database Engine, and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="68b12-128">Klicken Sie auf der Symbolleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="68b12-128">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="68b12-129">Verwenden Sie im Abfragefenster die gespeicherte System Prozedur [sp_post_msx_operation &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql) , um das Abruf Intervall für Zielserver festzulegen.</span><span class="sxs-lookup"><span data-stu-id="68b12-129">In the query window, use the [sp_post_msx_operation &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql) system stored procedure to set the polling interval for target servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68b12-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="68b12-130">See Also</span></span>  
 [<span data-ttu-id="68b12-131">dbo.sysdownloadlist &#40;Transact-SQL-&#41;</span><span class="sxs-lookup"><span data-stu-id="68b12-131">dbo.sysdownloadlist &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/dbo-sysdownloadlist-transact-sql)  
  
  
