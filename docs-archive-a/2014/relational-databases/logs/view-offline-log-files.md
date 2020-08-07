---
title: Anzeigen von Offlineprotokolldateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Log File Viewer, viewing offline logs
- offline log files
ms.assetid: 9223e474-f224-4907-a4f2-081e11db58f5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2afc1992b54c78f69bfae1fc152b41c20bcd4ea1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620366"
---
# <a name="view-offline-log-files"></a><span data-ttu-id="fe49b-102">Anzeigen von Offlineprotokolldateien</span><span class="sxs-lookup"><span data-stu-id="fe49b-102">View Offline Log Files</span></span>
  <span data-ttu-id="fe49b-103">Ab [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]können Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Protokolldateien von einer lokalen oder Remoteinstanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anzeigen, wenn die Zielinstanz offline ist oder nicht gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="fe49b-103">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], you can view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files from a local or remote instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] when the target instance is offline or cannot start.</span></span>  
  
 <span data-ttu-id="fe49b-104">Auf die Offlineprotokolldateien können Sie von Registrierte Server oder programmgesteuert mit WMI- und WQL (WMI Query Language)-Abfragen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="fe49b-104">You can access the offline log files from Registered Servers, or programmatically through WMI and WQL (WMI Query Language) queries.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fe49b-105">Mit diesen Methoden können Sie auch eine Verbindung mit einer Onlineinstanz herstellen, aber aus einem bestimmten Grund nicht über eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Verbindung.</span><span class="sxs-lookup"><span data-stu-id="fe49b-105">You can also use these methods to connect to an instance that is online, but for some reason, you cannot connect through a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="fe49b-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="fe49b-106">Before you Begin</span></span>  
 <span data-ttu-id="fe49b-107">Zum Herstellen einer Verbindung mit Offlineprotokolldateien muss eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf dem Computer installiert sein, den Sie zum Anzeigen der Offlineprotokolldateien verwenden möchten, und außerdem auf dem Computer, auf dem sich die Protokolldateien befinden, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="fe49b-107">To connect to offline log files, an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be installed on the computer that you are using to view the offline log files, and on the computer where the log files that you want to view are located.</span></span> <span data-ttu-id="fe49b-108">Wenn auf beiden Computern eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installiert ist, können Sie Offlinedateien für Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]sowie für Instanzen anzeigen, von denen frühere Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf einem der Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fe49b-108">If an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed on both computers, you can view offline files for instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and for instances that are running earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on either computer.</span></span>  
  
 <span data-ttu-id="fe49b-109">Wenn Sie Registrierte Server verwenden, muss die Instanz, mit der Sie eine Verbindung herstellen möchten, unter **Lokale Servergruppen** oder **Zentrale Verwaltungsserver**registriert sein.</span><span class="sxs-lookup"><span data-stu-id="fe49b-109">If you are using Registered Servers, the instance that you want to connect to must be registered under **Local Server Groups** or under **Central Management Servers**.</span></span> <span data-ttu-id="fe49b-110">(Die Instanz kann eigenständig oder als Mitglied einer Servergruppe registriert werden.) Weitere Informationen zum Hinzufügen einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zu Registrierte Server finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="fe49b-110">(The instance can be registered on its own or be a member of a server group.) For more information about how to add an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to Registered Servers, see the following topics:</span></span>  
  
-   [<span data-ttu-id="fe49b-111">Erstellen oder Bearbeiten einer Servergruppe &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="fe49b-111">Create or Edit a Server Group &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/register-servers/create-or-edit-a-server-group-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="fe49b-112">Registrieren eines verbundenen Servers &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="fe49b-112">Register a Connected Server &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="fe49b-113">Erstellen eines zentralen Verwaltungsservers und einer Servergruppe &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="fe49b-113">Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/register-servers/create-a-central-management-server-and-server-group.md)  
  
 <span data-ttu-id="fe49b-114">Weitere Informationen zum programmgesteuerten Anzeigen der Offlineprotokolldateien mit WMI- und WQL-Abfragen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="fe49b-114">For more information about how to view offline log files programmatically through WMI and WQL queries, see the following topics:</span></span>  
  
