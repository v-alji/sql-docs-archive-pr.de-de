---
title: Datenbank sichern (Task) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.backupdatabasetask.f1
helpviewer_keywords:
- database backups [Integration Services]
- Back Up Database task [Integration Services]
- backing up databases [Integration Services]
- transaction log backups [Integration Services]
- backing up transaction logs [Integration Services]
ms.assetid: b8839d71-13b7-41f2-a434-cb95020e79d7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b0980d89cc915121414dd7d3c89be6f4d72eb715
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615504"
---
# <a name="back-up-database-task"></a><span data-ttu-id="e3a7e-102">Datenbank sichern (Task)</span><span class="sxs-lookup"><span data-stu-id="e3a7e-102">Back Up Database Task</span></span>
  <span data-ttu-id="e3a7e-103">Der Task Datenbank sichern führt verschiedene Arten von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanksicherungen aus.</span><span class="sxs-lookup"><span data-stu-id="e3a7e-103">The Back Up Database task performs different types of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database backups.</span></span> <span data-ttu-id="e3a7e-104">Weitere Informationen finden Sie unter [Sichern und Wiederherstellen von SQL Server-Datenbanken](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span><span class="sxs-lookup"><span data-stu-id="e3a7e-104">For more information, see [Back Up and Restore of SQL Server Databases](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span></span>  
  
 <span data-ttu-id="e3a7e-105">Mithilfe des Tasks Datenbank sichern kann ein Paket eine einzelne Datenbank oder mehrere Datenbanken sichern.</span><span class="sxs-lookup"><span data-stu-id="e3a7e-105">By using the Back Up Database task, a package can back up a single database or multiple databases.</span></span> <span data-ttu-id="e3a7e-106">Wenn mit dem Task nur eine einzelne Datenbank gesichert wird, können Sie die Sicherungskomponente auswählen: die Datenbank, oder ihre Dateien und Dateigruppen.</span><span class="sxs-lookup"><span data-stu-id="e3a7e-106">If the task backs up only a single database, you can choose the backup component: the database, or its files and filegroups.</span></span>  
  
## <a name="supported-recover-models-and-backup-types"></a><span data-ttu-id="e3a7e-107">Unterstützte Wiederherstellungsmodelle und Sicherungstypen</span><span class="sxs-lookup"><span data-stu-id="e3a7e-107">Supported Recover Models and Backup Types</span></span>  
 <span data-ttu-id="e3a7e-108">In der folgenden Tabelle sind die Wiederherstellungsmodelle und Sicherungstypen aufgeführt, die vom Task Datenbank sichern unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="e3a7e-108">The following table lists the recovery models and backup types that the Back Up Database task supports.</span></span>  
  
|<span data-ttu-id="e3a7e-109">Wiederherstellungsmodell</span><span class="sxs-lookup"><span data-stu-id="e3a7e-109">Recovery model</span></span>|<span data-ttu-id="e3a7e-110">Datenbank</span><span class="sxs-lookup"><span data-stu-id="e3a7e-110">Database</span></span>|<span data-ttu-id="e3a7e-111">Datenbank - differenziell</span><span class="sxs-lookup"><span data-stu-id="e3a7e-111">Database differential</span></span>|<span data-ttu-id="e3a7e-112">Transaktionsprotokoll</span><span class="sxs-lookup"><span data-stu-id="e3a7e-112">Transaction log</span></span>|<span data-ttu-id="e3a7e-113">Datei oder differenzielle Datei</span><span class="sxs-lookup"><span data-stu-id="e3a7e-113">File or file differential</span></span>|  
|--------------------|--------------|---------------------------|---------------------|-------------------------------|  
|<span data-ttu-id="e3a7e-114">Einfach</span><span class="sxs-lookup"><span data-stu-id="e3a7e-114">Simple</span></span>|<span data-ttu-id="e3a7e-115">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="e3a7e-115">Required</span></span>|<span data-ttu-id="e3a7e-116">Optional</span><span class="sxs-lookup"><span data-stu-id="e3a7e-116">Optional</span></span>|<span data-ttu-id="e3a7e-117">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="e3a7e-117">Not supported</span></span>|<span data-ttu-id="e3a7e-118">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="e3a7e-118">Not supported</span></span>|  
|<span data-ttu-id="e3a7e-119">Vollständig</span><span class="sxs-lookup"><span data-stu-id="e3a7e-119">Full</span></span>|<span data-ttu-id="e3a7e-120">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="e3a7e-120">Required</span></span>|<span data-ttu-id="e3a7e-121">Optional</span><span class="sxs-lookup"><span data-stu-id="e3a7e-121">Optional</span></span>|<span data-ttu-id="e3a7e-122">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="e3a7e-122">Required</span></span>|<span data-ttu-id="e3a7e-123">Optional</span><span class="sxs-lookup"><span data-stu-id="e3a7e-123">Optional</span></span>|  
|<span data-ttu-id="e3a7e-124">Massenprotokolliert</span><span class="sxs-lookup"><span data-stu-id="e3a7e-124">Bulk-logged</span></span>|<span data-ttu-id="e3a7e-125">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="e3a7e-125">Required</span></span>|<span data-ttu-id="e3a7e-126">Optional</span><span class="sxs-lookup"><span data-stu-id="e3a7e-126">Optional</span></span>|<span data-ttu-id="e3a7e-127">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="e3a7e-127">Required</span></span>|<span data-ttu-id="e3a7e-128">Optional</span><span class="sxs-lookup"><span data-stu-id="e3a7e-128">Optional</span></span>|  
  
 <span data-ttu-id="e3a7e-129">Der Task Datenbank sichern kapselt eine BACKUP-Anweisung von Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="e3a7e-129">The Back Up Database task encapsulates a Transact-SQL BACKUP statement.</span></span> <span data-ttu-id="e3a7e-130">Weitere Informationen finden Sie unter [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e3a7e-130">For more information, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>  
  
## <a name="configuration-of-the-back-up-database-task"></a><span data-ttu-id="e3a7e-131">Konfiguration des Tasks "Datenbank sichern"</span><span class="sxs-lookup"><span data-stu-id="e3a7e-131">Configuration of the Back Up Database Task</span></span>  
 <span data-ttu-id="e3a7e-132">Eigenschaften können Sie mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer festlegen.</span><span class="sxs-lookup"><span data-stu-id="e3a7e-132">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="e3a7e-133">Dieser Task ist im **-Designer in der** Toolbox **im Abschnitt** Wartungsplantasks [!INCLUDE[ssIS](../../../includes/ssis-md.md)] enthalten.</span><span class="sxs-lookup"><span data-stu-id="e3a7e-133">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="e3a7e-134">Klicken Sie auf das folgende Thema, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer festlegen können:</span><span class="sxs-lookup"><span data-stu-id="e3a7e-134">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="e3a7e-135">Task „Datenbank sichern“ &#40;Wartungsplan&#41;</span><span class="sxs-lookup"><span data-stu-id="e3a7e-135">Back Up Database Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/options-in-the-back-up-database-task-for-maintenance-plan.md)  
  
 <span data-ttu-id="e3a7e-136">Klicken Sie auf das folgende Thema, um weitere Informationen zum Festlegen dieser Eigenschaften im [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="e3a7e-136">For more information about how to set these properties in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="e3a7e-137">Festlegen der Eigenschaften eines Tasks oder Containers</span><span class="sxs-lookup"><span data-stu-id="e3a7e-137">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
  
