---
title: Sichern und Wiederherstellen von DQS-Datenbanken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: f3091f62-2234-4a80-a615-cf14c2a1da85
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 489664d8c64a99d1ea4dcec79b93e5b01b28f649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609473"
---
# <a name="backing-up-and-restoring-dqs-databases"></a><span data-ttu-id="64f68-102">Sichern und Wiederherstellen von DQS-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="64f68-102">Backing Up and Restoring DQS Databases</span></span>
  <span data-ttu-id="64f68-103">In diesem Thema wird beschrieben, wie die DQS-Datenbanken gesichert und wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="64f68-103">This topic describes how to back up and restore the DQS databases.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="64f68-104">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="64f68-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="64f68-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="64f68-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="64f68-106">Sie müssen das Kennwort für den Datenbank-Hauptschlüssel kennen, das Sie während der DQS-Serverinstallation angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="64f68-106">You must know or remember the password for the database master key that you provided during the DQS server installation.</span></span>  
  
-   <span data-ttu-id="64f68-107">Stellen Sie sicher, dass in DQS keine Aktivitäten oder Prozesse ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="64f68-107">Ensure that there are no running activities or processes in DQS.</span></span> <span data-ttu-id="64f68-108">Dies kann mithilfe des Bildschirms **Aktivitätsüberwachung** überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="64f68-108">This can be verified using the **Activity Monitoring** screen.</span></span> <span data-ttu-id="64f68-109">Weitere Informationen zum Verwenden dieses Bildschirms finden Sie unter [Monitor DQS Activities](../../2014/data-quality-services/monitor-dqs-activities.md).</span><span class="sxs-lookup"><span data-stu-id="64f68-109">For detailed information about working in this screen, see [Monitor DQS Activities](../../2014/data-quality-services/monitor-dqs-activities.md).</span></span>  
  
-   <span data-ttu-id="64f68-110">Stellen Sie sicher, dass keine Benutzer am DQS-Server angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="64f68-110">Ensure that there are no users logged on the DQS server.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="64f68-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="64f68-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="64f68-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="64f68-112">Permissions</span></span>  
  
-   <span data-ttu-id="64f68-113">Das Windows-Benutzerkonto muss ein Mitglied der festen sysadmin-Serverrolle in der SQL Server-Instanz sein, um die Sicherungs- und Wiederherstellungsvorgänge auszuführen.</span><span class="sxs-lookup"><span data-stu-id="64f68-113">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance to perform the backup and restore operations.</span></span>  
  
-   <span data-ttu-id="64f68-114">Sie müssen über die Rolle „dqs_administrator“ in der DQS_MAIN-Datenbank verfügen, um ausgeführte Aktivitäten abzubrechen oder ausgeführte Prozesse in DQS anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="64f68-114">You must have the dqs_administrator role on the DQS_MAIN database to terminate any running activities or stop any running processes in DQS.</span></span>  
  
##  <a name="backup-and-restore-dqs-databases"></a><a name="BackupRestore"></a><span data-ttu-id="64f68-115">Sichern und Wiederherstellen von DQS-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="64f68-115">Backup and Restore DQS Databases</span></span>  
  
1.  <span data-ttu-id="64f68-116">Starten Sie Microsoft SQL Server Management Studio, und stellen Sie eine Verbindung mit der entsprechenden SQL Server-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="64f68-116">Start Microsoft SQL Server Management Studio, and connect to the appropriate SQL Server instance.</span></span>  
  