-   <span data-ttu-id="fe49b-115">[SqlErrorLogEvent Class](../wmi-provider-configuration-classes/sqlerrorlogevent-class.md) (Dieses Thema veranschaulicht das Abrufen von Werten für protokollierte Ereignisse in einer angegebenen Protokolldatei.)</span><span class="sxs-lookup"><span data-stu-id="fe49b-115">[SqlErrorLogEvent Class](../wmi-provider-configuration-classes/sqlerrorlogevent-class.md) (This topic shows how to retrieve values for logged events in a specified log file.)</span></span>  
  
-   <span data-ttu-id="fe49b-116">[SqlErrorLogFile Class](../wmi-provider-configuration-classes/sqlerrorlogfile-class.md) (Dieses Thema veranschaulicht das Abrufen von Informationen zu allen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Protokolldateien für eine angegebene Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="fe49b-116">[SqlErrorLogFile Class](../wmi-provider-configuration-classes/sqlerrorlogfile-class.md) (This topic shows how to retrieve information about all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files on a specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].)</span></span>  
  
##  <a name="permissions"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fe49b-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="fe49b-117">Permissions</span></span>  
 <span data-ttu-id="fe49b-118">Wenn Sie eine Verbindung mit einer Offlineprotokolldatei herstellen möchten, müssen Sie auf dem lokalen und dem Remotecomputer über die folgenden Berechtigungen verfügen:</span><span class="sxs-lookup"><span data-stu-id="fe49b-118">To connect to an offline log file, you must have the following permissions on both the local and remote computers:</span></span>  
  
-   <span data-ttu-id="fe49b-119">Lesezugriff auf den **Root\Microsoft\SqlServer\ComputerManagement12** -WMI-Namespace.</span><span class="sxs-lookup"><span data-stu-id="fe49b-119">Read access to the **Root\Microsoft\SqlServer\ComputerManagement12** WMI namespace.</span></span> <span data-ttu-id="fe49b-120">Standardmäßig verfügt jeder Benutzer durch die Berechtigung Konto aktivieren über Lesezugriff.</span><span class="sxs-lookup"><span data-stu-id="fe49b-120">By default, everyone has read access through the Enable Account permission.</span></span> <span data-ttu-id="fe49b-121">Weitere Informationen finden Sie im Verfahren "So überprüfen Sie WMI-Berechtigungen" weiter unten in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="fe49b-121">For more information, see the "To verify WMI permissions" procedure later in this section.</span></span>  
  
-   <span data-ttu-id="fe49b-122">Leseberechtigung für den Ordner mit den Fehlerprotokolldateien.</span><span class="sxs-lookup"><span data-stu-id="fe49b-122">Read permission to the folder that contains the error log files.</span></span> <span data-ttu-id="fe49b-123">Standardmäßig befinden sich die Fehlerprotokolldateien unter dem folgenden Pfad (wobei \<*Drive>\* das Laufwerk, auf dem Sie die Installation von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] durchgeführt haben, und \<*InstanceName*> den Namen der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] darstellt):</span><span class="sxs-lookup"><span data-stu-id="fe49b-123">By default the error log files are located in the following path (where \<*Drive>\* represents the drive where you installed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and \<*InstanceName*> is the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]):</span></span>  
  
     <span data-ttu-id="fe49b-124">**\<Drive>: \Programme\Microsoft SQL server\mssql12. \<InstanceName> \MSSQL\LOG erstellt**</span><span class="sxs-lookup"><span data-stu-id="fe49b-124">**\<Drive>:\Program Files\Microsoft SQL Server\MSSQL12.\<InstanceName>\MSSQL\Log**</span></span>  
  
 <span data-ttu-id="fe49b-125">Zum Überprüfen der Sicherheitseinstellungen für den WMI-Namespace können Sie das Snap-In WMI-Kontrolle verwenden.</span><span class="sxs-lookup"><span data-stu-id="fe49b-125">To verify WMI namespace security settings, you can use the WMI Control snap-in.</span></span>  
  
