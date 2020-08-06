---
title: Datenbank verkleinern (Task) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.shrinkdatabasetask.f1
helpviewer_keywords:
- Shrink Database task
- database shrinking [Integration Services]
- shrinking databases
ms.assetid: e66286f8-97b1-4e5a-86b4-e56f1932b7d5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 587777928e362e87e4b691e3c46167c1239984cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621128"
---
# <a name="shrink-database-task"></a><span data-ttu-id="de9b9-102">Datenbank verkleinern (Task)</span><span class="sxs-lookup"><span data-stu-id="de9b9-102">Shrink Database Task</span></span>
  <span data-ttu-id="de9b9-103">Der Task &lt;ui&gt;Datenbank verkleinern&lt;/ui&gt; reduziert die Größe von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbankdaten und -Protokolldateien.</span><span class="sxs-lookup"><span data-stu-id="de9b9-103">The Shrink Database task reduces the size of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database data and log files.</span></span>  
  
 <span data-ttu-id="de9b9-104">Mithilfe des Tasks <ui>Datenbank verkleinern</ui> kann ein Paket Dateien für eine einzelne oder mehrere Datenbanken verkleinern.</span><span class="sxs-lookup"><span data-stu-id="de9b9-104">By using the Shrink Database task, a package can shrink files for a single database or multiple databases.</span></span>  
  
 <span data-ttu-id="de9b9-105">Mit dem Verkleinern von Datendateien wird Platz gewonnen, indem Datenseiten vom Ende der Datei an nicht belegten Platz weiter am Dateianfang verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="de9b9-105">Shrinking data files recovers space by moving pages of data from the end of the file to unoccupied space closer to the front of the file.</span></span> <span data-ttu-id="de9b9-106">Wurde am Ende der Datei ausreichend Platz geschaffen, kann die Zuordnung der Datenseiten am Ende der Datei aufgehoben und die Datenseiten können ins Dateisystem zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="de9b9-106">When enough free space is created at the end of the file, data pages at end of the file can deallocated and returned to the file system.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="de9b9-107">Die zum Verkleinern einer Datei verschobenen Daten können an beliebigen freien Platz in der Datei verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="de9b9-107">Data that is moved to shrink a file can be scattered to any available location in the file.</span></span> <span data-ttu-id="de9b9-108">Dies führt zur Indexfragmentierung und kann die Leistung von Abfragen, die einen Bereich des Indexes suchen, verlangsamen.</span><span class="sxs-lookup"><span data-stu-id="de9b9-108">This causes index fragmentation and can slow the performance of queries that search a range of the index.</span></span> <span data-ttu-id="de9b9-109">Zur Vermeidung von Fragmentierung sollten die Dateiindizes nach der Verkleinerung neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="de9b9-109">To eliminate the fragmentation, consider rebuilding the indexes on the file after shrinking.</span></span>  
  
## <a name="commands"></a><span data-ttu-id="de9b9-110">Befehle</span><span class="sxs-lookup"><span data-stu-id="de9b9-110">Commands</span></span>  
 <span data-ttu-id="de9b9-111">Dieser Task kapselt eine DBCC SHRINKDATABASE-Anweisung, einschließlich der folgenden Argumente und Optionen:</span><span class="sxs-lookup"><span data-stu-id="de9b9-111">The Shrink Database task encapsulates a DBCC SHRINKDATABASE command, including the following arguments and options:</span></span>  
  
-   <span data-ttu-id="de9b9-112">*database_name*</span><span class="sxs-lookup"><span data-stu-id="de9b9-112">*database_name*</span></span>  
  
-   <span data-ttu-id="de9b9-113">*target_percent*</span><span class="sxs-lookup"><span data-stu-id="de9b9-113">*target_percent*</span></span>  
  
-   <span data-ttu-id="de9b9-114">NOTRUNCATE oder TRUNCATEONLY.</span><span class="sxs-lookup"><span data-stu-id="de9b9-114">NOTRUNCATE or TRUNCATEONLY.</span></span>  
  
 <span data-ttu-id="de9b9-115">Wenn der Task Datenbank verkleinern mehrere Datenbanken verkleinert, führt der Task mehrere SHRINKDATABASE-Befehle aus, und zwar einen Befehl pro Datenbank.</span><span class="sxs-lookup"><span data-stu-id="de9b9-115">If the Shrink Database task shrinks multiple databases, the task runs multiple SHRINKDATABASE commands, one for each database.</span></span> <span data-ttu-id="de9b9-116">Alle Instanzen des SHRINKDATABASE-Befehls verwenden die gleichen Argumentwerte; dies gilt nicht für das Argument *database_name* .</span><span class="sxs-lookup"><span data-stu-id="de9b9-116">All instances of the SHRINKDATABASE command use the same argument values, except for the *database_name* argument.</span></span> <span data-ttu-id="de9b9-117">Weitere Informationen finden Sie unter [DBCC SHRINKDATABASE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="de9b9-117">For more information, see [DBCC SHRINKDATABASE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-shrinkdatabase-transact-sql).</span></span>  
  
## <a name="configuration-of-the-shrink-database-task"></a><span data-ttu-id="de9b9-118">Konfiguration des Tasks "Datenbank verkleinern"</span><span class="sxs-lookup"><span data-stu-id="de9b9-118">Configuration of the Shrink Database Task</span></span>  
 <span data-ttu-id="de9b9-119">Eigenschaften können Sie mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer festlegen.</span><span class="sxs-lookup"><span data-stu-id="de9b9-119">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="de9b9-120">Dieser Task ist im **-Designer in der** Toolbox **im Abschnitt** Wartungsplantasks [!INCLUDE[ssIS](../../../includes/ssis-md.md)] enthalten.</span><span class="sxs-lookup"><span data-stu-id="de9b9-120">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="de9b9-121">Klicken Sie auf das folgende Thema, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer festlegen können:</span><span class="sxs-lookup"><span data-stu-id="de9b9-121">For more information about the properties that you can set in the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="de9b9-122">Task „Datenbank verkleinern“ &#40;Wartungsplan&#41;</span><span class="sxs-lookup"><span data-stu-id="de9b9-122">Shrink Database Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/shrink-database-task-maintenance-plan.md)  
  
 <span data-ttu-id="de9b9-123">Klicken Sie auf das folgende Thema, um weitere Informationen zum Festlegen dieser Eigenschaften im [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="de9b9-123">For more information about setting these properties in the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="de9b9-124">Festlegen der Eigenschaften eines Tasks oder Containers</span><span class="sxs-lookup"><span data-stu-id="de9b9-124">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
  
