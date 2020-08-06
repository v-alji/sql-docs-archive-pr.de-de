---
title: Tabellen und Spalten (Dialogfeld) (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.tablesandcolumns
ms.assetid: 8cf27be1-e66d-4735-a428-9ab4b33af4f5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 28e0c52b74413a3a5a4122412c6028b34e974b09
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621296"
---
# <a name="tables-and-columns-dialog-box-visual-database-tools"></a><span data-ttu-id="d426d-102">Tabellen und Spalten (Dialogfeld) (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="d426d-102">Tables and Columns Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="d426d-103">In diesem Dialogfeld können Sie einen Primärschlüssel in einer Tabelle einem Fremdschlüssel in einer anderen Tabelle zuordnen.</span><span class="sxs-lookup"><span data-stu-id="d426d-103">Use this dialog box to map a primary key in one table to a foreign key in another.</span></span> <span data-ttu-id="d426d-104">Sie können dieses Dialogfeld aufrufen, indem Sie im Menü **Tabellen-Designer** auf **Beziehungen**klicken.</span><span class="sxs-lookup"><span data-stu-id="d426d-104">To access this dialog box, from the **Table Designer** menu, click **Relationships**.</span></span> <span data-ttu-id="d426d-105">Klicken Sie im Dialogfeld **Fremdschlüsselbeziehungen** auf **Tabellen- und Spaltenspezifikation**, und klicken Sie anschließend auf die Auslassungspunkte **(…)** , die rechts neben der Eigenschaft angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d426d-105">In the **Foreign Key Relationships** dialog box, click the **Tables and Columns Specification** field, and then click the ellipses **(...)** to the right of the property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d426d-106">Wenn die Tabelle zur Replikation veröffentlicht ist, müssen Sie mit der Transact-SQL-Anweisung [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) oder mit SMO (SQL Server Management Objects) Schemaänderungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="d426d-106">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="d426d-107">Wenn die Schemaänderungen mit dem Tabellen-Designer oder dem Datenbankdiagramm-Designer ausgeführt werden, wird versucht, die Tabelle zu entfernen und erneut zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d426d-107">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="d426d-108">Da veröffentlichte Objekte nicht gelöscht werden können, schlägt die Schemaänderung fehl.</span><span class="sxs-lookup"><span data-stu-id="d426d-108">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d426d-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="d426d-109">Options</span></span>  
 <span data-ttu-id="d426d-110">**Beziehungsname**</span><span class="sxs-lookup"><span data-stu-id="d426d-110">**Relationship name**</span></span>  
 <span data-ttu-id="d426d-111">Zeigt den Namen der Beziehung an.</span><span class="sxs-lookup"><span data-stu-id="d426d-111">Shows the name of the relationship.</span></span>  
  
 <span data-ttu-id="d426d-112">**Primärschlüsseltabelle**</span><span class="sxs-lookup"><span data-stu-id="d426d-112">**Primary Key Table**</span></span>  
 <span data-ttu-id="d426d-113">Listet die in der Datenbank enthaltenen Tabellen auf.</span><span class="sxs-lookup"><span data-stu-id="d426d-113">Lists the tables in the database.</span></span> <span data-ttu-id="d426d-114">Wählen Sie die Tabelle für die Primärschlüsselseite der Beziehung aus.</span><span class="sxs-lookup"><span data-stu-id="d426d-114">Choose the table that will be on the primary-key side of the relationship.</span></span>  
  
 <span data-ttu-id="d426d-115">**Fremdschlüsseltabelle**</span><span class="sxs-lookup"><span data-stu-id="d426d-115">**Foreign Key Table**</span></span>  
 <span data-ttu-id="d426d-116">Zeigt die Tabelle an, die der Fremdschlüsselseite der Beziehung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="d426d-116">Shows the table on the foreign key side of the relationship.</span></span> <span data-ttu-id="d426d-117">Dabei handelt es sich um die aktuell im Tabellen-Designer ausgewählte Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d426d-117">This is the table currently selected in Table Designer.</span></span>  
  
 <span data-ttu-id="d426d-118">**Datenblatt unter der Primärschlüsseltabelle**</span><span class="sxs-lookup"><span data-stu-id="d426d-118">**Grid beneath Primary Key Table**</span></span>  
 <span data-ttu-id="d426d-119">Listet die Spalten der in der Liste **Primärschlüsseltabelle** ausgewählten Tabelle auf.</span><span class="sxs-lookup"><span data-stu-id="d426d-119">List the columns of the table selected in the **Primary Key Table** list.</span></span> <span data-ttu-id="d426d-120">Geben Sie die Spalten ein, die für den Primärschlüssel dieser Tabelle verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d426d-120">Enter the columns contributing to that table's primary key.</span></span>  
  
 <span data-ttu-id="d426d-121">**Datenblatt unter der Fremdschlüsseltabelle**</span><span class="sxs-lookup"><span data-stu-id="d426d-121">**Grid beneath Foreign Key Table**</span></span>  
 <span data-ttu-id="d426d-122">Listet die Spalten der in der Liste **Fremdschlüsseltabelle** ausgewählten Tabelle auf.</span><span class="sxs-lookup"><span data-stu-id="d426d-122">List the columns of the table selected in the **Foreign Key Table** list.</span></span> <span data-ttu-id="d426d-123">Geben Sie die Fremdschlüsselspalte der Fremdschlüsseltabelle ein, die der Primärschlüsselspalte entspricht.</span><span class="sxs-lookup"><span data-stu-id="d426d-123">Enter the foreign-key column of the foreign-key table that corresponds to the primary key column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d426d-124">Die Spalten, die Sie für den Fremdschlüssel auswählen, müssen denselben Datentyp wie die entsprechenden Primärspalten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d426d-124">The columns you choose for the foreign key must have the same data type of the primary columns they correspond to.</span></span> <span data-ttu-id="d426d-125">Die Anzahl der Spalten muss in den jeweiligen Schlüsseln gleich sein.</span><span class="sxs-lookup"><span data-stu-id="d426d-125">There must be an equal number of columns in each of the keys.</span></span> <span data-ttu-id="d426d-126">Wenn beispielsweise der Primärschlüssel der Tabelle auf der Primärseite der Beziehung aus zwei Spalten besteht, müssen Sie für jede Spalte eine entsprechende Spalte in der Tabelle für die Fremdschlüsselseite der Beziehung auswählen.</span><span class="sxs-lookup"><span data-stu-id="d426d-126">For example, if the primary key of the table on the primary side of the relationship is made up of two columns, you will need to match each of those columns with a column in the table for the foreign key side of the relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d426d-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d426d-127">See Also</span></span>  
 [<span data-ttu-id="d426d-128">Erstellen von Fremdschlüssel-Beziehungen</span><span class="sxs-lookup"><span data-stu-id="d426d-128">Create Foreign Key Relationships</span></span>](../../relational-databases/tables/create-foreign-key-relationships.md)  
  
  
