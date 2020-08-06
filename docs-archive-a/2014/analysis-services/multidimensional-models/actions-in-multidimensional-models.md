---
title: Aktionen in mehrdimensionalen Modellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- actions [Analysis Services], creating
- report actions [Analysis Services]
- drillthrough actions [Analysis Services]
- cubes [Analysis Services], actions
ms.assetid: b9fee2b9-05a5-4077-848d-d8457326dc27
author: minewiskan
ms.author: owend
ms.openlocfilehash: ce42907190363be085e8f4d8e9adfbab52a70590
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616759"
---
# <a name="actions-in-multidimensional-models"></a><span data-ttu-id="57ac2-102">Aktionen in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="57ac2-102">Actions in Multidimensional Models</span></span>
  <span data-ttu-id="57ac2-103">Eine Aktion ist ein vom Endbenutzer initiierter Vorgang, der auf einem ausgewählten Cube oder Teil eines Cubes ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="57ac2-103">An action is an end user-initiated operation upon a selected cube or portion of a cube.</span></span> <span data-ttu-id="57ac2-104">Der Vorgang kann eine Anwendung mit dem ausgewählten Element als Parameter starten, oder er kann Informationen zum ausgewählten Element abrufen.</span><span class="sxs-lookup"><span data-stu-id="57ac2-104">The operation can start an application with the selected item as a parameter, or it can retrieve information about the selected item.</span></span> <span data-ttu-id="57ac2-105">Weitere Informationen zu Aktionstypen finden Sie unter [Aktionen &#40;Analysis Services – Mehrdimensionale Daten&#41;](actions-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="57ac2-105">For more information about actions, see [Actions &#40;Analysis Services - Multidimensional Data&#41;](actions-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="57ac2-106">Mithilfe der Registerkarte **Aktionen** des Cube-Designers können Sie Aktionen für einen Cube erstellen.</span><span class="sxs-lookup"><span data-stu-id="57ac2-106">Use the **Actions** tab of Cube Designer to build actions for a cube.</span></span> <span data-ttu-id="57ac2-107">Geben Sie Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="57ac2-107">Specify the following:</span></span>  
  
 <span data-ttu-id="57ac2-108">**Name**</span><span class="sxs-lookup"><span data-stu-id="57ac2-108">**Name**</span></span>  
 <span data-ttu-id="57ac2-109">Wählen Sie einen Namen für die Aktion aus.</span><span class="sxs-lookup"><span data-stu-id="57ac2-109">Select a name that identifies the action.</span></span>  
  
 <span data-ttu-id="57ac2-110">**Aktionsziel**</span><span class="sxs-lookup"><span data-stu-id="57ac2-110">**Action Target**</span></span>  
 <span data-ttu-id="57ac2-111">Wählen Sie das Objekt aus, dem die Aktion angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="57ac2-111">Select the object to which the action is attached.</span></span> <span data-ttu-id="57ac2-112">In Clientanwendungen wird die Aktion grundsätzlich angezeigt, wenn der Endbenutzer das Zielobjekt ausgewählt hat; jedoch bestimmt die Clientanwendung, welcher Endbenutzervorgang Aktionen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="57ac2-112">Generally, in client applications, the action is displayed when end users select the target object; however, the client application determines which end-user operation displays actions.</span></span> <span data-ttu-id="57ac2-113">Wählen Sie für **Zieltyp**aus den folgenden Objekten aus:</span><span class="sxs-lookup"><span data-stu-id="57ac2-113">For **Target type**, select from the following objects:</span></span>  
  
-   <span data-ttu-id="57ac2-114">Attributelemente</span><span class="sxs-lookup"><span data-stu-id="57ac2-114">Attribute members</span></span>  
  
-   <span data-ttu-id="57ac2-115">Zellen</span><span class="sxs-lookup"><span data-stu-id="57ac2-115">Cells</span></span>  
  
-   <span data-ttu-id="57ac2-116">Cube</span><span class="sxs-lookup"><span data-stu-id="57ac2-116">Cube</span></span>  
  
-   <span data-ttu-id="57ac2-117">Dimensionselemente</span><span class="sxs-lookup"><span data-stu-id="57ac2-117">Dimension members</span></span>  
  
-   <span data-ttu-id="57ac2-118">Hierarchy</span><span class="sxs-lookup"><span data-stu-id="57ac2-118">Hierarchy</span></span>  
  
-   <span data-ttu-id="57ac2-119">Hierarchieelemente</span><span class="sxs-lookup"><span data-stu-id="57ac2-119">Hierarchy members</span></span>  
  
-   <span data-ttu-id="57ac2-120">Ebene</span><span class="sxs-lookup"><span data-stu-id="57ac2-120">Level</span></span>  
  
-   <span data-ttu-id="57ac2-121">Ebenenelemente</span><span class="sxs-lookup"><span data-stu-id="57ac2-121">Level members</span></span>  
  
 <span data-ttu-id="57ac2-122">Nachdem Sie den Zielobjekttyp ausgewählt haben, wählen Sie unter **Zielobjekt**das Cubeobjekt vom entsprechenden Typ aus.</span><span class="sxs-lookup"><span data-stu-id="57ac2-122">After you select the target object type, under **Target object**, select the cube object of the designated type.</span></span>  
  
 <span data-ttu-id="57ac2-123">**Bedingung (Optional)**</span><span class="sxs-lookup"><span data-stu-id="57ac2-123">**Condition (Optional)**</span></span>  
 <span data-ttu-id="57ac2-124">Geben Sie einen optionalen MDX-Ausdruck (Multidimensional Expressions) an, der zu einem Booleschen Wert aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="57ac2-124">Specify an optional Multidimensional Expressions (MDX) expression that resolves to a Boolean value.</span></span> <span data-ttu-id="57ac2-125">Beim Wert `True` wird die Aktion für das angegebene Ziel durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="57ac2-125">If the value is `True`, the action is performed on the specified target.</span></span> <span data-ttu-id="57ac2-126">Beim Wert `False` wird die Aktion nicht durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="57ac2-126">If the value is `False`, the action is not performed.</span></span>  
  
 <span data-ttu-id="57ac2-127">**Aktionsinhalt**</span><span class="sxs-lookup"><span data-stu-id="57ac2-127">**Action Content**</span></span>  
 <span data-ttu-id="57ac2-128">Wählen Sie den Typ der Aktion aus.</span><span class="sxs-lookup"><span data-stu-id="57ac2-128">Select the type of action.</span></span> <span data-ttu-id="57ac2-129">In der folgenden Tabelle werden die verfügbaren Aktionstypen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="57ac2-129">The following table summarizes the available types.</span></span>  
  
|<span data-ttu-id="57ac2-130">type</span><span class="sxs-lookup"><span data-stu-id="57ac2-130">Type</span></span>|<span data-ttu-id="57ac2-131">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="57ac2-131">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="57ac2-132">Dataset</span><span class="sxs-lookup"><span data-stu-id="57ac2-132">Data Set</span></span>|<span data-ttu-id="57ac2-133">Ruft ein Dataset ab.</span><span class="sxs-lookup"><span data-stu-id="57ac2-133">Retrieves a dataset.</span></span>|  
|<span data-ttu-id="57ac2-134">Proprietär</span><span class="sxs-lookup"><span data-stu-id="57ac2-134">Proprietary</span></span>|<span data-ttu-id="57ac2-135">Führt einen Vorgang über eine Schnittstelle aus, die nicht in dieser Tabelle aufgelistet ist.</span><span class="sxs-lookup"><span data-stu-id="57ac2-135">Performs an operation by using an interface other than those listed in this table.</span></span>|  
|<span data-ttu-id="57ac2-136">Rowset</span><span class="sxs-lookup"><span data-stu-id="57ac2-136">Row Set</span></span>|<span data-ttu-id="57ac2-137">Ruft ein Rowset ab.</span><span class="sxs-lookup"><span data-stu-id="57ac2-137">Retrieves a rowset.</span></span>|  
|<span data-ttu-id="57ac2-138">Anweisung</span><span class="sxs-lookup"><span data-stu-id="57ac2-138">Statement</span></span>|<span data-ttu-id="57ac2-139">Gibt einen OLE DB-Befehl zurück.</span><span class="sxs-lookup"><span data-stu-id="57ac2-139">Runs an OLE DB command.</span></span>|  
|<span data-ttu-id="57ac2-140">URL</span><span class="sxs-lookup"><span data-stu-id="57ac2-140">URL</span></span>|<span data-ttu-id="57ac2-141">Zeigt eine veränderliche Seite in einem Internetbrowser an.</span><span class="sxs-lookup"><span data-stu-id="57ac2-141">Displays a variable page in an Internet browser.</span></span>|  
  
 <span data-ttu-id="57ac2-142">Geben Sie für **Aktionsausdruck**die Parameter an, die beim Ausführen der Aktion übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="57ac2-142">For **Action Expression**, specify the parameters that are passed when the action is run.</span></span> <span data-ttu-id="57ac2-143">Die Syntax muss zu einer Zeichenfolge ausgewertet werden, und Sie müssen einen in MDX geschriebenen Ausdruck einschließen.</span><span class="sxs-lookup"><span data-stu-id="57ac2-143">The syntax must evaluate to a string, and you must include an expression written in MDX.</span></span> <span data-ttu-id="57ac2-144">Der MDX-Ausdruck kann z. B. einen Teil des Cubes anzeigen, der in die Syntax eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="57ac2-144">For example, your MDX expression can indicate a part of the cube that is included in the syntax.</span></span> <span data-ttu-id="57ac2-145">MDX-Ausdrücke werden ausgewertet, bevor die Parameter übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="57ac2-145">MDX expressions are evaluated before the parameters are passed.</span></span> <span data-ttu-id="57ac2-146">Darüber hinaus steht Ihnen der MDX-Generator zur Verfügung, der Sie bei der Erstellung von MDX-Ausdrücken unterstützt.</span><span class="sxs-lookup"><span data-stu-id="57ac2-146">Also, MDX Builder is available to help you build MDX expressions.</span></span>  
  
 <span data-ttu-id="57ac2-147">**Zusätzliche Eigenschaften**</span><span class="sxs-lookup"><span data-stu-id="57ac2-147">**Additional Properties**</span></span>  
 <span data-ttu-id="57ac2-148">Wählen Sie die Eigenschaft aus.</span><span class="sxs-lookup"><span data-stu-id="57ac2-148">Select the property.</span></span> <span data-ttu-id="57ac2-149">In der folgenden Tabelle werden die verfügbaren Eigenschaften zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="57ac2-149">The following table summarizes the available properties.</span></span>  
  
|<span data-ttu-id="57ac2-150">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="57ac2-150">Property</span></span>|<span data-ttu-id="57ac2-151">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="57ac2-151">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="57ac2-152">**Aufruf**</span><span class="sxs-lookup"><span data-stu-id="57ac2-152">**Invocation**</span></span>|<span data-ttu-id="57ac2-153">Gibt an, wie die Aktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="57ac2-153">Specifies how the action is run.</span></span> <span data-ttu-id="57ac2-154">Die Standardeinstellung Interaktiv gibt an, dass die Aktion ausgeführt wird, wenn ein Benutzer auf ein Objekt zugreift.</span><span class="sxs-lookup"><span data-stu-id="57ac2-154">Interactive, the default, specifies that the action is run when a user accesses an object.</span></span> <span data-ttu-id="57ac2-155">Die möglichen Einstellungen sind:</span><span class="sxs-lookup"><span data-stu-id="57ac2-155">The possible settings are:</span></span><br /><br /> <span data-ttu-id="57ac2-156">Batch</span><span class="sxs-lookup"><span data-stu-id="57ac2-156">Batch</span></span><br /><br /> <span data-ttu-id="57ac2-157">Interactive</span><span class="sxs-lookup"><span data-stu-id="57ac2-157">Interactive</span></span><br /><br /> <span data-ttu-id="57ac2-158">Beim Öffnen</span><span class="sxs-lookup"><span data-stu-id="57ac2-158">On Open</span></span>|  
|<span data-ttu-id="57ac2-159">**Anwendung**</span><span class="sxs-lookup"><span data-stu-id="57ac2-159">**Application**</span></span>|<span data-ttu-id="57ac2-160">Beschreibt die Anwendung der Aktion.</span><span class="sxs-lookup"><span data-stu-id="57ac2-160">Describes the application of the action.</span></span>|  
|<span data-ttu-id="57ac2-161">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="57ac2-161">**Description**</span></span>|<span data-ttu-id="57ac2-162">Beschreibt die Aktion.</span><span class="sxs-lookup"><span data-stu-id="57ac2-162">Describes the action.</span></span>|  
|<span data-ttu-id="57ac2-163">**Caption**</span><span class="sxs-lookup"><span data-stu-id="57ac2-163">**Caption**</span></span>|<span data-ttu-id="57ac2-164">Stellt eine Beschriftung bereit, die für die Aktion angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="57ac2-164">Provides a caption that is displayed for the action.</span></span> <span data-ttu-id="57ac2-165">Wenn es sich bei der Beschriftung um MDX handelt, geben Sie `True` für **Beschriftung ist MDX**an.</span><span class="sxs-lookup"><span data-stu-id="57ac2-165">If the caption is MDX, specify `True` for **Caption is MDX**.</span></span>|  
|<span data-ttu-id="57ac2-166">**Beschriftung ist MDX**</span><span class="sxs-lookup"><span data-stu-id="57ac2-166">**Caption is MDX**</span></span>|<span data-ttu-id="57ac2-167">Geben Sie `True` an, wenn es sich bei der Beschriftung um MDX handelt; andernfalls geben Sie `False` an.</span><span class="sxs-lookup"><span data-stu-id="57ac2-167">Specify `True` if the caption is MDX or `False` if it is not.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="57ac2-168">Sie müssen Analysis Services Scripting Language (ASSL) oder Analysis Management Objects (AMO) verwenden, um HTML- und Befehlszeilen-Aktionstypen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="57ac2-168">You must use Analysis Services Scripting Language (ASSL) or Analysis Management Objects (AMO) to define HTML and Command Line action types.</span></span> <span data-ttu-id="57ac2-169">Weitere Informationen finden Sie unter [Action-Element &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/objects/action-element-assl), [Type-Element &#40;Action&#41; &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/type-element-action-assl) und [Programmieren von erweiterten AMO OLAP-Objekten](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-advanced-objects).</span><span class="sxs-lookup"><span data-stu-id="57ac2-169">For more information, see [Action Element &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/objects/action-element-assl), [Type Element &#40;Action&#41; &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/type-element-action-assl), and [Programming AMO OLAP Advanced Objects](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-advanced-objects).</span></span>  
  
## <a name="creating-a-reporting-action"></a><span data-ttu-id="57ac2-170">Erstellen einer Berichtsaktion</span><span class="sxs-lookup"><span data-stu-id="57ac2-170">Creating a Reporting Action</span></span>  
 <span data-ttu-id="57ac2-171">Der Berichtsserver antwortet auf URL-basierte Anforderungen nach Berichten.</span><span class="sxs-lookup"><span data-stu-id="57ac2-171">The report server responds to URL-based requests for reports.</span></span> <span data-ttu-id="57ac2-172">Klicken Sie zum Erstellen einer Berichtsaktion im Menü **Cube** auf **Neue Berichtsaktion**.</span><span class="sxs-lookup"><span data-stu-id="57ac2-172">To create a reporting action, on the **Cube** menu, click **New Reporting Action**.</span></span> <span data-ttu-id="57ac2-173">Eine Berichtsaktion zeichnet sich durch die folgenden spezifischen Optionen aus.</span><span class="sxs-lookup"><span data-stu-id="57ac2-173">The following options are specific to a reporting action.</span></span>  
  
 <span data-ttu-id="57ac2-174">**Berichts Server**</span><span class="sxs-lookup"><span data-stu-id="57ac2-174">**Report Server**</span></span>  
 <span data-ttu-id="57ac2-175">Die in der folgenden Tabelle beschriebenen Eigenschaften sind spezifisch für den Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="57ac2-175">The properties described in the following table are specified for the report server.</span></span>  
  
|<span data-ttu-id="57ac2-176">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="57ac2-176">Property</span></span>|<span data-ttu-id="57ac2-177">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="57ac2-177">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="57ac2-178">**Servername**</span><span class="sxs-lookup"><span data-stu-id="57ac2-178">**Server name**</span></span>|<span data-ttu-id="57ac2-179">Name des Computers, auf dem der Berichtsserver ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="57ac2-179">The name of the computer running report server.</span></span>|  
|<span data-ttu-id="57ac2-180">**Serverpfad**</span><span class="sxs-lookup"><span data-stu-id="57ac2-180">**Server path**</span></span>|<span data-ttu-id="57ac2-181">Der vom Berichtsserver verfügbar gemachte Pfad.</span><span class="sxs-lookup"><span data-stu-id="57ac2-181">The path exposed by report server.</span></span>|  
|<span data-ttu-id="57ac2-182">**Berichtsformat**</span><span class="sxs-lookup"><span data-stu-id="57ac2-182">**Report format**</span></span>|<span data-ttu-id="57ac2-183">HTML5, HTML3, Excel oder PDF.</span><span class="sxs-lookup"><span data-stu-id="57ac2-183">HTML5, HTML3, Excel, or PDF.</span></span>|  
  
 <span data-ttu-id="57ac2-184">**Parameter (Optional)**</span><span class="sxs-lookup"><span data-stu-id="57ac2-184">**Parameters (Optional)**</span></span>  
 <span data-ttu-id="57ac2-185">Die Parameter werden als Bestandteil der URL-Zeichenfolge an den Server gesendet, wenn die Aktion erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="57ac2-185">The parameters are sent to the server as part of the URL string when the action is created.</span></span> <span data-ttu-id="57ac2-186">Dazu gehören **Parametername** und **Parameterwert**, wobei es sich um einen MDX-Ausdruck handelt.</span><span class="sxs-lookup"><span data-stu-id="57ac2-186">They include **Parameter Name** and **Parameter Value**, which is an MDX expression.</span></span>  
  
 <span data-ttu-id="57ac2-187">Die Berichtsserver-URL setzt sich wie folgt zusammen:</span><span class="sxs-lookup"><span data-stu-id="57ac2-187">The report server URL is constructed as follows:</span></span>  
  
```  
  
http://  
host  
/  
virtualdirectory  
/Path&  
parametername1  
=  
parametervalue1  
& ...  
```  
  
 <span data-ttu-id="57ac2-188">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="57ac2-188">For example:</span></span>  
  
```  
http://localhost/ReportServer/Sales/YearlySalesByCategory?rs:Command=Render&Region=West  
```  
  
## <a name="creating-a-drillthrough-action"></a><span data-ttu-id="57ac2-189">Erstellen einer Drillthroughaktion</span><span class="sxs-lookup"><span data-stu-id="57ac2-189">Creating a Drillthrough Action</span></span>  
 <span data-ttu-id="57ac2-190">Eine Drillthroughaktion wird durch eine Rowsetaktion definiert, die als Drillthroughanweisung an die Clientanwendung zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="57ac2-190">A drillthrough action is defined by a rowset action, which is returned to the client application as a drillthrough statement.</span></span> <span data-ttu-id="57ac2-191">Das Aktionsziel ist ein Mitglied einer Measuregruppe.</span><span class="sxs-lookup"><span data-stu-id="57ac2-191">The action target is a member of a measure group.</span></span> <span data-ttu-id="57ac2-192">Klicken Sie zum Erstellen einer neuen Drillthroughaktion im Menü **Cube** auf **Neue Drillthroughaktion**.</span><span class="sxs-lookup"><span data-stu-id="57ac2-192">To create a new drillthrough action, on the **Cube** menu, click **New Drillthrough Action**.</span></span> <span data-ttu-id="57ac2-193">Eine Drillthroughaktion zeichnet sich durch die folgenden spezifischen Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="57ac2-193">The following options are specific to a drillthrough action:</span></span>  
  
 <span data-ttu-id="57ac2-194">**Drillthroughspalten**</span><span class="sxs-lookup"><span data-stu-id="57ac2-194">**Drillthrough Columns**</span></span>  
 <span data-ttu-id="57ac2-195">Wählen Sie eine oder mehrere Dimensionen aus und für jede Dimension die durch die Aktion an die Clientanwendung zurückgegebenen Drillthroughspalten.</span><span class="sxs-lookup"><span data-stu-id="57ac2-195">Select one or more dimensions and, for each dimension, the drillthrough columns returned to the client application by the action.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57ac2-196">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="57ac2-196">See Also</span></span>  
 [<span data-ttu-id="57ac2-197">Cubes in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="57ac2-197">Cubes in Multidimensional Models</span></span>](cubes-in-multidimensional-models.md)  
  
  
