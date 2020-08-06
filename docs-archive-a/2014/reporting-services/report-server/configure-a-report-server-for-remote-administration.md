---
title: Konfigurieren eines Berichtsservers für die Remoteverwaltung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services Configuration tool
- WMI provider [Reporting Services], remote configuration
- configuration management [WMI]
- report servers [Reporting Services], configuring
- remote server administration [Reporting Services]
ms.assetid: 8c7f145f-3ac2-4203-8cd6-2a4694395d09
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2c34db5299fc1b82a7896a41519e55466c3b3b79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619603"
---
# <a name="configure-a-report-server-for-remote-administration"></a><span data-ttu-id="e468d-102">Konfigurieren eines Berichtsservers für die Remoteverwaltung</span><span class="sxs-lookup"><span data-stu-id="e468d-102">Configure a Report Server for Remote Administration</span></span>
  <span data-ttu-id="e468d-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]können Sie Berichtsserverinstanzen lokal oder remote konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e468d-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can configure report server instances locally or remotely.</span></span> <span data-ttu-id="e468d-104">Zum Konfigurieren einer Remote-Berichtsserverinstanz können Sie das Reporting Services-Konfigurationstool verwenden oder benutzerdefinierten Code schreiben, der für den Anbieter der [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Windows-Verwaltungsinstrumentation (Windows Management Instrumentation oder WMI) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e468d-104">To configure a remote report server instance, you can use the Reporting Services Configuration tool or write custom code that uses the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Windows Management Instrumentation (WMI) provider.</span></span> <span data-ttu-id="e468d-105">Das Reporting Services-Konfigurationstool stellt dem WMI-Anbieter eine grafische Benutzeroberfläche bereit, sodass Sie einen Berichtsserver konfigurieren können, ohne Code schreiben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="e468d-105">The Reporting Services Configuration tool provides a graphical interface to the WMI provider so that you can configure a report server without having to write code.</span></span> <span data-ttu-id="e468d-106">Wenn Sie das Tool starten, können Sie einen Remoteserver angeben, zu dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e468d-106">When you start the tool, you can specify a remote server to connect to.</span></span>  
  
 <span data-ttu-id="e468d-107">Bevor Sie das Tool zur Konfiguration eines Remoteberichtsservers verwenden können, müssen Sie die Anweisungen zu diesem Thema befolgen und die Ports in der Windows-Firewall, Remoteverbindungen und Remote-WMI-Anforderungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e468d-107">Before you can use the tool to configure a remote report server, you must follow the instructions in this topic to enable ports in Windows Firewall, enable remote connections, and enable remote WMI requests.</span></span>  
  
 <span data-ttu-id="e468d-108">Die richtige Konfiguration hilft Ihnen, den folgenden Fehler zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="e468d-108">Proper configuration helps you avoid the following error:</span></span>  
  
 `The machine could not be found.`  
  
 `"The RPC server is unavailable. (Exception from HRESULT: 0x800706BA)".`  
  
