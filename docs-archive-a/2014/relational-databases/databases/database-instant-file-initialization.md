---
title: Sofortige Datenbankdateiinitialisierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- initializing files [SQL Server]
- instant file initializations [SQL Server]
- fast file initialization (SQL Server)
- file initialization [SQL Server]
ms.assetid: 1ad468f5-4f75-480b-aac6-0b01b048bd67
author: stevestein
ms.author: sstein
ms.openlocfilehash: dedd2c5b8d075dee8aeeb438904137558c664d95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617104"
---
# <a name="database-instant-file-initialization"></a><span data-ttu-id="27076-102">Sofortige Datenbankdateiinitialisierung</span><span class="sxs-lookup"><span data-stu-id="27076-102">Database Instant File Initialization</span></span>
  <span data-ttu-id="27076-103">Daten- und Protokolldateien werden initialisiert, um vorhandene Daten zu überschreiben, die von zuvor gelöschten Dateien auf dem Datenträger zurückgelassen wurden.</span><span class="sxs-lookup"><span data-stu-id="27076-103">Data and log files are initialized to overwrite any existing data left on the disk from previously deleted files.</span></span> <span data-ttu-id="27076-104">Daten- und Protokolldateien werden erstmals durch Ausfüllen der Dateien mit Nullen initialisiert, wenn Sie eine der folgenden Operationen ausführen:</span><span class="sxs-lookup"><span data-stu-id="27076-104">Data and log files are first initialized by filling the files with zeros when you perform one of the following operations:</span></span>  
  
-   <span data-ttu-id="27076-105">Erstellen einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="27076-105">Create a database.</span></span>  
  
-   <span data-ttu-id="27076-106">Hinzufügen von Dateien, Protokoll- oder Datendateien, zu einer vorhandenen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="27076-106">Add files, log or data, to an existing database.</span></span>  
  
-   <span data-ttu-id="27076-107">Vergrößern einer vorhanden Datei (einschließlich Vorgängen zur automatischen Vergrößerung).</span><span class="sxs-lookup"><span data-stu-id="27076-107">Increase the size of an existing file (including autogrow operations).</span></span>  
  
-   <span data-ttu-id="27076-108">Wiederherstellen einer Datenbank oder Dateigruppe</span><span class="sxs-lookup"><span data-stu-id="27076-108">Restore a database or filegroup.</span></span>  
  
 <span data-ttu-id="27076-109">Die Dateiinitialisierung führt dazu, dass diese Vorgänge mehr Zeit benötigen.</span><span class="sxs-lookup"><span data-stu-id="27076-109">File initialization causes these operations to take longer.</span></span> <span data-ttu-id="27076-110">Aber wenn die Daten zum ersten Mal an die Dateien geschrieben werden, muss das Betriebssystem die Dateien nicht mit Nullen ausfüllen.</span><span class="sxs-lookup"><span data-stu-id="27076-110">However, when data is written to the files for the first time, the operating system does not have to fill the files with zeros.</span></span>  
  
