---
title: Verwenden der Werte von Variablen und Parametern in einem untergeordneten Paket | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- variables [Integration Services], passing between packages
- configurations [Integration Services]
- packages [Integration Services], configurations
- variables [Integration Services], adding
ms.assetid: 9b939edb-4e17-48e5-8428-855beb10049c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 28561db91e5e924d8b25f9c7be7a4a51c6c315ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619903"
---
# <a name="use-the-values-of-variables-and-parameters-in-a-child-package"></a><span data-ttu-id="56e4e-102">Verwenden der Werte von Variablen und Parametern in einem untergeordneten Paket</span><span class="sxs-lookup"><span data-stu-id="56e4e-102">Use the Values of Variables and Parameters in a Child Package</span></span>
  <span data-ttu-id="56e4e-103">In diesem Verfahren wird das Erstellen einer Paketkonfiguration beschrieben, die den Konfigurationstyp der übergeordneten Variablen verwendet.</span><span class="sxs-lookup"><span data-stu-id="56e4e-103">This procedure describes how to create a package configuration that uses the parent variable configuration type.</span></span> <span data-ttu-id="56e4e-104">Durch diesen Konfigurationstyp kann ein untergeordnetes Paket, das von einem übergeordneten Paket ausgeführt wird, auf eine Variable im übergeordneten Element zugreifen.</span><span class="sxs-lookup"><span data-stu-id="56e4e-104">This configuration type enables a child package that is run from a parent package to access a variable in the parent.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56e4e-105">Sie können auch Werte an ein untergeordnetes Paket übergeben, indem Sie den Task Paket ausführen konfigurieren, um untergeordneten Paketparametern Variablen oder Parameter für übergeordnete Pakete bzw. Projektparameter zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="56e4e-105">You can also pass values to a child package by configuring the Execute Package Task to map parent package variables or parameters, or project parameters, to child package parameters.</span></span> <span data-ttu-id="56e4e-106">Weitere Informationen finden Sie unter [Execute Package Task](control-flow/execute-package-task.md).</span><span class="sxs-lookup"><span data-stu-id="56e4e-106">For more information, see [Execute Package Task](control-flow/execute-package-task.md).</span></span>  
  
 <span data-ttu-id="56e4e-107">Dabei ist das Erstellen der Variablen im übergeordneten Paket vor dem Erstellen der Paketkonfiguration im untergeordneten Paket nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="56e4e-107">It is not necessary to create the variable in the parent package before you create the package configuration in the child package.</span></span> <span data-ttu-id="56e4e-108">Sie können dem übergeordneten Paket jederzeit die Variable hinzufügen. Allerdings müssen Sie in der Paketkonfiguration den genauen Namen der übergeordneten Variablen verwenden.</span><span class="sxs-lookup"><span data-stu-id="56e4e-108">You can add the variable to the parent package at any time, but you must use the exact name of the parent variable in the package configuration.</span></span> <span data-ttu-id="56e4e-109">Bevor Sie jedoch eine übergeordnete Variablenkonfiguration erstellen können, muss im untergeordneten Paket bereits eine Variable vorhanden sein, die von der Konfiguration aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="56e4e-109">However, before you can create a parent variable configuration, there must be an existing variable in the child package that the configuration can update.</span></span> <span data-ttu-id="56e4e-110">Weitere Informationen zum Hinzufügen und Konfigurieren von Variablen finden Sie unter [Hinzufügen, Löschen, Ändern des Bereichs von benutzerdefinierten Variablen in einem Paket](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span><span class="sxs-lookup"><span data-stu-id="56e4e-110">For more information about adding and configuring variables, see [Add, Delete, Change Scope of User-Defined Variable in a Package](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span></span>  
  
 <span data-ttu-id="56e4e-111">Der Gültigkeitsbereich der Variablen im übergeordneten Paket, das in einer übergeordneten Variablenkonfiguration verwendet wird, kann auf den Task Paket ausführen, auf den Container, in dem der Task enthalten ist, oder auf das Paket festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="56e4e-111">The scope of the variable in the parent package that is used in a parent variable configuration can be set to the Execute Package task, to the container that has the task, or to the package.</span></span> <span data-ttu-id="56e4e-112">Wenn in einem Paket mehrere gleichnamige Variablen vorhanden sind, wird die Variable verwendet, die im Gültigkeitsbereich des Tasks Paket ausführen am nächsten liegt.</span><span class="sxs-lookup"><span data-stu-id="56e4e-112">If multiple variables with the same name are defined in a package, the variable that is closest in scope to the Execute Package task is used.</span></span> <span data-ttu-id="56e4e-113">Der Gültigkeitsbereich, der am nächsten am Task Paket ausführen liegt, ist der Task selbst.</span><span class="sxs-lookup"><span data-stu-id="56e4e-113">The closest scope to the Execute Package task is the task itself.</span></span>  
  
### <a name="to-add-a-variable-to-a-parent-package"></a><span data-ttu-id="56e4e-114">So fügen Sie einem übergeordneten Paket eine Variable hinzu</span><span class="sxs-lookup"><span data-stu-id="56e4e-114">To add a variable to a parent package</span></span>  
  
1.  <span data-ttu-id="56e4e-115">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt mit dem Paket, dem Sie eine Variable hinzufügen möchten, um diese an ein untergeordnetes Paket zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="56e4e-115">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package to which you want to add a variable to pass to a child package.</span></span>  
  
2.  <span data-ttu-id="56e4e-116">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="56e4e-116">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="56e4e-117">Gehen Sie im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer zum Definieren des Gültigkeitsbereichs der Variablen wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="56e4e-117">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, to define the scope of the variable, do one of the following:</span></span>  
  
    -   <span data-ttu-id="56e4e-118">Um den Gültigkeitsbereich des Pakets festzulegen, klicken Sie an eine beliebige Stelle auf der Entwurfsoberfläche der Registerkarte **Ablaufsteuerung** .</span><span class="sxs-lookup"><span data-stu-id="56e4e-118">To set the scope to the package, click anywhere on the design surface of the **Control Flow** tab.</span></span>  
  
    -   <span data-ttu-id="56e4e-119">Klicken Sie auf den Container, um den Gültigkeitsbereich des übergeordneten Containers des Tasks "Paket ausführen" festzulegen.</span><span class="sxs-lookup"><span data-stu-id="56e4e-119">To set the scope to a parent container of the Execute Package task, click the container.</span></span>  
  
    -   <span data-ttu-id="56e4e-120">Klicken Sie auf den Task, um den Bereich auf den Task "Paket ausführen" festzulegen.</span><span class="sxs-lookup"><span data-stu-id="56e4e-120">To set the scope to the Execute Package task, click the task.</span></span>  
  
4.  <span data-ttu-id="56e4e-121">Fügen Sie eine Variable hinzu, und konfigurieren Sie diese.</span><span class="sxs-lookup"><span data-stu-id="56e4e-121">Add and configure a variable.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="56e4e-122">Wählen Sie einen Datentyp aus, der mit den in der Variablen gespeicherten Daten kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="56e4e-122">Select a data type that is compatible with the data that the variable will store.</span></span>  
  
5.  <span data-ttu-id="56e4e-123">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="56e4e-123">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-add-a-variable-to-a-child-package"></a><span data-ttu-id="56e4e-124">So fügen Sie einem untergeordneten Paket eine Variable hinzu</span><span class="sxs-lookup"><span data-stu-id="56e4e-124">To add a variable to a child package</span></span>  
  
1.  <span data-ttu-id="56e4e-125">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt mit dem Paket, dem Sie eine übergeordnete Variablenkonfiguration hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="56e4e-125">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package to which you want to add a parent variable configuration.</span></span>  
  
2.  <span data-ttu-id="56e4e-126">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="56e4e-126">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="56e4e-127">Klicken Sie im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer an eine beliebige Stelle auf der Entwurfsoberfläche der Registerkarte **Ablaufsteuerung** , um den Gültigkeitsbereich des Pakets festzulegen.</span><span class="sxs-lookup"><span data-stu-id="56e4e-127">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, to set the scope to the package, click anywhere on the design surface of the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="56e4e-128">Fügen Sie eine Variable hinzu, und konfigurieren Sie diese.</span><span class="sxs-lookup"><span data-stu-id="56e4e-128">Add and configure a variable.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="56e4e-129">Wählen Sie einen Datentyp aus, der mit den in der Variablen gespeicherten Daten kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="56e4e-129">Select a data type that is compatible with the data that the variable will store.</span></span>  
  
5.  <span data-ttu-id="56e4e-130">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="56e4e-130">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-add-a-parent-package-configuration-to-a-child-package"></a><span data-ttu-id="56e4e-131">So fügen Sie einem untergeordneten Paket eine übergeordnete Paketkonfiguration hinzu</span><span class="sxs-lookup"><span data-stu-id="56e4e-131">To add a parent package configuration to a child package</span></span>  
  
1.  <span data-ttu-id="56e4e-132">Öffnen Sie das untergeordnete Paket in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], falls das Paket noch nicht geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="56e4e-132">If it is not already open, open the child package in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="56e4e-133">Klicken Sie an eine beliebige Stelle auf der Entwurfsoberfläche der Registerkarte **Ablaufsteuerung** .</span><span class="sxs-lookup"><span data-stu-id="56e4e-133">Click anywhere on the design surface of the **Control Flow** tab.</span></span>  
  
3.  <span data-ttu-id="56e4e-134">Klicken Sie im Menü **SSIS** auf **Paketkonfigurationen**.</span><span class="sxs-lookup"><span data-stu-id="56e4e-134">On the **SSIS** menu, click **Package Configurations**.</span></span>  
  
4.  <span data-ttu-id="56e4e-135">Wählen Sie im Dialogfeld **Paketkonfigurationsplaner** die Option **Paketkonfigurationen aktivieren**aus, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="56e4e-135">In the **Package Configuration Organizer** dialog box, select **Enable package configuration**, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="56e4e-136">Klicken Sie auf der Willkommensseite des Paketkonfigurations-Assistenten auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="56e4e-136">On the welcome page of the Package Configuration Wizard, click **Next.**</span></span>  
  
6.  <span data-ttu-id="56e4e-137">Wählen Sie auf der Seite Konfigurationstyp auswählen in der Liste **Konfigurationstyp** die Option **Übergeordnete Paketvariable** aus, und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="56e4e-137">On the Select Configuration Type page, in the **Configuration type** list, select **Parent package variable** and do one of the following:</span></span>  
  
    -   <span data-ttu-id="56e4e-138">Wählen Sie die Option **Konfigurationseinstellungen direkt angeben**aus, und stellen Sie dann im Feld **Übergeordnete Variable** den Variablennamen des in der Konfiguration zu verwendenden übergeordneten Pakets bereit.</span><span class="sxs-lookup"><span data-stu-id="56e4e-138">Select **Specify configuration settings directly**, and then in the **Parent variable** box, provide the name of the variable in the parent package to use in the configuration.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="56e4e-139">Bei Variablennamen wird nach Groß-/Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="56e4e-139">Variable names are case sensitive.</span></span>  
  
    -   <span data-ttu-id="56e4e-140">Wählen Sie **Konfigurationsspeicherort ist in einer Umgebungsvariablen gespeichert** aus. Wählen Sie dann in der Liste **Umgebungsvariable**die Umgebungsvariable aus, die den Namen der Variablen enthält.</span><span class="sxs-lookup"><span data-stu-id="56e4e-140">Select or **Configuration location is stored in an environment variable,** and then in the **Environment variable list**, select the environmentvariable that contains the name of the variable.</span></span>  
  
7.  <span data-ttu-id="56e4e-141">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="56e4e-141">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="56e4e-142">Erweitern Sie auf der Seite Zieleigenschaft auswählen den Knoten **Variable** , erweitern Sie den Knoten **Eigenschaften** der zu konfigurierenden Variablen, und klicken Sie dann auf die von der Konfiguration festzulegende Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="56e4e-142">On the Select Target Property page, expand the **Variable** node, and expand the **Properties** node of the variable to configure, and then click the property to be set by the configuration.</span></span>  
  
9. <span data-ttu-id="56e4e-143">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="56e4e-143">Click **Next**.</span></span>  
  
10. <span data-ttu-id="56e4e-144">Ändern Sie optional auf der Seite Assistenten abschließen den Standardnamen der Konfiguration, und überprüfen Sie die Konfigurationsinformationen.</span><span class="sxs-lookup"><span data-stu-id="56e4e-144">On the Completing the Wizard page, optionally, modify the default name of the configuration and review the configuration information.</span></span>  
  
11. <span data-ttu-id="56e4e-145">Klicken Sie auf **Fertig stellen** , um den Assistenten zu beenden und zum Dialogfeld **Paketkonfigurationsplaner** zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="56e4e-145">Click **Finish** to complete the wizard and return to the **Package Configuration Organizer** dialog box.</span></span>  
  
12. <span data-ttu-id="56e4e-146">Die neue Konfiguration wird im Dialogfeld **Paketkonfigurationsplaner** im Feld **Konfiguration** aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="56e4e-146">In the **Package Configuration Organizer** dialog box, the **Configuration** box lists the new configuration.</span></span>  
  
13. <span data-ttu-id="56e4e-147">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="56e4e-147">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56e4e-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56e4e-148">See Also</span></span>  
 <span data-ttu-id="56e4e-149">[Paket Konfigurationen](../../2014/integration-services/package-configurations.md) </span><span class="sxs-lookup"><span data-stu-id="56e4e-149">[Package Configurations](../../2014/integration-services/package-configurations.md) </span></span>  
 <span data-ttu-id="56e4e-150">[Erstellen von Paket Konfigurationen](../../2014/integration-services/create-package-configurations.md) </span><span class="sxs-lookup"><span data-stu-id="56e4e-150">[Create Package Configurations](../../2014/integration-services/create-package-configurations.md) </span></span>  
 <span data-ttu-id="56e4e-151">[Integration Services-Variablen &#40;SSIS&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="56e4e-151">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 [<span data-ttu-id="56e4e-152">Verwenden von Variablen in Paketen</span><span class="sxs-lookup"><span data-stu-id="56e4e-152">Use Variables in Packages</span></span>](../../2014/integration-services/use-variables-in-packages.md)  
  
  
