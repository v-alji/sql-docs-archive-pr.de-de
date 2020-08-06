---
title: Gleichzeitiges Ausführen von Anweisungen für mehrere Server
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- multiserver queries
- executing queries against multiple servers
- queries [SQL Server], multiserver
ms.assetid: 197760f3-0a06-43de-8162-69c27d3fbe56
author: markingmyname
ms.author: maghan
ms.openlocfilehash: b94775029a1501d3e894d84ef4a027fc1595dc10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717191"
---
# <a name="execute-statements-against-multiple-servers-simultaneously-sql-server-management-studio"></a><span data-ttu-id="8f1c0-102">Gleichzeitiges Ausführen von Anweisungen für mehrere Server (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="8f1c0-102">Execute Statements Against Multiple Servers Simultaneously (SQL Server Management Studio)</span></span>
  <span data-ttu-id="8f1c0-103">In diesem Thema wird beschrieben, wie Sie in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]Abfragen gleichzeitig für mehrere Server durchführen, indem Sie eine lokale Servergruppe oder einen zentralen Verwaltungsserver und eine oder mehrere Servergruppen sowie einen oder mehrere registrierte Server innerhalb der Gruppen erstellen und anschließend eine Abfrage für die ganze Gruppe durchführen.</span><span class="sxs-lookup"><span data-stu-id="8f1c0-103">This topic describes how to query multiple servers at the same time in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], by creating a local server group, or a Central Management Server and one or more server groups, and one or more registered servers within the groups, and then querying the complete group.</span></span> <span data-ttu-id="8f1c0-104">Die von der Abfrage zurückgegebenen Ergebnisse können in einem einzigen Ergebnisbereich zusammengefasst oder in gesonderten Ergebnisbereichen ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8f1c0-104">The results that are returned by the query can be combined into a single results pane, or can be returned in separate results panes.</span></span> <span data-ttu-id="8f1c0-105">Das Resultset kann zusätzliche Spalten für den Servernamen und den Anmeldenamen umfassen, der für die Abfrage auf jedem einzelnen Server verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8f1c0-105">The results set can include additional columns for the server name and the login that is used by the query on each server.</span></span> <span data-ttu-id="8f1c0-106">Zentrale Verwaltungsserver und untergeordnete registrierte Server können nur mithilfe der Windows-Authentifizierung registriert werden.</span><span class="sxs-lookup"><span data-stu-id="8f1c0-106">Central Management Servers and subordinate servers can be registered by using only Windows Authentication.</span></span> <span data-ttu-id="8f1c0-107">Server in lokalen Servergruppen können mithilfe der Windows-Authentifizierung oder der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Authentifizierung registriert werden.</span><span class="sxs-lookup"><span data-stu-id="8f1c0-107">Servers in local server groups can be registered by using Windows Authentication or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8f1c0-108">Bevor Sie die folgenden Schritte ausführen, erstellen Sie einen zentralen Verwaltungsserver und Servergruppen.</span><span class="sxs-lookup"><span data-stu-id="8f1c0-108">Before you execute the following procedures, create a Central Management Server and server groups.</span></span> <span data-ttu-id="8f1c0-109">Weitere Informationen finden Sie unter [Erstellen eines zentralen Verwaltungsservers und einer Servergruppe &#40;SQL Server Management Studio&#41;](create-a-central-management-server-and-server-group.md).</span><span class="sxs-lookup"><span data-stu-id="8f1c0-109">For more information, see [Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;](create-a-central-management-server-and-server-group.md).</span></span>  
  
 <span data-ttu-id="8f1c0-110">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="8f1c0-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8f1c0-111">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="8f1c0-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8f1c0-112">Security</span><span class="sxs-lookup"><span data-stu-id="8f1c0-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8f1c0-113">**Ausführen von Anweisungen für mehrere Server mit:**</span><span class="sxs-lookup"><span data-stu-id="8f1c0-113">**To execute statements against multiple servers, using:**</span></span>  
  
     [<span data-ttu-id="8f1c0-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f1c0-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8f1c0-115">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="8f1c0-115">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8f1c0-116">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8f1c0-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8f1c0-117">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8f1c0-117">Permissions</span></span>  
 <span data-ttu-id="8f1c0-118">Da die durch einen zentralen Verwaltungsserver verwalteten Verbindungen im Kontext des Benutzers unter Verwendung der Windows-Authentifizierung ausgeführt werden, können die gültigen Berechtigungen auf den registrierten Servern variieren.</span><span class="sxs-lookup"><span data-stu-id="8f1c0-118">Because the connections maintained by a Central Management Server execute in the context of the user, by using Windows Authentication, the effective permissions on the registered servers might vary.</span></span> <span data-ttu-id="8f1c0-119">Der Benutzer kann beispielsweise für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz A ein Mitglied der festen Serverrolle sysadmin sein, für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz B jedoch über eingeschränkte Berechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="8f1c0-119">For example, the user might be a member of the sysadmin fixed server role on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] A, but have limited permissions on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] B.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8f1c0-120">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8f1c0-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-execute-statements-against-multiple-configuration-targets-simultaneously"></a><span data-ttu-id="8f1c0-121">So führen Sie Anweisungen gleichzeitig für mehrere Konfigurationsziele aus</span><span class="sxs-lookup"><span data-stu-id="8f1c0-121">To execute statements against multiple configuration targets simultaneously</span></span>  
  
