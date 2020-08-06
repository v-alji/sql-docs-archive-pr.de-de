---
title: Ändern von Unique-Einschränkungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- modifying constraints
- UNIQUE constraints [SQL Server], modifying
- constraints [SQL Server], modifying
- constraints [SQL Server], unique
ms.assetid: fddbdc9e-958b-4614-8e88-6ca205d64a4e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 74b044202f7e8e9bc762f025833cf2d0ff84c4c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630587"
---
# <a name="modify-unique-constraints"></a><span data-ttu-id="160b3-102">Ändern von UNIQUE-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="160b3-102">Modify Unique Constraints</span></span>
  <span data-ttu-id="160b3-103">Sie können mit [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] eine UNIQUE-Einschränkung in [!INCLUDE[tsql](../../includes/tsql-md.md)]ändern.</span><span class="sxs-lookup"><span data-stu-id="160b3-103">You can modify a unique constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="160b3-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="160b3-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="160b3-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="160b3-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="160b3-106">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="160b3-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="160b3-107">**So ändern Sie eine UNIQUE-Einschränkung mit:**</span><span class="sxs-lookup"><span data-stu-id="160b3-107">**To modify a unique constraint using:**</span></span>  
  
     [<span data-ttu-id="160b3-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="160b3-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="160b3-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="160b3-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="160b3-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="160b3-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="160b3-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="160b3-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="160b3-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="160b3-112">Permissions</span></span>  
 <span data-ttu-id="160b3-113">Erfordert die ALTER-Berechtigung für die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="160b3-113">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="160b3-114">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="160b3-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-unique-constraint"></a><span data-ttu-id="160b3-115">So ändern Sie eine UNIQUE-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="160b3-115">To modify a unique constraint</span></span>  
  
1.  <span data-ttu-id="160b3-116">Klicken Sie im **Objekt-Explorer**mit der rechten Maustaste auf die Tabelle mit der UNIQUE-Einschränkung, und wählen Sie dann **Entwerfen**aus.</span><span class="sxs-lookup"><span data-stu-id="160b3-116">In the **Object Explorer**, right-click the table containing the unique constraint and select **Design**.</span></span>  
  
2.  <span data-ttu-id="160b3-117">Klicken Sie im Menü **Tabellen-Designer** auf **Indizes/Schlüssel...** .</span><span class="sxs-lookup"><span data-stu-id="160b3-117">On the **Table Designer** menu, click **Indexes/Keys...**.</span></span>  
  
3.  <span data-ttu-id="160b3-118">Wählen Sie im Dialogfeld **Indizes/Schlüssel** unter **Ausgewählter Primärschlüssel/eindeutiger Schlüssel oder Index**die Einschränkung aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="160b3-118">In the **Indexes/Keys** dialog box, under **Selected Primary/Unique Key or Index**, select the constraint you wish to edit.</span></span>  
  
4.  <span data-ttu-id="160b3-119">Führen Sie eine Aktion aus der folgenden Tabelle aus:</span><span class="sxs-lookup"><span data-stu-id="160b3-119">Complete an action from the following table:</span></span>  
  
    |<span data-ttu-id="160b3-120">To</span><span class="sxs-lookup"><span data-stu-id="160b3-120">To</span></span>|<span data-ttu-id="160b3-121">Schritte</span><span class="sxs-lookup"><span data-stu-id="160b3-121">Follow these steps</span></span>|  
    |--------|------------------------|  
    |<span data-ttu-id="160b3-122">Ändern der Spalten, denen die Einschränkung zugewiesen ist</span><span class="sxs-lookup"><span data-stu-id="160b3-122">Change the columns that the constraint is associated with</span></span>|<span data-ttu-id="160b3-123">1.) Klicken Sie im Raster unter **Allgemein** auf **Spalten** und anschließend auf die Auslassungspunkten **(...)** rechts neben der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="160b3-123">1) In the grid under **(General)**, click **Columns** and then click the ellipses **(...)** to the right of the property.</span></span><br /><br /> <span data-ttu-id="160b3-124">2.) Geben Sie im Dialogfeld **Indexspalten** die neue Spalte oder die Sortierreihenfolge oder beides für den Index an.</span><span class="sxs-lookup"><span data-stu-id="160b3-124">2) In the **Index Columns** dialog box, specify the new column or sort order or both for the index.</span></span>|  
    |<span data-ttu-id="160b3-125">Umbenennen der Einschränkung</span><span class="sxs-lookup"><span data-stu-id="160b3-125">Rename the constraint</span></span>|<span data-ttu-id="160b3-126">Geben Sie im Raster unter **Identität**im Feld **Name** einen neuen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="160b3-126">In the grid under **Identity**, type a new name in the **Name** box.</span></span> <span data-ttu-id="160b3-127">Vergewissern Sie sich, dass der neue Name in der Liste **Ausgewählter Primärschlüssel/eindeutiger Schlüssel oder Index** nicht bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="160b3-127">Make sure that your new name does not duplicate a name in the **Selected Primary/Unique Key or Index** list.</span></span>|  
    |<span data-ttu-id="160b3-128">Festlegen der CLUSTERED-Option</span><span class="sxs-lookup"><span data-stu-id="160b3-128">Set the clustered option</span></span>|<span data-ttu-id="160b3-129">Wählen Sie im Raster unter **Tabellen-Designer** die Option **Als CLUSTERED erstellen** und in der Dropdownliste „Ja“ aus, um einen gruppierten Index zu erstellen, und „Nein“, um einen nicht gruppierten Index zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="160b3-129">In the grid under **Table Designer**, select **Create As Clustered** and from the dropdown choose Yes to create a clustered index and No to create a nonclustered one.</span></span> <span data-ttu-id="160b3-130">In jeder Tabelle darf nur ein gruppierter Index vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="160b3-130">Only one clustered index can exist per table.</span></span> <span data-ttu-id="160b3-131">Wenn in der Tabelle bereits ein gruppierter Index vorhanden ist, müssen Sie diese Einstellung zunächst für den ursprünglichen Index deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="160b3-131">If a clustered index already exists in this table, you must clear this setting on the original index.</span></span>|  
    |<span data-ttu-id="160b3-132">Definieren eines Füllfaktors</span><span class="sxs-lookup"><span data-stu-id="160b3-132">Define a fill factor</span></span>|<span data-ttu-id="160b3-133">Erweitern Sie im Raster unter **Tabellen-Designer**die Kategorie **Füllspezifikation** , und geben Sie im Feld **Füllfaktor** eine ganze Zahl zwischen 0 und 100 ein.</span><span class="sxs-lookup"><span data-stu-id="160b3-133">In the grid under **Table Designer**, expand the **Fill Specification** category and type an integer from 0 to 100 in the **Fill Factor** box.</span></span>|  
  
