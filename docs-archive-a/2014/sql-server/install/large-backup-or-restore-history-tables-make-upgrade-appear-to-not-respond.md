---
title: Die Verlaufs Tabellen für große Sicherungen oder Wiederherstellungen lassen das Upgrade scheinbar nicht Antworten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- backup history tables
- history tables
ms.assetid: f88d86ec-324b-4518-b6d7-1af7e7265812
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 918c20f58c00c535d8ed41d887e9671f5e821a17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609024"
---
# <a name="large-backup-or-restore-history-tables-make-upgrade-appear-to-not-respond"></a><span data-ttu-id="3b8b9-102">Das Upgrade reagiert bei Verlaufstabellen für große Sicherungen oder Wiederherstellungen anscheinend nicht mehr</span><span class="sxs-lookup"><span data-stu-id="3b8b9-102">Large backup or restore history tables make upgrade appear to not respond</span></span>
  <span data-ttu-id="3b8b9-103">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] wurden einigen Verlaufstabellen für Sicherungen und Wiederherstellungen neue Spalten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3b8b9-103">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], new columns were added to some of the backup and restore history tables.</span></span> <span data-ttu-id="3b8b9-104">Zum Aktualisieren dieser Tabellen müssen die neuen Spalten hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="3b8b9-104">Upgrading these tables requires altering them to add the new columns.</span></span> <span data-ttu-id="3b8b9-105">Wenn mindestens eine dieser Tabellen viele Zeilen enthält, steht das Upgrade bei der ALTER TABLE-Anweisung, die der Tabelle Spalten hinzufügt, über einen langen Zeitraum still.</span><span class="sxs-lookup"><span data-stu-id="3b8b9-105">If one or more of these tables contains a large number of rows, the upgrade will stall for a substantial amount of time on the ALTER TABLE statement that adds columns to that table.</span></span>  
  
## <a name="component"></a><span data-ttu-id="3b8b9-106">Komponente</span><span class="sxs-lookup"><span data-stu-id="3b8b9-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="3b8b9-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3b8b9-107">Description</span></span>  
 <span data-ttu-id="3b8b9-108">Das Upgrade kann anscheinend nicht mehr reagieren, wenn eine der folgenden Sicherungs-oder Wiederherstellungs Verlaufs Tabellen eine große Anzahl von Zeilen enthält:</span><span class="sxs-lookup"><span data-stu-id="3b8b9-108">Upgrade can appear to stop responding if any of the following backup or restore history tables contains a large number of rows:</span></span>  
  
-   <span data-ttu-id="3b8b9-109">**backupfile**</span><span class="sxs-lookup"><span data-stu-id="3b8b9-109">**backupfile**</span></span>  
  
-   <span data-ttu-id="3b8b9-110">**backupmediafamily**</span><span class="sxs-lookup"><span data-stu-id="3b8b9-110">**backupmediafamily**</span></span>  
  
-   <span data-ttu-id="3b8b9-111">**backupmediaset**</span><span class="sxs-lookup"><span data-stu-id="3b8b9-111">**backupmediaset**</span></span>  
  
-   <span data-ttu-id="3b8b9-112">**backupset**</span><span class="sxs-lookup"><span data-stu-id="3b8b9-112">**backupset**</span></span>  
  
-   <span data-ttu-id="3b8b9-113">**restorefile**</span><span class="sxs-lookup"><span data-stu-id="3b8b9-113">**restorefile**</span></span>  
  
-   <span data-ttu-id="3b8b9-114">**restorefilegroup**</span><span class="sxs-lookup"><span data-stu-id="3b8b9-114">**restorefilegroup**</span></span>  
  
-   <span data-ttu-id="3b8b9-115">**restorehistory**</span><span class="sxs-lookup"><span data-stu-id="3b8b9-115">**restorehistory**</span></span>  
  
 <span data-ttu-id="3b8b9-116">Wenn eine dieser Tabellen 10.000 oder mehr Zeilen hat, meldet der Upgrade Advisor einen Nichtkompatibilitätsfehler.</span><span class="sxs-lookup"><span data-stu-id="3b8b9-116">If any of these tables has 10,000 or more rows, Upgrade Advisor reports a noncompliance failure.</span></span> <span data-ttu-id="3b8b9-117">Er gibt nicht an, welche Tabelle die zulässige Anzahl an Zeilen übersteigt.</span><span class="sxs-lookup"><span data-stu-id="3b8b9-117">It does not report which table exceeds the allowed number of rows.</span></span> <span data-ttu-id="3b8b9-118">Die erste Tabelle, die 10.000 Zeilen übersteigt, verursacht den Fehler.</span><span class="sxs-lookup"><span data-stu-id="3b8b9-118">The first table that exceeds 10,000 rows causes the failure.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="3b8b9-119">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="3b8b9-119">Corrective Action</span></span>  
 <span data-ttu-id="3b8b9-120">Es empfiehlt sich vor dem Upgrade einer Datenbank, die Anzahl der Zeilen auf unter 10.000 zu reduzieren, falls eine der Tabellen mehr als 10.000 Zeilen besitzt.</span><span class="sxs-lookup"><span data-stu-id="3b8b9-120">Before you upgrade a database, if any of these tables exceeds 10,000 rows, we recommend that you reduce the number to less than 10,000.</span></span> <span data-ttu-id="3b8b9-121">Um Zeilen in allen diesen Tabellen zu reduzieren, können Sie die gespeicherte Prozedur **sp_delete_backuphistory** ausführen.</span><span class="sxs-lookup"><span data-stu-id="3b8b9-121">To reduce rows in all of these tables, you can run the **sp_delete_backuphistory** stored procedure.</span></span> <span data-ttu-id="3b8b9-122">Diese Prozedur löscht die Einträge in allen Verlaufstabellen für Sicherungen und Wiederherstellungen der Sicherungssätze, die älter sind als das angegebene Datum.</span><span class="sxs-lookup"><span data-stu-id="3b8b9-122">This procedure deletes the entries in all of the backup and restore history tables for backup sets older than a specified date.</span></span> <span data-ttu-id="3b8b9-123">Weitere Informationen finden Sie unter [sp_delete_backuphistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3b8b9-123">For more information, see [sp_delete_backuphistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3b8b9-124">Sie können eine Datenbank aktualisieren, deren Verlaufstabellen für Sicherungen und Wiederherstellungen mehr als 10.000 Zeilen besitzen.</span><span class="sxs-lookup"><span data-stu-id="3b8b9-124">You can upgrade a database whose backup and restore history tables are larger than 10,000 rows.</span></span> <span data-ttu-id="3b8b9-125">Beim Ändern großer Tabellen entsteht jedoch der Eindruck, dass das Upgrade still steht.</span><span class="sxs-lookup"><span data-stu-id="3b8b9-125">But the upgrade may appear to stall while large tables are being altered.</span></span> <span data-ttu-id="3b8b9-126">Je größer die Tabellen sind, um so länger dauert das Setup.</span><span class="sxs-lookup"><span data-stu-id="3b8b9-126">The larger the tables, the longer that Setup takes to complete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b8b9-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3b8b9-127">See Also</span></span>  
 <span data-ttu-id="3b8b9-128">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="3b8b9-128">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="3b8b9-129">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="3b8b9-129">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
