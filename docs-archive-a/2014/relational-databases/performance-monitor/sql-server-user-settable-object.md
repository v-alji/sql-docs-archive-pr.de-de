---
title: SQL Server, Benutzerdefinierbar-Objekt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- User Settable object
- SQLServer:User Settable
ms.assetid: 633de3ef-533c-4f0c-9c7b-c105129d8e94
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7243ab4767c8de93dccf4556f136a94b47554d3d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696750"
---
# <a name="sql-server-user-settable-object"></a><span data-ttu-id="0f6d5-102">SQL Server, Benutzerdefinierbar-Objekt</span><span class="sxs-lookup"><span data-stu-id="0f6d5-102">SQL Server, User Settable Object</span></span>
  <span data-ttu-id="0f6d5-103">Das **Benutzerdefinierbar** -Objekt in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ermöglicht Ihnen das Erstellen von benutzerdefinierten Leistungsindikatorinstanzen.</span><span class="sxs-lookup"><span data-stu-id="0f6d5-103">The **User Settable** object in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] allows you to create custom counter instances.</span></span> <span data-ttu-id="0f6d5-104">Verwenden Sie benutzerdefinierte Leistungsindikatorinstanzen zum Überwachen von Aspekten des Servers, die nicht von vorhandenen Leistungsindikatoren überwacht werden. Beispielsweise Komponenten, die ausschließlich in Ihrer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank vorkommen (z. B. für die Anzahl der protokollierten Kundenbestellungen oder das Produktverzeichnis).</span><span class="sxs-lookup"><span data-stu-id="0f6d5-104">Use custom counter instances to monitor aspects of the server not monitored by existing counters, such as components unique to your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database (for example, the number of customer orders logged or the product inventory).</span></span>  
  
 <span data-ttu-id="0f6d5-105">Das **User Settable**-Objekt enthält zehn Instanzen des Abfragezählers: **Benutzerzähler 1** bis **Benutzerzähler 10**.</span><span class="sxs-lookup"><span data-stu-id="0f6d5-105">The **User Settable** object contains 10 instances of the query counter: **User counter 1** through **User counter 10**.</span></span> <span data-ttu-id="0f6d5-106">Diese Leistungsindikatoren werden den gespeicherten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Prozeduren **sp_user_counter1** bis **sp_user_counter10**zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="0f6d5-106">These counters map to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures **sp_user_counter1** through **sp_user_counter10**.</span></span> <span data-ttu-id="0f6d5-107">Da diese gespeicherten Prozeduren von Benutzeranwendungen ausgeführt werden, werden die von den gespeicherten Prozeduren festgelegten Werte im Systemmonitor angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f6d5-107">As these stored procedures are executed by user applications, the values set by the stored procedures are displayed in System Monitor.</span></span> <span data-ttu-id="0f6d5-108">Ein Leistungsindikator kann einen einzelnen ganzzahligen Wert überwachen, wie z. B. eine gespeicherte Prozedur, die zählt, wie viele Bestellungen für ein bestimmtes Produkt an einem Tag eingegangen sind.</span><span class="sxs-lookup"><span data-stu-id="0f6d5-108">A counter can monitor any single integer value (for example, a stored procedure that counts how many orders for a particular product have occurred in one day).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0f6d5-109">Die gespeicherten Benutzerleistungsindikator-Prozeduren werden nicht automatisch vom Systemmonitor abgerufen.</span><span class="sxs-lookup"><span data-stu-id="0f6d5-109">The user counter stored procedures are not polled automatically by System Monitor.</span></span> <span data-ttu-id="0f6d5-110">Sie müssen explizit von einer Benutzeranwendung ausgeführt werden, damit die Leistungsindikatorwerte aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="0f6d5-110">They must be explicitly executed by a user application for the counter values to be updated.</span></span> <span data-ttu-id="0f6d5-111">Verwenden Sie einen Trigger für das automatische Update des Leistungsindikatorwerts.</span><span class="sxs-lookup"><span data-stu-id="0f6d5-111">Use a trigger to update the value of the counter automatically.</span></span> <span data-ttu-id="0f6d5-112">Wenn Sie z. B. einen Leistungsindikator erstellen möchten, der die Anzahl von Zeilen in einer Tabelle überwacht, erstellen Sie einen INSERT- und DELETE-Trigger für die Tabelle, der folgende Anweisung ausführt: `SELECT COUNT(*) FROM table`.</span><span class="sxs-lookup"><span data-stu-id="0f6d5-112">For example, to create a counter that monitors the number of rows in a table, create an INSERT and DELETE trigger on the table that executes the following statement: `SELECT COUNT(*) FROM table`.</span></span> <span data-ttu-id="0f6d5-113">Wenn der Trigger aufgrund einer INSERT- oder DELETE-Operation in der Tabelle ausgelöst wird, wird der Leistungsindikator des Systemmonitors automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="0f6d5-113">Whenever the trigger is fired because of an INSERT or DELETE operation occurring on the table, the System Monitor counter is automatically updated.</span></span>  
  
 <span data-ttu-id="0f6d5-114">In dieser Tabelle wird das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Objekt **Benutzerdefinierbar** beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0f6d5-114">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **User Settable** object.</span></span>  
  
