---
title: Ändern der Zielwiederherstellungszeit einer Datenbank (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/13/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
ms.assetid: e466419a-d8a4-48f7-8d97-13a903ad6b15
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4c4331d2ade2819d172189a0de9daddecf3d9f6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616546"
---
# <a name="change-the-target-recovery-time-of-a-database-sql-server"></a><span data-ttu-id="aa686-102">Ändern der Zielwiederherstellungszeit einer Datenbank (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="aa686-102">Change the Target Recovery Time of a Database (SQL Server)</span></span>
  <span data-ttu-id="aa686-103">In diesem Thema wird beschrieben, wie die Zielwiederherstellungszeit einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]geändert wird.</span><span class="sxs-lookup"><span data-stu-id="aa686-103">This topic describes how to set the change the target recovery time of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="aa686-104">Standardmäßig ist die Zielwiederherstellungszeit 0, und die Datenbank verwendet *automatische Prüfpunkte* (die durch die Serveroption **Wiederherstellungsintervall** gesteuert werden).</span><span class="sxs-lookup"><span data-stu-id="aa686-104">By default, the target recovery time is 0, and the database uses *automatic checkpoints* (which are controlled by the **recovery interval** server option).</span></span> <span data-ttu-id="aa686-105">Das Festlegen der Zielwiederherstellungszeit auf größer 0 führt dazu, dass die Datenbank die *indirekten Prüfpunkte* verwendet und eine Obergrenze der Wiederherstellungszeit für diese Datenbank festlegt.</span><span class="sxs-lookup"><span data-stu-id="aa686-105">Setting the target recovery time to greater than 0 causes the database to use the *indirect-checkpoints* and establishes an upper-bound on recovery time for this database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aa686-106">Die Obergrenze, die für eine bestimmte Datenbank durch die Wiederherstellungszeiteinstellung für das Ziel angegeben wird, könnte überschritten werden, wenn eine Transaktion mit langer Laufzeit übermäßig lange UNDO-Zeiten verursacht.</span><span class="sxs-lookup"><span data-stu-id="aa686-106">The upper-bound that is specified for a given database by its target recovery time setting could be exceeded if a long-running transaction causes excessive UNDO times.</span></span>  
  
-   <span data-ttu-id="aa686-107">**Vorbereitungen:**  [Beschränkungen](#Restrictions), [Sicherheit](#Security)</span><span class="sxs-lookup"><span data-stu-id="aa686-107">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="aa686-108">**So ändern Sie die Zielwiederherstellungszeit mithilfe von:**  [SQL Server Management Studio](#SSMSProcedure) oder [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="aa686-108">**To change the target recovery time, using:**  [SQL Server Management Studio](#SSMSProcedure) or [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="aa686-109">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="aa686-109">Before You Begin</span></span>  
  
###  <a name="Restrictions"></a>  
  
> [!CAUTION]  
>  <span data-ttu-id="aa686-110">Im Fall einer Arbeitsauslastung für Onlinetransaktionen bei einer Datenbank, die für indirekte Prüfpunkte konfiguriert ist, kann eine Verringerung der Leistung auftreten.</span><span class="sxs-lookup"><span data-stu-id="aa686-110">An online transactional workload on a database that is configured for indirect checkpoints could experience performance degradation.</span></span> <span data-ttu-id="aa686-111">Indirekte Prüfpunkte stellen sicher, dass die Anzahl der modifizierten Seiten unter einem bestimmten Schwellenwert liegt, sodass die Datenbankwiederherstellung innerhalb der Zielwiederherstellungszeit abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="aa686-111">Indirect checkpoints make sure that the number of dirty pages are below a certain threshold so that the database recovery completes within the target recovery time.</span></span> <span data-ttu-id="aa686-112">Die Konfigurationsoption „Wiederherstellungsintervall“ ermittelt die Wiederherstellungszeit über die Anzahl der Transaktionen. Im Gegensatz dazu greifen indirekte Prüfpunkte auf die Anzahl der modifizierten Seiten zurück.</span><span class="sxs-lookup"><span data-stu-id="aa686-112">The recovery interval configuration option uses the number of transactions to determine the recovery time as opposed to indirect checkpoints which makes use of number of dirty pages.</span></span> <span data-ttu-id="aa686-113">Wenn für eine Datenbank, die eine große Anzahl von DML-Vorgängen empfängt, indirekte Prüfpunkte aktiviert sind, können beim Schreiben im Hintergrund leere modifizierte Puffer aggressiv auf den Datenträger geleert werden. Dadurch wird sichergestellt, dass der Zeitaufwand für die Wiederherstellung innerhalb der Zielwiederherstellungszeit der Datenbank liegt.</span><span class="sxs-lookup"><span data-stu-id="aa686-113">When indirect checkpoints are enabled on a database receiving a large number of DML operations, the background writer can start aggressively flushing dirty buffers to disk to ensure that the time required to perform recovery is within the target recovery time set of the database.</span></span> <span data-ttu-id="aa686-114">Dies kann auf bestimmten Systemen zusätzliche E/A-Aktivitäten verursachen, die zu einem Leistungsengpass beitragen können, wenn das Datenträgersubsystem über oder nahe dem E/A-Schwellenwert arbeitet.</span><span class="sxs-lookup"><span data-stu-id="aa686-114">This can cause additional I/O activity on certain systems which can contribute to a performance bottleneck if the disk subsystem is operating above or nearing the I/O threshold.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="aa686-115">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="aa686-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="aa686-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="aa686-116">Permissions</span></span>  
 <span data-ttu-id="aa686-117">Erfordert die ALTER-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="aa686-117">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="aa686-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="aa686-118">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="aa686-119">**So ändern Sie die Zielwiederherstellungszeit**</span><span class="sxs-lookup"><span data-stu-id="aa686-119">**To change the target recovery time**</span></span>  
  
1.  <span data-ttu-id="aa686-120">Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]her, und erweitern Sie diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="aa686-120">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and expand that instance.</span></span>  
  
