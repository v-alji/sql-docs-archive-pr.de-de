---
title: Dienstkonten (Assistent zum Konfigurieren der Sicherheit für die Datenbankspiegelung) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.serviceaccounts.f1
ms.assetid: d58d8f93-7888-4d66-af4d-969ef6a2dbee
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 58e49467a28e816c6592b1ded212b5aea0e6bc55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701769"
---
# <a name="service-accounts-configure-database-mirroring-security-wizard"></a><span data-ttu-id="905a1-102">Dienstkonten (Assistent zum Konfigurieren der Sicherheit für die Datenbankspiegelung)</span><span class="sxs-lookup"><span data-stu-id="905a1-102">Service Accounts (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="905a1-103">Geben Sie bei Verwendung der Windows-Authentifizierung die Dienstkonten für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]an, wenn die Serverinstanzen verschiedene Konten verwenden.</span><span class="sxs-lookup"><span data-stu-id="905a1-103">When using Windows Authentication, if the server instances use different accounts, specify the service accounts for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="905a1-104">Diese Dienstkonten müssen alle Domänenkonten (in derselben oder vertrauenswürdigen Domäne) sein.</span><span class="sxs-lookup"><span data-stu-id="905a1-104">These service accounts must all be domain accounts (in the same or trusted domains).</span></span>  
  
 <span data-ttu-id="905a1-105">Wenn alle Serverinstanzen das gleiche Domänenkonto oder die zertifikatbasierte Authentifizierung verwenden, lassen Sie die Felder leer.</span><span class="sxs-lookup"><span data-stu-id="905a1-105">If all the server instances use the same domain account or use certificate-based authentication, leave the fields blank.</span></span> <span data-ttu-id="905a1-106">Klicken Sie einfach auf **Fertig stellen**, und der Assistent konfiguriert automatisch die Konten auf Basis des Kontos des aktuellen Assistenten.</span><span class="sxs-lookup"><span data-stu-id="905a1-106">Simply click **Finish**, and the wizard automatically configures the accounts based on the account of the current wizard.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="905a1-107">Wenn die Endpunkte für die Datenbankspiegelung der Serverinstanzen für die Verwendung von Zertifikaten konfiguriert sind, müssen Sie die Felder für die Dienstkonten leer lassen.</span><span class="sxs-lookup"><span data-stu-id="905a1-107">If the database mirroring endpoints of the server instances are configured to use certificates, you must leave the service account fields empty.</span></span>  
  
 <span data-ttu-id="905a1-108">**So konfigurieren Sie die Datenbankspiegelung mithilfe von SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="905a1-108">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="905a1-109">Einrichten einer Datenbank-Spiegelungssitzung mithilfe der Windows-Authentifizierung &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="905a1-109">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="905a1-110">Starten des Assistenten zum Konfigurieren der Sicherheit für die Datenbankspiegelung &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="905a1-110">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="905a1-111">Tastatur</span><span class="sxs-lookup"><span data-stu-id="905a1-111">Options</span></span>  
 <span data-ttu-id="905a1-112">**Prinzipal**</span><span class="sxs-lookup"><span data-stu-id="905a1-112">**Principal**</span></span>  
 <span data-ttu-id="905a1-113">Geben Sie das Dienstkonto der Prinzipalserverinstanz an.</span><span class="sxs-lookup"><span data-stu-id="905a1-113">Specify the service account of the principal server instance.</span></span> <span data-ttu-id="905a1-114">Geben Sie den Domänennamen in Großbuchstaben ein:</span><span class="sxs-lookup"><span data-stu-id="905a1-114">Enter the domain name in upper case:</span></span>  
  
 <span data-ttu-id="905a1-115">*Domain Name* \\ *Benutzername*</span><span class="sxs-lookup"><span data-stu-id="905a1-115">*DOMAINNAME*\\*username*</span></span>  
  
 <span data-ttu-id="905a1-116">**Spiegel**</span><span class="sxs-lookup"><span data-stu-id="905a1-116">**Mirror**</span></span>  
 <span data-ttu-id="905a1-117">Geben Sie das Dienstkonto der Spiegelserverinstanz an.</span><span class="sxs-lookup"><span data-stu-id="905a1-117">Specify the service account of the mirror server instance.</span></span> <span data-ttu-id="905a1-118">Geben Sie den Domänennamen in Großbuchstaben ein:</span><span class="sxs-lookup"><span data-stu-id="905a1-118">Enter the domain name in upper case:</span></span>  
  
 <span data-ttu-id="905a1-119">*Domain Name* \\ *Benutzername*</span><span class="sxs-lookup"><span data-stu-id="905a1-119">*DOMAINNAME*\\*username*</span></span>  
  
 <span data-ttu-id="905a1-120">**Denke**</span><span class="sxs-lookup"><span data-stu-id="905a1-120">**Witness**</span></span>  
 <span data-ttu-id="905a1-121">Geben Sie das Dienstkonto der Zeugenserverinstanz an.</span><span class="sxs-lookup"><span data-stu-id="905a1-121">Specify the service account of the witness server instance.</span></span> <span data-ttu-id="905a1-122">Geben Sie den Domänennamen in Großbuchstaben ein:</span><span class="sxs-lookup"><span data-stu-id="905a1-122">Enter the domain name in upper case:</span></span>  
  
 <span data-ttu-id="905a1-123">*Domain Name* \\ *Benutzername*</span><span class="sxs-lookup"><span data-stu-id="905a1-123">*DOMAINNAME*\\*username*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="905a1-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="905a1-124">See Also</span></span>  
 <span data-ttu-id="905a1-125">[Datenbankeigenschaften &#40;Seite Wird gespiegelt&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="905a1-125">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="905a1-126">[Starten des Datenbankspiegelungs-Monitors &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="905a1-126">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="905a1-127">[Datenbankspiegelung &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="905a1-127">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="905a1-128">Einrichten von Anmeldekonten für die Daten Bank Spiegelung oder AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="905a1-128">Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](set-up-login-accounts-database-mirroring-always-on-availability.md)  
  
  
