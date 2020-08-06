---
title: Hinzufügen, löschen, Ändern des Bereichs von benutzerdefinierten Variablen in einem Paket | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- variables [Integration Services], adding
ms.assetid: cbf40c7f-3c8a-48cd-aefa-8b37faf8b40e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1a7e5980fc7f730c69ef886e4e80760cfbdc9e4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617252"
---
# <a name="add-delete-change-scope-of-user-defined-variable-in-a-package"></a><span data-ttu-id="67519-102">Hinzufügen, Löschen, Ändern des Bereichs von benutzerdefinierten Variablen in einem Paket</span><span class="sxs-lookup"><span data-stu-id="67519-102">Add, Delete, Change Scope of User-Defined Variable in a Package</span></span>
  <span data-ttu-id="67519-103">In diesen Verfahren wird beschrieben, wie eine benutzerdefinierte Variable in einem Paket mithilfe des Fensters **Variablen** hinzugefügt oder gelöscht und ihr Bereich geändert wird.</span><span class="sxs-lookup"><span data-stu-id="67519-103">These procedures describe how to add, delete, and change the scope of a user-defined variable in a package by using the **Variables** window.</span></span>  
  
 <span data-ttu-id="67519-104">Weitere Informationen zu Variablenbereichen finden Sie unter [Integration Services-Variablen &#40;SSIS&#41;](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="67519-104">For more information about variable scope, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="67519-105">stellt außerdem Systemvariablen bereit, die zur Laufzeit Systeminformationen zur Verfügung stellen und die in Containern, z. B. Paketen und Ereignishandlern, verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="67519-105">also provides system variables that make system information available at run time and can be used in containers such as packages and event handlers.</span></span> <span data-ttu-id="67519-106">Systemvariablen können nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="67519-106">You cannot delete system variables.</span></span>  
  
### <a name="to-add-a-variable"></a><span data-ttu-id="67519-107">So fügen Sie eine Variable hinzu</span><span class="sxs-lookup"><span data-stu-id="67519-107">To add a variable</span></span>  
  
1.  <span data-ttu-id="67519-108">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]das gewünschte [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paket.</span><span class="sxs-lookup"><span data-stu-id="67519-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package you want to work with.</span></span>  
  
2.  <span data-ttu-id="67519-109">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="67519-109">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="67519-110">Gehen Sie im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer zum Definieren des Gültigkeitsbereichs der Variablen wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="67519-110">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, to define the scope of the variable, do one of the following:</span></span>  
  
    -   <span data-ttu-id="67519-111">Um den Gültigkeitsbereich des Pakets festzulegen, klicken Sie an eine beliebige Stelle auf der Entwurfsoberfläche der Registerkarte **Ablaufsteuerung** .</span><span class="sxs-lookup"><span data-stu-id="67519-111">To set the scope to the package, click anywhere on the design surface of the **Control Flow** tab.</span></span>  
  
    -   <span data-ttu-id="67519-112">Um den Gültigkeitsbereich auf einen Ereignishandler festzulegen, wählen Sie eine ausführbare Datei und einen Ereignishandler auf der Entwurfsoberfläche der Registerkarte **Ereignishandler** aus.</span><span class="sxs-lookup"><span data-stu-id="67519-112">To set the scope to an event handler, select an executable and an event handler on the design surface of the **Event Handler** tab.</span></span>  
  
    -   <span data-ttu-id="67519-113">Um den Gültigkeitsbereich auf einen Task oder Container festzulegen, klicken Sie auf der Entwurfsoberfläche der Registerkarte **Ablaufsteuerung** oder **Ereignishandler** auf einen Task oder Container.</span><span class="sxs-lookup"><span data-stu-id="67519-113">To set the scope to a task or container, on the design surface of the **Control Flow** tab or the **Event Handler** tab, click a task or container.</span></span>  
  
4.  <span data-ttu-id="67519-114">Klicken Sie im Menü **SSIS** auf **Variablen**.</span><span class="sxs-lookup"><span data-stu-id="67519-114">On the **SSIS** menu, click **Variables**.</span></span> <span data-ttu-id="67519-115">Sie können das Fenster **Variablen** auch anzeigen, indem Sie im Dialogfeld **Optionen** auf der Seite **Tastatur** den Befehl View.Variables einer beliebigen Tastenkombination zuordnen.</span><span class="sxs-lookup"><span data-stu-id="67519-115">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
5.  <span data-ttu-id="67519-116">Klicken Sie im Fenster **Variablen** auf das Symbol **Variable hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="67519-116">In the **Variables** window, click the **Add Variable** icon.</span></span> <span data-ttu-id="67519-117">Die neue Variable wird der Liste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="67519-117">The new variable is added to the list.</span></span>  
  
6.  <span data-ttu-id="67519-118">Klicken Sie wahlweise auf das Symbol **Rasteroptionen** , wählen Sie zusätzliche Spalten aus, die im Dialogfeld **Variable Rasteroptionen** angezeigt werden sollen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="67519-118">Optionally, click the **Grid Options** icon, select additional columns to show in the **Variables Grid Options** dialog box, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="67519-119">Legen Sie optional die Variableneigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="67519-119">Optionally, set the variable properties.</span></span> <span data-ttu-id="67519-120">Weitere Informationen finden Sie unter [Festlegen der Eigenschaften von benutzerdefinierten Variablen](../../2014/integration-services/set-the-properties-of-a-user-defined-variable.md)definiert.</span><span class="sxs-lookup"><span data-stu-id="67519-120">For more information, see [Set the Properties of a User-Defined Variable](../../2014/integration-services/set-the-properties-of-a-user-defined-variable.md).</span></span>  
  
8.  <span data-ttu-id="67519-121">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="67519-121">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-delete-a-variable"></a><span data-ttu-id="67519-122">So löschen Sie eine Variable</span><span class="sxs-lookup"><span data-stu-id="67519-122">To delete a variable</span></span>  
  
1.  <span data-ttu-id="67519-123">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="67519-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="67519-124">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="67519-124">In Solution Explorer, right-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="67519-125">Klicken Sie im Menü **SSIS** auf **Variablen**.</span><span class="sxs-lookup"><span data-stu-id="67519-125">On the **SSIS** menu, click **Variables**.</span></span> <span data-ttu-id="67519-126">Sie können das Fenster **Variablen** auch anzeigen, indem Sie im Dialogfeld **Optionen** auf der Seite **Tastatur** den Befehl View.Variables einer beliebigen Tastenkombination zuordnen.</span><span class="sxs-lookup"><span data-stu-id="67519-126">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
4.  <span data-ttu-id="67519-127">Wählen Sie die zu löschende Variable aus, und klicken Sie dann auf **Variable löschen**.</span><span class="sxs-lookup"><span data-stu-id="67519-127">Select the variable to delete, and then click **Delete Variable**.</span></span>  
  
     <span data-ttu-id="67519-128">Wenn die Variable nicht im Fenster Variablen angezeigt wird, klicken Sie auf **Raster Optionen** , und wählen Sie dann **Variablen aller Bereiche anzeigen aus**.</span><span class="sxs-lookup"><span data-stu-id="67519-128">If you don't see the variable in the Variables window, click **Grid Options** and then select **Show variables of all scopes**.</span></span>  
  
5.  <span data-ttu-id="67519-129">Wenn das Dialogfeld **Löschen der Variablen bestätigen** aufgerufen wird, klicken Sie zur Bestätigung auf **Ja** .</span><span class="sxs-lookup"><span data-stu-id="67519-129">If the **Confirm Deletion of Variables** dialog box opens, click **Yes** to confirm.</span></span>  
  
6.  <span data-ttu-id="67519-130">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="67519-130">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-change-the-scope-of-a-variable"></a><span data-ttu-id="67519-131">So ändern Sie den Bereich einer Variablen</span><span class="sxs-lookup"><span data-stu-id="67519-131">To change the scope of a variable</span></span>  
  
1.  <span data-ttu-id="67519-132">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="67519-132">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="67519-133">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="67519-133">In Solution Explorer, right-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="67519-134">Klicken Sie im Menü **SSIS** auf **Variablen**.</span><span class="sxs-lookup"><span data-stu-id="67519-134">On the **SSIS** menu, click **Variables**.</span></span> <span data-ttu-id="67519-135">Sie können das Fenster **Variablen** auch anzeigen, indem Sie im Dialogfeld **Optionen** auf der Seite **Tastatur** den Befehl View.Variables einer beliebigen Tastenkombination zuordnen.</span><span class="sxs-lookup"><span data-stu-id="67519-135">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
4.  <span data-ttu-id="67519-136">Wählen Sie die Variable aus, und klicken Sie dann auf **Variable verschieben**.</span><span class="sxs-lookup"><span data-stu-id="67519-136">Select the variable and then click **Move Variable**.</span></span>  
  
     <span data-ttu-id="67519-137">Wenn die Variable nicht im Fenster Variablen angezeigt wird, klicken Sie auf **Raster Optionen** , und wählen Sie dann **Variablen aller Bereiche anzeigen aus**.</span><span class="sxs-lookup"><span data-stu-id="67519-137">If you don't see the variable in the Variables window, click **Grid Options** and then select **Show variables of all scopes**.</span></span>  
  
5.  <span data-ttu-id="67519-138">Wählen Sie im Dialogfeld **Neuen Bereich auswählen** das Paket oder einen Container, Task oder Ereignishandler im Paket aus, um den Gültigkeitsbereich der Variablen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="67519-138">In the **Select New Scope** dialog box, select the package or a container, task, or event handler in the package, to change the variable scope.</span></span>  
  
6.  <span data-ttu-id="67519-139">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="67519-139">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67519-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="67519-140">See Also</span></span>  
 <span data-ttu-id="67519-141">[Integration Services-Variablen &#40;SSIS&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="67519-141">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="67519-142">[Verwenden von Variablen in Paketen](../../2014/integration-services/use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="67519-142">[Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md) </span></span>  
 <span data-ttu-id="67519-143">[Festlegen der Eigenschaften einer benutzerdefinierten Variablen](../../2014/integration-services/set-the-properties-of-a-user-defined-variable.md) </span><span class="sxs-lookup"><span data-stu-id="67519-143">[Set the Properties of a User-Defined Variable](../../2014/integration-services/set-the-properties-of-a-user-defined-variable.md) </span></span>  
 [<span data-ttu-id="67519-144">Verwenden der Werte von Variablen und Parametern in einem untergeordneten Paket</span><span class="sxs-lookup"><span data-stu-id="67519-144">Use the Values of Variables and Parameters in a Child Package</span></span>](../../2014/integration-services/use-the-values-of-variables-and-parameters-in-a-child-package.md)  
  
  
