---
title: Verschlüsselte Datenbanken mit AlwaysOn-Verfügbarkeitsgruppen (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Transparent Data Encryption, AlwaysOn Availability Groups
- TDE, AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 09eb6ebc-3051-4fff-86a5-93524507b1fc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 91e717a896634a7df5a96253c51207831f142cff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609449"
---
# <a name="encrypted-databases-with-alwayson-availability-groups-sql-server"></a><span data-ttu-id="267bc-102">Verschlüsselte Datenbanken bei AlwaysOn-Verfügbarkeitsgruppen (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="267bc-102">Encrypted Databases with AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="267bc-103">Dieses Thema enthält Informationen zur Verwendung aktuell verschlüsselter oder vor kurzem entschlüsselter Datenbanken mit [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="267bc-103">This topic contains information about the using currently encrypted or recently decrypted databases with [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="267bc-104">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="267bc-104">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="267bc-105">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="267bc-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
-   [<span data-ttu-id="267bc-106">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="267bc-106">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="267bc-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="267bc-107">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="267bc-108">Wenn eine Datenbank verschlüsselt ist oder sogar einen Datenbankverschlüsselungs-Schlüssel (DEK) enthält, können Sie die Datenbank nicht mithilfe von [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] oder [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] einer Verfügbarkeitsgruppe hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="267bc-108">If a database is encrypted or even contains a Database Encryption Key (DEK), you cannot use the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] or [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] to add the database to an availability group.</span></span> <span data-ttu-id="267bc-109">Selbst wenn eine verschlüsselte Datenbank entschlüsselt wurde, enthalten ihre Protokollsicherungen möglicherweise verschlüsselte Daten.</span><span class="sxs-lookup"><span data-stu-id="267bc-109">Even if an encrypted database has been decrypted, its log backups might contain encrypted data.</span></span> <span data-ttu-id="267bc-110">In diesem Fall ist es unter Umständen nicht möglich, die anfängliche Datensynchronisierung vollständig auf der Datenbank durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="267bc-110">In this case, full initial data synchronization could fail on the database.</span></span> <span data-ttu-id="267bc-111">Grund hierfür ist die Tatsache, dass für den Wiederherstellungsprotokollvorgang eventuell das Zertifikat erforderlich ist, das von den Datenbank-Verschlüsselungsschlüsseln (DEKs) verwendet wurde, und dieses Zertifikat möglicherweise nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="267bc-111">This is because the restore log operation might require the certificate that was used by the database encryption keys (DEKs), and that certificate might be unavailable.</span></span>  
  
     <span data-ttu-id="267bc-112">So machen Sie eine entschlüsselte Datenbank verfügbar für das Hinzufügen zu einer Verfügbarkeitsgruppe mithilfe des Assistenten:</span><span class="sxs-lookup"><span data-stu-id="267bc-112">To make a decrypted database eligible to add to an availability group using the wizard:</span></span>  
  
    1.  <span data-ttu-id="267bc-113">Erstellen Sie eine Protokollsicherung von der primären Datenbank.</span><span class="sxs-lookup"><span data-stu-id="267bc-113">Create a log backup of the primary database.</span></span>  
  
    2.  <span data-ttu-id="267bc-114">Erstellen Sie eine vollständige Datenbanksicherung der primären Datenbank.</span><span class="sxs-lookup"><span data-stu-id="267bc-114">Create a full database backup of the primary database.</span></span>  
  
    3.  <span data-ttu-id="267bc-115">Stellen Sie die Datenbanksicherung auf der Serverinstanz wieder her, die das sekundäre Replikat hostet.</span><span class="sxs-lookup"><span data-stu-id="267bc-115">Restore the database backup on the server instance that hosts the secondary replica.</span></span>  
  
    4.  <span data-ttu-id="267bc-116">Erstellen Sie eine neue Protokollsicherung aus der primären Datenbank.</span><span class="sxs-lookup"><span data-stu-id="267bc-116">Create a new log backup from primary database.</span></span>  
  
    5.  <span data-ttu-id="267bc-117">Stellen Sie diese Protokollsicherung in der sekundären Datenbank wieder her.</span><span class="sxs-lookup"><span data-stu-id="267bc-117">Restore this log backup on the secondary database.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="267bc-118">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="267bc-118">Related Tasks</span></span>  
  
-   [<span data-ttu-id="267bc-119">Manuelles Vorbereiten einer sekundären Datenbank auf eine Verfügbarkeitsgruppe &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="267bc-119">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="267bc-120">Verwenden des Assistenten für Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="267bc-120">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="267bc-121">Verwenden des Assistenten zum Hinzufügen von Datenbanken zu Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="267bc-121">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="267bc-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="267bc-122">See Also</span></span>  
 <span data-ttu-id="267bc-123">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="267bc-123">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="267bc-124">Transparente Datenverschlüsselung &#40;TDE&#41;</span><span class="sxs-lookup"><span data-stu-id="267bc-124">Transparent Data Encryption &#40;TDE&#41;</span></span>](../../../relational-databases/security/encryption/transparent-data-encryption.md)  
  
  
