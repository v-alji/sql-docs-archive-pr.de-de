---
title: Verwalten von Anmeldungen in der Veröffentlichungszugriffsliste| Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- logins [SQL Server replication], publication access list
- publications [SQL Server replication], publication access lists
- publication access list (PAL)
- PAL (publication access list)
- logins [SQL Server replication], managing
ms.assetid: fceb216b-0b18-4e3b-8ae0-13e35920dcbc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b96e6f46403cf3a482f00a3f5155527177920967
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615921"
---
# <a name="manage-logins-in-the-publication-access-list"></a><span data-ttu-id="b056a-102">Verwalten von Anmeldungen in der Veröffentlichungszugriffsliste</span><span class="sxs-lookup"><span data-stu-id="b056a-102">Manage Logins in the Publication Access List</span></span>
  <span data-ttu-id="b056a-103">In diesem Thema wird beschrieben, wie Anmeldungen in der Veröffentlichungszugriffsliste in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../../includes/tsql-md.md)]verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="b056a-103">This topic describes how to manage logins in the Publication Access List in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b056a-104">Der Zugriff auf eine Veröffentlichung wird von der Veröffentlichungszugriffsliste (Publication Access List, PAL) gesteuert.</span><span class="sxs-lookup"><span data-stu-id="b056a-104">Access to a publication is controlled by the publication access list (PAL).</span></span> <span data-ttu-id="b056a-105">Anmeldungen und Gruppen können hinzugefügt und aus PAL entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="b056a-105">Logins and groups can be added and removed from the PAL.</span></span>  
  
 <span data-ttu-id="b056a-106">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="b056a-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b056a-107">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="b056a-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b056a-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b056a-108">Prerequisites</span></span>](#Prerequisites)  
  
-   <span data-ttu-id="b056a-109">**So verwalten Sie Anmeldungen in der Veröffentlichungszugriffsliste mit:**</span><span class="sxs-lookup"><span data-stu-id="b056a-109">**To manage logins in the Publication Access List, using:**</span></span>  
  
     [<span data-ttu-id="b056a-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b056a-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b056a-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b056a-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b056a-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="b056a-112">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="b056a-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b056a-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="b056a-114">Sie müssen einem Datenbankbenutzer in der Veröffentlichungsdatenbank die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Anmeldung zuordnen, bevor Sie die Anmeldung PAL hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b056a-114">You must associate the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login with a database user in the publication database before you add the login to the PAL.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b056a-115">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b056a-115">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="b056a-116">Sie verwenden die Veröffentlichungszugriffsliste (Publication Access List, PAL) auf der Seite **Veröffentlichungszugriffsliste** des Dialogfelds **Veröffentlichungseigenschaften - \<Publication>** zum Verwalten der Anmeldenamen.</span><span class="sxs-lookup"><span data-stu-id="b056a-116">You use the publication access list (PAL) on the **Publication Access List** page of the **Publication Properties - \<Publication>** dialog box to manage logins.</span></span> <span data-ttu-id="b056a-117">Weitere Informationen zum Zugreifen auf dieses Dialogfeld finden Sie unter [Anzeigen und Ändern von Veröffentlichungseigenschaften](../publish/view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="b056a-117">For more information about how to access this dialog box, see [View and Modify Publication Properties](../publish/view-and-modify-publication-properties.md).</span></span>  
  
#### <a name="to-manage-logins-in-the-pal"></a><span data-ttu-id="b056a-118">So verwalten Sie Anmeldenamen in der Veröffentlichungszugriffsliste</span><span class="sxs-lookup"><span data-stu-id="b056a-118">To manage logins in the PAL</span></span>  
  
1.  <span data-ttu-id="b056a-119">Die Seite **Veröffentlichungszugriffsliste** des Dialogfelds **Veröffentlichungseigenschaften - \<Publication>** enthält die Schaltflächen **Hinzufügen**, **Entfernen** und **Alle entfernen**, mit denen Sie Benutzer (Anmeldenamen) und Gruppen in die Veröffentlichungszugriffsliste aufnehmen bzw. entfernen können.</span><span class="sxs-lookup"><span data-stu-id="b056a-119">On the **Publication Access List** page of the **Publication Properties - \<Publication>** dialog box, use the **Add**, **Remove**, and **Remove All** buttons to add and remove logins and groups from the PAL.</span></span> <span data-ttu-id="b056a-120">Sie dürfen **distributor_admin** nicht aus der PAL entfernen.</span><span class="sxs-lookup"><span data-stu-id="b056a-120">Do not remove **distributor_admin** from the PAL.</span></span> <span data-ttu-id="b056a-121">Dieses Konto wird für die Replikation verwendet.</span><span class="sxs-lookup"><span data-stu-id="b056a-121">This account is used by replication.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b056a-122">Wenn ein Remoteverteiler verwendet wird, müssen Konten in der PAL sowohl beim Verleger als auch beim Verteiler verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="b056a-122">If a remote Distributor is used, accounts in the PAL must be available at both the Publisher and the Distributor.</span></span> <span data-ttu-id="b056a-123">Das Konto muss entweder ein Domänenkonto oder ein lokales Konto sein, das auf beiden Servern definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b056a-123">The account must be either a domain account or a local account that is defined at both servers.</span></span> <span data-ttu-id="b056a-124">Die den Anmeldenamen zugehörigen Kennwörter müssen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="b056a-124">The passwords that are associated with both logins must be the same.</span></span>  
  
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b056a-125">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b056a-125">Using Transact-SQL</span></span>  
  
#### <a name="to-view-groups-and-logins-that-belong-to-the-pal"></a><span data-ttu-id="b056a-126">So zeigen Sie Gruppen und Anmeldungen an, die zur PAL gehören</span><span class="sxs-lookup"><span data-stu-id="b056a-126">To view groups and logins that belong to the PAL</span></span>  
  
1.  <span data-ttu-id="b056a-127">Führen Sie beim Verleger für die Veröffentlichungsdatenbank [sp_help_publication_access](/sql/relational-databases/system-stored-procedures/sp-help-publication-access-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="b056a-127">At the Publisher on the publication database, execute [sp_help_publication_access](/sql/relational-databases/system-stored-procedures/sp-help-publication-access-transact-sql).</span></span> <span data-ttu-id="b056a-128">Geben Sie für \*\* \@ Veröffentlichung\*\*den Veröffentlichungsnamen an.</span><span class="sxs-lookup"><span data-stu-id="b056a-128">For **\@publication**, specify the publication name.</span></span> <span data-ttu-id="b056a-129">Dadurch werden Informationen über die Gruppen und Anmeldungen in der PAL angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b056a-129">This displays information about the groups and logins in the PAL.</span></span>  
  
#### <a name="to-add-groups-and-logins-to-the-pal"></a><span data-ttu-id="b056a-130">So fügen Sie der PAL Gruppen und Anmeldungen hinzu</span><span class="sxs-lookup"><span data-stu-id="b056a-130">To add groups and logins to the PAL</span></span>  
  
1.  <span data-ttu-id="b056a-131">Führen Sie auf dem Verleger für die Veröffentlichungsdatenbank [sp_grant_publication_access](/sql/relational-databases/system-stored-procedures/sp-grant-publication-access-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="b056a-131">At the Publisher on the publication database, execute [sp_grant_publication_access](/sql/relational-databases/system-stored-procedures/sp-grant-publication-access-transact-sql).</span></span> <span data-ttu-id="b056a-132">Geben Sie für \*\* \@ Veröffentlichung**den Veröffentlichungsnamen an, und geben Sie für \*\* \@ Login**den Namen des Anmelde namens oder der Gruppe an, der hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="b056a-132">For **\@publication**, specify the publication name; and for **\@login**, specify the name of the login or group that is being added.</span></span>  
  
#### <a name="to-remove-groups-and-logins-from-the-pal"></a><span data-ttu-id="b056a-133">So entfernen Sie Gruppen und Anmeldungen aus der PAL</span><span class="sxs-lookup"><span data-stu-id="b056a-133">To remove groups and logins from the PAL</span></span>  
  
1.  <span data-ttu-id="b056a-134">Führen Sie auf dem Verleger für die Veröffentlichungsdatenbank [sp_revoke_publication_access](/sql/relational-databases/system-stored-procedures/sp-revoke-publication-access-transact-sql)aus.</span><span class="sxs-lookup"><span data-stu-id="b056a-134">At the Publisher on the publication database, execute [sp_revoke_publication_access](/sql/relational-databases/system-stored-procedures/sp-revoke-publication-access-transact-sql).</span></span> <span data-ttu-id="b056a-135">Geben Sie für \*\* \@ Veröffentlichung**den Veröffentlichungsnamen an, und geben Sie für \*\* \@ Login**den Namen des Anmelde namens oder der Gruppe an, der entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="b056a-135">For **\@publication**, specify the publication name; and for **\@login**, specify the name of the login or group that is being removed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b056a-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b056a-136">See Also</span></span>  
 <span data-ttu-id="b056a-137">[Sicherheitsmodell des Replikations-Agents](replication-agent-security-model.md) </span><span class="sxs-lookup"><span data-stu-id="b056a-137">[Replication Agent Security Model](replication-agent-security-model.md) </span></span>  
 <span data-ttu-id="b056a-138">[Sichern einer Replikationstopologie](view-and-modify-replication-security-settings.md) </span><span class="sxs-lookup"><span data-stu-id="b056a-138">[Secure a Replication Topology](view-and-modify-replication-security-settings.md) </span></span>  
 [<span data-ttu-id="b056a-139">Sichern des Verlegers</span><span class="sxs-lookup"><span data-stu-id="b056a-139">Secure the Publisher</span></span>](secure-the-publisher.md)  
  
  
