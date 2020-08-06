---
title: Anzeigen von Auftragsschrittinformationen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- displaying job step information
- jobs [SQL Server Agent], viewing
- SQL Server Agent jobs, viewing
- viewing job step information
ms.assetid: e3f06492-dc86-4e06-b186-ea58aff6d591
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5d9fc6a006884bc564b5db2bfa8b168c8ae59149
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607535"
---
# <a name="view-job-step-information"></a><span data-ttu-id="1324f-102">View Job Step Information</span><span class="sxs-lookup"><span data-stu-id="1324f-102">View Job Step Information</span></span>
  <span data-ttu-id="1324f-103">In diesem Thema wird beschrieben, wie Sie die Auftragsschrittdetails im Auftragsschritt-Eigenschaftendialogfeld anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1324f-103">This topic describes how to view job step details in the Job Step Properties dialog.</span></span> <span data-ttu-id="1324f-104">Es enthält auch Informationen zum Anzeigen der Auftragsschrittausgabe.</span><span class="sxs-lookup"><span data-stu-id="1324f-104">It also includes information about viewing job step output.</span></span>  
  
-   <span data-ttu-id="1324f-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="1324f-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1324f-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1324f-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="1324f-107">Security</span><span class="sxs-lookup"><span data-stu-id="1324f-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1324f-108">**So zeigen Sie Auftragsschrittinformationen an mit**</span><span class="sxs-lookup"><span data-stu-id="1324f-108">**To view job step information, using:**</span></span>  
  
     [<span data-ttu-id="1324f-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1324f-109">SQL Server Management Studio</span></span>](#SSMS)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1324f-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="1324f-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1324f-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1324f-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="1324f-112">Wenn der Auftragsschritt so konfiguriert wurde, dass seine Ausgabe in eine Tabelle oder Datei geschrieben wird, und der Auftrag wurde mindestens einmal ausgeführt, können Sie die Ausgabe auf der Seite **Erweitert** des Dialogfelds **Auftragsschritt-Eigenschaften** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1324f-112">If the job step has been configured to write its output to a table or file and the job has run at least once, you can view its output on the **Advanced** page of the **Job Step Properties** dialog.</span></span> <span data-ttu-id="1324f-113">Beim Löschen eines Auftrags oder Auftragsschritts wird das Ausgabeprotokoll automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="1324f-113">When a job or job step is deleted, the output log is automatically deleted.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1324f-114">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="1324f-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1324f-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1324f-115">Permissions</span></span>  
 <span data-ttu-id="1324f-116">Sie können nur die Aufträge anzeigen, die Sie besitzen, es sei denn, Sie sind ein Mitglied der festen Serverrolle **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="1324f-116">You can view only those jobs that you own, unless you are a member of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="1324f-117">Mitglieder dieser Rolle können alle Aufträge und Auftragsschrittdetails anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1324f-117">Members of this role can view all jobs and job step details.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="1324f-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1324f-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-job-step-information"></a><span data-ttu-id="1324f-119">So zeigen Sie Auftragsschrittinformationen an</span><span class="sxs-lookup"><span data-stu-id="1324f-119">To view job step information</span></span>  
  
1.  <span data-ttu-id="1324f-120">Stellen Sie in **Objekt-Explorer** eine Verbindung mit einer Instanz von her [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="1324f-120">In **Object Explorer,** connect to an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="1324f-121">Erweitern Sie **SQL Server-Agent**, erweitern Sie **Aufträge**, klicken Sie mit der rechten Maustaste auf den Auftrag, dessen Auftragsschritte Sie anzeigen möchten, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="1324f-121">Expand **SQL Server Agent**, expand **Jobs**, right-click the job that contains the job step to be viewed, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="1324f-122">Wählen Sie im Dialogfeld **Auftragseigenschaften** die Seite **Schritte** aus.</span><span class="sxs-lookup"><span data-stu-id="1324f-122">In the **Job Properties** dialog, click the **Steps** page.</span></span>  
  
4.  <span data-ttu-id="1324f-123">Klicken Sie auf den anzuzeigenden Auftragsschritt, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="1324f-123">Click the job step to be viewed, and click **Edit**.</span></span>  
  
5.  <span data-ttu-id="1324f-124">Sie können auf der Seite **Allgemein** des Dialogfelds **Auftragsschritt-Eigenschaften** den Typ des Auftragsschritts anzeigen und welche Aktion er ausführt.</span><span class="sxs-lookup"><span data-stu-id="1324f-124">On the **General** page of the **Job Step Properties** dialog, you can view the type of job step and what it does.</span></span>  
  
6.  <span data-ttu-id="1324f-125">Klicken Sie auf die Seite **Erweitert** , um die Aktionen des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents anzuzeigen wenn der Auftragsschritt erfolgreich ausgeführt wird oder einen Fehler erzeugt, wie oft der Auftragsschritt wiederholt werden sollte, wohin die Auftragsschrittausgabe geschrieben wird und welcher Benutzer den Auftragsschritt ausführt.</span><span class="sxs-lookup"><span data-stu-id="1324f-125">Click the **Advanced** page to view the actions [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent takes if the job step succeeds or fails, how many times the job step should be attempted, where the job step output is written, and the user the job step runs as.</span></span>  
  
#### <a name="to-view-job-step-output"></a><span data-ttu-id="1324f-126">So zeigen Sie die Auftragsschrittausgabe an</span><span class="sxs-lookup"><span data-stu-id="1324f-126">To view job step output</span></span>  
  
1.  <span data-ttu-id="1324f-127">Klicken Sie im Dialogfeld **Auftragsschritt-Eigenschaften** auf die Seite **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="1324f-127">In the **Job Step Properties** dialog, click the **Advanced** page.</span></span>  
  
2.  <span data-ttu-id="1324f-128">Abhängig von der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Version, mit der Sie verbunden sind, können Sie entweder die Auftragsschritt-Ausgabedatei oder die Auftragsschritt-Ausgabetabelle wie folgt anzeigen:</span><span class="sxs-lookup"><span data-stu-id="1324f-128">Depending on the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connected to, you can view either the job step output file or table as follows:</span></span>  
  
    -   <span data-ttu-id="1324f-129">Wenn Sie mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oder einer höheren Version verbunden sind, können Sie nur dann auf **Anzeigen** klicken, wenn **In Tabelle protokollieren** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1324f-129">When you are connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or later, you can click **View** only when **Log to table** is checked.</span></span> <span data-ttu-id="1324f-130">In diesem Fall wird die Auftragsschrittausgabe in die **sysjobstepslogs** -Tabelle der **msdb** -Datenbank geschrieben.</span><span class="sxs-lookup"><span data-stu-id="1324f-130">In this case, the job step output is written to the **sysjobstepslogs** table in the **msdb** database.</span></span>  
  
    -   <span data-ttu-id="1324f-131">Die Schaltfläche **Anzeigen** ist deaktiviert, wenn die Auftragsschrittausgabe in eine Datei geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="1324f-131">The **View** button is disabled when job step output is written to a file.</span></span> <span data-ttu-id="1324f-132">Verwenden Sie den Editor zum Anzeigen der Auftragsschritt-Ausgabedatei.</span><span class="sxs-lookup"><span data-stu-id="1324f-132">To view a job step output file, use Notepad.</span></span>  
  
  
