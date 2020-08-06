---
title: Anmeldename für aktualisierbare Abonnements | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.updatablesubscriptionslogin.f1
ms.assetid: 301ea227-0455-40ba-9009-d38f8676b325
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6a5cc9190c77f506b13ba8b5fba0e32d5a925570
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723686"
---
# <a name="login-for-updatable-subscriptions"></a><span data-ttu-id="40b63-102">Anmeldename für aktualisierbare Abonnements</span><span class="sxs-lookup"><span data-stu-id="40b63-102">Login for Updatable Subscriptions</span></span>
  <span data-ttu-id="40b63-103">Wenn Sie im Assistenten auf der Seite **Aktualisierbare Abonnements** die Option **Replizieren** ausgewählt haben, müssen Sie auf dem Abonnenten ein Konto angeben, unter dem die Verbindungen mit dem Verleger für die sofort aktualisierbaren Abonnements hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="40b63-103">If you selected **Replicate** on the **Updatable Subscriptions** page of this wizard, you must specify an account at the Subscriber under which connections to the Publisher are made for immediate updating subscriptions.</span></span> <span data-ttu-id="40b63-104">Die Verbindungen werden durch die Trigger verwendet, die auf dem Abonnenten ausgelöst werden und die Änderungen zum Verleger weitergeben.</span><span class="sxs-lookup"><span data-stu-id="40b63-104">Connections are used by the triggers that fire at the Subscriber and propagate changes to the Publisher.</span></span> <span data-ttu-id="40b63-105">Das Konto wird auch dann benötigt, wenn Sie auf der Seite **Aktualisierbare Abonnements** die Option **Änderungen in die Warteschlange einreihen und Commit baldmöglichst ausführen** ausgewählt haben, da die in die Warteschlange eingereihten Updates durch den Assistenten für neue Abonnements standardmäßig so konfiguriert werden, dass die Möglichkeit besteht, zum sofortigen Update zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="40b63-105">This account is required even if you selected **Queue changes and commit when possible** on the **Updatable Subscriptions** page, because by default the New Subscription Wizard configures queued updating with the ability to switch to immediate updating if required.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="40b63-106">Dem für die Verbindung angegebenen Konto sollten nur die Berechtigung zum Einfügen, Aktualisieren und Löschen der Daten in den durch die Replikation in der Veröffentlichungsdatenbank erstellten Sichten erteilt werden; darüber hinaus sollte das Konto über keine weiteren Berechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="40b63-106">The account specified for the connection should only be granted permission to insert, update, and delete data on the views that replication creates in the publication database; it should not be given any additional permissions.</span></span> <span data-ttu-id="40b63-107">Gewähren Sie dem Konto, das Sie für den jeweiligen Abonnenten konfiguriert haben, Berechtigungen für die Sichten in der Veröffentlichungsdatenbank im Format **syncobj_** _\<HexadecimalNumber>_ .</span><span class="sxs-lookup"><span data-stu-id="40b63-107">Grant permissions on views in the publication database that are named in the form **syncobj_**_\<HexadecimalNumber>_ to the account you configured at each Subscriber.</span></span>  
  
 <span data-ttu-id="40b63-108">Für den Typ der Verbindung gibt es drei Optionen:</span><span class="sxs-lookup"><span data-stu-id="40b63-108">There are three options available for the type of connection:</span></span>  
  
-   <span data-ttu-id="40b63-109">Ein vordefinierter Verbindungsserver oder Remoteserver.</span><span class="sxs-lookup"><span data-stu-id="40b63-109">A linked server or remote server that you have already defined.</span></span>  
  
-   <span data-ttu-id="40b63-110">Ein durch die Replikation erstellter Verbindungsserver. Die Verbindung wird mit den Anmeldeinformationen hergestellt, die Sie im Assistenten angeben.</span><span class="sxs-lookup"><span data-stu-id="40b63-110">A linked server that replication creates; the connection is made with the credentials you specify in this wizard.</span></span>  
  