#### <a name="to-verify-wmi-permissions"></a><span data-ttu-id="fe49b-126">So überprüfen Sie WMI-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="fe49b-126">To verify WMI permissions</span></span>  
  
1.  <span data-ttu-id="fe49b-127">Öffnen Sie das Snap-In WMI-Kontrolle.</span><span class="sxs-lookup"><span data-stu-id="fe49b-127">Open the WMI Control snap-in.</span></span> <span data-ttu-id="fe49b-128">Führen Sie dazu je nach Betriebssystem eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="fe49b-128">To do this, do either of the following, depending on the operating system:</span></span>  
  
    -   <span data-ttu-id="fe49b-129">Klicken Sie auf **Start**, geben Sie `wmimgmt.msc` im Feld **Suche starten** ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="fe49b-129">Click **Start**, type `wmimgmt.msc` in the **Start Search** box, and then press ENTER.</span></span>  
  
    -   <span data-ttu-id="fe49b-130">Klicken Sie im **Startmenü**auf **Ausführen**, geben Sie ein `wmimgmt.msc` , und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="fe49b-130">Click **Start**, click **Run**, type `wmimgmt.msc`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="fe49b-131">Standardmäßig wird mit dem Snap-In WMI-Kontrolle der lokale Computer verwaltet.</span><span class="sxs-lookup"><span data-stu-id="fe49b-131">By default, the WMI Control snap-in manages the local computer.</span></span>  
  
     <span data-ttu-id="fe49b-132">Wenn Sie eine Verbindung mit einem Remotecomputer herstellen möchten, führen Sie folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="fe49b-132">If you want to connect to a remote computer, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="fe49b-133">Klicken Sie mit der rechten Maustaste auf **WMI-Kontrolle (Lokal)** , und klicken Sie dann auf **Verbindung mit anderem Computer herstellen**.</span><span class="sxs-lookup"><span data-stu-id="fe49b-133">Right-click **WMI Control (Local)**, and then click **Connect to another computer**.</span></span>  
  
    2.  <span data-ttu-id="fe49b-134">Klicken Sie im Dialogfeld **Verwalteten Computer ändern** auf **Anderem Computer**.</span><span class="sxs-lookup"><span data-stu-id="fe49b-134">In the **Change managed computer** dialog box, click **Another computer**.</span></span>  
  
    3.  <span data-ttu-id="fe49b-135">Geben Sie den Namen des Remotecomputers ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe49b-135">Enter the remote computer name, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="fe49b-136">Klicken Sie mit der rechten Maustaste auf **WMI-Steuerung (lokal)** oder **WMI-Steuerung (***Remote Computername***)**, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="fe49b-136">Right-click **WMI Control (Local)** or **WMI Control (***RemoteComputerName***)**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="fe49b-137">Klicken Sie im Dialogfeld **Eigenschaften von WMI-Kontrolle** auf die Registerkarte **Sicherheit** .</span><span class="sxs-lookup"><span data-stu-id="fe49b-137">In the **WMI Control Properties** dialog box, click the **Security** tab.</span></span>  
  
5.  <span data-ttu-id="fe49b-138">Suchen Sie in der Namespacestruktur den folgenden Namespace, und klicken Sie auf diesen:</span><span class="sxs-lookup"><span data-stu-id="fe49b-138">In the namespace tree, locate and then click the following namespace:</span></span>  
  
     <span data-ttu-id="fe49b-139">**Root\Microsoft\SqlServer\ComputerManagement10**</span><span class="sxs-lookup"><span data-stu-id="fe49b-139">**Root\Microsoft\SqlServer\ComputerManagement10**</span></span>  
  
