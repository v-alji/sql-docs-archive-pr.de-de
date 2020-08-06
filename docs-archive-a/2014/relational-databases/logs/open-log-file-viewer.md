---
title: Öffnen des Protokolldatei-Viewers | Microsoft Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Log File Viewer, opening
ms.assetid: a86b89cb-0432-4648-895a-05ecc5450e45
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 269ff10275f7463a8a85249a2a0f06fe9bde364a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616533"
---
# <a name="open-log-file-viewer"></a><span data-ttu-id="d7ea0-102">Öffnen des Protokolldatei-Viewers</span><span class="sxs-lookup"><span data-stu-id="d7ea0-102">Open Log File Viewer</span></span>
  <span data-ttu-id="d7ea0-103">Sie können mithilfe des Protokolldatei-Viewers in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] auf Informationen zu Fehlern und Ereignissen zugreifen, die in folgenden Protokollen aufgezeichnet wurden:</span><span class="sxs-lookup"><span data-stu-id="d7ea0-103">You can use Log File Viewer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to access information about errors and events that are captured in the following logs:</span></span>  
  
-   <span data-ttu-id="d7ea0-104">Überwachungsauflistung</span><span class="sxs-lookup"><span data-stu-id="d7ea0-104">Audit Collection</span></span>  
  
-   <span data-ttu-id="d7ea0-105">Datensammlung</span><span class="sxs-lookup"><span data-stu-id="d7ea0-105">Data Collection</span></span>  
  
-   <span data-ttu-id="d7ea0-106">Datenbank-E-Mail</span><span class="sxs-lookup"><span data-stu-id="d7ea0-106">Database Mail</span></span>  
  
-   <span data-ttu-id="d7ea0-107">Auftragsverlauf</span><span class="sxs-lookup"><span data-stu-id="d7ea0-107">Job History</span></span>  
  
-   <span data-ttu-id="d7ea0-108">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d7ea0-108">SQL Server</span></span>  
  
-   <span data-ttu-id="d7ea0-109">SQL Server-Agent</span><span class="sxs-lookup"><span data-stu-id="d7ea0-109">SQL Server Agent</span></span>  
  
-   <span data-ttu-id="d7ea0-110">Windows-Ereignisse (auf diese Windows-Ereignisse kann auch mithilfe der Ereignisanzeige zugegriffen werden)</span><span class="sxs-lookup"><span data-stu-id="d7ea0-110">Windows events (These Windows events can also be accessed from Event Viewer.)</span></span>  
  
 <span data-ttu-id="d7ea0-111">Ab [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]können Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Protokolldateien aus lokalen oder Remoteinstanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]mit der Option Registrierte Server anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-111">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], you can use Registered Servers to view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files from local or remote instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d7ea0-112">Mit Registrierte Server können Sie die Protokolldateien unabhängig davon anzeigen, ob diese online oder offline sind.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-112">By using Registered Servers, you can view the log files when the instances are either online or offline.</span></span> <span data-ttu-id="d7ea0-113">Weitere Informationen zu Onlinezugriff finden Sie weiter unten in diesem Thema in der Vorgehensweise "So zeigen Sie Onlineprotokolldateien von registrierten Servern an".</span><span class="sxs-lookup"><span data-stu-id="d7ea0-113">For more information about online access, see the procedure "To view online log files from Registered Servers" later in this topic.</span></span> <span data-ttu-id="d7ea0-114">Weitere Informationen über den Zugriff auf [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Offlineprotokolldateien finden Sie unter [Anzeigen von Offlineprotokolldateien](view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="d7ea0-114">For more information about how to access offline [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files, see [View Offline Log Files](view-offline-log-files.md).</span></span>  
  
 <span data-ttu-id="d7ea0-115">Sie können den Protokolldatei-Viewer auf mehrere Arten öffnen, je nach anzuzeigenden Informationen.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-115">You can open Log File Viewer in several ways, depending on the information that you want to view.</span></span>  
  
##  <a name="permissions"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d7ea0-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="d7ea0-116">Permissions</span></span>  
 <span data-ttu-id="d7ea0-117">Zum Zugreifen auf Protokolldateien für Onlineinstanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] müssen Sie Mitglied der festen Serverrolle „securityadmin“ sein.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-117">To access log files for instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are online, this requires membership in the securityadmin fixed server role.</span></span>  
  
 <span data-ttu-id="d7ea0-118">Zum Zugreifen auf Protokolldateien für Offlineinstanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] müssen Sie über Lesezugriff für den WMI-Namespace **Root\Microsoft\SqlServer\ComputerManagement10** und den Ordner mit den Protokolldateien verfügen.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-118">To access log files for instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are offline, you must have read access to both the **Root\Microsoft\SqlServer\ComputerManagement10** WMI namespace, and to the folder where the log files are stored.</span></span> <span data-ttu-id="d7ea0-119">Weitere Informationen finden Sie im Abschnitt „Sicherheit“ des Themas [Anzeigen von Offlineprotokolldateien](view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="d7ea0-119">For more information, see the Security section of the topic [View Offline Log Files](view-offline-log-files.md).</span></span>  
  