1.  <span data-ttu-id="8f1c0-122">Klicken Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]im Menü **Ansicht** auf **Registrierte Server**.</span><span class="sxs-lookup"><span data-stu-id="8f1c0-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Registered Servers**.</span></span>  
  
2.  <span data-ttu-id="8f1c0-123">Erweitern Sie einen zentralen Verwaltungsserver, klicken Sie mit der rechten Maustaste auf eine Servergruppe, zeigen Sie auf **Verbinden**, und klicken Sie anschließend auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="8f1c0-123">Expand a Central Management Server, right-click a server group, point to **Connect**, and then click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8f1c0-124">Geben Sie im Abfrage-Editor eine [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung ein, und führen Sie sie aus, z. B.:</span><span class="sxs-lookup"><span data-stu-id="8f1c0-124">In Query Editor, type and execute a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, such as the following:</span></span>  
  
    ```  
    USE master  
    GO  
    SELECT * FROM sysdatabases;  
    GO  
    ```  
  
     <span data-ttu-id="8f1c0-125">Standardmäßig werden im Ergebnisbereich die Abfrageergebnisse aller Servern in der Servergruppe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8f1c0-125">By default, the results pane will combine the query results from all the servers in the server group.</span></span>  
  
#### <a name="to-change-the-multiserver-results-options"></a><span data-ttu-id="8f1c0-126">So ändern Sie die Optionen für Multiserverergebnisse</span><span class="sxs-lookup"><span data-stu-id="8f1c0-126">To change the multiserver results options</span></span>  
  
1.  <span data-ttu-id="8f1c0-127">Klicken Sie in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]im Menü **Extras** auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="8f1c0-127">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], on the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="8f1c0-128">Erweitern Sie **Abfrageergebnisse**, erweitern Sie **SQL Server**, und klicken Sie dann auf **Multiserverergebnisse**.</span><span class="sxs-lookup"><span data-stu-id="8f1c0-128">Expand **Query Results**, expand **SQL Server**, and then click **Multiserver Results**.</span></span>  
  
3.  <span data-ttu-id="8f1c0-129">Geben Sie auf der Seite **Multiserverergebnisse** die gewünschten Optionseinstellungen an, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f1c0-129">On the **Multiserver Results** page, specify the option settings that you want, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f1c0-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8f1c0-130">See Also</span></span>  
 [<span data-ttu-id="8f1c0-131">Verwalten mehrerer Server mithilfe von zentralen Verwaltungs Servern</span><span class="sxs-lookup"><span data-stu-id="8f1c0-131">Administer Multiple Servers Using Central Management Servers</span></span>](../../relational-databases/administer-multiple-servers-using-central-management-servers.md)  
  
  
