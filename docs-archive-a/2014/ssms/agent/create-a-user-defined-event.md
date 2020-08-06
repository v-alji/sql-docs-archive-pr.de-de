---
title: Erstellen eines benutzerdefinierten Ereignisses | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent alerts, user-defined events
- user-defined events [SQL Server]
- multiple language support [SQL Server], alerts
- languages [SQL Server], alerts
- severity levels [SQL Server]
- global considerations [SQL Server], alerts
- events [SQL Server], user-defined
- SQL Server Agent alerts, multiple-language environments
- alerts [SQL Server], user-defined events
- alerts [SQL Server], multiple-language environments
- custom events [SQL Server Agent]
- international considerations [SQL Server], alerts
ms.assetid: 03d71a35-97fa-4bba-aa9a-23ac9c9cf879
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2323dc4da3d1a8a67dad41ea189877ade25eff0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726425"
---
# <a name="create-a-user-defined-event"></a><span data-ttu-id="7b0ea-102">Erstellen eines benutzerdefinierten Ereignisses</span><span class="sxs-lookup"><span data-stu-id="7b0ea-102">Create a User-Defined Event</span></span>
  <span data-ttu-id="7b0ea-103">Sie können benutzerdefinierte Ereignisse erstellen, wenn Sie zusätzlich zu den von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vordefinierten Ereignissen weitere Ereignisse überwachen möchten.</span><span class="sxs-lookup"><span data-stu-id="7b0ea-103">You can create user-defined events if you want to monitor events other than events that are predefined by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7b0ea-104">Sie können allen benutzerdefinierten Ereignissen auch einen Schweregrad zuweisen.</span><span class="sxs-lookup"><span data-stu-id="7b0ea-104">You can also assign a severity level to each user-defined event.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7b0ea-105">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]sollten Sie für die Meldungen aller benutzerdefinierten Ereignisse die Option **In Windows-Anwendungsereignisprotokoll schreiben** auswählen, um sicherzustellen, dass die Meldungen protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="7b0ea-105">When using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the **Write to Windows application event log** option for each user-defined event message, to ensure that the messages are logged.</span></span> <span data-ttu-id="7b0ea-106">Benutzerdefinierte Meldungen mit einem Schweregrad kleiner als 19 werden standardmäßig nicht im [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Anwendungsereignisprotokoll protokolliert.</span><span class="sxs-lookup"><span data-stu-id="7b0ea-106">By default, user-defined messages of severity lower than 19 are not sent to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application log when they occur.</span></span> <span data-ttu-id="7b0ea-107">Benutzerdefinierte Meldungen mit einem Schweregrad kleiner als 19 lösen daher keine Warnungen des SQL Server-Agents aus.</span><span class="sxs-lookup"><span data-stu-id="7b0ea-107">User-defined messages of severity lower than 19 therefore do not trigger SQL Server Agent alerts.</span></span>  
  
 <span data-ttu-id="7b0ea-108">Benutzerdefinierte Ereignisse müssen eine eindeutige Meldungsnummer besitzen.</span><span class="sxs-lookup"><span data-stu-id="7b0ea-108">User-defined events must have a unique message number.</span></span> <span data-ttu-id="7b0ea-109">Die Meldungsnummern für ein benutzerdefiniertes Ereignis müssen größer als 50.000 sein.</span><span class="sxs-lookup"><span data-stu-id="7b0ea-109">Message numbers for a user-defined event must be greater than 50,000.</span></span> <span data-ttu-id="7b0ea-110">Meldungen für das Ereignis können in mehreren Sprachen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="7b0ea-110">You can define messages for the event in multiple languages.</span></span> <span data-ttu-id="7b0ea-111">Allerdings muss vor dem Hinzufügen von Meldungen in anderen Sprachen eine Fehlermeldung in **En-US** vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="7b0ea-111">However, an **En-US** error message must exist before messages in other languages can be added.</span></span>  
  
 <span data-ttu-id="7b0ea-112">Wenn Sie eine mehrsprachige [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Umgebung verwalten, sollten Sie in allen unterstützten Sprachen benutzerdefinierte Meldungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="7b0ea-112">If you administer a multiple-language [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] environment, create user-defined messages in each of the languages that are supported.</span></span> <span data-ttu-id="7b0ea-113">Wenn Sie beispielsweise eine neue Ereignismeldung erstellen, die sowohl auf einem deutschen als auch auf einem englischen Server verwendet werden soll, können Sie für beide dieselbe Meldungsnummer und denselben Schweregrad verwenden, müssen ihnen jedoch unterschiedliche Sprachen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="7b0ea-113">For example, if you are creating a new event message to be used on both an English and a German server, use the same message number and severity for both, but assign a different language to each.</span></span>  
  
 <span data-ttu-id="7b0ea-114">In den folgenden Aufgaben werden Informationen bereitgestellt, wie Sie benutzerdefinierte Ereignisse und die dazugehörigen Warnungen erstellen:</span><span class="sxs-lookup"><span data-stu-id="7b0ea-114">The following tasks provide information about how to create user-defined events and alerts that respond to them:</span></span>  
  
 <span data-ttu-id="7b0ea-115">**So erstellen Sie eine Warnung auf der Grundlage einer Meldungsnummer**</span><span class="sxs-lookup"><span data-stu-id="7b0ea-115">**To create an alert based on a message number**</span></span>  
  
-   [<span data-ttu-id="7b0ea-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7b0ea-116">SQL Server Management Studio</span></span>](create-an-alert-using-an-error-number.md)  
  
-   [<span data-ttu-id="7b0ea-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7b0ea-117">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql)  
  
 <span data-ttu-id="7b0ea-118">**So erstellen Sie eine Warnung auf der Grundlage von Schweregraden**</span><span class="sxs-lookup"><span data-stu-id="7b0ea-118">**To create an alert based on severity levels**</span></span>  
  
-   [<span data-ttu-id="7b0ea-119">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7b0ea-119">SQL Server Management Studio</span></span>](create-an-alert-using-severity-level.md)  
  
-   [<span data-ttu-id="7b0ea-120">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7b0ea-120">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql)  
  
 <span data-ttu-id="7b0ea-121">**So definieren Sie die Antwort auf eine Warnung**</span><span class="sxs-lookup"><span data-stu-id="7b0ea-121">**To define the response to an alert**</span></span>  
  
-   [<span data-ttu-id="7b0ea-122">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7b0ea-122">SQL Server Management Studio</span></span>](../sql-server-management-studio-ssms.md)  
  
-   [<span data-ttu-id="7b0ea-123">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7b0ea-123">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql)  
  
 <span data-ttu-id="7b0ea-124">**So erstellen Sie eine benutzerdefinierte Ereignisfehlermeldung**</span><span class="sxs-lookup"><span data-stu-id="7b0ea-124">**To create a user-defined event error message**</span></span>  
  
-   [<span data-ttu-id="7b0ea-125">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7b0ea-125">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-addmessage-transact-sql)  
  
 <span data-ttu-id="7b0ea-126">**So ändern Sie eine benutzerdefinierte Ereignisfehlermeldung**</span><span class="sxs-lookup"><span data-stu-id="7b0ea-126">**To modify a user-defined event error message**</span></span>  
  
-   [<span data-ttu-id="7b0ea-127">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7b0ea-127">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-altermessage-transact-sql)  
  
 <span data-ttu-id="7b0ea-128">**So löschen Sie eine benutzerdefinierte Ereignisfehlermeldung**</span><span class="sxs-lookup"><span data-stu-id="7b0ea-128">**To delete a user-defined event error message**</span></span>  
  
-   [<span data-ttu-id="7b0ea-129">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7b0ea-129">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-dropmessage-transact-sql)  
  
 <span data-ttu-id="7b0ea-130">**So deaktivieren oder reaktivieren Sie eine Warnung**</span><span class="sxs-lookup"><span data-stu-id="7b0ea-130">**To disable or reactivate an alert**</span></span>  
  
-   [<span data-ttu-id="7b0ea-131">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7b0ea-131">SQL Server Management Studio</span></span>](disable-or-reactivate-an-alert.md)  
  
-   [<span data-ttu-id="7b0ea-132">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7b0ea-132">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="7b0ea-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7b0ea-133">See Also</span></span>  
 [<span data-ttu-id="7b0ea-134">sp_update_alert &#40;Transact-SQL-&#41;</span><span class="sxs-lookup"><span data-stu-id="7b0ea-134">sp_update_alert &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql)  
  
  
