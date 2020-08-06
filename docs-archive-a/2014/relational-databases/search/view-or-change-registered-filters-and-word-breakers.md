---
title: Anzeigen oder Ändern von registrierten Filtern und Wörtertrennungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- full-text search [SQL Server], word breakers
- full-text search [SQL Server], filters
- filters [full-text search]
- word breakers [full-text search]
ms.assetid: f88c54df-b1aa-4701-807f-dc92c32363fd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 79ad7f1f7df15fed21a132bbe253adc7185d8c06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697809"
---
# <a name="view-or-change-registered-filters-and-word-breakers"></a><span data-ttu-id="584e3-102">Anzeigen oder Ändern von registrierten Filtern und Wörtertrennungen</span><span class="sxs-lookup"><span data-stu-id="584e3-102">View or Change Registered Filters and Word Breakers</span></span>
  <span data-ttu-id="584e3-103">Nach dem Installieren oder Deinstallieren von Wörtertrennungen oder Filtern werden die Änderungen nicht automatisch auf Serverinstanzen wirksam.</span><span class="sxs-lookup"><span data-stu-id="584e3-103">After any word breakers or filters are installed or uninstalled on a system, the changes do not automatically take effect on server instances.</span></span> <span data-ttu-id="584e3-104">In diesem Thema wird beschrieben, wie die zurzeit registrierte Wörtertrennung oder die Filter angezeigt werden und wie neu installierte Wörtertrennungen und Filter auf einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]registriert werden.</span><span class="sxs-lookup"><span data-stu-id="584e3-104">This topic describes how to view the currently registered word breaker or filters and how to register newly installed word breakers and filters on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="to-view-a-list-of-languages-whose-word-breakers-are-currently-registered"></a><span data-ttu-id="584e3-105">So zeigen Sie eine Liste der Sprachen an, deren Wörtertrennungen derzeit registriert sind.</span><span class="sxs-lookup"><span data-stu-id="584e3-105">To view a list of languages whose word breakers are currently registered</span></span>  
  
1.  <span data-ttu-id="584e3-106">Verwenden Sie die [sys.fulltext_languages](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql) -Katalogsicht wie folgt:</span><span class="sxs-lookup"><span data-stu-id="584e3-106">Use the [sys.fulltext_languages](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql) catalog view, as follows:</span></span>  
  
    ```  
    SELECT * FROM sys.fulltext_languages;   
    ```  
  
### <a name="to-view-a-list-of-the-filters-that-are-currently-registered"></a><span data-ttu-id="584e3-107">So zeigen Sie eine Liste der Filter an, die derzeit registriert sind</span><span class="sxs-lookup"><span data-stu-id="584e3-107">To view a list of the filters that are currently registered</span></span>  
  
1.  <span data-ttu-id="584e3-108">Verwenden Sie die gespeicherte Systemprozedur [sp_help_fulltext_system_components](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) wie folgt:</span><span class="sxs-lookup"><span data-stu-id="584e3-108">Use the [sp_help_fulltext_system_components](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) system stored procedure, as follows:</span></span>  
  
    ```  
    EXEC sp_help_fulltext_system_components 'filter';    
    ```  
  
### <a name="to-register-newly-installed-word-breakers-and-filters"></a><span data-ttu-id="584e3-109">So registrieren Sie neu installierte Wörtertrennungen und Filter</span><span class="sxs-lookup"><span data-stu-id="584e3-109">To register newly installed word breakers and filters</span></span>  
  
1.  <span data-ttu-id="584e3-110">Verwenden Sie zum Aktualisieren der Liste mit den Sprachen die gespeicherte Systemprozedur [sp_fulltext_service](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql) wie folgt:</span><span class="sxs-lookup"><span data-stu-id="584e3-110">Use the [sp_fulltext_service](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql) system stored procedure to update the list of languages, as follows:</span></span>  
  
    ```  
    exec sp_fulltext_service 'update_languages';   
    ```  
  
### <a name="to-unregister-uninstalled-word-breakers-and-filters"></a><span data-ttu-id="584e3-111">So heben Sie die Registrierung deinstallierter Wörtertrennungen und Filter auf</span><span class="sxs-lookup"><span data-stu-id="584e3-111">To unregister uninstalled word breakers and filters</span></span>  
  
1.  <span data-ttu-id="584e3-112">Verwenden Sie zum Aktualisieren der Liste mit den Sprachen **sp_fulltext_service** wie folgt:</span><span class="sxs-lookup"><span data-stu-id="584e3-112">Use the **sp_fulltext_service** to update the list of languages, as follows:</span></span>  
  
    ```  
    exec sp_fulltext_service 'update_languages'  
    ```  
  
2.  <span data-ttu-id="584e3-113">Verwenden Sie zum Neustarten der Filterdaemon-Hostprozesse (fdhost.exe) **sp_fulltext_service** wie folgt:</span><span class="sxs-lookup"><span data-stu-id="584e3-113">Use the **sp_fulltext_service** to restart the filter daemon host processes (fdhost.exe), as follows:</span></span>  
  
    ```  
    exec sp_fulltext_service 'restart_all_fdhosts';  
    ```  
  
### <a name="to-replace-existing-word-breakers-or-filters-when-installing-new-ones"></a><span data-ttu-id="584e3-114">So ersetzen Sie vorhandene Wörtertrennungen oder Filter beim Installieren neuer Wörtertrennungen und Filter</span><span class="sxs-lookup"><span data-stu-id="584e3-114">To replace existing word breakers or filters when installing new ones</span></span>  
  