|<span data-ttu-id="0f6d5-115">Benutzerdefinierbar-Leistungsindikatoren von SQL Server</span><span class="sxs-lookup"><span data-stu-id="0f6d5-115">SQL Server User Settable counters</span></span>|<span data-ttu-id="0f6d5-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0f6d5-116">Description</span></span>|  
|---------------------------------------|-----------------|  
|<span data-ttu-id="0f6d5-117">**Abfrage**</span><span class="sxs-lookup"><span data-stu-id="0f6d5-117">**Query**</span></span>|<span data-ttu-id="0f6d5-118">Das **Benutzerdefinierbar** -Objekt enthält den Abfrageleistungsindikator.</span><span class="sxs-lookup"><span data-stu-id="0f6d5-118">The **User Settable** object contains the query counter.</span></span> <span data-ttu-id="0f6d5-119">Die Benutzer konfigurieren die **User counter** innerhalb des Abfrageobjekts.</span><span class="sxs-lookup"><span data-stu-id="0f6d5-119">Users configure the **User counters** within the query object.</span></span>|  
  
 <span data-ttu-id="0f6d5-120">In dieser Tabelle werden die **Instanzen** des **Abfrage** -Leistungsindikators beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0f6d5-120">This table describes the **instances** of the **Query** counter.</span></span>  
  
|<span data-ttu-id="0f6d5-121">Instanzen des Abfrageleistungsindikators</span><span class="sxs-lookup"><span data-stu-id="0f6d5-121">Query counter instances</span></span>|<span data-ttu-id="0f6d5-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0f6d5-122">Description</span></span>|  
|-----------------------------|-----------------|  
|<span data-ttu-id="0f6d5-123">**Benutzerindikator 1**</span><span class="sxs-lookup"><span data-stu-id="0f6d5-123">**User counter 1**</span></span>|<span data-ttu-id="0f6d5-124">Definiert mithilfe von **sp_user_counter1**.</span><span class="sxs-lookup"><span data-stu-id="0f6d5-124">Defined using **sp_user_counter1**.</span></span>|  
|<span data-ttu-id="0f6d5-125">**User counter 2**</span><span class="sxs-lookup"><span data-stu-id="0f6d5-125">**User counter 2**</span></span>|<span data-ttu-id="0f6d5-126">Definiert mithilfe von **sp_user_counter2**.</span><span class="sxs-lookup"><span data-stu-id="0f6d5-126">Defined using **sp_user_counter2**.</span></span>|  
|<span data-ttu-id="0f6d5-127">**User counter 3**</span><span class="sxs-lookup"><span data-stu-id="0f6d5-127">**User counter 3**</span></span>|<span data-ttu-id="0f6d5-128">Definiert mithilfe von **sp_user_counter3**.</span><span class="sxs-lookup"><span data-stu-id="0f6d5-128">Defined using **sp_user_counter3**.</span></span>|  
|<span data-ttu-id="0f6d5-129">...</span><span class="sxs-lookup"><span data-stu-id="0f6d5-129">...</span></span>||  
|<span data-ttu-id="0f6d5-130">**Benutzerindikator 10**</span><span class="sxs-lookup"><span data-stu-id="0f6d5-130">**User counter 10**</span></span>|<span data-ttu-id="0f6d5-131">Definiert mithilfe von **sp_user_counter10**.</span><span class="sxs-lookup"><span data-stu-id="0f6d5-131">Defined using **sp_user_counter10**.</span></span>|  
  
 <span data-ttu-id="0f6d5-132">Wenn Sie die gespeicherten Benutzerleistungsindikator-Prozeduren verwenden möchten, führen Sie sie von Ihrer eigenen Anwendung mit einem einzelnen ganzzahligen Parameter, der den neuen Wert für den Leistungsindikator darstellt, aus.</span><span class="sxs-lookup"><span data-stu-id="0f6d5-132">To make use of the user counter stored procedures, execute them from your own application with a single integer parameter representing the new value for the counter.</span></span> <span data-ttu-id="0f6d5-133">Um beispielsweise den Wert 10 für **User counter 1** festzulegen, führen Sie die folgende Transact-SQL-Anweisung aus:</span><span class="sxs-lookup"><span data-stu-id="0f6d5-133">For example, to set **User counter 1** to the value 10, execute this Transact-SQL statement:</span></span>  
  