6.  <span data-ttu-id="fe49b-140">Klicken Sie auf **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="fe49b-140">Click **Security**.</span></span>  
  
7.  <span data-ttu-id="fe49b-141">Stellen Sie sicher, dass das verwendete Konto über die Berechtigung **Konto aktivieren** verfügt.</span><span class="sxs-lookup"><span data-stu-id="fe49b-141">Make sure that the account that will be used has the **Enable Account** permission.</span></span> <span data-ttu-id="fe49b-142">Diese Berechtigung erlaubt den Lesezugriff auf WMI-Objekte.</span><span class="sxs-lookup"><span data-stu-id="fe49b-142">This permission allows Read access to WMI objects.</span></span>  
  
### <a name="view-log-files"></a><span data-ttu-id="fe49b-143">Anzeigen von Protokolldateien</span><span class="sxs-lookup"><span data-stu-id="fe49b-143">View Log Files</span></span>  
 <span data-ttu-id="fe49b-144">Das folgende Verfahren veranschaulicht das Anzeigen von Offlineprotokolldateien über Registrierte Server.</span><span class="sxs-lookup"><span data-stu-id="fe49b-144">The following procedure shows how to view offline log files through Registered Servers.</span></span> <span data-ttu-id="fe49b-145">Dabei wird Folgendes vorausgesetzt:</span><span class="sxs-lookup"><span data-stu-id="fe49b-145">The procedure assumes the following:</span></span>  
  
 <span data-ttu-id="fe49b-146">Die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , mit der Sie eine Verbindung herstellen möchten, wurde bereits in Registrierte Server registriert.</span><span class="sxs-lookup"><span data-stu-id="fe49b-146">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to connect to is already registered in Registered Servers.</span></span>  
  
##### <a name="to-view-log-files-for-instances-that-are-offline"></a><span data-ttu-id="fe49b-147">So zeigen Sie Protokolldateien für Offlineinstanzen an</span><span class="sxs-lookup"><span data-stu-id="fe49b-147">To view log files for instances that are offline</span></span>  
  
1.  <span data-ttu-id="fe49b-148">Wenn Sie Offlineprotokolldateien für eine lokale Instanz anzeigen möchten, stellen Sie sicher, dass Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] mit erhöhten Berechtigungen starten.</span><span class="sxs-lookup"><span data-stu-id="fe49b-148">If you want to view offline log files on a local instance, make sure that you start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] with elevated permissions.</span></span> <span data-ttu-id="fe49b-149">Dazu klicken Sie beim Starten von [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]mit der rechten Maustaste auf **SQL Server Management Studio**, und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="fe49b-149">To do this, when you start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], right-click **SQL Server Management Studio**, and then click **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="fe49b-150">Klicken Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]im Menü **Ansicht** auf **Registrierte Server**.</span><span class="sxs-lookup"><span data-stu-id="fe49b-150">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Registered Servers**.</span></span>  
  
3.  <span data-ttu-id="fe49b-151">Suchen Sie in der Konsolenstruktur die Instanz, in der Sie die Offlinedateien anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="fe49b-151">In the console tree, locate the instance on which you want to view the offline files.</span></span>  
  