2.  <span data-ttu-id="aa686-121">Klicken Sie mit der rechten Maustaste auf die Datenbank, die geändert werden soll, und klicken Sie auf den Befehl **Eigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="aa686-121">Right-click the database you want to change, and click the **Properties** command.</span></span>  
  
3.  <span data-ttu-id="aa686-122">Klicken Sie im Dialogfeld **Datenbankeigenschaften** auf die Seite **Optionen** .</span><span class="sxs-lookup"><span data-stu-id="aa686-122">In the **Database Properties** dialog box, click the **Options** page.</span></span>  
  
4.  <span data-ttu-id="aa686-123">Geben Sie im Bereich **Wiederherstellung** im Feld **Zielwiederherstellungszeit (Sekunden)** die Anzahl von Sekunden als gewünschte Obergrenze der Wiederherstellungszeit für diese Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="aa686-123">In the **Recovery** panel, in the **Target Recovery Time (Seconds)** field, specify the number of seconds that you want as the upper-bound on the recovery time for this database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="aa686-124">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="aa686-124">Using Transact-SQL</span></span>  
 <span data-ttu-id="aa686-125">**So ändern Sie die Zielwiederherstellungszeit**</span><span class="sxs-lookup"><span data-stu-id="aa686-125">**To change the target recovery time**</span></span>  
  
1.  <span data-ttu-id="aa686-126">Stellen Sie eine Verbindung mit der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] her, auf der sich die Datenbank befindet.</span><span class="sxs-lookup"><span data-stu-id="aa686-126">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where the database resides.</span></span>  
  
2.  <span data-ttu-id="aa686-127">Verwenden Sie die folgende [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options)-Anweisung wie folgt:</span><span class="sxs-lookup"><span data-stu-id="aa686-127">Use the following [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-options)statement, as follows:</span></span>  
  
     <span data-ttu-id="aa686-128">TARGET_RECOVERY_TIME **=** _target_recovery_time_ { SECONDS | MINUTES }</span><span class="sxs-lookup"><span data-stu-id="aa686-128">TARGET_RECOVERY_TIME **=**_target_recovery_time_ { SECONDS | MINUTES }</span></span>  
  
     <span data-ttu-id="aa686-129">*target_recovery_time*</span><span class="sxs-lookup"><span data-stu-id="aa686-129">*target_recovery_time*</span></span>  
     <span data-ttu-id="aa686-130">Gibt bei einem Wert von größer 0 (Standardwert) die Obergrenze der Wiederherstellungszeit für die angegebene Datenbank im Fall eines Absturzes an.</span><span class="sxs-lookup"><span data-stu-id="aa686-130">When greater than 0 (the default), specifies the upper-bound on the recovery time for the specified database in the event of a crash.</span></span>  
  
     <span data-ttu-id="aa686-131">SECONDS</span><span class="sxs-lookup"><span data-stu-id="aa686-131">SECONDS</span></span>  
     <span data-ttu-id="aa686-132">Gibt an, dass *target_recovery_time* die Anzahl von Sekunden darstellt.</span><span class="sxs-lookup"><span data-stu-id="aa686-132">Indicates that *target_recovery_time* is expressed as the number of seconds.</span></span>  
  
     <span data-ttu-id="aa686-133">MINUTES</span><span class="sxs-lookup"><span data-stu-id="aa686-133">MINUTES</span></span>  
     <span data-ttu-id="aa686-134">Gibt an, dass *target_recovery_time* die Anzahl von Minuten darstellt.</span><span class="sxs-lookup"><span data-stu-id="aa686-134">Indicates that *target_recovery_time* is expressed as the number of minutes.</span></span>  
  
     <span data-ttu-id="aa686-135">Im folgenden Beispiel wird die Zielwiederherstellungszeit der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank auf `60` Sekunden festgelegt.</span><span class="sxs-lookup"><span data-stu-id="aa686-135">The following example sets the target recovery time of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database to `60` seconds.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET TARGET_RECOVERY_TIME = 60 SECONDS;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="aa686-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa686-136">See Also</span></span>  
 <span data-ttu-id="aa686-137">[Datenbankprüfpunkte &#40;SQL Server&#41;](database-checkpoints-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="aa686-137">[Database Checkpoints &#40;SQL Server&#41;](database-checkpoints-sql-server.md) </span></span>  
 [<span data-ttu-id="aa686-138">ALTER DATABASE SET-Optionen &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="aa686-138">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-set-options)  
  
  
