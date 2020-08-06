---
title: Festlegen eines Ereignis Weiterleitungs Servers (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- event forwarding servers [SQL Server]
- events [SQL Server], forwarding
- alerts [SQL Server], forwarded events
ms.assetid: 81dfcbe4-3000-4e77-99de-bf85fef63a12
author: stevestein
ms.author: sstein
ms.openlocfilehash: bc5f01507bf893d1bffc682f65a01b9ff48ffa9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722198"
---
# <a name="designate-an-events-forwarding-server-sql-server-management-studio"></a><span data-ttu-id="37541-102">Designate an Events Forwarding Server (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="37541-102">Designate an Events Forwarding Server (SQL Server Management Studio)</span></span>
  <span data-ttu-id="37541-103">In diesem Thema wird beschrieben, wie Sie einen Server festlegen, auf dem [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Ereignisse in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von weitergeleitet werden [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="37541-103">This topic describes how to designate a server to which [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] forwards events in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span></span> <span data-ttu-id="37541-104">Ereignisweiterleitung gilt für Ereignisse, die zwischen Servern weitergeleitet werden, und nicht für Ereignisse, die zwischen Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] weitergeleitet werden, die auf einem einzelnen Computer gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="37541-104">Note that event forwarding applies to events forwarded between servers, not to events forwarded between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] hosted on a single computer.</span></span> <span data-ttu-id="37541-105">Beachten Sie außerdem, dass zum Empfangen weitergeleiteter Ereignisse der Warnungsverwaltungsserver eine Standardinstanz von SQL Server sein muss.</span><span class="sxs-lookup"><span data-stu-id="37541-105">Also note that in order to receive forwarded events, the alerts management server must be a default instance of SQL Server.</span></span>  
  
 <span data-ttu-id="37541-106">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="37541-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="37541-107">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="37541-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="37541-108">Security</span><span class="sxs-lookup"><span data-stu-id="37541-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="37541-109">**So bestimmen Sie einen Ereignisweiterleitungsserver mit**</span><span class="sxs-lookup"><span data-stu-id="37541-109">**To designate an events forwarding server, using:**</span></span>  
  
     [<span data-ttu-id="37541-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="37541-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="37541-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="37541-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="37541-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="37541-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="37541-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="37541-113">Permissions</span></span>  
 <span data-ttu-id="37541-114">Erfordert die Mitgliedschaft in der festen Serverrolle **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="37541-114">Requires membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="37541-115">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="37541-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-designate-an-events-forwarding-server"></a><span data-ttu-id="37541-116">So bestimmen Sie einen Ereignisweiterleitungsserver</span><span class="sxs-lookup"><span data-stu-id="37541-116">To designate an events forwarding server</span></span>  
  
1.  <span data-ttu-id="37541-117">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Server zu erweitern, von dem aus Sie Ereignisse an andere Server weiterleiten möchten.</span><span class="sxs-lookup"><span data-stu-id="37541-117">In **Object Explorer,** click the plus sign to expand the server from which you want to forward events to another server.</span></span>  
  
2.  <span data-ttu-id="37541-118">Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent** , und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="37541-118">Right-click **SQL Server Agent** and select **Properties**.</span></span>  

3.  <span data-ttu-id="37541-119">Klicken Sie im Dialogfeld **Eigenschaften des SQL Server-Agents >**_Servername_ unter **Seite auswählen** auf **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="37541-119">In the **SQL Server Agent Properties -**_server_name_ dialog box, under **Select a page**, select **Advanced**.</span></span>  

4.  <span data-ttu-id="37541-120">Aktivieren Sie unter **SQL Server-Ereignisweiterleitung**das Kontrollkästchen **Ereignisse an anderen Server weiterleiten** .</span><span class="sxs-lookup"><span data-stu-id="37541-120">Under **SQL Server event forwarding**, select the **Forward events to a different server** check box.</span></span>  
  
5.  <span data-ttu-id="37541-121">Klicken Sie in der Liste **Server** auf einen Server, und wählen Sie dann unter **Ereignisse**eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="37541-121">In the **Server** list, select a server, and then, under **Events**, select one of the following:</span></span>  
  
    -   <span data-ttu-id="37541-122">Klicken Sie auf **Ereignisse ohne Behandlung** , um nur Ereignisse weiterzuleiten, die noch nicht von lokalen Warnungen verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="37541-122">Select **Unhandled events** to forward only the events that have not been handled by local alerts.</span></span>  
  
    -   <span data-ttu-id="37541-123">Klicken Sie auf **Alle Ereignisse** , um alle Ereignisse unabhängig davon weiterzuleiten, ob sie von lokalen Warnungen verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="37541-123">Select **All events** to forward all events regardless of whether they have been handled by local alerts.</span></span>  
  
6.  <span data-ttu-id="37541-124">Klicken Sie in der Liste **Bei diesem Schweregrad des Ereignisses oder darüber** auf den Schweregrad, bei dem Ereignisse an den ausgewählten Server weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="37541-124">In the **If event has severity at or above** list, click the severity level at which events are forwarded to the selected server.</span></span>  
  
7.  <span data-ttu-id="37541-125">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="37541-125">When finished, click **OK**.</span></span>  
  
  
