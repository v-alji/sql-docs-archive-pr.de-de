---
title: 'Lektion 12: Erstellen von Rollen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 984face4-00fc-46d3-8ae1-9755bf737bdf
author: minewiskan
ms.author: owend
ms.openlocfilehash: 962cd19726a5404de81e20a2209b25b9cc277e21
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608039"
---
# <a name="lesson-12-create-roles"></a><span data-ttu-id="75659-102">Lektion 12: Erstellen von Rollen</span><span class="sxs-lookup"><span data-stu-id="75659-102">Lesson 12: Create Roles</span></span>
  <span data-ttu-id="75659-103">In dieser Lektion erstellen Sie Rollen.</span><span class="sxs-lookup"><span data-stu-id="75659-103">In this lesson, you will create roles.</span></span> <span data-ttu-id="75659-104">Rollen stellen Modelldatenbankobjekt- und Datensicherheit bereit, indem sie den Zugriff auf die Windows-Benutzer einschränken, die Rollenmitglieder sind.</span><span class="sxs-lookup"><span data-stu-id="75659-104">Roles provide model database object and data security by limiting access to only those Windows users which are role members.</span></span> <span data-ttu-id="75659-105">Jede Rolle ist mit einer einzigen Berechtigung definiert: Keine, Lesen, Lesen und Verarbeiten, Verarbeiten und Administrator.</span><span class="sxs-lookup"><span data-stu-id="75659-105">Each role is defined with a single permission: None, Read, Read and Process, Process, or Administrator.</span></span> <span data-ttu-id="75659-106">Rollen können in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]während der Modellerstellung im Dialogfeld Rollen-Manager definiert werden.</span><span class="sxs-lookup"><span data-stu-id="75659-106">Roles can be defined during model authoring by using the Role Manager dialog box in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="75659-107">Nachdem ein Modell bereitgestellt wurde, können Sie mit [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]Rollen verwalten.</span><span class="sxs-lookup"><span data-stu-id="75659-107">After a model has been deployed, you can manage roles by using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="75659-108">Weitere Informationen finden Sie unter [Rollen &#40;SSAS – tabellarisch&#41;](tabular-models/roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="75659-108">To learn more, see [Roles &#40;SSAS Tabular&#41;](tabular-models/roles-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="75659-109">Das Erstellen von Rollen ist zum Abschließen dieses Lernprogramms nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="75659-109">Creating roles is not necessary to complete this tutorial.</span></span> <span data-ttu-id="75659-110">Standardmäßig erhält das Konto, mit dem Sie eingeloggt sind, Administratorberechtigungen für das Modell.</span><span class="sxs-lookup"><span data-stu-id="75659-110">By default, the account you are currently logged in with will have Administrator privileges on the model.</span></span> <span data-ttu-id="75659-111">Um Benutzern in Ihrer Organisation jedoch das Durchsuchen des Modells mithilfe einer Berichterstellungsclientanwendung zu ermöglichen, müssen Sie mindestens eine Rolle mit Leseberechtigung erstellen und diese Benutzer als Mitglieder hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="75659-111">However, to allow other users in your organization to browse the model by using a reporting client application, you must create at least one role with Read permissions and add those users as members.</span></span>  
  
 <span data-ttu-id="75659-112">Erstellen Sie drei Rollen:</span><span class="sxs-lookup"><span data-stu-id="75659-112">You will create three roles:</span></span>  
  
-   <span data-ttu-id="75659-113">Sales Manager: diese Rolle kann Benutzer in Ihrer Organisation umfassen, für die Sie über die Berechtigung Lesen für alle Modell Objekte und-Daten verfügen möchten.</span><span class="sxs-lookup"><span data-stu-id="75659-113">Sales Manager - This role can include users in your organization for which you want to have Read permission to all model objects and data.</span></span>  
  
-   <span data-ttu-id="75659-114">Sales Analyst US: diese Rolle kann Benutzer in Ihrer Organisation umfassen, für die Sie nur Daten im Zusammenhang mit den Verkäufen in den USA (USA) durchsuchen möchten.</span><span class="sxs-lookup"><span data-stu-id="75659-114">Sales Analyst US - This role can include users in your organization for which you want only to be able to browse data related to sales in the US (United States).</span></span> <span data-ttu-id="75659-115">Für diese Rolle definieren Sie mit einer DAX-Formel einen *Zeilenfilter*, der Mitgliedern der Rolle lediglich das Durchsuchen von Daten in den USA ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="75659-115">For this role, you will use a DAX formula to define a *Row Filter*, which restricts members to browse data only for the United States.</span></span>  
  
-   <span data-ttu-id="75659-116">Administrator: diese Rolle kann Benutzer umfassen, für die Sie über die Administrator Berechtigung verfügen möchten, die uneingeschränkten Zugriff und Berechtigungen zum Ausführen administrativer Aufgaben für die Modelldatenbank ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="75659-116">Administrator - This role can include users for which you want to have Administrator permission, which allows unlimited access and permissions to perform administrative tasks on the model database.</span></span>  
  
 <span data-ttu-id="75659-117">Da Windows-Benutzer- und -Gruppenkonten in der Organisation eindeutig sind, können Sie Mitgliedern Konten aus Ihrer Organisation hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="75659-117">Because Windows user and group accounts in your organization are unique, you can add accounts from your particular organization to members.</span></span> <span data-ttu-id="75659-118">In diesem Lernprogramm können Sie die Angaben zu den Mitgliedern auch weglassen.</span><span class="sxs-lookup"><span data-stu-id="75659-118">However, for this tutorial, you can also leave the members blank.</span></span> <span data-ttu-id="75659-119">Sie können die Auswirkungen der einzelnen Rollen immer noch in "Lektion 12: Analysieren in Excel" testen.</span><span class="sxs-lookup"><span data-stu-id="75659-119">You will still be able to test the effect of each role later in Lesson 12: Analyze in Excel.</span></span>  
  
 <span data-ttu-id="75659-120">Geschätzte Zeit zum Bearbeiten dieser Lektion: **15 Minuten**</span><span class="sxs-lookup"><span data-stu-id="75659-120">Estimated time to complete this lesson: **15 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="75659-121">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="75659-121">Prerequisites</span></span>  
 <span data-ttu-id="75659-122">Dieses Thema ist Teil eines Tutorials zur Tabellenmodellierung, das in der richtigen Reihenfolge absolviert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="75659-122">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="75659-123">Sie sollten vor dem Ausführen der Aufgaben in dieser Lektion die vorherige Lektion abgeschlossen haben: [Lektion 11: Erstellen von Partitionen](lesson-10-create-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="75659-123">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 11: Create Partitions](lesson-10-create-partitions.md).</span></span>  
  
## <a name="create-roles"></a><span data-ttu-id="75659-124">Erstellen von Rollen</span><span class="sxs-lookup"><span data-stu-id="75659-124">Create Roles</span></span>  
  
#### <a name="to-create-a-sales-manager-user-role"></a><span data-ttu-id="75659-125">So erstellen Sie die Benutzerrolle „Verkaufs-Manager“</span><span class="sxs-lookup"><span data-stu-id="75659-125">To create a Sales Manager user role</span></span>  
  
1.  <span data-ttu-id="75659-126">Klicken Sie in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf das Menü **Modell** und anschließend auf **Rollen**.</span><span class="sxs-lookup"><span data-stu-id="75659-126">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **Model** menu, and then click **Roles**.</span></span>  
  
2.  <span data-ttu-id="75659-127">Klicken Sie im Dialogfeld **Rollen-Manager** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="75659-127">In the **Role Manager** dialog box, click **New**.</span></span>  
  
     <span data-ttu-id="75659-128">Der Liste wird eine neue Rolle mit der Berechtigung „None“ hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="75659-128">A new role with the None permission is added to the list.</span></span>  
  
3.  <span data-ttu-id="75659-129">Klicken Sie auf die neue Rolle, und benennen Sie in der Spalte **Name** die Rolle in um `Internet Sales Manager` .</span><span class="sxs-lookup"><span data-stu-id="75659-129">Click on the new role, and then in the **Name** column, rename the role to `Internet Sales Manager`.</span></span>  
  
4.  <span data-ttu-id="75659-130">Klicken sie in der Spalte **Berechtigungen** auf die Dropdownliste, und wählen Sie anschließend die Berechtigung **Lesen** aus.</span><span class="sxs-lookup"><span data-stu-id="75659-130">In the **Permissions** column, click the dropdown list, and then select the **Read** permission.</span></span>  
  
5.  <span data-ttu-id="75659-131">Optional: Klicken Sie auf die Registerkarte **Member** und anschließend auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="75659-131">Optional: Click on the **Members** tab, and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="75659-132">Geben Sie im Dialogfeld **Select Users or Groups** (Benutzer oder Gruppen auswählen) die Windows-Benutzer oder -Gruppen Ihrer Organisation ein, denen Sie die Rolle erteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="75659-132">In the **Select Users or Groups** dialog box, enter the Windows users or groups from your organization you want to include in the role.</span></span>  
  
7.  <span data-ttu-id="75659-133">Überprüfen Sie Ihre Auswahl, und klicken Sie auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="75659-133">Verify your selections, and then click **OK**</span></span>  
  
#### <a name="to-create-a-sales-analyst-us-user-role"></a><span data-ttu-id="75659-134">So erstellen Sie die Benutzerrolle "Sales Analyst US"</span><span class="sxs-lookup"><span data-stu-id="75659-134">To create a Sales Analyst US user role</span></span>  
  
1.  <span data-ttu-id="75659-135">Klicken Sie in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf das Menü **Modell** und anschließend auf **Rollen**.</span><span class="sxs-lookup"><span data-stu-id="75659-135">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **Model** menu, and then click **Roles**.</span></span>  
  
2.  <span data-ttu-id="75659-136">Klicken Sie im Dialogfeld **Rollen-Manager** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="75659-136">In the **Role Manager** dialog box, click **New**.</span></span>  
  
     <span data-ttu-id="75659-137">Der Liste wird eine neue Rolle mit der Berechtigung „None“ hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="75659-137">A new role with the None permission is added to the list.</span></span>  
  
3.  <span data-ttu-id="75659-138">Klicken Sie auf die neue Rolle, und benennen Sie in der Spalte **Name** die Rolle in um `Internet Sales US` .</span><span class="sxs-lookup"><span data-stu-id="75659-138">Click on the new role, and then in the **Name** column, rename the role to `Internet Sales US`.</span></span>  
  
4.  <span data-ttu-id="75659-139">Klicken sie in der Spalte **Berechtigungen** auf die Dropdownliste, und wählen Sie anschließend die Berechtigung **Lesen** aus.</span><span class="sxs-lookup"><span data-stu-id="75659-139">In the **Permissions** column, click the dropdown list, and then select the **Read** permission.</span></span>  
  
5.  <span data-ttu-id="75659-140">Klicken Sie auf die Registerkarte Zeilenfilter, und geben Sie anschließend nur für die Tabelle **Geography** in der Spalte DAX Filter die folgende Formel ein:</span><span class="sxs-lookup"><span data-stu-id="75659-140">Click on the Row Filters tab, and then for the **Geography** table only, in the DAX Filter column, type the following formula:</span></span>  
  
     `=Geography[Country Region Code] = "US"`  
  
     <span data-ttu-id="75659-141">Eine Zeilenfilterformel muss einen Booleschen Wert ergeben (TRUE/FALSE).</span><span class="sxs-lookup"><span data-stu-id="75659-141">A Row Filter formula must resolve to a Boolean (TRUE/FALSE) value.</span></span> <span data-ttu-id="75659-142">Mit dieser Formel geben Sie an, dass nur Zeilen mit dem Länder-/regionscodewert "US" für den Benutzer sichtbar sein sollen.</span><span class="sxs-lookup"><span data-stu-id="75659-142">With this formula, you are specifying that only rows with the Country Region Code value of "US" be visible to the user.</span></span>  
  
     <span data-ttu-id="75659-143">Drücken Sie nach dem Erstellen der Formel die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="75659-143">When you have finished building the formula, press ENTER.</span></span>  
  
6.  <span data-ttu-id="75659-144">Optional: Klicken Sie auf die Registerkarte **Member** und anschließend auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="75659-144">Optional: Click on the **Members** tab, and then click **Add**.</span></span>  
  
7.  <span data-ttu-id="75659-145">Geben Sie im Dialogfeld **Select Users or Groups** (Benutzer oder Gruppen auswählen) die Windows-Benutzer oder -Gruppen Ihrer Organisation ein, denen Sie die Rolle erteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="75659-145">In the **Select Users or Groups** dialog box, enter the Windows users or groups from your organization you want to include in the role.</span></span>  
  
8.  <span data-ttu-id="75659-146">Überprüfen Sie Ihre Auswahl, und klicken Sie auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="75659-146">Verify your selections, and then click **OK**</span></span>  
  
#### <a name="to-create-an-administrator-role"></a><span data-ttu-id="75659-147">So erstellen Sie die Rolle "Administrator"</span><span class="sxs-lookup"><span data-stu-id="75659-147">To create an Administrator role</span></span>  
  
1.  <span data-ttu-id="75659-148">Klicken Sie im Dialogfeld **Rollen-Manager** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="75659-148">In the **Role Manager** dialog box, click **New**.</span></span>  
  
2.  <span data-ttu-id="75659-149">Klicken Sie auf die neue Rolle, und benennen Sie in der Spalte **Name** die Rolle in um `Internet Sales Administrator` .</span><span class="sxs-lookup"><span data-stu-id="75659-149">Click on the new role, and then in the **Name** column, rename the role to `Internet Sales Administrator`.</span></span>  
  
3.  <span data-ttu-id="75659-150">Klicken Sie in der Spalte **Berechtigungen** auf die Dropdownliste und wählen Sie anschließend die Berechtigung **Administrator** aus.</span><span class="sxs-lookup"><span data-stu-id="75659-150">In the **Permissions** column, click the dropdown list, and then select the **Administrator** permission.</span></span>  
  
4.  <span data-ttu-id="75659-151">Klicken Sie auf die Registerkarte **Mitglieder** und anschließend auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="75659-151">Click on the **Members** tab, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="75659-152">Optional: Geben Sie im Dialogfeld **Benutzer oder Gruppen auswählen** die Windows-Benutzer oder -Gruppen in Ihrer Organisation ein, die Sie der Rolle hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="75659-152">Optional: In the **Select Users or Groups** dialog box, enter the Windows users or groups from your organization you want to include in the role.</span></span>  
  
6.  <span data-ttu-id="75659-153">Überprüfen Sie Ihre Auswahl, und klicken Sie auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="75659-153">Verify your selections, and then click **OK**</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="75659-154">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="75659-154">Next Steps</span></span>  
 <span data-ttu-id="75659-155">Wenn Sie mit diesem Tutorial fortfahren möchten, wechseln Sie zur nächsten Lektion: [Lektion 13: Analysieren in Excel](lesson-12-analyze-in-excel.md).</span><span class="sxs-lookup"><span data-stu-id="75659-155">To continue this tutorial, go to the next lesson: Lesson: [Lesson 13: Analyze in Excel](lesson-12-analyze-in-excel.md).</span></span>  
  
  