### <a name="security"></a><span data-ttu-id="d7ea0-120">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d7ea0-120">Security</span></span>  
 <span data-ttu-id="d7ea0-121">Erfordert die Mitgliedschaft in der festen Serverrolle securityadmin.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-121">Requires membership in the securityadmin fixed server role.</span></span>  
  
### <a name="view-log-files"></a><span data-ttu-id="d7ea0-122">Anzeigen von Protokolldateien</span><span class="sxs-lookup"><span data-stu-id="d7ea0-122">View Log Files</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-general-sql-server-activity"></a><span data-ttu-id="d7ea0-123">So zeigen Sie Protokolle zu allgemeinen SQL Server-Aktivitäten an</span><span class="sxs-lookup"><span data-stu-id="d7ea0-123">To view logs that are related to general SQL Server activity</span></span>  
  
1.  <span data-ttu-id="d7ea0-124">Erweitern Sie im Objekt-Explorer den Knoten **Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-124">In Object Explorer, expand **Management**.</span></span>  
  
2.  <span data-ttu-id="d7ea0-125">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="d7ea0-125">Do either of the following:</span></span>  
  
    -   <span data-ttu-id="d7ea0-126">Klicken Sie mit der rechten Maustaste auf **SQL Server-Protokolle**, zeigen Sie auf **Sicht**und dann entweder auf **SQL Server-Protokoll** oder **SQL Server- und Windows-Protokoll**.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-126">Right-click **SQL Server Logs**, point to **View**, and then click either **SQL Server Log** or **SQL Server and Windows Log**.</span></span>  
  
    -   <span data-ttu-id="d7ea0-127">Erweitern Sie **SQL Server-Protokolle**, klicken Sie mit der rechten Maustaste auf eine der Protokolldateien, und klicken Sie dann auf **SQL Server-Protokoll anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-127">Expand **SQL Server Logs**, right-click any log file, and then click **View SQL Server Log**.</span></span> <span data-ttu-id="d7ea0-128">Sie können auch auf jede beliebige Protokolldatei doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-128">You can also double-click any log file.</span></span>  
  
     <span data-ttu-id="d7ea0-129">Die Protokolle sind **Datenbank-E-Mail**, **SQL Server**, **SQL Server-Agent**und **Windows NT**-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-129">The logs include **Database Mail**, **SQL Server**, **SQL Server Agent**, and **Windows NT**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-jobs"></a><span data-ttu-id="d7ea0-130">So zeigen Sie Protokolle zu Aufträgen an</span><span class="sxs-lookup"><span data-stu-id="d7ea0-130">To view logs that are related to jobs</span></span>  
  
-   <span data-ttu-id="d7ea0-131">Erweitern Sie im Objekt-Explorer den Knoten **SQL Server-Agent**, klicken Sie mit der rechten Maustaste auf **Aufträge**, und klicken Sie dann auf **Verlauf anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-131">In Object Explorer, expand **SQL Server Agent**, right-click **Jobs**, and then click **View History**.</span></span>  
  
     <span data-ttu-id="d7ea0-132">Die Protokolle sind **Datenbank-E-Mail**, **Auftragsverlauf**und **SQL Server-Agent**.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-132">The logs include **Database Mail**, **Job History**, and **SQL Server Agent**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-maintenance-plans"></a><span data-ttu-id="d7ea0-133">So zeigen Sie Protokolle zu Wartungsplänen an</span><span class="sxs-lookup"><span data-stu-id="d7ea0-133">To view logs that are related to maintenance plans</span></span>  
  
-   <span data-ttu-id="d7ea0-134">Erweitern Sie im Objekt-Explorer den Knoten **Verwaltung**, klicken Sie mit der rechten Maustaste auf **Wartungspläne**, und klicken Sie dann auf **Verlauf anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-134">In Object Explorer, expand **Management**, right-click **Maintenance Plans**, and then click **View History**.</span></span>  
  
     <span data-ttu-id="d7ea0-135">Die Protokolle sind **Datenbank-E-Mail**, **Auftragsverlauf**, **Wartungspläne**, **Remotewartungspläne**und **SQL Server-Agent**.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-135">The logs include **Database Mail**, **Job History**, **Maintenance Plans**, **Remote Maintenance Plans**, and **SQL Server Agent**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-data-collection"></a><span data-ttu-id="d7ea0-136">So zeigen Sie Protokolle zu Datensammlungen an</span><span class="sxs-lookup"><span data-stu-id="d7ea0-136">To view logs that are related to Data Collection</span></span>  
  
