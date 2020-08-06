---
title: Fragen zur Datenbankentwicklung (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- compatibility [SQL Server], multuser database changes
- database evolution [SQL Server]
ms.assetid: 1ed6ae10-d212-4ec2-8569-1b94ab1cba6d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 80daa694cd015a83657368902b07da254e6196ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724337"
---
# <a name="issues-of-database-evolution-visual-database-tools"></a><span data-ttu-id="03ccd-102">Fragen zur Datenbankentwicklung (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="03ccd-102">Issues of Database Evolution (Visual Database Tools)</span></span>
  <span data-ttu-id="03ccd-103">Wenn Sie die Struktur einer bereitgestellten Datenbank ändern, sollten Sie insbesondere darauf achten, dass die Änderungen mit den vorhandenen Daten und der vorhandenen Datenbankstruktur kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="03ccd-103">If you change the structure of a deployed database, you must take special care that your alteration is compatible with the existing data and database structure.</span></span> <span data-ttu-id="03ccd-104">Besondere Vorkehrungen können bei den folgenden Änderungen erforderlich sein:</span><span class="sxs-lookup"><span data-stu-id="03ccd-104">You might need to take special steps when you make the following modifications:</span></span>  
  
-   <span data-ttu-id="03ccd-105">**Hinzufügen einer Einschränkung**: Wenn Sie eine Einschränkung hinzufügen, können in der Datenbank bereits Daten vorhanden sein, die der Einschränkung nicht entsprechen.</span><span class="sxs-lookup"><span data-stu-id="03ccd-105">**Adding a Constraint** If you add a constraint, the database might already contain data that does not satisfy it.</span></span> <span data-ttu-id="03ccd-106">Wenn Sie versuchen, die neue Einschränkung zu speichern, werden Sie im [Benachrichtigung nach dem Speichervorgang (Dialogfeld) &#40;Visual Database Tools&#41;](visual-database-tools.md) darüber informiert, dass der Datenbankserver die Einschränkung nicht erstellen konnte.</span><span class="sxs-lookup"><span data-stu-id="03ccd-106">When you try to save the new constraint, the [Post-Save Notifications Dialog Box &#40;Visual Database Tools&#41;](visual-database-tools.md) informs you that the database server could not create the constraint.</span></span> <span data-ttu-id="03ccd-107">Um die Übernahme der neuen Einschränkung in die Datenbank zu erzwingen, können Sie das Kontrollkästchen **Vorhandene Daten bei Erstellung überprüfen** deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="03ccd-107">To force the database to accept the new constraint, you can clear the **Check existing data on creation** check box.</span></span>  
  
-   <span data-ttu-id="03ccd-108">**Hinzufügen einer Beziehung** : Wenn Sie eine Beziehung hinzufügen, können sich in der Datenbank bereits Zeilen der Fremdschlüsseltabelle befinden, für die es in der Primärschlüsseltabelle keine übereinstimmenden Zeilen gibt.</span><span class="sxs-lookup"><span data-stu-id="03ccd-108">**Adding a Relationship** If you add a relationship, the database might already contain rows of the foreign-key table that do not have corresponding rows in the primary-key table.</span></span> <span data-ttu-id="03ccd-109">Das bedeutet, dass die vorhandenen Daten die Forderung nach referenzieller Integrität nicht erfüllen.</span><span class="sxs-lookup"><span data-stu-id="03ccd-109">That is, the existing data might not satisfy referential integrity.</span></span> <span data-ttu-id="03ccd-110">Wenn Sie versuchen, die neue Beziehung zu speichern, werden Sie im [Benachrichtigung nach dem Speichervorgang (Dialogfeld) &#40;Visual Database Tools&#41;](visual-database-tools.md) darüber informiert, dass der Datenbankserver die überarbeitete Fremdschlüsseltabelle nicht speichern konnte.</span><span class="sxs-lookup"><span data-stu-id="03ccd-110">When you try to save the new relationship, the[Post-Save Notifications Dialog Box &#40;Visual Database Tools&#41;](visual-database-tools.md) informs you that the database server could not save the revised foreign-key table.</span></span> <span data-ttu-id="03ccd-111">Um die Übernahme der Änderung in die Datenbank zu erzwingen, können Sie das Kontrollkästchen **Vorhandene Daten bei Erstellung überprüfen** deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="03ccd-111">To force the database to accept the modification, you can clear the **Check existing data on creation** check box.</span></span>  
  
-   <span data-ttu-id="03ccd-112">**Ändern einer Tabelle, die zu einer indizierten Ansicht gehört** : Wenn Sie eine Tabelle ändern, die Teil einer mit Microsoft SQL Server indizierten Ansicht ist, gehen die zur Ansicht gehörenden Indizes verloren.</span><span class="sxs-lookup"><span data-stu-id="03ccd-112">**Modifying a Table Contributing to an Indexed View** If you modify a table that contributes to a Microsoft SQL Server indexed view, the indexes on the view will be lost.</span></span> <span data-ttu-id="03ccd-113">Informationen über das Neuerstellen von Indizes finden Sie in SQL Server Books Online.</span><span class="sxs-lookup"><span data-stu-id="03ccd-113">See the SQL Server Books Online for information on recreating indexes.</span></span>  
  
-   <span data-ttu-id="03ccd-114">**Objekt löschen** : Wenn Sie ein Objekt löschen, z. B. eine Spalte, Tabelle oder Ansicht, prüfen Sie zuerst, ob auf das Objekt nicht von einem anderen Objekt in der Datenbank verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="03ccd-114">**Deleting an Object** If you delete an object, such as a column, table, or view, check first to be sure that the object is not referenced by another object in the database.</span></span>  
  
 <span data-ttu-id="03ccd-115">Unabhängig davon, welche Arten von Änderungen Sie am Entwurf der Datenbank vornehmen, sollten Sie jede Änderung protokollieren.</span><span class="sxs-lookup"><span data-stu-id="03ccd-115">No matter how you alter the database design, you should retain a history of the alterations.</span></span> <span data-ttu-id="03ccd-116">Eine Möglichkeit dafür ist das Aufbewahren der SQL-Skripts aller Änderungen, die Sie an der Produktionsdatenbank vornehmen.</span><span class="sxs-lookup"><span data-stu-id="03ccd-116">One approach is to retain SQL scripts for all modifications that you ever make to your production database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03ccd-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="03ccd-117">See Also</span></span>  
 <span data-ttu-id="03ccd-118">[Unique-Einschränkungen und Check-Einschränkungen](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="03ccd-118">[Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span></span>  
 [<span data-ttu-id="03ccd-119">Mehrbenutzerumgebungen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="03ccd-119">Multiuser Environments &#40;Visual Database Tools&#41;</span></span>](multiuser-environments-visual-database-tools.md)  
  
  
