---
title: Schreiben von SQL-Serverüberwachungsereignissen in das Sicherheitsprotokoll | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], Security Log
- server audit [SQL Server]
- audits [SQL Server], writing to Security Log
- security logs [SQL Server]
ms.assetid: 6fabeea3-7a42-4769-a0f3-7e04daada314
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: d59134b278f29c9b604208d8cab7e982144b9c9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609772"
---
# <a name="write-sql-server-audit-events-to-the-security-log"></a><span data-ttu-id="3e634-102">Schreiben von SQL-Serverüberwachungsereignissen in das Sicherheitsprotokoll</span><span class="sxs-lookup"><span data-stu-id="3e634-102">Write SQL Server Audit Events to the Security Log</span></span>
  <span data-ttu-id="3e634-103">In einer Umgebung mit hoher Sicherheit ist das Windows-Sicherheitsprotokoll der geeignete Speicherort für Ereignisse, die Objektzugriffe aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="3e634-103">In a high security environment, the Windows Security log is the appropriate location to write events that record object access.</span></span> <span data-ttu-id="3e634-104">Andere Überwachungsspeicherorte werden unterstützt, können aber leichter manipuliert werden.</span><span class="sxs-lookup"><span data-stu-id="3e634-104">Other audit locations are supported but are more subject to tampering.</span></span>  
  
 <span data-ttu-id="3e634-105">Es gibt zwei Hauptanforderungen für das Schreiben von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Serverüberwachungen in das Windows-Sicherheitsprotokoll:</span><span class="sxs-lookup"><span data-stu-id="3e634-105">There are two key requirements for writing [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] server audits to the Windows Security log:</span></span>  
  
-   <span data-ttu-id="3e634-106">Die Einstellungen für die Überwachung von Objektzugriffsversuchen müssen so konfiguriert sein, dass die Ereignisse aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="3e634-106">The audit object access setting must be configured to capture the events.</span></span> <span data-ttu-id="3e634-107">Das Tool für Überwachungsrichtlinien (`auditpol.exe`) macht eine Vielzahl von Einstellungen für Unterrichtlinien in der Kategorie **Überwachung von Objektzugriffsversuchen** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3e634-107">The audit policy tool (`auditpol.exe`) exposes a variety of sub-policies settings in the **audit object access** category.</span></span> <span data-ttu-id="3e634-108">Um [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] die Überwachung des Objektzugriffs zu ermöglichen, konfigurieren Sie die Einstellung **automatisch generiert** .</span><span class="sxs-lookup"><span data-stu-id="3e634-108">To allow [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to audit object access, configure the **application generated** setting.</span></span>  
  
-   <span data-ttu-id="3e634-109">Das Konto, unter dem der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Dienst ausgeführt wird, muss über die Berechtigung zum **Generieren von Sicherheitsüberwachungen** verfügen, um in das Windows-Sicherheitsprotokoll schreiben zu können.</span><span class="sxs-lookup"><span data-stu-id="3e634-109">The account that the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service is running under must have the **generate security audits** permission to write to the Windows Security log.</span></span> <span data-ttu-id="3e634-110">Standardmäßig verfügen die Konten LOCAL SERVICE und NETWORK SERVICE über diese Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="3e634-110">By default, the LOCAL SERVICE and the NETWORK SERVICE accounts have this permission.</span></span> <span data-ttu-id="3e634-111">Dieser Schritt ist nicht erforderlich, wenn [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] unter einem dieser Konten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3e634-111">This step is not required if [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is running under one of those accounts.</span></span>  
  
 <span data-ttu-id="3e634-112">Die Windows-Überwachungsrichtlinie kann sich auf die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Überwachung auswirken, wenn sie so konfiguriert wurde, dass sie in das Windows-Sicherheitsprotokoll schreibt. In diesem Fall besteht bei einer falschen Konfiguration der Überwachungsrichtlinie die Gefahr, dass Ereignisse verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="3e634-112">The Windows audit policy can affect [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] auditing if it is configured to write to the Windows Security log, with the potential of losing events if the audit policy is incorrectly configured.</span></span> <span data-ttu-id="3e634-113">Das Windows-Sicherheitsprotokoll ist standardmäßig so konfiguriert, dass ältere Ereignisse überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="3e634-113">Typically, the Windows Security log is set to overwrite the older events.</span></span> <span data-ttu-id="3e634-114">Hierdurch werden immer die neuesten Ereignisse beibehalten.</span><span class="sxs-lookup"><span data-stu-id="3e634-114">This preserves the most recent events.</span></span> <span data-ttu-id="3e634-115">Wurde das Windows-Sicherheitsprotokoll jedoch so festgelegt, dass ältere Ereignisse nicht überschrieben werden, löst das System das Windows-Ereignis 1104 aus, sobald das Sicherheitsprotokoll voll ist.</span><span class="sxs-lookup"><span data-stu-id="3e634-115">However, if the Windows Security log is not set to overwrite older events, then if the Security log is full, the system will issue Windows event 1104 (Log is full).</span></span> <span data-ttu-id="3e634-116">In diesem Fall geschieht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3e634-116">At that point:</span></span>  
  
