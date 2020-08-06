---
title: Erstellen und Verwalten von Rollen (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.rolemanager.f1
- sql12.asvs.bidtoolset.roledb.f1
ms.assetid: e23d27a8-e968-4082-9dbe-963fc724b5d9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 335e0e311d97ea452449cd0c5d6550f6dbcca4f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609497"
---
# <a name="create-and-manage-roles-ssas-tabular"></a><span data-ttu-id="cf8c5-102">Erstellen und Verwalten von Rollen (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="cf8c5-102">Create and Manage Roles (SSAS Tabular)</span></span>
  <span data-ttu-id="cf8c5-103">Mit Rollen werden in tabellarischen Modellen Elementberechtigungen für ein Modell definiert.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-103">Roles, in tabular models, define member permissions for a model.</span></span> <span data-ttu-id="cf8c5-104">Rollen für ein Modellprojekt werden in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]im Dialogfeld Rollen-Manager definiert.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-104">Roles are defined for a model project by using the Role Manager dialog box in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="cf8c5-105">Nach der Bereitstellung eines Modells können die Rollen vom Datenbankadministrator in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-105">When a model is deployed, database administrators can manage roles by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="cf8c5-106">In den Aufgaben in diesem Thema wird beschrieben, wie Rollen während der Modellerstellung mithilfe des Dialogfelds Rollen-Manager in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]erstellt und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-106">The tasks in this topic describe how to create and manage roles during model authoring by using the Role Manager dialog box in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="cf8c5-107">Informationen zum Verwalten von Rollen in einer bereitgestellten Modelldatenbank finden Sie unter [Rollen tabellarischer Modelle &#40;SSAS – tabellarisch&#41;](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="cf8c5-107">For information about managing roles in a deployed model database, see [Tabular Model Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="cf8c5-108">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="cf8c5-108">Tasks</span></span>  
 <span data-ttu-id="cf8c5-109">Zum Erstellen, Bearbeiten, Kopieren und Löschen von Rollen verwenden Sie das Dialogfeld **Rollen-Manager** .</span><span class="sxs-lookup"><span data-stu-id="cf8c5-109">To create, edit, copy, and delete roles, you will use the **Role Manager** dialog box.</span></span> <span data-ttu-id="cf8c5-110">Klicken Sie zum Anzeigen des Dialogfelds **Rollen-Manager** in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]auf das Menü **Modell** und anschließend auf **Rollen-Manager**.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-110">To view the **Role Manager** dialog box, in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, and then click **Role Manager**.</span></span>  
  
###  <a name="to-create-a-new-role"></a><a name="bkmk_new_role"></a><span data-ttu-id="cf8c5-111">So erstellen Sie eine neue Rolle</span><span class="sxs-lookup"><span data-stu-id="cf8c5-111">To create a new role</span></span>  
  
1.  <span data-ttu-id="cf8c5-112">Klicken Sie in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]auf das Menü **Modell** und dann auf **Rollen-Manager**.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-112">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, and then click **Role Manager**.</span></span>  
  
2.  <span data-ttu-id="cf8c5-113">Klicken Sie im Dialogfeld **Rollen-Manager** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-113">In the **Role Manager** dialog box, click **New**.</span></span>  
  
     <span data-ttu-id="cf8c5-114">Der Liste Rollen wird eine neue hervorgehobene Rolle hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-114">A new highlighted role is added to the Roles list.</span></span>  
  
3.  <span data-ttu-id="cf8c5-115">Geben Sie in der Liste **Rollen** im Feld **Name** einen Namen für die Rolle ein.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-115">In the **Roles** list, in the **Name** field, type a name for the role.</span></span>  
  
     <span data-ttu-id="cf8c5-116">Der Name der Standardrolle wird für jede neue Rolle automatisch inkrementell erhöht.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-116">By default, the name of the default role will be incrementally numbered for each new role.</span></span> <span data-ttu-id="cf8c5-117">Es wird empfohlen, einen Namen einzugeben, durch den der Elementtyp eindeutig identifiziert wird, beispielsweise "Finance Managers" oder "Human Resources Specialists".</span><span class="sxs-lookup"><span data-stu-id="cf8c5-117">It is recommended you type a name that clearly identifies the member type, for example, Finance Managers or Human Resources Specialists.</span></span>  
  
