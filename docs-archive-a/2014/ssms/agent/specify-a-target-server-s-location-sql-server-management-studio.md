---
title: Geben Sie einen Ziel Server&#39;s-Speicherort an (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- target servers [SQL Server], location
ms.assetid: 511ff311-21f5-4f2f-839f-b4deee26ec98
author: stevestein
ms.author: sstein
ms.openlocfilehash: 938528ab78f0f457cde69d8fd4d5432cc14a79b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620105"
---
# <a name="specify-a-target-server39s-location-sql-server-management-studio"></a><span data-ttu-id="7d927-102">Angeben eines Zielserverstandorts r&#39;s (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="7d927-102">Specify a Target Server&#39;s Location (SQL Server Management Studio)</span></span>
  <span data-ttu-id="7d927-103">In diesem Thema wird beschrieben, wie Sie den Speicherort eines Zielservers in einer Multiserververwaltungskonfiguration in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]angeben können.</span><span class="sxs-lookup"><span data-stu-id="7d927-103">This topic describes how to specify the location of a target server in a multiserver administration configuration in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7d927-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="7d927-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7d927-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="7d927-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7d927-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="7d927-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="7d927-107">Security</span><span class="sxs-lookup"><span data-stu-id="7d927-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7d927-108">**So geben Sie den Speicherort eines Zielservers an mit**</span><span class="sxs-lookup"><span data-stu-id="7d927-108">**To specify a target server's location, using:**</span></span>  
  
     [<span data-ttu-id="7d927-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7d927-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7d927-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7d927-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7d927-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="7d927-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="7d927-112">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="7d927-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="7d927-113">Wenn diese Aktion ausgeführt wird, wird die Registrierung bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="7d927-113">Performing this action edits the registry.</span></span> <span data-ttu-id="7d927-114">Die Registrierung sollte nicht manuell bearbeitet werden, da durch ungeeignete oder fehlerhafte Änderungen schwerwiegende Konfigurationsprobleme auf dem System verursacht werden können.</span><span class="sxs-lookup"><span data-stu-id="7d927-114">Manual editing of the registry is not recommended because inappropriate or incorrect changes can cause serious configuration problems for your system.</span></span> <span data-ttu-id="7d927-115">Nur erfahrene Benutzer sollten deshalb den Registrierungs-Editor zum Bearbeiten der Registrierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d927-115">Therefore, only experienced users should use the Registry Editor program to edit the registry.</span></span> <span data-ttu-id="7d927-116">Weitere Informationen finden Sie in der Dokumentation zu Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="7d927-116">For more information, see the Microsoft Windows documentation.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7d927-117">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7d927-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7d927-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="7d927-118">Permissions</span></span>  
 <span data-ttu-id="7d927-119">Erfordert die Mitgliedschaft in der festen Serverrolle **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="7d927-119">Requires membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7d927-120">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7d927-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-a-target-servers-location"></a><span data-ttu-id="7d927-121">So geben Sie den Speicherort eines Zielservers an</span><span class="sxs-lookup"><span data-stu-id="7d927-121">To specify a target server's location</span></span>  
  
1.  <span data-ttu-id="7d927-122">Klicken Sie im **Objekt-Explorer** auf das Pluszeichen, um den Masterserver zu erweitern, auf dem Sie den Speicherort des Zielservers angeben möchten.</span><span class="sxs-lookup"><span data-stu-id="7d927-122">In **Object Explorer**, click the plus sign to expand the master server on which you want to specify a target server's location.</span></span>  
  
2.  <span data-ttu-id="7d927-123">Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent**, zeigen Sie auf **Multiserververwaltung**, und klicken Sie auf **Zielserver verwalten**.</span><span class="sxs-lookup"><span data-stu-id="7d927-123">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and select **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="7d927-124">Klicken Sie mit der rechten Maustaste auf den Zielserver, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="7d927-124">Right-click a target server and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="7d927-125">Geben Sie in das Feld **Speicherort** einen Speicherort für den Server ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7d927-125">In the **Location** box, enter a location for the server, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7d927-126">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7d927-126">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-a-target-servers-location"></a><span data-ttu-id="7d927-127">So geben Sie den Speicherort eines Zielservers an</span><span class="sxs-lookup"><span data-stu-id="7d927-127">To specify a target server's location</span></span>  
  
1.  <span data-ttu-id="7d927-128">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="7d927-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7d927-129">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="7d927-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7d927-130">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7d927-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb ;  
    GO  
    -- enlists the current server into the AdventureWorks1 master server.   
    -- The location for the current server is Building 21, Room 309, Rack 5  
    EXEC dbo.sp_msx_enlist N'AdventureWorks2012',   
        N'Building 21, Room 309, Rack 5' ;  
    GO  
    ```  
  
 <span data-ttu-id="7d927-131">Weitere Informationen finden Sie unter [sp_msx_enlist &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7d927-131">For more information, see [sp_msx_enlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-enlist-transact-sql).</span></span>  
  
  
