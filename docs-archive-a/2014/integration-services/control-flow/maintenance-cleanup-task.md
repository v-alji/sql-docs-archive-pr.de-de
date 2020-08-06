---
title: Wartungscleanup (Task) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.maintenancecleanuptask.f1
helpviewer_keywords:
- deleting files
- removing files
- Maintenance Cleanup task
ms.assetid: 73ad3cd6-9a6d-44cf-905f-c56aa658bf42
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4d39dd775402adadbe51eaadc530f4feb288ab9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616617"
---
# <a name="maintenance-cleanup-task"></a><span data-ttu-id="f0355-102">Wartungscleanup (Task)</span><span class="sxs-lookup"><span data-stu-id="f0355-102">Maintenance Cleanup Task</span></span>
  <span data-ttu-id="f0355-103">Mit dem Task Wartungscleanup werden Dateien entfernt, die mit Wartungsplänen verbunden sind, einschließlich Datenbanksicherungsdateien und Berichte, die von Wartungsplänen erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="f0355-103">The Maintenance Cleanup task removes files related to maintenance plans, including database backup files and reports created by maintenance plans.</span></span> <span data-ttu-id="f0355-104">Weitere Informationen finden Sie unter [Wartungspläne](../../relational-databases/maintenance-plans/maintenance-plans.md) und [Sichern und Wiederherstellen von SQL Server-Datenbanken](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span><span class="sxs-lookup"><span data-stu-id="f0355-104">For more information, see [Maintenance Plans](../../relational-databases/maintenance-plans/maintenance-plans.md) and [Back Up and Restore of SQL Server Databases](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span></span>  
  
 <span data-ttu-id="f0355-105">Ein Paket kann mithilfe des Tasks Wartungscleanup die Sicherungsdateien oder Wartungsplanberichte auf dem angegebenen Server entfernen.</span><span class="sxs-lookup"><span data-stu-id="f0355-105">By using the Maintenance Cleanup task, a package can remove the backup files or maintenance plan reports on the specified server.</span></span> <span data-ttu-id="f0355-106">Der Task Wartungscleanup schließt eine Option zum Entfernen einer bestimmten Datei bzw. einer Gruppe von Dateien eines Ordners ein.</span><span class="sxs-lookup"><span data-stu-id="f0355-106">The Maintenance Cleanup task includes an option to remove a specific file or remove a group of files in a folder.</span></span> <span data-ttu-id="f0355-107">Optional können Sie die Erweiterung der zu löschenden Dateien angeben.</span><span class="sxs-lookup"><span data-stu-id="f0355-107">Optionally you can specify the extension of the files to delete.</span></span>  
  
 <span data-ttu-id="f0355-108">Wenn Sie den Task Wartungscleanup zum Entfernen von Sicherungsdateien konfigurieren, lautet die Standard-Dateinamenerweiterung BAK.</span><span class="sxs-lookup"><span data-stu-id="f0355-108">When you configure the Maintenance Cleanup task to remove backup files, the default file name extension is BAK.</span></span> <span data-ttu-id="f0355-109">Für Berichtsdateien lautet die Standard-Dateinamenerweiterung TXT.</span><span class="sxs-lookup"><span data-stu-id="f0355-109">For report files, the default file name extension is TXT.</span></span> <span data-ttu-id="f0355-110">Sie können die Erweiterungen nach Ihren Bedürfnissen aktualisieren. Als einzige Beschränkung gilt, dass Erweiterungen eine Länge von maximal 256 Zeichen aufweisen dürfen.</span><span class="sxs-lookup"><span data-stu-id="f0355-110">You can update the extensions to suit your needs; the only limitation is that extensions must be less than 256 characters long.</span></span>  
  
 <span data-ttu-id="f0355-111">In der Regel werden alte Dateien, die nicht mehr benötigt werden, entfernt. Der Task Wartungscleanup kann so konfiguriert werden, dass sämtliche Dateien, die ein bestimmtes Alter erreicht haben, gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="f0355-111">Typically, you want to remove old files that are no longer needed, and the Maintenance Cleanup task can be configured to delete files that have reached a specified age.</span></span> <span data-ttu-id="f0355-112">Der Task kann beispielsweise zum Löschen von Dateien konfiguriert werden, die älter als vier Wochen sind.</span><span class="sxs-lookup"><span data-stu-id="f0355-112">For example, the task can be configured to delete files that are older than four weeks.</span></span> <span data-ttu-id="f0355-113">Sie können das Alter der zu löschenden Dateien angeben, indem Sie Tage, Wochen, Monate oder Jahre verwenden.</span><span class="sxs-lookup"><span data-stu-id="f0355-113">You can specify the age of files to delete by using days, weeks, months, or years.</span></span> <span data-ttu-id="f0355-114">Wenn Sie das Mindestalter der zu löschenden Dateien nicht angeben, werden alle Dateien des angegebenen Typs gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f0355-114">If you do not specify the minimum age of files to delete, all files of the specified type are deleted.</span></span>  
  
 <span data-ttu-id="f0355-115">Im Gegensatz zu früheren Versionen des Tasks Wartungscleanup löscht die Version des Tasks in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht automatisch Dateien in den Unterverzeichnissen des angegebenen Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="f0355-115">In contrast to earlier versions of the Maintenance Cleanup task, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version of the task does not automatically delete files in the subdirectories of the specified directory.</span></span> <span data-ttu-id="f0355-116">Diese Einschränkung verringert die Oberfläche eines Angriffs, der die Funktionalität des Tasks Wartungscleanup ausnutzen könnte, um Dateien in böswilliger Absicht zu löschen.</span><span class="sxs-lookup"><span data-stu-id="f0355-116">This constraint reduces the surface area of any attack that could exploit the functionality of the Maintenance Cleanup task to delete files maliciously.</span></span> <span data-ttu-id="f0355-117">Wenn Sie die Unterordner auf oberster Ebene löschen möchten, müssen Sie dies ausdrücklich durch Aktivieren der Option **Unterordner auf oberster Ebene einschließen** im Dialogfeld **Task "Wartungscleanup"** auswählen.</span><span class="sxs-lookup"><span data-stu-id="f0355-117">To delete the first-level subfolders, you must explicitly elect to do this by checking the **Include first-level subfolders** option in the **Maintenance Cleanup Task** dialog box.</span></span>  
  
## <a name="configuration-of-the-maintenance-cleanup-task"></a><span data-ttu-id="f0355-118">Konfiguration des Task "Wartungscleanup"</span><span class="sxs-lookup"><span data-stu-id="f0355-118">Configuration of the Maintenance Cleanup Task</span></span>  
 <span data-ttu-id="f0355-119">Eigenschaften können Sie mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen.</span><span class="sxs-lookup"><span data-stu-id="f0355-119">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="f0355-120">Dieser Task ist im **-Designer in der** Toolbox **im Abschnitt** Wartungsplantasks [!INCLUDE[ssIS](../../includes/ssis-md.md)] enthalten.</span><span class="sxs-lookup"><span data-stu-id="f0355-120">This task is in the **Maintenance Plan Tasks** section of the **Toolbox** in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="f0355-121">Klicken Sie auf das folgende Thema, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können:</span><span class="sxs-lookup"><span data-stu-id="f0355-121">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="f0355-122">Task „Wartungscleanup“ &#40;Wartungsplan&#41;</span><span class="sxs-lookup"><span data-stu-id="f0355-122">Maintenance Cleanup Task &#40;Maintenance Plan&#41;</span></span>](../../relational-databases/maintenance-plans/maintenance-cleanup-task-maintenance-plan.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="f0355-123">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="f0355-123">Related Tasks</span></span>  
 <span data-ttu-id="f0355-124">Informationen zum Festlegen dieser Eigenschaften im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer finden Sie unter [Festlegen der Eigenschaften eines Tasks oder Containers](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="f0355-124">For details about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0355-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0355-125">See Also</span></span>  
 <span data-ttu-id="f0355-126">[Integration Services-Tasks](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="f0355-126">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="f0355-127">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="f0355-127">Control Flow</span></span>](control-flow.md)  
  
  
