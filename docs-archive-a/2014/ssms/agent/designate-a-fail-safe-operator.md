---
title: Bestimmen eines Ausfallsicherheitsoperators | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- fail-safe operator [SQL Server]
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
ms.assetid: 0f4eb513-5c0a-4523-974e-e85c1deeb57f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 714ed78875bd289f2fe2d64a5699c59bce58ced0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722202"
---
# <a name="designate-a-fail-safe-operator"></a><span data-ttu-id="1a6db-102">Bestimmen eines Ausfallsicherheitsoperators</span><span class="sxs-lookup"><span data-stu-id="1a6db-102">Designate a Fail-Safe Operator</span></span>
  <span data-ttu-id="1a6db-103">Ein Ausfallsicherheitsoperator ist ein Benutzer, der die Warnungen empfängt, wenn der vorgesehene Operator nicht erreichbar ist.</span><span class="sxs-lookup"><span data-stu-id="1a6db-103">A fail-safe operator is a user who receives the alert if the designated operator cannot be reached.</span></span> <span data-ttu-id="1a6db-104">In diesem Thema wird beschrieben, wie Sie einen Ausfall Sicherheits Operator zum Empfang [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] von-Agent-Warn Benachrichtigungen in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von festlegen [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1a6db-104">This topic describes how to set a fail-safe operator to receive [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert notifications in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="1a6db-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="1a6db-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1a6db-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="1a6db-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1a6db-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1a6db-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="1a6db-108">Security</span><span class="sxs-lookup"><span data-stu-id="1a6db-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1a6db-109">**So bestimmen Sie einen Ausfallsicherheitsoperator mit**</span><span class="sxs-lookup"><span data-stu-id="1a6db-109">**To designate a fail-safe operator, using:**</span></span>  
  
     [<span data-ttu-id="1a6db-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1a6db-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1a6db-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="1a6db-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1a6db-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1a6db-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="1a6db-113">Die Pager- und **net send** -Optionen werden in zukünftigen Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht mehr im [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a6db-113">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1a6db-114">Nutzen Sie diese Funktionen bei Neuentwicklungen nicht mehr, und planen Sie die Änderung von Anwendungen, die diese Funktionen zurzeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="1a6db-114">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="1a6db-115">Beachten Sie, dass E-Mail- und Pagerbenachrichtigungen an Operatoren nur versendet werden können, wenn der SQL Server-Agent für die Verwendung von Datenbank-E-Mail konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="1a6db-115">Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators.</span></span> <span data-ttu-id="1a6db-116">Weitere Informationen finden Sie unter [Zuweisen von Warnungen zu einem Operator](assign-alerts-to-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="1a6db-116">For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="1a6db-117">können Aufträge problemlos mithilfe einer grafischen Oberfläche verwaltet werden. Dies ist die empfohlene Vorgehensweise für die Erstellung und Verwaltung der Auftragsinfrastruktur.</span><span class="sxs-lookup"><span data-stu-id="1a6db-117">provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1a6db-118">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="1a6db-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1a6db-119">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1a6db-119">Permissions</span></span>  
 <span data-ttu-id="1a6db-120">Nur Mitglieder der festen Serverrolle **sysadmin** können Ausfallsicherheitsoperatoren bestimmen.</span><span class="sxs-lookup"><span data-stu-id="1a6db-120">Only members of the **sysadmin** fixed server role can designate fail-safe operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1a6db-121">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1a6db-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-designate-a-fail-safe-operator"></a><span data-ttu-id="1a6db-122">So bestimmen Sie einen Ausfallsicherheitsoperator</span><span class="sxs-lookup"><span data-stu-id="1a6db-122">To designate a fail-safe operator</span></span>  
  
1.  <span data-ttu-id="1a6db-123">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, der den SQL Server-Agent-Operator enthält, den Sie als ausfallsicher bestimmen möchten.</span><span class="sxs-lookup"><span data-stu-id="1a6db-123">In **Object Explorer,** click the plus sign to expand the server that contains the SQL Server Agent operator that you want to designate as a fail-safe.</span></span>  
  
2.  <span data-ttu-id="1a6db-124">Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent** , und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="1a6db-124">Right-click **SQL Server Agent** and select **Properties**.</span></span>  

3.  <span data-ttu-id="1a6db-125">Wählen Sie im Dialogfeld **SQL Server-Agent Eigenschaften**_server_name_ unter **Seite auswählen**die Option Warnungs **System**aus.</span><span class="sxs-lookup"><span data-stu-id="1a6db-125">In the **SQL Server Agent Properties -**_server_name_ dialog box, under **Select a page**, select **Alert System**.</span></span>  
 
4.  <span data-ttu-id="1a6db-126">Aktivieren Sie unter **Ausfallsicherheitsoperator**die Option **Ausfallsicherheitsoperator aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="1a6db-126">Under **Fail-safe operator**, select **Enable fail-safe operator**.</span></span>  
  
5.  <span data-ttu-id="1a6db-127">Wählen Sie in der Liste **Operator** den Operator aus, den Sie als ausfallsicher bestimmen möchten.</span><span class="sxs-lookup"><span data-stu-id="1a6db-127">In the **Operator** list, select the operator that you want to make a fail-safe.</span></span>  
  
6.  <span data-ttu-id="1a6db-128">Aktivieren Sie entweder eines oder alle der folgenden Kontrollkästchen – **E-Mail**, **Pager**oder **NET SEND**–, um zu bestimmen, wie der Operator benachrichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="1a6db-128">Select either any or all of the following check boxes to specify how the operator will be notified: **E-mail**, **Pager**, or **Net send**.</span></span>  
  
7.  <span data-ttu-id="1a6db-129">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a6db-129">When finished, click **OK**.</span></span>  
  
  
