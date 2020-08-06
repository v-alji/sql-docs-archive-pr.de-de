---
title: Erstellen eines zentralen Verwaltungs Servers und einer Gruppe
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- configuration server
ms.assetid: da265482-3953-440a-ac23-0ab7e42a55eb
author: markingmyname
ms.author: maghan
ms.openlocfilehash: f53b75966a14dbc6fd6cdc9bea0929ccac7780c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695209"
---
# <a name="create-a-central-management-server-and-server-group-sql-server-management-studio"></a><span data-ttu-id="7f4f9-102">Erstellen eines zentralen Verwaltungsservers und einer Servergruppe (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="7f4f9-102">Create a Central Management Server and Server Group (SQL Server Management Studio)</span></span>
  <span data-ttu-id="7f4f9-103">In diesem Thema wird beschrieben, wie Sie mithilfe von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eine Instanz von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] als zentralen Verwaltungsserver in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]festlegen.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-103">This topic describes how to designate an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as a central management server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="7f4f9-104">Zentrale Verwaltungsserver speichern eine Liste von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanzen, die in ein oder mehrere Gruppen zentraler Verwaltungsserver unterteilt sind.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-104">Central management servers store a list of instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is organized into one or more central management server groups.</span></span> <span data-ttu-id="7f4f9-105">Aktionen, die unter Verwendung einer Gruppe zentraler Verwaltungsserver ausgeführt werden, wirken sich auf alle Server in der Servergruppe aus.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-105">Actions that are taken by using a central management server group act on all servers in the server group.</span></span> <span data-ttu-id="7f4f9-106">Dazu gehören das Herstellen von Verbindungen mit Servern mithilfe des Objekt-Explorers und das Ausführen von [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen und richtlinienbasierten Verwaltungsrichtlinien auf mehreren Servern gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-106">This includes connecting to servers by using Object Explorer and executing [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and Policy-Based Management policies on multiple servers at the same time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7f4f9-107">Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , die älter sind als [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] , können nicht als zentraler Verwaltungsserver festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-107">Versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] cannot be designated as a central management server.</span></span>  
  
 <span data-ttu-id="7f4f9-108">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="7f4f9-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7f4f9-109">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="7f4f9-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7f4f9-110">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7f4f9-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7f4f9-111">**Erstellen eines zentralen Verwaltungsservers und einer Servergruppe mit:**</span><span class="sxs-lookup"><span data-stu-id="7f4f9-111">**To create a Central Management Server and Server Group, using:**</span></span>  
  
     [<span data-ttu-id="7f4f9-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7f4f9-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7f4f9-113">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="7f4f9-113">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7f4f9-114">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7f4f9-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7f4f9-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="7f4f9-115">Permissions</span></span>  
 <span data-ttu-id="7f4f9-116">Zwei Datenbankrollen in der msdb-Datenbank gewähren Zugriff auf die zentralen Verwaltungsserver.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-116">Two database roles in the msdb database grant access to central management servers.</span></span> <span data-ttu-id="7f4f9-117">Nur Mitglieder der Rolle ServerGroupAdministratorRole können den zentralen Verwaltungsserver verwalten.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-117">Only members of the ServerGroupAdministratorRole role can manage the central management server.</span></span> <span data-ttu-id="7f4f9-118">Die Mitgliedschaft in der Rolle ServerGroupReaderRole ist erforderlich, um eine Verbindung mit einem zentralen Verwaltungsserver herzustellen.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-118">Membership in the ServerGroupReaderRole role is required to connect to a central management server.</span></span>  
  
 <span data-ttu-id="7f4f9-119">Da die durch einen zentralen Verwaltungsserver verwalteten Verbindungen im Kontext des Benutzers unter Verwendung der Windows-Authentifizierung ausgeführt werden, können die gültigen Berechtigungen auf den registrierten Servern variieren.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-119">Because the connections that are maintained by a central management server execute in the context of the user, by using Windows Authentication, the effective permissions on the registered servers might vary.</span></span> <span data-ttu-id="7f4f9-120">Der Benutzer kann beispielsweise für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz A ein Mitglied der festen Serverrolle sysadmin sein, für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz B jedoch über eingeschränkte Berechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-120">For example, the user might be a member of the sysadmin fixed server role on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] A, but have limited permissions on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] B.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7f4f9-121">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7f4f9-121">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="7f4f9-122">Die folgenden Verfahren beschreiben, wie Sie die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-122">The following procedures describe how to perform the following steps.</span></span>  
  
