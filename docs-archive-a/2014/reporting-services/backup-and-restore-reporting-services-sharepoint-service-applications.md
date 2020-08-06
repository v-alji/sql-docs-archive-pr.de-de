---
title: Sichern und Wiederherstellen Reporting Services SharePoint-Dienst Anwendungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: dfb4ed77-90e5-4273-b690-89a945508ed2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 488659d269542381be9bcf1b1b6115acf89f8a98
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617814"
---
# <a name="backup-and-restore-reporting-services-sharepoint-service-applications"></a><span data-ttu-id="6b71f-102">Sichern und Wiederherstellen von Reporting Services-SharePoint-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="6b71f-102">Backup and Restore Reporting Services SharePoint Service Applications</span></span>
  <span data-ttu-id="6b71f-103">In diesem Thema wird das Sichern und Wiederherstellen einer [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Dienstanwendung mit der SharePoint-Zentraladministration oder PowerShell beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6b71f-103">This topic describes how to backup and restore a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] services application using SharePoint Central Administration or PowerShell.</span></span> <span data-ttu-id="6b71f-104">Das Thema enthält:</span><span class="sxs-lookup"><span data-stu-id="6b71f-104">The topic contains:</span></span>  
  
-   [<span data-ttu-id="6b71f-105">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="6b71f-105">Limitations and Restrictions</span></span>](#bkmk_Restrictions)  
  
-   [<span data-ttu-id="6b71f-106">Sichern der Dienst Anwendung</span><span class="sxs-lookup"><span data-stu-id="6b71f-106">Backup The Service application</span></span>](#bkmk_backup)  
  
-   [<span data-ttu-id="6b71f-107">Wiederherstellen der Dienst Anwendung</span><span class="sxs-lookup"><span data-stu-id="6b71f-107">Restore the Service Application</span></span>](#bkmk_restore)  
  
##  <a name="before-you-begin"></a><a name="bkmk_BeforeYouBegin"></a> <span data-ttu-id="6b71f-108">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="6b71f-108">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="bkmk_Restrictions"></a> <span data-ttu-id="6b71f-109">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="6b71f-109">Limitations and Restrictions</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]<span data-ttu-id="6b71f-110">-Dienstanwendungen können teilweise mithilfe der SharePoint-Funktionen zum Sichern und Wiederherstellen gesichert und wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6b71f-110">service applications can partially be backed up and restored using the SharePoint backup and restore functionality.</span></span> <span data-ttu-id="6b71f-111">**Zusätzliche Schritte sind erforderlich** , und die Schritte werden in diesem Thema dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="6b71f-111">**Additional steps are required** and the steps are documented in this topic.</span></span> <span data-ttu-id="6b71f-112">Derzeit lassen sich auf Basis des Sicherungsprozesses **keine** Verschlüsselungsschlüssel und Anmeldeinformationen für Konten mit unbeaufsichtigter Ausführung oder Windows-Authentifizierung für die [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Datenbank sichern.</span><span class="sxs-lookup"><span data-stu-id="6b71f-112">Currently the backup process **does not** backup encryption keys and credentials for unattended execution accounts (UEA) or windows authentication to the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] database.</span></span>  
  
###  <a name="recommendations"></a><a name="bkmk_recommendations"></a> <span data-ttu-id="6b71f-113">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="6b71f-113">Recommendations</span></span>  
  
-   <span data-ttu-id="6b71f-114">Sichern Sie die Verschlüsselungsschlüssel vor dem Starten der SharePoint-Sicherung.</span><span class="sxs-lookup"><span data-stu-id="6b71f-114">Backup the encryption keys before starting the SharePoint backup.</span></span> <span data-ttu-id="6b71f-115">Wenn Sie die Verschlüsselungsschlüssel nicht sichern, ist der Zugriff auf die verschlüsselten Daten nach der Wiederherstellung der Dienstanwendung nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="6b71f-115">If you do not backup the encryption keys, then you will not be able to access your encrypted data, following the restore of the service application.</span></span> <span data-ttu-id="6b71f-116">Sie müssen die verschlüsselten Daten löschen.</span><span class="sxs-lookup"><span data-stu-id="6b71f-116">You will need to delete your encrypted data.</span></span>  
  
-   <span data-ttu-id="6b71f-117">Überprüfen Sie, ob die [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Dienstanwendung Konten mit unbeaufsichtigter Ausführung oder Windows-Authentifizierung für den Datenbankzugriff verwendet.</span><span class="sxs-lookup"><span data-stu-id="6b71f-117">Verify if your [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application is using UEA or Windows authentication for database access.</span></span> <span data-ttu-id="6b71f-118">Bei Verwendung einer dieser Kontotypen sind die entsprechenden Anmeldeinformationen zu ermitteln, damit Sie die Dienstanwendung nach der Wiederherstellung richtig konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="6b71f-118">If it is using either, verify what the proper credentials are so you can correctly configure the service application after the restore process.</span></span>  
  
-   <span data-ttu-id="6b71f-119">Stellen Sie sicher, dass das SharePoint-Sicherungsprotokoll im gleichen Ordner wie die Sicherungsdatei erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="6b71f-119">Review the SharePoint backup log is created in the same folder as the backup file.</span></span> <span data-ttu-id="6b71f-120">Die Datei wird in der Regel **spbackup.log**genannt.</span><span class="sxs-lookup"><span data-stu-id="6b71f-120">The file is typically named **spbackup.log**</span></span>  
  
##  <a name="backup-the-service-application"></a><a name="bkmk_backup"></a><span data-ttu-id="6b71f-121">Sichern der Dienst Anwendung</span><span class="sxs-lookup"><span data-stu-id="6b71f-121">Backup The Service application</span></span>  
 <span data-ttu-id="6b71f-122">Führen Sie die folgenden Schritte wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="6b71f-122">Complete the following steps in order:</span></span>  
  
1.  <span data-ttu-id="6b71f-123">Sichern der Verschlüsselungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="6b71f-123">Backup the encryption keys</span></span>  
  
2.  <span data-ttu-id="6b71f-124">Sichern der Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="6b71f-124">Backup the Service application</span></span>  
  
3.  <span data-ttu-id="6b71f-125">Überprüfen Sie, ob die Dienstanwendung ein Konto mit unbeaufsichtigter Ausführung oder Windows-Authentifizierung für den Datenbankzugriff verwendet.</span><span class="sxs-lookup"><span data-stu-id="6b71f-125">Verify if you service application uses an UEA or Windows authentication for database access.</span></span> <span data-ttu-id="6b71f-126">Bei Verwendung einer dieser Kontotypen müssen Sie sich die Anmeldeinformationen notieren, damit Sie die Dienstanwendung nach der Wiederherstellung konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="6b71f-126">If it does, make a note of the credentials so you can use them to configure the service application after it is restored.</span></span>  
  
### <a name="backup-the-encryption-keys-using-central-administration"></a><span data-ttu-id="6b71f-127">Sichern der Verschlüsselungsschlüssel mit der Zentraladministration</span><span class="sxs-lookup"><span data-stu-id="6b71f-127">Backup the Encryption Keys using Central Administration</span></span>  
 <span data-ttu-id="6b71f-128">Informationen zum Sichern der [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Verschlüsselungsschlüssel finden Sie im Abschnitt "Verschlüsselungsschlüssel" unter [Verwalten einer Reporting Services SharePoint-Dienst Anwendung](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="6b71f-128">For information on backing up the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] encryption keys, see the "Encryption Keys" section of [Manage a Reporting Services SharePoint Service Application](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md).</span></span>  
  
###  <a name="backup-the-service-application-using-sharepoint-central-administration"></a><a name="bkmk_centraladmin"></a> <span data-ttu-id="6b71f-129">Sichern der Dienstanwendung mit der SharePoint-Zentraladministration</span><span class="sxs-lookup"><span data-stu-id="6b71f-129">Backup the Service application Using SharePoint Central Administration</span></span>  
 <span data-ttu-id="6b71f-130">So sichern Sie die Dienstanwendung:</span><span class="sxs-lookup"><span data-stu-id="6b71f-130">To back up the Service Application, complete the following steps:</span></span>  
  
1.  <span data-ttu-id="6b71f-131">Klicken Sie in der Gruppe **Sichern und Wiederherstellen** der SharePoint-Zentraladministration auf **Sicherung durchführen** .</span><span class="sxs-lookup"><span data-stu-id="6b71f-131">In SharePoint Central Administration Click **Perform a backup** in the **Backup and Restore** group.</span></span>  
  
2.  <span data-ttu-id="6b71f-132">Erweitern Sie unter dem Knoten **Gemeinsame Dienste** die Option für **gemeinsame Dienstanwendungen** , und wählen Sie die Dienstanwendung aus.</span><span class="sxs-lookup"><span data-stu-id="6b71f-132">Under the **Shared Services** node, expand **Shared Service Applications** and select your service application.</span></span> <span data-ttu-id="6b71f-133">Sie weist einen Typ von **SQL Server Reporting Services-Dienstanwendung**auf.</span><span class="sxs-lookup"><span data-stu-id="6b71f-133">It will have a type of **SQL Server Reporting Services Service Application**.</span></span>  
  
3.  <span data-ttu-id="6b71f-134">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="6b71f-134">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="6b71f-135">Geben Sie im Feld **Sicherungsspeicherort:** den Pfad für den Speicherort an, und klicken Sie auf **Sicherung starten**.</span><span class="sxs-lookup"><span data-stu-id="6b71f-135">Type the path for the **Backup location:** and click **Start Backup**</span></span>  
  
5.  <span data-ttu-id="6b71f-136">Wiederholen Sie den oben beschriebenen Prozess. Erweitern Sie jedoch anstelle der Auswahl der Dienstanwendung den Knoten **Proxys der gemeinsamen Dienste** , und wählen Sie den Dienstanwendungsproxy aus.</span><span class="sxs-lookup"><span data-stu-id="6b71f-136">Repeat the process above but instead of selecting the service application, expand the **Shared Services Proxies** node, and select service application proxy.</span></span> <span data-ttu-id="6b71f-137">Er weist einen Typ von **Proxy für die SQL Server Reporting Services-Dienstanwendung**auf.</span><span class="sxs-lookup"><span data-stu-id="6b71f-137">It will have a type of **SQL Server Reporting Services Service Application Proxy**.</span></span>  
  
 <span data-ttu-id="6b71f-138">Weitere Information finden Sie in den folgenden Themen in der SharePoint-Dokumentation:</span><span class="sxs-lookup"><span data-stu-id="6b71f-138">For more information, see the following topics in the SharePoint documentation:</span></span>  
  
 <span data-ttu-id="6b71f-139">[Sichern einer Dienstanwendung (SharePoint Foundation 2010)](https://msdn.microsoft.com/library/ee748601.aspx)in der SharePoint-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="6b71f-139">[Back up a service application (SharePoint Foundation 2010) in the SharePoint documenttation](https://msdn.microsoft.com/library/ee748601.aspx).</span></span>  
  
 [<span data-ttu-id="6b71f-140">Sichern einer Dienstanwendung (SharePoint Server 2010)</span><span class="sxs-lookup"><span data-stu-id="6b71f-140">Back up a service application (SharePoint Server 2010)</span></span>](https://technet.microsoft.com/library/ee428318.aspx)  
  
### <a name="verify-execution-account-and-database-authentication"></a><span data-ttu-id="6b71f-141">Überprüfen der Kontoausführung und Datenbankauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="6b71f-141">Verify Execution Account and Database Authentication</span></span>  
 <span data-ttu-id="6b71f-142">**Ausführungskonto:** So überprüfen Sie, ob die Dienstanwendung ein Ausführungskonto verwendet:</span><span class="sxs-lookup"><span data-stu-id="6b71f-142">**Execution Account:** To verify if your service application is using an execution account:</span></span>  
  
1.  <span data-ttu-id="6b71f-143">Klicken Sie in der SharePoint-zentral Administration in der Gruppe **Anwendungs Verwaltung** auf **Dienst Anwendungen verwalten** .</span><span class="sxs-lookup"><span data-stu-id="6b71f-143">In SharePoint Central Administration, click **Manage Service Applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="6b71f-144">Klicken Sie auf den Namen der Dienstanwendung und dann im SharePoint-Menüband auf **Verwalten** .</span><span class="sxs-lookup"><span data-stu-id="6b71f-144">Click the name of your service application and then click **Manage** in the SharePoint Ribbon.</span></span>  
  
3.  <span data-ttu-id="6b71f-145">Klicken Sie auf **Ausführungskonto**.</span><span class="sxs-lookup"><span data-stu-id="6b71f-145">Click **Execution Account**.</span></span>  
  
4.  <span data-ttu-id="6b71f-146">Ist ein Ausführungskonto konfiguriert, müssen Ihnen die Anmeldeinformationen bekannt sein, um die Sicherung der Dienstanwendung wiederherstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="6b71f-146">If an execution account is configured, you need to know the credentials when it is time to restore the service application backup.</span></span> <span data-ttu-id="6b71f-147">Fahren Sie erst mit der Sicherungs- und Wiederherstellungsprozedur fort, wenn Sie die richtigen Anmeldeinformationen kennen.</span><span class="sxs-lookup"><span data-stu-id="6b71f-147">Do not proceed with the backup and restore procedure until you know the correct credentials.</span></span>  
  
 <span data-ttu-id="6b71f-148">**Datenbankauthentifizierung** : So überprüfen Sie, ob die Dienstanwendung die Windows-Authentifizierung für die Datenbankauthentifizierung verwendet:</span><span class="sxs-lookup"><span data-stu-id="6b71f-148">**Database Authentication:** To verify if your service application is using Windows Authentication for the database authentication:</span></span>  
  
1.  <span data-ttu-id="6b71f-149">Klicken Sie in der SharePoint-zentral Administration in der Gruppe **Anwendungs Verwaltung** auf **Dienst Anwendungen verwalten** .</span><span class="sxs-lookup"><span data-stu-id="6b71f-149">In SharePoint Central Administration, click **Manage Service Applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="6b71f-150">Klicken Sie auf den Namen der Dienstanwendung und dann im SharePoint-Menüband auf **Eigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="6b71f-150">Click the name of your service application and then click **Properties** in the SharePoint Ribbon.</span></span>  
  
3.  <span data-ttu-id="6b71f-151">Lesen Sie den Abschnitt **Reporting Services-Dienstdatenbank (SSRS)** .</span><span class="sxs-lookup"><span data-stu-id="6b71f-151">Review the **Reporting Services (SSRS) Service Database** section.</span></span>  
  
4.  <span data-ttu-id="6b71f-152">Ist die Windows-Authentifizierung konfiguriert, müssen Ihnen die Anmeldeinformationen bekannt sein, um die Dienstanwendung nach der Wiederherstellung konfigurieren zu können.</span><span class="sxs-lookup"><span data-stu-id="6b71f-152">If Windows Authentication is configured, you need to know the credentials so you can configure the service application after you restore it.</span></span> <span data-ttu-id="6b71f-153">Fahren Sie erst mit der Sicherungs- und Wiederherstellungsprozedur fort, wenn Sie die richtigen Anmeldeinformationen kennen.</span><span class="sxs-lookup"><span data-stu-id="6b71f-153">Do not proceed with the backup and restore procedure until you know the correct credentials.</span></span>  
  
##  <a name="restore-the-service-application"></a><a name="bkmk_restore"></a><span data-ttu-id="6b71f-154">Wiederherstellen der Dienst Anwendung</span><span class="sxs-lookup"><span data-stu-id="6b71f-154">Restore the Service Application</span></span>  
 <span data-ttu-id="6b71f-155">Führen Sie die folgenden Schritte wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="6b71f-155">Complete the following steps in order:</span></span>  
  
1.  <span data-ttu-id="6b71f-156">Stellen Sie die [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Dienstanwendung wieder her.</span><span class="sxs-lookup"><span data-stu-id="6b71f-156">Restore the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>  
  
2.  <span data-ttu-id="6b71f-157">Wiederherstellen der Verschlüsselungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="6b71f-157">Restore the encryption keys</span></span>  
  
3.  <span data-ttu-id="6b71f-158">Wurde für die Dienstanwendung ein Ausführungskonto oder die Windows-Authentifizierung für den Datenbankzugriff verwendet, konfigurieren Sie die Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="6b71f-158">If your service application was using an execution account or Windows authentication for database access, configure the credentials.</span></span>  
  
### <a name="restore-the-service-application-using-sharepoint-central-administration"></a><span data-ttu-id="6b71f-159">Wiederherstellen der Dienstanwendung mit der SharePoint-Zentraladministration</span><span class="sxs-lookup"><span data-stu-id="6b71f-159">Restore the Service application Using SharePoint Central Administration</span></span>  
  
1.  <span data-ttu-id="6b71f-160">Klicken Sie in der Gruppe **Sichern und Wiederherstellen** der SharePoint-Zentraladministration auf die Option zum Wiederherstellen aus einer Sicherung \*\*\*\* .</span><span class="sxs-lookup"><span data-stu-id="6b71f-160">In SharePoint Central Administration Click **Restore from a backup** in the **Backup and Restore** group.</span></span>  
  
2.  <span data-ttu-id="6b71f-161">Geben Sie in das Feld für den Sicherungsverzeichnisspeicherort \*\*\*\* den Pfad für die Sicherungsdatei ein, und klicken Sie auf **Aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="6b71f-161">Type the path to your backup file in **Backup Directory Location** box and click **Refresh**.</span></span>  
  
3.  <span data-ttu-id="6b71f-162">Wählen Sie die Dienstanwendungssicherung aus der Liste **Komponente der höchsten Ebene** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="6b71f-162">Select your service application backup from the **Top Component** list and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="6b71f-163">Wählen Sie die [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Anwendung aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="6b71f-163">Select your [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] application and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="6b71f-164">Geben Sie im Abschnitt **Anmeldenamen und Kennwörter** das Kennwort für den Anmeldenamen ein.</span><span class="sxs-lookup"><span data-stu-id="6b71f-164">In the **Login Names and Passwords** section type the password for the login name.</span></span> <span data-ttu-id="6b71f-165">Das Feld für den Anmeldenamen muss mit der Anmeldung ausgefüllt werden, die von der Dienstanwendung vor der Sicherung verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="6b71f-165">The login name box should be populated with the login the service application was using prior to the backup.</span></span>  
  
6.  <span data-ttu-id="6b71f-166">Klicken Sie auf **Wiederherstellung starten**.</span><span class="sxs-lookup"><span data-stu-id="6b71f-166">Click **Start Restore**.</span></span>  
  
7.  <span data-ttu-id="6b71f-167">Wiederholen Sie den oben beschriebenen Prozess. Erweitern Sie jedoch anstelle der Wiederherstellung der Dienstanwendung den Knoten **Gemeinsame Dienste** , und erweitern Sie anschließend den Knoten für **gemeinsame Dienstanwendungen** .</span><span class="sxs-lookup"><span data-stu-id="6b71f-167">Repeat the process above but instead of restoring the service application, expand the **Shared Services** node and then expand the **Shared Service Applications** node.</span></span>  
  
 <span data-ttu-id="6b71f-168">Weitere Information finden Sie in den folgenden Themen in der SharePoint-Dokumentation:</span><span class="sxs-lookup"><span data-stu-id="6b71f-168">For more information, see the following topics in the SharePoint documentation:</span></span>  
  
 <span data-ttu-id="6b71f-169">[Wiederherstellen einer Dienstanwendung (SharePoint Foundation 2010)](https://msdn.microsoft.com/library/ee748615.aspx)</span><span class="sxs-lookup"><span data-stu-id="6b71f-169">[Restore a service application (SharePoint Foundation 2010)](https://msdn.microsoft.com/library/ee748615.aspx).</span></span>  
  
 <span data-ttu-id="6b71f-170">[Wiederherstellen einer Dienstanwendung (SharePoint Server 2010)](https://technet.microsoft.com/library/ee428305.aspx)</span><span class="sxs-lookup"><span data-stu-id="6b71f-170">[Restore a service application (SharePoint Server 2010)](https://technet.microsoft.com/library/ee428305.aspx).</span></span>  
  
### <a name="restore-the-encryption-keys-using-central-administration"></a><span data-ttu-id="6b71f-171">Wiederherstellen der Verschlüsselungsschlüssel mit der Zentraladministration</span><span class="sxs-lookup"><span data-stu-id="6b71f-171">Restore the Encryption Keys using Central Administration</span></span>  
 <span data-ttu-id="6b71f-172">Informationen zum Wiederherstellen der [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Verschlüsselungsschlüssel finden Sie im Abschnitt "Verschlüsselungsschlüssel" unter [Verwalten einer Reporting Services SharePoint-Dienst Anwendung](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="6b71f-172">For information on restoring the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] encryption keys, see the "Encryption Keys" section of [Manage a Reporting Services SharePoint Service Application](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md).</span></span>  
  
### <a name="configure-the-execution-account-and-database-authentication"></a><span data-ttu-id="6b71f-173">Konfigurieren des Ausführungskontos und der Datenbankauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="6b71f-173">Configure the Execution Account and Database Authentication</span></span>  
 <span data-ttu-id="6b71f-174">**Ausführungskonto** : Wurde für die Dienstanwendung ein Ausführungskonto verwendet, gehen Sie zum Konfigurieren des Kontos wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="6b71f-174">**Execution Account:** If your service application was using an execution account complete the following steps to configure it:</span></span>  
  
1.  <span data-ttu-id="6b71f-175">Klicken Sie in der SharePoint-zentral Administration in der Gruppe **Anwendungs Verwaltung** auf **Dienst Anwendungen verwalten** .</span><span class="sxs-lookup"><span data-stu-id="6b71f-175">In SharePoint Central Administration, click **Manage Service Applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="6b71f-176">Klicken Sie auf den Namen der Dienstanwendung und dann im SharePoint-Menüband auf **Verwalten** .</span><span class="sxs-lookup"><span data-stu-id="6b71f-176">Click the name of your service application and then click **Manage** in the SharePoint Ribbon.</span></span>  
  
3.  <span data-ttu-id="6b71f-177">Klicken Sie auf **Ausführungskonto**.</span><span class="sxs-lookup"><span data-stu-id="6b71f-177">Click **Execution Account**.</span></span>  
  
4.  <span data-ttu-id="6b71f-178">Geben Sie das Konto und Kennwort ein, und wählen Sie das Feld **Ausführungskonto angeben** aus.</span><span class="sxs-lookup"><span data-stu-id="6b71f-178">Type the account, password, and select the **Specify and Execution Account** box.</span></span>  
  
5.  <span data-ttu-id="6b71f-179">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6b71f-179">Click **OK**.</span></span>  
  
 <span data-ttu-id="6b71f-180">**Datenbankauthentifizierung** : Wenn für die Dienstanwendung die Windows-Authentifizierung zur Datenbankauthentifizierung verwendet wurde, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="6b71f-180">**Database Authentication:** If your service application was using Windows Authentication for the database authentication complete the following steps:</span></span>  
  
1.  <span data-ttu-id="6b71f-181">Klicken Sie in der SharePoint-zentral Administration in der Gruppe **Anwendungs Verwaltung** auf **Dienst Anwendungen verwalten** .</span><span class="sxs-lookup"><span data-stu-id="6b71f-181">In SharePoint Central Administration click **Manage Service Applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="6b71f-182">Klicken Sie auf den Namen der Dienstanwendung und dann im SharePoint-Menüband auf **Eigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="6b71f-182">Click the name of your service application and then click **Properties** in the SharePoint Ribbon.</span></span>  
  
3.  <span data-ttu-id="6b71f-183">Lesen Sie den Abschnitt **Reporting Services-Dienstdatenbank (SSRS)** .</span><span class="sxs-lookup"><span data-stu-id="6b71f-183">Review the **Reporting Services (SSRS) Service Database** section.</span></span>  
  
4.  <span data-ttu-id="6b71f-184">Wählen Sie **Windows-Authentifizierung** aus.</span><span class="sxs-lookup"><span data-stu-id="6b71f-184">Select **Windows Authentication**.</span></span>  
  
5.  <span data-ttu-id="6b71f-185">Geben Sie das Konto und Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="6b71f-185">Type the account and password.</span></span> <span data-ttu-id="6b71f-186">Wählen Sie ggf. die Option **Windows-Anmeldeinformationen verwenden** aus.</span><span class="sxs-lookup"><span data-stu-id="6b71f-186">Select **Use as Windows Credentials** if appropriate.</span></span>  
  
6.  <span data-ttu-id="6b71f-187">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6b71f-187">Click **Ok**</span></span>  
  
  