5.  <span data-ttu-id="160b3-134">Klicken Sie im Menü **Datei** auf _Tabellenname_**speichern**.</span><span class="sxs-lookup"><span data-stu-id="160b3-134">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="to-modify-a-unique-constraint"></a><a name="TsqlProcedure"></a> <span data-ttu-id="160b3-135">**Ändern einer UNIQUE-Einschränkung**</span><span class="sxs-lookup"><span data-stu-id="160b3-135">**To modify a unique constraint**</span></span>  
  
 <span data-ttu-id="160b3-136">Um eine UNIQUE-Einschränkung mit Transact-SQL ändern zu können, müssen Sie zuerst die vorhandene UNIQUE-Einschränkung löschen und sie dann mit der neuen Definition neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="160b3-136">To modify a UNIQUE constraint using Transact-SQL, you must first delete the existing UNIQUE constraint and then re-create it with the new definition.</span></span> <span data-ttu-id="160b3-137">Weitere Informationen finden Sie unter [Delete Unique Constraints](delete-unique-constraints.md) und [Create Unique Constraints](create-unique-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="160b3-137">For more information, see [Delete Unique Constraints](delete-unique-constraints.md) and [Create Unique Constraints](create-unique-constraints.md).</span></span>  
  
###  <a name="TsqlExample"></a>  