2.  <span data-ttu-id="64f68-117">Erweitern Sie im Objekt-Explorer den Knoten **Datenbanken** .</span><span class="sxs-lookup"><span data-stu-id="64f68-117">In Object Explorer, expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="64f68-118">Sichern Sie die DQS_STAGING_DATA-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="64f68-118">Back up the DQS_STAGING_DATA database.</span></span> <span data-ttu-id="64f68-119">Ausführliche Anweisungen zum Sichern einer SQL Server-Datenbank finden Sie unter [Erstellen einer vollständigen Datenbanksicherung &#40;SQL Server&#41;](../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="64f68-119">For step-by-step instructions for backing a SQL Server database, see [Create a Full Database Backup &#40;SQL Server&#41;](../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md).</span></span>  
  
4.  <span data-ttu-id="64f68-120">Sichern Sie die DQS_PROJECTS-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="64f68-120">Back up the DQS_PROJECTS database.</span></span>  
  
5.  <span data-ttu-id="64f68-121">Sichern Sie die DQS_MAIN-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="64f68-121">Back up the DQS_MAIN database.</span></span>  
  
6.  <span data-ttu-id="64f68-122">Trennen Sie die Verbindung mit der aktuellen Instanz von SQL Server, und stellen Sie eine Verbindung mit der SQL Server-Instanz her, auf der Sie diese Datenbanken wiederherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="64f68-122">Disconnect from the current instance of SQL Server, and connect to the SQL Server instance where you want to restore these databases.</span></span>  
  
7.  <span data-ttu-id="64f68-123">Stellen Sie die DQS_MAIN-Datenbank wieder her.</span><span class="sxs-lookup"><span data-stu-id="64f68-123">Restore DQS_MAIN database.</span></span> <span data-ttu-id="64f68-124">Schritt-für-Schritt-Anweisungen zum Wiederherstellen einer SQL Server Datenbank finden Sie unter [Wiederherstellen einer Datenbanksicherung &#40;SQL Server Management Studio&#41;](../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="64f68-124">For step-by-step instructions to restore a SQL Server database, see [Restore a Database Backup &#40;SQL Server Management Studio&#41;](../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md).</span></span>  
  
8.  <span data-ttu-id="64f68-125">Stellen Sie die DQS_PROJECTS-Datenbank wieder her.</span><span class="sxs-lookup"><span data-stu-id="64f68-125">Restore the DQS_PROJECTS database.</span></span>  
  
9. <span data-ttu-id="64f68-126">Stellen Sie die DQS_STAGING_DATA-Datenbank wieder her.</span><span class="sxs-lookup"><span data-stu-id="64f68-126">Restore the DQS_STAGING_DATA database.</span></span>  
  
10. <span data-ttu-id="64f68-127">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf den Server, und klicken Sie dann auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="64f68-127">In Object Explorer, right-click the server, and then click **New Query**.</span></span>  
  
11. <span data-ttu-id="64f68-128">Kopieren Sie im Abfrage-Editor-Fenster die folgenden SQL-Anweisungen, und ersetzen *\<PASSWORD>* Sie durch das Kennwort, das Sie während der DQS-Installation für den Datenbank-Hauptschlüssel angegeben haben:</span><span class="sxs-lookup"><span data-stu-id="64f68-128">In the Query Editor window, copy the following SQL statements, and replace *\<PASSWORD>* with the password that you provided during the DQS installation for the database master key:</span></span>  
  
    ```sql  
    USE [DQS_MAIN]  
    GO  
    EXECUTE [internal_core].[RestoreDQDatabases] '<PASSWORD>'  
    GO  
    ```  
  
12. <span data-ttu-id="64f68-129">Drücken Sie F5, um die Anweisungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="64f68-129">Press F5 to execute the statements.</span></span> <span data-ttu-id="64f68-130">Überprüfen Sie im **Ergebnis** Bereich, ob die Anweisungen erfolgreich ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="64f68-130">Check the **Results** pane to verify that the statements have executed successfully.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64f68-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="64f68-131">See Also</span></span>  
 [<span data-ttu-id="64f68-132">Manage DQS Databases</span><span class="sxs-lookup"><span data-stu-id="64f68-132">Manage DQS Databases</span></span>](../../2014/data-quality-services/manage-dqs-databases.md)  
  
  
