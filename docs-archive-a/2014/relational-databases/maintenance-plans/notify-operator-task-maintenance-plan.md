---
title: Task 'Operator benachrichtigen' (Wartungsplan) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.notifyoperator.f1
helpviewer_keywords:
- Notify Operator Task dialog box
ms.assetid: 39c0797c-ad2b-4591-85c9-a23a7f902895
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4feb59622c2a42de67193c75d545a6b8a2a08863
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619115"
---
# <a name="notify-operator-task-maintenance-plan"></a><span data-ttu-id="75130-102">Task 'Operator benachrichtigen' (Wartungsplan)</span><span class="sxs-lookup"><span data-stu-id="75130-102">Notify Operator Task (Maintenance Plan)</span></span>
  <span data-ttu-id="75130-103">Mithilfe des Dialogfelds **Task 'Operator benachrichtigen'** können Sie dem Wartungsplan eine automatische Benachrichtigung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="75130-103">Use the **Notify Operators Task** dialog to add an automatic notification to this maintenance plan.</span></span> <span data-ttu-id="75130-104">Um diesen Task zu verwenden, müssen Datenbank-E-Mails aktiviert und ordnungsgemäß mit msdb als Mailhostdatenbank konfiguriert sein. Außerdem muss der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agentoperator über eine gültige E-Mail-Adresse verfügen.</span><span class="sxs-lookup"><span data-stu-id="75130-104">To use this task you must have Database Mail enabled and properly configured with MSDB as a Mail Host Database, and have a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent operator with a valid e-mail address.</span></span>  
  
 <span data-ttu-id="75130-105">Dieser Task verwendet die gespeicherte Prozedur sp_notify_operator.</span><span class="sxs-lookup"><span data-stu-id="75130-105">This task uses the sp_notify_operator stored procedure.</span></span>  
  
## <a name="options"></a><span data-ttu-id="75130-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="75130-106">Options</span></span>  
 <span data-ttu-id="75130-107">**Connection**</span><span class="sxs-lookup"><span data-stu-id="75130-107">**Connection**</span></span>  
 <span data-ttu-id="75130-108">Wählen Sie die Serververbindung aus, die bei der Ausführung dieses Tasks verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="75130-108">Select the server connection to use when performing this task.</span></span>  
  
 <span data-ttu-id="75130-109">**Neu**</span><span class="sxs-lookup"><span data-stu-id="75130-109">**New**</span></span>  
 <span data-ttu-id="75130-110">Erstellen Sie eine neue Serververbindung, die bei der Ausführung dieses Tasks verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="75130-110">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="75130-111">Das Dialogfeld **Neue Verbindung** wird im Folgenden beschrieben.</span><span class="sxs-lookup"><span data-stu-id="75130-111">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="75130-112">**Zu benachrichtigende Operatoren**</span><span class="sxs-lookup"><span data-stu-id="75130-112">**Operators to notify**</span></span>  
 <span data-ttu-id="75130-113">Gibt den Empfänger der E-Mail an.</span><span class="sxs-lookup"><span data-stu-id="75130-113">Specify the recipient of the e-mail.</span></span>  
  
 <span data-ttu-id="75130-114">**Betreff einer Benachrichtigungsmeldung**</span><span class="sxs-lookup"><span data-stu-id="75130-114">**Notification message subject**</span></span>  
 <span data-ttu-id="75130-115">Geben Sie den Text an, der in der Betreffzeile der Benachrichtigungsmeldung enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="75130-115">Specify the text to include in the notification message subject line.</span></span>  
  
 <span data-ttu-id="75130-116">**Textkörper einer Benachrichtigungsmeldung**</span><span class="sxs-lookup"><span data-stu-id="75130-116">**Notification message body**</span></span>  
 <span data-ttu-id="75130-117">Geben Sie den Text an, der in dem Textkörper der Benachrichtigungsmeldung enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="75130-117">Specify the text to include in the notification message body.</span></span>  
  
 <span data-ttu-id="75130-118">**T-SQL anzeigen**</span><span class="sxs-lookup"><span data-stu-id="75130-118">**View T-SQL**</span></span>  
 <span data-ttu-id="75130-119">Zeigt die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen an, die für diesen Task auf dem Server auf Basis der ausgewählten Optionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="75130-119">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="75130-120">Wenn die Anzahl der betroffenen Objekte groß ist, kann die Anzeige erhebliche Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="75130-120">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="75130-121">Neue Verbindung (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="75130-121">New Connection Dialog Box</span></span>  
 <span data-ttu-id="75130-122">**Verbindungsname**</span><span class="sxs-lookup"><span data-stu-id="75130-122">**Connection name**</span></span>  
 <span data-ttu-id="75130-123">Geben Sie einen Namen für die neue Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="75130-123">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="75130-124">**Wählen Sie einen Servernamen aus, oder geben Sie ihn ein.**</span><span class="sxs-lookup"><span data-stu-id="75130-124">**Select or enter a server name**</span></span>  
 <span data-ttu-id="75130-125">Wählen Sie den Server aus, zu dem bei der Ausführung dieses Tasks eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="75130-125">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="75130-126">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="75130-126">**Refresh**</span></span>  
 <span data-ttu-id="75130-127">Mithilfe dieser Option aktualisieren Sie die Liste der verfügbaren Server.</span><span class="sxs-lookup"><span data-stu-id="75130-127">Refresh the list of available servers.</span></span>  
  
 <span data-ttu-id="75130-128">**Geben Sie Informationen zum Anmelden am Server ein**</span><span class="sxs-lookup"><span data-stu-id="75130-128">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="75130-129">Legt fest, wie die Authentifizierung gegenüber dem Server stattfindet.</span><span class="sxs-lookup"><span data-stu-id="75130-129">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="75130-130">**Integrierte Sicherheit von Windows NT verwenden**</span><span class="sxs-lookup"><span data-stu-id="75130-130">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="75130-131">Stellt mithilfe der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Windows-Authentifizierung eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] [!INCLUDE[msCoName](../../includes/msconame-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="75130-131">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="75130-132">**Bestimmten Benutzernamen und bestimmtes Kennwort verwenden**</span><span class="sxs-lookup"><span data-stu-id="75130-132">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="75130-133">Stellt mithilfe der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Authentifizierung eine Verbindung zu einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="75130-133">Connect to an instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="75130-134">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="75130-134">This option is not available.</span></span>  
  
 <span data-ttu-id="75130-135">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="75130-135">**User name**</span></span>  
 <span data-ttu-id="75130-136">Stellt eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung für den Gebrauch bei der Authentifizierung bereit.</span><span class="sxs-lookup"><span data-stu-id="75130-136">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="75130-137">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="75130-137">This option is not available.</span></span>  
  
 <span data-ttu-id="75130-138">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="75130-138">**Password**</span></span>  
 <span data-ttu-id="75130-139">Stellt ein Kennwort für den Gebrauch bei der Authentifizierung bereit.</span><span class="sxs-lookup"><span data-stu-id="75130-139">Provide a password to use when authenticating.</span></span> <span data-ttu-id="75130-140">Diese Option ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="75130-140">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75130-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="75130-141">See Also</span></span>  
 <span data-ttu-id="75130-142">[Datenbank-E-Mail](../database-mail/database-mail.md) </span><span class="sxs-lookup"><span data-stu-id="75130-142">[Database Mail](../database-mail/database-mail.md) </span></span>  
 [<span data-ttu-id="75130-143">sp_notify_operator &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="75130-143">sp_notify_operator &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-notify-operator-transact-sql)  
  
  
