---
title: Skript Task-Editor (Seite Skript) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.scripttask.script.f1
helpviewer_keywords:
- Script Task Editor
ms.assetid: 93da0e0d-83f5-406d-b144-4cce216571cb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4eec491cc689d7d5c616e0819075e1ee5159d4e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695834"
---
# <a name="script-task-editor-script-page"></a><span data-ttu-id="a732e-102">Skripttask-Editor (Seite Skript)</span><span class="sxs-lookup"><span data-stu-id="a732e-102">Script Task Editor (Script Page)</span></span>
  <span data-ttu-id="a732e-103">Mithilfe der Seite **Skript** des Dialogfelds **Skripttask-Editor** können Sie Skripteigenschaften festlegen und Variablen angeben, auf die dieses Skript zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="a732e-103">Use the **Script** page of the **Script Task Editor** dialog box to set script properties and specify variables that can be accessed by the script.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a732e-104">In [!INCLUDE[ssISversion10](../includes/ssisversion10-md.md)] und höheren Versionen werden alle Skripts vorkompiliert.</span><span class="sxs-lookup"><span data-stu-id="a732e-104">In [!INCLUDE[ssISversion10](../includes/ssisversion10-md.md)] and later versions, all scripts are precompiled.</span></span> <span data-ttu-id="a732e-105">In früheren Versionen wurde eine **PrecompileScriptIntoBinaryCode** -Eigenschaft festgelegt, um anzugeben, dass das Skript vorkompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="a732e-105">In earlier versions, you set a **PrecompileScriptIntoBinaryCode** property to specify that the script was precompiled.</span></span>  
  
 <span data-ttu-id="a732e-106">Weitere Informationen zum Skripttask finden Sie unter [Script Task](control-flow/script-task.md) und [Konfigurieren des Skripttasks im Skripttask-Editor](extending-packages-scripting/task/configuring-the-script-task-in-the-script-task-editor.md).</span><span class="sxs-lookup"><span data-stu-id="a732e-106">To learn more about the Script task, see [Script Task](control-flow/script-task.md) and [Configuring the Script Task in the Script Task Editor](extending-packages-scripting/task/configuring-the-script-task-in-the-script-task-editor.md).</span></span> <span data-ttu-id="a732e-107">Informationen zum Programmieren des Skripttasks finden Sie unter [Extending the Package with the Script Task](extending-packages-scripting/task/extending-the-package-with-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="a732e-107">To learn about programming the Script task, see [Extending the Package with the Script Task](extending-packages-scripting/task/extending-the-package-with-the-script-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a732e-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="a732e-108">Options</span></span>  
 <span data-ttu-id="a732e-109">**ScriptLanguage**</span><span class="sxs-lookup"><span data-stu-id="a732e-109">**ScriptLanguage**</span></span>  
 <span data-ttu-id="a732e-110">Wählen Sie die Skriptsprache für den Task aus, entweder [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual Basic oder [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="a732e-110">Select the scripting language for the task, either [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual C#.</span></span>  
  
 <span data-ttu-id="a732e-111">Nachdem Sie ein Skript für den Task erstellt haben, können Sie den Wert der **ScriptLanguage** -Eigenschaft nicht mehr ändern.</span><span class="sxs-lookup"><span data-stu-id="a732e-111">After you have created a script for the task, you cannot change the value of the **ScriptLanguage** property.</span></span>  
  
 <span data-ttu-id="a732e-112">Um die Standardskriptsprache für den Skripttask festzulegen, verwenden Sie im Dialogfeld **Optionen** auf der Seite **Allgemein** die Option **Skriptsprache** .</span><span class="sxs-lookup"><span data-stu-id="a732e-112">To set the default scripting language for the Script task, use the **Scripting language** option on **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="a732e-113">Weitere Informationen finden Sie unter [General Page](general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="a732e-113">For more information, see [General Page](general-page-of-integration-services-designers-options.md).</span></span>  
  
 <span data-ttu-id="a732e-114">**EntryPoint**</span><span class="sxs-lookup"><span data-stu-id="a732e-114">**EntryPoint**</span></span>  
 <span data-ttu-id="a732e-115">Geben Sie die Methode an, die die [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Laufzeit als Einstiegspunkt in den Code des Skripttasks aufruft.</span><span class="sxs-lookup"><span data-stu-id="a732e-115">Specify the method that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] runtime calls as the entry point into the code of the Script task.</span></span> <span data-ttu-id="a732e-116">Die angegebene Methode muss sich in der ScriptMain-Klasse des [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Tools for Applications (VSTA)-Projekts befinden. die ScriptMain-Klasse ist die Standardklasse, die von den Skript Vorlagen generiert wird.</span><span class="sxs-lookup"><span data-stu-id="a732e-116">The specified method must be in the ScriptMain class of the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Tools for Applications (VSTA) project The ScriptMain class is the default class generated by the script templates.</span></span>  
  
 <span data-ttu-id="a732e-117">Wenn Sie den Namen der Methode im VSTA-Projekt geändert haben, müssen Sie den Wert der **EntryPoint** -Eigenschaft ändern.</span><span class="sxs-lookup"><span data-stu-id="a732e-117">If you change the name of the method in the VSTA project, you must change the value of the **EntryPoint** property.</span></span>  
  
 <span data-ttu-id="a732e-118">**ReadOnlyVariables**</span><span class="sxs-lookup"><span data-stu-id="a732e-118">**ReadOnlyVariables**</span></span>  
 <span data-ttu-id="a732e-119">Geben Sie eine durch Trennzeichen getrennte Liste von schreibgeschützten Variablen ein, die für das Skript verfügbar sind, oder klicken Sie auf die Schaltfläche mit den Auslassungspunkten (**...**), und wählen Sie die Variablen im Dialogfeld **Variablen auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="a732e-119">Type a comma-separated list of read-only variables that are available to the script, or click the ellipsis (**...**) button and select the variables in the **Select variables** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a732e-120">Bei Variablennamen wird nach Groß-/Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="a732e-120">Variable names are case sensitive.</span></span>  
  
 <span data-ttu-id="a732e-121">**ReadWriteVariables**</span><span class="sxs-lookup"><span data-stu-id="a732e-121">**ReadWriteVariables**</span></span>  
 <span data-ttu-id="a732e-122">Geben Sie eine durch Trennzeichen getrennte Liste von Lese-/Schreibvariablen ein, die für das Skript verfügbar sind, oder klicken Sie auf die Schaltfläche mit den Auslassungspunkten (**...**), und wählen Sie die Variablen im Dialogfeld **Variablen auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="a732e-122">Type a comma-separated list of read/write variables that are available to the script, or click the ellipsis (**...**) button and select the variables in the **Select variables** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a732e-123">Bei Variablennamen wird nach Groß-/Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="a732e-123">Variable names are case sensitive.</span></span>  
  
 <span data-ttu-id="a732e-124">**Skript bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="a732e-124">**Edit Script**</span></span>  
 <span data-ttu-id="a732e-125">Öffnet die VSTA IDE, in der Sie das Skript erstellen oder ändern können.</span><span class="sxs-lookup"><span data-stu-id="a732e-125">Opens the VSTA IDE where you can create or modify the script.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a732e-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a732e-126">See Also</span></span>  
 <span data-ttu-id="a732e-127">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a732e-127">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="a732e-128">[Seite "Allgemein"](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="a732e-128">[General Page](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="a732e-129">[Skript Task-Editor &#40;Seite "Allgemein"&#41;](../../2014/integration-services/script-task-editor-general-page.md) </span><span class="sxs-lookup"><span data-stu-id="a732e-129">[Script Task Editor &#40;General Page&#41;](../../2014/integration-services/script-task-editor-general-page.md) </span></span>  
 <span data-ttu-id="a732e-130">[Seite Ausdrücke](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="a732e-130">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="a732e-131">[Skript Task-Beispiele](extending-packages-scripting-task-examples/script-task-examples.md) </span><span class="sxs-lookup"><span data-stu-id="a732e-131">[Script Task Examples](extending-packages-scripting-task-examples/script-task-examples.md) </span></span>  
 <span data-ttu-id="a732e-132">[Integration Services-Variablen &#40;SSIS&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="a732e-132">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 [<span data-ttu-id="a732e-133">Hinzufügen, Löschen, Ändern des Bereichs von benutzerdefinierten Variablen in einem Paket</span><span class="sxs-lookup"><span data-stu-id="a732e-133">Add, Delete, Change Scope of User-Defined Variable in a Package</span></span>](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md)  
  
  
