---
title: Ändern von Primärschlüsseln | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- modifying primary keys
- primary keys [SQL Server], modifying
ms.assetid: 8e2a15ba-1cd1-4408-b860-16c3ee37d635
author: stevestein
ms.author: sstein
ms.openlocfilehash: f24deeac45491f9097d90ee0407464f928a0713b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607595"
---
# <a name="modify-primary-keys"></a><span data-ttu-id="17ab9-102">Ändern von Primärschlüsseln</span><span class="sxs-lookup"><span data-stu-id="17ab9-102">Modify Primary Keys</span></span>
  <span data-ttu-id="17ab9-103">Sie können mit [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] einen Primärschlüssel in [!INCLUDE[tsql](../../includes/tsql-md.md)]ändern.</span><span class="sxs-lookup"><span data-stu-id="17ab9-103">You can modify a primary key in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="17ab9-104">Sie können den Primärschlüssel einer Tabelle ändern, indem Sie die Spaltenreihenfolge, den Indexnamen, die CLUSTERED-Option oder den Füllfaktor bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="17ab9-104">You can modify the primary key of a table by changing the column order, index name, clustered option, or fill factor.</span></span>  
  
 <span data-ttu-id="17ab9-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="17ab9-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="17ab9-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="17ab9-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="17ab9-107">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="17ab9-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="17ab9-108">**So ändern Sie einen Primärschlüssel mit:**</span><span class="sxs-lookup"><span data-stu-id="17ab9-108">**To modify a primary key, using:**</span></span>  
  
     [<span data-ttu-id="17ab9-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="17ab9-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="17ab9-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="17ab9-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="17ab9-111">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="17ab9-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="17ab9-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="17ab9-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="17ab9-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="17ab9-113">Permissions</span></span>  
 <span data-ttu-id="17ab9-114">Erfordert die ALTER-Berechtigung für die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="17ab9-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="17ab9-115">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="17ab9-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-primary-key"></a><span data-ttu-id="17ab9-116">So ändern Sie einen Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="17ab9-116">To modify a primary key</span></span>  
  
1.  <span data-ttu-id="17ab9-117">Öffnen Sie den Tabellen-Designer für die Tabelle, deren Primärschlüssel Sie ändern möchten. Klicken Sie mit der rechten Maustaste auf den Tabellen-Designer, und wählen Sie im Kontextmenü den Befehl **Indizes/Schlüssel** aus.</span><span class="sxs-lookup"><span data-stu-id="17ab9-117">Open the Table Designer for the table whose primary key you want to modify, right-click in the Table Designer, and choose **Indexes/Keys** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="17ab9-118">Wählen Sie im Dialogfeld **Indizes/Schlüssel** aus der Liste **Ausgewählter Primärschlüssel/eindeutiger Schlüssel oder Index** den Primärschlüsselindex aus.</span><span class="sxs-lookup"><span data-stu-id="17ab9-118">In the **Indexes/Keys** dialog box, select the primary key index from the **Selected Primary/Unique Key or Index** list.</span></span>  
  
3.  <span data-ttu-id="17ab9-119">Führen Sie eine Aktion aus der folgenden Tabelle aus:</span><span class="sxs-lookup"><span data-stu-id="17ab9-119">Complete an action from the following table:</span></span>  
  
    |<span data-ttu-id="17ab9-120">To</span><span class="sxs-lookup"><span data-stu-id="17ab9-120">To</span></span>|<span data-ttu-id="17ab9-121">Schritte</span><span class="sxs-lookup"><span data-stu-id="17ab9-121">Follow these steps</span></span>|  
    |--------|------------------------|  
    |<span data-ttu-id="17ab9-122">Umbenennen des Primärschlüssels</span><span class="sxs-lookup"><span data-stu-id="17ab9-122">Rename the primary key</span></span>|<span data-ttu-id="17ab9-123">Geben Sie im Feld **Name** einen neuen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="17ab9-123">Type a new name in the **Name** box.</span></span> <span data-ttu-id="17ab9-124">Vergewissern Sie sich, dass der neue Name in der Liste **Ausgewählter Primärschlüssel/eindeutiger Schlüssel oder Index** nicht bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="17ab9-124">Make sure that your new name does not duplicate a name in the **Selected Primary/Unique Key or Index** list.</span></span>|  
    |<span data-ttu-id="17ab9-125">Festlegen der CLUSTERED-Option</span><span class="sxs-lookup"><span data-stu-id="17ab9-125">Set the clustered option</span></span>|<span data-ttu-id="17ab9-126">Um einen gruppierten Index für den Primärschlüssel zu erstellen, wählen Sie **Als CLUSTERED erstellen**aus, und wählen Sie die Option im Dropdown-Listenfeld aus.</span><span class="sxs-lookup"><span data-stu-id="17ab9-126">To create a clustered index for the primary key, select **Create as CLUSTERED**, and select the option from the drop-down list box.</span></span> <span data-ttu-id="17ab9-127">In jeder Tabelle darf nur ein gruppierter Index vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="17ab9-127">Only one clustered index can exist per table.</span></span> <span data-ttu-id="17ab9-128">Wenn diese Option für einen Index nicht verfügbar ist, müssen Sie zunächst diese Einstellung für den vorhandenen gruppierten Index deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="17ab9-128">If this option is not available for your index, you must first clear this setting on the existing clustered index.</span></span><br /><br /> <span data-ttu-id="17ab9-129">Wenn diese Option nicht aktiviert wird, wird ein eindeutiger nicht gruppierter Index erstellt.</span><span class="sxs-lookup"><span data-stu-id="17ab9-129">If this option is not selected, a unique nonclustered index is created.</span></span>|  
    |<span data-ttu-id="17ab9-130">Definieren eines Füllfaktors</span><span class="sxs-lookup"><span data-stu-id="17ab9-130">Define a fill factor</span></span>|<span data-ttu-id="17ab9-131">Erweitern Sie die Kategorie **Füllspezifikation** , und geben Sie im Feld **Füllfaktor** einen ganzzahligen Wert zwischen 0 und 100 ein.</span><span class="sxs-lookup"><span data-stu-id="17ab9-131">Expand the **Fill Specification** category and type an integer from 0 to 100 in the **Fill factor** box.</span></span> <span data-ttu-id="17ab9-132">Weitere Informationen über Füllfaktoren und deren Verwendung finden Sie unter [Angeben des Füllfaktors für einen Index](../indexes/specify-fill-factor-for-an-index.md).</span><span class="sxs-lookup"><span data-stu-id="17ab9-132">For more information about fill factors and their uses, see [Specify Fill Factor for an Index](../indexes/specify-fill-factor-for-an-index.md).</span></span>|  
    |<span data-ttu-id="17ab9-133">Ändern der Spaltenreihenfolge</span><span class="sxs-lookup"><span data-stu-id="17ab9-133">Change the column order</span></span>|<span data-ttu-id="17ab9-134">Wählen Sie **Spalten** aus, und klicken Sie dann auf die Auslassungspunkte **(…)** rechts neben der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="17ab9-134">Select **Columns**, and then click the ellipses **(...)** to the right of the property.</span></span> <span data-ttu-id="17ab9-135">Entfernen Sie im Dialogfeld  **Indexspalten** die Spalten aus dem Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="17ab9-135">In the  **Index Columns** dialog box, remove the columns from the primary key.</span></span> <span data-ttu-id="17ab9-136">Fügen Sie die Spalten in der gewünschten Reihenfolge wieder ein.</span><span class="sxs-lookup"><span data-stu-id="17ab9-136">Then add the columns back in the order you want.</span></span> <span data-ttu-id="17ab9-137">Zum Entfernen einer Spalte aus dem Schlüssel können Sie den Spaltennamen einfach aus der Namensliste der **Spalten** entfernen.</span><span class="sxs-lookup"><span data-stu-id="17ab9-137">To remove a column from the key, simply remove the column name from the **Column** name list.</span></span>|  
  
4.  <span data-ttu-id="17ab9-138">Klicken Sie im Menü **Datei** auf _Tabellenname_**speichern**.</span><span class="sxs-lookup"><span data-stu-id="17ab9-138">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="17ab9-139">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="17ab9-139">Using Transact-SQL</span></span>  
 <span data-ttu-id="17ab9-140">**So ändern Sie einen Primärschlüssel**</span><span class="sxs-lookup"><span data-stu-id="17ab9-140">**To modify a primary key**</span></span>  
  
 <span data-ttu-id="17ab9-141">Um eine PRIMARY KEY-Einschränkung mit Transact-SQLzu ändern, müssen Sie zuerst die vorhandene PRIMARY KEY-Einschränkung löschen und sie dann mit der neuen Definition neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="17ab9-141">To modify a PRIMARY KEY constraint using Transact-SQL, you must first delete the existing PRIMARY KEY constraint and then re-create it with the new definition.</span></span> <span data-ttu-id="17ab9-142">Weitere Informationen finden Sie unter [Delete Primary Keys](delete-primary-keys.md) und [Create Primary Keys](create-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="17ab9-142">For more information, see [Delete Primary Keys](delete-primary-keys.md) and [Create Primary Keys](create-primary-keys.md).</span></span>  
  
###  <a name="TsqlExample"></a>  
