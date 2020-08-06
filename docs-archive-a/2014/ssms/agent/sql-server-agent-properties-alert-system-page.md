---
title: SQL Server-Agent-Eigenschaften (Seite Warnungssystem)|Microsoft-Dokumente
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.alert.f1
ms.assetid: 3e6d3bfd-20ee-4593-86cc-f65b1c08c69d
author: stevestein
ms.author: sstein
ms.openlocfilehash: ff203be21efbd99b90f02261cfe94dd49bd0d849
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621310"
---
# <a name="sql-server-agent-properties-alert-system-page"></a><span data-ttu-id="5f77c-102">SQL Server-Agent-Eigenschaften (Seite Warnungssystem)</span><span class="sxs-lookup"><span data-stu-id="5f77c-102">SQL Server Agent Properties (Alert System Page)</span></span>
  <span data-ttu-id="5f77c-103">Auf dieser Seite können Sie die Einstellungen für die vom [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent versendeten Warnmeldungen abrufen und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="5f77c-103">Use this page to view and modify the settings for messages sent by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5f77c-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="5f77c-104">Options</span></span>  
 <span data-ttu-id="5f77c-105">**Mailsitzung**</span><span class="sxs-lookup"><span data-stu-id="5f77c-105">**Mail session**</span></span>  
 <span data-ttu-id="5f77c-106">Mithilfe der Optionen in diesem Abschnitt wird [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Mail konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="5f77c-106">The options in this section configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Mail.</span></span>  
  
 <span data-ttu-id="5f77c-107">**Mailprofil aktivieren**</span><span class="sxs-lookup"><span data-stu-id="5f77c-107">**Enable mail profile**</span></span>  
 <span data-ttu-id="5f77c-108">Aktiviert [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Mail.</span><span class="sxs-lookup"><span data-stu-id="5f77c-108">Enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Mail.</span></span> <span data-ttu-id="5f77c-109">Standardmäßig ist [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Mail nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="5f77c-109">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Mail is not enabled.</span></span>  
  
 <span data-ttu-id="5f77c-110">**Mailsystem**</span><span class="sxs-lookup"><span data-stu-id="5f77c-110">**Mail System**</span></span>  
 <span data-ttu-id="5f77c-111">Legt das von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent zu verwendende Mailsystem fest.</span><span class="sxs-lookup"><span data-stu-id="5f77c-111">Sets the mail system for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to use.</span></span> <span data-ttu-id="5f77c-112">Datenbank-E-Mail</span><span class="sxs-lookup"><span data-stu-id="5f77c-112">Database Mail</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5f77c-113">Nach der Änderung des E-Mail-Systems müssen Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst neu starten, damit die Änderung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="5f77c-113">After changing the e-mail system, you must restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service for the change to take effect.</span></span>  
  
 <span data-ttu-id="5f77c-114">**Mailprofil**</span><span class="sxs-lookup"><span data-stu-id="5f77c-114">**Mail Profile**</span></span>  
 <span data-ttu-id="5f77c-115">Legt das von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent zu verwendende Profil fest.</span><span class="sxs-lookup"><span data-stu-id="5f77c-115">Sets the profile for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to use.</span></span> <span data-ttu-id="5f77c-116">Sie können auch ein **\<new Database Mail profile...>** auswählen, um ein neues Profil zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5f77c-116">You may also select **\<new Database Mail profile...>** to create a new profile.</span></span>  
  
 <span data-ttu-id="5f77c-117">**Pager-E-Mails**</span><span class="sxs-lookup"><span data-stu-id="5f77c-117">**Pager e-mails**</span></span>  
 <span data-ttu-id="5f77c-118">Mithilfe der Optionen in diesem Abschnitt können Sie die an Pageradressen zu versendenden E-Mail-Nachrichten so konfigurieren, dass eine Kommunikation mit Ihrem Pagingsystem möglich ist.</span><span class="sxs-lookup"><span data-stu-id="5f77c-118">The options in this section allow you to configure e-mail messages sent to pager addresses to work with your paging system.</span></span>  
  
 <span data-ttu-id="5f77c-119">**Adressformatierung für Pager-E-Mails**</span><span class="sxs-lookup"><span data-stu-id="5f77c-119">**Address formatting for pager e-mails**</span></span>  
 <span data-ttu-id="5f77c-120">In diesem Abschnitt können Sie das in Pager-E-Mails verwendete Format für Adressen und Betreffzeile angeben.</span><span class="sxs-lookup"><span data-stu-id="5f77c-120">This section allows you to specify the format of the addresses and the subject line included in pager e-mails.</span></span>  
  
 <span data-ttu-id="5f77c-121">**An-Zeile**</span><span class="sxs-lookup"><span data-stu-id="5f77c-121">**To line**</span></span>  
 <span data-ttu-id="5f77c-122">Bestimmt die Optionen für die Zeile **An** der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="5f77c-122">Specifies the options for the **To** line of the message</span></span>  
  
 <span data-ttu-id="5f77c-123">**Präfix**</span><span class="sxs-lookup"><span data-stu-id="5f77c-123">**Prefix**</span></span>  
 <span data-ttu-id="5f77c-124">Geben Sie einen beliebigen festgelegten Text ein, den das System bei Nachrichten, die an Pager gesendet werden, am Anfang der Zeile **An** verlangt.</span><span class="sxs-lookup"><span data-stu-id="5f77c-124">Type any fixed text that your system requires at the beginning of the **To** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="5f77c-125">**Pager**</span><span class="sxs-lookup"><span data-stu-id="5f77c-125">**Pager**</span></span>  
 <span data-ttu-id="5f77c-126">Enthält die E-Mail-Adresse der Nachricht zwischen Präfix und Suffix.</span><span class="sxs-lookup"><span data-stu-id="5f77c-126">Includes the e-mail address for the message between the prefix and the suffix.</span></span>  
  
 <span data-ttu-id="5f77c-127">**Suffix**</span><span class="sxs-lookup"><span data-stu-id="5f77c-127">**Suffix**</span></span>  
 <span data-ttu-id="5f77c-128">Geben Sie einen beliebigen festgelegten Text ein, den das Pagingsystem bei Nachrichten, die an Pager gesendet werden, am Ende der Zeile **An** verlangt.</span><span class="sxs-lookup"><span data-stu-id="5f77c-128">Type any fixed text that your paging system requires at the end of the **To** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="5f77c-129">**Cc-Zeile**</span><span class="sxs-lookup"><span data-stu-id="5f77c-129">**Cc line**</span></span>  
 <span data-ttu-id="5f77c-130">Bestimmt Optionen für die Zeile **Cc** der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="5f77c-130">Specifies options for the **Cc** line of the message.</span></span>  
  
 <span data-ttu-id="5f77c-131">**Präfix**</span><span class="sxs-lookup"><span data-stu-id="5f77c-131">**Prefix**</span></span>  
 <span data-ttu-id="5f77c-132">Geben Sie einen beliebigen festgelegten Text ein, den das System bei Nachrichten, die an Pager gesendet werden, am Anfang der Zeile **Cc** verlangt.</span><span class="sxs-lookup"><span data-stu-id="5f77c-132">Type any fixed text that your system requires at the beginning of the **Cc** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="5f77c-133">**Pager**</span><span class="sxs-lookup"><span data-stu-id="5f77c-133">**Pager**</span></span>  
 <span data-ttu-id="5f77c-134">Enthält die E-Mail-Adresse der Nachricht zwischen Präfix und Suffix.</span><span class="sxs-lookup"><span data-stu-id="5f77c-134">Includes the e-mail address for the message between the prefix and the suffix.</span></span>  
  
 <span data-ttu-id="5f77c-135">**Suffix**</span><span class="sxs-lookup"><span data-stu-id="5f77c-135">**Suffix**</span></span>  
 <span data-ttu-id="5f77c-136">Geben Sie einen beliebigen festgelegten Text ein, den das Pagingsystem bei Nachrichten, die an Pager gesendet werden, am Ende der Zeile **Cc** verlangt.</span><span class="sxs-lookup"><span data-stu-id="5f77c-136">Type any fixed text that your paging system requires at the end of the **Cc** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="5f77c-137">**Subject**</span><span class="sxs-lookup"><span data-stu-id="5f77c-137">**Subject**</span></span>  
 <span data-ttu-id="5f77c-138">Bestimmt die Optionen für den Betreff der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="5f77c-138">Specifies the options for the subject of the message.</span></span>  
  
 <span data-ttu-id="5f77c-139">**Präfix**</span><span class="sxs-lookup"><span data-stu-id="5f77c-139">**Prefix**</span></span>  
 <span data-ttu-id="5f77c-140">Geben Sie einen beliebigen festgelegten Text ein, den das Pagingsystem bei Nachrichten, die an Pager gesendet werden, am Anfang der Zeile **Betreff** verlangt.</span><span class="sxs-lookup"><span data-stu-id="5f77c-140">Type any fixed text that your paging system requires at the beginning of the **Subject** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="5f77c-141">**Suffix**</span><span class="sxs-lookup"><span data-stu-id="5f77c-141">**Suffix**</span></span>  
 <span data-ttu-id="5f77c-142">Geben Sie einen beliebigen festgelegten Text ein, den das Pagingsystem bei Nachrichten, die an Pager gesendet werden, am Ende der Zeile **Betreff** verlangt.</span><span class="sxs-lookup"><span data-stu-id="5f77c-142">Type any fixed text that your paging system requires at the end of the **Subject** line of messages sent to a pager.</span></span>  
  
 <span data-ttu-id="5f77c-143">**E-Mail-Textkörper in Benachrichtigungsmeldung einschließen**</span><span class="sxs-lookup"><span data-stu-id="5f77c-143">**Include body of e-mail in notification message**</span></span>  
 <span data-ttu-id="5f77c-144">Schließt den Textkörper der E-Mail-Nachricht in die an den Pager versendete Nachricht ein.</span><span class="sxs-lookup"><span data-stu-id="5f77c-144">Includes the body of the e-mail message in the message sent to the pager.</span></span>  
  
 <span data-ttu-id="5f77c-145">**Ausfallsicherheitsoperator**</span><span class="sxs-lookup"><span data-stu-id="5f77c-145">**Fail-safe operator**</span></span>  
 <span data-ttu-id="5f77c-146">In diesem Abschnitt können Sie die Optionen für den Ausfallsicherheitsoperator angeben.</span><span class="sxs-lookup"><span data-stu-id="5f77c-146">This section allows you to specify the options for the fail-safe operator.</span></span>  
  
 <span data-ttu-id="5f77c-147">**Ausfallsicherheitsoperator aktivieren**</span><span class="sxs-lookup"><span data-stu-id="5f77c-147">**Enable fail-safe operator**</span></span>  
 <span data-ttu-id="5f77c-148">Legt einen Ausfallsicherheitsoperator fest.</span><span class="sxs-lookup"><span data-stu-id="5f77c-148">Specifies a fail safe operator.</span></span>  
  
 <span data-ttu-id="5f77c-149">**Operator**</span><span class="sxs-lookup"><span data-stu-id="5f77c-149">**Operator**</span></span>  
 <span data-ttu-id="5f77c-150">Legt den Namen des Operators fest, der die Ausfallsicherheitsbenachrichtigungen empfängt.</span><span class="sxs-lookup"><span data-stu-id="5f77c-150">Sets the name of the operator to receive fail-safe notifications.</span></span>  
  
 <span data-ttu-id="5f77c-151">**Benachrichtigen durch**</span><span class="sxs-lookup"><span data-stu-id="5f77c-151">**Notify using**</span></span>  
 <span data-ttu-id="5f77c-152">Legt die Methode zur Benachrichtigung des Ausfallsicherheitsoperators fest.</span><span class="sxs-lookup"><span data-stu-id="5f77c-152">Sets the method to use for notifying the fail-safe operator.</span></span>  
  
 <span data-ttu-id="5f77c-153">**Tokenersetzung**</span><span class="sxs-lookup"><span data-stu-id="5f77c-153">**Token Replacement**</span></span>  
 <span data-ttu-id="5f77c-154">In diesem Abschnitt können Sie Tokens für Auftragsschritte aktivieren, die in von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Warnungen ausgeführten Aufträgen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="5f77c-154">This section allows you to enable job step tokens that can be used in jobs run by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span> <span data-ttu-id="5f77c-155">Weitere Informationen zu Auftragsschritttokens finden Sie unter [Verwenden von Token in Auftragsschritten](use-tokens-in-job-steps.md).</span><span class="sxs-lookup"><span data-stu-id="5f77c-155">For more information about job step tokens, see [Use Tokens in Job Steps](use-tokens-in-job-steps.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5f77c-156">Jeder Windows-Benutzer mit Schreibberechtigungen für das Windows-Ereignisprotokoll hat u. U. die Möglichkeit, auf Auftragsschritte zuzugreifen, die von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Warnungen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="5f77c-156">Any Windows user with write permissions on the Windows Event Log may be able to access job steps that are activated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span> <span data-ttu-id="5f77c-157">Zur Vermeidung dieses Sicherheitsrisikos sind [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Tokens, die in von Warnungen aktivierten Aufträgen verwendet werden können, standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="5f77c-157">To avoid this security risk, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent tokens that can be used in jobs activated by alerts are disabled by default.</span></span> <span data-ttu-id="5f77c-158">Hierbei handelt es sich um folgende Token: **$(A-DBN)** , **$(A-SVR)** , **$(A-ERR)** , **$(A-SEV)** und **$(A-MSG)** .</span><span class="sxs-lookup"><span data-stu-id="5f77c-158">These tokens are: **$(A-DBN)**, **$(A-SVR)**, **$(A-ERR)**, **$(A-SEV)**, and **$(A-MSG)**.</span></span>  
>   
>  <span data-ttu-id="5f77c-159">Wenn Sie diese Tokens verwenden müssen, können Sie sie aktivieren. Stellen Sie zuvor jedoch sicher, dass nur Mitglieder von vertrauenswürdigen Windows-Sicherheitsgruppen, wie z. B. die Gruppe Administratoren, über Schreibberechtigungen für das Ereignisprotokoll des Computers verfügen, auf dem sich [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] befindet.</span><span class="sxs-lookup"><span data-stu-id="5f77c-159">If you need to use these tokens, ensure that only members of trusted Windows security groups, such as the Administrators group, have write permissions on the Event Log of the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resides before enabling them.</span></span>  
  
 <span data-ttu-id="5f77c-160">**Token für alle Auftragsantworten auf Warnungen ersetzen**</span><span class="sxs-lookup"><span data-stu-id="5f77c-160">**Replace tokens for all job responses to alerts**</span></span>  
 <span data-ttu-id="5f77c-161">Aktivieren Sie dieses Kontrollkästchen, um die Tokenersetzung für Aufträge zu aktivieren, die von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Warnungen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="5f77c-161">Select this check box to enable token replacement for jobs that are activated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alerts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f77c-162">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5f77c-162">See Also</span></span>  
 <span data-ttu-id="5f77c-163">[Veranstalter](operators.md) </span><span class="sxs-lookup"><span data-stu-id="5f77c-163">[Operators](operators.md) </span></span>  
 <span data-ttu-id="5f77c-164">[SQL Server-Agent zu verwendende e-Mail konfigurieren Datenbank-E-Mail](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md) </span><span class="sxs-lookup"><span data-stu-id="5f77c-164">[Configure SQL Server Agent Mail to Use Database Mail](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md) </span></span>  
 [<span data-ttu-id="5f77c-165">Datenbank-E-Mail</span><span class="sxs-lookup"><span data-stu-id="5f77c-165">Database Mail</span></span>](../../relational-databases/database-mail/database-mail.md)  
  
  
