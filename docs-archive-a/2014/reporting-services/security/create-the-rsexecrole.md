---
title: Erstellen der Rolle „RSExecRole“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- RSExecRole
ms.assetid: 7ac17341-df7e-4401-870e-652caa2859c0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0037ef0c4d7a949b5a30bb45356613f6114db130
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699290"
---
# <a name="create-the-rsexecrole"></a><span data-ttu-id="4c93d-102">Erstellen der Rolle RSExecRole</span><span class="sxs-lookup"><span data-stu-id="4c93d-102">Create the RSExecRole</span></span>
  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="4c93d-103">verwendet eine vordefinierte Datenbankrolle namens `RSExecRole`, um Berichtsserverberechtigungen für die Berichtsserver-Datenbank zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="4c93d-103">uses a predefined database role called `RSExecRole` to grant report server permissions to the report server database.</span></span> <span data-ttu-id="4c93d-104">Die `RSExecRole` Rolle wird automatisch mit der Berichts Server-Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="4c93d-104">The `RSExecRole` role is created automatically with the report server database.</span></span> <span data-ttu-id="4c93d-105">Als Faustregel gilt, dass Sie sie nie ändern und ihr keine anderen Benutzer zuweisen sollten.</span><span class="sxs-lookup"><span data-stu-id="4c93d-105">As a rule, you should never modify it or assign other users to the role.</span></span> <span data-ttu-id="4c93d-106">Wenn Sie jedoch eine Berichts Server-Datenbank in eine neue oder andere verschieben [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../../includes/ssde-md.md)] , muss die Rolle in den System Datenbanken Master und msdb neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4c93d-106">However, when you move a report server database to a new or different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../../includes/ssde-md.md)], must re-create the role in the Master and MSDB system databases.</span></span>

 <span data-ttu-id="4c93d-107">Mithilfe der folgenden Anweisungen führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="4c93d-107">Using the following instructions, you will perform the following steps:</span></span>

-   <span data-ttu-id="4c93d-108">Erstellen Sie die Rolle `RSExecRole` und stellen Sie sie in der Systemdatenbank Master bereit.</span><span class="sxs-lookup"><span data-stu-id="4c93d-108">Create and provision the `RSExecRole` in the Master system database.</span></span>

-   <span data-ttu-id="4c93d-109">Erstellen Sie die Rolle `RSExecRole` und stellen Sie sie in der Systemdatenbank MSDB bereit.</span><span class="sxs-lookup"><span data-stu-id="4c93d-109">Create and provision the `RSExecRole` in the MSDB system database.</span></span>