-   <span data-ttu-id="40b63-111">Ein durch die Replikation erstellter Verbindungsserver. Die Verbindung wird mit den Anmeldeinformationen des Benutzers hergestellt, der die Änderung auf dem Abonnenten vornimmt.</span><span class="sxs-lookup"><span data-stu-id="40b63-111">A linked server that replication creates; the connection is made with the credentials of the user making the change at the Subscriber.</span></span>  
  
 <span data-ttu-id="40b63-112">Die ersten beiden Optionen können im Assistenten angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="40b63-112">The first two options can be specified in this wizard.</span></span> <span data-ttu-id="40b63-113">Die letzte Option kann nur mit [sp_link_publication &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-link-publication-transact-sql)angegeben werden. Geben Sie für den Parameter den Wert **1** an **@security_mode** .</span><span class="sxs-lookup"><span data-stu-id="40b63-113">The last option can only be specified using [sp_link_publication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-link-publication-transact-sql); specify a value of **1** for the parameter **@security_mode**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="40b63-114">Tastatur</span><span class="sxs-lookup"><span data-stu-id="40b63-114">Options</span></span>  
 <span data-ttu-id="40b63-115">**Erstellen Sie einen Verbindungsserver, der die Verbindung mithilfe des folgenden Anmeldenamens für die SQL Server-Authentifizierung herstellt:**</span><span class="sxs-lookup"><span data-stu-id="40b63-115">**Create a linked server that connects using the following SQL Server Authentication login:**</span></span>  
 <span data-ttu-id="40b63-116">Durch die Replikation wird ein Verbindungsserver mithilfe der in den Feldern **Anmeldename** und **Kennwort** angegebenen Anmeldeinformationen erstellt.</span><span class="sxs-lookup"><span data-stu-id="40b63-116">Replication creates a linked server using the credentials specified in the **Login** and **Password** fields.</span></span>  
  
 <span data-ttu-id="40b63-117">**Anmeldung**</span><span class="sxs-lookup"><span data-stu-id="40b63-117">**Login**</span></span>  
 <span data-ttu-id="40b63-118">Geben Sie einen [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Anmeldenamen ein, der nur die in diesem Thema beschriebenen Berechtigungen aufweist.</span><span class="sxs-lookup"><span data-stu-id="40b63-118">Enter a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login that has only the permissions described in this topic.</span></span>  
  
 <span data-ttu-id="40b63-119">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="40b63-119">**Password**</span></span>  
 <span data-ttu-id="40b63-120">Geben Sie ein sicheres Kennwort für den in **Anmeldename**angegebenen Anmeldenamen ein.</span><span class="sxs-lookup"><span data-stu-id="40b63-120">Enter a strong password for the login specified in **Login**.</span></span>  
  
 <span data-ttu-id="40b63-121">**Kennwort bestätigen**</span><span class="sxs-lookup"><span data-stu-id="40b63-121">**Confirm Password**</span></span>  
 <span data-ttu-id="40b63-122">Geben Sie das Kennwort zur Bestätigung der fehlerfreien Eingabe erneut ein.</span><span class="sxs-lookup"><span data-stu-id="40b63-122">Re-enter the password to confirm that it was entered correctly.</span></span>  
  
 <span data-ttu-id="40b63-123">**Vordefinierten Verbindungsserver oder Remoteserver verwenden**</span><span class="sxs-lookup"><span data-stu-id="40b63-123">**Use a linked server or remote server that you have already defined.**</span></span>  
 <span data-ttu-id="40b63-124">Bei dieser Option ist ein bereits von Ihnen definierter Verbindungsserver oder Remoteserver erforderlich.</span><span class="sxs-lookup"><span data-stu-id="40b63-124">This option requires a linked server or remote server that you have already defined.</span></span> <span data-ttu-id="40b63-125">Weitere Informationen finden Sie unter [Verbindungsserver &#40;Datenbank-Engine&#41;](../linked-servers/linked-servers-database-engine.md) und [Remoteserver](../../database-engine/configure-windows/remote-servers.md).</span><span class="sxs-lookup"><span data-stu-id="40b63-125">For more information, see [Linked Servers &#40;Database Engine&#41;](../linked-servers/linked-servers-database-engine.md) and [Remote Servers](../../database-engine/configure-windows/remote-servers.md).</span></span> <span data-ttu-id="40b63-126">Stellen Sie sicher, dass der für den Verbindungsserver oder Remoteserver verwendete Anmeldename ein sicheres Kennwort sowie ausschließlich die in diesem Thema beschriebenen Berechtigungen aufweist.</span><span class="sxs-lookup"><span data-stu-id="40b63-126">Ensure that the login used for the linked server or remote server has a strong password and has only the permissions described in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40b63-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="40b63-127">See Also</span></span>  
 <span data-ttu-id="40b63-128">[Create an Updatable Subscription to a Transactional Publication](publish/create-an-updatable-subscription-to-a-transactional-publication.md) </span><span class="sxs-lookup"><span data-stu-id="40b63-128">[Create an Updatable Subscription to a Transactional Publication](publish/create-an-updatable-subscription-to-a-transactional-publication.md) </span></span>  
 <span data-ttu-id="40b63-129">[Anzeigen und Ändern von Replikationssicherheitseinstellungen](security/view-and-modify-replication-security-settings.md) </span><span class="sxs-lookup"><span data-stu-id="40b63-129">[View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md) </span></span>  
 <span data-ttu-id="40b63-130">[Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="40b63-130">[Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md) </span></span>  
 [<span data-ttu-id="40b63-131">Abonnieren von Veröffentlichungen</span><span class="sxs-lookup"><span data-stu-id="40b63-131">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