## <a name="instant-file-initialization"></a><span data-ttu-id="27076-111">Sofortige Dateiinitialisierung</span><span class="sxs-lookup"><span data-stu-id="27076-111">Instant File Initialization</span></span>  
 <span data-ttu-id="27076-112">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]können Datendateien sofort initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="27076-112">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], data files can be initialized instantaneously.</span></span> <span data-ttu-id="27076-113">Damit ist eine schnelle Ausführung der zuvor erwähnten Dateivorgänge möglich.</span><span class="sxs-lookup"><span data-stu-id="27076-113">This allows for fast execution of the previously mentioned file operations.</span></span> <span data-ttu-id="27076-114">Bei der sofortigen Dateiinitialisierung wird belegter Speicherplatz freigegeben, ohne diesen Speicherplatz mit Nullen auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="27076-114">Instant file initialization reclaims used disk space without filling that space with zeros.</span></span> <span data-ttu-id="27076-115">Stattdessen wird Datenträgerinhalt überschrieben, wenn neue Daten an die Dateien geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="27076-115">Instead, disk content is overwritten as new data is written to the files.</span></span> <span data-ttu-id="27076-116">Protokolldateien können nicht sofort initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="27076-116">Log files cannot be initialized instantaneously.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="27076-117">Die sofortige Dateiinitialisierung ist nur in [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[winxppro](../../includes/winxppro-md.md)] oder [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] oder höheren Versionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="27076-117">Instant file initialization is available only on [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[winxppro](../../includes/winxppro-md.md)] or [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] or later versions.</span></span>  
  
 <span data-ttu-id="27076-118">Die sofortige Dateiinitialisierung ist nur verfügbar, wenn dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER)-Servicekonto SE_MANAGE_VOLUME_NAME erteilt wurde.</span><span class="sxs-lookup"><span data-stu-id="27076-118">Instant file initialization is only available if the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER) service account has been granted SE_MANAGE_VOLUME_NAME.</span></span> <span data-ttu-id="27076-119">Mitglieder der Windows-Administratorengruppe verfügen über dieses Recht und können es anderen Benutzern erteilen, indem sie diese der Sicherheitsrichtlinie **Durchführen von Volumewartungsaufgaben** hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="27076-119">Members of the Windows Administrator group have this right and can grant it to other users by adding them to the **Perform Volume Maintenance Tasks** security policy.</span></span> <span data-ttu-id="27076-120">Weitere Informationen zum Zuweisen von Benutzerrechten finden Sie in der Windows-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="27076-120">For more information about assigning user rights, see the Windows documentation.</span></span>  
  
 <span data-ttu-id="27076-121">Die sofortige Dateiinitialisierung ist nicht verfügbar, wenn TDE aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="27076-121">Instant file initialization is not available when TDE is enabled.</span></span>  
  
 <span data-ttu-id="27076-122">So erteilen Sie einem Konto die Berechtigung `Perform volume maintenance tasks` :</span><span class="sxs-lookup"><span data-stu-id="27076-122">To grant an account the `Perform volume maintenance tasks` permission:</span></span>  
  
1.  <span data-ttu-id="27076-123">Öffnen Sie auf dem Computer, auf die Sicherungsdatei erstellt wird, die Anwendung `Local Security Policy` (`secpol.msc`).</span><span class="sxs-lookup"><span data-stu-id="27076-123">On the computer where the backup file will be created, open the `Local Security Policy` application (`secpol.msc`).</span></span>  
  
2.  <span data-ttu-id="27076-124">Erweitern Sie im linken Bereich **Lokale Richtlinien**, und klicken Sie dann auf **Zuweisen von Benutzerrechten**.</span><span class="sxs-lookup"><span data-stu-id="27076-124">In the left pane, expand **Local Policies**, and then click **User Rights Assignment**.</span></span>  
  
3.  <span data-ttu-id="27076-125">Doppelklicken Sie im rechten Bereich auf **Durchführen von Volumewartungsaufgaben**.</span><span class="sxs-lookup"><span data-stu-id="27076-125">In the right pane, double-click **Perform volume maintenance tasks**.</span></span>  
  
4.  <span data-ttu-id="27076-126">Klicken Sie auf **Benutzer oder Gruppe hinzufügen** , und fügen Sie alle Benutzerkonten hinzu, die für Sicherungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="27076-126">Click **Add User or Group** and add any user accounts that are used for backups.</span></span>  
  
5.  <span data-ttu-id="27076-127">Klicken **Sie**auf übernehmen, und schließen Sie dann alle `Local Security Policy` Dialogfelder.</span><span class="sxs-lookup"><span data-stu-id="27076-127">Click **Apply**, and then close all `Local Security Policy` dialog boxes.</span></span>  
  
