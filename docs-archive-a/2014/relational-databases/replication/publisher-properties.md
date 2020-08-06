---
title: SQL Server-Replikation Verleger Eigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.configdistwizard.distpubproperties.f1
- sql12.rep.configdistwizard.pubproperties.general.f1
- sql12.rep.configdistwizard.pubproperties.pubdb.f1
- sql12.rep.configdistwizard.pubproperties.subscribers.f1
ms.assetid: 98df1aea-0406-40bf-a917-4bd80464125c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f3e14f82e855cc29f83859d85dfdaaf85a1bda37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701048"
---
# <a name="sql-server-replication-publisher-properties"></a><span data-ttu-id="2d2a7-102">SQL Server-Replikation Herausgeber Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2d2a7-102">SQL Server Replication Publisher Properties</span></span>
  <span data-ttu-id="2d2a7-103">Dieser Abschnitt enthält Informationen zu den Verleger Eigenschaften, die auf dem Verteiler und dem Verleger verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="2d2a7-103">This section contains information on Publisher properties available at the Distributor and the Publisher.</span></span> 

## <a name="general"></a><span data-ttu-id="2d2a7-104">Allgemein</span><span class="sxs-lookup"><span data-stu-id="2d2a7-104">General</span></span>  
  <span data-ttu-id="2d2a7-105"> Die Seite **Allgemein** des Dialogfelds **Verlegereigenschaften** zeigt schreibgeschützte Informationen zu dem Verteiler und der Verteilungsdatenbank an, die vom Verleger verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2d2a7-105">The **General** page of the **Publisher Properties** dialog box displays read-only information on the Distributor and distribution database that the Publisher uses.</span></span> <span data-ttu-id="2d2a7-106">So ändern Sie den Verteiler oder die Verteilungsdatenbank für einen Verleger:</span><span class="sxs-lookup"><span data-stu-id="2d2a7-106">To change the Distributor or distribution database for a Publisher:</span></span>  
  