4.  <span data-ttu-id="cf8c5-118">Klicken Sie im Feld **Berechtigungen** auf den Pfeil nach unten, und wählen Sie einen der folgenden Berechtigungstypen aus:</span><span class="sxs-lookup"><span data-stu-id="cf8c5-118">In the **Permissions** field, click the down arrow and then select one of the following permission types:</span></span>  
  
    |<span data-ttu-id="cf8c5-119">Berechtigung</span><span class="sxs-lookup"><span data-stu-id="cf8c5-119">Permission</span></span>|<span data-ttu-id="cf8c5-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cf8c5-120">Description</span></span>|  
    |----------------|-----------------|  
    |<span data-ttu-id="cf8c5-121">**None**</span><span class="sxs-lookup"><span data-stu-id="cf8c5-121">**None**</span></span>|<span data-ttu-id="cf8c5-122">Mitglieder können keine Änderungen am Modellschema vornehmen und keine Daten abfragen.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-122">Members cannot make any modifications to the model schema and cannot query data.</span></span>|  
    |<span data-ttu-id="cf8c5-123">**Lesen**</span><span class="sxs-lookup"><span data-stu-id="cf8c5-123">**Read**</span></span>|<span data-ttu-id="cf8c5-124">Mitglieder dürfen Daten (basierend auf Zeilenfiltern) abfragen, doch sie können keine Änderungen am Modellschema vornehmen.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-124">Members are allowed to query data (based on row filters) but cannot make any changes to the model schema.</span></span>|  
    |<span data-ttu-id="cf8c5-125">**Lesen und Verarbeiten**</span><span class="sxs-lookup"><span data-stu-id="cf8c5-125">**Read and Process**</span></span>|<span data-ttu-id="cf8c5-126">Mitglieder können Daten (basierend auf Filtern auf Zeilenebene) abfragen und die Vorgänge Verarbeiten und Alles verarbeiten ausführen, jedoch keine Änderungen am Modellschema vornehmen.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-126">Members are allowed to query data (based on row-level filters) and run Process and Process All operations, but cannot make any changes to the model schema.</span></span>|  
    |<span data-ttu-id="cf8c5-127">**Prozess**</span><span class="sxs-lookup"><span data-stu-id="cf8c5-127">**Process**</span></span>|<span data-ttu-id="cf8c5-128">Mitglieder können die Vorgänge Verarbeiten und Alles verarbeiten ausführen.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-128">Members can run Process and Process All operations.</span></span> <span data-ttu-id="cf8c5-129">Sie können weder das Modellschema ändern noch Daten abfragen.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-129">Cannot modify the model schema and cannot query data.</span></span>|  
    |<span data-ttu-id="cf8c5-130">**Administrator**</span><span class="sxs-lookup"><span data-stu-id="cf8c5-130">**Administrator**</span></span>|<span data-ttu-id="cf8c5-131">Mitglieder können Änderungen am Modellschema vornehmen und alle Daten abfragen.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-131">Members can make modifications to the model schema and can query all data.</span></span>|  
  
5.  <span data-ttu-id="cf8c5-132">Um eine Beschreibung für die Rolle einzugeben, klicken Sie auf das Feld **Beschreibung** und geben dann eine Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-132">To enter a description for the role, click the **Description** field, and then type a description.</span></span>  
  
6.  <span data-ttu-id="cf8c5-133">Wenn die erstellte Rolle über Lese- bzw. Lese- und Verarbeitungsberechtigungen verfügt, können Sie Zeilenfilter mithilfe einer DAX-Formel hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-133">If the role you are creating has Read or Read and Process permission, you can add row filters using a DAX formula.</span></span> <span data-ttu-id="cf8c5-134">Um Zeilenfilter hinzuzufügen, klicken Sie auf die Registerkarte **Zeilenfilter** , wählen eine Tabelle aus, klicken auf das Feld **DAX-Filter** und geben eine DAX-Formel ein.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-134">To add row filters, click the **Row Filters** tab, then select a table, then click the **DAX Filter** field, and then type a DAX formula.</span></span>  
  
7.  <span data-ttu-id="cf8c5-135">Um der Rolle Mitglieder hinzuzufügen, klicken Sie auf die Registerkarte **Mitglieder** und dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-135">To add members to the role, click the **Members** tab, and then click **Add**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cf8c5-136">Rollenmitglieder können einem bereitgestellten Modell auch mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-136">Role members can also be added to a deployed model by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="cf8c5-137">Weitere Informationen finden Sie unter [Verwalten von Rollen mit SSMS &#40;SSAS – tabellarisch&#41;](manage-roles-by-using-ssms-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="cf8c5-137">For more information, see [Manage Roles by using SSMS &#40;SSAS Tabular&#41;](manage-roles-by-using-ssms-ssas-tabular.md).</span></span>  
  
8.  <span data-ttu-id="cf8c5-138">Geben Sie im Dialogfeld **Benutzer oder Gruppen auswählen** Windows-Benutzer- oder Windows-Gruppenobjekte als Mitglieder ein.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-138">In the **Select Users or Groups** dialog box, enter Windows user or Windows group objects as members.</span></span>  
  
9. <span data-ttu-id="cf8c5-139">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="cf8c5-139">Click **Ok**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf8c5-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cf8c5-140">See Also</span></span>  
 <span data-ttu-id="cf8c5-141">[Rollen &#40;tabellarischen SSAS-&#41;](roles-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="cf8c5-141">[Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md) </span></span>  
 <span data-ttu-id="cf8c5-142">[Perspektiven &#40;tabellarischen SSAS-&#41;](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="cf8c5-142">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 <span data-ttu-id="cf8c5-143">[In Excel analysieren &#40;tabellarischen SSAS-&#41;](analyze-in-excel-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="cf8c5-143">[Analyze in Excel &#40;SSAS Tabular&#41;](analyze-in-excel-ssas-tabular.md) </span></span>  
 <span data-ttu-id="cf8c5-144">[USERNAME-Funktion &#40;DAX-&#41;](/dax/username-function-dax) </span><span class="sxs-lookup"><span data-stu-id="cf8c5-144">[USERNAME Function &#40;DAX&#41;](/dax/username-function-dax) </span></span>  
 [<span data-ttu-id="cf8c5-145">CustomData-Funktion &#40;DAX-&#41;</span><span class="sxs-lookup"><span data-stu-id="cf8c5-145">CUSTOMDATA Function &#40;DAX&#41;</span></span>](/dax/customdata-function-dax)  
  
  