### <a name="security-considerations"></a><span data-ttu-id="27076-128">Überlegungen zur Sicherheit</span><span class="sxs-lookup"><span data-stu-id="27076-128">Security Considerations</span></span>  
 <span data-ttu-id="27076-129">Da der gelöschte Datenträgerinhalt nur überschrieben wird, wenn neue Daten an die Dateien geschrieben wird, kann ein nicht autorisierter Prinzipal möglicherweise auf den gelöschten Inhalt zugreifen.</span><span class="sxs-lookup"><span data-stu-id="27076-129">Because the deleted disk content is overwritten only as new data is written to the files, the deleted content might be accessed by an unauthorized principal.</span></span> <span data-ttu-id="27076-130">Während die Datenbankdatei an die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]angefügt ist, wird diese Bedrohung einer Offenlegung von Informationen durch die besitzerverwaltete Zugriffssteuerungsliste (Discretionary Access Control List, DACL) in der Datei verringert.</span><span class="sxs-lookup"><span data-stu-id="27076-130">While the database file is attached to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this information disclosure threat is reduced by the discretionary access control list (DACL) on the file.</span></span> <span data-ttu-id="27076-131">Diese DACL gewährt den Dateizugriff nur für das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienstkonto und den lokalen Administrator.</span><span class="sxs-lookup"><span data-stu-id="27076-131">This DACL allows file access only to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and the local administrator.</span></span> <span data-ttu-id="27076-132">Wenn die Datei jedoch getrennt wird, kann möglicherweise ein Benutzer oder Dienst darauf zugreifen, der nicht über SE_MANAGE_VOLUME_NAME verfügt.</span><span class="sxs-lookup"><span data-stu-id="27076-132">However, when the file is detached, it may be accessed by a user or service that does not have SE_MANAGE_VOLUME_NAME.</span></span> <span data-ttu-id="27076-133">Eine ähnliche Bedrohung besteht, wenn die Datenbank gesichert wird.</span><span class="sxs-lookup"><span data-stu-id="27076-133">A similar threat exists when the database is backed up.</span></span> <span data-ttu-id="27076-134">Der gelöschte Inhalt kann für einen nicht autorisierten Benutzer oder Dienst verfügbar werden, wenn die Sicherungsdatei nicht mit einer entsprechenden DACL geschützt wird.</span><span class="sxs-lookup"><span data-stu-id="27076-134">The deleted content can become available to an unauthorized user or service if the backup file is not protected with an appropriate DACL.</span></span>  
  
 <span data-ttu-id="27076-135">Wenn Sie sich Gedanken über eine potenzielle Offenlegung von Informationen machen, sollten Sie eine oder beide der folgenden Maßnahmen treffen:</span><span class="sxs-lookup"><span data-stu-id="27076-135">If the potential for disclosing deleted content is a concern, you should do one or both of the following:</span></span>  
  
-   <span data-ttu-id="27076-136">Stellen Sie immer sicher, dass alle angebundenen Daten- und Sicherungsdateien über restriktive DACLs verfügen.</span><span class="sxs-lookup"><span data-stu-id="27076-136">Always make sure that any detached data files and backup files have restrictive DACLs.</span></span>  
  
-   <span data-ttu-id="27076-137">Deaktivieren Sie die sofortige Dateiinitialisierung für die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , indem Sie SE_MANAGE_VOLUME_NAME im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienstkonto widerrufen.</span><span class="sxs-lookup"><span data-stu-id="27076-137">Disable instant file initialization for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by revoking SE_MANAGE_VOLUME_NAME from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="27076-138">Das Deaktivieren der sofortigen Dateiinitialisierung wirkt sich nur auf Dateien aus, die nach dem Widerrufen des Benutzerrechts erstellt oder vergrößert werden.</span><span class="sxs-lookup"><span data-stu-id="27076-138">Disabling instant file initialization only affects files that are created or increased in size after the user right is revoked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27076-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="27076-139">See Also</span></span>  
 [<span data-ttu-id="27076-140">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="27076-140">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
  
