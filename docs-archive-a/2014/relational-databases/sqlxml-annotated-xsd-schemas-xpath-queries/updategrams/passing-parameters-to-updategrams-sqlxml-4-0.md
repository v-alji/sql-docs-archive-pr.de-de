---
title: Übergeben von Parametern an Updategrams (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- nullvalue attribute
- passing parameters [SQLXML]
- parameters [SQLXML]
- updategrams [SQLXML], passing parameters
- null values [SQLXML]
ms.assetid: 2354e6e7-1860-471f-8711-4e374c5a4ed2
author: rothja
ms.author: jroth
ms.openlocfilehash: 4bc29de2dab3d0bc3587cb21b7005c0c23dcf7c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619740"
---
# <a name="passing-parameters-to-updategrams-sqlxml-40"></a><span data-ttu-id="a1cdc-102">Übergeben von Parametern an Updategrams (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="a1cdc-102">Passing Parameters to Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="a1cdc-103">Updategrams sind Vorlagen. Daher können Sie ihnen Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="a1cdc-103">Updategrams are templates; therefore, you can pass them parameters.</span></span> <span data-ttu-id="a1cdc-104">Weitere Informationen zum Übergeben von Parametern an Vorlagen finden Sie unter [Updategram Security Überlegungen &#40;SQLXML 4,0&#41;](../security/updategram-security-considerations-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="a1cdc-104">For more information about passing parameters to templates, see [Updategram Security Considerations &#40;SQLXML 4.0&#41;](../security/updategram-security-considerations-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="a1cdc-105">Mit Updategrams können Sie NULL als Parameterwert übergeben.</span><span class="sxs-lookup"><span data-stu-id="a1cdc-105">Updategrams allow you to pass NULL as a parameter value.</span></span> <span data-ttu-id="a1cdc-106">Um den NULL-Parameterwert zu übergeben, geben Sie das `nullvalue`-Attribut an.</span><span class="sxs-lookup"><span data-stu-id="a1cdc-106">To pass the NULL parameter value, you specify the `nullvalue` attribute.</span></span> <span data-ttu-id="a1cdc-107">Der Wert, der dem `nullvalue`-Attribut zugewiesen wird, wird dann als Parameterwert zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="a1cdc-107">The value that is assigned to the `nullvalue` attribute is then provided as the parameter value.</span></span> <span data-ttu-id="a1cdc-108">Updategrams behandeln diesen Wert als NULL.</span><span class="sxs-lookup"><span data-stu-id="a1cdc-108">Updategrams treat this value as NULL.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a1cdc-109">In `<sql:header>` und `<updg:header>` geben Sie den `nullvalue`-Wert als nicht qualifiziert an, während Sie den `<updg:sync>`-Wert in `nullvalue` als qualifiziert angeben (z. B. `updg:nullvalue`).</span><span class="sxs-lookup"><span data-stu-id="a1cdc-109">In `<sql:header>` and `<updg:header>`, you should specify the `nullvalue` as unqualified; whereas, in `<updg:sync>`, you specify the `nullvalue` as qualified (for example, `updg:nullvalue`).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="a1cdc-110">Beispiele</span><span class="sxs-lookup"><span data-stu-id="a1cdc-110">Examples</span></span>  
 <span data-ttu-id="a1cdc-111">Wenn Sie in den folgenden Beispielen funktionierende Beispiele erstellen möchten, müssen Sie die unter [Anforderungen zum Ausführen von SQLXML-Beispielen](../../sqlxml/requirements-for-running-sqlxml-examples.md)angegebenen Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a1cdc-111">To create working samples using the following examples, you must meet the requirements specified in [Requirements for Running SQLXML Examples](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
 <span data-ttu-id="a1cdc-112">Beachten Sie vor der Verwendung der Update Gram-Beispiele Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a1cdc-112">Before using the updategram examples, note the following:</span></span>  
  
-   <span data-ttu-id="a1cdc-113">Die Beispiele verwenden die Standardzuordnung (d. h. es ist kein Zuordnungsschema im Updategram angegeben).</span><span class="sxs-lookup"><span data-stu-id="a1cdc-113">The examples use default mapping (that is, no mapping schema is specified in the updategram).</span></span> <span data-ttu-id="a1cdc-114">Weitere Beispiele für Update grams, die Mapping-Schemas verwenden, finden Sie unter [Angeben eines Mappingschemas mit Anmerkungen in einem Update Gram &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="a1cdc-114">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
### <a name="a-passing-parameters-to-an-updategram"></a><span data-ttu-id="a1cdc-115">A.</span><span class="sxs-lookup"><span data-stu-id="a1cdc-115">A.</span></span> <span data-ttu-id="a1cdc-116">Übergeben von Parametern an ein Updategram</span><span class="sxs-lookup"><span data-stu-id="a1cdc-116">Passing parameters to an updategram</span></span>  
 <span data-ttu-id="a1cdc-117">In diesem Beispiel ändert das Updategram den Nachnamen eines Angestellten in der HumanResources.Shift-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a1cdc-117">In this example, the updategram changes the last name of an employee in the HumanResources.Shift table.</span></span> <span data-ttu-id="a1cdc-118">An das Updategram werden zwei Parameter übergeben: ShiftID zur eindeutigen Identifizierung der Schicht und Name.</span><span class="sxs-lookup"><span data-stu-id="a1cdc-118">The updategram is passed two parameters: ShiftID, which is used to uniquely identify a shift, and Name.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:header>  
  <updg:param name="ShiftID"/>  
  <updg:param name="Name" />  
</updg:header>  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Shift ShiftID="$ShiftID" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift Name="$Name" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="a1cdc-119">So testen Sie das Updategram</span><span class="sxs-lookup"><span data-stu-id="a1cdc-119">To test the updategram</span></span>  
  
1.  <span data-ttu-id="a1cdc-120">Kopieren Sie das oben angegebene Updategram in Editor, und speichern Sie es als Datei unter UpdategramWithParameters.xml.</span><span class="sxs-lookup"><span data-stu-id="a1cdc-120">Copy the updategram above into Notepad and save it to file as UpdategramWithParameters.xml.</span></span>  
  
2.  <span data-ttu-id="a1cdc-121">Bereiten Sie das SQLXML 4,0-Testskript (Sqlxml4test. vb) [mithilfe von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) zum Ausführen des Update grams vor, indem Sie die folgenden Zeilen nach Hinzufügen `cmd.Properties("Output Stream").Value = outStream` :</span><span class="sxs-lookup"><span data-stu-id="a1cdc-121">Prepare the SQLXML 4.0 test script (Sqlxml4test.vbs) in [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) to execute the updategram by adding the following lines after the `cmd.Properties("Output Stream").Value = outStream`:</span></span>  
  
    ```  
    cmd.NamedParameters = True  
    ' CreateParameter arguments: Name, Type, Direction, Size, Value  
    cmd.Parameters.Append cmd.CreateParameter("@ShiftID",  2, 1,  0, 1)  
    cmd.Parameters.Append cmd.CreateParameter("@Name",   200, 1, 50, "New Name")  
    ```  
  
### <a name="b-passing-null-as-a-parameter-value-to-an-updategram"></a><span data-ttu-id="a1cdc-122">B.</span><span class="sxs-lookup"><span data-stu-id="a1cdc-122">B.</span></span> <span data-ttu-id="a1cdc-123">Übergeben von NULL als Parameterwert an ein Updategram</span><span class="sxs-lookup"><span data-stu-id="a1cdc-123">Passing NULL as a parameter value to an updategram</span></span>  
 <span data-ttu-id="a1cdc-124">Durch Ausführen eines Updategrams wird der Wert "isnull" dem Parameter zugewiesen, der auf NULL gesetzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a1cdc-124">In executing an updategram, the "isnull" value is assigned to the parameter that you want to set to NULL.</span></span> <span data-ttu-id="a1cdc-125">Das Updategram konvertiert den "isnulll"-Parameterwert in NULL und verarbeitet ihn entsprechend.</span><span class="sxs-lookup"><span data-stu-id="a1cdc-125">Updategram converts the "isnulll" parameter value to NULL and processes it accordingly.</span></span>  
  
 <span data-ttu-id="a1cdc-126">Das folgende Updategram legt einen Mitarbeitertitel auf NULL fest:</span><span class="sxs-lookup"><span data-stu-id="a1cdc-126">The following updategram sets an employee title to NULL:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:header nullvalue="isnull" >  
  <updg:param name="EmployeeID"/>  
  <updg:param name="ManagerID" />  
</updg:header>  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Employee EmployeeID="$EmployeeID" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Employee ManagerID="$ManagerID" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="a1cdc-127">So testen Sie das Updategram</span><span class="sxs-lookup"><span data-stu-id="a1cdc-127">To test the updategram</span></span>  
  
1.  <span data-ttu-id="a1cdc-128">Kopieren Sie das oben angegebene Updategram in Editor, und speichern Sie es als Datei unter UpdategramPassingNullvalues.xml.</span><span class="sxs-lookup"><span data-stu-id="a1cdc-128">Copy the updategram above into Notepad and save it to file as UpdategramPassingNullvalues.xml.</span></span>  
  
2.  <span data-ttu-id="a1cdc-129">Bereiten Sie das SQLXML 4,0-Testskript (Sqlxml4test. vb) [mithilfe von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) zum Ausführen des Update grams vor, indem Sie die folgenden Zeilen nach Hinzufügen `cmd.Properties("Output Stream").Value = outStream` :</span><span class="sxs-lookup"><span data-stu-id="a1cdc-129">Prepare the SQLXML 4.0 test script (Sqlxml4test.vbs) in [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) to execute the updategram by adding the following lines after the `cmd.Properties("Output Stream").Value = outStream`:</span></span>  
  
    ```  
    cmd.NamedParameters = True  
    ' CreateParameter arguments: Name, Type, Direction, Size, Value   
    cmd.Parameters.Append cmd.CreateParameter("@EmployeeID", 3, 1, 0, 1)  
    cmd.Parameters.Append cmd.CreateParameter("@ManagerID",  3, 1, 0, Null)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a1cdc-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a1cdc-130">See Also</span></span>  
 [<span data-ttu-id="a1cdc-131">Sicherheitsüberlegungen zu Update grams &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="a1cdc-131">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
