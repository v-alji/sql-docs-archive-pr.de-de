---
title: Ändern von Check-Einschränkungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- CHECK constraints, modifying
- modifying constraints
- constraints [SQL Server], check
- constraints [SQL Server], modifying
ms.assetid: f22daef8-e350-40ef-8ff0-b5f87d1d9e56
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8377c80590612c8b68c315f7c37823eb8f5c5093
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619031"
---
# <a name="modify-check-constraints"></a><span data-ttu-id="a0a10-102">Ändern von CHECK-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a0a10-102">Modify Check Constraints</span></span>
  <span data-ttu-id="a0a10-103">Sie können eine CHECK-Einschränkung mit [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] in [!INCLUDE[tsql](../../includes/tsql-md.md)] ändern, wenn Sie entweder den Einschränkungsausdruck oder die Optionen ändern möchten, mit denen die Einschränkung unter bestimmten Bedingungen aktiviert bzw. deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="a0a10-103">You can modify a check constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)] when you want to change the constraint expression or the options that enable or disable the constraint for specific conditions.</span></span>  
  
 <span data-ttu-id="a0a10-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="a0a10-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a0a10-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="a0a10-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a0a10-106">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="a0a10-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a0a10-107">**So ändern Sie eine CHECK-Einschränkung mit:**</span><span class="sxs-lookup"><span data-stu-id="a0a10-107">**To modify a check constraint using:**</span></span>  
  
     [<span data-ttu-id="a0a10-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a0a10-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a0a10-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a0a10-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a0a10-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="a0a10-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a0a10-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="a0a10-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a0a10-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="a0a10-112">Permissions</span></span>  
 <span data-ttu-id="a0a10-113">Erfordert die ALTER-Berechtigung für die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a0a10-113">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a0a10-114">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a0a10-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-check-constraint"></a><span data-ttu-id="a0a10-115">So ändern Sie eine CHECK-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="a0a10-115">To modify a check constraint</span></span>  
  
1.  <span data-ttu-id="a0a10-116">Klicken Sie im **Objekt-Explorer**mit der rechten Maustaste auf die Tabelle mit der CHECK-Einschränkung, und wählen Sie dann **Entwerfen**aus.</span><span class="sxs-lookup"><span data-stu-id="a0a10-116">In the **Object Explorer**, right-click the table containing the check constraint and select **Design**.</span></span>  
  
2.  <span data-ttu-id="a0a10-117">Klicken Sie im Menü **Tabellen-Designer** auf **Einschränkungen überprüfen...** .</span><span class="sxs-lookup"><span data-stu-id="a0a10-117">On the **Table Designer** menu, click **Check Constraints...**.</span></span>  
  
3.  <span data-ttu-id="a0a10-118">Wählen Sie im Dialogfeld **CHECK-Einschränkungen** unter **Ausgewählte CHECK-Einschränkung**die Einschränkung aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="a0a10-118">In the **Check Constraints** dialog box, under **Selected Check Constraint**, select the constraint you wish to edit.</span></span>  
  
4.  <span data-ttu-id="a0a10-119">Führen Sie eine Aktion aus der folgenden Tabelle aus:</span><span class="sxs-lookup"><span data-stu-id="a0a10-119">Complete an action from the following table:</span></span>  
  
    |<span data-ttu-id="a0a10-120">To</span><span class="sxs-lookup"><span data-stu-id="a0a10-120">To</span></span>|<span data-ttu-id="a0a10-121">Schritte</span><span class="sxs-lookup"><span data-stu-id="a0a10-121">Follow these steps</span></span>|  
    |--------|------------------------|  
    |<span data-ttu-id="a0a10-122">Ändern des Einschränkungsausdrucks</span><span class="sxs-lookup"><span data-stu-id="a0a10-122">Edit the constraint expression</span></span>|<span data-ttu-id="a0a10-123">Geben Sie im Feld **Ausdruck** den neuen Ausdruck ein.</span><span class="sxs-lookup"><span data-stu-id="a0a10-123">Type the new expression in the **Expression** field.</span></span>|  
    |<span data-ttu-id="a0a10-124">Umbenennen der Einschränkung</span><span class="sxs-lookup"><span data-stu-id="a0a10-124">Rename the constraint</span></span>|<span data-ttu-id="a0a10-125">Geben Sie im Feld **Name** einen neuen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="a0a10-125">Type a new name in the **Name** field.</span></span>|  
    |<span data-ttu-id="a0a10-126">Anwenden der Einschränkung auf die vorhandenen Daten</span><span class="sxs-lookup"><span data-stu-id="a0a10-126">Apply the constraint to existing data</span></span>|<span data-ttu-id="a0a10-127">Aktivieren Sie die Option **Vorhandene Daten bei Erstellung oder Aktivierung überprüfen** .</span><span class="sxs-lookup"><span data-stu-id="a0a10-127">Select the **Check Existing Data on Creation or Enabling** option.</span></span>|  
    |<span data-ttu-id="a0a10-128">Deaktivieren der Einschränkung, wenn der Tabelle neue Daten hinzugefügt werden oder wenn die vorhandenen Daten in der Tabelle aktualisiert werden</span><span class="sxs-lookup"><span data-stu-id="a0a10-128">Disable the constraint when new data is added to the table or when existing data is updated in the table.</span></span>|<span data-ttu-id="a0a10-129">Deaktivieren Sie die Option **Einschränkung für INSERT und UPDATE erzwingen** .</span><span class="sxs-lookup"><span data-stu-id="a0a10-129">Clear the **Enforce Constraint for INSERTs and UPDATEs** option.</span></span>|  
    |<span data-ttu-id="a0a10-130">Deaktivieren Sie die Einschränkung, wenn ein Replikations-Agent Daten in die Tabelle einfügt oder darin aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="a0a10-130">Disable the constraint when a replication agent inserts or updates data in your table.</span></span>|<span data-ttu-id="a0a10-131">Deaktivieren Sie die Option **Für Replikation erzwingen** .</span><span class="sxs-lookup"><span data-stu-id="a0a10-131">Clear the **Enforce For Replication** option.</span></span>|  
  
    > [!NOTE]  
    >  <span data-ttu-id="a0a10-132">Die Funktionsweise der CHECK-Einschränkung kann je nach Datenbank unterschiedlich ausfallen.</span><span class="sxs-lookup"><span data-stu-id="a0a10-132">Some databases have different functionality for check constraints.</span></span>  
  
5.  <span data-ttu-id="a0a10-133">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="a0a10-133">Click **Close**.</span></span>  
  
6.  <span data-ttu-id="a0a10-134">Klicken Sie im Menü **Datei** auf _Tabellenname_**speichern**.</span><span class="sxs-lookup"><span data-stu-id="a0a10-134">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a0a10-135">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a0a10-135">Using Transact-SQL</span></span>  
 <span data-ttu-id="a0a10-136">**So ändern Sie eine CHECK-Einschränkung**</span><span class="sxs-lookup"><span data-stu-id="a0a10-136">**To modify a check constraint**</span></span>  
  
 <span data-ttu-id="a0a10-137">Um eine `CHECK` -Einschränkung mit [!INCLUDE[tsql](../../includes/tsql-md.md)]zu ändern, müssen Sie zuerst die vorhandene `CHECK` -Einschränkung löschen und sie dann mit der neuen Definition neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a0a10-137">To modify a `CHECK` constraint using [!INCLUDE[tsql](../../includes/tsql-md.md)], you must first delete the existing `CHECK` constraint and then re-create it with the new definition.</span></span> <span data-ttu-id="a0a10-138">Weitere Informationen finden Sie unter [Löschen von CHECK-Einschränkungen](delete-check-constraints.md) und [Erstellen von CHECK-Einschränkungen](create-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="a0a10-138">For more information, see [Delete Check Constraints](delete-check-constraints.md) and [Create Check Constraints](create-check-constraints.md).</span></span>  
  
###  <a name="TsqlExample"></a>  
