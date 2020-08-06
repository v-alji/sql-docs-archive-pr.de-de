---
title: Erstellen und Ändern von Objekten (XMLA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- objects [XML for Analysis]
- subordinate objects [XML for Analysis]
- XML for Analysis, objects
- modifying objects
- removing objects
- deleting objects
- XMLA, objects
ms.assetid: a2080867-e130-440c-92eb-f768869f34a8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2390c0b921368e7e06f0e5563a7eb59769d99c17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621236"
---
# <a name="creating-and-altering-objects-xmla"></a><span data-ttu-id="62b5b-102">Erstellen und Ändern von Objekten (XMLA)</span><span class="sxs-lookup"><span data-stu-id="62b5b-102">Creating and Altering Objects (XMLA)</span></span>
  <span data-ttu-id="62b5b-103">Hauptobjekte können unabhängig erstellt, geändert und gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="62b5b-103">Major objects can be independently created, altered, and deleted.</span></span> <span data-ttu-id="62b5b-104">Zu den Hauptobjekten gehören die folgenden Objekte:</span><span class="sxs-lookup"><span data-stu-id="62b5b-104">Major objects include the following objects:</span></span>  
  
-   <span data-ttu-id="62b5b-105">Server</span><span class="sxs-lookup"><span data-stu-id="62b5b-105">Servers</span></span>  
  
-   <span data-ttu-id="62b5b-106">Datenbanken</span><span class="sxs-lookup"><span data-stu-id="62b5b-106">Databases</span></span>  
  
-   <span data-ttu-id="62b5b-107">Dimensionen</span><span class="sxs-lookup"><span data-stu-id="62b5b-107">Dimensions</span></span>  
  
-   <span data-ttu-id="62b5b-108">Cubes</span><span class="sxs-lookup"><span data-stu-id="62b5b-108">Cubes</span></span>  
  
-   <span data-ttu-id="62b5b-109">Measuregruppen</span><span class="sxs-lookup"><span data-stu-id="62b5b-109">Measure groups</span></span>  
  
-   <span data-ttu-id="62b5b-110">Partitionen</span><span class="sxs-lookup"><span data-stu-id="62b5b-110">Partitions</span></span>  
  
-   <span data-ttu-id="62b5b-111">Perspektiven</span><span class="sxs-lookup"><span data-stu-id="62b5b-111">Perspectives</span></span>  
  
-   <span data-ttu-id="62b5b-112">Miningmodelle</span><span class="sxs-lookup"><span data-stu-id="62b5b-112">Mining models</span></span>  
  
-   <span data-ttu-id="62b5b-113">Rollen</span><span class="sxs-lookup"><span data-stu-id="62b5b-113">Roles</span></span>  
  
-   <span data-ttu-id="62b5b-114">Einem Server oder einer Datenbank zugeordnete Befehle</span><span class="sxs-lookup"><span data-stu-id="62b5b-114">Commands associated with a server or database</span></span>  
  
-   <span data-ttu-id="62b5b-115">Datenquellen</span><span class="sxs-lookup"><span data-stu-id="62b5b-115">Data sources</span></span>  
  
 <span data-ttu-id="62b5b-116">Verwenden Sie den [Create](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla) -Befehl, um ein Hauptobjekt für eine Instanz von zu erstellen [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , und den [Alter](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla) -Befehl, um ein vorhandenes Hauptobjekt in einer-Instanz zu ändern.</span><span class="sxs-lookup"><span data-stu-id="62b5b-116">You use the [Create](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla) command to create a major object on an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], and the [Alter](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla) command to alter an existing major object on an instance.</span></span> <span data-ttu-id="62b5b-117">Beide Befehle werden mit der [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) -Methode ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="62b5b-117">Both commands are run using the [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) method.</span></span>  
  
## <a name="creating-objects"></a><span data-ttu-id="62b5b-118">Erstellen von Objekten</span><span class="sxs-lookup"><span data-stu-id="62b5b-118">Creating Objects</span></span>  
 <span data-ttu-id="62b5b-119">Wenn Sie Objekte über die `Create`-Methode erstellen, müssen Sie zunächst das übergeordnete Objekt identifizieren, das das zu erstellende [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="62b5b-119">When you create objects by using the `Create` method, you must first identify the parent object that contains the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] object to be created.</span></span> <span data-ttu-id="62b5b-120">Sie identifizieren das übergeordnete Objekt, indem Sie einen Objekt Verweis in der Eigenschaft " [parametriobject](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) " des `Create` Befehls angeben.</span><span class="sxs-lookup"><span data-stu-id="62b5b-120">You identify the parent object by providing an object reference in the [ParentObject](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) property of the `Create` command.</span></span> <span data-ttu-id="62b5b-121">Jeder Objektverweis enthält die Objektbezeichner, die notwendig sind, um das übergeordnete Objekt für den `Create`-Befehl zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="62b5b-121">Each object reference contains the object identifiers needed to uniquely identify the parent object for the `Create` command.</span></span> <span data-ttu-id="62b5b-122">Weitere Informationen zu Objekt verweisen finden Sie unter [definieren und Identifizieren von Objekten &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects).</span><span class="sxs-lookup"><span data-stu-id="62b5b-122">For more information about object references, see [Defining and Identifying Objects &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects).</span></span>  
  
 <span data-ttu-id="62b5b-123">Beispielsweise müssen Sie einen Objektverweis auf einen Cube bereitstellen, um eine neue Measuregruppe für den Cube zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="62b5b-123">For example, you must provide an object reference to a cube to create a new measure group for the cube.</span></span> <span data-ttu-id="62b5b-124">Der Objektverweis für den Cube in der Eigenschaft `ParentObject` enthält sowohl einen Datenbankbezeichner als auch einen Cubebezeichner, da der gleiche Cubebezeichner potenziell von einer anderen Datenbank verwendet werden könnte.</span><span class="sxs-lookup"><span data-stu-id="62b5b-124">The object reference for the cube in the `ParentObject` property contains both a database identifier and a cube identifier, as the same cube identifier could potentially be used on a different database.</span></span>  
  
 <span data-ttu-id="62b5b-125">Das [ObjectDefinition](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/objectdefinition-element-xmla) -Element enthält ASSL-Elemente (Analysis Services Scripting Language), die das zu erstellende Hauptobjekt definieren.</span><span class="sxs-lookup"><span data-stu-id="62b5b-125">The [ObjectDefinition](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/objectdefinition-element-xmla) element contains Analysis Services Scripting Language (ASSL) elements that define the major object to be created.</span></span> <span data-ttu-id="62b5b-126">Weitere Informationen zu ASSL finden Sie unter [entwickeln mit Analysis Services Skriptsprache &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span><span class="sxs-lookup"><span data-stu-id="62b5b-126">For more information about ASSL, see [Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span></span>  
  
 <span data-ttu-id="62b5b-127">Wenn Sie das `AllowOverwrite`-Attribut des `Create`-Befehls auf True setzen, können Sie ein vorhandenes Hauptobjekt mit dem gleichen Bezeichner überschreiben.</span><span class="sxs-lookup"><span data-stu-id="62b5b-127">If you set the `AllowOverwrite` attribute of the `Create` command to true, you can overwrite an existing major object that has the specified identifier.</span></span> <span data-ttu-id="62b5b-128">Andernfalls tritt ein Fehler auf, wenn im übergeordneten Objekt bereits ein Hauptobjekt mit dem gleichen Bezeichner vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="62b5b-128">Otherwise, an error occurs if a major object that has the specified identifier already exists in the parent object.</span></span>  
  
 <span data-ttu-id="62b5b-129">Weitere Informationen zum- `Create` Befehl finden Sie unter [Create Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla).</span><span class="sxs-lookup"><span data-stu-id="62b5b-129">For more information about the `Create` command, see [Create Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla).</span></span>  
  
### <a name="creating-session-objects"></a><span data-ttu-id="62b5b-130">Erstellen von Sitzungsobjekten</span><span class="sxs-lookup"><span data-stu-id="62b5b-130">Creating Session Objects</span></span>  
 <span data-ttu-id="62b5b-131">Sitzungsobjekte sind temporäre Objekte, die nur für die explizite oder implizierte Sitzung zur Verfügung stehen, die von einer Clientanwendung verwendet werden. Bei Beendigung der Sitzung werden diese gelöscht.</span><span class="sxs-lookup"><span data-stu-id="62b5b-131">Session objects are temporary objects that are available only to the explicit or implicit session used by a client application and are deleted when the session is ended.</span></span> <span data-ttu-id="62b5b-132">Sie können Sitzungs Objekte erstellen, indem Sie das- `Scope` Attribut des- `Create` Befehls auf *Session*festlegen.</span><span class="sxs-lookup"><span data-stu-id="62b5b-132">You can create session objects by setting the `Scope` attribute of the `Create` command to *Session*.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="62b5b-133">Wenn Sie die *Sitzungs* Einstellung verwenden, `ObjectDefinition` kann das-Element nur [Dimensions](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl)-, [Cube](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl)-oder [Mining Model](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) -ASSL-Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="62b5b-133">When using the *Session* setting, the `ObjectDefinition` element can only contain [Dimension](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl), [Cube](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl), or [MiningModel](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) ASSL elements.</span></span>  
  
## <a name="altering-objects"></a><span data-ttu-id="62b5b-134">Ändern von Objekten</span><span class="sxs-lookup"><span data-stu-id="62b5b-134">Altering Objects</span></span>  
 <span data-ttu-id="62b5b-135">Wenn Sie Objekte mithilfe der- `Alter` Methode ändern, müssen Sie zuerst das zu ändernde Objekt identifizieren, indem Sie einen Objekt Verweis in der [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) -Eigenschaft des- `Alter` Befehls angeben.</span><span class="sxs-lookup"><span data-stu-id="62b5b-135">When modifying objects by using the `Alter` method, you must first identify the object to be modified by providing an object reference in the [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) property of the `Alter` command.</span></span> <span data-ttu-id="62b5b-136">Jeder Objektverweis enthält die Objektbezeichner, die notwendig sind, um das Objekt für den `Alter`-Befehl zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="62b5b-136">Each object reference contains the object identifiers needed to uniquely identify the object for the `Alter` command.</span></span> <span data-ttu-id="62b5b-137">Weitere Informationen zu Objekt verweisen finden Sie unter [definieren und Identifizieren von Objekten &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects).</span><span class="sxs-lookup"><span data-stu-id="62b5b-137">For more information about object references, see [Defining and Identifying Objects &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects).</span></span>  
  
 <span data-ttu-id="62b5b-138">Beispielsweise müssen Sie einen Objektverweis auf einen Cube bereitstellen, um die Struktur eines Cubes zu ändern.</span><span class="sxs-lookup"><span data-stu-id="62b5b-138">For example, you must provide an object reference to a cube in order to modify the structure of a cube.</span></span> <span data-ttu-id="62b5b-139">Der Objektverweis für den Cube in der Eigenschaft `Object` enthält sowohl einen Datenbankbezeichner als auch einen Cubebezeichner, da der gleiche Cubebezeichner potenziell von einer anderen Datenbank verwendet werden könnte.</span><span class="sxs-lookup"><span data-stu-id="62b5b-139">The object reference for the cube in the `Object` property contains both a database identifier and a cube identifier, as the same cube identifier could potentially be used on a different database.</span></span>  
  
 <span data-ttu-id="62b5b-140">Das `ObjectDefinition`-Element enthält ASSL-Elemente, die das Hauptobjekt definieren, das geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="62b5b-140">The `ObjectDefinition` element contains ASSL elements that define the major object to be modified.</span></span> <span data-ttu-id="62b5b-141">Weitere Informationen zu ASSL finden Sie unter [entwickeln mit Analysis Services Skriptsprache &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span><span class="sxs-lookup"><span data-stu-id="62b5b-141">For more information about ASSL, see [Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span></span>  
  
 <span data-ttu-id="62b5b-142">Wenn Sie das `AllowCreate`-Attribut des `Alter`-Befehls auf True setzen, können Sie das angegebene Hauptobjekt erstellen, wenn das Objekt nicht existiert.</span><span class="sxs-lookup"><span data-stu-id="62b5b-142">If you set the `AllowCreate` attribute of the `Alter` command to true, you can create the specified major object if the object does not exist.</span></span> <span data-ttu-id="62b5b-143">Andernfalls tritt ein Fehler auf, wenn ein angegebenes Hauptobjekt nicht bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="62b5b-143">Otherwise, an error occurs if a specified major object does not already exist.</span></span>  
  
### <a name="using-the-objectexpansion-attribute"></a><span data-ttu-id="62b5b-144">Verwenden des ObjectExpansion-Attributs</span><span class="sxs-lookup"><span data-stu-id="62b5b-144">Using the ObjectExpansion Attribute</span></span>  
 <span data-ttu-id="62b5b-145">Wenn Sie nur die Eigenschaften des Haupt Objekts ändern und keine Hilfsobjekte neu definieren, die im Hauptobjekt enthalten sind, können Sie das- `ObjectExpansion` Attribut des- `Alter` Befehls auf *ObjectProperties*festlegen.</span><span class="sxs-lookup"><span data-stu-id="62b5b-145">If you are changing only the properties of the major object and are not redefining minor objects that are contained by the major object, you can set the `ObjectExpansion` attribute of the `Alter` command to *ObjectProperties*.</span></span> <span data-ttu-id="62b5b-146">Die `ObjectDefinition`-Eigenschaft muss dann nur die Elemente für die Eigenschaften des Hauptobjekts enthalten, und der `Alter`-Befehl lässt die zum Hauptobjekt gehörenden Nebenobjekte unverändert.</span><span class="sxs-lookup"><span data-stu-id="62b5b-146">The `ObjectDefinition` property then only has to contain the elements for the properties of the major object, and the `Alter` command leaves minor objects associated with the major object untouched.</span></span>  
  
 <span data-ttu-id="62b5b-147">Zum Neudefinieren von neben Objekten für ein Hauptobjekt müssen Sie das `ObjectExpansion` -Attribut auf *ExpandFull* festlegen, und die Objektdefinition muss alle neben Objekte enthalten, die im Hauptobjekt enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="62b5b-147">To redefine minor objects for a major object, you must set the `ObjectExpansion` attribute to *ExpandFull* and the object definition must include all minor objects that are contained by the major object.</span></span> <span data-ttu-id="62b5b-148">Wenn die `ObjectDefinition`-Eigenschaft des `Alter`-Befehls nicht explizit ein im Hauptobjekt enthaltenes Nebenobjekt einbindet, wird das nicht eingebundene Nebenobjekt gelöscht.</span><span class="sxs-lookup"><span data-stu-id="62b5b-148">If the `ObjectDefinition` property of the `Alter` command does not explicitly include a minor object that is contained by the major object, the minor object that was not included is deleted.</span></span>  
  
### <a name="altering-session-objects"></a><span data-ttu-id="62b5b-149">Ändern von Sitzungsobjekten</span><span class="sxs-lookup"><span data-stu-id="62b5b-149">Altering Session Objects</span></span>  
 <span data-ttu-id="62b5b-150">Um die vom Befehl erstellten Sitzungs Objekte zu ändern `Create` , legen `Scope` Sie das-Attribut des- `Alter` Befehls auf *Session*fest.</span><span class="sxs-lookup"><span data-stu-id="62b5b-150">To modify session objects created by the `Create` command, set the `Scope` attribute of the `Alter` command to *Session*.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="62b5b-151">Wenn Sie die *Sitzungs* Einstellung verwenden, `ObjectDefinition` kann das-Element nur [Dimensions](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl)-, [Cube](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl)-oder [Mining Model](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) -ASSL-Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="62b5b-151">When using the *Session* setting, the `ObjectDefinition` element can only contain [Dimension](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl), [Cube](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl), or [MiningModel](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) ASSL elements.</span></span>  
  
## <a name="creating-or-altering-subordinate-objects"></a><span data-ttu-id="62b5b-152">Erstellen oder Ändern von untergeordneten Objekten</span><span class="sxs-lookup"><span data-stu-id="62b5b-152">Creating or Altering Subordinate Objects</span></span>  
 <span data-ttu-id="62b5b-153">Obwohl ein `Create`- oder  `Alter`-Befehl nur das oberste Hauptobjekt erstellt oder ändert, kann das Hauptobjekt, das erstellt oder geändert wird, Definitionen innerhalb der einschließenden `ObjectDefinition`-Eigenschaft für andere Haupt- und Nebenobjekte enthalten, die ihm untergeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="62b5b-153">Although a `Create` or `Alter` command creates or alters only one topmost major object, the major object being created or modified can contain definitions within the enclosing `ObjectDefinition` property for other major and minor objects that are subordinate to it.</span></span> <span data-ttu-id="62b5b-154">Beispielsweise geben Sie bei der Definition eines Cubes die übergeordnete Datenbank in `ParentObject` an, und innerhalb der Cubedefinition in `ObjectDefinition` können Sie Measuregruppen für den Cube erstellen, und innerhalb der Measuregruppen können Sie Partitionen für jede Measuregruppe definieren.</span><span class="sxs-lookup"><span data-stu-id="62b5b-154">For example, if you define a cube, you specify the parent database in `ParentObject`, and within the cube definition in `ObjectDefinition` you can define measure groups for the cube, and within the measure groups you can define partitions for each measure group.</span></span> <span data-ttu-id="62b5b-155">Ein Nebenobjekt kann nur unter dem Hauptobjekt definiert werden, das es enthält.</span><span class="sxs-lookup"><span data-stu-id="62b5b-155">A minor object can be defined only under the major object that contains it.</span></span> <span data-ttu-id="62b5b-156">Weitere Informationen zu Haupt-und neben Objekten finden Sie unter [Datenbankobjekte &#40;Analysis Services-Mehrdimensionale Daten&#41;](../multidimensional-models/olap-logical/database-objects-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="62b5b-156">For more information about major and minor objects, see [Database Objects &#40;Analysis Services - Multidimensional Data&#41;](../multidimensional-models/olap-logical/database-objects-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="62b5b-157">Beispiele</span><span class="sxs-lookup"><span data-stu-id="62b5b-157">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="62b5b-158">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="62b5b-158">Description</span></span>  
 <span data-ttu-id="62b5b-159">Im folgenden Beispiel wird eine relationale Datenquelle erstellt, die auf die- [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] Beispiel [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Datenbank verweist.</span><span class="sxs-lookup"><span data-stu-id="62b5b-159">The following example creates a relational data source that references the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] sample [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
### <a name="code"></a><span data-ttu-id="62b5b-160">Code</span><span class="sxs-lookup"><span data-stu-id="62b5b-160">Code</span></span>  
  
```  
<Create xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <ParentObject>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
    </ParentObject>  
    <ObjectDefinition>  
        <DataSource xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RelationalDataSource">  
            <ID>AdventureWorksDW2012</ID>  
            <Name>AdventureWorksDW2012</Name>  
            <ConnectionString>Data Source=localhost;Initial Catalog=AdventureWorksDW2008R2;Integrated Security=True</ConnectionString>  
            <ImpersonationInfo>  
                <ImpersonationMode>ImpersonateServiceAccount</ImpersonationMode>  
            </ImpersonationInfo>  
            <ManagedProvider>System.Data.SqlClient</ManagedProvider>  
            <Timeout>PT0S</Timeout>  
        </DataSource>  
    </ObjectDefinition>  
</Create>  
```  
  
### <a name="description"></a><span data-ttu-id="62b5b-161">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="62b5b-161">Description</span></span>  
 <span data-ttu-id="62b5b-162">Im folgenden Beispiel wird die im vorherigen Beispiel erzeugte relationale Datenquelle so geändert, dass der Abfragetimeout der Datenquelle nach 30 Sekunden einsetzt.</span><span class="sxs-lookup"><span data-stu-id="62b5b-162">The following example alters the relational data source created in the previous example to set the query time-out for the data source to 30 seconds.</span></span>  
  
### <a name="code"></a><span data-ttu-id="62b5b-163">Code</span><span class="sxs-lookup"><span data-stu-id="62b5b-163">Code</span></span>  
  
```  
<Alter ObjectExpansion="ObjectProperties" xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <DataSourceID>AdventureWorksDW2012</DataSourceID>  
    </Object>  
    <ObjectDefinition>  
        <DataSource xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RelationalDataSource">  
            <ID>AdventureWorksDW2012</ID>  
            <Name>AdventureWorksDW2012</Name>  
            <ConnectionString>Data Source=fr-dwk-02;Initial Catalog=AdventureWorksDW2008R2;Integrated Security=True</ConnectionString>  
            <ManagedProvider>System.Data.SqlClient</ManagedProvider>  
            <Timeout>PT30S</Timeout>  
        </DataSource>  
    </ObjectDefinition>  
</Alter>  
```  
  
### <a name="comments"></a><span data-ttu-id="62b5b-164">Kommentare</span><span class="sxs-lookup"><span data-stu-id="62b5b-164">Comments</span></span>  
 <span data-ttu-id="62b5b-165">Das- `ObjectExpansion` Attribut des- `Alter` Befehls wurde auf *ObjectProperties*festgelegt.</span><span class="sxs-lookup"><span data-stu-id="62b5b-165">The `ObjectExpansion` attribute of the `Alter` command was set to *ObjectProperties*.</span></span> <span data-ttu-id="62b5b-166">Diese Einstellung ermöglicht es, dass das Element "Identitätswechsel [Informationen](https://docs.microsoft.com/bi-reference/assl/properties/impersonationinfo-element-assl) " (ein neben Objekt) aus der in definierten Datenquelle ausgeschlossen wird `ObjectDefinition` .</span><span class="sxs-lookup"><span data-stu-id="62b5b-166">This setting allows the [ImpersonationInfo](https://docs.microsoft.com/bi-reference/assl/properties/impersonationinfo-element-assl) element, a minor object, to be excluded from the data source defined in `ObjectDefinition`.</span></span> <span data-ttu-id="62b5b-167">Daher bleiben die Informationen zum Identitätswechsel für die Datenquelle auf "Service Account" festgelegt, wie es im ersten Beispiel angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="62b5b-167">Therefore, the impersonation information for that data source remains set to the service account, as specified in the first example.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62b5b-168">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="62b5b-168">See Also</span></span>  
 <span data-ttu-id="62b5b-169">[Execute-Methode &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) </span><span class="sxs-lookup"><span data-stu-id="62b5b-169">[Execute Method &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) </span></span>  
 <span data-ttu-id="62b5b-170">[Entwickeln mit Analysis Services Skriptsprache &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md) </span><span class="sxs-lookup"><span data-stu-id="62b5b-170">[Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md) </span></span>  
 [<span data-ttu-id="62b5b-171">Entwickeln mit XMLA in Analysis Services</span><span class="sxs-lookup"><span data-stu-id="62b5b-171">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
