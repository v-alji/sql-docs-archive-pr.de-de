---
title: Auswählen von Oracle-Tabellen zum Aufzeichnen von Änderungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- selOraTabDia
ms.assetid: 2e295dc8-999d-4c4d-96cc-1519674b47a4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e9064789dce83ff7d3917ed026c861743142e048
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720302"
---
# <a name="select-oracle-tables-for-capturing-changes"></a><span data-ttu-id="3f305-102">Auswählen von Oracle-Tabellen zum Aufzeichnen von Änderungen</span><span class="sxs-lookup"><span data-stu-id="3f305-102">Select Oracle Tables for Capturing Changes</span></span>
  <span data-ttu-id="3f305-103">Verwenden Sie dieses Dialogfeld, um die Tabellen auszuwählen, die in der CDC-Instanz enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="3f305-103">Use this dialog box to select the tables that are included in the CDC instance.</span></span> <span data-ttu-id="3f305-104">Die ausgewählten Tabellen werden im Assistenten für neue Instanzen der Liste auf der Seite **Select Tables and Columns** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3f305-104">The tables selected are added to the list in the **Select Tables and Columns** page of the New Instance wizard.</span></span> <span data-ttu-id="3f305-105">In diesem Dialogfeld können Sie die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="3f305-105">You can do the following in this dialog box.</span></span>  
  
 <span data-ttu-id="3f305-106">Standardmäßig sind in diesem Dialogfeld in der Tabellenliste keine Tabellen enthalten.</span><span class="sxs-lookup"><span data-stu-id="3f305-106">By default, no tables are included in the list of tables in this dialog box.</span></span> <span data-ttu-id="3f305-107">Sie können das Kontrollkästchen oberhalb der Kontrollkästchenspalte aktivieren, um alle Tabellen auszuwählen, oder Sie können nach bestimmten Tabellen suchen.</span><span class="sxs-lookup"><span data-stu-id="3f305-107">You can select the check box at the top of the check box column to select all of the tables or search for specific tables.</span></span>  
  
 <span data-ttu-id="3f305-108">**So suchen Sie nach bestimmten Tabellen**</span><span class="sxs-lookup"><span data-stu-id="3f305-108">**To search for specific tables**</span></span>  
 <span data-ttu-id="3f305-109">Geben Sie die Suchkriterien wie folgt ein, und klicken Sie dann auf **Suchen**:</span><span class="sxs-lookup"><span data-stu-id="3f305-109">Enter search criteria as follows, and then click **Search**:</span></span>  
  
-   <span data-ttu-id="3f305-110">**Schema**: Wählen Sie in der Liste ein Datenbankschema aus.</span><span class="sxs-lookup"><span data-stu-id="3f305-110">**Schema**: Select a database schema from the list.</span></span> <span data-ttu-id="3f305-111">In der Liste werden nur Tabellen aufgeführt, die über dieses Schema verfügen.</span><span class="sxs-lookup"><span data-stu-id="3f305-111">Only tables that have that schema will be included in the list.</span></span>  
  
-   <span data-ttu-id="3f305-112">**Table Name Pattern**: Geben Sie eine beliebige Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="3f305-112">**Table Name Pattern**: Enter any string of characters.</span></span> <span data-ttu-id="3f305-113">Es werden nur Tabellen angezeigt, die die eingegebene Zeichenfolge enthalten.</span><span class="sxs-lookup"><span data-stu-id="3f305-113">Only tables that include the character string entered are displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3f305-114">Sie können Kriterien in eines der Felder oder beide Felder eingeben.</span><span class="sxs-lookup"><span data-stu-id="3f305-114">You can enter criteria in one or both of these fields.</span></span>  
  
-   <span data-ttu-id="3f305-115">**Display first 1000 matching tables**: Dieses Kontrollkästchen ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3f305-115">**Display first 1000 matching tables**: By default this check box is selected.</span></span> <span data-ttu-id="3f305-116">Diese Option beschränkt die Anzeige auf die ersten 1000 übereinstimmenden Tabellen.</span><span class="sxs-lookup"><span data-stu-id="3f305-116">It limits the display to the first 1000 matching tables.</span></span> <span data-ttu-id="3f305-117">Wenn Sie das Kontrollkästchen deaktivieren, werden alle Tabellen angezeigt, die zu einer Übereinstimmung führen.</span><span class="sxs-lookup"><span data-stu-id="3f305-117">If you clear the check box, all tables that match the criteria are displayed.</span></span> <span data-ttu-id="3f305-118">Falls eine große Anzahl von Tabellen vorhanden ist, kann es relativ lange dauern, bis die Liste angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3f305-118">If there are a large number of tables, it may take a long time to display the list.</span></span>  
  
 <span data-ttu-id="3f305-119">**So wählen Sie die Tabellen aus, die in die CDC-Instanz eingeschlossen werden sollen**</span><span class="sxs-lookup"><span data-stu-id="3f305-119">**To select tables to include in the CDC instance**</span></span>  
 <span data-ttu-id="3f305-120">Aktivieren Sie das Kontrollkästchen neben einer beliebigen Tabelle, die Sie einschließen möchten, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3f305-120">Click the check box next to any of the tables you want to include, and then click **Add**.</span></span> <span data-ttu-id="3f305-121">Die Tabellen werden im Assistenten für neue Instanzen der Liste auf der Seite **Select Tables and Columns** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3f305-121">The tables are added to the list in the New Instance Wizard **Select Tables and Columns** page.</span></span>  
  
 <span data-ttu-id="3f305-122">Klicken Sie auf **Schließen** , um das Dialogfeld zu schließen, ohne weitere Tabellen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3f305-122">Click **Close** to close the dialog box without adding any additional tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3f305-123">Wenn Sie eine Tabelle auswählen, die einen nicht unterstützten Datentyp enthält, wird eine Fehlermeldung angezeigt, und die Tabelle wird nicht eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="3f305-123">If you select a table that includes a non-supported data type, you will see an error message and the table will not be included.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f305-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3f305-124">See Also</span></span>  
 <span data-ttu-id="3f305-125">[Erstellen der Instanz für die SQL Server-Änderungsdatenbank](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="3f305-125">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="3f305-126">Auswählen von Oracle-Tabellen und -Spalten</span><span class="sxs-lookup"><span data-stu-id="3f305-126">Select Oracle Tables and Columns</span></span>](select-oracle-tables-and-columns.md)  
  
  