> [!NOTE]
>  <span data-ttu-id="4c93d-110">Die Anweisungen in diesem Thema sind für Benutzer vorgesehen, die zur Bereitstellung der Berichtsserver-Datenbank kein Skript ausführen oder WMI-Code schreiben möchten.</span><span class="sxs-lookup"><span data-stu-id="4c93d-110">The instructions in this topic are intended for users who do not want to run a script or write WMI code to provision the report server database.</span></span> <span data-ttu-id="4c93d-111">Wenn Sie eine umfangreiche Bereitstellung verwalten und regelmäßig Datenbanken verschieben, sollten Sie ein Skript zur Automatisierung dieser Schritte schreiben.</span><span class="sxs-lookup"><span data-stu-id="4c93d-111">If you manage a large deployment and will be moving databases routinely, you should write a script to automate these steps.</span></span> <span data-ttu-id="4c93d-112">Weitere Informationen finden Sie unter [Zugreifen auf den Reporting Services-WMI-Anbieter](../tools/access-the-reporting-services-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="4c93d-112">For more information, see [Access the Reporting Services WMI Provider](../tools/access-the-reporting-services-wmi-provider.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="4c93d-113">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="4c93d-113">Before you start</span></span>

-   <span data-ttu-id="4c93d-114">Sichern Sie die Verschlüsselungsschlüssel, damit Sie sie wiederherstellen können, nachdem die Datenbank verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="4c93d-114">Back up the encryption keys so that you can restore them after the database is moved.</span></span> <span data-ttu-id="4c93d-115">Dieser Schritt wirkt sich nicht direkt auf die Erstellung oder Bereitstellung der Rolle `RSExecRole` aus. Sie müssen jedoch über eine Sicherung der Schlüssel verfügen, um die durchgeführten Schritte verifizieren zu können.</span><span class="sxs-lookup"><span data-stu-id="4c93d-115">This is step does not directly affect your ability to create and provision the `RSExecRole`, but you must have a backup of the keys in order to verify your work.</span></span> <span data-ttu-id="4c93d-116">Weitere Informationen finden Sie unter [Back Up and Restore Reporting Services Encryption Keys](../install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md).</span><span class="sxs-lookup"><span data-stu-id="4c93d-116">For more information, see [Back Up and Restore Reporting Services Encryption Keys](../install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md).</span></span>

-   <span data-ttu-id="4c93d-117">Überzeugen Sie sich davon, dass Sie unter einem Benutzerkonto angemeldet sind, das über `sysadmin`-Berechtigungen für die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Instanz verfügt.</span><span class="sxs-lookup"><span data-stu-id="4c93d-117">Verify you are logged on as a user account that has `sysadmin` permissions on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span>

-   <span data-ttu-id="4c93d-118">Überprüfen Sie, ob der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Agent-Dienst installiert wurde und auf der Instanz der [!INCLUDE[ssDE](../../../includes/ssde-md.md)] -Instanz ausgeführt wird, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="4c93d-118">Verify [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent service is installed and running on the instance of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] instance that you plan to use.</span></span>

-   <span data-ttu-id="4c93d-119">Fügen Sie die Datenbanken reportservertempdb und reportserver an.</span><span class="sxs-lookup"><span data-stu-id="4c93d-119">Attach the reportservertempdb and reportserver databases.</span></span> <span data-ttu-id="4c93d-120">Zum Erstellen der Rolle ist das Anfügen der Datenbanken nicht erforderlich. Die Datenbanken müssen jedoch angefügt werden, damit Sie Ihre Implementierung testen können.</span><span class="sxs-lookup"><span data-stu-id="4c93d-120">You are not required to attach the databases to create the actual role, but they must be attached before you can test your work.</span></span>

 <span data-ttu-id="4c93d-121">Die Anweisungen zum manuellen Erstellen der Rolle `RSExecRole` sollen im Kontext einer Migration der Berichtsserver-Installation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4c93d-121">The instructions for manually creating the `RSExecRole` are intended to be used within the context of migrating a report server installation.</span></span> <span data-ttu-id="4c93d-122">In diesem Thema wird auf wichtige Aufgaben, wie z. B. das Sichern und Verschieben der Berichtsserver-Datenbank, nicht eingegangen. Diese Aufgaben werden aber in der Dokumentation zur Datenbank-Engine beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4c93d-122">Important tasks such as backing up and moving the report server database are not addressed in this topic, but are documented in the Database Engine documentation.</span></span>

## <a name="create-rsexecrole-in-master"></a><span data-ttu-id="4c93d-123">Erstellen der Rolle 'RSExecRole' in 'Master'</span><span class="sxs-lookup"><span data-stu-id="4c93d-123">Create RSExecRole in Master</span></span>
 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="4c93d-124">wird durch den Einsatz von erweiterten gespeicherten Prozeduren sichergestellt, dass der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Agent-Dienst geplante Vorgänge unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4c93d-124">uses extended stored procedures for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent service to support scheduled operations.</span></span> <span data-ttu-id="4c93d-125">Die folgenden Schritte erklären, wie der Rolle `RSExecRole` Berechtigungen zum Ausführen der Prozeduren gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="4c93d-125">The following steps explain how to grant Execute permissions for the procedures to the `RSExecRole` role.</span></span>

#### <a name="to-create-rsexecrole-in-the-master-system-database-using-management-studio"></a><span data-ttu-id="4c93d-126">So erstellen Sie die Rolle 'RSExecRole' mit Management Studio in der Systemdatenbank 'Master'</span><span class="sxs-lookup"><span data-stu-id="4c93d-126">To create RSExecRole in the Master system database using Management Studio</span></span>

1.  <span data-ttu-id="4c93d-127">Starten Sie [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], und stellen Sie eine Verbindung mit der [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her, die als Host für die Berichtsserver-Datenbank fungiert.</span><span class="sxs-lookup"><span data-stu-id="4c93d-127">Start [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] instance that hosts the report server database.</span></span>

2.  <span data-ttu-id="4c93d-128">Öffnen Sie **Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="4c93d-128">Open **Databases**.</span></span>

3.  <span data-ttu-id="4c93d-129">Öffnen Sie **Systemdatenbanken**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-129">Open **System Databases**.</span></span>

4.  <span data-ttu-id="4c93d-130">Öffnen Sie `Master`.</span><span class="sxs-lookup"><span data-stu-id="4c93d-130">Open `Master`.</span></span>

5.  <span data-ttu-id="4c93d-131">Öffnen Sie **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-131">Open **Security**.</span></span>

6.  <span data-ttu-id="4c93d-132">Öffnen Sie **Rollen**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-132">Open **Roles**.</span></span>

7.  <span data-ttu-id="4c93d-133">Klicken Sie mit der rechten Maustaste auf **Datenbankrollen**, und wählen Sie **Neue Datenbankrolle**aus.</span><span class="sxs-lookup"><span data-stu-id="4c93d-133">Right-click **Database Roles**, and select **New Database Role**.</span></span> <span data-ttu-id="4c93d-134">Die Seite Allgemein wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c93d-134">The General page appears.</span></span>

8.  <span data-ttu-id="4c93d-135">Geben Sie unter **Rollenname den Namen**ein `RSExecRole` .</span><span class="sxs-lookup"><span data-stu-id="4c93d-135">In **Role name**, type `RSExecRole`.</span></span>

9. <span data-ttu-id="4c93d-136">Geben Sie im Feld **Besitzer**die Zeichenfolge **DBO**ein.</span><span class="sxs-lookup"><span data-stu-id="4c93d-136">In **Owner**, type **DBO**.</span></span>

10. <span data-ttu-id="4c93d-137">Klicken Sie auf **Sicherungsfähige Elemente**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-137">Click **Securables**.</span></span>

11. <span data-ttu-id="4c93d-138">Klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-138">Click **Search**.</span></span> <span data-ttu-id="4c93d-139">Das Dialogfeld **Objekte hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c93d-139">The **Add Objects** dialog box appears.</span></span> <span data-ttu-id="4c93d-140">Standardmäßig ist die Option **Bestimmte Objekte** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4c93d-140">The **Specific Objects** option is selected by default.</span></span>

12. <span data-ttu-id="4c93d-141">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-141">Click **OK**.</span></span> <span data-ttu-id="4c93d-142">Das Dialogfeld **Objekte auswählen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c93d-142">The **Select Objects** dialog box appears.</span></span>

13. <span data-ttu-id="4c93d-143">Klicken Sie auf **Objekttypen**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-143">Click **Object Types**.</span></span>

14. <span data-ttu-id="4c93d-144">Klicken Sie auf **Erweiterte gespeicherte Prozeduren**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-144">Click **Extended Stored Procedures**.</span></span>

15. <span data-ttu-id="4c93d-145">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-145">Click **OK**.</span></span>

16. <span data-ttu-id="4c93d-146">Klicken Sie auf **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-146">Click **Browse**.</span></span>

17. <span data-ttu-id="4c93d-147">Führen Sie in der Liste erweiterter gespeicherter Prozeduren einen Bildlauf durch, und wählen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="4c93d-147">Scroll down the list of extended stored procedures and select the following:</span></span>

    1.  <span data-ttu-id="4c93d-148">xp_sqlagent_enum_jobs</span><span class="sxs-lookup"><span data-stu-id="4c93d-148">xp_sqlagent_enum_jobs</span></span>

    2.  <span data-ttu-id="4c93d-149">xp_sqlagent_is_starting</span><span class="sxs-lookup"><span data-stu-id="4c93d-149">xp_sqlagent_is_starting</span></span>

    3.  <span data-ttu-id="4c93d-150">xp_sqlagent_notify</span><span class="sxs-lookup"><span data-stu-id="4c93d-150">xp_sqlagent_notify</span></span>

18. <span data-ttu-id="4c93d-151">Klicken Sie auf **OK**, und klicken Sie dann nochmals auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="4c93d-151">Click **OK**, and the click **OK** again.</span></span>

19. <span data-ttu-id="4c93d-152">Klicken Sie in der Zeile **Ausführen** auf das Kontrollkästchen in der Spalte **Erteilen** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-152">In the **Execute** row, in the **Grant** column, click the check box, and then click **OK**.</span></span>

20. <span data-ttu-id="4c93d-153">Wiederholen Sie diesen Schritt für alle übrigen gespeicherten Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="4c93d-153">Repeat for each of the remaining stored procedures.</span></span> <span data-ttu-id="4c93d-154">Der Rolle `RSExecRole` müssen Berechtigungen zum Ausführen aller drei gespeicherten Prozeduren gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="4c93d-154">`RSExecRole` must be granted Execute permissions for all three stored procedures.</span></span>

 <span data-ttu-id="4c93d-155">![Eigenschaftenseite für Datenbankrolle](../media/rsexecroledbproperties.gif "Eigenschaftenseite für Datenbankrolle")</span><span class="sxs-lookup"><span data-stu-id="4c93d-155">![Database Role Properties page](../media/rsexecroledbproperties.gif "Database Role Properties page")</span></span>

## <a name="create-rsexecrole-in-msdb"></a><span data-ttu-id="4c93d-156">Erstellen der Rolle 'RSExecRole' in 'MSDB'</span><span class="sxs-lookup"><span data-stu-id="4c93d-156">Create RSExecRole in MSDB</span></span>
 <span data-ttu-id="4c93d-157">Reporting Services verwendet gespeicherte Prozeduren für den SQL Server-Agent-Dienst und ruft zur Unterstützung geplanter Vorgänge Auftragsinformationen ab.</span><span class="sxs-lookup"><span data-stu-id="4c93d-157">Reporting Services uses stored procedures for SQL Server Agent service and retrieves job information from system tables to support scheduled operations.</span></span> <span data-ttu-id="4c93d-158">Die folgenden Schritte erklären, wie der Rolle RSExecRole Berechtigungen zum Ausführen der Prozeduren und zum Auswählen der Tabellen gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="4c93d-158">The following steps explain how to grant Execute permissions for the procedures and Select permissions on the tables to the RSExecRole.</span></span>

#### <a name="to-create-rsexecrole-in-the-msdb-system-database"></a><span data-ttu-id="4c93d-159">So erstellen Sie die Rolle 'RSExecRole' in der Systemdatenbank 'MSDB'</span><span class="sxs-lookup"><span data-stu-id="4c93d-159">To create RSExecRole in the MSDB system database</span></span>

1.  <span data-ttu-id="4c93d-160">Wiederholen Sie ähnliche Schritte, um Berechtigungen für gespeicherte Prozeduren und Tabellen in MSDB zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="4c93d-160">Repeat similar steps for granting permissions to stored procedures and tables in MSDB.</span></span> <span data-ttu-id="4c93d-161">Um die Schritte zu vereinfachen, stellen Sie die gespeicherten Prozeduren und die Tabellen getrennt bereit.</span><span class="sxs-lookup"><span data-stu-id="4c93d-161">To simplify the steps, you will provision the stored procedures and tables separately.</span></span>

2.  <span data-ttu-id="4c93d-162">Öffnen Sie `MSDB`.</span><span class="sxs-lookup"><span data-stu-id="4c93d-162">Open `MSDB`.</span></span>

3.  <span data-ttu-id="4c93d-163">Öffnen Sie **Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-163">Open **Security**.</span></span>

4.  <span data-ttu-id="4c93d-164">Öffnen Sie **Rollen**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-164">Open **Roles**.</span></span>

5.  <span data-ttu-id="4c93d-165">Klicken Sie mit der rechten Maustaste auf **Datenbankrollen**, und wählen Sie **Neue Datenbankrolle**aus.</span><span class="sxs-lookup"><span data-stu-id="4c93d-165">Right-click **Database Roles**, and select **New Database Role**.</span></span> <span data-ttu-id="4c93d-166">Die Seite Allgemein wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c93d-166">The General page appears.</span></span>

6.  <span data-ttu-id="4c93d-167">Geben Sie unter Rollenname den Namen ein `RSExecRole` .</span><span class="sxs-lookup"><span data-stu-id="4c93d-167">In Role name, type `RSExecRole`.</span></span>

7.  <span data-ttu-id="4c93d-168">Geben Sie unter Besitzer den Namen **dbo**ein.</span><span class="sxs-lookup"><span data-stu-id="4c93d-168">In Owner, type **DBO**.</span></span>

8.  <span data-ttu-id="4c93d-169">Klicken Sie auf **Sicherungsfähige Elemente**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-169">Click **Securables**.</span></span>

9. <span data-ttu-id="4c93d-170">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-170">Click **Add**.</span></span> <span data-ttu-id="4c93d-171">Das Dialogfeld **Objekte hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c93d-171">The **Add Objects** dialog box appears.</span></span> <span data-ttu-id="4c93d-172">Standardmäßig ist die Option **Objekte angeben** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4c93d-172">The **Specify Objects** option is selected by default.</span></span>

10. <span data-ttu-id="4c93d-173">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-173">Click **OK**.</span></span>

11. <span data-ttu-id="4c93d-174">Klicken Sie auf **Objekttypen**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-174">Click **Object Types**.</span></span>

12. <span data-ttu-id="4c93d-175">Klicken Sie auf **Gespeicherte Prozeduren**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-175">Click **Stored Procedures.**</span></span>

13. <span data-ttu-id="4c93d-176">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-176">Click **OK**.</span></span>

14. <span data-ttu-id="4c93d-177">Klicken Sie auf **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-177">Click **Browse**.</span></span>

15. <span data-ttu-id="4c93d-178">Führen Sie in der Liste der Elemente einen Bildlauf durch, und wählen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="4c93d-178">Scroll down the list of items and select the following:</span></span>

    1.  <span data-ttu-id="4c93d-179">sp_add_category</span><span class="sxs-lookup"><span data-stu-id="4c93d-179">sp_add_category</span></span>

    2.  <span data-ttu-id="4c93d-180">sp_add_job</span><span class="sxs-lookup"><span data-stu-id="4c93d-180">sp_add_job</span></span>

    3.  <span data-ttu-id="4c93d-181">sp_add_jobschedule</span><span class="sxs-lookup"><span data-stu-id="4c93d-181">sp_add_jobschedule</span></span>

    4.  <span data-ttu-id="4c93d-182">sp_add_jobserver</span><span class="sxs-lookup"><span data-stu-id="4c93d-182">sp_add_jobserver</span></span>

    5.  <span data-ttu-id="4c93d-183">sp_add_jobstep</span><span class="sxs-lookup"><span data-stu-id="4c93d-183">sp_add_jobstep</span></span>

    6.  <span data-ttu-id="4c93d-184">sp_delete_job</span><span class="sxs-lookup"><span data-stu-id="4c93d-184">sp_delete_job</span></span>

    7.  <span data-ttu-id="4c93d-185">sp_help_category</span><span class="sxs-lookup"><span data-stu-id="4c93d-185">sp_help_category</span></span>

    8.  <span data-ttu-id="4c93d-186">sp_help_job</span><span class="sxs-lookup"><span data-stu-id="4c93d-186">sp_help_job</span></span>

    9. <span data-ttu-id="4c93d-187">sp_help_jobschedule</span><span class="sxs-lookup"><span data-stu-id="4c93d-187">sp_help_jobschedule</span></span>

    10. <span data-ttu-id="4c93d-188">sp_verify_job_identifiers</span><span class="sxs-lookup"><span data-stu-id="4c93d-188">sp_verify_job_identifiers</span></span>

16. <span data-ttu-id="4c93d-189">Klicken Sie auf **OK**, und klicken Sie dann nochmals auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="4c93d-189">Click **OK**, and the click **OK** again.</span></span>

17. <span data-ttu-id="4c93d-190">Wählen Sie die erste gespeicherte Prozedur aus: sp_add_category.</span><span class="sxs-lookup"><span data-stu-id="4c93d-190">Select the first stored procedure: sp_add_category.</span></span>

18. <span data-ttu-id="4c93d-191">Klicken Sie in der Zeile **Ausführen** auf das Kontrollkästchen in der Spalte **Erteilen** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-191">In the **Execute** row, in the **Grant** column, click the checkbox, and then click **OK**.</span></span>

19. <span data-ttu-id="4c93d-192">Wiederholen Sie diesen Schritt für alle übrigen gespeicherten Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="4c93d-192">Repeat for each of the remaining stored procedures.</span></span> <span data-ttu-id="4c93d-193">Der Rolle RSExecRole müssen Berechtigungen zum Ausführen aller zehn gespeicherten Prozeduren gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="4c93d-193">RSExecRole must be granted Execute permissions for all ten stored procedures.</span></span>

20. <span data-ttu-id="4c93d-194">Klicken Sie auf der Registerkarte **Sicherungsfähige Elemente** auf Hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4c93d-194">On the Securables tab, and click **Add** again.</span></span> <span data-ttu-id="4c93d-195">Das Dialogfeld **Objekte hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4c93d-195">The **Add Objects** dialog box appears.</span></span> <span data-ttu-id="4c93d-196">Standardmäßig ist die Option **Objekte angeben** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4c93d-196">The **Specify Objects** option is selected by default.</span></span>

21. <span data-ttu-id="4c93d-197">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-197">Click **OK**.</span></span>

22. <span data-ttu-id="4c93d-198">Klicken Sie auf **Objekttypen**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-198">Click **Object Types**.</span></span>

23. <span data-ttu-id="4c93d-199">Klicken Sie auf **Tabellen.**</span><span class="sxs-lookup"><span data-stu-id="4c93d-199">Click **Tables.**</span></span>

24. <span data-ttu-id="4c93d-200">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-200">Click **OK**.</span></span>

25. <span data-ttu-id="4c93d-201">Klicken Sie auf **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-201">Click **Browse**.</span></span>

26. <span data-ttu-id="4c93d-202">Führen Sie in der Liste der Elemente einen Bildlauf durch, und wählen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="4c93d-202">Scroll down the list of items and select the following:</span></span>

    1.  <span data-ttu-id="4c93d-203">syscategories</span><span class="sxs-lookup"><span data-stu-id="4c93d-203">syscategories</span></span>

    2.  <span data-ttu-id="4c93d-204">sysjobs</span><span class="sxs-lookup"><span data-stu-id="4c93d-204">sysjobs</span></span>

27. <span data-ttu-id="4c93d-205">Klicken Sie auf **OK**, und klicken Sie dann nochmals auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="4c93d-205">Click **OK**, and the click **OK** again.</span></span>

28. <span data-ttu-id="4c93d-206">Wählen Sie die erste Tabelle aus: syscategories.</span><span class="sxs-lookup"><span data-stu-id="4c93d-206">Select the first table: syscategories.</span></span>

29. <span data-ttu-id="4c93d-207">Klicken Sie in der Zeile **Auswählen** auf das Kontrollkästchen in der Spalte **Erteilen** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-207">In the **Select** row, in the **Grant** column, click the checkbox, and then click **OK**.</span></span>

30. <span data-ttu-id="4c93d-208">Wiederholen Sie diesen Schritt für die Tabelle sysjobs.</span><span class="sxs-lookup"><span data-stu-id="4c93d-208">Repeat for the sysjobs table.</span></span> <span data-ttu-id="4c93d-209">Die Rolle RSExecRole muss Berechtigungen zum Auswählen beider Tabellen erhalten.</span><span class="sxs-lookup"><span data-stu-id="4c93d-209">RSExecRole must be granted Select permissions for both tables.</span></span>

## <a name="move-the-report-server-database"></a><span data-ttu-id="4c93d-210">Verlagern der Berichtsserver-Datenbank</span><span class="sxs-lookup"><span data-stu-id="4c93d-210">Move the Report Server Database</span></span>
 <span data-ttu-id="4c93d-211">Nachdem Sie die Rollen erstellt haben, können Sie die Berichtsserver-Datenbank auf eine andere SQL Server-Instanz verschieben.</span><span class="sxs-lookup"><span data-stu-id="4c93d-211">After you create the roles, you can move the report server database to new SQL Server instance.</span></span> <span data-ttu-id="4c93d-212">Weitere Informationen finden Sie unter [Verschieben von Berichtsserver-Datenbanken auf einen anderen Computer &#40;einheitlicher SSRS-Modus&#41;](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="4c93d-212">For more information, see [Moving the Report Server Databases to Another Computer &#40;SSRS Native Mode&#41;](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md).</span></span>

 <span data-ttu-id="4c93d-213">Wenn Sie das [!INCLUDE[ssDE](../../../includes/ssde-md.md)] auf [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]aktualisieren, können Sie dieses Upgrade vor oder nach dem Verschieben der Datenbank durchführen.</span><span class="sxs-lookup"><span data-stu-id="4c93d-213">If you are upgrading the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], you can upgrade it before or after moving the database.</span></span>

 <span data-ttu-id="4c93d-214">Die Berichtsserver-Datenbank wird automatisch auf [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] aktualisiert, wenn der Berichtsserver eine Verbindung mit der Datenbank herstellt.</span><span class="sxs-lookup"><span data-stu-id="4c93d-214">The report server database will be upgraded to the [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] automatically when the report server connects to it.</span></span> <span data-ttu-id="4c93d-215">Zum Aktualisieren der Datenbank müssen keine bestimmten Schritte ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4c93d-215">There are no specific steps required for upgrading the database.</span></span>

## <a name="restore-encryption-keys-and-verify-your-work"></a><span data-ttu-id="4c93d-216">Wiederherstellen von Verschlüsselungsschlüsseln und Überprüfen der Arbeit</span><span class="sxs-lookup"><span data-stu-id="4c93d-216">Restore Encryption Keys and Verify Your Work</span></span>
 <span data-ttu-id="4c93d-217">Nachdem die Berichtsserver-Datenbanken angefügt wurden, sollten Sie die folgenden Schritte ausführen können, um Ihre Implementierung zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="4c93d-217">If you have attached the report server databases, you should now be able to complete the following steps to verify your work.</span></span>

#### <a name="to-verify-report-server-operability-after-a-database-move"></a><span data-ttu-id="4c93d-218">So überprüfen Sie nach einer Datenbankverschiebung die Funktionsfähigkeit des Berichtsservers</span><span class="sxs-lookup"><span data-stu-id="4c93d-218">To verify report server operability after a database move</span></span>

1.  <span data-ttu-id="4c93d-219">Starten Sie das Reporting Services-Konfigurationstool, und stellen Sie eine Verbindung mit dem Berichtsserver her.</span><span class="sxs-lookup"><span data-stu-id="4c93d-219">Start the Reporting Services Configuration tool and connect to the report server.</span></span>

2.  <span data-ttu-id="4c93d-220">Klicken Sie auf **Datenbank**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-220">Click **Database**.</span></span>

3.  <span data-ttu-id="4c93d-221">Klicken Sie auf **Datenbank ändern**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-221">Click **Change Database**.</span></span>

4.  <span data-ttu-id="4c93d-222">Sie können auch auf **Wählen Sie eine vorhandene Berichtsserver-Datenbank aus**klicken.</span><span class="sxs-lookup"><span data-stu-id="4c93d-222">Click **Choose an existing report server database**.</span></span>

5.  <span data-ttu-id="4c93d-223">Geben Sie den Servernamen der Datenbank-Engine ein.</span><span class="sxs-lookup"><span data-stu-id="4c93d-223">Enter the server name of the Database Engine.</span></span> <span data-ttu-id="4c93d-224">Wenn Sie die Berichts Server-Datenbanken an eine benannte Instanz angefügt haben, müssen Sie den Instanznamen im folgenden Format eingeben: \<servername> \\<instanceName \> .</span><span class="sxs-lookup"><span data-stu-id="4c93d-224">If you attached the report server databases to a named instance, you must type the instance name in this format: \<servername>\\<instancename\>.</span></span>

6.  <span data-ttu-id="4c93d-225">Klicken Sie auf **Verbindung testen**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-225">Click **Test Connection**.</span></span>

7.  <span data-ttu-id="4c93d-226">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-226">Click **Next**.</span></span>

8.  <span data-ttu-id="4c93d-227">Wählen Sie die Berichtsserver-Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="4c93d-227">On the Database, select the report server database.</span></span>

9. <span data-ttu-id="4c93d-228">Klicken Sie auf **Weiter** , und schließen Sie den Assistenten ab.</span><span class="sxs-lookup"><span data-stu-id="4c93d-228">Click **Next** and complete the wizard.</span></span>

10. <span data-ttu-id="4c93d-229">Klicken Sie auf **Verschlüsselungsschlüssel**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-229">Click **Encryption Keys**.</span></span>

11. <span data-ttu-id="4c93d-230">Klicken Sie auf **Wiederherstellen**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-230">Click **Restore**.</span></span>

12. <span data-ttu-id="4c93d-231">Wählen Sie die Datei mit starkem Namen (Dateierweiterung .snk) aus, welche die Sicherungskopie des symmetrischen Schlüssel enthält, der zum Entschlüsseln gespeicherter Anmeldeinformationen und Verbindungsinformationen in der Berichtsserver-Datenbank verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4c93d-231">Select the strong file (.snk) that has the backup copy of the symmetric key used to decrypt stored credentials and connection information in the report server database.</span></span>

13. <span data-ttu-id="4c93d-232">Geben Sie das Kennwort ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-232">Enter the password and click **OK**.</span></span>

14. <span data-ttu-id="4c93d-233">Klicken Sie auf **Berichts-Manager-URL**.</span><span class="sxs-lookup"><span data-stu-id="4c93d-233">Click **Report Manager URL**.</span></span>

15. <span data-ttu-id="4c93d-234">Klicken Sie auf den Link zum Öffnen des Berichts-Managers.</span><span class="sxs-lookup"><span data-stu-id="4c93d-234">Click the link to open Report Manager.</span></span> <span data-ttu-id="4c93d-235">Daraufhin sollten die Berichtsserver-Elemente aus der Berichtsserver-Datenbank angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4c93d-235">You should see the report server items from the report server database.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c93d-236">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4c93d-236">See Also</span></span>
 <span data-ttu-id="4c93d-237">[Verschieben der Berichts Server-Datenbanken auf einen anderen Computer &#40;SSRS im einheitlichen Modus&#41;](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md) [Konfigurations-Manager für Reporting Services &#40;einheitlichen Modus&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) [Erstellen einer Berichts Server-Datenbank im einheitlichen Modus &#40;SSRS Configuration Manager](../install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md)&#41;[Sichern und Wiederherstellen Reporting Services Verschlüsselungsschlüsseln](../install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md)</span><span class="sxs-lookup"><span data-stu-id="4c93d-237">[Moving the Report Server Databases to Another Computer &#40;SSRS Native Mode&#41;](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md) [Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) [Create a Native Mode Report Server Database  &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md) [Back Up and Restore Reporting Services Encryption Keys](../install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md)</span></span>


