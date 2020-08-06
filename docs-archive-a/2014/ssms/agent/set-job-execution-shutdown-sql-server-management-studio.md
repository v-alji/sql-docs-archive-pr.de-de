---
title: Festlegen des Herunterfahrens der Auftragsausführung (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], stopping
- SQL Server Agent jobs, stopping
- stopping jobs
- SQL Server Agent jobs, execution shutdowns
ms.assetid: ac23e88f-53fc-41de-bb16-0c27c002d5a5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0e60807676c3c54faf1d44de318ff0a31c2e20b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621315"
---
# <a name="set-job-execution-shutdown-sql-server-management-studio"></a><span data-ttu-id="96de5-102">Set Job Execution Shutdown (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="96de5-102">Set Job Execution Shutdown (SQL Server Management Studio)</span></span>
  <span data-ttu-id="96de5-103">In diesem Thema wird beschrieben, wie Sie die Zeit festlegen, die der-Agent auf die [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Beendigung von Ausführungs Aufträgen wartet, bevor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] der-Agent selbst in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von abgeschlossen wird [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96de5-103">This topic describes how to set the time that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will wait for executing jobs to finish before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent itself finishes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="96de5-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="96de5-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="96de5-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="96de5-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="96de5-106">Security</span><span class="sxs-lookup"><span data-stu-id="96de5-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="96de5-107">**So legen Sie eine Zeit für das Herunterfahren für einen SQL Server-Agent-Auftrag fest mit**</span><span class="sxs-lookup"><span data-stu-id="96de5-107">**To set a shutdown time for a SQL Server Agent job, using:**</span></span>  
  
     [<span data-ttu-id="96de5-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="96de5-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="96de5-109">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="96de5-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="96de5-110">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="96de5-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="96de5-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="96de5-111">Permissions</span></span>  
 <span data-ttu-id="96de5-112">Standardmäßig können Mitglieder der festen Serverrolle **sysadmin** festlegen, wie lange der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent auf die Beendigung von ausgeführten Aufträgen wartet, bevor der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent selbst beendet wird.</span><span class="sxs-lookup"><span data-stu-id="96de5-112">By default, members of the **sysadmin** fixed server role can set the time that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will wait for executing jobs to finish before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent itself finishes.</span></span> <span data-ttu-id="96de5-113">Andere Benutzer müssen Mitglieder der festen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Datenbankrollen in der **msdb** -Datenbank sein:</span><span class="sxs-lookup"><span data-stu-id="96de5-113">Other users must be granted one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the **msdb** database:</span></span>  
  
-   <span data-ttu-id="96de5-114">**SQLAgentUserRole**</span><span class="sxs-lookup"><span data-stu-id="96de5-114">**SQLAgentUserRole**</span></span>  
  
-   <span data-ttu-id="96de5-115">**SQLAgentReaderRole**</span><span class="sxs-lookup"><span data-stu-id="96de5-115">**SQLAgentReaderRole**</span></span>  
  
-   <span data-ttu-id="96de5-116">**SQLAgentOperatorRole**</span><span class="sxs-lookup"><span data-stu-id="96de5-116">**SQLAgentOperatorRole**</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="96de5-117">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="96de5-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-job-execution-shutdown"></a><span data-ttu-id="96de5-118">So legen Sie das Herunterfahren der Auftragsausführung fest</span><span class="sxs-lookup"><span data-stu-id="96de5-118">To set job execution shutdown</span></span>  
  
1.  <span data-ttu-id="96de5-119">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, auf dem Sie ein Intervall für das Herunterfahren der Auftragsausführung festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="96de5-119">In **Object Explorer,** , click the plus sign to expand the server where you want to set a job execution shutdown interval.</span></span>  
  
2.  <span data-ttu-id="96de5-120">Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent** , und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="96de5-120">Right-click **SQL Server Agent** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="96de5-121">Wählen Sie unter **Seite auswählen**die Option **Auftragssystem**aus.</span><span class="sxs-lookup"><span data-stu-id="96de5-121">Under **Select a page**, select **Job System**.</span></span>  
  
4.  <span data-ttu-id="96de5-122">Erhöhen oder reduzieren Sie den Wert für **Timeoutintervall beim Herunterfahren (Sekunden)** .</span><span class="sxs-lookup"><span data-stu-id="96de5-122">Set the **Shutdown time-out interval** in seconds to increase or decrease the shutdown time-out interval.</span></span> <span data-ttu-id="96de5-123">Damit wird bestimmt, wie lange der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent auf die Beendigung von ausführenden Aufträgen wartet, bevor der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent selbst beendet wird.</span><span class="sxs-lookup"><span data-stu-id="96de5-123">This determines how long [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will wait for executing jobs to finish before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent itself finishes.</span></span>  
  
  