1.  <span data-ttu-id="7f4f9-123">Erstellen Sie einen zentralen Verwaltungsserver.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-123">Create a central management server.</span></span>  
  
2.  <span data-ttu-id="7f4f9-124">Fügen Sie dem zentralen Verwaltungsserver eine oder mehrere Servergruppen hinzu, und fügen Sie den Servergruppen einen oder mehrere registrierte Server hinzu.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-124">Add one or more server groups to the central management server and add one or more registered servers to the server groups.</span></span>  
  
#### <a name="create-a-central-management-server"></a><span data-ttu-id="7f4f9-125">Erstellen eines zentralen Verwaltungsservers</span><span class="sxs-lookup"><span data-stu-id="7f4f9-125">Create a central management server</span></span>  
  
1.  <span data-ttu-id="7f4f9-126">Klicken Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]im Menü **Ansicht** auf **Registrierte Server**.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-126">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Registered Servers**.</span></span>  
  
2.  <span data-ttu-id="7f4f9-127">Erweitern Sie im Fenster „Registrierte Server“ den Knoten **Datenbank-Engine**, klicken Sie mit der rechten Maustaste auf **Zentrale Verwaltungsserver**, und klicken Sie dann auf **Zentralen Verwaltungsserver registieren**.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-127">In Registered Servers, expand **Database Engine**, right-click **Central Management Servers**, and then  click **Register Central Management Server**.</span></span>  
  
3.  <span data-ttu-id="7f4f9-128">Wählen Sie im Dialogfeld **Neuen Server registrieren** aus der Dropdownliste von Servern die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aus, die der zentrale Verwaltungsserver werden soll.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-128">In the **New Server Registration** dialog box, select the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to become the central management server from the drop-down list of servers.</span></span> <span data-ttu-id="7f4f9-129">Sie müssen für den zentralen Verwaltungsserver die Windows-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-129">You must use Windows Authentication for the central management server.</span></span>  
  
4.  <span data-ttu-id="7f4f9-130">Geben Sie im Feld **Registrierter Server**einen Servernamen und ggf. eine Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-130">In **Registered Server**, enter a server name and optional description.</span></span>  
  
5.  <span data-ttu-id="7f4f9-131">Prüfen oder ändern Sie auf der Registerkarte **Verbindungseigenschaften** die Netzwerk- und Verbindungseigenschaften.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-131">From the **Connection Properties** tab, review or modifiy the network  and connection properties.</span></span> <span data-ttu-id="7f4f9-132">Weitere Informationen finden Sie unter [Verbinden mit SQL Server-Datenbank-Engine &#40;Eigenschaftenseite Verbindung&#41;](../f1-help/connect-to-server-connection-properties-page-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="7f4f9-132">For more information, see [Connect to Server &#40;Connection Properties Page&#41; Database Engine](../f1-help/connect-to-server-connection-properties-page-database-engine.md)</span></span>  
  
6.  <span data-ttu-id="7f4f9-133">Klicken Sie auf **Testen**, um die Verbindung zu testen.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-133">Click **Test**, to test the connection.</span></span>  
  
7.  <span data-ttu-id="7f4f9-134">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-134">Click **Save**.</span></span> <span data-ttu-id="7f4f9-135">Die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird unter dem Ordner **Zentrale Verwaltungsserver** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-135">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will appear under the **Central Management Servers** folder.</span></span>  
  
