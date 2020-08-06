---
title: Zuordnen von m:n-Beziehungen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- relationships [SQL Server], many-to-many
- junction tables [SQL Server]
- many-to-many relationships [SQL Server]
- mapping many-to-many relationships [SQL Server]
- database diagrams [SQL Server], relationships
ms.assetid: 2977cf92-98b5-48b2-b0fd-8fbc7040f2b4
author: stevestein
ms.author: sstein
ms.openlocfilehash: cbcbdbdf8d8371baa2a817e43b831535723be7ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621799"
---
# <a name="map-many-to-many-relationships-visual-database-tools"></a><span data-ttu-id="4873e-102">Zuordnen von m:n-Beziehungen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="4873e-102">Map Many-to-Many Relationships (Visual Database Tools)</span></span>
  <span data-ttu-id="4873e-103">Durch m:n-Beziehungen können Sie jede Zeile in einer Tabelle mit mehreren Zeilen in einer anderen Tabelle verknüpfen und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="4873e-103">Many-to-many relationships let you relate each row in one table to many rows in another table, and vice versa.</span></span> <span data-ttu-id="4873e-104">Sie können z. B. eine m:n-Beziehung zwischen der Tabelle `authors` und der Tabelle `titles` erstellen, um einerseits allen Autoren ihre Bücher und andererseits jedem Buch alle seine Autoren zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="4873e-104">For example, you could create a many-to-many relationship between the `authors` table and the `titles` table to match each author to all of his or her books and to match each book to all of its authors.</span></span> <span data-ttu-id="4873e-105">Das Erstellen einer 1:n-Beziehung von einer der beiden Tabellen würde fälschlicherweise angeben, dass jedes Buch nur einen Autor besitzen oder jeder Autor nur ein Buch schreiben kann.</span><span class="sxs-lookup"><span data-stu-id="4873e-105">Creating a one-to-many relationship from either table would incorrectly indicate that every book can have only one author, or that every author can write only one book.</span></span>  
  
 <span data-ttu-id="4873e-106">In Datenbanken werden n:n-Beziehungen zwischen Tabellen mithilfe von Jointabellen erstellt.</span><span class="sxs-lookup"><span data-stu-id="4873e-106">Many-to-many relationships between tables are accommodated in databases by means of junction tables.</span></span> <span data-ttu-id="4873e-107">Eine Jointabelle enthält die Primärschlüsselspalten der beiden zu verknüpfenden Tabellen.</span><span class="sxs-lookup"><span data-stu-id="4873e-107">A junction table contains the primary key columns of the two tables you want to relate.</span></span> <span data-ttu-id="4873e-108">Erstellen Sie dann eine Beziehung von den Primärschlüsselspalten beider Tabellen zu den korrespondierenden Spalten in der Jointabelle.</span><span class="sxs-lookup"><span data-stu-id="4873e-108">You then create a relationship from the primary key columns of each of those two tables to the matching columns in the junction table.</span></span> <span data-ttu-id="4873e-109">In der Datenbank Pubs handelt es sich bei der Tabelle `titleauthor` um eine Jointabelle.</span><span class="sxs-lookup"><span data-stu-id="4873e-109">In the pubs database, the `titleauthor` table is a junction table.</span></span>  
  
### <a name="to-create-a-many-to-many-relationship-between-tables"></a><span data-ttu-id="4873e-110">So erstellen Sie eine m:n-Beziehung zwischen Tabellen</span><span class="sxs-lookup"><span data-stu-id="4873e-110">To create a many-to-many relationship between tables</span></span>  
  
1.  <span data-ttu-id="4873e-111">Fügen Sie im Datenbankdiagramm die Tabellen hinzu, zwischen denen Sie eine m:n-Beziehung erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="4873e-111">In your database diagram, add the tables that you want to create a many-to-many relationship between.</span></span>  
  
