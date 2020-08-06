---
title: Modellelement Sicherheit (Seite) (Berichts-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.modelproperties.modelitemsecurity.f1
ms.assetid: 8c5b29ae-1f17-41f2-ab59-97899b8fb4fc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 928572437990c7f7fe1117c086c65c939aa9c999
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608383"
---
# <a name="model-item-security-page-report-manager"></a><span data-ttu-id="7baef-102">Modellelementsicherheit (Seite) (Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="7baef-102">Model Item Security Page (Report Manager)</span></span>
  <span data-ttu-id="7baef-103">Verwenden Sie diese Seite, um Teile eines Modells zu sichern, indem Sie schreibgeschützte Berechtigungen für bestimmte Elemente erteilen oder aufheben.</span><span class="sxs-lookup"><span data-stu-id="7baef-103">Use this page to secure parts of a model by granting or revoking read-only permissions on particular items.</span></span> <span data-ttu-id="7baef-104">Die Modellelementsicherheit hat Auswirkungen auf die Ad-hoc-Durchsuchung von Daten zur Laufzeit und die Möglichkeit, Teile eines veröffentlichten Modells bei der Erstellung von Berichten im Berichts-Generator zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7baef-104">Model item security affects ad hoc data exploration at run time and the ability to use parts of a published model when creating reports in Report Builder.</span></span> <span data-ttu-id="7baef-105">Sie müssen über Inhalts-Manager-Berechtigungen verfügen, um diese Funktion zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7baef-105">To use this feature, you must have Content Manager permissions.</span></span>  
  
 <span data-ttu-id="7baef-106">Die Modellelementsicherheit wird auf ein auf dem Berichtsserver verarbeitetes Modell angewendet und wirkt sich nicht auf SMDL-Dateien aus, die Sie im Modell-Designer bearbeiten oder im Berichts-Designer verwenden.</span><span class="sxs-lookup"><span data-stu-id="7baef-106">Model item security is applied to a model that is processed on the report server and does not affect .smdl files that you edit in Model Designer or use in Report Designer.</span></span> <span data-ttu-id="7baef-107">Darüber hinaus hat sie keine Auswirkungen auf Benutzer, die über die Berechtigung zum Ändern einer Modelldefinition verfügen.</span><span class="sxs-lookup"><span data-stu-id="7baef-107">Furthermore, it has no effect on users who have permission to modify a model definition.</span></span> <span data-ttu-id="7baef-108">Benutzer mit Inhalts-Manager- oder Verlegerberechtigungen für ein Modell können sämtliche Teile dieses Modells anzeigen, unabhängig davon, ob Sie Modellelementsicherheit anwenden.</span><span class="sxs-lookup"><span data-stu-id="7baef-108">Any user who has Content Manager or Publisher permissions on a model can see all parts of it, regardless of whether you apply model item security.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7baef-109">Modellelemente können mithilfe von Sicherheitsfiltern zusätzlich gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="7baef-109">Model items can be further secured through the use of security filters.</span></span>  
  
 <span data-ttu-id="7baef-110">Sie können Modellelementsicherheit für Entitäten, Ordner und einzelne Feldern innerhalb eines Modells definieren.</span><span class="sxs-lookup"><span data-stu-id="7baef-110">You can define model item security on entities, folders, and individual fields within a model.</span></span> <span data-ttu-id="7baef-111">Da ein Modell eine breite Vielfalt sicherungsfähiger Elemente umfasst, wurde Berechtigungsvererbung in das Modell integriert, wodurch Sie eine große Zahl von Elementen mittels einer kleinen Anzahl von Rollenzuweisungen sichern können.</span><span class="sxs-lookup"><span data-stu-id="7baef-111">Because a model presents such a large surface of securable items, permission inheritance is built into the model so that you can secure a large number of items through a relatively small number of role assignments.</span></span> <span data-ttu-id="7baef-112">Die Berechtigungsvererbung basiert auf folgenden Elementen:</span><span class="sxs-lookup"><span data-stu-id="7baef-112">Permission inheritance is based on the following:</span></span>  
  
-   <span data-ttu-id="7baef-113">Modell</span><span class="sxs-lookup"><span data-stu-id="7baef-113">Model</span></span>  
  
-   <span data-ttu-id="7baef-114">Stammknoten</span><span class="sxs-lookup"><span data-stu-id="7baef-114">Root node</span></span>  
  
-   <span data-ttu-id="7baef-115">Ordner oder Entitäten</span><span class="sxs-lookup"><span data-stu-id="7baef-115">Folders or entities</span></span>  
  
-   <span data-ttu-id="7baef-116">Felder</span><span class="sxs-lookup"><span data-stu-id="7baef-116">Fields</span></span>  
  
 <span data-ttu-id="7baef-117">Anfangs wird die Zugriffsberechtigung für Elemente des Modells durch die Rollenzuweisungen vererbt, die für das Modell selbst festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="7baef-117">Initially, permission to access to model items is inherited through role assignments that are set on the model itself.</span></span> <span data-ttu-id="7baef-118">Ein Benutzer mit der Berechtigung, ein Modell in einem Ordner im Berichts-Manager anzuzeigen, kann alle Elemente im Modell anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7baef-118">A user who has permission to view a model in a folder in Report Manager can view all of the items in the model.</span></span>  
  
 <span data-ttu-id="7baef-119">Wenn Sie Modellelementsicherheit anwenden, müssen Sie zumindest eine Rollenzuweisung für den Stammknoten erstellen.</span><span class="sxs-lookup"><span data-stu-id="7baef-119">If you apply model item security, you must create at least one role assignment on the root node.</span></span> <span data-ttu-id="7baef-120">Diese erste Rollenzuweisung für den Stammknoten wird zur Quelle vererbter Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="7baef-120">This initial role assignment on the root node becomes the new source of inherited permissions.</span></span> <span data-ttu-id="7baef-121">Die Rollenzuweisung für den Stammknoten wird automatisch allen Elementen in der Modellhierarchie vererbt.</span><span class="sxs-lookup"><span data-stu-id="7baef-121">The role assignment on the root node is automatically inherited by all items in the model hierarchy.</span></span>  
  
 <span data-ttu-id="7baef-122">Um die Berechtigungen für das Durchsuchen von Daten noch weiter anzupassen, können Sie Berechtigungen für Ordner und Entitäten ändern.</span><span class="sxs-lookup"><span data-stu-id="7baef-122">To further customize permissions on data exploration, you can vary permissions on folders and entities.</span></span> <span data-ttu-id="7baef-123">Abschließend können Sie Berechtigungen für einzelne Felder festlegen.</span><span class="sxs-lookup"><span data-stu-id="7baef-123">Finally, you can set permissions on individual fields.</span></span>  
  
 <span data-ttu-id="7baef-124">Damit Rollenzuweisungen einfacher zu verwalten sind, sollten Sie Berechtigungen nur für Ordner oder Entitäten festlegen und nicht für einzelne Felder.</span><span class="sxs-lookup"><span data-stu-id="7baef-124">To make role assignments easier to maintain, set permissions only on folders or entities rather than individual fields.</span></span> <span data-ttu-id="7baef-125">Sie können nicht nach den Rollenzuweisungen suchen, die Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="7baef-125">You cannot search for role assignments that you create.</span></span> <span data-ttu-id="7baef-126">Wenn Sie also Sicherheitseinstellungen für bestimmte Felder festlegen und diese Einstellungen zu einem späteren Zeitpunkt aktualisieren möchten, müssen Sie durch das gesamte Modellnamespace klicken, um diese Felder wiederzufinden.</span><span class="sxs-lookup"><span data-stu-id="7baef-126">If you set security on specific fields and you want to update the security settings later, you must click through the model namespace to find the fields you secured.</span></span>  
  
 <span data-ttu-id="7baef-127">Erstellen Sie anfangs eine Rollenzuweisung für den Stammknoten und dann zusätzliche Rollenzuweisungen für Ordner und Entitäten.</span><span class="sxs-lookup"><span data-stu-id="7baef-127">To get started, create a role assignment on the root node and then create additional role assignments on entities and folders.</span></span> <span data-ttu-id="7baef-128">Deaktivieren Sie das Kontrollkästchen **Einzelne Modellelemente für dieses Modell unabhängig voneinander sichern**, um die Modellelementsicherheit zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7baef-128">To clear model item security, clear the check box for **Secure individual model items independently for this model**.</span></span> <span data-ttu-id="7baef-129">Wenn Sie das Kontrollkästchen deaktivieren, werden die ursprünglichen Berechtigungen wiederhergestellt, die vom Modell geerbt wurden.</span><span class="sxs-lookup"><span data-stu-id="7baef-129">Clearing the check box reverts back to the initial permissions that are inherited from the model.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="7baef-130">Navigation</span><span class="sxs-lookup"><span data-stu-id="7baef-130">Navigation</span></span>  
 <span data-ttu-id="7baef-131">Verwenden Sie folgendes Verfahren, um zu dieser Position in der Benutzeroberfläche zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="7baef-131">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-general-properties-page-for-a-report"></a><span data-ttu-id="7baef-132">So öffnen Sie die Seite Allgemeine Eigenschaften für einen Bericht</span><span class="sxs-lookup"><span data-stu-id="7baef-132">To open the General properties page for a report</span></span>  
  
1.  <span data-ttu-id="7baef-133">Öffnen Sie den Berichts-Manager, und suchen Sie das Modell, für das Sie Modellelementsicherheit konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="7baef-133">Open Report Manager, and locate the model for which you want to configure security for model items.</span></span>  
  
2.  <span data-ttu-id="7baef-134">Zeigen Sie auf das Modell, und klicken Sie auf den Dropdownpfeil.</span><span class="sxs-lookup"><span data-stu-id="7baef-134">Hover over the model, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="7baef-135">Klicken Sie im Dropdownmenü auf **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="7baef-135">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="7baef-136">Dadurch wird die Seite Allgemeine Eigenschaften für das Modell geöffnet.</span><span class="sxs-lookup"><span data-stu-id="7baef-136">This opens the General properties page for the model.</span></span>  
  
4.  <span data-ttu-id="7baef-137">Wählen Sie die Registerkarte **Modellelementsicherheit** aus.</span><span class="sxs-lookup"><span data-stu-id="7baef-137">Select the **Model Item Security** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7baef-138">Tastatur</span><span class="sxs-lookup"><span data-stu-id="7baef-138">Options</span></span>  
 <span data-ttu-id="7baef-139">**Einzelne Modellelemente für dieses Modell unabhängig voneinander sichern**</span><span class="sxs-lookup"><span data-stu-id="7baef-139">**Secure individual model items independently for this model**</span></span>  
 <span data-ttu-id="7baef-140">Aktivieren Sie dieses Kontrollkästchen, um die Modellelementsicherheit zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7baef-140">Click this check box to enable model item security.</span></span>  
  
 <span data-ttu-id="7baef-141">**Geben Sie die Sicherheit für einzelne Modellelemente im Modell an**</span><span class="sxs-lookup"><span data-stu-id="7baef-141">**Specify security for individual model items in the mode**</span></span>  
 <span data-ttu-id="7baef-142">Zeigt alle Elemente eines Modells.</span><span class="sxs-lookup"><span data-stu-id="7baef-142">Shows all of the items in a model.</span></span> <span data-ttu-id="7baef-143">Sie können im Modellnamespace navigieren, um das mit Sicherheitseinstellungen zu versehende Element auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="7baef-143">You can navigate the model namespace to select the item you want to secure.</span></span> <span data-ttu-id="7baef-144">Sie können jeweils nur ein Element auswählen.</span><span class="sxs-lookup"><span data-stu-id="7baef-144">You can only select one item at a time.</span></span> <span data-ttu-id="7baef-145">Stellen Sie sicher, dass Sie die erste Rollenzuweisung für den Stammknoten erstellt haben, bevor Sie mit anderen Ordnern und Entitäten fortfahren.</span><span class="sxs-lookup"><span data-stu-id="7baef-145">Be sure to create the first role assignment on the root node before proceeding to other entities and folders.</span></span>  
  
 <span data-ttu-id="7baef-146">**Berechtigungen vom übergeordneten Element erben**</span><span class="sxs-lookup"><span data-stu-id="7baef-146">**Inherit permissions from the parent item**</span></span>  
 <span data-ttu-id="7baef-147">Aktivieren Sie diese Option, wenn das Element die Sicherheitseinstellungen des übergeordneten Elements erben soll.</span><span class="sxs-lookup"><span data-stu-id="7baef-147">Click this option to inherit the security settings of the parent item.</span></span>  
  
 <span data-ttu-id="7baef-148">**Weisen Sie den folgenden Benutzern und Gruppen Leseberechtigungen zu (durch Semikolons getrennt)**</span><span class="sxs-lookup"><span data-stu-id="7baef-148">**Assign read permission to the following users and groups (semi-colon separated)**</span></span>  
 <span data-ttu-id="7baef-149">Aktivieren Sie diese Option, um das Benutzer- bzw. Gruppenkonto anzugeben, für das Sie den Zugriff definieren.</span><span class="sxs-lookup"><span data-stu-id="7baef-149">Click this option to specify the user or group account for which you are defining access.</span></span> <span data-ttu-id="7baef-150">Wenn Sie die Standardsicherheitseinstellungen verwenden, handelt es sich bei den Benutzer- bzw. Gruppenkonten um Windows-Domänenkonten.</span><span class="sxs-lookup"><span data-stu-id="7baef-150">If you are using default security, the user and group accounts are Windows domain accounts.</span></span> <span data-ttu-id="7baef-151">Geben Sie die Konten im folgenden Format an: \* \<domain> \\<Konto \> \*.</span><span class="sxs-lookup"><span data-stu-id="7baef-151">Specify the accounts in this format: *\<domain>\\<account\>*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7baef-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7baef-152">See Also</span></span>  
 [<span data-ttu-id="7baef-153">Berichtsserver im Management Studio (F1-Hilfe)</span><span class="sxs-lookup"><span data-stu-id="7baef-153">Report Server in Management Studio F1 Help</span></span>](tools/report-server-in-management-studio-f1-help.md)  
  
  
