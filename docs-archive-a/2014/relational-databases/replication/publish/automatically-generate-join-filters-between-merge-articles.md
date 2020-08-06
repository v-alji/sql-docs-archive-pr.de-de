---
title: Automatisches Generieren einer Reihe von Joinfiltern zwischen Mergeartikeln (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- automatic join filter generation
- join filters
ms.assetid: 7ef419f4-c17f-42a5-9068-174a3ec08941
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4bfdbf93aad134e4da873a6aade307754a2637e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607644"
---
# <a name="automatically-generate-a-set-of-join-filters-between-merge-articles-sql-server-management-studio"></a><span data-ttu-id="9bdf7-102">Automatisches Generieren einer Reihe von Joinfiltern zwischen Mergeartikeln (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="9bdf7-102">Automatically Generate a Set of Join Filters Between Merge Articles (SQL Server Management Studio)</span></span>
  <span data-ttu-id="9bdf7-103">Mithilfe des Assistenten für neue Veröffentlichung auf der Seite **Tabellenzeilen filtern** oder des Dialogfelds **Veröffentlichungseigenschaften - \<Publication>** auf der Seite **Zeilen filtern** können Sie eine Reihe von Joinfiltern automatisch generieren.</span><span class="sxs-lookup"><span data-stu-id="9bdf7-103">Automatically generate a set of join filters on the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="9bdf7-104">Weitere Informationen zum Verwenden des Assistenten sowie Zugriff auf das Dialogfeld finden Sie unter [Erstellen einer Veröffentlichung](create-a-publication.md) und [Anzeigen und Ändern von Veröffentlichungseigenschaften](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="9bdf7-104">For more information about using the wizard and accessing the dialog box, see [Create a Publication](create-a-publication.md) and [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9bdf7-105">Wenn Sie nach dem Initialisieren von Abonnements für die Veröffentlichung automatisch eine Reihe von Joinfiltern im Dialogfeld **Veröffentlichungseigenschaften - \<Publication>** generieren, müssen Sie eine neue Momentaufnahme generieren und nach der Änderung alle Abonnements erneut initialisieren.</span><span class="sxs-lookup"><span data-stu-id="9bdf7-105">If you automatically generate a set of join filters in the **Publication Properties - \<Publication>** dialog box after subscriptions to the publication have been initialized, you must generate a new snapshot and reinitialize all subscriptions after making the change.</span></span> <span data-ttu-id="9bdf7-106">Weitere Informationen zum Ändern von Eigenschaften finden Sie unter [Ändern von Veröffentlichungs- und Artikeleigenschaften](change-publication-and-article-properties.md).</span><span class="sxs-lookup"><span data-stu-id="9bdf7-106">For more information about requirements for property changes, see [Change Publication and Article Properties](change-publication-and-article-properties.md).</span></span>  
  
 <span data-ttu-id="9bdf7-107">Joinfilter können manuell für eine Gruppe von Tabellen erstellt werden. Die Filter können auch automatisch durch die Replikation anhand der Primärschlüssel/Fremdschlüssel-Beziehungen generiert werden, die für die Tabellen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="9bdf7-107">Join filters can be created manually for a set of tables, or replication can generate the filters automatically based on the foreign key to primary key relationships defined on the tables.</span></span> <span data-ttu-id="9bdf7-108">Weitere Informationen zum manuellen Definieren von Joinfiltern finden Sie unter [Definieren und Ändern eines Verknüpfungsfilters zwischen Mergeartikeln](define-and-modify-a-join-filter-between-merge-articles.md).</span><span class="sxs-lookup"><span data-stu-id="9bdf7-108">For more information about creating join filters manually, see [Define and Modify a Join Filter Between Merge Articles](define-and-modify-a-join-filter-between-merge-articles.md).</span></span>  
  
### <a name="to-automatically-generate-a-set-of-join-filters-between-merge-articles"></a><span data-ttu-id="9bdf7-109">So generieren Sie automatisch eine Reihe von Joinfiltern zwischen Mergeartikeln</span><span class="sxs-lookup"><span data-stu-id="9bdf7-109">To automatically generate a set of join filters between merge articles</span></span>  
  
1.  <span data-ttu-id="9bdf7-110">Klicken Sie im Assistenten für neue Veröffentlichung auf der Seite **Tabellenzeilen filtern** oder im Dialogfeld **Veröffentlichungseigenschaften - \<Publication>** auf der Seite **Zeilen filtern** auf **Hinzufügen**, und klicken Sie dann auf **Filter automatisch generieren**.</span><span class="sxs-lookup"><span data-stu-id="9bdf7-110">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, click **Add**, and then click **Automatically Generate Filters**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9bdf7-111">Beim automatischen Generieren von Filtern werden alle vorhandenen Zeilenfilter oder Joinfilter in der Veröffentlichung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="9bdf7-111">Automatically generating filters deletes any existing row filters or join filters in the publication.</span></span> <span data-ttu-id="9bdf7-112">Sie können nach dem automatischen Generieren einer Reihe von Filtern weitere Filter hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9bdf7-112">You can add filters after automatically generating a set of filters.</span></span>  
  
2.  <span data-ttu-id="9bdf7-113">Folgen Sie zum Erstellen eines Zeilenfilters dem Verfahren im Dialogfeld **Filter generieren** .</span><span class="sxs-lookup"><span data-stu-id="9bdf7-113">Follow the process in the **Generate Filters** dialog box to create a row filter.</span></span> <span data-ttu-id="9bdf7-114">Der Zeilenfilter wird dann basierend auf den aufgeführt automatisch auf die Tabellen ausgeweitet, die mit der gefilterten Tabelle verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="9bdf7-114">The row filter is then extended to the tables related to the filtered table through primary key and foreign key relationships.</span></span>  
  
    1.  <span data-ttu-id="9bdf7-115">Wählen Sie im Dropdown-Listenfeld eine Tabelle aus, die Sie filtern möchten.</span><span class="sxs-lookup"><span data-stu-id="9bdf7-115">Select a table to filter from the drop-down list box.</span></span>  
  
    2.  <span data-ttu-id="9bdf7-116">Erstellen Sie im Textfeld **Filteranweisung** eine Filteranweisung.</span><span class="sxs-lookup"><span data-stu-id="9bdf7-116">Create a filter statement in the **Filter statement** text box.</span></span> <span data-ttu-id="9bdf7-117">Sie können den Text direkt in den Textbereich eingeben, und Sie können Spalten auch mit Drag und Drop aus dem Listenfeld **Spalten** einfügen.</span><span class="sxs-lookup"><span data-stu-id="9bdf7-117">You can type directly in the text area, and you can also drag and drop columns from the **Columns** list box.</span></span>  
  
         <span data-ttu-id="9bdf7-118">Der Textbereich **Filteranweisung** enthält den Standardtext im folgenden Format:</span><span class="sxs-lookup"><span data-stu-id="9bdf7-118">The **Filter statement** text area includes the default text, which is in the form of:</span></span>  
  
        ```  
        SELECT <published_columns> FROM [tableowner].[tablename] WHERE  
        ```  
  
         <span data-ttu-id="9bdf7-119">Der Standardtext kann nicht geändert werden. Geben Sie die Filterklausel für einen statischen Zeilenfilter oder einen parametrisierten Zeilenfilter nach dem WHERE-Schlüsselwort mithilfe der standardmäßigen SQL-Syntax ein.</span><span class="sxs-lookup"><span data-stu-id="9bdf7-119">The default text cannot be changed; type the filter clause for a static row filter or a parameterized row filter after the WHERE keyword using standard SQL syntax.</span></span> <span data-ttu-id="9bdf7-120">Die vollständige Filterklausel für einen parametrisierten Zeilenfilter würde wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="9bdf7-120">The complete filter clause for a parameterized row filter would look like:</span></span>  
  
        ```  
        SELECT <published_columns> FROM [HumanResources].[Employee] WHERE LoginID = SUSER_SNAME()  
        ```  
  
         <span data-ttu-id="9bdf7-121">Verwenden Sie einen zweiteiligen Namen für die WHERE-Klausel, drei- oder vierteilige Namen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9bdf7-121">The WHERE clause should use two-part naming; three-part naming and four-part naming are not supported.</span></span>  
  
    3.  <span data-ttu-id="9bdf7-122">Geben Sie Filteroptionen an.</span><span class="sxs-lookup"><span data-stu-id="9bdf7-122">Specify filter options.</span></span>  
  
         <span data-ttu-id="9bdf7-123">Wählen Sie die Option aus, mit der angegeben wird, wie Daten für mehrere Abonnenten freigegeben werden: **Eine Zeile aus dieser Tabelle wird an mehrere Abonnements gesendet** oder **Eine Zeile aus dieser Tabelle wird nur an ein Abonnement gesendet**.</span><span class="sxs-lookup"><span data-stu-id="9bdf7-123">Select the option that matches how data will be shared among Subscribers: **A row from this table will go to multiple subscriptions** or **A row from this table will go to only one subscription**.</span></span> <span data-ttu-id="9bdf7-124">Wenn Sie **Eine Zeile aus dieser Tabelle wird nur an ein Abonnement gesendet**auswählen, kann die Mergereplikation die Leistung optimieren, da weniger Metadaten gespeichert und verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="9bdf7-124">If you select **A row from this table will go to only one subscription**, merge replication can optimize performance by storing and processing less metadata.</span></span> <span data-ttu-id="9bdf7-125">Sie müssen jedoch sicherstellen, dass die Daten so partitioniert werden, dass eine Zeile nicht für mehrere Abonnenten repliziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="9bdf7-125">However, you must ensure that the data is partitioned in such a way that a row cannot be replicated to more than one Subscriber.</span></span> <span data-ttu-id="9bdf7-126">Weitere Informationen finden Sie im Abschnitt zum Festlegen von Partitionsoptionen unter [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="9bdf7-126">For more information, see the section "Setting 'partition options'" in the topic [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="9bdf7-127">Der von Ihnen angegebene Filter wird analysiert und für die Tabelle in der SELECT-Klausel ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9bdf7-127">The filter you specified is parsed and run against the table in the SELECT clause.</span></span> <span data-ttu-id="9bdf7-128">Wenn die Filteranweisung Syntaxfehler oder andere Probleme enthält, werden Sie benachrichtigt und können die Filteranweisung bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="9bdf7-128">If the filter statement contains syntax errors or other problems, you will be notified and will be able to edit the filter statement.</span></span>  
  
     <span data-ttu-id="9bdf7-129">Nach der Analyse der Anweisung erstellt die Replikation die nötigen Joinfilter und zeigt sie auf der Seite **Tabellenzeilen filtern** oder der Seite **Zeilen filtern** im Bereich **Gefilterte Tabellen** an.</span><span class="sxs-lookup"><span data-stu-id="9bdf7-129">After the statement is parsed, replication creates the necessary join filters and displays them in the **Filtered Tables** pane on the **Filter Table Rows** or **Filter Rows** page.</span></span> <span data-ttu-id="9bdf7-130">Wenn Sie Filter im Assistenten für neue Veröffentlichung generieren und noch nicht den Verteiler für den Verleger konfiguriert haben, für den dieser Assistent ausgeführt wird, werden Sie zum Konfigurieren des Verteilers aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="9bdf7-130">If you are generating filters from the New Publication Wizard and have not yet configured the Distributor for the Publisher against which this wizard is running, you are prompted to configure it.</span></span>  
  
4.  <span data-ttu-id="9bdf7-131">Wenn Sie sich im Dialogfeld **Veröffentlichungseigenschaften - \<Publication>** befinden, klicken Sie auf **OK**, um die Einstellungen zu speichern und das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="9bdf7-131">If you are in the **Publication Properties - \<Publication>** dialog box, click **OK** to save and close the dialog box.</span></span>  
  
### <a name="to-modify-a-filter-that-was-automatically-generated"></a><span data-ttu-id="9bdf7-132">So ändern Sie einen automatisch generierten Filter</span><span class="sxs-lookup"><span data-stu-id="9bdf7-132">To modify a filter that was automatically generated</span></span>  
  
1.  <span data-ttu-id="9bdf7-133">Wählen Sie auf der Seite **Tabellenzeilen filtern** des Assistenten für neue Veröffentlichung oder auf der Seite **Filterzeilen** von **Veröffentlichungseigenschaften - \<Publication>** einen Filter im Bereich **gefilterte Tabellen**, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="9bdf7-133">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, select a filter in the **Filtered Tables** pane, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="9bdf7-134">Ändern Sie den Filter im Dialogfeld **Filter bearbeiten** oder **Join bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="9bdf7-134">In the **Edit Filter** or **Edit Join** dialog box, modify the filter.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-filter-that-was-automatically-generated"></a><span data-ttu-id="9bdf7-135">So löschen Sie einen automatisch generierten Filter</span><span class="sxs-lookup"><span data-stu-id="9bdf7-135">To delete a filter that was automatically generated</span></span>  
  
1.  <span data-ttu-id="9bdf7-136">Wählen Sie auf der Seite **Tabellenzeilen filtern** des Assistenten für neue Veröffentlichung oder der Seite **Filterzeilen** von **Veröffentlichungseigenschaften - \<Publication>** einen Filter im Bereich **gefilterte Tabellen**, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="9bdf7-136">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, select a filter in the **Filtered Tables** pane, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bdf7-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9bdf7-137">See Also</span></span>  
 <span data-ttu-id="9bdf7-138">[Join Filters](../merge/join-filters.md) </span><span class="sxs-lookup"><span data-stu-id="9bdf7-138">[Join Filters](../merge/join-filters.md) </span></span>  
 [<span data-ttu-id="9bdf7-139">Parametrisierte Zeilenfilter</span><span class="sxs-lookup"><span data-stu-id="9bdf7-139">Parameterized Row Filters</span></span>](../merge/parameterized-filters-parameterized-row-filters.md)  
  
  