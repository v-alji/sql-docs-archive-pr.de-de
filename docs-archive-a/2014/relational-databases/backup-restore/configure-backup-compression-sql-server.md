---
title: Konfigurieren von Sicherungskomprimierung (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 430905eb-d218-458c-bd48-aeee6fbb7446
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f70994eb64cb6a50b538fd87f03ce7ea2fafe857
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622717"
---
# <a name="configure-backup-compression-sql-server"></a><span data-ttu-id="02d64-102">Konfigurieren von Sicherungskomprimierung (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="02d64-102">Configure Backup Compression (SQL Server)</span></span>
  <span data-ttu-id="02d64-103">Die Sicherungskomprimierung wird bei der Installation standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="02d64-103">At installation, backup compression is off by default.</span></span> <span data-ttu-id="02d64-104">Das Standardverhalten für die Sicherungskomprimierung wird auf Serverebene durch die Konfigurationsoption **backup compression default** definiert.</span><span class="sxs-lookup"><span data-stu-id="02d64-104">The default behavior for backup compression is defined by the **backup compression default** Option server-level configuration option.</span></span> <span data-ttu-id="02d64-105">Sie können jedoch die Standardeinstellung auf Serverebene überschreiben, wenn Sie eine einzelne Sicherung erstellen oder eine Reihe von Routinesicherungen einplanen.</span><span class="sxs-lookup"><span data-stu-id="02d64-105">However, you can override the server-level default when creating a single backup or scheduling a series of routine backups.</span></span> <span data-ttu-id="02d64-106">Zum Ändern der Standardeinstellung auf Serverlevel gehen Sie unter [Anzeigen oder Konfigurieren der Serverkonfigurationsoption Standardeinstellung für die Sicherungskomprimierung](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="02d64-106">To change the server-level default, see [View or Configure the backup compression default Server Configuration Option](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span></span>  
  
## <a name="override-the-backup-compression-default"></a><span data-ttu-id="02d64-107">Überschreiben der Standardeinstellung für die Sicherungskomprimierung</span><span class="sxs-lookup"><span data-stu-id="02d64-107">Override the Backup Compression Default</span></span>  
 <span data-ttu-id="02d64-108">Sie können das Verhalten der Sicherungskomprimierung für eine einzelne Sicherung, einen Sicherungsauftrag oder eine Protokollversandkonfiguration ändern.</span><span class="sxs-lookup"><span data-stu-id="02d64-108">You can change the backup compression behavior for an individual backup, backup job, or log shipping configuration.</span></span>  
  
-   **[!INCLUDE[tsql](../../includes/tsql-md.md)]**  
  
     <span data-ttu-id="02d64-109">Verwenden Sie WITH NO_COMPRESSION oder WITH COMPRESSION in der [BACKUP](/sql/t-sql/statements/backup-transact-sql)-Anweisung, um die Standardeinstellung für die Serversicherungskomprimierung zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="02d64-109">To override the server backup-compression default when creating a backup, use either WITH NO_COMPRESSION or WITH COMPRESSION in you [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement.</span></span>  
  
     <span data-ttu-id="02d64-110">Bei einer Protokollversandkonfiguration können Sie das Verhalten der Sicherungskomprimierung für Protokollsicherungen mithilfe von [sp_add_log_shipping_primary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-database-transact-sql)[sp_change_log_shipping_primary_database &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-log-shipping-primary-database-transact-sql) steuern.</span><span class="sxs-lookup"><span data-stu-id="02d64-110">For a log shipping configuration, you can control the backup compression behavior of log backups by using [sp_add_log_shipping_primary_database](/sql/relational-databases/system-stored-procedures/sp-add-log-shipping-primary-database-transact-sql)[sp_change_log_shipping_primary_database &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-log-shipping-primary-database-transact-sql).</span></span>  
  
-   **[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**  
  
     <span data-ttu-id="02d64-111">Informationen zum Anzeigen oder Konfigurieren der Standardoption für die Sicherungskomprimierung für eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], gehen Sie unter [Anzeigen oder Konfigurieren der Serverkonfigurationsoption Standardeinstellung für die Sicherungskomprimierung](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="02d64-111">For information about how to view or configure the backup compression default option for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [View or Configure the backup compression default Server Configuration Option](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span></span>  
  
     <span data-ttu-id="02d64-112">Sie können die Standardeinstellung für die Serversicherungskomprimierung beim Erstellen einer Sicherung überschreiben, indem Sie die Optionen **Sicherung komprimieren** oder **Sicherung nicht komprimieren** in einem der folgenden Dialogfelder angeben:</span><span class="sxs-lookup"><span data-stu-id="02d64-112">You can override the server backup-compression default when creating a backup by specifying **Compress backup** or **Do not compress backup** in any of the following dialog boxes:</span></span>  
  
    -   [<span data-ttu-id="02d64-113">Datenbank sichern (Seite Optionen)</span><span class="sxs-lookup"><span data-stu-id="02d64-113">Back Up Database (Options Page)</span></span>](back-up-database-backup-options-page.md)  
  
         <span data-ttu-id="02d64-114">Beim Sichern einer Datenbank können Sie die Sicherungskomprimierung für eine einzelne Datenbank, Datei oder Protokollsicherung steuern.</span><span class="sxs-lookup"><span data-stu-id="02d64-114">When backing up a database, you can control backup compression for an individual database, file, or log backup.</span></span>  
  
    -   [<span data-ttu-id="02d64-115">Verwenden des Wartungsplanungs-Assistenten</span><span class="sxs-lookup"><span data-stu-id="02d64-115">Use the Maintenance Plan Wizard</span></span>](../maintenance-plans/use-the-maintenance-plan-wizard.md)  
  
         <span data-ttu-id="02d64-116">Mit dem Wartungsplanungs-Assistenten können Sie die Sicherungskomprimierung bei jeder Gruppe von geplanten vollständigen oder differenziellen Datenbank- bzw. Protokollsicherungen steuern.</span><span class="sxs-lookup"><span data-stu-id="02d64-116">The Maintenance Plan Wizard enables you to control backup compression for each set full or differential database backups or log backups that you schedule.</span></span>  
  
    -   <span data-ttu-id="02d64-117">Integration Services (SSIS) [Task "Datenbank sichern"](../../integration-services/control-flow/back-up-database-task.md)</span><span class="sxs-lookup"><span data-stu-id="02d64-117">Integration Services (SSIS) [Back Up Database task](../../integration-services/control-flow/back-up-database-task.md)</span></span>  
  
         <span data-ttu-id="02d64-118">Sie können das Verhalten der Sicherungskomprimierung steuern, wenn Sie ein Paket für die Sicherung einer einzelnen oder mehrerer Datenbanken erstellen.</span><span class="sxs-lookup"><span data-stu-id="02d64-118">You can control the backup compression behavior when creating a package for backing up a single database or multiple databases.</span></span>  
  
    -   [<span data-ttu-id="02d64-119">Sicherungseinstellungen für den Transaktionsprotokollversand</span><span class="sxs-lookup"><span data-stu-id="02d64-119">Log Shipping Transaction Log Backup Settings</span></span>](../databases/log-shipping-transaction-log-backup-settings.md)  
  
         <span data-ttu-id="02d64-120">Sie können das Sicherungskomprimierungsverhalten von Protokollsicherungen steuern.</span><span class="sxs-lookup"><span data-stu-id="02d64-120">You can control the backup compression behavior of log backups.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="02d64-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02d64-121">See Also</span></span>  
 [<span data-ttu-id="02d64-122">Sicherungskomprimierung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="02d64-122">Backup Compression &#40;SQL Server&#41;</span></span>](backup-compression-sql-server.md)  
  
  
