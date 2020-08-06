---
title: Verwalten von Rollen mit SSMS (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 652faac0-1cfc-438b-8119-2f4b090a2381
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4ee34d5e75d5d4ce3679d46d29af3215852d2bbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696165"
---
# <a name="manage-roles-by-using-ssms-ssas-tabular"></a><span data-ttu-id="c438b-102">Verwalten von Rollen mit SSMS (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="c438b-102">Manage Roles by using SSMS (SSAS Tabular)</span></span>
  <span data-ttu-id="c438b-103">Sie können Rollen für ein bereitgestelltes tabellarisches Modell mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]erstellen, bearbeiten und verwalten.</span><span class="sxs-lookup"><span data-stu-id="c438b-103">You can create, edit, and manage roles for a deployed tabular model by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="c438b-104">Aufgaben in diesem Thema:</span><span class="sxs-lookup"><span data-stu-id="c438b-104">Tasks in this topic:</span></span>  
  
-   [<span data-ttu-id="c438b-105">So erstellen Sie eine neue Rolle</span><span class="sxs-lookup"><span data-stu-id="c438b-105">To create a new role</span></span>](#bkmk_new_role)  
  
-   [<span data-ttu-id="c438b-106">So kopieren Sie eine Rolle</span><span class="sxs-lookup"><span data-stu-id="c438b-106">To copy a role</span></span>](#bkmk_copy_role)  
  
-   [<span data-ttu-id="c438b-107">So bearbeiten Sie eine Rolle</span><span class="sxs-lookup"><span data-stu-id="c438b-107">To edit a role</span></span>](#bkmk_edit_role)  
  
-   [<span data-ttu-id="c438b-108">So löschen Sie eine Rolle</span><span class="sxs-lookup"><span data-stu-id="c438b-108">To delete a role</span></span>](#bkmk_deletet_role)  
  
> [!CAUTION]  
>  <span data-ttu-id="c438b-109">Wenn ein tabellarisches Modellprojekt, dessen Rollen mithilfe des Rollen-Managers in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] definiert wurden, erneut bereitgestellt wird, dann werden die in einem bereitgestellten tabellarischen Modell definierten Rollen überschrieben.</span><span class="sxs-lookup"><span data-stu-id="c438b-109">Re-deploying a tabular model project with roles defined by using Role Manager in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] will overwrite roles defined in a deployed tabular model.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="c438b-110">Wenn Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] verwenden, um eine Arbeitsbereichsdatenbank für tabellarische Modelle zu verwalten, während das Modellprojekt in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] geöffnet ist, kann die Datei Model.bim beschädigt werden.</span><span class="sxs-lookup"><span data-stu-id="c438b-110">Using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to manage a tabular model workspace database while the model project is open in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] may cause the Model.bim file to become corrupted.</span></span> <span data-ttu-id="c438b-111">Wenn Sie Rollen für eine Arbeitsbereichsdatenbank für tabellarische Modelle erstellen und verwalten, verwenden Sie den Rollen-Manager in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c438b-111">When creating and managing roles for a tabular model workspace database, use Role Manager in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
###  <a name="to-create-a-new-role"></a><a name="bkmk_new_role"></a><span data-ttu-id="c438b-112">So erstellen Sie eine neue Rolle</span><span class="sxs-lookup"><span data-stu-id="c438b-112">To create a new role</span></span>  
  
1.  <span data-ttu-id="c438b-113">Erweitern Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]die tabellarische Modelldatenbank, für die Sie eine neue Rolle erstellen möchten, klicken Sie mit der rechten Maustaste auf **Rollen**, und klicken Sie dann auf **Neue Rolle**.</span><span class="sxs-lookup"><span data-stu-id="c438b-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the tabular model database for which you want to create a new role, then right click on **Roles**, and then click **New Role**.</span></span>  
  
2.  <span data-ttu-id="c438b-114">Klicken Sie im Dialogfeld **Rolle erstellen** im Fenster "Seite auswählen" auf **Allgemein**.</span><span class="sxs-lookup"><span data-stu-id="c438b-114">In the **Create Role** dialog box, in the Select a page window, click **General**.</span></span>  
  
