---
title: Hinzufügen von Tabellen zu einer CDC-Instanz | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- addTabs
ms.assetid: ad260e19-c021-4035-9311-c02fc96ceaea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: edcd84db9e3c464334d407987cb3567f78edd44e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696005"
---
# <a name="add-tables-to-a-cdc-instance"></a><span data-ttu-id="19f63-102">Hinzufügen von Tabellen zu einer CDC-Instanz</span><span class="sxs-lookup"><span data-stu-id="19f63-102">Add Tables to a CDC Instance</span></span>
  <span data-ttu-id="19f63-103">Verwenden Sie das Dialogfeld Tabellenauswahl, um der CDC-Instanz weitere Tabellen der Oracle-Quelle hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="19f63-103">Use the Table Selection dialog box to add additional tables from the Oracle source to the CDC instance.</span></span> <span data-ttu-id="19f63-104">Die ausgewählten Tabellen werden im Eigenschaften-Editor der Liste auf der Registerkarte **Tabellen** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="19f63-104">The tables selected are added to the list in the **Tables** tab of the Properties editor.</span></span>  
  
 <span data-ttu-id="19f63-105">Standardmäßig sind in diesem Dialogfeld in der Tabellenliste keine Tabellen enthalten.</span><span class="sxs-lookup"><span data-stu-id="19f63-105">By default, no tables are included in the list of tables in this dialog box.</span></span> <span data-ttu-id="19f63-106">Sie können das Kontrollkästchen **(Alles auswählen)** aktivieren oder nach bestimmten Tabellen suchen.</span><span class="sxs-lookup"><span data-stu-id="19f63-106">You can select the **(Select All)** check box or search for specific tables.</span></span>  
  
 <span data-ttu-id="19f63-107">**So suchen Sie nach bestimmten Tabellen**</span><span class="sxs-lookup"><span data-stu-id="19f63-107">**To search for specific tables**</span></span>  
 <span data-ttu-id="19f63-108">Geben Sie die Suchkriterien wie folgt ein, und klicken Sie dann auf **Suchen**:</span><span class="sxs-lookup"><span data-stu-id="19f63-108">Enter search criteria as follows, and then click **Search**:</span></span>  
  
-   <span data-ttu-id="19f63-109">**Schema**: Wählen Sie in der Liste ein Datenbankschema aus.</span><span class="sxs-lookup"><span data-stu-id="19f63-109">**Schema**: Select a database schema from the list.</span></span> <span data-ttu-id="19f63-110">In der Liste werden nur Tabellen aufgeführt, die über dieses Schema verfügen.</span><span class="sxs-lookup"><span data-stu-id="19f63-110">Only tables that have that schema will be included in the list.</span></span>  
  
-   <span data-ttu-id="19f63-111">**Table Name Pattern**: Geben Sie eine beliebige Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="19f63-111">**Table Name Pattern**: Enter any string of characters.</span></span> <span data-ttu-id="19f63-112">Es werden nur Tabellen angezeigt, die die eingegebene Zeichenfolge enthalten.</span><span class="sxs-lookup"><span data-stu-id="19f63-112">Only tables that include the character string entered are displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="19f63-113">Sie können Kriterien in eines der Felder oder beide Felder eingeben.</span><span class="sxs-lookup"><span data-stu-id="19f63-113">You can enter criteria in one or both of these fields.</span></span>  
  
-   <span data-ttu-id="19f63-114">**Display first 1000 matching tables**: Dieses Kontrollkästchen ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="19f63-114">**Display first 1000 matching tables**: By default this check box is selected.</span></span> <span data-ttu-id="19f63-115">Diese Option beschränkt die Anzeige auf die ersten 1000 übereinstimmenden Tabellen.</span><span class="sxs-lookup"><span data-stu-id="19f63-115">It limits the display to the first 1000 matching tables.</span></span> <span data-ttu-id="19f63-116">Wenn Sie das Kontrollkästchen deaktivieren, werden alle Tabellen angezeigt, die zu einer Übereinstimmung führen.</span><span class="sxs-lookup"><span data-stu-id="19f63-116">If you clear the check box, all tables that match the criteria are displayed.</span></span> <span data-ttu-id="19f63-117">Falls eine große Anzahl von Tabellen vorhanden ist, kann es relativ lange dauern, bis die Liste angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="19f63-117">If there are a large number of tables, it may take a long time to display the list.</span></span>  
  
 <span data-ttu-id="19f63-118">**So wählen Sie die Tabellen aus, die in die CDC-Instanz eingeschlossen werden sollen**</span><span class="sxs-lookup"><span data-stu-id="19f63-118">**To select tables to include in the CDC instance**</span></span>  
 <span data-ttu-id="19f63-119">Aktivieren Sie das Kontrollkästchen neben einer beliebigen Tabelle, die Sie einschließen möchten, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="19f63-119">Click the check box next to any of the tables you want to include, and then click **Add**.</span></span> <span data-ttu-id="19f63-120">Die Tabellen werden im Assistenten für neue Instanzen der Liste auf der Seite **Select Tables and Columns** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="19f63-120">The tables are added to the list in the New Instance Wizard **Select Tables and Columns** page.</span></span>  
  
 <span data-ttu-id="19f63-121">Klicken Sie auf **Schließen** , um das Dialogfeld zu schließen, ohne Tabellen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="19f63-121">Click **Close** to close the dialog box without adding any tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="19f63-122">Wenn Sie eine Tabelle auswählen, die einen nicht unterstützten Datentyp enthält, wird eine Fehlermeldung angezeigt, und die Tabelle wird nicht eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="19f63-122">If you select a table that includes a non-supported data type, you will see an error message and the table will not be included.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="19f63-123">Sie können die Liste der Tabellen im Viewer anzeigen.</span><span class="sxs-lookup"><span data-stu-id="19f63-123">You can view the list of tables in the viewer.</span></span> <span data-ttu-id="19f63-124">Beim Verwenden des Viewers sind die Informationen schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="19f63-124">When using the viewer the information is read only.</span></span> <span data-ttu-id="19f63-125">Der Viewer enthält auch eine Liste der aufgezeichneten Spalten in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="19f63-125">The viewer also includes a list of the captured columns in the table.</span></span> <span data-ttu-id="19f63-126">Informationen zum Zugriff auf den Viewer finden Sie unter [How to Manage a CDC Instance](manage-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="19f63-126">For information on how to access the viewer, see [How to Manage a CDC Instance](manage-a-cdc-instance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19f63-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="19f63-127">See Also</span></span>  
 <span data-ttu-id="19f63-128">[Bearbeiten der CDC-Instanzeigenschaften](how-to-edit-the-cdc-instance-properties.md) </span><span class="sxs-lookup"><span data-stu-id="19f63-128">[How to Edit the CDC Instance Properties](how-to-edit-the-cdc-instance-properties.md) </span></span>  
 <span data-ttu-id="19f63-129">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span><span class="sxs-lookup"><span data-stu-id="19f63-129">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span></span>  
 [<span data-ttu-id="19f63-130">Auswählen von Oracle-Tabellen zum Aufzeichnen von Änderungen</span><span class="sxs-lookup"><span data-stu-id="19f63-130">Select Oracle Tables for Capturing Changes</span></span>](select-oracle-tables-for-capturing-changes.md)  
  
  
