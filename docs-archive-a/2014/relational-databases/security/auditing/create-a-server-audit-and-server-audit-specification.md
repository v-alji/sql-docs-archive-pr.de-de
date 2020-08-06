---
title: Erstellen einer Serverüberwachung und einer Serverüberwachungsspezifikation | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.SQLAUDIT.FILTER.F1
- sql12.swb.sqlaudit.srvaudit.general.f1
- sql12.swb.sqlaudit.general.f1
helpviewer_keywords:
- server audit [SQL Server]
- audits [SQL Server], specification
ms.assetid: 6624b1ab-7ec8-44ce-8292-397edf644394
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: a648a975ae9f2c4139a8ebd584f6998f4d0fa1a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700959"
---
# <a name="create-a-server-audit-and-server-audit-specification"></a><span data-ttu-id="565e8-102">Erstellen einer Serverüberwachung und einer Serverüberwachungsspezifikation</span><span class="sxs-lookup"><span data-stu-id="565e8-102">Create a Server Audit and Server Audit Specification</span></span>
  <span data-ttu-id="565e8-103">In diesem Thema wird beschrieben, wie eine Serverüberwachung und Serverüberwachungsspezifikation in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../../includes/tsql-md.md)]erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="565e8-103">This topic describes how to create a server audit and server audit specification in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="565e8-104">Bei der*Überwachung* einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] oder einer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Datenbank werden Ereignisse im System verfolgt und protokolliert.</span><span class="sxs-lookup"><span data-stu-id="565e8-104">*Auditing* an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database involves tracking and logging events that occur on the system.</span></span> <span data-ttu-id="565e8-105">Das *SQL Server Audit* -Objekt listet eine einzelne Instanz an Aktionen oder Aktionsgruppen auf Server- oder Datenbankebene auf, die überwacht werden soll.</span><span class="sxs-lookup"><span data-stu-id="565e8-105">The *SQL Server Audit* object collects a single instance of server- or database-level actions and groups of actions to monitor.</span></span> <span data-ttu-id="565e8-106">Die Überwachung wird auf [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Instanzebene ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="565e8-106">The audit is at the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance level.</span></span> <span data-ttu-id="565e8-107">Es können mehrere Überwachungen pro [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Instanz vorliegen.</span><span class="sxs-lookup"><span data-stu-id="565e8-107">You can have multiple audits per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="565e8-108">Das *Serverüberwachungsspezifikation* -Objekt gehört zu einer Überwachung.</span><span class="sxs-lookup"><span data-stu-id="565e8-108">The *Server Audit Specification* object belongs to an audit.</span></span> <span data-ttu-id="565e8-109">Sie können eine Serverüberwachungsspezifikation pro Überwachung erstellen, da beide im [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Instanzbereich erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="565e8-109">You can create one server audit specification per audit, because both are created at the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance scope.</span></span> <span data-ttu-id="565e8-110">Weitere Informationen finden Sie unter [SQL Server Audit &#40;Datenbank-Engine&#41;](sql-server-audit-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="565e8-110">For more information, see [SQL Server Audit &#40;Database Engine&#41;](sql-server-audit-database-engine.md).</span></span>  
  
 <span data-ttu-id="565e8-111">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="565e8-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="565e8-112">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="565e8-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="565e8-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="565e8-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="565e8-114">Security</span><span class="sxs-lookup"><span data-stu-id="565e8-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="565e8-115">**So erstellen Sie eine Serverüberwachung und eine Serverüberwachungsspezifikation mit**</span><span class="sxs-lookup"><span data-stu-id="565e8-115">**To create a server audit and server audit specification, using:**</span></span>  
  
     [<span data-ttu-id="565e8-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="565e8-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="565e8-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="565e8-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="565e8-118">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="565e8-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="565e8-119">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="565e8-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="565e8-120">Eine Überwachung muss vorhanden sein, bevor Sie eine Serverüberwachungsspezifikation für sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="565e8-120">An audit must exist before creating a server audit specification for it.</span></span> <span data-ttu-id="565e8-121">Wenn eine Serverüberwachungsspezifikation erstellt wird, befindet sie sich im deaktivierten Zustand.</span><span class="sxs-lookup"><span data-stu-id="565e8-121">When a server audit specification is created, it is in a disabled state.</span></span>  
  
-   <span data-ttu-id="565e8-122">Die CREATE SERVER AUDIT-Anweisung liegt im Bereich einer Transaktion.</span><span class="sxs-lookup"><span data-stu-id="565e8-122">The CREATE SERVER AUDIT statement is in a transaction's scope.</span></span> <span data-ttu-id="565e8-123">Wird ein Rollback für die Transaktion ausgeführt, so wird auch für die Anweisung ein Rollback durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="565e8-123">If the transaction is rolled back, the statement is also rolled back.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="565e8-124">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="565e8-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="565e8-125">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="565e8-125">Permissions</span></span>  
  
-   <span data-ttu-id="565e8-126">Um eine Serverüberwachung zu erstellen, zu ändern oder zu löschen, benötigen Prinzipale die ALTER ANY SERVER AUDIT-Berechtigung oder die CONTROL SERVER-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="565e8-126">To create, alter, or drop a server audit, principals require the ALTER ANY SERVER AUDIT or the CONTROL SERVER permission.</span></span>  
  
-   <span data-ttu-id="565e8-127">Benutzer mit der Berechtigung ALTER ANY SERVER AUDIT können Serverüberwachungsspezifikationen erstellen und diese an eine beliebige Überwachung binden.</span><span class="sxs-lookup"><span data-stu-id="565e8-127">Users with the ALTER ANY SERVER AUDIT permission can create server audit specifications and bind them to any audit.</span></span>  
  
-   <span data-ttu-id="565e8-128">Sobald eine Serverüberwachungsspezifikation erstellt wurde, kann sie von Prinzipalen mit den folgenden Berechtigungen eingesehen werden: CONTROL SERVER oder ALTER ANY SERVER AUDIT. Außerdem kann sie von Prinzipalen eingesehen werden, die über das „sysadmin“-Konto oder expliziten Zugriff auf die Überwachung verfügen.</span><span class="sxs-lookup"><span data-stu-id="565e8-128">After a server audit specification is created, it can be viewed by principals with the CONTROL SERVER or ALTER ANY SERVER AUDIT permissions, the sysadmin account, or principals having explicit access to the audit.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="565e8-129">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="565e8-129">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-server-audit"></a><span data-ttu-id="565e8-130">So erstellen Sie eine Serverüberwachung</span><span class="sxs-lookup"><span data-stu-id="565e8-130">To create a server audit</span></span>  
  
1.  <span data-ttu-id="565e8-131">Erweitern Sie im Objekt-Explorer den Ordner **Sicherheit** .</span><span class="sxs-lookup"><span data-stu-id="565e8-131">In Object Explorer, expand the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="565e8-132">Klicken Sie mit der rechten Maustaste auf den Ordner **Überwachungen**, und wählen Sie dann **Neue Überwachung...** aus.</span><span class="sxs-lookup"><span data-stu-id="565e8-132">Right-click the **Audits** folder and select **New Audit...**.</span></span>  
  
     <span data-ttu-id="565e8-133">Die folgenden Optionen befinden sich im Dialogfeld **Überwachung erstellen** auf der Seite **Allgemein** :</span><span class="sxs-lookup"><span data-stu-id="565e8-133">The following options are available on the **General** page of the **Create Audit** dialog box.</span></span>  
  
     <span data-ttu-id="565e8-134">**Überwachungsname**</span><span class="sxs-lookup"><span data-stu-id="565e8-134">**Audit name**</span></span>  
     <span data-ttu-id="565e8-135">Der Name der Überwachung.</span><span class="sxs-lookup"><span data-stu-id="565e8-135">The name of the audit.</span></span> <span data-ttu-id="565e8-136">Der Name wird automatisch generiert, wenn Sie eine neue Überwachung erstellen, er kann jedoch bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="565e8-136">This is generated automatically when you create a new audit but is editable.</span></span>  
  
     <span data-ttu-id="565e8-137">**Warteschlangenverzögerung (in Millisekunden)**</span><span class="sxs-lookup"><span data-stu-id="565e8-137">**Queue delay (in milliseconds)**</span></span>  
     <span data-ttu-id="565e8-138">Gibt in Millisekunden den Zeitraum an, der verstreichen kann, bevor die Verarbeitung von Überwachungsaktionen erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="565e8-138">Specifies the amount of time in milliseconds that can elapse before audit actions are forced to be processed.</span></span>  <span data-ttu-id="565e8-139">Der Wert 0 steht für eine synchrone Übermittlung.</span><span class="sxs-lookup"><span data-stu-id="565e8-139">A value of 0 indicates synchronous delivery.</span></span> <span data-ttu-id="565e8-140">Der standardmäßige Mindestwert beträgt **1000** (1 Sekunde).</span><span class="sxs-lookup"><span data-stu-id="565e8-140">The default minimum value is **1000** (1 second).</span></span> <span data-ttu-id="565e8-141">Der maximale Wert beträgt 2.147.483.647 (2.147.483,647 Sekunden oder 24 Tage, 20 Stunden, 31 Minuten und 23,647 Sekunden).</span><span class="sxs-lookup"><span data-stu-id="565e8-141">The maximum is 2,147,483,647 (2,147,483.647 seconds or 24 days, 20 hours, 31 minutes, 23.647 seconds).</span></span>  
  
     <span data-ttu-id="565e8-142">**Bei Überwachungsprotokollfehler:**</span><span class="sxs-lookup"><span data-stu-id="565e8-142">**On Audit Log Failure:**</span></span>  
     <span data-ttu-id="565e8-143">**Fortsetzen**</span><span class="sxs-lookup"><span data-stu-id="565e8-143">**Continue**</span></span>  
     [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="565e8-144">-Vorgänge werden fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="565e8-144">operations continue.</span></span> <span data-ttu-id="565e8-145">Überwachungsdatensätze werden nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="565e8-145">Audit records are not retained.</span></span> <span data-ttu-id="565e8-146">Die Überwachung versucht weiterhin, Ereignisse zu protokollieren und wird fortgesetzt, wenn die Fehlerbedingung aufgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="565e8-146">The audit continues to attempt to log events and will resume if the failure condition is resolved.</span></span> <span data-ttu-id="565e8-147">Durch Auswählen der **Continue** -Option können unter Umständen unüberwachte Aktivitäten ausgeführt werden, die gegen Ihre Sicherheitsrichtlinien verstoßen.</span><span class="sxs-lookup"><span data-stu-id="565e8-147">Selecting the **Continue** option can allow unaudited activity which could violate your security policies.</span></span> <span data-ttu-id="565e8-148">Wählen Sie diese Option aus, wenn die weitere Verwendung von [!INCLUDE[ssDE](../../../includes/ssde-md.md)] wichtiger als die Beibehaltung einer vollständigen Überwachung ist.</span><span class="sxs-lookup"><span data-stu-id="565e8-148">Select this option when continuing operation of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] is more important than maintaining a complete audit.</span></span> <span data-ttu-id="565e8-149">Dies ist die Standardauswahl.</span><span class="sxs-lookup"><span data-stu-id="565e8-149">This is the default selection.</span></span>  
  
     <span data-ttu-id="565e8-150">**Herunterfahren des Servers**</span><span class="sxs-lookup"><span data-stu-id="565e8-150">**Shut down server**</span></span>  
     <span data-ttu-id="565e8-151">Erzwingt, dass ein Server heruntergefahren wird, wenn die Serverinstanz, die in das Ziel schreiben soll, keine Daten in das Überwachungsziel schreiben kann.</span><span class="sxs-lookup"><span data-stu-id="565e8-151">Forces a server shut down when the server instance writing to the target cannot write data to the audit target.</span></span> <span data-ttu-id="565e8-152">Die Anmeldung, die dies ausgibt, muss über die `SHUTDOWN`-Berechtigung verfügen.</span><span class="sxs-lookup"><span data-stu-id="565e8-152">The login issuing this must have the `SHUTDOWN` permission.</span></span> <span data-ttu-id="565e8-153">Wenn die Anmeldung nicht über diese Berechtigung verfügt, schlägt diese Funktion fehl, und es wird eine Fehlermeldung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="565e8-153">If the logon does not have this permission, this function will fail and an error message will be raised.</span></span> <span data-ttu-id="565e8-154">Es treten keine überwachten Ereignisse auf.</span><span class="sxs-lookup"><span data-stu-id="565e8-154">No audited events occur.</span></span> <span data-ttu-id="565e8-155">Wählen Sie diese Option aus, wenn ein Überwachungsfehler die Sicherheit oder die Integrität des Systems beeinträchtigen konnte.</span><span class="sxs-lookup"><span data-stu-id="565e8-155">Select this option when an audit failure could compromise the security or integrity of the system.</span></span>  
  
     <span data-ttu-id="565e8-156">**Fehler bei Vorgang**</span><span class="sxs-lookup"><span data-stu-id="565e8-156">**Fail operation**</span></span>  
     <span data-ttu-id="565e8-157">In Fällen, in denen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Audit keine Informationen in das Überwachungsprotokoll schreiben kann, bewirkt diese Option, dass Datenbankaktionen fehlschlagen, wenn sie andernfalls überwachte Ereignisse verursachen würden.</span><span class="sxs-lookup"><span data-stu-id="565e8-157">In cases where the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Audit cannot write to the audit log this option causes database actions to fail if they would otherwise cause audited events.</span></span> <span data-ttu-id="565e8-158">Es treten keine überwachten Ereignisse auf.</span><span class="sxs-lookup"><span data-stu-id="565e8-158">No audited events occur.</span></span> <span data-ttu-id="565e8-159">Aktionen, die keine überwachten Ereignisse verursachen, können fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="565e8-159">Actions which do not cause audited events can continue.</span></span> <span data-ttu-id="565e8-160">Die Überwachung versucht weiterhin, Ereignisse zu protokollieren und wird fortgesetzt, wenn die Fehlerbedingung aufgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="565e8-160">The audit continues to attempt to log events and will resume if the failure condition is resolved.</span></span> <span data-ttu-id="565e8-161">Wählen Sie diese Option aus, wenn die Beibehaltung einer vollständigen Überwachung wichtiger als der Vollzugriff auf [!INCLUDE[ssDE](../../../includes/ssde-md.md)]ist.</span><span class="sxs-lookup"><span data-stu-id="565e8-161">Select this option when maintaining a complete audit is more important than full access to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="565e8-162">Wenn sich die Überwachung in einem fehlerhaften Status befindet, kann die dedizierte Administratorverbindung weiterhin überwachte Ereignisse ausführen.</span><span class="sxs-lookup"><span data-stu-id="565e8-162">When the audit is in a failed state, the Dedicated Administrator Connection can continue to perform audited events.</span></span>  
  
     <span data-ttu-id="565e8-163">**Überwachungsziel** (Liste)</span><span class="sxs-lookup"><span data-stu-id="565e8-163">**Audit destination** list</span></span>  
     <span data-ttu-id="565e8-164">Gibt das Ziel für die Überwachungsdaten an.</span><span class="sxs-lookup"><span data-stu-id="565e8-164">Specifies the target for auditing data.</span></span> <span data-ttu-id="565e8-165">Die verfügbaren Optionen sind eine Binärdatei, das Windows-Anwendungsprotokoll oder das Windows-Sicherheitsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="565e8-165">The available options are a binary file, the Windows Application log, or the Windows Security log.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="565e8-166">kann nicht in das Windows-Sicherheitsprotokoll schreiben, ohne zusätzliche Einstellungen in Windows zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="565e8-166">cannot write to the Windows Security log without configuring additional settings in Windows.</span></span> <span data-ttu-id="565e8-167">Weitere Informationen finden Sie unter [Schreiben von SQL-Serverüberwachungsereignissen in das Sicherheitsprotokoll](write-sql-server-audit-events-to-the-security-log.md).</span><span class="sxs-lookup"><span data-stu-id="565e8-167">For more information, see [Write SQL Server Audit Events to the Security Log](write-sql-server-audit-events-to-the-security-log.md).</span></span>  
  
     <span data-ttu-id="565e8-168">**Dateipfad**</span><span class="sxs-lookup"><span data-stu-id="565e8-168">**File path**</span></span>  
     <span data-ttu-id="565e8-169">Gibt den Speicherort des Ordners an, in den Überwachungsdaten geschrieben werden, wenn das **Überwachungsziel** eine Datei ist.</span><span class="sxs-lookup"><span data-stu-id="565e8-169">Specifies the location of the folder where audit data is written when the **Audit destination** is a file.</span></span>  
  
     <span data-ttu-id="565e8-170">**Auslassungspunkte (…)**</span><span class="sxs-lookup"><span data-stu-id="565e8-170">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="565e8-171">Öffnet das Dialogfeld **Ordner suchen-**_server_name_ , um einen Dateipfad anzugeben oder einen Ordner zu erstellen, in den die Überwachungs Datei geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="565e8-171">Opens the **Locate Folder -**_server_name_ dialog box to specify a file path or create a folder where the audit file is written.</span></span>  
  
     <span data-ttu-id="565e8-172">**Maximale Grenze für Überwachungsdatei:**</span><span class="sxs-lookup"><span data-stu-id="565e8-172">**Audit File Maximum Limit:**</span></span>  
     <span data-ttu-id="565e8-173">**Maximale Anzahl Rolloverdateien**</span><span class="sxs-lookup"><span data-stu-id="565e8-173">**Maximum rollover files**</span></span>  
     <span data-ttu-id="565e8-174">Wenn die maximale Anzahl von Überwachungsdateien erreicht wird, werden die ältesten Überwachungsdateien durch neuen Dateiinhalt überschrieben.</span><span class="sxs-lookup"><span data-stu-id="565e8-174">Specifies that, when the maximum number of audit files is reached, the oldest audit files are overwritten by new file content.</span></span>  
  
     <span data-ttu-id="565e8-175">**Maximale Dateien**</span><span class="sxs-lookup"><span data-stu-id="565e8-175">**Maximum files**</span></span>  
     <span data-ttu-id="565e8-176">Wenn die maximale Anzahl von Überwachungsdateien erreicht wird, tritt bei jeder Aktion, durch die zusätzliche Überwachungsereignisse verursacht werden, ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="565e8-176">Specifies that, when the maximum number of audit files is reached, any action that causes additional audit events to be generated will fail with an error.</span></span>  
  
     <span data-ttu-id="565e8-177">**Unbegrenzt** (Kontrollkästchen)</span><span class="sxs-lookup"><span data-stu-id="565e8-177">**Unlimited** check box</span></span>  
     <span data-ttu-id="565e8-178">Wenn das Kontrollkästchen **Unbegrenzt** unter **Maximale Anzahl Rolloverdateien** aktiviert ist, kann eine unbegrenzte Anzahl von Rolloverdateien erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="565e8-178">When the **Unlimited** check box under **Maximum rollover files** is selected, there is no limit imposed on the number of audit files that will be created.</span></span> <span data-ttu-id="565e8-179">Das Kontrollkästchen **Unbegrenzt** ist standardmäßig aktiviert und gilt sowohl für **Maximale Anzahl Rolloverdateien** als auch für **Maximale Dateien** .</span><span class="sxs-lookup"><span data-stu-id="565e8-179">The **Unlimited** check box is selected by default and applies to both the **Maximum rollover files** and **Maximum files** selections.</span></span>  
  
     <span data-ttu-id="565e8-180">**Anzahl der Dateien** (Feld)</span><span class="sxs-lookup"><span data-stu-id="565e8-180">**Number of files** box</span></span>  
     <span data-ttu-id="565e8-181">Gibt die Anzahl von Überwachungsdateien an, die erstellt werden können, und zwar bis zu 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="565e8-181">Specifies the number of audit files to be created, up to 2,147,483,647.</span></span> <span data-ttu-id="565e8-182">Diese Option ist nur verfügbar, wenn **Unbegrenzt** deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="565e8-182">This option is only available if **Unlimited** is unchecked.</span></span>  
  
     <span data-ttu-id="565e8-183">**Maximale Dateigröße**</span><span class="sxs-lookup"><span data-stu-id="565e8-183">**Maximum file size**</span></span>  
     <span data-ttu-id="565e8-184">Gibt die maximale Größe für eine Überwachungsdatei entweder in Megabyte (MB), Gigabyte (GB) oder Terabyte (TB) an.</span><span class="sxs-lookup"><span data-stu-id="565e8-184">Specifies the maximum size for an audit file in either megabytes (MB), gigabytes (GB), or terabytes (TB).</span></span> <span data-ttu-id="565e8-185">Sie können zwischen 1024 MB und 2.147.483.647 TB angeben.</span><span class="sxs-lookup"><span data-stu-id="565e8-185">You can specify between 1024 MB and 2,147,483,647 TB.</span></span> <span data-ttu-id="565e8-186">Durch Aktivieren des Kontrollkästchen **Unbegrenzt** gibt es keine Begrenzung der Dateigröße.</span><span class="sxs-lookup"><span data-stu-id="565e8-186">Selecting the **Unlimited** check box does not place a limit on the size of the file.</span></span> <span data-ttu-id="565e8-187">Die Angabe eines Werts kleiner 1024 MB löst einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="565e8-187">Specifying a value lower than 1024 MB will fail, returning an error.</span></span> <span data-ttu-id="565e8-188">Das Kontrollkästchen **Unbegrenzt** ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="565e8-188">The **Unlimited** check box is selected by default.</span></span>  
  
     <span data-ttu-id="565e8-189">**Speicherplatz reservieren** (Kontrollkästchen)</span><span class="sxs-lookup"><span data-stu-id="565e8-189">**Reserve disk space** check box</span></span>  
     <span data-ttu-id="565e8-190">Gibt an, dass der auf dem Datenträger vorab zugeordnete Speicherplatz der festgelegten maximalen Dateigröße entspricht.</span><span class="sxs-lookup"><span data-stu-id="565e8-190">Specifies that space is pre-allocated on the disk equal to the specified maximum file size.</span></span> <span data-ttu-id="565e8-191">Diese Einstellung kann nur verwendet werden, wenn das Kontrollkästchen **Unbegrenzt** unter **Maximale Dateigröße** deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="565e8-191">This setting can only be used if the **Unlimited** check box under **Maximum file size** is not selected.</span></span> <span data-ttu-id="565e8-192">Dieses Kontrollkästchen ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="565e8-192">This check box is not selected by default.</span></span>  
  
3.  <span data-ttu-id="565e8-193">Geben Sie auf der Seite **Filter** optional ein Prädikat oder eine `WHERE` -Klausel für die Serverüberwachung ein, um Optionen anzugeben, die auf der Seite **Allgemein** nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="565e8-193">Optionally, on the **Filter** page, enter a predicate, or `WHERE` clause, to the server audit to specify additional options not available from the **General** page.</span></span> <span data-ttu-id="565e8-194">Schließen Sie das Prädikat in Klammern ein; z. B.: `(object_name = 'EmployeesTable')`.</span><span class="sxs-lookup"><span data-stu-id="565e8-194">Enclose the predicate in parentheses; for example: `(object_name = 'EmployeesTable')`.</span></span>  
  
4.  <span data-ttu-id="565e8-195">Nachdem Sie alle Optionen ausgewählt haben, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="565e8-195">When you are finished selecting options, click **OK**.</span></span>  
  
#### <a name="to-create-a-server-audit-specification"></a><span data-ttu-id="565e8-196">So erstellen Sie eine Serverüberwachungsspezifikation</span><span class="sxs-lookup"><span data-stu-id="565e8-196">To create a server audit specification</span></span>  
  
1.  <span data-ttu-id="565e8-197">Klicken Sie im Objekt-Explorer auf das Pluszeichen, um den Ordner **Sicherheit** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="565e8-197">In Object Explorer, click the plus sign to expand the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="565e8-198">Klicken Sie mit der rechten Maustaste auf den Ordner **Serverüberwachungsspezifikationen**, und wählen Sie dann **Neue Serverüberwachungsspezifikation...** aus.</span><span class="sxs-lookup"><span data-stu-id="565e8-198">Right-click the **Server Audit Specifications** folder and select **New Server Audit Specification...**.</span></span>  
  
     <span data-ttu-id="565e8-199">Die folgenden Optionen sind im Dialogfeld **Serverüberwachungsspezifikation erstellen** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="565e8-199">The following options are available on the **Create Server Audit Specification** dialog box.</span></span>  
  
     <span data-ttu-id="565e8-200">**Name**</span><span class="sxs-lookup"><span data-stu-id="565e8-200">**Name**</span></span>  
     <span data-ttu-id="565e8-201">Der Name der Serverüberwachungsspezifikation.</span><span class="sxs-lookup"><span data-stu-id="565e8-201">The name of the server audit specification.</span></span> <span data-ttu-id="565e8-202">Er wird automatisch generiert, wenn Sie eine neue Serverüberwachungsspezifikation erstellen, er kann jedoch bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="565e8-202">This is generated automatically when you create a new server audit specification but is editable.</span></span>  
  
     <span data-ttu-id="565e8-203">**Überwachung**</span><span class="sxs-lookup"><span data-stu-id="565e8-203">**Audit**</span></span>  
     <span data-ttu-id="565e8-204">Der Name einer vorhandenen Serverüberwachung.</span><span class="sxs-lookup"><span data-stu-id="565e8-204">The name of an existing server audit.</span></span> <span data-ttu-id="565e8-205">Geben Sie den Namen der Überwachung ein, oder wählen Sie ihn aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="565e8-205">Either type in the name of the audit or select it from the list.</span></span>  
  
     <span data-ttu-id="565e8-206">**Überwachungsaktionstyp**</span><span class="sxs-lookup"><span data-stu-id="565e8-206">**Audit Action Type**</span></span>  
     <span data-ttu-id="565e8-207">Gibt die aufzuzeichnenden Überwachungsaktionsgruppen auf Serverebene und Überwachungsaktionen an.</span><span class="sxs-lookup"><span data-stu-id="565e8-207">Specifies the server-level audit action groups and audit actions to capture.</span></span> <span data-ttu-id="565e8-208">Eine Liste der Überwachungsaktionsgruppen auf Serverebene und Überwachungsaktionen sowie eine Beschreibung der darin enthaltenen Ereignisse finden Sie unter [SQL Server Audit-Aktionsgruppen und -Aktionen](sql-server-audit-action-groups-and-actions.md).</span><span class="sxs-lookup"><span data-stu-id="565e8-208">For the list of server-level audit action groups and audit actions and a description of the events they contain, see [SQL Server Audit Action Groups and Actions](sql-server-audit-action-groups-and-actions.md).</span></span>  
  
     <span data-ttu-id="565e8-209">**Objektschema**</span><span class="sxs-lookup"><span data-stu-id="565e8-209">**Object Schema**</span></span>  
     <span data-ttu-id="565e8-210">Zeigt das Schema für den angegebenen **Objektnamen**an.</span><span class="sxs-lookup"><span data-stu-id="565e8-210">Displays the schema for the specified **Object Name**.</span></span>  
  
     <span data-ttu-id="565e8-211">**Objektnamen**</span><span class="sxs-lookup"><span data-stu-id="565e8-211">**Object Name**</span></span>  
     <span data-ttu-id="565e8-212">Der Name des zu überwachenden Objekts.</span><span class="sxs-lookup"><span data-stu-id="565e8-212">The name of the object to audit.</span></span> <span data-ttu-id="565e8-213">Das Objekt ist nur für Überwachungsaktionen verfügbar, es gilt nicht für Überwachungsgruppen.</span><span class="sxs-lookup"><span data-stu-id="565e8-213">This is only available for audit actions; it does not apply to audit groups.</span></span>  
  
     <span data-ttu-id="565e8-214">**Auslassungspunkte (…)**</span><span class="sxs-lookup"><span data-stu-id="565e8-214">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="565e8-215">Öffnet das Dialogfeld **Objekte auswählen** , in dem Sie anhand des angegebenen **Überwachungsaktionstyps**nach einem verfügbaren Objekt suchen und es auswählen können.</span><span class="sxs-lookup"><span data-stu-id="565e8-215">Opens the **Select Objects** dialog to browse for and select an available object, based on the specified **Audit Action Type**.</span></span>  
  
     <span data-ttu-id="565e8-216">**Prinzipalname**</span><span class="sxs-lookup"><span data-stu-id="565e8-216">**Principal Name**</span></span>  
     <span data-ttu-id="565e8-217">Das Konto, anhand dessen die Überwachung für das zu überwachende Objekt gefiltert wird.</span><span class="sxs-lookup"><span data-stu-id="565e8-217">The account to filter the audit by for the object being audited.</span></span>  
  
     <span data-ttu-id="565e8-218">**Auslassungspunkte (…)**</span><span class="sxs-lookup"><span data-stu-id="565e8-218">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="565e8-219">Öffnet das Dialogfeld **Objekte auswählen** , in dem Sie nach einem verfügbaren Objekt anhand des angegebenen **Objektnamens**suchen und es auswählen können.</span><span class="sxs-lookup"><span data-stu-id="565e8-219">Opens the **Select Objects** dialog to browse for and select an available object, based on the specified **Object Name**.</span></span>  
  
3.  <span data-ttu-id="565e8-220">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="565e8-220">When you are finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="565e8-221">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="565e8-221">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-server-audit"></a><span data-ttu-id="565e8-222">So erstellen Sie eine Serverüberwachung</span><span class="sxs-lookup"><span data-stu-id="565e8-222">To create a server audit</span></span>  
  
1.  <span data-ttu-id="565e8-223">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="565e8-223">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="565e8-224">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="565e8-224">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="565e8-225">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="565e8-225">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates a server audit called "HIPAA_Audit" with a binary file as the target and no options.  
    CREATE SERVER AUDIT HIPAA_Audit  
        TO FILE ( FILEPATH ='\\SQLPROD_1\Audit\' );  
    ```  
  
#### <a name="to-create-a-server-audit-specification"></a><span data-ttu-id="565e8-226">So erstellen Sie eine Serverüberwachungsspezifikation</span><span class="sxs-lookup"><span data-stu-id="565e8-226">To create a server audit specification</span></span>  
  
1.  <span data-ttu-id="565e8-227">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="565e8-227">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="565e8-228">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="565e8-228">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="565e8-229">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="565e8-229">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    /*Creates a server audit specification called "HIPAA_Audit_Specification" that audits failed logins for the SQL Server audit "HIPAA_Audit" created above.  
    */  
  
    CREATE SERVER AUDIT SPECIFICATION HIPAA_Audit_Specification  
    FOR SERVER AUDIT HIPAA_Audit  
        ADD (FAILED_LOGIN_GROUP);  
    GO  
    -- Enables the audit.   
  
    ALTER SERVER AUDIT HIPAA_Audit  
    WITH (STATE = ON);  
    GO  
    ```  
  
 <span data-ttu-id="565e8-230">Weitere Informationen finden Sie unter [CREATE SERVER AUDIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-transact-sql) und [CREATE SERVER AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-specification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="565e8-230">For more information, see [CREATE SERVER AUDIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-transact-sql) and [CREATE SERVER AUDIT SPECIFICATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-audit-specification-transact-sql).</span></span>  
  
  
