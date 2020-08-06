---
title: Bereitstellen von Abonnements und Warnungen für SSRS-Dienstanwendungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services Shared Service
- SharePoint Mode [Reporting Services]
- SharePoint Mode
- Reporting Services Service Application
- SSRS service application
ms.assetid: d0de3f1f-4887-47fb-bacf-46aaad74c4be
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9c09033b6a31295b8fbe42058cba9059f5d05629
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726621"
---
# <a name="provision-subscriptions-and-alerts-for-ssrs-service-applications"></a><span data-ttu-id="c78f7-102">Bereitstellen von Abonnements und Warnungen für SSRS-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="c78f7-102">Provision Subscriptions and Alerts for SSRS Service Applications</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="c78f7-103">-Abonnements und -Datenwarnungen setzt voraus, dass der SQL Server-Agent verwendet und SQL Server-Agentberechtigungen konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="c78f7-103">subscriptions and data alerts require SQL Server Agent and require the configuration of permissions for SQL Server Agent.</span></span> <span data-ttu-id="c78f7-104">Wenn Fehlermeldungen darauf hinweisen, dass der SQL Server-Agent erforderlich ist und Sie den SQL Server-Agent gestartet haben, können Sie die Berechtigungen aktualisieren oder überprüfen.</span><span class="sxs-lookup"><span data-stu-id="c78f7-104">If you see error messages that indicate SQL Server Agent is required and you have verified SQL Server Agent is running, then update or verify permissions.</span></span> <span data-ttu-id="c78f7-105">Dieses Thema erstreckt sich auf [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] im SharePoint-Modus. Es werden drei Methoden beschrieben, wie Sie SQL Server-Agentberechtigungen bei Verwendung von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Abonnements aktualisieren können.</span><span class="sxs-lookup"><span data-stu-id="c78f7-105">The scope of this topic is [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in SharePoint mode and the topic describes three ways you can update the permissions of SQL Server Agent with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] subscriptions.</span></span> <span data-ttu-id="c78f7-106">Die Anmeldeinformationen, die Sie in den Schritten dieses Themas verwenden, müssen ausreichende Berechtigungen aufweisen, um RSExecRole-Ausführungsberechtigungen für Objekte in der Dienstanwendung sowie in der msdb- und Masterdatenbank zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="c78f7-106">The credentials you use for the steps in this topic need to have sufficient permissions to grant execute permissions to the RSExecRole for objects in the service application, msdb, and master databases.</span></span>