2.  <span data-ttu-id="4873e-112">Erstellen Sie eine dritte Tabelle, indem Sie mit rechten Maustaste auf das Diagramm klicken und anschließend im Kontextmenü **Neue Tabelle** auswählen.</span><span class="sxs-lookup"><span data-stu-id="4873e-112">Create a third table by right-clicking the diagram and choosing **New Table** from the shortcut menu.</span></span> <span data-ttu-id="4873e-113">Die neue Tabelle fungiert als Jointabelle.</span><span class="sxs-lookup"><span data-stu-id="4873e-113">This will become the junction table.</span></span>  
  
3.  <span data-ttu-id="4873e-114">Ändern Sie im Dialogfeld **Namen auswählen** den vom System zugewiesenen Tabellennamen.</span><span class="sxs-lookup"><span data-stu-id="4873e-114">In the **Choose Name** dialog box, change the system-assigned table name.</span></span> <span data-ttu-id="4873e-115">Die Jointabelle zwischen der Tabelle `titles` und der Tabelle `authors` heißt jetzt `titleauthors`.</span><span class="sxs-lookup"><span data-stu-id="4873e-115">For example, the junction table between the `titles` table and the `authors` table is now named `titleauthors`.</span></span>  
  
4.  <span data-ttu-id="4873e-116">Kopieren Sie die Primärschlüsselspalten aus den beiden anderen Tabellen in die Jointabelle.</span><span class="sxs-lookup"><span data-stu-id="4873e-116">Copy the primary key columns from each of the other two tables to the junction table.</span></span> <span data-ttu-id="4873e-117">Sie können der Jointabelle wie jeder anderen Tabelle weitere Spalten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4873e-117">You can add other columns to this table, just as you can to any other table.</span></span>  
  
5.  <span data-ttu-id="4873e-118">Der Primärschlüssel in der Jointabelle muss sämtliche Primärschlüsselspalten aus den beiden anderen Tabellen enthalten.</span><span class="sxs-lookup"><span data-stu-id="4873e-118">In the junction table, set the primary key to include all the primary key columns from the other two tables.</span></span> <span data-ttu-id="4873e-119">Weitere Informationen finden Sie unter [Erstellen von primär Schlüsseln](../../relational-databases/tables/create-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="4873e-119">For details, see [Create Primary Keys](../../relational-databases/tables/create-primary-keys.md).</span></span>  
  
6.  <span data-ttu-id="4873e-120">Definieren Sie zwischen beiden Primärtabellen und der Jointabelle jeweils eine 1:n-Beziehung.</span><span class="sxs-lookup"><span data-stu-id="4873e-120">Define a one-to-many relationship between each of the two primary tables and the junction table.</span></span> <span data-ttu-id="4873e-121">Die Jointabelle muss in beiden Beziehungen die n-Seite darstellen.</span><span class="sxs-lookup"><span data-stu-id="4873e-121">The junction table should be at the "many" side of both of the relationships you create.</span></span> <span data-ttu-id="4873e-122">Weitere Informationen finden Sie unter [Erstellen von Fremdschlüssel Beziehungen](../../relational-databases/tables/create-foreign-key-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="4873e-122">For details, see [Create Foreign Key Relationships](../../relational-databases/tables/create-foreign-key-relationships.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4873e-123">Beim Erstellen einer Jointabelle in einem Datenbankdiagramm werden keine Daten aus den verknüpften Tabellen in die Jointabelle eingefügt.</span><span class="sxs-lookup"><span data-stu-id="4873e-123">The creation of a junction table in a database diagram does not insert data from the related tables into the junction table.</span></span> <span data-ttu-id="4873e-124">Informationen zum Einfügen von Daten in eine Tabelle finden Sie unter [Erstellen von Abfragen zum Einfügen von Ergebnissen &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4873e-124">For information about inserting data into a table, see [Create Insert Results Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4873e-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4873e-125">See Also</span></span>  
 [<span data-ttu-id="4873e-126">Verwenden von Datenbankdiagrammen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4873e-126">Work with Database Diagrams &#40;Visual Database Tools&#41;</span></span>](work-with-database-diagrams-visual-database-tools.md)  
  
  