#### <a name="create-a-new-server-group-and-add-servers-to-the-group"></a><span data-ttu-id="7f4f9-136">Erstellen einer neuen Servergruppe und Hinzufügen von Servern zur Gruppe</span><span class="sxs-lookup"><span data-stu-id="7f4f9-136">Create a new server group and add servers to the group</span></span>  
  
1.  <span data-ttu-id="7f4f9-137">Erweitern Sie im Fenster **Registrierte Server** **Zentrale Verwaltungsserver**.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-137">From **Registered Servers**, expand **Central Management Servers**.</span></span> <span data-ttu-id="7f4f9-138">Klicken Sie mit der rechten Maustaste auf die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , die im obigen Verfahren hinzugefügt wurde, und wählen Sie **Neue Servergruppe**aus.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-138">Right-click the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] added in the procedure above and select **New Server Group**.</span></span>  
  
2.  <span data-ttu-id="7f4f9-139">Geben Sie in **-Eigenschaften für neue Servergruppe**einen Gruppennamen und ggf. eine Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-139">In **New Server Group Properties**, enter a group name and optional description.</span></span>  
  
3.  <span data-ttu-id="7f4f9-140">Klicken Sie im Fenster **Registrierte Server**mit der rechten Maustaste auf die Servergruppe, und klicken Sie auf **Neue Serverregistrierung**.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-140">From **Registered Servers**, right-click the server group and click **New Server Registration**.</span></span>  
  
4.  <span data-ttu-id="7f4f9-141">Wählen Sie im Fenster "Neue Serverregistrierung" eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aus.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-141">From New Server Registration, select an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7f4f9-142">Weitere Informationen finden Sie unter [Erstellen eines neu registrierten Servers &#40;SQL Server Management Studio&#41;](create-a-new-registered-server-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="7f4f9-142">For more information, see [Create a New Registered Server &#40;SQL Server Management Studio&#41;](create-a-new-registered-server-sql-server-management-studio.md).</span></span> <span data-ttu-id="7f4f9-143">Fügen Sie weitere Server nach Bedarf hinzu.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-143">Add more servers as appropriate.</span></span>  
  
#### <a name="to-execute-queries-against-several-configuration-targets-at-the-same-time"></a><span data-ttu-id="7f4f9-144">So führen Sie Abfragen für mehrere Konfigurationsziele gleichzeitig aus</span><span class="sxs-lookup"><span data-stu-id="7f4f9-144">To execute queries against several configuration targets at the same time</span></span>  
  
-   <span data-ttu-id="7f4f9-145">Nachdem Sie einen zentralen Verwaltungsserver, ein oder mehrere Servergruppen und ein oder mehrere registrierte Server erstellt haben, können Sie Abfragen für die ganze Gruppe gleichzeitig ausführen.</span><span class="sxs-lookup"><span data-stu-id="7f4f9-145">After you create a central management server, one or more server groups, and one or more registered servers, you can execute queries against a whole group at the same time.</span></span> <span data-ttu-id="7f4f9-146">Weitere Informationen zum gleichzeitigen Ausführen von [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisungen auf den Servern in einer Servergruppe finden Sie unter [Gleichzeitiges Ausführen von Anweisungen für mehrere Server &#40;SQL Server Management Studio&#41;](execute-statements-against-multiple-servers-simultaneously.md).</span><span class="sxs-lookup"><span data-stu-id="7f4f9-146">For more information about how to execute [!INCLUDE[tsql](../../includes/tsql-md.md)] statements on the servers in a server group at the same time, see [Execute Statements Against Multiple Servers Simultaneously &#40;SQL Server Management Studio&#41;](execute-statements-against-multiple-servers-simultaneously.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f4f9-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7f4f9-147">See Also</span></span>  
 [<span data-ttu-id="7f4f9-148">Verwalten mehrerer Server mithilfe von zentralen Verwaltungsservern</span><span class="sxs-lookup"><span data-stu-id="7f4f9-148">Administer Multiple Servers Using Central Management Servers</span></span>](../../relational-databases/administer-multiple-servers-using-central-management-servers.md)  
  
  