4.  <span data-ttu-id="fe49b-152">Führen Sie eines der folgenden Verfahren aus:</span><span class="sxs-lookup"><span data-stu-id="fe49b-152">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="fe49b-153">Wenn die Instanz unter **Lokale Servergruppen**aufgeführt wird, erweitern Sie **Lokale Servergruppen**und die Servergruppe (wenn die Instanz Mitglied einer Gruppe ist), klicken Sie mit der rechten Maustaste auf die Instanz, und klicken Sie dann auf **SQL Server-Protokoll anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="fe49b-153">If the instance is under **Local Server Groups**, expand **Local Server Groups**, expand the server group (if the instance is a member of a group), right-click the instance, and then click **View SQL Server Log**.</span></span>  
  
    -   <span data-ttu-id="fe49b-154">Wenn es sich bei der Instanz um den zentralen Verwaltungsserver selbst handelt, erweitern Sie **Zentrale Verwaltungsserver**, klicken Sie mit der rechten Maustaste auf die Instanz, zeigen Sie auf **Aktionen des zentralen Verwaltungsservers**, und klicken Sie dann auf **SQL Server-Protokoll**anzeigen.</span><span class="sxs-lookup"><span data-stu-id="fe49b-154">If the instance is the Central Management Server itself, expand **Central Management Servers**, right-click the instance, point to **Central Management Server Actions**, and then click **View SQL Server Log**.</span></span>  
  
    -   <span data-ttu-id="fe49b-155">Wenn die Instanz unter **Zentrale Verwaltungsserver**aufgeführt wird, erweitern Sie **Zentrale Verwaltungsserver**und den zentralen Verwaltungsserver, klicken Sie mit der rechten Maustaste auf die Instanz (oder erweitern Sie eine Servergruppe, und klicken Sie mit der rechten Maustaste auf die Instanz), und klicken Sie dann auf **SQL Server-Protokoll anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="fe49b-155">If the instance is under **Central Management Servers**, expand **Central Management Servers**, expand the Central Management Server, right-click the instance (or expand a server group and right-click the instance), and then click **View SQL Server Log**.</span></span>  
  
5.  <span data-ttu-id="fe49b-156">Wenn Sie eine Verbindung mit einer lokalen Instanz herstellen, wird die Verbindung mit den aktuellen Benutzeranmeldeinformationen hergestellt.</span><span class="sxs-lookup"><span data-stu-id="fe49b-156">If you are connecting to a local instance, the connection is made using the current user credentials.</span></span>  
  
     <span data-ttu-id="fe49b-157">Wenn Sie eine Verbindung mit einer Remoteinstanz herstellen, führen Sie im Dialogfeld **Protokolldatei-Viewer – Verbinden als** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="fe49b-157">If you are connecting to a remote instance, in the **Log File Viewer - Connect As** dialog box, do either of the following:</span></span>  
  
    -   <span data-ttu-id="fe49b-158">Wenn Sie eine Verbindung als der aktuelle Benutzer herstellen möchten, stellen Sie sicher, dass das Kontrollkästchen **Als anderer Benutzer verbinden** deaktiviert ist, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe49b-158">To connect as the current user, make sure that the **Connect as another user** check box is cleared, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="fe49b-159">Wenn Sie eine Verbindung als ein anderer Benutzer herstellen möchten, aktivieren Sie das Kontrollkästchen **Als anderer Benutzer verbinden** , und klicken Sie dann auf **Benutzer festlegen**.</span><span class="sxs-lookup"><span data-stu-id="fe49b-159">To connect as another user, select the **Connect as another user** check box, and then click **Set User**.</span></span> <span data-ttu-id="fe49b-160">Wenn Sie dazu aufgefordert werden, geben Sie die Benutzeranmeldeinformationen ein (mit dem Benutzernamen im Format *Domänenname*\\*Benutzername*), klicken Sie auf **OK**, und klicken Sie dann erneut auf **OK** , um eine Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="fe49b-160">When you are prompted, enter the user credentials (with the user name in the format *domain_name*\\*user_name*), click **OK**, and then click **OK** again to connect.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fe49b-161">Wenn das Laden der Protokolldateien zu lange dauert, können Sie auf der Symbolleiste des Protokolldatei-Viewers auf **Beenden** klicken.</span><span class="sxs-lookup"><span data-stu-id="fe49b-161">If the log files take too long to load, you can click **Stop** on the Log File Viewer toolbar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe49b-162">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fe49b-162">See Also</span></span>  
 [<span data-ttu-id="fe49b-163">Protokolldatei-Viewer</span><span class="sxs-lookup"><span data-stu-id="fe49b-163">Log File Viewer</span></span>](log-file-viewer.md)  
  
  
