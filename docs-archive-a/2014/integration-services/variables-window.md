---
title: Fenster „Variablen“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.variables.f1
helpviewer_keywords:
- Variables Window dialog box
ms.assetid: f405e5ce-ef69-4c58-8c7d-a3d44dfe9ab0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ffd6da67386291c14ebf588da9a1cf8f399214b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619897"
---
# <a name="variables-window"></a><span data-ttu-id="b3ef3-102">Variablen (Fenster)</span><span class="sxs-lookup"><span data-stu-id="b3ef3-102">Variables Window</span></span>
  <span data-ttu-id="b3ef3-103">Verwenden Sie das Fenster **Variablen** , um benutzerdefinierte Variablen zu erstellen und zu ändern sowie um Systemvariablen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-103">Use the **Variables** window to create and modify user-defined variables and view system variables.</span></span>  
  
 <span data-ttu-id="b3ef3-104">Das Fenster **Variablen** befindet sich in **standardmäßig im SSIS-Designer unterhalb des Bereichs** Verbindungs-Manager [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3ef3-104">By default, the **Variables** window is located below the **Connection Managers** area in the SSIS Designer, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="b3ef3-105">Wenn das Fenster **Variablen** nicht angezeigt wird, klicken Sie im Menü **SSIS** auf **Variablen**, um das Fenster einzublenden.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-105">If you don't see the **Variables** window, click **Variables** on the **SSIS** menu to display the window.</span></span>  
  
 <span data-ttu-id="b3ef3-106">Sie können das Fenster **Variablen** auch anzeigen, indem Sie im Dialogfeld **Optionen** auf der Seite **Tastatur** den Befehl View.Variables einer beliebigen Tastenkombination zuordnen.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-106">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3ef3-107">Die Werte der Eigenschaften `Name` und `Namespace` müssen mit einem Buchstaben beginnen, wie in Unicode-Standard 2.0 definiert ist, oder mit einem Unterstrich (_).</span><span class="sxs-lookup"><span data-stu-id="b3ef3-107">The values of the `Name` and `Namespace` properties must begin with an alphabetic character letter as defined by the Unicode Standard 2.0, or an underscore (_).</span></span> <span data-ttu-id="b3ef3-108">Bei den nachfolgenden Zeichen kann es sich um Buchstaben oder Zahlen gemäß Unicode-Standard 2.0 oder um einem Unterstrich (\_) handeln.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-108">Subsequent characters can be letters or numbers as defined in the Unicode Standard 2.0, or the underscore (\_).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b3ef3-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="b3ef3-109">Options</span></span>  
 <span data-ttu-id="b3ef3-110">**Hinzufügen von Variablen**</span><span class="sxs-lookup"><span data-stu-id="b3ef3-110">**Add Variable**</span></span>  
 <span data-ttu-id="b3ef3-111">Fügt eine benutzerdefinierte Variable hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-111">Add a user-defined variable.</span></span>  
  
 <span data-ttu-id="b3ef3-112">**Variable verschieben**</span><span class="sxs-lookup"><span data-stu-id="b3ef3-112">**Move Variable**</span></span>  
 <span data-ttu-id="b3ef3-113">Klicken Sie in der Liste auf eine Variable, und klicken Sie dann auf **Variable verschieben** , um den Gültigkeitsbereich der Variablen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-113">Click a variable in the list, and then click **Move Variable** to change the variable scope.</span></span> <span data-ttu-id="b3ef3-114">Wählen Sie im Dialogfeld **Neuen Bereich auswählen** das Paket oder einen Container, Task oder Ereignishandler im Paket aus, um den Gültigkeitsbereich der Variablen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-114">In the **Select New Scope** dialog box, select the package or a container, task, or event handler in the package, to change the variable scope.</span></span>  
  
 <span data-ttu-id="b3ef3-115">Weitere Informationen zu Variablenbereichen finden Sie unter [Integration Services-Variablen &#40;SSIS&#41;](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="b3ef3-115">For more information about variable scope, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
 <span data-ttu-id="b3ef3-116">**Variable löschen**</span><span class="sxs-lookup"><span data-stu-id="b3ef3-116">**Delete Variable**</span></span>  
 <span data-ttu-id="b3ef3-117">Wählen Sie in der Liste eine Variable aus, und klicken Sie auf **Variable löschen**.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-117">Select a variable from the list, and then click **Delete Variable**.</span></span>  
  
 <span data-ttu-id="b3ef3-118">**Rasteroptionen**</span><span class="sxs-lookup"><span data-stu-id="b3ef3-118">**Grid Options**</span></span>  
 <span data-ttu-id="b3ef3-119">Klicken Sie auf diese Option, um das Dialogfeld **Variable Rasteroptionen** zu öffnen. Hier können Sie die Spaltenauswahl ändern und Filter auf das Fenster **Variablen** anwenden.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-119">Click to open the **Variable Grid Options** dialog box where you can change the column selection and apply filters to the **Variables** window.</span></span> <span data-ttu-id="b3ef3-120">Weitere Informationen finden Sie unter [Variable Rasteroptionen](../../2014/integration-services/variable-grid-options.md).</span><span class="sxs-lookup"><span data-stu-id="b3ef3-120">For more information, see [Variable Grid Options](../../2014/integration-services/variable-grid-options.md).</span></span>  
  
 `Name`  
 <span data-ttu-id="b3ef3-121">Zeigt den Variablennamen an.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-121">View the variable name.</span></span> <span data-ttu-id="b3ef3-122">Bei benutzerdefinierten Variablen können Sie den Namen der Variablen aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-122">You can update the name for user-defined variables.</span></span>  
  
 <span data-ttu-id="b3ef3-123">**Umfang**</span><span class="sxs-lookup"><span data-stu-id="b3ef3-123">**Scope**</span></span>  
 <span data-ttu-id="b3ef3-124">Zeigt den Bereich der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-124">View the scope of the variable.</span></span> <span data-ttu-id="b3ef3-125">Eine Variable verfügt entweder über den Bereich des gesamten Pakets oder den Bereich eines Containers bzw. Tasks.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-125">A variable has either the scope of the entire package, or the scope of a container or task.</span></span> <span data-ttu-id="b3ef3-126">Der Bereich der Variable muss ausreichend sein, sodass die Variable für alle anderen Tasks oder Komponenten sichtbar ist, die ihren Wert lesen oder festlegen müssen.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-126">The scope of the variable must be sufficient so that the variable is visible to any other tasks or components that need to read or set its value.</span></span>  
  
 <span data-ttu-id="b3ef3-127">Sie können den Bereich ändern, indem Sie auf die Variable klicken und dann im Fenster **Variablen** auf **Variable verschieben** klicken.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-127">You can change the scope by clicking the variable and then clicking **Move Variable** in the **Variables** window.</span></span>  
  
 <span data-ttu-id="b3ef3-128">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="b3ef3-128">**Data Type**</span></span>  
 <span data-ttu-id="b3ef3-129">Zeigt den Datentyp der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-129">View the data type of the variable.</span></span> <span data-ttu-id="b3ef3-130">Bei benutzerdefinierten Variablen können Sie einen Datentyp in der Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-130">You can select a data type from the list for user-defined variables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b3ef3-131">Wenn Sie der Variable einen Ausdruck zuweisen, können Sie den Datentyp nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-131">If you assign an expression to the variable, you cannot change the data type.</span></span>  
  
 <span data-ttu-id="b3ef3-132">**Wert**</span><span class="sxs-lookup"><span data-stu-id="b3ef3-132">**Value**</span></span>  
 <span data-ttu-id="b3ef3-133">Zeigt den Wert der Variablen an.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-133">View the variable value.</span></span> <span data-ttu-id="b3ef3-134">Bei benutzerdefinierten Variablen können Sie den Wert aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-134">You can update the value for user-defined variables.</span></span> <span data-ttu-id="b3ef3-135">Dieser Wert kann ein Literal oder ein Ausdruck sein, und der Wert kann eine mehrzeilige Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-135">This value can be a literal or an expression, and the value can be a multi-line string.</span></span> <span data-ttu-id="b3ef3-136">Um der Variable einen Ausdruck zuzuweisen, klicken Sie auf die Schaltfläche mit den Auslassungspunkten neben der Spalte **Ausdruck** im Fenster **Variablen** .</span><span class="sxs-lookup"><span data-stu-id="b3ef3-136">To assign an expression to the variable, click the ellipse button that is next to the **Expression** column in the **Variables** window.</span></span>  
  
 `Namespace`  
 <span data-ttu-id="b3ef3-137">Zeigt den Namen des Namespaces an.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-137">View the namespace name.</span></span> <span data-ttu-id="b3ef3-138">Benutzerdefinierte Variablen werden anfänglich im **User** -Namespace erstellt, aber Sie können den Namespace Namen im Feld ändern `Namespace` .</span><span class="sxs-lookup"><span data-stu-id="b3ef3-138">User-defined variables are initially created in the **User** namespace, but you can change the namespace name in the `Namespace` field.</span></span> <span data-ttu-id="b3ef3-139">Klicken Sie zum Anzeigen dieser Spalte auf **Rasteroptionen**.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-139">To display this column, click **Grid Options**.</span></span>  
  
 <span data-ttu-id="b3ef3-140">**Ereignis bei Änderung des Variablenwertes auslösen**</span><span class="sxs-lookup"><span data-stu-id="b3ef3-140">**Raise Change Event**</span></span>  
 <span data-ttu-id="b3ef3-141">Gibt an, ob das `OnVariableValueChanged`-Ereignis ausgelöst werden soll, wenn ein Wert geändert wird.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-141">Indicate whether to raise the `OnVariableValueChanged` event when a value changes.</span></span> <span data-ttu-id="b3ef3-142">Bei benutzerdefinierten und Systemvariablen können Sie den Wert aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-142">You can update the value for user-defined and system variables.</span></span> <span data-ttu-id="b3ef3-143">Standardmäßig wird diese Spalte nicht im Fenster **Variablen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-143">By default, the **Variables** window does not list this column.</span></span> <span data-ttu-id="b3ef3-144">Klicken Sie zum Anzeigen dieser Spalte auf **Rasteroptionen**.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-144">To display this column, click **Grid Options**.</span></span>  
  
 <span data-ttu-id="b3ef3-145">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b3ef3-145">**Description**</span></span>  
 <span data-ttu-id="b3ef3-146">Anzeigen der Variablenbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-146">View the variable description.</span></span> <span data-ttu-id="b3ef3-147">Sie können die Beschreibung für benutzerdefinierte Variablen ändern.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-147">You can change the description for user-defined variables.</span></span> <span data-ttu-id="b3ef3-148">Standardmäßig wird diese Spalte nicht im Fenster **Variablen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-148">By default, the **Variables** window does not list this column.</span></span> <span data-ttu-id="b3ef3-149">Klicken Sie zum Anzeigen dieser Spalte auf **Rasteroptionen**.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-149">To display this column, click **Grid Options**.</span></span>  
  
 <span data-ttu-id="b3ef3-150">**Ausdruck**</span><span class="sxs-lookup"><span data-stu-id="b3ef3-150">**Expression**</span></span>  
 <span data-ttu-id="b3ef3-151">Anzeigen des der Variable zugewiesenen Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-151">View the expression assigned to the variable.</span></span> <span data-ttu-id="b3ef3-152">Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um einen Ausdruck zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-152">To assign an expression, click the ellipse button.</span></span>  
  
 <span data-ttu-id="b3ef3-153">Wenn Sie einer Variablen einen Ausdruck zuweisen, wird ein spezieller Symbolmarker neben der Variablen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-153">If you assign an expression to a variable, a special icon marker displays next to the variable.</span></span> <span data-ttu-id="b3ef3-154">Dieser spezielle Symbolmarker wird auch neben Verbindungs-Managern und Tasks angezeigt, für die Ausdrücke festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="b3ef3-154">This special icon marker also displays next to connection managers and tasks that have expressions set on them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3ef3-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b3ef3-155">See Also</span></span>  
 <span data-ttu-id="b3ef3-156">[Integration Services-Variablen &#40;SSIS&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="b3ef3-156">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="b3ef3-157">[Verwenden von Variablen in Paketen](../../2014/integration-services/use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="b3ef3-157">[Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md) </span></span>  
 <span data-ttu-id="b3ef3-158">[Integration Services &#40;SSIS-&#41; Ausdrücke](expressions/integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="b3ef3-158">[Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md) </span></span>  
 [<span data-ttu-id="b3ef3-159">Generieren von Dumpdateien für die Paketausführung</span><span class="sxs-lookup"><span data-stu-id="b3ef3-159">Generating Dump Files for Package Execution</span></span>](troubleshooting/generating-dump-files-for-package-execution.md)  
  
  