-   <span data-ttu-id="3e634-117">Es werden keine weiteren Sicherheitsereignisse aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3e634-117">No further security events will be recorded</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="3e634-118">kann nicht erkennen, dass das System keine Ereignisse mehr im Sicherheitsprotokoll aufzeichnen kann, sodass Überwachungsereignisse möglicherweise verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="3e634-118">will not be able to detect that the system is not able to record the events in the Security log, resulting in the potential loss of audit events</span></span>  
  
-   <span data-ttu-id="3e634-119">Nachdem der Administrator das Sicherheitsprotokoll korrigiert hat, wird die Protokollierung wieder wie gewohnt ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3e634-119">After the box administrator fixes the Security log, the logging behavior will return to normal.</span></span>  
  
 <span data-ttu-id="3e634-120">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="3e634-120">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3e634-121">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="3e634-121">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3e634-122">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="3e634-122">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="3e634-123">Security</span><span class="sxs-lookup"><span data-stu-id="3e634-123">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3e634-124">**So schreiben Sie SQL-Serverüberwachungsereignisse in das Sicherheitsprotokoll**</span><span class="sxs-lookup"><span data-stu-id="3e634-124">**To write SQL Server audit events to the Security Log:**</span></span>  
  
     [<span data-ttu-id="3e634-125">Konfigurieren der Einstellung für die Überwachung von Objektzugriffsversuchen in Windows mit "auditpol"</span><span class="sxs-lookup"><span data-stu-id="3e634-125">Configure the audit object access setting in Windows using auditpol</span></span>](#auditpolAccess)  
  
     [<span data-ttu-id="3e634-126">Konfigurieren der Einstellung für die Überwachung von Objektzugriffsversuchen in Windows mit "secpol"</span><span class="sxs-lookup"><span data-stu-id="3e634-126">Configure the audit object access setting in Windows using secpol</span></span>](#secpolAccess)  
  
     [<span data-ttu-id="3e634-127">Erteilen von Berechtigungen zum Generieren von Sicherheitsüberwachungen für ein Konto mit "secpol"</span><span class="sxs-lookup"><span data-stu-id="3e634-127">Grant the generate security audits permission to an account using secpol</span></span>](#secpolPermission)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3e634-128">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="3e634-128">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="3e634-129">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="3e634-129">Limitations and Restrictions</span></span>  
 <span data-ttu-id="3e634-130">Administratoren des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Computers sollten sich bewusst sein, dass lokale Einstellungen für das Sicherheitsprotokoll durch eine Domänenrichtlinie überschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="3e634-130">Administrators of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] computer should understand that local settings for the Security log can be overwritten by a domain policy.</span></span> <span data-ttu-id="3e634-131">In diesem Fall überschreibt die Domänenrichtlinie möglicherweise die Einstellung für die Unterkategorie (**auditpol /get /subcategory:"application generated"** ).</span><span class="sxs-lookup"><span data-stu-id="3e634-131">In this case, the domain policy might overwrite the subcategory setting (**auditpol /get /subcategory:"application generated"**).</span></span> <span data-ttu-id="3e634-132">Dies kann sich auf die Fähigkeit von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] auswirken, Ereignisse zu protokollieren. Dabei kann nicht nachvollzogen werden, dass die Ereignisse, die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] zu überwachen versucht, nicht aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="3e634-132">This can affect [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ability to log events without having any way to detect that the events that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is trying to audit are not going to be recorded.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3e634-133">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="3e634-133">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3e634-134">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="3e634-134">Permissions</span></span>  
 <span data-ttu-id="3e634-135">Sie müssen Windows-Administrator sein, um diese Einstellungen konfigurieren zu können.</span><span class="sxs-lookup"><span data-stu-id="3e634-135">You must be a Windows administrator to configure these settings.</span></span>  
  
##  <a name="to-configure-the-audit-object-access-setting-in-windows-using-auditpol"></a><a name="auditpolAccess"></a> <span data-ttu-id="3e634-136">So konfigurieren Sie die Einstellung für die Überwachung von Objektzugriffsversuchen in Windows mit "auditpol"</span><span class="sxs-lookup"><span data-stu-id="3e634-136">To configure the audit object access setting in Windows using auditpol</span></span>  
  
1.  <span data-ttu-id="3e634-137">Öffnen Sie eine Eingabeaufforderung mit Administratorberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="3e634-137">Open a command prompt with administrative permissions.</span></span>  
  
    1.  <span data-ttu-id="3e634-138">Zeigen Sie im Menü **Start** auf **Alle Programme**, zeigen Sie auf **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3e634-138">On the **Start** menu, point to **All Programs**, point to **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>  
  
    2.  <span data-ttu-id="3e634-139">Wenn das Dialogfeld **Benutzerkontensteuerung** geöffnet wird, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3e634-139">If the **User Account Control** dialog box opens, click **Continue**.</span></span>  
  
2.  <span data-ttu-id="3e634-140">Führen Sie die folgende Anweisung aus, um die Überwachung von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3e634-140">Execute the following statement to enable auditing from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
    ```  
    auditpol /set /subcategory:"application generated" /success:enable /failure:enable  
    ```  
  
3.  <span data-ttu-id="3e634-141">Schließen Sie das Eingabeaufforderungsfenster.</span><span class="sxs-lookup"><span data-stu-id="3e634-141">Close the command prompt window.</span></span>  
  
##  <a name="to-grant-the-generate-security-audits-permission-to-an-account-using-secpol"></a><a name="secpolAccess"></a> <span data-ttu-id="3e634-142">So erteilen Sie die Berechtigung zum Generieren von Sicherheitsüberwachungen für ein Konto mit "secpol"</span><span class="sxs-lookup"><span data-stu-id="3e634-142">To grant the generate security audits permission to an account using secpol</span></span>  
  
1.  <span data-ttu-id="3e634-143">Klicken Sie in allen Windows-Betriebssystemen im Menü **Start** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3e634-143">For any Windows operating system, on the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="3e634-144">Geben Sie **secpol.msc** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e634-144">Type **secpol.msc** and then click **OK**.</span></span> <span data-ttu-id="3e634-145">Wenn das Dialogfeld **Benutzerzugriffssteuerung** angezeigt wird, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3e634-145">If the **User Access Control** dialog box appears, click **Continue**.</span></span>  
  
3.  <span data-ttu-id="3e634-146">Erweitern Sie im Tool "Lokale Sicherheitsrichtlinie" die **Sicherheitseinstellungen**, erweitern Sie **Lokale Richtlinien**, und klicken Sie dann auf **Zuweisen von Benutzerrechten**.</span><span class="sxs-lookup"><span data-stu-id="3e634-146">In the Local Security Policy tool, expand **Security Settings**, expand **Local Policies**, and then click **User Rights Assignment**.</span></span>  
  
4.  <span data-ttu-id="3e634-147">Doppelklicken Sie im Ergebnisbereich auf **Generieren von Sicherheitsüberwachungen**.</span><span class="sxs-lookup"><span data-stu-id="3e634-147">In the results pane, double-click **Generate security audits**.</span></span>  
  
5.  <span data-ttu-id="3e634-148">Klicken Sie auf der Registerkarte **Lokale Sicherheitseinstellung** auf **Benutzer oder Gruppe hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3e634-148">On the **Local Security Setting** tab, click **Add User or Group**.</span></span>  
  
6.  <span data-ttu-id="3e634-149">Geben Sie im Dialogfeld **Benutzer, Computer oder Gruppen auswählen** entweder den Namen des Benutzerkontos, z. B. **Domäne1\Benutzer1** ein, und klicken Sie dann auf **OK**, oder klicken Sie auf **Erweitert** , und suchen Sie nach dem Konto.</span><span class="sxs-lookup"><span data-stu-id="3e634-149">In the **Select Users, Computers, or Groups** dialog box, either type the name of the user account, such as **domain1\user1** and then click **OK**, or click **Advanced** and search for the account.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="3e634-150">Schließen Sie das Tool "Sicherheitsrichtlinie".</span><span class="sxs-lookup"><span data-stu-id="3e634-150">Close the Security Policy tool.</span></span>  
  
9. <span data-ttu-id="3e634-151">Starten Sie [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] neu, um diese Einstellung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3e634-151">Restart [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to enable this setting.</span></span>  
  
##  <a name="to-configure-the-audit-object-access-setting-in-windows-using-secpol"></a><a name="secpolPermission"></a> <span data-ttu-id="3e634-152">So konfigurieren Sie die Einstellung für die Überwachung von Objektzugriffsversuchen in Windows mit "secpol"</span><span class="sxs-lookup"><span data-stu-id="3e634-152">To configure the audit object access setting in Windows using secpol</span></span>  
  
1.  <span data-ttu-id="3e634-153">Wenn das Betriebssystem eine frühere Version als [!INCLUDE[wiprlhext](../../../includes/wiprlhext-md.md)] oder Windows Server 2008 ist, klicken Sie im Menü **Start** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="3e634-153">If the operating system is earlier than [!INCLUDE[wiprlhext](../../../includes/wiprlhext-md.md)] or Windows Server 2008, on the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="3e634-154">Geben Sie **secpol.msc** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e634-154">Type **secpol.msc** and then click **OK**.</span></span> <span data-ttu-id="3e634-155">Wenn das Dialogfeld **Benutzerzugriffssteuerung** angezeigt wird, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3e634-155">If the **User Access Control** dialog box appears, click **Continue**.</span></span>  
  
3.  <span data-ttu-id="3e634-156">Erweitern Sie im Tool "Lokale Sicherheitsrichtlinie" die **Sicherheitseinstellungen**, erweitern Sie **Lokale Richtlinien**, und klicken Sie dann auf **Überwachungsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="3e634-156">In the Local Security Policy tool, expand **Security Settings**, expand **Local Policies**, and then click **Audit Policy**.</span></span>  
  
4.  <span data-ttu-id="3e634-157">Doppelklicken Sie im Ergebnisbereich auf **Objektzugriffsversuche überwachen**.</span><span class="sxs-lookup"><span data-stu-id="3e634-157">In the results pane, double-click **Audit object access**.</span></span>  
  
5.  <span data-ttu-id="3e634-158">Wählen Sie im Bereich **Diese Versuche überwachen** auf der Registerkarte **Lokale Sicherheitseinstellung** sowohl **Erfolg** als auch **Fehler**aus.</span><span class="sxs-lookup"><span data-stu-id="3e634-158">On the **Local Security Setting** tab, in the **Audit these attempts** area, select both **Success** and **Failure**.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="3e634-159">Schließen Sie das Tool "Sicherheitsrichtlinie".</span><span class="sxs-lookup"><span data-stu-id="3e634-159">Close the Security Policy tool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e634-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3e634-160">See Also</span></span>  
 [<span data-ttu-id="3e634-161">SQL Server Audit &#40;Datenbank-Engine&#41;</span><span class="sxs-lookup"><span data-stu-id="3e634-161">SQL Server Audit &#40;Database Engine&#41;</span></span>](sql-server-audit-database-engine.md)  
  
  