-   <span data-ttu-id="d7ea0-137">Erweitern Sie im Objekt-Explorer den Knoten **Verwaltung**, klicken Sie mit der rechten Maustaste auf **Datensammlung**, und klicken Sie dann auf **Protokolle anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-137">In Object Explorer, expand **Management**, right-click **Data Collection**, and then click **View Logs**.</span></span>  
  
     <span data-ttu-id="d7ea0-138">Die Protokolle sind **Datensammlung**, **Auftragsverlauf**und **SQL Server-Agent**.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-138">The logs include **Data Collection**, **Job History**, and **SQL Server Agent**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-database-mail"></a><span data-ttu-id="d7ea0-139">So zeigen Sie Protokolle zu Datenbank-E-Mails an</span><span class="sxs-lookup"><span data-stu-id="d7ea0-139">To view logs that are related to Database Mail</span></span>  
  
-   <span data-ttu-id="d7ea0-140">Erweitern Sie im Objekt-Explorer den Knoten **Verwaltung**, klicken Sie mit der rechten Maustaste auf **Datenbank-E-Mail**, und klicken Sie dann auf **Datenbank-E-Mail-Protokoll anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-140">In Object Explorer, expand **Management**, right-click **Database Mail**, and then click **View Database Mail Log**.</span></span>  
  
     <span data-ttu-id="d7ea0-141">Die Protokolle sind **Datenbank-E-Mail, Auftragsverlauf**, **Wartungspläne**, **Remotewartungspläne**, **SQL Server**, **SQL Server-Agent**und **Windows NT**-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-141">The logs include **Database Mail, Job History**, **Maintenance Plans**, **Remote Maintenance Plans**, **SQL Server**, **SQL Server Agent**, and **Windows NT**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-audits-collections"></a><span data-ttu-id="d7ea0-142">So zeigen Sie Protokolle zu Überwachungsauflistungen an</span><span class="sxs-lookup"><span data-stu-id="d7ea0-142">To view logs that are related to audits collections</span></span>  
  
-   <span data-ttu-id="d7ea0-143">Erweitern Sie im Objekt-Explorer den Knoten **Sicherheit**, erweitern Sie **Überwachungen**, klicken Sie mit der rechten Maustaste auf eine Überwachung, und klicken Sie dann auf **Überwachungsprotokolle anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-143">In Object Explorer, expand **Security**, expand **Audits**, right-click an audit, and then click **View Audit Logs**.</span></span>  
  
     <span data-ttu-id="d7ea0-144">Die Protokolle sind **Überwachungsauflistung** und **Windows NT**.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-144">The logs include **Audit Collection** and **Windows NT**.</span></span>  
  
##### <a name="to-view-logs-that-are-related-to-audits-collections"></a><span data-ttu-id="d7ea0-145">So zeigen Sie Protokolle zu Überwachungsauflistungen an</span><span class="sxs-lookup"><span data-stu-id="d7ea0-145">To view logs that are related to audits collections</span></span>  
  
-   <span data-ttu-id="d7ea0-146">Erweitern Sie im Objekt-Explorer den Knoten **Sicherheit**, erweitern Sie **Überwachungen**, klicken Sie mit der rechten Maustaste auf eine Überwachung, und klicken Sie dann auf **Überwachungsprotokolle anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-146">In Object Explorer, expand **Security**, expand **Audits**, right-click an audit, and then click **View Audit Logs**.</span></span>  
  
     <span data-ttu-id="d7ea0-147">Die Protokolle sind **Überwachungsauflistung** und **Windows NT**.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-147">The logs include **Audit Collection** and **Windows NT**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7ea0-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d7ea0-148">See Also</span></span>  
 <span data-ttu-id="d7ea0-149">[Protokolldatei-Viewer](log-file-viewer.md) </span><span class="sxs-lookup"><span data-stu-id="d7ea0-149">[Log File Viewer](log-file-viewer.md) </span></span>  
 <span data-ttu-id="d7ea0-150">[SQL Server Audit &#40;Datenbank-Engine&#41;](../security/auditing/sql-server-audit-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="d7ea0-150">[SQL Server Audit &#40;Database Engine&#41;](../security/auditing/sql-server-audit-database-engine.md) </span></span>  
 [<span data-ttu-id="d7ea0-151">Anzeigen von Offlineprotokolldateien</span><span class="sxs-lookup"><span data-stu-id="d7ea0-151">View Offline Log Files</span></span>](view-offline-log-files.md)  
  
  