1.  <span data-ttu-id="2d2a7-107">Deaktivieren Sie die Veröffentlichung auf dem Verleger.</span><span class="sxs-lookup"><span data-stu-id="2d2a7-107">Disable publishing on the Publisher.</span></span> <span data-ttu-id="2d2a7-108">Weitere Informationen finden Sie unter [Deaktivieren der Veröffentlichung und Verteilung](disable-publishing-and-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="2d2a7-108">For more information, see [Disable Publishing and Distribution](disable-publishing-and-distribution.md).</span></span>    
2.  <span data-ttu-id="2d2a7-109">Konfigurieren Sie die Veröffentlichung und die Verteilung neu.</span><span class="sxs-lookup"><span data-stu-id="2d2a7-109">Reconfigure publishing and distribution.</span></span> <span data-ttu-id="2d2a7-110">Weitere Informationen finden Sie unter [Configure Publishing and Distribution](configure-publishing-and-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="2d2a7-110">For more information, see [Configure Publishing and Distribution](configure-publishing-and-distribution.md).</span></span>  

## <a name="distributor"></a><span data-ttu-id="2d2a7-111">Verteiler</span><span class="sxs-lookup"><span data-stu-id="2d2a7-111">Distributor</span></span>
  <span data-ttu-id="2d2a7-112">Mithilfe des Dialogfelds **Verlegereigenschaften** können Sie mit der Beziehung zwischen dem Verleger und dem Verteiler verknüpfte Eigenschaften anzeigen und ändern.</span><span class="sxs-lookup"><span data-stu-id="2d2a7-112">The **Publisher Properties** dialog box allows you to view and modify properties associated with the relationship between the Publisher and its Distributor.</span></span>  
  
### <a name="options"></a><span data-ttu-id="2d2a7-113">Tastatur</span><span class="sxs-lookup"><span data-stu-id="2d2a7-113">Options</span></span>  
 <span data-ttu-id="2d2a7-114">**Agentverbindung mit dem Verleger**</span><span class="sxs-lookup"><span data-stu-id="2d2a7-114">**Agent Connection to the Publisher**</span></span>  
 <span data-ttu-id="2d2a7-115">Geben Sie den Kontext an, in dem die folgenden Agenten Verbindungen vom Verteiler zum Verleger herstellen können:</span><span class="sxs-lookup"><span data-stu-id="2d2a7-115">Specify the context under which the following agents make connections from the Distributor to the Publisher:</span></span>  
  
-   <span data-ttu-id="2d2a7-116">Der Warteschlangenlese-Agent für Transaktionsveröffentlichungen, die Abonnements mit verzögertem Update über eine Warteschlange gestatten.</span><span class="sxs-lookup"><span data-stu-id="2d2a7-116">The Queue Reader Agent for transactional publications that allow queued updating subscriptions.</span></span>  
  
-   <span data-ttu-id="2d2a7-117">Der Momentaufnahme-Agent und der Protokolllese-Agent für Oracle-Veröffentlichungen.</span><span class="sxs-lookup"><span data-stu-id="2d2a7-117">The Snapshot Agent and Log Reader Agent for Oracle publications.</span></span>  
  
 <span data-ttu-id="2d2a7-118">Wählen Sie **Identität des Agentprozesskontos annehmen** aus, um Verbindungen mit dem Verleger mithilfe des Kontexts des [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Kontos herzustellen, unter dem diese Agents ausgeführt werden, oder geben Sie **SQL Server-Authentifizierung**an, und geben Sie dann einen Wert für **Benutzername** und **Kennwort**ein.</span><span class="sxs-lookup"><span data-stu-id="2d2a7-118">Select **Impersonate agent process account** to make connections to the Publisher using the context of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account under which these agents run, or specify **SQL Server Authentication**, and then enter a value for **Login** and **Password**.</span></span> <span data-ttu-id="2d2a7-119">Es wird empfohlen, **Identität des Agentprozesskontos annehmen**auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="2d2a7-119">It is recommended that you select **Impersonate agent process account**.</span></span> <span data-ttu-id="2d2a7-120">Weitere Informationen zur Agentsicherheit finden Sie unter [Replication Agent Security Model](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="2d2a7-120">For more information on agent security, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
 <span data-ttu-id="2d2a7-121">Die Windows-Konten, unter denen diese Agents ausgeführt werden, werden im Assistenten für neue Veröffentlichung angegeben.</span><span class="sxs-lookup"><span data-stu-id="2d2a7-121">The Windows accounts under which these agents run are specified in the New Publication Wizard.</span></span> <span data-ttu-id="2d2a7-122">Diese Konten können geändert werden:</span><span class="sxs-lookup"><span data-stu-id="2d2a7-122">These accounts can be changed:</span></span>  
  
-   <span data-ttu-id="2d2a7-123">Im Dialogfeld **Verteilereigenschaften** für den Warteschlangenlese-Agent.</span><span class="sxs-lookup"><span data-stu-id="2d2a7-123">In the **Distributor Properties** dialog box for the Queue Reader Agent.</span></span>  
  
-   <span data-ttu-id="2d2a7-124">Im Dialogfeld **Veröffentlichungseigenschaften** für den Momentaufnahme-Agent und den Protokolllese-Agent.</span><span class="sxs-lookup"><span data-stu-id="2d2a7-124">In the **Publication Properties** dialog box for the Snapshot Agent and Log Reader Agent.</span></span>  
  
 <span data-ttu-id="2d2a7-125">**Verschiedenes**</span><span class="sxs-lookup"><span data-stu-id="2d2a7-125">**Miscellaneous**</span></span>  
 <span data-ttu-id="2d2a7-126">Die Eigenschaften **Verlegertyp** und **Name der Verteilungsdatenbank** sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="2d2a7-126">The properties **Publisher Type** and **Distribution Database Name** are read-only.</span></span> <span data-ttu-id="2d2a7-127">Die Eigenschaft **Standardmomentaufnahmeordner** kann geändert werden.</span><span class="sxs-lookup"><span data-stu-id="2d2a7-127">The property **Default Snapshot Folder** can be changed.</span></span> <span data-ttu-id="2d2a7-128">Weitere Informationen zum Momentaufnahmeordner finden Sie unter [Sichern des Momentaufnahmeordners](security/secure-the-snapshot-folder.md).</span><span class="sxs-lookup"><span data-stu-id="2d2a7-128">For more information about the snapshot folder, see [Secure the Snapshot Folder](security/secure-the-snapshot-folder.md).</span></span>  
  

## <a name="publication-databases"></a><span data-ttu-id="2d2a7-129">Veröffentlichungsdatenbanken</span><span class="sxs-lookup"><span data-stu-id="2d2a7-129">Publication Databases</span></span>
  <span data-ttu-id="2d2a7-130"> Mithilfe der Seite **Veröffentlichungsdatenbanken** des Dialogfelds **Verlegereigenschaften** können Benutzer mit der festen Serverrolle **sysadmin** Datenbanken für die Replikation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2d2a7-130">The **Publication Databases** page of the **Publisher Properties** dialog box allows a user in the **sysadmin** fixed server role to enable databases for replication.</span></span> <span data-ttu-id="2d2a7-131">Das Aktivieren der Datenbank führt nicht zur Veröffentlichung dieser Datenbank. Vielmehr ermöglicht dies allen Benutzern mit der festen Datenbankrolle **db_owner** für diese Datenbank eine oder mehrere Veröffentlichungen auf dieser Datenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2d2a7-131">Enabling a database does not publish that database; rather, it allows any user in the **db_owner** fixed database role for that database to create one or more publications on the database.</span></span>  
  
### <a name="options"></a><span data-ttu-id="2d2a7-132">Tastatur</span><span class="sxs-lookup"><span data-stu-id="2d2a7-132">Options</span></span>  
 <span data-ttu-id="2d2a7-133">**Transaktion**</span><span class="sxs-lookup"><span data-stu-id="2d2a7-133">**Transactional**</span></span>  
 <span data-ttu-id="2d2a7-134">Aktivieren Sie dieses Kontrollkästchen, um es Benutzern mit der festen Datenbankrolle **db_owner** zu ermöglichen, Momentaufnahme- oder Transaktionsveröffentlichungen in der Datenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2d2a7-134">Select this check box to allow users in the **db_owner** fixed database role to create snapshot publications or transactional publications in the database.</span></span> 
  
 <span data-ttu-id="2d2a7-135">**Merge** (Zusammenführen)</span><span class="sxs-lookup"><span data-stu-id="2d2a7-135">**Merge**</span></span>  
 <span data-ttu-id="2d2a7-136">Aktivieren Sie dieses Kontrollkästchen, um es Benutzern mit der festen Datenbankrolle **db_owner** zu ermöglichen, Mergeveröffentlichungen in der Datenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2d2a7-136">Select this check box to allow users in the **db_owner** fixed database role to create merge publications in the database.</span></span>  

## <a name="subscribers"></a><span data-ttu-id="2d2a7-137">Abonnenten</span><span class="sxs-lookup"><span data-stu-id="2d2a7-137">Subscribers</span></span>

  <span data-ttu-id="2d2a7-138">Die Seite **Abonnenten** des Dialogfelds **Verlegereigenschaften** wird für Verleger verwendet, die Versionen von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vor [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ausführen.</span><span class="sxs-lookup"><span data-stu-id="2d2a7-138">The **Subscribers** page of the **Publisher Properties** dialog box is used for Publishers running versions of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="2d2a7-139">Mithilfe dieser Seite können Sie es Abonnenten ermöglichen, Daten von Veröffentlichungen auf diesem Verleger zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="2d2a7-139">The page allows you to enable Subscribers to receive data from publications on this Publisher.</span></span> <span data-ttu-id="2d2a7-140">Wenn Sie einem Abonnenten ermöglichen, Daten von diesem Verleger zu empfangen, werden dadurch keine Abonnements für Veröffentlichungen auf diesem Verleger erstellt.</span><span class="sxs-lookup"><span data-stu-id="2d2a7-140">Enabling a Subscriber to receive data from this Publisher does not create subscriptions to publications on this Publisher.</span></span> <span data-ttu-id="2d2a7-141">Zum Erstellen eines Abonnements müssen Sie den Assistenten für neue Abonnements verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d2a7-141">To create a subscription, you must use the New Subscription Wizard.</span></span>  
  
### <a name="options"></a><span data-ttu-id="2d2a7-142">Tastatur</span><span class="sxs-lookup"><span data-stu-id="2d2a7-142">Options</span></span>  
 <span data-ttu-id="2d2a7-143">**Abonnenten**</span><span class="sxs-lookup"><span data-stu-id="2d2a7-143">**Subscribers**</span></span>  
 <span data-ttu-id="2d2a7-144">Das Eigenschaftenraster **Abonnenten** zeigt Abonnenten an, die zum Empfangen von Daten von Veröffentlichungen auf diesem Verleger aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="2d2a7-144">The **Subscribers** property grid shows Subscribers that are enabled to receive data from publications on this Publisher.</span></span> <span data-ttu-id="2d2a7-145">Klicken Sie neben einem Abonnenten auf die Eigenschaftenschaltfläche (die Schaltfläche mit den **drei Punkten**), um zusätzliche Eigenschaften anzuzeigen und festzulegen.</span><span class="sxs-lookup"><span data-stu-id="2d2a7-145">Click the properties button (**...**) next to a Subscriber to view and set additional properties.</span></span>  
  
 <span data-ttu-id="2d2a7-146">**Add**</span><span class="sxs-lookup"><span data-stu-id="2d2a7-146">**Add**</span></span>  
 <span data-ttu-id="2d2a7-147">Klicken Sie auf **Hinzufügen** , um einen Abonnenten hinzuzufügen, und dann auf **SQL Server-Abonnenten hinzufügen** oder **Nicht-SQL Server-Abonnenten hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2d2a7-147">Click **Add** to add a Subscriber, and then click **Add SQL Server Subscriber** or **Add Non-SQL Server Subscriber**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="2d2a7-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d2a7-148">See Also</span></span>  
 [<span data-ttu-id="2d2a7-149">Anzeigen und Ändern der Verteiler- und Verlegereigenschaften</span><span class="sxs-lookup"><span data-stu-id="2d2a7-149">View and Modify Distributor and Publisher Properties</span></span>](view-and-modify-distributor-and-publisher-properties.md)   

  
  