1.  <span data-ttu-id="584e3-115">Vergewissern Sie sich bei der Vorbereitung zur Installation einer DLL-Datei, die neue Wörtertrennungen oder Filter enthält, dass diese nicht den gleichen Namen einer DLL-Datei hat, die bereits auf Ihrer Serverinstanz installiert ist.</span><span class="sxs-lookup"><span data-stu-id="584e3-115">When preparing to install a DLL file that contains new word breakers or filters, verify that it has a different filename from any of the existing DLL files installed on your server instance.</span></span>  
  
2.  <span data-ttu-id="584e3-116">Kopieren Sie die neue DLL-Datei in das Verzeichnis, das die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Standard-DLL-Dateien für die Serverinstanz enthält.</span><span class="sxs-lookup"><span data-stu-id="584e3-116">Copy the new DLL file into the directory containing the standard [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] DLL files for the server instance.</span></span> <span data-ttu-id="584e3-117">Dies ist der Standardspeicherort:</span><span class="sxs-lookup"><span data-stu-id="584e3-117">The default location is:</span></span>  
  
     <span data-ttu-id="584e3-118">C:\Programme\Microsoft SQL Server\MSSQL.*Instanzname*\MSSQL\Binn</span><span class="sxs-lookup"><span data-stu-id="584e3-118">C:\Program Files\Microsoft SQL Server\MSSQL.*instance_name*\MSSQL\Binn</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="584e3-119">Es wird dringend empfohlen, nur signierte und überprüfte Komponenten zu laden.</span><span class="sxs-lookup"><span data-stu-id="584e3-119">We highly recommend that you load only signed and verified components.</span></span> <span data-ttu-id="584e3-120">Außerdem sollten Sie den FDHOST-Startprogrammdienst (MSSQLFDLauncher) mit den geringstmöglichen Privilegien ausführen.</span><span class="sxs-lookup"><span data-stu-id="584e3-120">Also, we recommend that you run the FDHOST Launcher (MSSQLFDLauncher) Service with the least possible privileges.</span></span>  
  
3.  <span data-ttu-id="584e3-121">Installieren Sie die neue Wörtertrennung oder die Filter.</span><span class="sxs-lookup"><span data-stu-id="584e3-121">Install the new word breaker or filters.</span></span>  
  
     <span data-ttu-id="584e3-122">**So installieren und laden Sie Microsoft Filter Pack IFilters**</span><span class="sxs-lookup"><span data-stu-id="584e3-122">**To install and load Microsoft Filter Pack IFilters**</span></span>  
  
    -   [<span data-ttu-id="584e3-123">So registrieren Sie Microsoft Filter Pack IFilters bei SQL Server</span><span class="sxs-lookup"><span data-stu-id="584e3-123">How to register Microsoft Filter Pack IFilters with SQL Server</span></span>](https://go.microsoft.com/fwlink/?LinkId=130439)  
  
4.  <span data-ttu-id="584e3-124">Verwenden Sie zum Laden neu installierter Wörtertrennungen und Filter in die Serverinstanz **sp_fulltext_service** wie folgt:</span><span class="sxs-lookup"><span data-stu-id="584e3-124">Use **sp_fulltext_service** to load newly installed word breakers and filters in the server instance, as follows:</span></span>  
  
    ```  
    EXEC sp_fulltext_service @action='load_os_resources', @value=1;  
    ```  
  
5.  <span data-ttu-id="584e3-125">Verwenden Sie zum Aktualisieren der Liste mit den Sprachen **sp_fulltext_service** wie folgt:</span><span class="sxs-lookup"><span data-stu-id="584e3-125">Use **sp_fulltext_service** to update the list of languages, as follows:</span></span>  
  
    ```  
    EXEC sp_fulltext_service 'update_languages';  
    ```  
  
6.  <span data-ttu-id="584e3-126">Verwenden Sie zum Neustarten der Filterdaemon-Hostprozesse (fdhost.exe) **sp_fulltext_service** wie folgt:</span><span class="sxs-lookup"><span data-stu-id="584e3-126">Restart the filter daemon host processes (fdhost.exe), using **sp_fulltext_service** as follows:</span></span>  
  
    ```  
    EXEC sp_fulltext_service 'restart_all_fdhosts';   
    ```  
  
## <a name="see-also"></a><span data-ttu-id="584e3-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="584e3-127">See Also</span></span>  
 <span data-ttu-id="584e3-128">[Festlegen des Dienstkontos für das Startprogramm des Volltextfilterdaemon](set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span><span class="sxs-lookup"><span data-stu-id="584e3-128">[Set the Service Account for the Full-text Filter Daemon Launcher](set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span></span>  
 <span data-ttu-id="584e3-129">[Konfigurieren und Verwalten von Filtern für die Suche](configure-and-manage-filters-for-search.md) </span><span class="sxs-lookup"><span data-stu-id="584e3-129">[Configure and Manage Filters for Search](configure-and-manage-filters-for-search.md) </span></span>  
 [<span data-ttu-id="584e3-130">Konfigurieren und Verwalten von Wörtertrennungen und Wortstammerkennungen für die Suche</span><span class="sxs-lookup"><span data-stu-id="584e3-130">Configure and Manage Word Breakers and Stemmers for Search</span></span>](configure-and-manage-word-breakers-and-stemmers-for-search.md)  
  
  
