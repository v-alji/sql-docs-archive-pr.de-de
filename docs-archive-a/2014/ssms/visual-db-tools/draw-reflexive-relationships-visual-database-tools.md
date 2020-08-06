---
title: Zeichnen reflexiver Beziehungen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- drawing reflexive relationships
- reflexive relationships
- database diagrams [SQL Server], relationships
ms.assetid: e218363f-faec-46d5-9904-a537fbcc994d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8e5056b1a5d0d884edbc4fc818fe8c7ef5cc8ad4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619495"
---
# <a name="draw-reflexive-relationships-visual-database-tools"></a><span data-ttu-id="bfe45-102">Zeichnen reflexiver Beziehungen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="bfe45-102">Draw Reflexive Relationships (Visual Database Tools)</span></span>
  <span data-ttu-id="bfe45-103">Sie erstellen eine reflexive Beziehung, um eine Spalte oder mehrere Spalten in einer Tabelle mit einer anderen Spalte oder mehreren Spalten in derselben Tabelle zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="bfe45-103">You create a reflexive relationship to link a column or columns in a table with another column or columns in the same table.</span></span> <span data-ttu-id="bfe45-104">Angenommen, in der Tabelle `employee` gibt es die Spalte `emp_id` und die Spalte `mgr_id` .</span><span class="sxs-lookup"><span data-stu-id="bfe45-104">For example, suppose the `employee` table has an `emp_id` column and a `mgr_id` column.</span></span> <span data-ttu-id="bfe45-105">Da jeder Manager gleichzeitig ein Mitarbeiter ist, verknüpfen Sie diese beiden Spalten, indem Sie eine Beziehungslinie innerhalb der Tabelle ziehen.</span><span class="sxs-lookup"><span data-stu-id="bfe45-105">Because each manager is also an employee, you relate these two columns by drawing a relationship line from the table to itself.</span></span> <span data-ttu-id="bfe45-106">Durch diese Beziehung wird sichergestellt, dass jede der Tabelle hinzugefügte Manager-ID mit einer vorhandenen Mitarbeiter-ID übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="bfe45-106">This relationship ensures each manager ID that is added to the table matches an existing employee ID.</span></span>  
  
 <span data-ttu-id="bfe45-107">Bevor Sie eine Beziehung erstellen, müssen Sie zunächst einen Primärschlüssel oder eine UNIQUE-Einschränkung für die Tabelle definieren.</span><span class="sxs-lookup"><span data-stu-id="bfe45-107">Before you create a relationship, you must first define a primary key or unique constraint for your table.</span></span> <span data-ttu-id="bfe45-108">Anschließend verknüpfen Sie die Primärschlüsselspalte mit einer übereinstimmenden Spalte.</span><span class="sxs-lookup"><span data-stu-id="bfe45-108">You then relate the primary key column to a matching column.</span></span> <span data-ttu-id="bfe45-109">Wenn die Beziehung erstellt ist, wird die übereinstimmende Spalte der Fremdschlüssel für die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="bfe45-109">Once you create the relationship, the matching column becomes a foreign key of the table.</span></span>  
  
### <a name="to-draw-a-reflexive-relationship"></a><span data-ttu-id="bfe45-110">So erstellen Sie eine reflexive Beziehung</span><span class="sxs-lookup"><span data-stu-id="bfe45-110">To draw a reflexive relationship</span></span>  
  
1.  <span data-ttu-id="bfe45-111">Klicken Sie im Datenbankdiagramm auf den Zeilenselektor für die Datenbankspalte, die Sie zu einer anderen Spalte in Beziehung setzen möchten, und ziehen Sie den Mauszeiger aus der Tabelle heraus, bis eine Linie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="bfe45-111">In your database diagram, click the row selector for the database column that you want to relate to another column and drag the pointer outside the table until a line appears.</span></span>  
  
2.  <span data-ttu-id="bfe45-112">Ziehen Sie die Linie zurück in die ausgewählte Tabelle.</span><span class="sxs-lookup"><span data-stu-id="bfe45-112">Drag the line back to the selected table.</span></span>  
  
3.  <span data-ttu-id="bfe45-113">Lassen Sie die Maustaste los.</span><span class="sxs-lookup"><span data-stu-id="bfe45-113">Release the mouse button.</span></span> <span data-ttu-id="bfe45-114">Das Dialogfeld **Tabellen und Spalten** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bfe45-114">The **Tables and Columns** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="bfe45-115">Wählen Sie die Fremdschlüsselspalte und die Primärschlüsseltabelle sowie -spalte aus, zu denen eine Beziehung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bfe45-115">Select the foreign key column and the primary key table and column with which you want form a relationship.</span></span>  
  
5.  <span data-ttu-id="bfe45-116">Klicken Sie zweimal auf **OK** , um die Beziehung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bfe45-116">Choose **OK** twice to create the relationship.</span></span>  
  
 <span data-ttu-id="bfe45-117">Wenn Sie Abfragen in einer Tabelle ausführen, können Sie mithilfe einer reflexiven Beziehung einen Selbstjoin erstellen.</span><span class="sxs-lookup"><span data-stu-id="bfe45-117">When you run queries against a table, you can use a reflexive relationship to create a self-join.</span></span> <span data-ttu-id="bfe45-118">Informationen über das Abfragen von Tabellen mit Joins finden Sie unter [Erstellen von Abfragen mit Joins &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bfe45-118">For information about querying tables with joins, see [Query with Joins &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfe45-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bfe45-119">See Also</span></span>  
 [<span data-ttu-id="bfe45-120">Erstellen von Abfragen mit Joins &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="bfe45-120">Query with Joins &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