||
|-|
|<span data-ttu-id="c78f7-107">**[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2013 &#124; SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="c78f7-107">**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2013 &#124; SharePoint 2010</span></span>|

 <span data-ttu-id="c78f7-108">![SQL-Agent-Berechtigungen für Dienstanwendungs-Datenbanken](../../../2014/sql-server/install/media/rs-provisionsqlagent.gif "SQL-Agent-Berechtigungen für Dienstanwendungs-Datenbanken")</span><span class="sxs-lookup"><span data-stu-id="c78f7-108">![SQL Agent permissions to Service Application DBs](../../../2014/sql-server/install/media/rs-provisionsqlagent.gif "SQL Agent permissions to Service Application DBs")</span></span>

||<span data-ttu-id="c78f7-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c78f7-109">Description</span></span>|
|------|-----------------|
|<span data-ttu-id="c78f7-110">**1**</span><span class="sxs-lookup"><span data-stu-id="c78f7-110">**1**</span></span>|<span data-ttu-id="c78f7-111">Die Instanz der SQL Server-Datenbank-Engine, die die Reporting Services-Dienstanwendungsdatenbanken hostet.</span><span class="sxs-lookup"><span data-stu-id="c78f7-111">The instance of SQL Server Database engine that is hosting the Reporting Services service application databases.</span></span>|
|<span data-ttu-id="c78f7-112">**2**</span><span class="sxs-lookup"><span data-stu-id="c78f7-112">**2**</span></span>|<span data-ttu-id="c78f7-113">Die Instanz des SQL Server-Agents für die Instanz der SQL-Datenbank-Engine</span><span class="sxs-lookup"><span data-stu-id="c78f7-113">The instance of SQL Server agent for the instance of the SQL database engine.</span></span>|
|<span data-ttu-id="c78f7-114">**3**</span><span class="sxs-lookup"><span data-stu-id="c78f7-114">**3**</span></span>|<span data-ttu-id="c78f7-115">Die Reporting Services-Dienstanwendungsdatenbanken</span><span class="sxs-lookup"><span data-stu-id="c78f7-115">The Reporting Services service application databases.</span></span> <span data-ttu-id="c78f7-116">Die Namen basieren auf den Informationen, die zum Erstellen der Dienstanwendung verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="c78f7-116">The names are based on the information used for creating the service application.</span></span> <span data-ttu-id="c78f7-117">Es werden beispielsweise folgende Datenbanknamen verwendet:</span><span class="sxs-lookup"><span data-stu-id="c78f7-117">The following are example database names:</span></span><br /><br /> <span data-ttu-id="c78f7-118">ReportingService_2fbae157295d49df86d0b85760c704b0</span><span class="sxs-lookup"><span data-stu-id="c78f7-118">ReportingService_2fbae157295d49df86d0b85760c704b0</span></span><br /><br /> <span data-ttu-id="c78f7-119">ReportingService_2fbae157295d49df86d0b85760c704b0_Alerting</span><span class="sxs-lookup"><span data-stu-id="c78f7-119">ReportingService_2fbae157295d49df86d0b85760c704b0_Alerting</span></span><br /><br /> <span data-ttu-id="c78f7-120">ReportingService_2fbae157295d49df86d0b85760c704b0TempDB</span><span class="sxs-lookup"><span data-stu-id="c78f7-120">ReportingService_2fbae157295d49df86d0b85760c704b0TempDB</span></span>|
|<span data-ttu-id="c78f7-121">**4**</span><span class="sxs-lookup"><span data-stu-id="c78f7-121">**4**</span></span>|<span data-ttu-id="c78f7-122">Der Master und die MSDB-Datenbank der Instanz der SQL-Datenbank-Engine.</span><span class="sxs-lookup"><span data-stu-id="c78f7-122">The master and MSDB database of the instance of the SQL Server Database engine.</span></span>|

 <span data-ttu-id="c78f7-123">Verwenden Sie einen der folgenden drei Methoden, um die Berechtigungen zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="c78f7-123">Use one the following three methods to update the permissions:</span></span>

1.  <span data-ttu-id="c78f7-124">Geben Sie auf der Seite **Bereitstellungen und Abonnements und Warnungen** Anmeldeinformationen ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c78f7-124">From the **Provisions and Subscriptions and Alerts** page, type credentials and click **ok**.</span></span>

2.  <span data-ttu-id="c78f7-125">Klicken auf die Schaltfläche **Skript herunterladen** auf der Seite Bereitstellungen und Abonnements und Warnungen, um ein Transact-SQL-Skript für die Konfiguration von Berechtigungen herunterzuladen</span><span class="sxs-lookup"><span data-stu-id="c78f7-125">From the Provisions and Subscriptions and Alerts page, click the **Download Script** button to download a transact SQL script that can be used to configure permissions.</span></span>

3.  <span data-ttu-id="c78f7-126">Ausführen eines PowerShell-Cmdlet, um ein Transact-SQL-Skript für die Konfiguration von Berechtigungen zu erstellen</span><span class="sxs-lookup"><span data-stu-id="c78f7-126">Run a PowerShell cmdlet to build a transact SQL script that can be used to configure permissions.</span></span>

### <a name="to-update-permissions-using-the-provision-page"></a><span data-ttu-id="c78f7-127">So aktualisieren Sie Berechtigungen mithilfe der Bereitstellungsseite</span><span class="sxs-lookup"><span data-stu-id="c78f7-127">To update permissions using the provision page</span></span>

1.  <span data-ttu-id="c78f7-128">Klicken Sie in der SharePoint-Zentraladministration in der Gruppe **Anwendungsverwaltung** auf **Dienstanwendungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="c78f7-128">From SharePoint Central Administration, in the **Application Management** group click **Manage Service Applications**</span></span>

2.  <span data-ttu-id="c78f7-129">Suchen Sie die Dienstanwendung in der Liste, und klicken Sie auf den Namen der Anwendung. Sie können zum Auswählen der Dienstanwendung auch auf die Spalte **Typ** und anschließend im SharePoint-Menüband auf die Schaltfläche **Verwalten** klicken.</span><span class="sxs-lookup"><span data-stu-id="c78f7-129">Find your service application in the list and click the name of the application or click the **Type** column to select the services application and click the **Manage** button in the SharePoint ribbon.</span></span>

3.  <span data-ttu-id="c78f7-130">Klicken Sie auf der Seite **Reporting Services-Anwendung verwalten** auf **Abonnements und Warnungen bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="c78f7-130">On the **Manage Reporting Services Application** page, click **Provision Subscriptions and Alerts**.</span></span>

4.  <span data-ttu-id="c78f7-131">Wenn der SharePoint-Administrator über ausreichende Berechtigungen für die Masterdatenbank und die Dienstanwendungsdatenbanken verfügt, geben Sie diese Anmeldeinformationen ein.</span><span class="sxs-lookup"><span data-stu-id="c78f7-131">If the SharePoint administrator has enough privileges to the Master database and the service application databases, type those credentials.</span></span>

5.  <span data-ttu-id="c78f7-132">Klicken Sie auf die Schaltfläche **OK** .</span><span class="sxs-lookup"><span data-stu-id="c78f7-132">Click the **OK** button.</span></span>

##  <a name="to-download-the-transact-sql-script"></a><a name="bkmk_download"></a> <span data-ttu-id="c78f7-133">So laden Sie das Transact-SQL-Skript herunter</span><span class="sxs-lookup"><span data-stu-id="c78f7-133">To download the Transact-SQL Script</span></span>

1.  <span data-ttu-id="c78f7-134">Klicken Sie in der SharePoint-Zentraladministration in der Gruppe **Anwendungsverwaltung** auf **Dienstanwendungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="c78f7-134">From SharePoint Central Administration, in the **Application Management** group click **Manage Service Applications**</span></span>

2.  <span data-ttu-id="c78f7-135">Suchen Sie die Dienstanwendung in der Liste, und klicken Sie auf den Namen der Anwendung. Sie können zum Auswählen der Dienstanwendung auch auf die Spalte **Typ** und anschließend im SharePoint-Menüband auf die Schaltfläche **Verwalten** klicken.</span><span class="sxs-lookup"><span data-stu-id="c78f7-135">Find your service application in the list and click the name of the application or click the **Type** column to select the services application and click the **Manage** button in the SharePoint ribbon.</span></span>

3.  <span data-ttu-id="c78f7-136">Klicken Sie auf der Seite **Reporting Services-Anwendung verwalten** auf **Abonnements und Warnungen bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="c78f7-136">On the **Manage Reporting Services Application** page, click **Provision Subscriptions and Alerts**.</span></span>

4.  <span data-ttu-id="c78f7-137">Überprüfen Sie im Bereich **Status anzeigen** , ob der SQL Server-Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c78f7-137">In the **View Status** area, verify SQL Server Agent is running.</span></span>

5.  <span data-ttu-id="c78f7-138">Klicken Sie auf **Skript herunterladen** , um das Transact-SQL-Skript herunterzuladen, das Sie zum Erteilen von Berechtigungen in SQL Server Management Studio ausführen können.</span><span class="sxs-lookup"><span data-stu-id="c78f7-138">Click **Download Script** to download a transact SQL script you can run in SQL Server Management studio to grant permissions.</span></span> <span data-ttu-id="c78f7-139">Der Name der erstellten Skriptdatei enthält den Namen der Reporting Services-Dienstanwendung, z.B. **[Name der Dienstanwendung]-GrantRights.sql**.</span><span class="sxs-lookup"><span data-stu-id="c78f7-139">The script file name that is created will contain the name of your Reporting Services service application name, for example **[name of the service application]-GrantRights.sql**.</span></span>

### <a name="to-generate-the-transact-sql-statement-with-powershell"></a><span data-ttu-id="c78f7-140">So generieren Sie die Transact-SQL-Anweisung mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="c78f7-140">To generate the Transact-SQL statement with PowerShell</span></span>

1.  <span data-ttu-id="c78f7-141">Sie können auch ein Windows PowerShell-cmdlet in der SharePoint 2010-Verwaltungsshell verwenden, um das Transact-SQL-Skript zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c78f7-141">You can also use a Windows PowerShell cmdlet in the SharePoint 2010 Management Shell to create the Transact-SQL script.</span></span>

2.  <span data-ttu-id="c78f7-142">Klicken Sie im Menü **Start** auf **Alle Programme**.</span><span class="sxs-lookup"><span data-stu-id="c78f7-142">On the **Start** menu, click **All Programs**.</span></span>

3.  <span data-ttu-id="c78f7-143">Erweitern Sie **Microsoft SharePoint 2010-Produkte** , und klicken Sie auf **SharePoint 2010-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="c78f7-143">Expand **Microsoft SharePoint 2010 Products** and click **SharePoint 2010 Management Shell**.</span></span>

4.  <span data-ttu-id="c78f7-144">Aktualisieren Sie das folgende PowerShell-Cmdlet, indem Sie den Namen der Berichtsserver-Datenbank, das Anwendungspoolkonto und den Pfad der Anweisung ersetzen.</span><span class="sxs-lookup"><span data-stu-id="c78f7-144">Update the following PowerShell cmdlet by replacing the name of the report server database, application pool account, and the path of the statement.</span></span>

     <span data-ttu-id="c78f7-145">**Syntax des Cmdlets:** `Get-SPRSDatabaseRightsScript -DatabaseName <ReportingServices database name> -UserName <app pool account> -IsWindowsUser | Out-File <path of statement>`</span><span class="sxs-lookup"><span data-stu-id="c78f7-145">**Syntax of cmdlet:** `Get-SPRSDatabaseRightsScript -DatabaseName <ReportingServices database name> -UserName <app pool account> -IsWindowsUser | Out-File <path of statement>`</span></span>

     <span data-ttu-id="c78f7-146">**Beispiel-Cmdlet:** `Get-SPRSDatabaseRightsScript -DatabaseName ReportingService_46fd00359f894b828907b254e3f6257c -UserName "NT AUTHORITY\NETWORK SERVICE" -IsWindowsUser | Out-File c:\SQLServerAgentrights.sql`</span><span class="sxs-lookup"><span data-stu-id="c78f7-146">**Sample cmdlet:** `Get-SPRSDatabaseRightsScript -DatabaseName ReportingService_46fd00359f894b828907b254e3f6257c -UserName "NT AUTHORITY\NETWORK SERVICE" -IsWindowsUser | Out-File c:\SQLServerAgentrights.sql`</span></span>

## <a name="using-the-transact-sql-script"></a><span data-ttu-id="c78f7-147">Verwenden des Transact-SQL-Skripts</span><span class="sxs-lookup"><span data-stu-id="c78f7-147">Using the Transact-SQL Script</span></span>
 <span data-ttu-id="c78f7-148">Die folgenden Verfahren können mit Skripts verwendet werden, die von der Bereitstellungsseite heruntergeladen oder mit PowerShell erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="c78f7-148">The following procedures can be used with scripts download from the provisions page or scripts created using PowerShell.</span></span>

#### <a name="to-load-the-transact-sql-script-in-sql-server-management-studio"></a><span data-ttu-id="c78f7-149">So laden Sie das Transact-SQL-Skript in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c78f7-149">To load the Transact-SQL script in SQL Server Management Studio</span></span>

1.  <span data-ttu-id="c78f7-150">Um SQL Server Management Studio zu öffnen, klicken Sie im **Startmenü** auf **Microsoft SQL Server 2012** , und klicken Sie auf **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="c78f7-150">To open SQL Server Management Studio, on the **Start** menu, click **Microsoft SQL Server 2012** and click **SQL Server Management Studio**.</span></span>

2.  <span data-ttu-id="c78f7-151">Legen Sie im Dialogfeld **Verbindung mit Server herstellen** die folgenden Optionen fest:</span><span class="sxs-lookup"><span data-stu-id="c78f7-151">In the **Connect to Server** dialog box set the following options:</span></span>

    -   <span data-ttu-id="c78f7-152">Wählen Sie in der Liste **Servertyp** die Option **Datenbank-Engine**aus.</span><span class="sxs-lookup"><span data-stu-id="c78f7-152">In the **Server type** list, select **Database Engine**</span></span>

    -   <span data-ttu-id="c78f7-153">Geben Sie unter **Servernamen**den Namen der SQL Server-Instanz ein, auf der Sie den SQL Server-Agent konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="c78f7-153">In **Server Name**, type the name of the SQL Server instance on which you want to configure SQL Server Agent.</span></span>

    -   <span data-ttu-id="c78f7-154">Wählen Sie einen Authentifizierungsmodus aus.</span><span class="sxs-lookup"><span data-stu-id="c78f7-154">Select an authentication mode.</span></span>

    -   <span data-ttu-id="c78f7-155">Wenn Sie eine Verbindung mit SQL Server-Authentifizierung herstellen, geben Sie einen Anmeldenamen und ein Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="c78f7-155">If connecting using SQL Server Authentication, provide a login and password.</span></span>

3.  <span data-ttu-id="c78f7-156">Klicken Sie auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="c78f7-156">Click **Connect**.</span></span>

#### <a name="to-run-the-transact-sql-statement"></a><span data-ttu-id="c78f7-157">So führen Sie die Transact-SQL-Anweisung aus</span><span class="sxs-lookup"><span data-stu-id="c78f7-157">To run the Transact-SQL statement</span></span>

1.  <span data-ttu-id="c78f7-158">Klicken Sie auf der Symbolleiste von SQL Server Management Studio auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="c78f7-158">On the toolbar of SQL Server Management Studio, click **New Query**.</span></span>

2.  <span data-ttu-id="c78f7-159">Klicken Sie im Menü **Datei** auf **Öffnen**und dann auf **Datei**.</span><span class="sxs-lookup"><span data-stu-id="c78f7-159">On the **File** menu, click **Open**, and then click **File**.</span></span>

3.  <span data-ttu-id="c78f7-160">Navigieren Sie zu dem Ordner, in dem Sie die Transact-SQL-Anweisung gespeichert haben, die Sie in der SharePoint 2010-Verwaltungsshell generiert haben.</span><span class="sxs-lookup"><span data-stu-id="c78f7-160">Navigate to the folder where you saved the Transact-SQL statement that you generated in SharePoint 2010 Management Shell.</span></span>

4.  <span data-ttu-id="c78f7-161">Klicken Sie auf die Datei, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="c78f7-161">Click the file and then click **Open**.</span></span>

     <span data-ttu-id="c78f7-162">Die Anweisung wird dem Abfragefenster hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c78f7-162">The statement is added to the query window.</span></span>

5.  <span data-ttu-id="c78f7-163">Klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c78f7-163">Click **Execute**.</span></span>


