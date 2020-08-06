---
title: 'Exemplarische Vorgehensweise: Hinzufügen und Ändern von Datenbankdiagrammen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- database diagrams [SQL Server], about database diagrams
- database diagrams [SQL Server], designing
- database diagrams [SQL Server], creating
ms.assetid: 228caa0d-8f24-46ab-86d1-b6d8631322bc
author: stevestein
ms.author: sstein
ms.openlocfilehash: c35eb3674c817e98a25a74cd0309fc7376fe2f58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608998"
---
# <a name="walkthrough-adding-and-changing-a-database-diagram"></a><span data-ttu-id="a3170-102">Exemplarische Vorgehensweise: Hinzufügen und Ändern von Datenbankdiagrammen</span><span class="sxs-lookup"><span data-stu-id="a3170-102">Walkthrough: Adding and Changing a Database Diagram</span></span>
  <span data-ttu-id="a3170-103">In dieser exemplarischen Vorgehensweise wird das Erstellen und Ändern eines Datenbankdiagramms und das Ausführen von Änderungen an der Datenbank mithilfe der Datenbankdiagrammkomponente erläutert.</span><span class="sxs-lookup"><span data-stu-id="a3170-103">This walkthrough illustrates how to create and modify a database diagram and make changes to the database through the database diagrams component.</span></span> <span data-ttu-id="a3170-104">Es wird in Einzelschritten erklärt, wie Diagrammen Tabellen hinzugefügt werden, wie Beziehungen zwischen Tabellen erstellt werden, wie Einschränkungen und Indizes für Spalten erstellt werden und wie die Ebene der Informationen geändert wird, die für die einzelnen Tabellen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a3170-104">You will see how to add tables to diagrams, create relationships between tables, create constraints and indexes on columns, and change the level of information you see for each table.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a3170-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="a3170-105">Prerequisites</span></span>  
 <span data-ttu-id="a3170-106">Wenn Sie diese exemplarische Vorgehensweise abschließen möchten, müssen folgende Voraussetzungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="a3170-106">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="a3170-107">Zugriff auf [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mit der [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Beispieldatenbank</span><span class="sxs-lookup"><span data-stu-id="a3170-107">Access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database</span></span>  
  
-   <span data-ttu-id="a3170-108">Ein Konto mit Rechten als Datenbankbesitzer (`dbo`)</span><span class="sxs-lookup"><span data-stu-id="a3170-108">An account with database owner `dbo` privileges</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a3170-109">Wenn Sie versuchen, über ein Konto Änderungen vorzunehmen, das nicht über ausreichende Rechte zum Ändern von Tabellen verfügt, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3170-109">If you attempt to make changes when using an account without sufficient privileges to make changes to tables, then an error message appears.</span></span>  
  
## <a name="creating-a-diagram"></a><span data-ttu-id="a3170-110">Erstellen eines Diagramms</span><span class="sxs-lookup"><span data-stu-id="a3170-110">Creating a Diagram</span></span>  
  
#### <a name="to-create-a-new-database-diagram"></a><span data-ttu-id="a3170-111">So erstellen Sie ein neues Datenbankdiagramm</span><span class="sxs-lookup"><span data-stu-id="a3170-111">To create a new database diagram</span></span>  
  
1.  <span data-ttu-id="a3170-112">Klicken Sie im Menü **Ansicht** auf **Objekt-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="a3170-112">On the **View** menu, click **Object Explorer**.</span></span>  
  
2.  <span data-ttu-id="a3170-113">Öffnen Sie den Knoten Datenbanken und dann den Knoten [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a3170-113">Open the Databases node and then open the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] node.</span></span>  
  
3.  <span data-ttu-id="a3170-114">Klicken Sie mit der rechten Maustaste auf den Knoten Datenbankdiagramme, und wählen Sie **Neues Datenbankdiagramm** aus.</span><span class="sxs-lookup"><span data-stu-id="a3170-114">Right-click the Database Diagrams node and choose **New Database Diagram**.</span></span>  
  
     <span data-ttu-id="a3170-115">Wenn die Datenbank nicht über die zum Erstellen von Diagrammen erforderlichen Objekte verfügt, wird folgende Meldung angezeigt: **Dieser Datenbank fehlt mindestens eines der Unterstützungsobjekte, die erforderlich sind, damit Diagramme für die Datenbank erstellt werden können. Möchten Sie es erstellen?**</span><span class="sxs-lookup"><span data-stu-id="a3170-115">If the database does not have objects necessary to create diagrams, the following message appears: **This database does not have one or more of the support objects required to use database diagramming. Do you wish to create them?**</span></span> <span data-ttu-id="a3170-116">Wählen Sie die Option **Ja** aus.</span><span class="sxs-lookup"><span data-stu-id="a3170-116">Choose **Yes**.</span></span>  
  
     <span data-ttu-id="a3170-117">Das Dialogfeld **Tabelle hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3170-117">The **Add Table** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="a3170-118">Wählen Sie **Adresstyp (Person)** und **Adresse (Person)** aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a3170-118">Select **AddressType (Person)** and **Address (Person)** and click **Add**.</span></span>  
  
     <span data-ttu-id="a3170-119">Dem Diagramm werden zwei Tabellen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a3170-119">Two tables are added to the diagram.</span></span>  
  
5.  <span data-ttu-id="a3170-120">Schließen Sie das Dialogfeld **Tabelle hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="a3170-120">Close the **Add Table** dialog box.</span></span>  
  
#### <a name="to-view-different-column-data"></a><span data-ttu-id="a3170-121">So zeigen Sie unterschiedliche Spaltendaten an</span><span class="sxs-lookup"><span data-stu-id="a3170-121">To view different column data</span></span>  
  
1.  <span data-ttu-id="a3170-122">Klicken Sie mit der rechten Maustaste auf die `Address` -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a3170-122">Right-click the `Address` table.</span></span> <span data-ttu-id="a3170-123">Zeigen Sie im Kontextmenü auf **Tabellensicht**, und klicken Sie dann auf **Standard**.</span><span class="sxs-lookup"><span data-stu-id="a3170-123">On the shortcut menu, point to **Table View**, and then click **Standard**.</span></span>  
  
     <span data-ttu-id="a3170-124">Im Tabellenraster werden drei Spalten angezeigt: **Spaltenname**, **Datentyp**und **NULL-Werte zulassen**.</span><span class="sxs-lookup"><span data-stu-id="a3170-124">The table grid shows three columns: **Column Name**, **Data Type**, and **Allow Nulls**.</span></span>  
  
2.  <span data-ttu-id="a3170-125">Klicken Sie mit der rechten Maustaste auf die `Address` -Tabelle, klicken Sie auf **Tabellensicht** , und wählen Sie **Schlüssel**aus.</span><span class="sxs-lookup"><span data-stu-id="a3170-125">Right-click the `Address` table, click **Table View** and select **Keys**.</span></span>  
  
     <span data-ttu-id="a3170-126">Im Tabellenraster wird eine Spalte mit den Tabellenspaltennamen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3170-126">The table grid shows one column, with the table-column names.</span></span> <span data-ttu-id="a3170-127">Es werden nur solche Spalten angezeigt, die an Indizes beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="a3170-127">Only those columns participating in indexes appear.</span></span>  
  
## <a name="creating-new-tables"></a><span data-ttu-id="a3170-128">Erstellen neuer Tabellen</span><span class="sxs-lookup"><span data-stu-id="a3170-128">Creating New Tables</span></span>  
  
#### <a name="to-create-tables-within-diagram-designer"></a><span data-ttu-id="a3170-129">So erstellen Sie Tabellen im Datenbank-Designer</span><span class="sxs-lookup"><span data-stu-id="a3170-129">To create tables within Diagram Designer</span></span>  
  
1.  <span data-ttu-id="a3170-130">Klicken Sie mit der rechten Maustaste auf den Datenbank-Designer außerhalb der vorhandenen Tabellen, und wählen Sie **Neue Tabelle**aus.</span><span class="sxs-lookup"><span data-stu-id="a3170-130">Right-click the Diagram Designer outside the existing tables and choose **New Table**.</span></span>  
  
2.  <span data-ttu-id="a3170-131">Klicken Sie im Dialogfeld **Namen auswählen** auf **OK** , um den Standardnamen zu übernehmen `Table1` .</span><span class="sxs-lookup"><span data-stu-id="a3170-131">In the **Choose Name** dialog box, click **OK** to accept the default name `Table1`.</span></span>  
  
     <span data-ttu-id="a3170-132">Ein neues Tabellenraster mit drei Spalten wird angezeigt: **Spaltenname**, **Datentyp**und **NULL-Werte zulassen**.</span><span class="sxs-lookup"><span data-stu-id="a3170-132">A new table grid appears with three columns: **Column Name**, **Data Type**, and **Allow Nulls**.</span></span>  
  
3.  <span data-ttu-id="a3170-133">Fügen Sie die folgenden Informationen hinzu `Table1` :</span><span class="sxs-lookup"><span data-stu-id="a3170-133">Add the following information to `Table1`:</span></span>  
  
    |<span data-ttu-id="a3170-134">**Spaltenname**</span><span class="sxs-lookup"><span data-stu-id="a3170-134">**Column Name**</span></span>|<span data-ttu-id="a3170-135">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="a3170-135">**Data Type**</span></span>|<span data-ttu-id="a3170-136">**NULL-Werte zulassen**</span><span class="sxs-lookup"><span data-stu-id="a3170-136">**Allow Nulls**</span></span>|  
    |---------------------|-------------------|---------------------|  
    |`T1col1`|`int`|<span data-ttu-id="a3170-137">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="a3170-137">checked</span></span>|  
    |`T1col2`|`varchar(50)`|<span data-ttu-id="a3170-138">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="a3170-138">checked</span></span>|  
    |`T1col3`|`float`|<span data-ttu-id="a3170-139">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="a3170-139">checked</span></span>|  
  
4.  <span data-ttu-id="a3170-140">Klicken Sie mit der rechten Maustaste auf `T1col1` , und wählen Sie **Primärschlüssel festlegen**aus.</span><span class="sxs-lookup"><span data-stu-id="a3170-140">Right-click `T1col1` and select **Set Primary Key**.</span></span>  
  
     <span data-ttu-id="a3170-141">Neben dem Spaltennamen wird ein Schlüsselsymbol angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3170-141">A key icon will appear beside the column name.</span></span>  
  
5.  <span data-ttu-id="a3170-142">Klicken Sie im Menü **Datei** auf **Diagramm1 speichern**.</span><span class="sxs-lookup"><span data-stu-id="a3170-142">From the **File** menu, click **Save Diagram1**.</span></span>  
  
6.  <span data-ttu-id="a3170-143">Klicken Sie im Dialogfeld **Namen auswählen** auf **OK** , um den Standardnamen zu übernehmen `Diagram1` .</span><span class="sxs-lookup"><span data-stu-id="a3170-143">In the **Choose Name** dialog box, click **OK** to accept the default name `Diagram1`.</span></span>  
  
7.  <span data-ttu-id="a3170-144">Das Dialogfeld **Speichern** wird angezeigt, und in einer Meldung wird darüber informiert, dass `Table1` in der Datenbank gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="a3170-144">The **Save** dialog box appears with a message that `Table1` will be saved to the database.</span></span> <span data-ttu-id="a3170-145">Klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="a3170-145">Click **Yes**.</span></span>  
  
## <a name="modifying-table-structure"></a><span data-ttu-id="a3170-146">Ändern der Tabellenstruktur</span><span class="sxs-lookup"><span data-stu-id="a3170-146">Modifying Table Structure</span></span>  
 <span data-ttu-id="a3170-147">Im Datenbank-Designer können Sie CHECK-Einschränkungen hinzufügen und Beziehungen zwischen Tabellen herstellen.</span><span class="sxs-lookup"><span data-stu-id="a3170-147">You can add check constraints and make relationships between tables in Diagram Designer.</span></span>  
  
#### <a name="to-create-check-constraints"></a><span data-ttu-id="a3170-148">So erstellen Sie CHECK-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a3170-148">To create check constraints</span></span>  
  
1.  <span data-ttu-id="a3170-149">Klicken Sie in `Table1`mit der rechten Maustaste in die `T1col3` -Zeile, und wählen Sie **CHECK-Einschränkungen**aus.</span><span class="sxs-lookup"><span data-stu-id="a3170-149">In `Table1`, right-click the `T1col3` row and choose **Check Constraints**.</span></span>  
  
     <span data-ttu-id="a3170-150">Das Dialogfeld **CHECK-Einschränkungen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3170-150">The **Check Constraints** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="a3170-151">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a3170-151">Click **Add**.</span></span>  
  
     <span data-ttu-id="a3170-152">In der Liste **CHECK-Einschränkung (ausgewählt)** wird eine neue Einschränkung mit dem Standardnamen `CK_Table1`angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3170-152">A new constraint appears in the **Selected Check Constraint** list, with the default name `CK_Table1`.</span></span>  
  
3.  <span data-ttu-id="a3170-153">Wählen Sie im Raster die **Ausdruck** -Zeile aus, und klicken Sie auf die Schaltfläche mit den Auslassungspunkten.</span><span class="sxs-lookup"><span data-stu-id="a3170-153">Select the **Expression** row in the grid and click the ellipsis button.</span></span>  
  
     <span data-ttu-id="a3170-154">Das Dialogfeld **CHECK-Einschränkungsausdruck** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3170-154">The **Check Constraint Expression** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="a3170-155">Geben Sie `T1col3 > 5` ein und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3170-155">Type `T1col3 > 5` and click **OK**.</span></span>  
  
     <span data-ttu-id="a3170-156">`Table1` verfügt jetzt über die Einschränkung, dass alle in `T1col3` eingegebenen Werte größer als 5 sein müssen.</span><span class="sxs-lookup"><span data-stu-id="a3170-156">`Table1` now has a constraint that all values entered into `T1col3` must be greater than 5.</span></span>  
  
5.  <span data-ttu-id="a3170-157">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="a3170-157">Click **Close**.</span></span>  
  
#### <a name="to-create-relationships-between-tables"></a><span data-ttu-id="a3170-158">So erstellen Sie Beziehungen zwischen Tabellen</span><span class="sxs-lookup"><span data-stu-id="a3170-158">To create relationships between tables</span></span>  
  
1.  <span data-ttu-id="a3170-159">Erstellen Sie im Datenbank-Designer eine neue Tabelle mit dem Namen `Table2` und mit folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="a3170-159">Create a new table in Diagram designer named `Table2` with the following columns:</span></span>  
  
    |<span data-ttu-id="a3170-160">**Spaltenname**</span><span class="sxs-lookup"><span data-stu-id="a3170-160">**Column Name**</span></span>|<span data-ttu-id="a3170-161">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="a3170-161">**Data Type**</span></span>|<span data-ttu-id="a3170-162">**NULL-Werte zulassen**</span><span class="sxs-lookup"><span data-stu-id="a3170-162">**Allow Nulls**</span></span>|  
    |---------------------|-------------------|---------------------|  
    |`T2col1`|`int`|<span data-ttu-id="a3170-163">nicht aktiviert</span><span class="sxs-lookup"><span data-stu-id="a3170-163">not checked</span></span>|  
    |`T2col2`|`varchar(50)`|<span data-ttu-id="a3170-164">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="a3170-164">checked</span></span>|  
    |`T2col3`|`xml`|<span data-ttu-id="a3170-165">Aktiviert</span><span class="sxs-lookup"><span data-stu-id="a3170-165">checked</span></span>|  
  
    > [!NOTE]  
    >  <span data-ttu-id="a3170-166">Die Spalten in einer Fremdschlüsselbeziehung, die sich auf der Seite des Primärschlüssels befinden, müssen Teil eines Primärschlüssels oder einer Unique-Einschränkung sein.</span><span class="sxs-lookup"><span data-stu-id="a3170-166">The columns on the primary key side of a foreign key relationship must participate in either a Primary Key or a Unique Constraint.</span></span>  
  
2.  <span data-ttu-id="a3170-167">Ziehen Sie `T2col1` in `T1col1`.</span><span class="sxs-lookup"><span data-stu-id="a3170-167">Drag `T2col1` to `T1col1`.</span></span>  
  
     <span data-ttu-id="a3170-168">Es werden zwei Dialogfelder angezeigt: **Fremdschlüsselbeziehung** im Hintergrund und **Tabellen und Spalten** im Vordergrund.</span><span class="sxs-lookup"><span data-stu-id="a3170-168">Two dialog boxes appear: **Foreign Key Relationship** in the background and **Tables and Columns** in the foreground.</span></span>  
  
3.  <span data-ttu-id="a3170-169">Klicken Sie auf **OK** , um die neue Beziehung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a3170-169">Click **OK** to save the new relationship.</span></span>  
  
4.  <span data-ttu-id="a3170-170">Klicken Sie erneut auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="a3170-170">Click **OK** again.</span></span>  
  
## <a name="creating-indexes"></a><span data-ttu-id="a3170-171">Erstellen von Indizes</span><span class="sxs-lookup"><span data-stu-id="a3170-171">Creating Indexes</span></span>  
 <span data-ttu-id="a3170-172">Sie können für die meisten Datentypen (einschließlich XML) Indizes erstellen.</span><span class="sxs-lookup"><span data-stu-id="a3170-172">You can create indexes on most types of data, including XML.</span></span>  
  
#### <a name="to-create-a-standard-index"></a><span data-ttu-id="a3170-173">So erstellen Sie einen Standardindex</span><span class="sxs-lookup"><span data-stu-id="a3170-173">To create a standard index</span></span>  
  
1.  <span data-ttu-id="a3170-174">Klicken Sie mit der rechten Maustaste auf `Table1` , und wählen Sie **Indizes/Schlüssel**aus.</span><span class="sxs-lookup"><span data-stu-id="a3170-174">Right-click `Table1` and choose **Indexes/Keys**.</span></span>  
  
     <span data-ttu-id="a3170-175">Das Dialogfeld **Indizes/Schlüssel** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3170-175">The **Indexes/Keys** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="a3170-176">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a3170-176">Click **Add**.</span></span>  
  
     <span data-ttu-id="a3170-177">In der Liste **Primärschlüssel/eindeutiger Schlüssel oder Index (ausgewählt)** wird ein neuer Index mit einem Standardnamen wie `IX_Table1`angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3170-177">A new index appears in the **Selected Primary/Unique Key or Index** list, with a default name similar to `IX_Table1`.</span></span>  
  
3.  <span data-ttu-id="a3170-178">Wählen Sie die **Spalten** -Zeile aus, und klicken Sie auf die Schaltfläche mit den Auslassungspunkten.</span><span class="sxs-lookup"><span data-stu-id="a3170-178">Select the **Columns** row and click the ellipsis button.</span></span>  
  
     <span data-ttu-id="a3170-179">Das Dialogfeld **Indexspalten** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3170-179">The **Index Columns** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="a3170-180">Klicken Sie auf den Dropdownpfeil unter **Spaltenname** , und wählen Sie `T1col2`aus.</span><span class="sxs-lookup"><span data-stu-id="a3170-180">Click the drop-down arrow under **Column Name** and select `T1col2`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a3170-181">Sie können diesem Index zusätzliche Spalten hinzufügen, indem Sie die Zelle unter `T1col2` auswählen und einen anderen Spaltennamen auswählen.</span><span class="sxs-lookup"><span data-stu-id="a3170-181">You may add additional columns to this index by selecting the cell below `T1col2` and choosing another column name.</span></span>  
  
5.  <span data-ttu-id="a3170-182">Klicken Sie auf **OK** , um diesen Index zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a3170-182">Click **OK** to save this index.</span></span>  
  
6.  <span data-ttu-id="a3170-183">Klicken Sie im Dialogfeld **Indizes/Schlüssel** auf **Schließen** .</span><span class="sxs-lookup"><span data-stu-id="a3170-183">Click **Close** in the **Indexes/Keys** dialog box.</span></span>  
  
#### <a name="to-create-an-xml-index"></a><span data-ttu-id="a3170-184">So erstellen Sie einen XML-Index</span><span class="sxs-lookup"><span data-stu-id="a3170-184">To create an XML index</span></span>  
  
1.  <span data-ttu-id="a3170-185">Klicken Sie mit der rechten Maustaste auf `T2col1` , und wählen Sie **Primärschlüssel festlegen**aus.</span><span class="sxs-lookup"><span data-stu-id="a3170-185">Right-click `T2col1` and choose **Set Primary Key**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a3170-186">Voraussetzung für das Hinzufügen eines XML-Index ist es, dass eine andere Spalte in der Tabelle als gruppierter Primärschlüssel festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="a3170-186">Adding an XML index requires that another column in the table be set as a clustered primary key.</span></span>  
  
2.  <span data-ttu-id="a3170-187">Klicken Sie mit der rechten Maustaste auf die `T2col3` -Zeile in `Table2` , und wählen Sie **XML-Indizes**aus.</span><span class="sxs-lookup"><span data-stu-id="a3170-187">Right-click the `T2col3` row in `Table2` and select **XML Indexes**.</span></span>  
  
     <span data-ttu-id="a3170-188">Das Dialogfeld **XML-Indizes** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3170-188">The **XML Indexes** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="a3170-189">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a3170-189">Click **Add**.</span></span>  
  
     <span data-ttu-id="a3170-190">Ein XML-Index mit Standardwerten wird der Liste **XML-Index (ausgewählt)** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a3170-190">An XML index with default values will be added to the **Selected XML Index** list.</span></span>  
  
4.  <span data-ttu-id="a3170-191">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="a3170-191">Click **Close**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a3170-192">XML-Indizes werden auf Spaltenbasis erstellt.</span><span class="sxs-lookup"><span data-stu-id="a3170-192">XML indexes are created per-column.</span></span> <span data-ttu-id="a3170-193">Dabei ist der erste XML-Index primär, und alle weiteren Indizes sind sekundär.</span><span class="sxs-lookup"><span data-stu-id="a3170-193">The first XML index is primary; any additional indexes are secondary.</span></span>  
  
## <a name="saving-the-diagram"></a><span data-ttu-id="a3170-194">Speichern des Diagramms</span><span class="sxs-lookup"><span data-stu-id="a3170-194">Saving the Diagram</span></span>  
 <span data-ttu-id="a3170-195">Sämtliche von Ihnen an einem Diagramm vorgenommenen Änderungen werden erst nach dem Speichern des Diagramms an die Datenbank gesendet.</span><span class="sxs-lookup"><span data-stu-id="a3170-195">All of the changes you make to a diagram are not posted to the database until you save it.</span></span> <span data-ttu-id="a3170-196">Wenn Probleme oder Konflikte auftreten, wird ein Dialogfeld mit weiteren Informationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3170-196">If there are problems or conflicts, a dialog box appears with more information.</span></span>  
  
#### <a name="to-save-a-database-diagram"></a><span data-ttu-id="a3170-197">So speichern Sie ein Datenbankdiagramm</span><span class="sxs-lookup"><span data-stu-id="a3170-197">To save a database diagram</span></span>  
  
1.  <span data-ttu-id="a3170-198">Wählen Sie im Menü **Datei** die Option **Diagramm1 speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="a3170-198">On the **File** menu, select **Save Diagram1**.</span></span>  
  
     <span data-ttu-id="a3170-199">Das Dialogfeld **Speichern** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a3170-199">The **Save** dialog box appears.</span></span> <span data-ttu-id="a3170-200">Wenn **Warnung bei betroffenen Tabellen** aktiviert ist, werden Informationen zu neuen oder geänderten Tabellen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a3170-200">If **Warn about Tables Affected** is selected, information about new or changed tables is listed.</span></span>  
  
2.  <span data-ttu-id="a3170-201">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3170-201">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="a3170-202">Wenn Fehler aufgetreten sind, wird das Dialogfeld **Benachrichtigung nach dem Speichervorgang** angezeigt, das die Fehler und deren Ursachen enthält.</span><span class="sxs-lookup"><span data-stu-id="a3170-202">If any errors occurred, the **Post-Save Notifications** dialog box appears with the errors and their causes.</span></span> <span data-ttu-id="a3170-203">Beheben Sie die Fehler, und speichern Sie das Diagramm anschließend erneut.</span><span class="sxs-lookup"><span data-stu-id="a3170-203">Fix the errors and save the diagram again.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a3170-204">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a3170-204">Next Steps</span></span>  
 <span data-ttu-id="a3170-205">Hierbei handelt es sich um ein einfaches Diagramm, das nur zwei vorhandene und zwei neue Tabellen enthält. Damit wird jedoch das Potenzial zur Diagrammdarstellung einer vorhandenen Datenbank oder zur visuellen Erstellung eines neuen Schemas veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a3170-205">This is a basic diagram with just two existing and two new tables, but it illustrates the potential for diagramming an existing database or creating a new schema visually.</span></span> <span data-ttu-id="a3170-206">Mit folgenden Funktionen können Sie Ihre Fähigkeiten vertiefen:</span><span class="sxs-lookup"><span data-stu-id="a3170-206">Suggestions for more exploration include:</span></span>  
  
-   <span data-ttu-id="a3170-207">Erstellen neuer Diagramme mit Gruppen verbundener Tabellen</span><span class="sxs-lookup"><span data-stu-id="a3170-207">Create new diagrams containing groups of related tables</span></span>  
  
-   <span data-ttu-id="a3170-208">Anpassen der für jede Tabelle angezeigten Informationsmenge</span><span class="sxs-lookup"><span data-stu-id="a3170-208">Customize the amount of information shown for each table</span></span>  
  
-   <span data-ttu-id="a3170-209">Ändern des Layouts und Hinzufügen von Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="a3170-209">Change the layout and add annotations</span></span>  
  
-   <span data-ttu-id="a3170-210">Kopieren des Diagramms in eine Bitmap</span><span class="sxs-lookup"><span data-stu-id="a3170-210">Copy the diagram to a bitmap</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3170-211">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a3170-211">See Also</span></span>  
 <span data-ttu-id="a3170-212">[Passen Sie die Menge der Informationen an, die in Diagrammen &#40;Visual Database Tools angezeigt werden&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a3170-212">[Customize the Amount of Information Displayed in Diagrams &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="a3170-213">[Einrichten des Daten Bank Diagramm-Designers &#40;Visual Database Tools&#41;](set-up-database-diagram-designer-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a3170-213">[Set Up Database Diagram Designer &#40;Visual Database Tools&#41;](set-up-database-diagram-designer-visual-database-tools.md) </span></span>  
 <span data-ttu-id="a3170-214">[Hinzufügen von Tabellen zu Diagrammen &#40;Visual Database Tools&#41;](add-tables-to-diagrams-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a3170-214">[Add Tables to Diagrams &#40;Visual Database Tools&#41;](add-tables-to-diagrams-visual-database-tools.md) </span></span>  
 <span data-ttu-id="a3170-215">[Erstellen von Beziehungen zwischen Tabellen in einem Diagramm &#40;Visual Database Tools&#41;](create-relationships-between-tables-on-a-diagram-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a3170-215">[Create Relationships Between Tables on a Diagram &#40;Visual Database Tools&#41;](create-relationships-between-tables-on-a-diagram-visual-database-tools.md) </span></span>  
 <span data-ttu-id="a3170-216">[Erstellen von XML-Indizes](../../relational-databases/xml/create-xml-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="a3170-216">[Create XML Indexes](../../relational-databases/xml/create-xml-indexes.md) </span></span>  
 <span data-ttu-id="a3170-217">[Kopieren eines Images eines Daten Bank Diagramms in die Zwischenablage &#40;Visual Database Tools&#41;](copy-an-image-of-a-database-diagram-to-the-clipboard-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a3170-217">[Copy an Image of a Database Diagram to the Clipboard &#40;Visual Database Tools&#41;](copy-an-image-of-a-database-diagram-to-the-clipboard-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="a3170-218">Verwenden von Diagrammlayout &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="a3170-218">Work with Diagram Layout &#40;Visual Database Tools&#41;</span></span>](work-with-diagram-layout-visual-database-tools.md)  
  
  
