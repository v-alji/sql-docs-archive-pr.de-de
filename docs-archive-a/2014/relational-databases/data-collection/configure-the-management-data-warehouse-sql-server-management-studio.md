---
title: Konfigurieren des Verwaltungs-Data Warehouses (SQL Server Management Studio) | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dc.datacollection.wizard_finish.f1
- sql12.swb.dc.datacollection.wizard_maploginuser.f1
- sql12.swb.dc.datacollection.wizard_welcome.f1
- sql12.swb.dc.datacollection.wizard_choosemdw.f1
- sql12.swb.dc.datacollection.wizard_completecfg.f1
- sql12.swb.dc.datacollection.wizard_config.f1
- sql12.swb.dc.datacollection.wizard_createmdw.f1
helpviewer_keywords:
- data warehouse [SQL Server], multiple instances
- data warehouse [SQL Server], configuring
- Configure Management Data Warehouse Wizard
- management data warehouse, configuring
ms.assetid: 23a584f3-c5e1-414c-9afe-73cd7efbda4b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1ef4ddd518343a3076c72ecc41f9b15ddf092dc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630669"
---
# <a name="configure-the-management-data-warehouse-sql-server-management-studio"></a><span data-ttu-id="11b1c-102">Konfigurieren des Verwaltungs-Data Warehouses (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="11b1c-102">Configure the Management Data Warehouse (SQL Server Management Studio)</span></span>
  <span data-ttu-id="11b1c-103">In diesem Thema wird beschrieben, wie Sie das Verwaltungs-Data Warehouse für die Unterstützung der Datenspeicherung für einzelne oder mehrere [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanzen, die den Datensammler verwenden, konfigurieren müssen</span><span class="sxs-lookup"><span data-stu-id="11b1c-103">This topic describes how to configure the management data warehouse to support data storage on a single instance or multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are using the data collector.</span></span> <span data-ttu-id="11b1c-104">Diese Instanzen können sich auf dem gleichen Server oder auf verschiedenen Servern befinden.</span><span class="sxs-lookup"><span data-stu-id="11b1c-104">These instances can be on the same server or on different servers.</span></span> <span data-ttu-id="11b1c-105">In diesem Thema sind auch Beschreibungen der Benutzeroberfläche des Dialogfelds [Assistent für die Konfiguration des Verwaltungs-Data Warehouses](#Wizard) enthalten.</span><span class="sxs-lookup"><span data-stu-id="11b1c-105">This topic also provides descriptions of the user interface for the [Configure Data Management Warehouse Wizard](#Wizard) dialog box.</span></span> <span data-ttu-id="11b1c-106">Weitere Informationen zum Konfigurieren eines Datensammlers finden Sie unter [Configure Properties of a Data Collector](configure-properties-of-a-data-collector.md).</span><span class="sxs-lookup"><span data-stu-id="11b1c-106">For information about configuring a data collector, see [Configure Properties of a Data Collector](configure-properties-of-a-data-collector.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="11b1c-107">Wenn der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent für die Verwendung eines der Systemdienstkonten (Lokales System, Netzwerkdienst oder Lokaler Dienst) konfiguriert ist und das Verwaltungs-Data Warehouse auf einer anderen Instanz als der Datensammler erstellt wird, müssen Sie die Sammlungssätze so konfigurieren, dass sie einen Proxy zum Hochladen von Daten in das Verwaltungs-Data Warehouse verwenden.</span><span class="sxs-lookup"><span data-stu-id="11b1c-107">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is configured to run using one of the System service accounts (Local System, Network Service, or Local Service), and the management data warehouse is created on a different instance from the data collector, you must configure collection sets to use a proxy for uploading data to the management data warehouse.</span></span>  
  
### <a name="configure-the-management-data-warehouse-on-a-single-instance-or-multiple-instances-of-ssnoversion"></a><span data-ttu-id="11b1c-108">Konfigurieren des Verwaltungs-Data Warehouses auf einer einzelnen oder mehreren [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11b1c-108">Configure the management data warehouse on a single instance or multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
1.  <span data-ttu-id="11b1c-109">Stellen Sie sicher, dass der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="11b1c-109">Ensure that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is running.</span></span>  
  
2.  <span data-ttu-id="11b1c-110">Erweitern Sie im Objekt-Explorer den Knoten **Verwaltung** .</span><span class="sxs-lookup"><span data-stu-id="11b1c-110">In Object Explorer, expand the **Management** node.</span></span>  
  
3.  <span data-ttu-id="11b1c-111">Klicken Sie mit der rechten Maustaste auf **Datensammlung**, erweitern Sie **Aufgaben**, und klicken Sie dann auf **Verwaltungs-Data Warehouse konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="11b1c-111">Right-click **Data Collection**, expand **Tasks**, and then click **Configure Management Data Warehouse**.</span></span>  
  
4.  <span data-ttu-id="11b1c-112">Verwenden Sie den [Assistenten für die Konfiguration des Verwaltungs-Data Warehouses](#Wizard) , um ein Verwaltungs-Data Warehouse zu erstellen, die Anmeldungen zu konfigurieren, die Datensammlung zu aktivieren und die **Systemdaten-Sammlungssätze**zu starten.</span><span class="sxs-lookup"><span data-stu-id="11b1c-112">Use the [Configure Management Data Warehouse Wizard](#Wizard) to create a management data warehouse, configure logins, enable data collection, and start the **System Data Collection Sets**.</span></span>  
  
     <span data-ttu-id="11b1c-113">Zum Konfigurieren mehrerer Instanzen fahren Sie mit Schritt 5 fort.</span><span class="sxs-lookup"><span data-stu-id="11b1c-113">To configure multiple instances, continue with step 5.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="11b1c-114">Es wird empfohlen, für Bereitstellungen, bei denen der Datensammler auf mehreren Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installiert ist, die dasselbe Verwaltungs-Data Warehouse verwenden, Proxys zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="11b1c-114">It is considered best practice to use proxies in deployments where the data collector is installed on multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are using the same management data warehouse.</span></span>  
  
5.  <span data-ttu-id="11b1c-115">Öffnen Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] auf einer anderen Instanz, und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="11b1c-115">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] on another instance and do either of the following:</span></span>  
  
    -   <span data-ttu-id="11b1c-116">Verwenden Sie den Assistenten für die Konfiguration des Verwaltungs-Data Warehouses, um die Datensammlung für das vorhandene Verwaltungs-Data Warehouse zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="11b1c-116">Use the Configure Management Data Warehouse wizard to configure data collection for the existing management data warehouse.</span></span>  
  
    -   <span data-ttu-id="11b1c-117">Klicken Sie mit der rechten Maustaste auf **Datensammlung**und dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="11b1c-117">Right-click **Data Collection**, and then click **Properties**.</span></span> <span data-ttu-id="11b1c-118">Geben Sie auf der Registerkarte **Allgemein** das vorhandene Verwaltungs-Data Warehouse und den Server an, auf dem es installiert ist.</span><span class="sxs-lookup"><span data-stu-id="11b1c-118">On the **General** tab, specify the existing management data warehouse and the server that it is installed on.</span></span>  
  
6.  <span data-ttu-id="11b1c-119">Wiederholen Sie Schritt 5, bis alle Datenbankinstanzen, die den Datensammler verwenden, so konfiguriert sind, dass sie Daten in das gemeinsam verwendete Verwaltungs-Data Warehouse hochladen.</span><span class="sxs-lookup"><span data-stu-id="11b1c-119">Repeat step 5 until all the database instances that use the data collector are configured to upload data to the shared management data warehouse.</span></span>  
  
####  <a name="configure-management-data-warehouse-wizard"></a><a name="Wizard"></a> <span data-ttu-id="11b1c-120">Assistent für die Konfiguration des Verwaltungs-Data Warehouses</span><span class="sxs-lookup"><span data-stu-id="11b1c-120">Configure Management Data Warehouse Wizard</span></span>  
 <span data-ttu-id="11b1c-121">**Willkommensseite**</span><span class="sxs-lookup"><span data-stu-id="11b1c-121">**Welcome Page**</span></span>  
  
 <span data-ttu-id="11b1c-122">Die Willkommensseite ist die Anfangsseite des Assistenten für die Konfiguration der Datensammlung.</span><span class="sxs-lookup"><span data-stu-id="11b1c-122">The Welcome page is the starting page of the Configure Data Collection Wizard.</span></span> <span data-ttu-id="11b1c-123">Die Anzeige dieser Seite ist optional.</span><span class="sxs-lookup"><span data-stu-id="11b1c-123">Displaying this page is optional.</span></span>  
  
 <span data-ttu-id="11b1c-124">**Diese Anfangsseite nicht mehr anzeigen.**</span><span class="sxs-lookup"><span data-stu-id="11b1c-124">**Do not show this starting page again.**</span></span>  
 <span data-ttu-id="11b1c-125">Wählen Sie diese Option aus, damit diese Seite beim nächsten Start des Assistenten für die Konfiguration der Datensammlung nicht mehr angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="11b1c-125">Select to suppress this page the next time you launch the Configure Data Collection Wizard.</span></span>  
  
 <span data-ttu-id="11b1c-126">**Konfiguration der Verwaltungs-Data Warehouse-Speicherseite**</span><span class="sxs-lookup"><span data-stu-id="11b1c-126">**Configure Management Data Warehouse Storage Page**</span></span>  
  
 <span data-ttu-id="11b1c-127">Auf dieser Seite können Sie einen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbankserver und ein Verwaltungs-Data Warehouse auswählen.</span><span class="sxs-lookup"><span data-stu-id="11b1c-127">Use this page to select a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database server and management data warehouse.</span></span> <span data-ttu-id="11b1c-128">Das Verwaltungs-Data Warehouse ist eine relationale Datenbank, in der aufgelistete Daten gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="11b1c-128">The management data warehouse is a relational database that will store collected data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="11b1c-129">Sie müssen die erforderlichen Berechtigungen zum Erstellen des Verwaltungs-Data Warehouses auf dem Server besitzen.</span><span class="sxs-lookup"><span data-stu-id="11b1c-129">You must have the appropriate level of permissions in order to create the management data warehouse on the server.</span></span> <span data-ttu-id="11b1c-130">Weitere Informationen finden Sie unter [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="11b1c-130">For more information, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span> <span data-ttu-id="11b1c-131">Zudem müssen Sie die erforderlichen Berechtigungen zum Erstellen von Anmeldenamen für Verwaltungs-Data Warehouse-Rollen besitzen.</span><span class="sxs-lookup"><span data-stu-id="11b1c-131">You also must have the appropriate level of permissions to create logins for management data warehouse roles.</span></span>  
  
 <span data-ttu-id="11b1c-132">**Servername**</span><span class="sxs-lookup"><span data-stu-id="11b1c-132">**Server name**</span></span>  
 <span data-ttu-id="11b1c-133">Gibt den Namen des Servers an, der als Host für das Verwaltungs-Data Warehouse fungiert.</span><span class="sxs-lookup"><span data-stu-id="11b1c-133">Specifies the name of the server that will host the management data warehouse.</span></span>  
  
 <span data-ttu-id="11b1c-134">Bei der Konfiguration eines Verwaltungs-Data Warehouse ist **Servername** stets der Name des lokalen Servers und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="11b1c-134">When configuring a management data warehouse, **Server name** is always the name of the local server and cannot be modified.</span></span>  
  
 <span data-ttu-id="11b1c-135">**Datenbankname**</span><span class="sxs-lookup"><span data-stu-id="11b1c-135">**Database name**</span></span>  
 <span data-ttu-id="11b1c-136">Gibt die relationale Datenbank an, in der aufgelistete Daten gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="11b1c-136">Specifies the relational database that will store collected data.</span></span> <span data-ttu-id="11b1c-137">Wählen Sie eine vorhandene Datenbank aus der Liste aus, oder klicken Sie auf **Neu** , um im Dialogfeld **Neue Datenbank** eine neue Datenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="11b1c-137">Use the list to select an existing database or click **New** to create a new database using the **New Database** dialog.</span></span>  
  
 <span data-ttu-id="11b1c-138">Die Option **Neu** ist nur beim Konfigurieren eines Datensammlungssatzes verfügbar.</span><span class="sxs-lookup"><span data-stu-id="11b1c-138">The **New** option is available only when configuring a data collection set</span></span>  
  
 <span data-ttu-id="11b1c-139">**Zuordnen von Anmeldenamen und Benutzern (Seite)**</span><span class="sxs-lookup"><span data-stu-id="11b1c-139">**Map Logins and Users Page**</span></span>  
  
 <span data-ttu-id="11b1c-140">Verwenden Sie diese Seite, um Benutzerrollen für Datenbanken Anmeldenamen für das Verwaltungs-Data Warehouse zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="11b1c-140">Use this page to map logins to database user roles for the management data warehouse.</span></span>  
  
 <span data-ttu-id="11b1c-141">**Benutzer, die dieser Anmeldung zugeordnet sind**</span><span class="sxs-lookup"><span data-stu-id="11b1c-141">**Users mapped to this login**</span></span>  
 <span data-ttu-id="11b1c-142">Zeigt die Anmeldungen an, die auf dem Server vorhanden sind, der als Host für das Verwaltungs-Data Warehouse fungiert.</span><span class="sxs-lookup"><span data-stu-id="11b1c-142">Displays the existing logins on the server that will host the management data warehouse.</span></span> <span data-ttu-id="11b1c-143">Jede Zeile enthält folgende Elemente, die bearbeitet werden können: das Kontrollkästchen **Zuordnen** , einen Namen für die **Anmeldung** und einen **Typ** für die Anmeldung.</span><span class="sxs-lookup"><span data-stu-id="11b1c-143">Each row contains an editable **Map** check box, a **Login** name, and a **Type** of login.</span></span>  
  
 <span data-ttu-id="11b1c-144">Geben Sie eine Anmeldung durch Aktivieren des Kontrollkästchens **Zuordnen** für die Anmeldung an.</span><span class="sxs-lookup"><span data-stu-id="11b1c-144">Specify a login by selecting the **Map** checkbox for the login.</span></span>  
  
 <span data-ttu-id="11b1c-145">**Mitgliedschaft in Datenbankrolle für:**  *\<data warehouse name>*</span><span class="sxs-lookup"><span data-stu-id="11b1c-145">**Database role membership for:**  *\<data warehouse name>*</span></span>  
 <span data-ttu-id="11b1c-146">Wählen Sie die Verwaltungs-Data Warehouse-Rolle aus, der der Anmeldenamen zugeordnet ist. Aktivieren Sie zu diesem Zweck das bzw. die entsprechenden Kontrollkästchen:</span><span class="sxs-lookup"><span data-stu-id="11b1c-146">Select the management data warehouse role that the login is mapped to by clicking the checkbox by one or more of the following options:</span></span>  
  
-   <span data-ttu-id="11b1c-147">**mdw_admin**</span><span class="sxs-lookup"><span data-stu-id="11b1c-147">**mdw_admin**</span></span>  
  
-   <span data-ttu-id="11b1c-148">**mdw_reader**</span><span class="sxs-lookup"><span data-stu-id="11b1c-148">**mdw_reader**</span></span>  
  
-   <span data-ttu-id="11b1c-149">**mdw_writer**</span><span class="sxs-lookup"><span data-stu-id="11b1c-149">**mdw_writer**</span></span>  
  
 <span data-ttu-id="11b1c-150">**Neue Anmeldung**</span><span class="sxs-lookup"><span data-stu-id="11b1c-150">**New Login**</span></span>  
 <span data-ttu-id="11b1c-151">Öffnen Sie das Dialogfeld **Anmeldung – Neu** , und erstellen Sie eine neue Anmeldung für das Verwaltungs-Data Warehouse.</span><span class="sxs-lookup"><span data-stu-id="11b1c-151">Open the **Login - New** dialog box and create a new login for the management data warehouse.</span></span>  
  
 <span data-ttu-id="11b1c-152">**Seite "Assistenten abschließen"**</span><span class="sxs-lookup"><span data-stu-id="11b1c-152">**Complete the Wizard Page**</span></span>  
  
 <span data-ttu-id="11b1c-153">Auf dieser Seite können Sie die Datensammlungskonfiguration überprüfen und abschließen.</span><span class="sxs-lookup"><span data-stu-id="11b1c-153">Use this page to verify and complete data collection configuration.</span></span> <span data-ttu-id="11b1c-154">Der im Ansichtsfenster angezeigten Struktur ist zu entnehmen, welche Konfigurationen angewendet und welche Aktionen ausgeführt werden, wenn Sie auf **Fertig stellen**klicken.</span><span class="sxs-lookup"><span data-stu-id="11b1c-154">The tree displayed in the viewing window shows what configurations will applied as well as what actions will take place when you click **Finish**.</span></span>  
  
 <span data-ttu-id="11b1c-155">**Konfigurieren des Fortschritts des Assistenten für die Konfiguration der Datensammlung (Seite)**</span><span class="sxs-lookup"><span data-stu-id="11b1c-155">**Configure Data Collection Wizard Progress Page**</span></span>  
  
 <span data-ttu-id="11b1c-156">Auf dieser Seite können Sie die Ergebnisse der einzelnen Konfigurationsschritte anzeigen.</span><span class="sxs-lookup"><span data-stu-id="11b1c-156">Use this page to view the results of each configuration step.</span></span>  
  
 <span data-ttu-id="11b1c-157">**Details**</span><span class="sxs-lookup"><span data-stu-id="11b1c-157">**Details**</span></span>  
 <span data-ttu-id="11b1c-158">Zeigt jeden Konfigurationsschritt als Zeile im Raster **Details** an.</span><span class="sxs-lookup"><span data-stu-id="11b1c-158">Displays each configuration step as a row in the **Details** grid.</span></span> <span data-ttu-id="11b1c-159">In jeder Zeile wird in der Spalte **Aktion** der Schritt beschrieben, und in der Spalte **Status** wird angegeben, ob der Schritt erfolgreich ausgeführt wurde oder fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="11b1c-159">Each row contains an **Action** column that describes the step, and a **Status** column that indicates the success or failure of the step.</span></span> <span data-ttu-id="11b1c-160">Wenn ein Fehler aufgetreten ist, wird in der Spalte **Meldung** eine Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="11b1c-160">If there is an error, a message appears in the **Message** column.</span></span>  
  
 <span data-ttu-id="11b1c-161">**Beenden**</span><span class="sxs-lookup"><span data-stu-id="11b1c-161">**Stop**</span></span>  
 <span data-ttu-id="11b1c-162">Beendet die Verarbeitung des Assistenten.</span><span class="sxs-lookup"><span data-stu-id="11b1c-162">Stop wizard processing.</span></span>  
  
 <span data-ttu-id="11b1c-163">**Report**</span><span class="sxs-lookup"><span data-stu-id="11b1c-163">**Report**</span></span>  
 <span data-ttu-id="11b1c-164">Zeigt einen Bericht über die Datensammlungskonfiguration an.</span><span class="sxs-lookup"><span data-stu-id="11b1c-164">View a report of the data collection configuration.</span></span> <span data-ttu-id="11b1c-165">Die folgenden Berichtsoptionen stehen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="11b1c-165">The following report options are provided:</span></span>  
  
-   <span data-ttu-id="11b1c-166">Bericht anzeigen</span><span class="sxs-lookup"><span data-stu-id="11b1c-166">View Report</span></span>  
  
-   <span data-ttu-id="11b1c-167">Bericht in Datei speichern</span><span class="sxs-lookup"><span data-stu-id="11b1c-167">Save Report to File</span></span>  
  
-   <span data-ttu-id="11b1c-168">Bericht in Zwischenablage kopieren</span><span class="sxs-lookup"><span data-stu-id="11b1c-168">Copy Report to Clipboard</span></span>  
  
-   <span data-ttu-id="11b1c-169">Bericht als E-Mail senden</span><span class="sxs-lookup"><span data-stu-id="11b1c-169">Send Report as E-mail</span></span>  
  
 <span data-ttu-id="11b1c-170">**Close**</span><span class="sxs-lookup"><span data-stu-id="11b1c-170">**Close**</span></span>  
 <span data-ttu-id="11b1c-171">Schließen Sie den Assistenten.</span><span class="sxs-lookup"><span data-stu-id="11b1c-171">Close the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11b1c-172">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="11b1c-172">See Also</span></span>  
 <span data-ttu-id="11b1c-173">[sp_syscollector_enable_collector &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="11b1c-173">[sp_syscollector_enable_collector &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql) </span></span>  
 <span data-ttu-id="11b1c-174">[sp_syscollector_disable_collector &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="11b1c-174">[sp_syscollector_disable_collector &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql) </span></span>  
 <span data-ttu-id="11b1c-175">[Datensammlung](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="11b1c-175">[Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="11b1c-176">Verwalten von Datensammlungen</span><span class="sxs-lookup"><span data-stu-id="11b1c-176">Manage Data Collection</span></span>](manage-data-collection.md)  
  
  