## <a name="prerequisites"></a><span data-ttu-id="e468d-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e468d-109">Prerequisites</span></span>  
 <span data-ttu-id="e468d-110">Zum Ändern der Firewalleinstellungen müssen Sie lokal angemeldet und Mitglied der lokalen Administratorengruppe sein.</span><span class="sxs-lookup"><span data-stu-id="e468d-110">To modify firewall settings, you must be logged on locally and you must be a member of the local Administrators group.</span></span> <span data-ttu-id="e468d-111">Die Windows-Firewalleinstellungen eines Remotecomputers können nicht über eine Remoteverbindung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e468d-111">You cannot modify the Windows firewall settings of a remote computer over a remote connection.</span></span>  
  
 <span data-ttu-id="e468d-112">Wenn Sie die Remoteverwaltung für einen Benutzer aktivieren möchten, der kein Administrator ist, müssen Sie dem Konto DCOM-Remoteaktivierungsberechtigungen gewähren (Distributed Component Object Model).</span><span class="sxs-lookup"><span data-stu-id="e468d-112">If you want to enable remote administration for a non-administrator user, you must grant the account Distributed Component Object Model (DCOM) Remote Activation permissions.</span></span> <span data-ttu-id="e468d-113">Anweisungen zum Konfigurieren des Servers für den Zugriff durch Nichtadministratoren sind in diesem Thema enthalten.</span><span class="sxs-lookup"><span data-stu-id="e468d-113">Instructions for configuring the server for non-administrator access are provided in this topic.</span></span>  
  
 <span data-ttu-id="e468d-114">Einige Organisationen verfügen über Gruppenrichtlinien, durch die die Remoteserververwaltung für bestimmte Betriebssysteme oder Benutzer verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="e468d-114">Some organizations have group policies that prevent remote server administration for certain operating systems or users.</span></span> <span data-ttu-id="e468d-115">Bevor Sie die Firewalleinstellungen ändern, sollten Sie beim Netzwerkadministrator anfragen, ob Einschränkungen für die Remoteverwaltung vorliegen.</span><span class="sxs-lookup"><span data-stu-id="e468d-115">Before you begin modifying firewall settings, check with your network administrator to verify whether there are restrictions on remote administration.</span></span>  
  
 <span data-ttu-id="e468d-116">Weitere Informationen finden Sie unter [Connecting Through Windows Firewall](https://go.microsoft.com/fwlink/?LinkId=63615) in der Dokumentation zur Plattform MSDN.</span><span class="sxs-lookup"><span data-stu-id="e468d-116">For more information, see [Connecting Through Windows Firewall](https://go.microsoft.com/fwlink/?LinkId=63615) in the Platform SDK documentation on MSDN.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="e468d-117">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="e468d-117">Tasks</span></span>  
 <span data-ttu-id="e468d-118">Anhand folgender Tasks kann die Konfiguration des Remoteberichtsservers aktiviert werden:</span><span class="sxs-lookup"><span data-stu-id="e468d-118">Tasks that enable remote report server configuration include the following:</span></span>  
  
-   <span data-ttu-id="e468d-119">Ports in der Windows-Firewall aktivieren, um Anforderungen in Ports zuzulassen, die vom Berichtsserver und von der Instanz der SQL Server-Datenbank-Engine verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e468d-119">Enable ports in Windows Firewall to allow requests on ports used by the report server and by the SQL Server Database Engine instance.</span></span>  
  
-   <span data-ttu-id="e468d-120">Remoteverbindungen für die Instanz der Datenbank-Engine aktivieren, auf der die Berichtserver-Datenbank gehostet ist.</span><span class="sxs-lookup"><span data-stu-id="e468d-120">Enable remote connections to the instance of the Database Engine instance that hosts the report server database.</span></span> <span data-ttu-id="e468d-121">Eine Remoteverbindung ist zum Konfigurieren der Berichtsserver-Datenbankverbindung und zum Verwalten der Verschlüsselungsschlüssel erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e468d-121">A remote connection is necessary for configuring the report server database connection and managing the encryption keys.</span></span>  
  
-   <span data-ttu-id="e468d-122">Remote-WMI-Anforderungen aktivieren, sodass diese die [!INCLUDE[msCoName](../../includes/msconame-md.md)] -Windows-Firewall passieren können.</span><span class="sxs-lookup"><span data-stu-id="e468d-122">Enable remote WMI requests to pass through the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows firewall.</span></span>  
  
-   <span data-ttu-id="e468d-123">Wenn Sie einen Remoteberichtsserver für die Verwaltung durch einen Benutzer konfigurieren, der kein Administrator ist, müssen Sie die DCOM-Berechtigungen so einstellen, dass Remote-WMI-Zugriffe auf ein Standard-Windows-Benutzerkonto möglich sind.</span><span class="sxs-lookup"><span data-stu-id="e468d-123">If you are configuring a remote report server for administration by a non-administrative user, you must set DCOM permissions to enable remote WMI access to a standard Windows user account.</span></span> <span data-ttu-id="e468d-124">Da DCOM von der WMI als Transportmedium für Remoteaufrufe verwendet wird, müssen Sie die DCOM-Berechtigungen so festlegen, dass Benutzer, die nicht als lokaler Administrator angemeldet sind, den Server konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="e468d-124">Because WMI uses DCOM as transport for remote calls, you must set the DCOM permissions so that users who are not logged on as the local administrator can configure the server.</span></span>  
  
-   <span data-ttu-id="e468d-125">Wenn Sie einen Remoteberichtsserver für die Verwaltung durch einen Benutzer konfigurieren, der kein Administrator ist, müssen Sie außerdem die WMI-Berechtigungen auf den Berichtsserver-WMI-Namespace einstellen.</span><span class="sxs-lookup"><span data-stu-id="e468d-125">If you are configuring a remote report server for administration by a non-administrative user, you must also set WMI permissions on the report server WMI namespace.</span></span> <span data-ttu-id="e468d-126">In der Standardeinstellung haben alle Mitglieder der lokalen Administratorgruppe Zugriff auf den WMI-Namespace des Berichtsservers.</span><span class="sxs-lookup"><span data-stu-id="e468d-126">By default, all members of the local Administrator group have access to the report server WMI namespace.</span></span> <span data-ttu-id="e468d-127">Wenn Sie Nichtadministratoren Zugriff gewähren möchten, müssen Sie Berechtigungen festlegen.</span><span class="sxs-lookup"><span data-stu-id="e468d-127">If you want to grant access to non-administrators, you must set permissions.</span></span>  
  
 <span data-ttu-id="e468d-128">Anweisungen zum Ausführen dieser Tasks sind in diesem Thema enthalten.</span><span class="sxs-lookup"><span data-stu-id="e468d-128">Instructions on how to perform these tasks are provided in this topic.</span></span>  
  
### <a name="to-open-ports-in-windows-firewall"></a><span data-ttu-id="e468d-129">So öffnen Sie Ports in der Windows-Firewall</span><span class="sxs-lookup"><span data-stu-id="e468d-129">To open ports in Windows Firewall</span></span>  
  
1.  <span data-ttu-id="e468d-130">[Konfigurieren Sie eine Windows-Firewall für den Datenbank-Engine Zugriff](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md).</span><span class="sxs-lookup"><span data-stu-id="e468d-130">[Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md).</span></span>  
  
2.  <span data-ttu-id="e468d-131">[Konfigurieren einer Firewall für den Zugriff auf den Berichts Server](configure-a-firewall-for-report-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="e468d-131">[Configure a Firewall for Report Server Access](configure-a-firewall-for-report-server-access.md).</span></span>  
  
### <a name="to-configure-remote-connections-to-the-report-server-database"></a><span data-ttu-id="e468d-132">Konfigurieren von Remoteverbindungen für die Berichtsserver-Datenbank</span><span class="sxs-lookup"><span data-stu-id="e468d-132">To configure remote connections to the report server database</span></span>  
  
1.  <span data-ttu-id="e468d-133">Klicken Sie auf **Start**, zeigen Sie auf **Programme**, zeigen Sie auf [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], dann auf **Konfigurationstools**, und klicken Sie auf **SQL Server-Konfigurations-Manager**.</span><span class="sxs-lookup"><span data-stu-id="e468d-133">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="e468d-134">Erweitern Sie im linken Bereich den Eintrag **SQL Server-Netzwerkkonfiguration**, und klicken Sie dann für die Instanz von auf **Protokolle**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e468d-134">In the left pane, expand **SQL Server Network Configuration**, and then click **Protocols** for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="e468d-135">Aktivieren Sie im Detailbereich die Protokolle TCP/IP und Named Pipes, und starten Sie dann den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst neu.</span><span class="sxs-lookup"><span data-stu-id="e468d-135">In the details pane, enable the TCP/IP and Named Pipes protocols, and then restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
### <a name="to-enable-remote-administration-in-windows-firewall"></a><span data-ttu-id="e468d-136">Aktivieren der Remoteverwaltung in der Windows-Firewall</span><span class="sxs-lookup"><span data-stu-id="e468d-136">To enable remote administration in Windows Firewall</span></span>  
  
1.  <span data-ttu-id="e468d-137">Melden Sie sich als lokaler Administrator an dem Computer an, für den Sie die Remoteverwaltung aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e468d-137">Log on as a local administrator to the computer for which you want to enable remote administration.</span></span>  
  
2.  <span data-ttu-id="e468d-138">Wenn der Berichts Server unter Windows Vista ausgeführt wird, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung** , und wählen Sie **als Administrator ausführen**aus.</span><span class="sxs-lookup"><span data-stu-id="e468d-138">If the report server is running on Windows Vista, right-click **Command Prompt** and select **Run as administrator**.</span></span> <span data-ttu-id="e468d-139">Bei anderen Betriebssystemen öffnen Sie ein Fenster zur Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="e468d-139">For other operating systems, open a command prompt window.</span></span>  
  
3.  <span data-ttu-id="e468d-140">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="e468d-140">Run the following command:</span></span>  
  
    ```  
    netsh.exe firewall set service type=REMOTEADMIN mode=ENABLE scope=ALL  
    ```  
  
     <span data-ttu-id="e468d-141">Für Bereich können Sie verschiedene Optionen angeben.</span><span class="sxs-lookup"><span data-stu-id="e468d-141">You can specify different options for Scope.</span></span> <span data-ttu-id="e468d-142">Weitere Informationen finden Sie in der Produktdokumentation zur Windows-Firewall.</span><span class="sxs-lookup"><span data-stu-id="e468d-142">For more information, see the Windows Firewall product documentation.</span></span>  
  
4.  <span data-ttu-id="e468d-143">Überprüfen Sie, ob die Remoteverwaltung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e468d-143">Verify that remote administration is enabled.</span></span> <span data-ttu-id="e468d-144">Sie können den folgenden Befehl ausführen, um den Status anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="e468d-144">You can run the following command to show the status:</span></span>  
  
    ```  
    netsh.exe firewall show state  
    ```  
  
5.  <span data-ttu-id="e468d-145">Starten Sie den Computer neu.</span><span class="sxs-lookup"><span data-stu-id="e468d-145">Reboot the computer.</span></span>  
  
### <a name="to-set-dcom-permissions-to-enable-remote-wmi-access-for-non-administrators"></a><span data-ttu-id="e468d-146">So legen Sie DCOM-Berechtigungen zum Aktivieren des WMI-Remotezugriffs für Nichtadministratoren fest</span><span class="sxs-lookup"><span data-stu-id="e468d-146">To set DCOM permissions to enable remote WMI access for non-administrators</span></span>  
  
1.  <span data-ttu-id="e468d-147">Zeigen Sie im Menü Start auf **Verwaltung**, und klicken Sie auf **Komponentendienste**.</span><span class="sxs-lookup"><span data-stu-id="e468d-147">On the Start menu, point to **Administrative Tools**, click **Component Services**.</span></span>  
  
     <span data-ttu-id="e468d-148">Für Windows Vista klicken Sie im Startmenü auf **Alle Programme**, klicken Sie auf **Ausführen**, und geben Sie dann ein `mmc comexp.msc` .</span><span class="sxs-lookup"><span data-stu-id="e468d-148">For Windows Vista, on the Start menu, click **All Programs**, click **Run**, and then enter `mmc comexp.msc`.</span></span>  
  
2.  <span data-ttu-id="e468d-149">Öffnen Sie den Ordner Komponentendienste.</span><span class="sxs-lookup"><span data-stu-id="e468d-149">Open the Component Services folder.</span></span>  
  
3.  <span data-ttu-id="e468d-150">Öffnen Sie den Ordner Computer.</span><span class="sxs-lookup"><span data-stu-id="e468d-150">Open the Computers folder.</span></span>  
  
4.  <span data-ttu-id="e468d-151">Wählen Sie Arbeitsplatz aus.</span><span class="sxs-lookup"><span data-stu-id="e468d-151">Select My Computer.</span></span>  
  
5.  <span data-ttu-id="e468d-152">Wählen Sie im Menü **Aktion** die Option **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="e468d-152">On the **Action** menu, and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="e468d-153">Klicken Sie auf **COM-Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="e468d-153">Click **COM Security**.</span></span>  
  
7.  <span data-ttu-id="e468d-154">Klicken Sie unter **Start- und Aktivierungsberechtigungen**auf **Limits bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="e468d-154">In **Launch and Activation Permissions**, click **Edit Limits**.</span></span>  
  
8.  <span data-ttu-id="e468d-155">Wenn Ihr Name unter **Startberechtigung**nicht angezeigt wird, klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e468d-155">If you do not see your name in **Launch Permission**, click **Add**.</span></span>  
  
9. <span data-ttu-id="e468d-156">Geben Sie den Namen Ihres Benutzerkontos ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e468d-156">Type the name of your user account, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="e468d-157">Wählen Sie unter \*\*Berechtigungen für \<User or Group> \*\*in der Spalte **zulassen** die Option **Remote Start** und **Remote Aktivierung**aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e468d-157">In **Permissions for \<User or Group>**, in the **Allow** column, select **Remote Launch** and **Remote Activation**, and then click **OK**.</span></span>  
  
### <a name="to-set-permissions-on-the-report-server-wmi-namespace-for-non-administrators"></a><span data-ttu-id="e468d-158">Festlegen von Berechtigungen für den Berichtsserver-WMI-Namespace für Nichtadministratoren</span><span class="sxs-lookup"><span data-stu-id="e468d-158">To set permissions on the report server WMI namespace for non-administrators</span></span>  
  
1.  <span data-ttu-id="e468d-159">Zeigen Sie im Menü Start auf **Verwaltung**, und klicken Sie auf **Computerverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="e468d-159">On the Start menu, point to **Administrative Tools**, click **Computer Management**.</span></span>  
  
2.  <span data-ttu-id="e468d-160">Öffnen Sie den Ordner Dienste und Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="e468d-160">Open the Services and Applications folder.</span></span>  
  
3.  <span data-ttu-id="e468d-161">Klicken Sie mit der rechten Maustaste auf **WMI-Steuerung**, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="e468d-161">Right-click **WMI Control**, and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="e468d-162">Klicken Sie auf **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="e468d-162">Click **Security**.</span></span>  
  
5.  <span data-ttu-id="e468d-163">Öffnen Sie den Stammordner.</span><span class="sxs-lookup"><span data-stu-id="e468d-163">Open the Root folder.</span></span>  
  
6.  <span data-ttu-id="e468d-164">Öffnen Sie den Ordner Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e468d-164">Open the Microsoft folder.</span></span>  
  
7.  <span data-ttu-id="e468d-165">Öffnen Sie den Ordner SQLServer.</span><span class="sxs-lookup"><span data-stu-id="e468d-165">Open the SQLServer folder.</span></span>  
  
8.  <span data-ttu-id="e468d-166">Öffnen Sie den Ordner ReportServer.</span><span class="sxs-lookup"><span data-stu-id="e468d-166">Open the ReportServer folder.</span></span>  
  
9. <span data-ttu-id="e468d-167">Öffnen Sie den Ordner Instanz.</span><span class="sxs-lookup"><span data-stu-id="e468d-167">Open instance folder.</span></span> <span data-ttu-id="e468d-168">Wenn Sie die Standardinstanz installiert haben, ist der Ordner MSSQLSERVER.</span><span class="sxs-lookup"><span data-stu-id="e468d-168">If you installed the default instance, the folder is MSSQLSERVER.</span></span>  
  
10. <span data-ttu-id="e468d-169">Öffnen Sie den Ordner v10</span><span class="sxs-lookup"><span data-stu-id="e468d-169">Open the v10 folder.</span></span>  
  
11. <span data-ttu-id="e468d-170">Wählen Sie den Ordner Admin aus, und klicken Sie dann auf **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="e468d-170">Select the Admin folder, and then click **Security**.</span></span>  
  
12. <span data-ttu-id="e468d-171">Klicken Sie auf **Hinzufügen**, und geben Sie anschließend das Benutzerkonto ein, das Sie zum Verwalten des Servers verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="e468d-171">Click **Add**, and then type the user account you will use to manage the server.</span></span>  
  
13. <span data-ttu-id="e468d-172">Aktivieren Sie in der Spalte **Zulassen** die Optionen **Konto aktivieren**, **Remoteaktivierung**und **Sicherheit lesen**, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e468d-172">In the **Allow** column, select **Enable Account**, **Remote Enable**, and **Read Security**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e468d-173">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e468d-173">See Also</span></span>  
 [<span data-ttu-id="e468d-174">Reporting Services-Konfigurations-Manager &#40;einheitlicher Modus&#41;</span><span class="sxs-lookup"><span data-stu-id="e468d-174">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)  
  
  