```  
EXECUTE sp_user_counter1 10  
```  
  
 <span data-ttu-id="0f6d5-134">Die gespeicherten Benutzerleistungsindikator-Prozeduren können von jeder beliebigen Stelle aufgerufen werden, von der andere gespeicherte Prozeduren, wie etwa Ihre eigenen gespeicherten Prozeduren, auch aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="0f6d5-134">The user counter stored procedures can be called from anywhere other stored procedures can be called, such as your own stored procedures.</span></span> <span data-ttu-id="0f6d5-135">Sie können beispielsweise die folgende gespeicherte Prozedur erstellen, um die Anzahl von Verbindungen und Verbindungsversuchen seit dem Starten einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zu zählen:</span><span class="sxs-lookup"><span data-stu-id="0f6d5-135">For example, you can create the following stored procedure to count the number of connections and attempted connections since an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] was started:</span></span>  
  
```  
DROP PROC My_Proc  
GO  
CREATE PROC My_Proc  
AS   
   EXECUTE sp_user_counter1 @@CONNECTIONS  
GO  
```  
  
 <span data-ttu-id="0f6d5-136">Die @@CONNECTIONS-Funktion gibt die Anzahl von Verbindungen und Verbindungsversuchen seit dem Starten einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zurück.</span><span class="sxs-lookup"><span data-stu-id="0f6d5-136">The @@CONNECTIONS function returns the number of connections or attempted connections since an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] started.</span></span> <span data-ttu-id="0f6d5-137">Dieser Wert wird an die gespeicherte Prozedur **sp_user_counter1** als Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="0f6d5-137">This value is passed to the **sp_user_counter1** stored procedure as the parameter.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0f6d5-138">Die in den gespeicherten Benutzerleistungsindikator-Prozeduren definierten Abfragen sollten so einfach wie möglich sein.</span><span class="sxs-lookup"><span data-stu-id="0f6d5-138">Make the queries defined in the user counter stored procedures as simple as possible.</span></span> <span data-ttu-id="0f6d5-139">Arbeitsspeicherintensive Abfragen mit umfangreichen Sortier- oder Hashvorgängen oder Abfragen, die viele E/A-Vorgänge ausführen, sind bezüglich der Ausführung aufwendig und können die Leistung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="0f6d5-139">Memory-intensive queries that perform substantial sort or hash operations or queries that perform large amounts of I/O are expensive to execute and can impact performance.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="0f6d5-140">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="0f6d5-140">Permissions</span></span>  
 <span data-ttu-id="0f6d5-141">**sp_user_counter** ist für alle Benutzer verfügbar, kann jedoch für jeden Abfrageleistungsindikator eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="0f6d5-141">**sp_user_counter** is available for all users but can be restricted for any query counter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f6d5-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0f6d5-142">See Also</span></span>  
 [<span data-ttu-id="0f6d5-143">Überwachen der Ressourcenverwendung &#40;Systemmonitor&#41;</span><span class="sxs-lookup"><span data-stu-id="0f6d5-143">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