3.  <span data-ttu-id="c438b-115">Geben Sie im Fenster für allgemeine Einstellungen im Feld **Name** einen Namen für die Rolle ein.</span><span class="sxs-lookup"><span data-stu-id="c438b-115">In the general settings window, in the **Name** field, type a name for the role.</span></span>  
  
     <span data-ttu-id="c438b-116">Der Name der Standardrolle wird für jede neue Rolle automatisch inkrementell erhöht.</span><span class="sxs-lookup"><span data-stu-id="c438b-116">By default, the name of the default role will be incrementally numbered for each new role.</span></span> <span data-ttu-id="c438b-117">Es wird empfohlen, einen Namen einzugeben, durch den der Elementtyp eindeutig identifiziert wird, beispielsweise "Finance Managers" oder "Human Resources Specialists".</span><span class="sxs-lookup"><span data-stu-id="c438b-117">It is recommended you type a name that clearly identifies the member type, for example, Finance Managers or Human Resources Specialists.</span></span>  
  
4.  <span data-ttu-id="c438b-118">Aktivieren Sie in **Legen Sie die Datenbankberechtigung für diese Rolle fest**eine der folgenden Berechtigungsoptionen:</span><span class="sxs-lookup"><span data-stu-id="c438b-118">In **Set the database permissions for this role**, select one of the following permissions options:</span></span>  
  
    |<span data-ttu-id="c438b-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="c438b-119">Permission</span></span>|<span data-ttu-id="c438b-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c438b-120">Description</span></span>|  
    |----------------|-----------------|  
    |<span data-ttu-id="c438b-121">**Vollzugriff (Administrator)**</span><span class="sxs-lookup"><span data-stu-id="c438b-121">**Full control (Administrator)**</span></span>|<span data-ttu-id="c438b-122">Mitglieder können Änderungen am Modellschema vornehmen und alle Daten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c438b-122">Members can make modifications to the model schema and can view all data.</span></span>|  
    |<span data-ttu-id="c438b-123">**Datenbank verarbeiten**</span><span class="sxs-lookup"><span data-stu-id="c438b-123">**Process database**</span></span>|<span data-ttu-id="c438b-124">Mitglieder können die Vorgänge Verarbeiten und Alles verarbeiten ausführen.</span><span class="sxs-lookup"><span data-stu-id="c438b-124">Members can run Process and Process All operations.</span></span> <span data-ttu-id="c438b-125">Sie können weder das Modellschema ändern noch Daten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c438b-125">Cannot modify the model schema and cannot view data.</span></span>|  
    |<span data-ttu-id="c438b-126">**Lesen**</span><span class="sxs-lookup"><span data-stu-id="c438b-126">**Read**</span></span>|<span data-ttu-id="c438b-127">Mitglieder dürfen Daten (basierend auf Zeilenfiltern) anzeigen, doch sie können keine Änderungen am Modellschema vornehmen.</span><span class="sxs-lookup"><span data-stu-id="c438b-127">Members are allowed to view data (based on row filters) but cannot make any changes to the model schema.</span></span>|  
  
5.  <span data-ttu-id="c438b-128">Klicken Sie im Dialogfeld **Rolle erstellen** im Fenster "Seite auswählen" auf **Mitgliedschaft**.</span><span class="sxs-lookup"><span data-stu-id="c438b-128">In the **Create Role** dialog box, in the Select a page window, click **Membership**.</span></span>  
  
6.  <span data-ttu-id="c438b-129">Klicken Sie im Mitgliedschaftseinstellungen-Fenster auf **Hinzufügen**, und fügen Sie dann im Dialogfeld **Benutzer oder Gruppen auswählen** die Windows-Benutzer oder die Gruppen hinzu, die Sie als Elemente hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="c438b-129">In the membership settings window, click **Add**, and then in the **Select Users or Groups** dialog box, add the Windows users or groups you want to add as members.</span></span>  
  
7.  <span data-ttu-id="c438b-130">Wenn die Rolle, die Sie erstellen, Leseberechtigungen aufweist, können Sie Zeilenfilter für jede beliebige Tabelle hinzufügen, in der eine DAX-Formel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c438b-130">If the role you are creating has Read permissions, you can add row filters for any table using a DAX formula.</span></span> <span data-ttu-id="c438b-131">Um Zeilen Filter hinzuzufügen, klicken Sie im Dialogfeld \*\*Rollen Eigenschaften- \<rolename> \*\* unter **Seite auswählen**auf **Zeilen Filter**.</span><span class="sxs-lookup"><span data-stu-id="c438b-131">To add row filters, in the **Role Properties - \<rolename>** dialog box, in **Select a page**, click on **Row Filters**.</span></span>  
  
