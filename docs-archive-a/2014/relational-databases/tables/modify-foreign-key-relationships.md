---
title: Ändern von Fremdschlüsselbeziehungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:65538
- vdt.ppg.relationships
helpviewer_keywords:
- foreign keys [SQL Server], modifying
- modifying foreign keys
ms.assetid: 0c9ca80d-d79b-44c4-a21e-0fce39c398ec
author: stevestein
ms.author: sstein
ms.openlocfilehash: ba9010b0d634a174dd35391c870d5003aa78efa1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609042"
---
# <a name="modify-foreign-key-relationships"></a><span data-ttu-id="dcf6e-102">Ändern von Fremdschlüsselbeziehungen</span><span class="sxs-lookup"><span data-stu-id="dcf6e-102">Modify Foreign Key Relationships</span></span>
  <span data-ttu-id="dcf6e-103">Sie können die Fremdschlüsselseite einer Beziehung in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]ändern.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-103">You can modify the foreign key side of a relationship in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="dcf6e-104">Wenn Sie den Fremdschlüssel einer Tabelle ändern, wird entsprechend angepasst, welche Spalten mit den Spalten in der Primärschlüsseltabelle verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-104">Modifying a table's foreign key changes which columns are related to columns in the primary key table.</span></span>  
  
 <span data-ttu-id="dcf6e-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="dcf6e-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="dcf6e-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="dcf6e-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="dcf6e-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="dcf6e-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="dcf6e-108">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="dcf6e-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="dcf6e-109">**So ändern Sie einen Fremdschlüssel mit:**</span><span class="sxs-lookup"><span data-stu-id="dcf6e-109">**To modify a foreign key using:**</span></span>  
  
     [<span data-ttu-id="dcf6e-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dcf6e-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="dcf6e-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dcf6e-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dcf6e-112">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="dcf6e-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="dcf6e-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="dcf6e-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="dcf6e-114">Für die neue Fremdschlüsselspalte und die verknüpfte Primärschlüsselspalte müssen Datentyp und Größe übereinstimmen, mit diesen Ausnahmen:</span><span class="sxs-lookup"><span data-stu-id="dcf6e-114">The new foreign key column must match the data type and size of the primary key column to which it relates, with these exceptions:</span></span>  
  
-   <span data-ttu-id="dcf6e-115">Eine Spalte vom Typ `char` oder `sysname` kann mit einer Spalte vom Typ `varchar` verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-115">A `char` column or `sysname` column can relate to a `varchar` column.</span></span>  
  
-   <span data-ttu-id="dcf6e-116">Eine Spalte vom Typ `binary` kann mit einer Spalte vom Typ `varbinary` verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-116">A `binary` column can relate to a `varbinary` column.</span></span>  
  
-   <span data-ttu-id="dcf6e-117">Ein Aliasdatentyp kann mit seinem Basistyp verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-117">An alias data type can relate to its base type.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dcf6e-118">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="dcf6e-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="dcf6e-119">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="dcf6e-119">Permissions</span></span>  
 <span data-ttu-id="dcf6e-120">Erfordert die ALTER-Berechtigung für die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-120">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="dcf6e-121">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dcf6e-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-foreign-key"></a><span data-ttu-id="dcf6e-122">So ändern Sie einen Fremdschlüssel</span><span class="sxs-lookup"><span data-stu-id="dcf6e-122">To modify a foreign key</span></span>  
  
1.  <span data-ttu-id="dcf6e-123">Erweitern Sie im **Objekt-Explorer**die Tabelle mit dem Fremdschlüssel, und erweitern Sie dann die Option **Schlüssel**.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-123">In **Object Explorer**, expand the table with the foreign key and then expand **Keys**.</span></span>  
  
2.  <span data-ttu-id="dcf6e-124">Klicken Sie mit der rechten Maustaste auf den zu ändernden Fremdschlüssel, und wählen Sie die Option **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-124">Right-click the foreign key to be modified and select **Modify**.</span></span>  
  
3.  <span data-ttu-id="dcf6e-125">Im Dialogfeld **Fremdschlüsselbeziehungen** können Sie die folgenden Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-125">In the **Foreign Key Relationships** dialog box, you can make the following modifications.</span></span>  
  
     <span data-ttu-id="dcf6e-126">**Ausgew. Beziehung**</span><span class="sxs-lookup"><span data-stu-id="dcf6e-126">**Selected Relationship**</span></span>  
     <span data-ttu-id="dcf6e-127">Listet bestehende Beziehungen auf.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-127">Lists existing relationships.</span></span> <span data-ttu-id="dcf6e-128">Wählen Sie eine Beziehung aus, um ihre Eigenschaften im Datenblatt rechts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-128">Select a relationship to show its properties in the grid to the right.</span></span> <span data-ttu-id="dcf6e-129">Wenn die Liste leer ist, wurden bisher keine Beziehungen für die Tabelle definiert.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-129">If the list is empty, no relationships have been defined for the table.</span></span>  
  
     <span data-ttu-id="dcf6e-130">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="dcf6e-130">**Add**</span></span>  
     <span data-ttu-id="dcf6e-131">Erstellt eine neue Beziehung.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-131">Create a new relationship.</span></span> <span data-ttu-id="dcf6e-132">Die **Tabellen- und Spaltenspezifikation** muss festgelegt werden, bevor die Beziehung gültig wird.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-132">The **Tables and Columns Specifications** must be set before the relationship will be valid.</span></span>  
  
     <span data-ttu-id="dcf6e-133">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="dcf6e-133">**Delete**</span></span>  
     <span data-ttu-id="dcf6e-134">Löscht die in der Liste **ausgewählte Beziehung** ausgewählte Beziehung.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-134">Delete the relationship selected in the **Selected Relationships** list.</span></span> <span data-ttu-id="dcf6e-135">Verwenden Sie diese Schaltfläche zum Entfernen der Beziehung, um das Hinzufügen einer Beziehung abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-135">To cancel the addition of a relationship, use this button to remove the relationship.</span></span>  
  
     <span data-ttu-id="dcf6e-136">**Kategorie Allgemein**</span><span class="sxs-lookup"><span data-stu-id="dcf6e-136">**General Category**</span></span>  
     <span data-ttu-id="dcf6e-137">Wenn die Kategorie erweitert ist, werden **Vorhandene Daten bei Erstellung oder Reaktivierung überprüfen** und **Tabellen- und Spaltenspezifikation**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-137">Expand to show **Check Existing Data on Creation or RE-Enabling** and **Tables and Columns Specifications**.</span></span>  
  
     <span data-ttu-id="dcf6e-138">**Check Existing Data on Creation or Re-Enabling**</span><span class="sxs-lookup"><span data-stu-id="dcf6e-138">**Check Existing Data on Creation or Re-Enabling**</span></span>  
     <span data-ttu-id="dcf6e-139">Überprüft alle Daten, die vor der Erstellung oder Reaktivierung der Einschränkung in der Tabelle vorhandenen sind, auf die Einschränkung hin.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-139">Verify all existing data in the table before the constraint was created or re-enabled, against the constraint.</span></span>  
  
     <span data-ttu-id="dcf6e-140">**Kategorie Tabellen- und Spaltenspezifikation**</span><span class="sxs-lookup"><span data-stu-id="dcf6e-140">**Tables and Columns Specifications Category**</span></span>  
     <span data-ttu-id="dcf6e-141">Wenn die Kategorie erweitert ist, wird angezeigt, welche Spalten aus welchen Tabellen als Fremdschlüssel, Primärschlüssel oder eindeutiger Schlüssel in der Beziehung fungieren.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-141">Expand to show which columns from which tables act as the foreign key and primary (or unique) key in the relationship.</span></span> <span data-ttu-id="dcf6e-142">Klicken Sie rechts neben dem Eigenschaftenfeld auf die Schaltfläche mit den Auslassungspunkten ( **...** ), um diese Werte zu bearbeiten oder zu definieren.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-142">To edit or define these values, click the ellipsis button (**...**) to the right of the property field.</span></span>  
  
     <span data-ttu-id="dcf6e-143">**Fremdschlüssel-Basistabelle**</span><span class="sxs-lookup"><span data-stu-id="dcf6e-143">**Foreign Key Base Table**</span></span>  
     <span data-ttu-id="dcf6e-144">Zeigt an, welche Tabelle die Spalte enthält, die in der ausgewählten Beziehung als Fremdschlüssel fungiert.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-144">Shows which table contains the column acting as a foreign key in the selected relationship.</span></span>  
  
     <span data-ttu-id="dcf6e-145">**Fremdschlüsselspalten**</span><span class="sxs-lookup"><span data-stu-id="dcf6e-145">**Foreign Key Columns**</span></span>  
     <span data-ttu-id="dcf6e-146">Zeigt an, welche Spalte in der ausgewählten Beziehung als Fremdschlüssel fungiert.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-146">Shows which column acts as a foreign key in the selected relationship.</span></span>  
  
     <span data-ttu-id="dcf6e-147">**Primary/Unique Schlüsselbasistabelle**</span><span class="sxs-lookup"><span data-stu-id="dcf6e-147">**Primary/Unique Key Base Table**</span></span>  
     <span data-ttu-id="dcf6e-148">Zeigt an, welche Tabelle die Spalte enthält, die in der ausgewählten Beziehung als Primärschlüssel oder eindeutiger Schlüssel fungiert.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-148">Shows which table contains the column acting as a primary (or unique) key in the selected relationship.</span></span>  
  
     <span data-ttu-id="dcf6e-149">**Primary/Unique Schlüsselspalten**</span><span class="sxs-lookup"><span data-stu-id="dcf6e-149">**Primary/Unique Key Columns**</span></span>  
     <span data-ttu-id="dcf6e-150">Zeigt an, welche Spalte in der ausgewählten Beziehung als Primärschlüssel oder eindeutiger Schlüssel fungiert.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-150">Shows which column acts as a primary (or unique) key in the selected relationship.</span></span>  
  
     <span data-ttu-id="dcf6e-151">**Kategorie Identität**</span><span class="sxs-lookup"><span data-stu-id="dcf6e-151">**Identity Category**</span></span>  
     <span data-ttu-id="dcf6e-152">Wenn die Kategorie erweitert ist, werden die Eigenschaftenfelder für **Name** und **Beschreibung**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-152">Expand to show the property fields for **Name** and **Description**.</span></span>  
  
     <span data-ttu-id="dcf6e-153">**Name**</span><span class="sxs-lookup"><span data-stu-id="dcf6e-153">**Name**</span></span>  
     <span data-ttu-id="dcf6e-154">Zeigt den Namen der Beziehung an.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-154">Shows the name of the relationship.</span></span> <span data-ttu-id="dcf6e-155">Wenn eine neue Beziehung erstellt wird, erhält sie einen Standardnamen, der auf der Tabelle im aktiven Fenster im **Tabellen-Designer** basiert.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-155">When a new relationship is created, it is given a default name based on the table in the active window in **Table Designer**.</span></span> <span data-ttu-id="dcf6e-156">Sie können den Namen jederzeit ändern.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-156">You can change the name at any time.</span></span>  
  
     <span data-ttu-id="dcf6e-157">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="dcf6e-157">**Description**</span></span>  
     <span data-ttu-id="dcf6e-158">Beschreibt die Beziehung.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-158">Describe the relationship.</span></span> <span data-ttu-id="dcf6e-159">Um eine detailliertere Beschreibung zu erstellen, klicken Sie auf **Beschreibung** , und klicken Sie anschließend auf die Auslassungspunkte **(...)** rechts neben dem Eigenschaftenfeld.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-159">To write a more detailed description, click **Description** and then click the ellipsis **(...)** that appears to the right of the property field.</span></span> <span data-ttu-id="dcf6e-160">Dadurch wird ein größerer Bereich verfügbar, in den Sie Text eingeben können.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-160">This provides a larger area in which to write text.</span></span>  
  
     <span data-ttu-id="dcf6e-161">**Kategorie Tabellen-Designer**</span><span class="sxs-lookup"><span data-stu-id="dcf6e-161">**Table Designer Category**</span></span>  
     <span data-ttu-id="dcf6e-162">Wenn die Kategorie erweitert ist, werden Informationen über **Vorhandene Daten bei Erstellung oder Reaktivierung überprüfen** und **Für Replikation erzwingen**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-162">Expand to show information for **Check Existing Data on Creation or Re-Enabling** and **Enforce for Replication**.</span></span>  
  
     <span data-ttu-id="dcf6e-163">**Für Replikation erzwingen**</span><span class="sxs-lookup"><span data-stu-id="dcf6e-163">**Enforce For Replication**</span></span>  
     <span data-ttu-id="dcf6e-164">Gibt an, ob die Einschränkung erzwungen wird, wenn durch den Replikations-Agent in der Tabelle eine INSERT-, ein UPDATE- oder DELETE-Anweisung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-164">Indicates whether to enforce the constraint when a replication agent performs an insert, update, or delete on this table.</span></span>  
  
     <span data-ttu-id="dcf6e-165">**Fremdschlüsseleinschränkung erzwingen**</span><span class="sxs-lookup"><span data-stu-id="dcf6e-165">**Enforce Foreign Key Constraint**</span></span>  
     <span data-ttu-id="dcf6e-166">Gibt an, ob Änderungen der Daten in den Spalten der Beziehung zulässig sind, wenn die Integrität der Fremdschlüsselbeziehung durch diese Änderungen aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-166">Specify whether changes are allowed to the data of the columns in the relationship if those changes would invalidate the integrity of the foreign key relationship.</span></span> <span data-ttu-id="dcf6e-167">Wählen Sie **Ja** aus, um solche Änderungen nicht zuzulassen, und wählen Sie **Nein** aus, um sie zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-167">Choose **Yes** if you do not want to allow such changes, and choose **No** if you do want to allow them.</span></span>  
  
     <span data-ttu-id="dcf6e-168">**Kategorie INSERT- und UPDATE-Spezifikation**</span><span class="sxs-lookup"><span data-stu-id="dcf6e-168">**INSERT and UPDATE Specification Category**</span></span>  
     <span data-ttu-id="dcf6e-169">Wenn die Kategorie erweitert ist, werden Informationen über **Regel löschen** und **Regel aktualisieren** für die Beziehung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-169">Expand to show information for the **Delete Rule** and the **Update Rule** for the relationship.</span></span>  
  
     <span data-ttu-id="dcf6e-170">**Regel löschen**</span><span class="sxs-lookup"><span data-stu-id="dcf6e-170">**Delete Rule**</span></span>  
     <span data-ttu-id="dcf6e-171">Gibt an, was geschehen soll, wenn ein Benutzer versucht, eine Zeile mit Daten zu löschen, die Teil einer Fremdschlüsselbeziehung ist.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-171">Specify what happens if a user tries to delete a row with data that is involved in a foreign key relationship:</span></span>  
  
    -   <span data-ttu-id="dcf6e-172">**Keine Aktion** Eine Fehlermeldung teilt dem Benutzer mit, dass der Löschvorgang unzulässig ist und ein Rollback für die DELETE-Anweisung durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-172">**No Action** An error message tells the user that the deletion is not allowed and the DELETE is rolled back.</span></span>  
  
    -   <span data-ttu-id="dcf6e-173">**Löschweitergabe** Löscht alle Zeilen, die Daten enthalten, die Teil der Fremdschlüsselbeziehung sind.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-173">**Cascade** Deletes all rows containing data involved in the foreign key relationship.</span></span> <span data-ttu-id="dcf6e-174">Geben Sie CASCADE nicht an, wenn die Tabelle in eine Mergeveröffentlichung einbezogen werden soll, bei der logische Datensätze verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-174">Do not specify CASCADE if the table will be included in a merge publication that uses logical records.</span></span>  
  
    -   <span data-ttu-id="dcf6e-175">**NULL festlegen** Legt den Wert auf NULL fest, wenn alle Fremdschlüsselspalten der Tabelle NULL-Werte annehmen können.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-175">**Set Null** Sets the value to null if all foreign key columns for the table can accept null values.</span></span>  
  
    -   <span data-ttu-id="dcf6e-176">**Standard festlegen** Legt den Wert auf den für die Spalte definierten Standardwert fest, wenn für alle Fremdschlüsselspalten der Tabelle Standardwerte definiert sind.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-176">**Set Default** Sets the value to the default value defined for the column if all foreign key columns for the table have defaults defined for them.</span></span>  
  
     <span data-ttu-id="dcf6e-177">**Regel aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="dcf6e-177">**Update Rule**</span></span>  
     <span data-ttu-id="dcf6e-178">Geben Sie an, was geschieht, wenn ein Benutzer versucht, eine Zeile mit Daten zu aktualisieren, die an einer Fremdschlüsselbeziehung beteiligt sind:</span><span class="sxs-lookup"><span data-stu-id="dcf6e-178">Specify what occurs if a user tries to update a row with data that is involved in a foreign key relationship:</span></span>  
  
    -   <span data-ttu-id="dcf6e-179">**Keine Aktion** In einer Fehlermeldung wird dem Benutzer mitgeteilt, dass das Update unzulässig ist und ein Rollback für die UPDATE-Anweisung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-179">**No Action** An error message tells the user that the update is not allowed and the UPDATE is rolled back.</span></span>  
  
    -   <span data-ttu-id="dcf6e-180">**Überlappend** Aktualisiert alle Zeilen, die Daten enthalten, die an der Fremdschlüsselbeziehung beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-180">**Cascade** Updates all rows that contain data involved in the foreign key relationship.</span></span> <span data-ttu-id="dcf6e-181">Geben Sie CASCADE nicht an, wenn die Tabelle in eine Mergeveröffentlichung einbezogen werden soll, bei der logische Datensätze verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-181">Do not specify CASCADE if the table will be included in a merge publication that uses logical records.</span></span>  
  
    -   <span data-ttu-id="dcf6e-182">**NULL festlegen** Legt den Wert auf NULL fest, wenn alle Fremdschlüsselspalten der Tabelle NULL-Werte annehmen können.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-182">**Set Null** Sets the value to null if all foreign key columns for the table can accept null values.</span></span>  
  
    -   <span data-ttu-id="dcf6e-183">**Standard festlegen** Legt den Wert auf den für die Spalte definierten Standardwert fest, wenn für alle Fremdschlüsselspalten der Tabelle Standardwerte definiert sind.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-183">**Set Default** Sets the value to the default value that is defined for the column if all foreign key columns for the table have defaults defined for them.</span></span>  
  
4.  <span data-ttu-id="dcf6e-184">Klicken Sie im Menü **Datei** auf _Tabellenname_**speichern**.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-184">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="dcf6e-185">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dcf6e-185">Using Transact-SQL</span></span>  
 <span data-ttu-id="dcf6e-186">**So ändern Sie einen Fremdschlüssel**</span><span class="sxs-lookup"><span data-stu-id="dcf6e-186">**To modify a foreign key**</span></span>  
  
 <span data-ttu-id="dcf6e-187">Um eine FOREIGN KEY-Einschränkung mit Transact-SQL zu ändern, müssen Sie zuerst die vorhandene FOREIGN KEY-Einschränkung löschen und sie dann mit der neuen Definition neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dcf6e-187">To modify a FOREIGN KEY constraint by using Transact-SQL, you must first delete the existing FOREIGN KEY constraint and then re-create it with the new definition.</span></span> <span data-ttu-id="dcf6e-188">Weitere Informationen finden Sie unter [Delete Foreign Key Relationships](delete-foreign-key-relationships.md) und [Create Foreign Key Relationships](create-foreign-key-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="dcf6e-188">For more information, see [Delete Foreign Key Relationships](delete-foreign-key-relationships.md) and [Create Foreign Key Relationships](create-foreign-key-relationships.md).</span></span>  
  
###  <a name="TsqlExample"></a>  
