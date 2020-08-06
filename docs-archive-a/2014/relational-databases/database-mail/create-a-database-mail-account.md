---
title: Erstellen eines Kontos für die Datenbank-E-Mail | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Mail [SQL Server], accounts
- accounts [Database Mail]
ms.assetid: c07abbc6-fc6a-470b-8fa3-532f2e06b16a
author: stevestein
ms.author: sstein
ms.openlocfilehash: ec7d1c9147998b5a19cc0e6af13220bd64e165fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616101"
---
# <a name="create-a-database-mail-account"></a><span data-ttu-id="cff15-102">Erstellen eines Kontos für Datenbank-E-Mail</span><span class="sxs-lookup"><span data-stu-id="cff15-102">Create a Database Mail Account</span></span>
  <span data-ttu-id="cff15-103">Verwenden Sie entweder den **Assistenten zum Konfigurieren von Datenbank-E-Mail** oder [!INCLUDE[tsql](../../includes/tsql-md.md)] , um ein Datenbank-E-Mail-Konto zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cff15-103">Use either the **Database Mail Configuration Wizard** or [!INCLUDE[tsql](../../includes/tsql-md.md)] to create a Database Mail account.</span></span>  
  
-   <span data-ttu-id="cff15-104">**Vorbereitungen:**  [Voraussetzungen](#Prerequisites)</span><span class="sxs-lookup"><span data-stu-id="cff15-104">**Before you begin:**  [Prerequisites](#Prerequisites)</span></span>  
  
-   <span data-ttu-id="cff15-105">**Folgendes können Sie zum Erstellen eines Datenbank-E-Mail-Kontos verwenden:**  [Assistent zum Konfigurieren von Datenbank-E-Mails](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="cff15-105">**To Create a Database Mail Account, using:**  [Database Mail Configuration Wizard](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
-   <span data-ttu-id="cff15-106">**Nachverfolgung:**  [Nächste Schritte zum Konfigurieren von Datenbank-E-Mail](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="cff15-106">**Follow Up:**  [Next Steps to Configure the Database Mail](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cff15-107">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="cff15-107">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="cff15-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="cff15-108">Prerequisites</span></span>  
  
-   <span data-ttu-id="cff15-109">Bestimmen Sie den Servernamen und die Portnummer für den SMTP-Server (Simple Mail Transfer Protocol), den Sie zum Senden von E-Mail verwenden. Falls der SMTP-Server eine Authentifizierung erfordert, bestimmen Sie den Benutzernamen und das Kennwort für den SMTP-Server.</span><span class="sxs-lookup"><span data-stu-id="cff15-109">Determine the server name and port number for the Simple Mail Transfer Protocol (SMTP) server you use to send e-mail.If the SMTP server requires authentication, determine the user name and password for the SMTP server.</span></span>  
  
-   <span data-ttu-id="cff15-110">Optional können Sie auch den Servertyp und die Portnummer für den Server angeben.</span><span class="sxs-lookup"><span data-stu-id="cff15-110">Optionally, you may also specify the type of the server and the port number for the server.</span></span> <span data-ttu-id="cff15-111">Der Servertyp ist für ausgehende E-Mails immer 'SMTP'.</span><span class="sxs-lookup"><span data-stu-id="cff15-111">The server type is always 'SMTP' for outgoing mail.</span></span> <span data-ttu-id="cff15-112">Die meisten SMTP-Server verwenden standardmäßig Port 25.</span><span class="sxs-lookup"><span data-stu-id="cff15-112">Most SMTP servers use port 25, the default.</span></span>  
  
##  <a name="using-database-mail-configuration-wizard"></a><a name="SSMSProcedure"></a> <span data-ttu-id="cff15-113">Verwenden des Assistenten zum Konfigurieren von Datenbank-E-Mail</span><span class="sxs-lookup"><span data-stu-id="cff15-113">Using Database Mail Configuration Wizard</span></span>  
 <span data-ttu-id="cff15-114">**So erstellen Sie ein Konto für Datenbank-E-Mail mithilfe eines Assistenten**</span><span class="sxs-lookup"><span data-stu-id="cff15-114">**To create a Database Mail account using a Wizard**</span></span>  
  
-   <span data-ttu-id="cff15-115">Stellen Sie im Objekt-Explorer eine Verbindung mit der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] her, auf der Datenbank-E-Mail konfiguriert werden soll, und erweitern Sie die Serverstruktur.</span><span class="sxs-lookup"><span data-stu-id="cff15-115">In Object Explorer, connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you want to configure Database Mail on, and expand the server tree.</span></span>  
  
-   <span data-ttu-id="cff15-116">Erweitern Sie den Knoten **Verwaltung** .</span><span class="sxs-lookup"><span data-stu-id="cff15-116">Expand the **Management** node</span></span>  
  
-   <span data-ttu-id="cff15-117">Doppelklicken Sie auf "Datenbank-E-Mail", um den Assistenten zum Konfigurieren von Datenbank-E-Mail zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="cff15-117">Double Click Database Mail to open the Database Mail Configuration Wizard.</span></span>  
  
-   <span data-ttu-id="cff15-118">Aktivieren Sie auf der Seite **Konfigurationsaufgabe auswählen** die Option **Konten und Profile für Datenbank-E-Mail verwalten**, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="cff15-118">On the **Select Configuration Task** page, select **Manage Database Mail accounts and profiles**, and click **Next**.</span></span>  
  
-   <span data-ttu-id="cff15-119">Wählen Sie auf der Seite **Profile und Konten verwalten** die Option **Neues Konto erstellen** , und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="cff15-119">On the **Manage Profiles and Accounts** page, select **Create a new account** and click **Next**.</span></span>  
  
-   <span data-ttu-id="cff15-120">Geben Sie auf der Seite **Neues Konto** den Kontonamen, eine Beschreibung, Informationen zum Mailserver und den Authentifizierungstyp an.</span><span class="sxs-lookup"><span data-stu-id="cff15-120">On the **New Account** page, specify the account name, description, mail server information, and authentication type.</span></span> <span data-ttu-id="cff15-121">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="cff15-121">Click **Next**</span></span>  
  
-   <span data-ttu-id="cff15-122">Überprüfen Sie auf der Seite **Assistenten abschließen** die auszuführenden Aktionen, und klicken Sie auf **Fertig stellen** , um die Erstellung des neuen Kontos abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="cff15-122">On the **Complete the Wizard** page, review the actions to be performed and click **Finish** to complete creating the new account.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cff15-123">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cff15-123">Using Transact-SQL</span></span>  
 <span data-ttu-id="cff15-124">**So erstellen Sie ein Konto für Datenbank-E-Mail mithilfe von Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="cff15-124">**To Create a Database Mail account using Transact-SQL**</span></span>  
  
 <span data-ttu-id="cff15-125">Führen Sie die gespeicherte Prozedur **msdb.dbo.sysmail_add_account_sp** aus, um das Konto zu erstellen, und geben Sie die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="cff15-125">Execute the stored procedure **msdb.dbo.sysmail_add_account_sp** to create the account and specify the following information:</span></span>  
  
-   <span data-ttu-id="cff15-126">Den Namen des zu erstellenden Kontos</span><span class="sxs-lookup"><span data-stu-id="cff15-126">The name of the account to create.</span></span>  
  
-   <span data-ttu-id="cff15-127">Eine optionale Beschreibung des Kontos</span><span class="sxs-lookup"><span data-stu-id="cff15-127">An optional description of the account.</span></span>  
  
-   <span data-ttu-id="cff15-128">Die E-Mail-Adresse, die auf ausgehenden E-Mail-Nachrichten angezeigt werden soll</span><span class="sxs-lookup"><span data-stu-id="cff15-128">The e-mail address to show on outgoing e-mail messages.</span></span>  
  
-   <span data-ttu-id="cff15-129">Den Namen, der auf ausgehenden E-Mail-Nachrichten angezeigt werden soll</span><span class="sxs-lookup"><span data-stu-id="cff15-129">The display name to show on outgoing e-mail messages.</span></span>  
  
-   <span data-ttu-id="cff15-130">Den Namen des SMTP-Servers</span><span class="sxs-lookup"><span data-stu-id="cff15-130">The server name of the SMTP server.</span></span>  
  
-   <span data-ttu-id="cff15-131">Den Benutzernamen, der zum Anmelden am SMTP-Server verwendet werden soll, falls der SMTP-Server eine Authentifizierung erfordert</span><span class="sxs-lookup"><span data-stu-id="cff15-131">The user name to use to log on to the SMTP server, if the SMTP server requires authentication.</span></span>  
  
-   <span data-ttu-id="cff15-132">Das Kennwort, das zum Anmelden am SMTP-Server verwendet werden soll, falls der SMTP-Server eine Authentifizierung erfordert</span><span class="sxs-lookup"><span data-stu-id="cff15-132">The password to use to log on to the SMTP server, if the SMTP server requires authentication.</span></span>  
  
 <span data-ttu-id="cff15-133">Im folgenden Beispiel wird ein neues Datenbank-E-Mail-Konto erstellt.</span><span class="sxs-lookup"><span data-stu-id="cff15-133">The following example creates a new Database Mail account.</span></span>  
  
```  
EXECUTE msdb.dbo.sysmail_add_account_sp  
    @account_name = 'AdventureWorks Administrator',  
    @description = 'Mail account for administrative e-mail.',  
    @email_address = 'dba@Adventure-Works.com',  
    @display_name = 'AdventureWorks Automated Mailer',  
    @mailserver_name = 'smtp.Adventure-Works.com' ;  
```  
  
##  <a name="follow-up-next-steps-to-configuring-the-database-mail"></a><a name="FollowUp"></a><span data-ttu-id="cff15-134">Nächster Schritt: Nächste Schritte zum Konfigurieren von Datenbank-E-Mail</span><span class="sxs-lookup"><span data-stu-id="cff15-134">Follow Up: Next Steps to Configuring the Database Mail</span></span>  
  
-   [<span data-ttu-id="cff15-135">Erstellen eines Profils für Datenbank-E-Mail</span><span class="sxs-lookup"><span data-stu-id="cff15-135">Create a Database Mail Profile</span></span>](create-a-database-mail-profile.md)  
  
  
