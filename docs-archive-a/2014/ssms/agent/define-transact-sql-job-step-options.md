---
title: So definieren Sie die Optionen für Transact-SQL-Auftragsschritte | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL job step
- job steps [Transact-SQL]
- SQL Server Agent jobs, Transact-SQL step
ms.assetid: b2a47057-f6fb-432b-a7b6-5d61f33a5d9c
author: stevestein
ms.author: sstein
ms.openlocfilehash: cc1d6412e52e74ce0c6d987d6189c0c72ffd7df7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696370"
---
# <a name="define-transact-sql-job-step-options"></a><span data-ttu-id="dbb74-102">Definieren von Optionen für Transact-SQL-Auftragsschritte</span><span class="sxs-lookup"><span data-stu-id="dbb74-102">Define Transact-SQL Job Step Options</span></span>
  <span data-ttu-id="dbb74-103">In diesem Thema wird beschrieben, wie Optionen für- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent- [!INCLUDE[tsql](../../includes/tsql-md.md)] Auftrags Schritte in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder SQL Server Management Objects definiert werden.</span><span class="sxs-lookup"><span data-stu-id="dbb74-103">This topic describes how to define options for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent [!INCLUDE[tsql](../../includes/tsql-md.md)] job steps in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or SQL Server Management Objects.</span></span>  
  
 <span data-ttu-id="dbb74-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="dbb74-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="dbb74-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="dbb74-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="dbb74-106">Security</span><span class="sxs-lookup"><span data-stu-id="dbb74-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="dbb74-107">**So definieren Sie die Optionen für Transact-SQL-Auftragsschritte mit**</span><span class="sxs-lookup"><span data-stu-id="dbb74-107">**To define Transact-SQL job step options, using:** ,</span></span>  
  
     [<span data-ttu-id="dbb74-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dbb74-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="dbb74-109">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="dbb74-109">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dbb74-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="dbb74-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dbb74-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="dbb74-111">Security</span></span>  
 <span data-ttu-id="dbb74-112">Ausführliche Informationen finden Sie unter [Implementieren der SQL Server-Agent-Sicherheit](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="dbb74-112">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="dbb74-113">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dbb74-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-define-transact-sql-job-step-options"></a><span data-ttu-id="dbb74-114">So definieren Sie die Optionen für Transact-SQL-Auftragsschritte</span><span class="sxs-lookup"><span data-stu-id="dbb74-114">To define Transact-SQL job step options</span></span>  
  
1.  <span data-ttu-id="dbb74-115">Erweitern Sie in **Objekt-Explorer**die Option **SQL Server-Agent**, und erweitern Sie **Aufträge**. Klicken Sie mit der rechten Maustaste auf den Auftrag, den sie bearbeiten möchten, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="dbb74-115">In **Object Explorer**, expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="dbb74-116">Klicken Sie auf die Seite **Schritte** , klicken Sie auf einen Auftragsschritt und dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="dbb74-116">Click the **Steps** page, click a job step, and then click **Edit**.</span></span>  
  
3.  <span data-ttu-id="dbb74-117">Bestätigen Sie im Dialogfeld **Auftragsschritt-Eigenschaften** , ob **Transact-SQL-Skript (TSQL)** als Typ festgelegt ist, und klicken Sie dann auf die Seite **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="dbb74-117">On the **Job Step Properties** dialog, confirm that the job type is **Transact-SQL script (TSQL)**, and then select the **Advanced** page.</span></span>  
  
4.  <span data-ttu-id="dbb74-118">Wählen Sie in der Liste **Aktion bei Erfolg** aus, welche Aktion ausgeführt werden soll, wenn der Auftrag erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="dbb74-118">Specify an action to take if the job is successful by selecting from the **On success action** list.</span></span>  
  
5.  <span data-ttu-id="dbb74-119">Geben Sie die Anzahl von Wiederholungsversuchen an, indem Sie in das Feld **Wiederholungsversuche** eine Zahl zwischen 0 und 9999 eingeben.</span><span class="sxs-lookup"><span data-stu-id="dbb74-119">Specify a number of retry attempts by entering a number from 0 to 9999 into the **Retry attempts** box.</span></span>  
  
6.  <span data-ttu-id="dbb74-120">Geben Sie ein Wiederholungsintervall an, indem Sie in das Feld **Wiederholungsintervall** einen Wert zwischen 0 und 9999 Minuten eingeben.</span><span class="sxs-lookup"><span data-stu-id="dbb74-120">Specify a retry interval by entering a number of minutes from 0 to 9999 into the **Retry interval** box.</span></span>  
  
7.  <span data-ttu-id="dbb74-121">Wählen Sie in der Liste **Aktion bei Fehler** eine Aktion aus, die ausgeführt werden soll, wenn der Auftrag fehlerhaft verläuft.</span><span class="sxs-lookup"><span data-stu-id="dbb74-121">Specify an action to take if the job fails by choosing from the **On failure action** list.</span></span>  
  
8.  <span data-ttu-id="dbb74-122">Wenn es sich bei dem Auftrag um ein [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skript handelt, können Sie eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="dbb74-122">If the job is a [!INCLUDE[tsql](../../includes/tsql-md.md)] script, you can choose from the following options:</span></span>  
  
    -   <span data-ttu-id="dbb74-123">Geben Sie den Namen einer **Ausgabedatei**ein.</span><span class="sxs-lookup"><span data-stu-id="dbb74-123">Enter the name of an **Output file**.</span></span> <span data-ttu-id="dbb74-124">Diese Datei wird standardmäßig bei jeder Ausführung des Auftragsschrittes überschrieben.</span><span class="sxs-lookup"><span data-stu-id="dbb74-124">By default the file is overwritten each time the job step executes.</span></span> <span data-ttu-id="dbb74-125">Wenn Sie nicht möchten, dass die Ausgabedatei überschrieben wird, aktivieren Sie **Ausgabe an vorhandene Datei anfügen**.</span><span class="sxs-lookup"><span data-stu-id="dbb74-125">If you do not want the output file overwritten, check **Append output to existing file**.</span></span> <span data-ttu-id="dbb74-126">Diese Option ist nur für Mitglieder der festen Serverrolle **sysadmin** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dbb74-126">This option is only available to members of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="dbb74-127">Beachten Sie, dass Benutzer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] nicht beliebige Dateien im Dateisystem anzeigen können. Deshalb können mit [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] keine Auftragsschrittprotokolle angezeigt werden, die in das Dateisystem geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="dbb74-127">Note that [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] does not allow users to view arbitrary files on the file system, so you cannot use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to view job step logs that are written to the file system.</span></span>  
  
    -   <span data-ttu-id="dbb74-128">Aktivieren Sie **In Tabelle protokollieren** , wenn der Auftragsschritt in einer Datenbanktabelle protokolliert werden soll.</span><span class="sxs-lookup"><span data-stu-id="dbb74-128">Check **Log to table** if you want to log the job step to a database table.</span></span> <span data-ttu-id="dbb74-129">Standardmäßig wird der Tabelleninhalt bei jeder Ausführung des Auftragsschrittes überschrieben.</span><span class="sxs-lookup"><span data-stu-id="dbb74-129">By default the table contents are overwritten each time the job step executes.</span></span> <span data-ttu-id="dbb74-130">Wenn der Tabelleninhalt nicht überschrieben werden soll, aktivieren Sie **Ausgabe an vorhandenen Eintrag in Tabelle anfügen**.</span><span class="sxs-lookup"><span data-stu-id="dbb74-130">If you do not want the table contents overwritten, check **Append output to existing entry in table**.</span></span> <span data-ttu-id="dbb74-131">Nachdem der Auftragsschritt ausgeführt wurde, können Sie den Inhalt dieser Tabelle anzeigen, indem Sie auf **Anzeigen**klicken.</span><span class="sxs-lookup"><span data-stu-id="dbb74-131">After the job step executes, you can view the contents of this table by clicking **View**.</span></span>  
  
    -   <span data-ttu-id="dbb74-132">Aktivieren Sie **Schrittausgabe in Verlauf einschließen** , wenn die Ausgabe in den Schrittverlauf eingeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="dbb74-132">Check **Include step output in history** if you want the output included in the step's history.</span></span> <span data-ttu-id="dbb74-133">Die Ausgabe wird nur angezeigt, wenn keine Fehler auftraten.</span><span class="sxs-lookup"><span data-stu-id="dbb74-133">Output will only be shown if there were no errors.</span></span> <span data-ttu-id="dbb74-134">Es kann auch vorkommen, dass die Ausgabe abgeschnitten wird.</span><span class="sxs-lookup"><span data-stu-id="dbb74-134">Also, output may be truncated.</span></span>  
  
9. <span data-ttu-id="dbb74-135">Wenn Sie ein Mitglied der festen Serverrolle **sysadmin** sind und diesen Auftragsschritt unter einem anderen SQL-Anmeldenamen ausführen möchten, wählen Sie den SQL-Anmeldenamen in der Liste **Ausführen als Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="dbb74-135">If you are a member of the **sysadmin** fixed server role and you want to run this job step as a different SQL login, select the SQL login from the **Run as user** list.</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="dbb74-136">Verwenden von SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="dbb74-136">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="dbb74-137">**So definieren Sie die Optionen für Transact-SQL-Auftragsschritte**</span><span class="sxs-lookup"><span data-stu-id="dbb74-137">**To define Transact-SQL job step options**</span></span>  
  
 <span data-ttu-id="dbb74-138">Verwenden Sie die `JobStep`-Klasse in einer von Ihnen ausgewählten Programmiersprache, z. B. Visual Basic, Visual C# oder PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dbb74-138">Use the `JobStep` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span>  
  
  