8.  <span data-ttu-id="c438b-132">Wählen Sie im Fenster Zeilen Filter eine Tabelle aus, klicken Sie dann auf das Feld **DAX-Filter** , und geben Sie dann im Feld **DAX- \<tablename> Filter** eine DAX-Formel ein.</span><span class="sxs-lookup"><span data-stu-id="c438b-132">In the row filters window, select a table, then click on the **DAX Filter** field, and then in the **DAX Filter - \<tablename>** field, type a DAX formula.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c438b-133">Das DAX-Filter- \<tablename> Feld enthält keinen AutoComplete-Abfrage-Editor oder Funktion zum Einfügen von Funktionen.</span><span class="sxs-lookup"><span data-stu-id="c438b-133">The DAX Filter - \<tablename> field does not contain an AutoComplete query editor or insert function feature.</span></span> <span data-ttu-id="c438b-134">Um beim Schreiben einer DAX-Formel die Funktion zum AutoVervollständigen verwenden zu können, müssen Sie in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]einen DAX-Formel-Editor verwenden.</span><span class="sxs-lookup"><span data-stu-id="c438b-134">To use AutoComplete when writing a DAX formula, you must use a DAX formula editor in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
9. <span data-ttu-id="c438b-135">Klicken Sie auf **OK** , um die Rolle zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c438b-135">Click **Ok** to save the role.</span></span>  
  
###  <a name="to-copy-a-role"></a><a name="bkmk_copy_role"></a> <span data-ttu-id="c438b-136">So kopieren Sie eine Rolle</span><span class="sxs-lookup"><span data-stu-id="c438b-136">To copy a role</span></span>  
  
1.  <span data-ttu-id="c438b-137">Erweitern Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]die tabellarische Modelldatenbank, die die Rolle enthält, die Sie kopieren möchten, und erweitern Sie dann **Rollen**. Klicken Sie mit der rechten Maustaste auf die Rolle, und klicken Sie dann auf **Duplizieren**.</span><span class="sxs-lookup"><span data-stu-id="c438b-137">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the tabular model database that contains the role you want to copy, then expand **Roles**, then right click on the role, and then click **Duplicate**.</span></span>  
  
###  <a name="to-edit-a-role"></a><a name="bkmk_edit_role"></a><span data-ttu-id="c438b-138">So bearbeiten Sie eine Rolle</span><span class="sxs-lookup"><span data-stu-id="c438b-138">To edit a role</span></span>  
  
-   <span data-ttu-id="c438b-139">Erweitern Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]die tabellarische Modelldatenbank, die die Rolle enthält, die Sie bearbeiten möchten, und erweitern Sie dann **Rollen**. Klicken Sie mit der rechten Maustaste auf die Rolle, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="c438b-139">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the tabular model database that contains the role you want to edit, then expand **Roles**, then right click on the role, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="c438b-140">Im Dialogfeld **Rollen Eigenschaften** \<rolename> können Sie Berechtigungen ändern, Mitglieder hinzufügen oder entfernen und Zeilen Filter hinzufügen/bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="c438b-140">In the **Role Properties** \<rolename> dialog box, you can change permissions, add or remove members, and add/edit row filters.</span></span>  
  
###  <a name="to-delete-a-role"></a><a name="bkmk_deletet_role"></a><span data-ttu-id="c438b-141">So löschen Sie eine Rolle</span><span class="sxs-lookup"><span data-stu-id="c438b-141">To delete a role</span></span>  
  
-   <span data-ttu-id="c438b-142">Erweitern Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]die tabellarische Modelldatenbank, die die Rolle enthält, die Sie löschen möchten, und erweitern Sie dann **Rollen**. Klicken Sie mit der rechten Maustaste auf die Rolle, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="c438b-142">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the tabular model database that contains the role you want to delete, then expand **Roles**, then right click on the role, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c438b-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c438b-143">See Also</span></span>  
 [<span data-ttu-id="c438b-144">Rollen &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="c438b-144">Roles &#40;SSAS Tabular&#41;</span></span>](roles-ssas-tabular.md)  
  
  
