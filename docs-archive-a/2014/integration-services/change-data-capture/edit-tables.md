---
title: Bearbeiten von Tabellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- tabProps
ms.assetid: fed8fada-2abc-45e2-8228-0656f9c599cb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8e8058a0c3e8b81814283f055e4c4ac2b08dd2fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608789"
---
# <a name="edit-tables"></a><span data-ttu-id="dba91-102">Bearbeiten von Tabellen</span><span class="sxs-lookup"><span data-stu-id="dba91-102">Edit Tables</span></span>
  <span data-ttu-id="dba91-103">Verwenden Sie die Registerkarte **Tabellen** , um Änderungen an den Tabellen und Spalten vorzunehmen, die Sie in der Oracle-Quelldatenbank ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="dba91-103">Use the **Tables** tab to make changes to the tables and columns that you selected from the Oracle source database.</span></span> <span data-ttu-id="dba91-104">Diese Registerkarte verfügt über die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="dba91-104">This tab has the following elements:</span></span>  
  
 <span data-ttu-id="dba91-105">**Liste 'Tabelle'**</span><span class="sxs-lookup"><span data-stu-id="dba91-105">**Table list**</span></span>  
 <span data-ttu-id="dba91-106">Die Tabellenliste enthält drei Spalten:</span><span class="sxs-lookup"><span data-stu-id="dba91-106">The table list has three columns:</span></span>  
  
-   <span data-ttu-id="dba91-107">**Oracle Table Name**: Der Name der Tabelle, einschließlich des Tabellenschemas.</span><span class="sxs-lookup"><span data-stu-id="dba91-107">**Oracle Table Name**: The name of the table, including the table schema.</span></span>  
  
-   <span data-ttu-id="dba91-108">**Capture Instance:** Der Name der Aufzeichnungsinstanz, die für die Benennung der instanzspezifischen Change Data Capture-Objekte verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dba91-108">**Capture Instance**: The name of the capture instance used to name instance-specific change data capture objects.</span></span> <span data-ttu-id="dba91-109">Die Aufzeichnungsinstanz darf nicht NULL sein.</span><span class="sxs-lookup"><span data-stu-id="dba91-109">The capture instance cannot be NULL.</span></span> <span data-ttu-id="dba91-110">Wenn der Name nicht angegeben ist, wird er vom Namen des Quellschemas sowie vom Namen der Quelltabelle im Format `<schema-name>_<table-name>.` abgeleitet. Der Name der Aufzeichnungsinstanz darf maximal 100 Zeichen umfassen und muss innerhalb der Datenbank eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="dba91-110">If not specified, the name is derived from the source schema name plus the source table name in the format `<schema-name>_<table-name>.` The capture instance name cannot exceed 100 characters and must be unique within the database.</span></span> <span data-ttu-id="dba91-111">Sie können in dieser Spalte in jede Zelle klicken, um die **capture_instance**manuell zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="dba91-111">You can click in any cell in this column to manually edit the **capture_instance**.</span></span>  
  
-   <span data-ttu-id="dba91-112">**Security Role**: Der Name der Datenbankrolle, mit deren Hilfe der Zugriff auf die Änderungsdaten erlangt wird.</span><span class="sxs-lookup"><span data-stu-id="dba91-112">**Security Role**: The name of the database role used to gain access to change data.</span></span> <span data-ttu-id="dba91-113">Sie können in dieser Spalte in jede Zelle klicken, um die **security_role**manuell zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="dba91-113">You can click in any cell in this column to manually edit the **security_role**.</span></span>  
  
 <span data-ttu-id="dba91-114">**Tabellen hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="dba91-114">**Add Tables**</span></span>  
 <span data-ttu-id="dba91-115">Klicken Sie auf **Tabellen hinzufügen** , um das Dialogfeld „Tabellenauswahl“ zu öffnen und den Schritt [Hinzufügen von Tabellen zu einer CDC-Instanz](add-tables-to-a-cdc-instance.md)auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dba91-115">Click **Add Tables** to open the Table Selection dialog box where you can [Add Tables to a CDC Instance](add-tables-to-a-cdc-instance.md).</span></span> <span data-ttu-id="dba91-116">Bei der ersten Sitzung, bei der Sie auf die Oracle-Datenbank zugreifen, müssen Sie den Schritt [Connect to Oracle](connect-to-oracle.md)ausführen.</span><span class="sxs-lookup"><span data-stu-id="dba91-116">The first time this session that you access the Oracle database, you must [Connect to Oracle](connect-to-oracle.md).</span></span>  
  
 <span data-ttu-id="dba91-117">**Bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="dba91-117">**Edit**</span></span>  
 <span data-ttu-id="dba91-118">Wählen Sie in der Liste eine Tabelle aus, und wählen Sie **Bearbeiten** aus, um das Dialogfeld **Eigenschaften** für die Tabelle zu öffnen, in dem Sie den Schritt [Bearbeiten der Tabelleneigenschaften](edit-the-table-properties.md)ausführen können.</span><span class="sxs-lookup"><span data-stu-id="dba91-118">Select a table from the list and select **Edit** to open the **Properties** dialog box for that table where you can [Edit the Table Properties](edit-the-table-properties.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dba91-119">Sie können die Typzuordnung nicht für Tabellen bearbeiten, die bereits über Spiegeltabellen verfügen.</span><span class="sxs-lookup"><span data-stu-id="dba91-119">You cannot edit type mapping for tables that already have mirror tables.</span></span> <span data-ttu-id="dba91-120">Dies ist nur für neue Tabellen möglich.</span><span class="sxs-lookup"><span data-stu-id="dba91-120">You can do this for new tables only.</span></span>  
  
 <span data-ttu-id="dba91-121">**Remove**</span><span class="sxs-lookup"><span data-stu-id="dba91-121">**Remove**</span></span>  
 <span data-ttu-id="dba91-122">Wählen Sie in der Liste eine Tabelle aus, und klicken Sie auf **Entfernen** , um die Tabelle aus der CDC-Instanz zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="dba91-122">Select a table from the list and click **Remove** to remove the table from the CDC instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dba91-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dba91-123">See Also</span></span>  
 <span data-ttu-id="dba91-124">[Bearbeiten der CDC-Instanzeigenschaften](how-to-edit-the-cdc-instance-properties.md) </span><span class="sxs-lookup"><span data-stu-id="dba91-124">[How to Edit the CDC Instance Properties](how-to-edit-the-cdc-instance-properties.md) </span></span>  
 [<span data-ttu-id="dba91-125">Auswählen von Oracle-Tabellen und -Spalten</span><span class="sxs-lookup"><span data-stu-id="dba91-125">Select Oracle Tables and Columns</span></span>](select-oracle-tables-and-columns.md)  
  
  
