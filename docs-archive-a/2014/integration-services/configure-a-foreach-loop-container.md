---
title: Konfigurieren eines Foreach-Schleifen Containers | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Foreach Loop containers
- containers [Integration Services], Foreach Loop
ms.assetid: 519c6f96-5e1f-47d2-b96a-d49946948c25
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 85fb399f51e22e091fac9b1d8d332b9a12e7d77e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609370"
---
# <a name="configure-a-foreach-loop-container"></a><span data-ttu-id="5ff40-102">Konfigurieren eines Foreach-Schleifencontainers</span><span class="sxs-lookup"><span data-stu-id="5ff40-102">Configure a Foreach Loop Container</span></span>
  <span data-ttu-id="5ff40-103">In diesem Verfahren wird das Konfigurieren eines Foreach-Schleifencontainers beschrieben, einschließlich der Eigenschaftsausdrücke auf Enumerator- und Containerebene.</span><span class="sxs-lookup"><span data-stu-id="5ff40-103">This procedure describes how to configure a Foreach Loop container, including property expressions at the enumerator and container levels.</span></span>  
  
### <a name="to-configure-the-foreach-loop-container"></a><span data-ttu-id="5ff40-104">So konfigurieren Sie den Foreach-Schleifencontainer</span><span class="sxs-lookup"><span data-stu-id="5ff40-104">To configure the Foreach Loop container</span></span>  
  
1.  <span data-ttu-id="5ff40-105">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="5ff40-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="5ff40-106">Klicken Sie auf die Registerkarte **Ablaufsteuerung**, und doppelklicken Sie auf die Foreach-Schleife.</span><span class="sxs-lookup"><span data-stu-id="5ff40-106">Click the **Control Flow** tab and double-click the Foreach Loop.</span></span>  
  
3.  <span data-ttu-id="5ff40-107">Klicken Sie im Dialogfeld **Foreach-Schleifen-Editor** auf **Allgemein**, und ändern Sie optional den Namen und die Beschreibung der Foreach-Schleife.</span><span class="sxs-lookup"><span data-stu-id="5ff40-107">In the **Foreach Loop Editor** dialog box, click **General** and, optionally, modify the name and description of the Foreach Loop.</span></span>  
  
4.  <span data-ttu-id="5ff40-108">Klicken Sie auf **Sammlung**, und wählen Sie aus der Liste **Enumerator** einen Enumeratortyp aus.</span><span class="sxs-lookup"><span data-stu-id="5ff40-108">Click **Collection** and select an enumerator type from the **Enumerator** list.</span></span>  
  
5.  <span data-ttu-id="5ff40-109">Geben Sie einen Enumerator an, und legen Sie die Enumeratoroptionen wie folgt fest:</span><span class="sxs-lookup"><span data-stu-id="5ff40-109">Specify an enumerator and set enumerator options as follows:</span></span>  
  
    -   <span data-ttu-id="5ff40-110">Wenn Sie den Foreach-Dateienumerator verwenden möchten, stellen Sie den Ordner bereit, der die aufzuzählenden Dateien enthält. Geben Sie einen Filter für den Dateinamen und den Typ an, und geben Sie an, ob der vollqualifizierte Dateiname zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="5ff40-110">To usethe Foreach File enumerator, provide the folder that contains the files to enumerate, specify a filter for the file name and type, and specify whether the fully qualified file name should be returned.</span></span> <span data-ttu-id="5ff40-111">Bestimmen Sie außerdem, ob Unterordner nach weiteren Dateien durchsucht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5ff40-111">Also, indicate whether to recurse through subfolders for more files.</span></span>  
  
    -   <span data-ttu-id="5ff40-112">Wenn Sie den Foreach-Element-Enumerator verwenden möchten, klicken Sie auf **Spalten**, und klicken Sie im Dialogfeld **For Each Item-Spalten** auf **Hinzufügen**, um Spalten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="5ff40-112">To use the Foreach Item enumerator, click **Columns**, and, in the **For Each Item Columns** dialog box, click **Add** to add columns.</span></span> <span data-ttu-id="5ff40-113">Wählen Sie in der Liste **Datentyp** einen Datentyp für jede Spalte aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ff40-113">Select a data type in the **Data Type** list for each column, and click **OK**.</span></span>  
  
         <span data-ttu-id="5ff40-114">Geben Sie Werte in die Spalten ein, oder wählen Sie Werte in Listen aus.</span><span class="sxs-lookup"><span data-stu-id="5ff40-114">Type values in the columns or select values from lists.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="5ff40-115">Klicken Sie an einer beliebigen Stelle außerhalb der Zelle, in die Sie Werte eingegeben haben, um eine neue Zeile hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="5ff40-115">To add a new row, click anywhere outside the cell in which you typed.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="5ff40-116">Falls ein Wert nicht mit dem Spaltendatentyp kompatibel ist, wird der Text hervorgehoben dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5ff40-116">If a value is not compatible with the column data type, the text is highlighted.</span></span>  
  
    -   <span data-ttu-id="5ff40-117">Wenn Sie den Foreach-ADO-Enumerator verwenden möchten, wählen Sie eine vorhandene Variable aus, oder Sie klicken in der Liste **ADO-Objektquellvariable** auf **Neue Variable**, um die Variable anzugeben, die den Namen des aufzuzählenden ADO-Objekts enthält, und wählen dann eine Option für den Enumerationsmodus aus.</span><span class="sxs-lookup"><span data-stu-id="5ff40-117">To use the Foreach ADO enumerator, select an existing variable or click **New variable** in the **ADO object source variable** list to specify the variable that contains the name of the ADO object to enumerate, and select an enumeration mode option.</span></span>  
  
         <span data-ttu-id="5ff40-118">Wenn Sie eine neue Variable erstellen, legen Sie die Variableneigenschaften im Dialogfeld **Variable hinzufügen** fest.</span><span class="sxs-lookup"><span data-stu-id="5ff40-118">If creating a new variable, set the variable properties in the **Add Variable** dialog box.</span></span>  
  
    -   <span data-ttu-id="5ff40-119">Wenn Sie den Enumerator für Foreach-ADO.NET-Schemarowsets verwenden möchten, wählen Sie eine vorhandene ADO.NET-Verbindung aus, oder klicken Sie in der Liste **Verbindung** auf **Neue Verbindung**, und wählen Sie ein Schema aus.</span><span class="sxs-lookup"><span data-stu-id="5ff40-119">To use the Foreach ADO.NET Schema Rowset enumerator, select an existing ADO.NET connection or click **New connection** in the **Connection** list, and then select a schema.</span></span>  
  
         <span data-ttu-id="5ff40-120">Klicken Sie optional auf **Einschränkungen festlegen**, und wählen Sie Schemaeinschränkungen aus, wählen Sie die Variable aus, die den Einschränkungswert enthält, oder geben Sie den Einschränkungswert ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ff40-120">Optionally, click **Set Restrictions** and select schema restrictions, select the variable that contains the restriction value or type the restriction value, and click **OK**.</span></span>  
  
    -   <span data-ttu-id="5ff40-121">Wenn Sie einen Foreach-Enumerator für Daten aus Variablen verwenden möchten, wählen Sie aus der Liste **Variable** eine Variable aus.</span><span class="sxs-lookup"><span data-stu-id="5ff40-121">To use the Foreach From Variable enumerator, select a variable in the **Variable** list.</span></span>  
  
    -   <span data-ttu-id="5ff40-122">Um den Foreach-NodeList-Enumerator zu verwenden, klicken Sie auf „DocumentSourceType“ und wählen den Quelltyp aus der Liste aus. Anschließend klicken Sie auf „DocumentSource“.</span><span class="sxs-lookup"><span data-stu-id="5ff40-122">To use the Foreach NodeList enumerator, click DocumentSourceType and select the source type from the list, and then click DocumentSource.</span></span> <span data-ttu-id="5ff40-123">Je nach dem für „DocumentSourceType“ ausgewählten Wert wählen Sie eine Variable bzw. eine Dateiverbindung aus der Liste aus, erstellen eine neue Variable bzw. Dateiverbindung oder geben die XML-Quelle in den **Dokumentquellen-Editor** ein.</span><span class="sxs-lookup"><span data-stu-id="5ff40-123">Depending on the value selected for DocumentSourceType, select a variable or a file connection from the list, create a new variable or file connection, or type the XML source in the **Document Source Editor**.</span></span>  
  
         <span data-ttu-id="5ff40-124">Klicken Sie anschließend auf „EnumerationType“, und wählen Sie einen Enumerationstyp aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="5ff40-124">Next, click EnumerationType and select an enumeration type from the list.</span></span> <span data-ttu-id="5ff40-125">Wenn „EnumerationType“ den Wert **Navigator, Node oder NodeText** hat, klicken Sie auf „OuterXPathStringSourceType“, wählen den Quelltyp aus und klicken dann auf „OuterXPathString“.</span><span class="sxs-lookup"><span data-stu-id="5ff40-125">If EnumerationType is **Navigator, Node, or NodeText**, click OuterXPathStringSourceType and select the source type, and then click OuterXPathString.</span></span> <span data-ttu-id="5ff40-126">Je nach dem für „OuterXPathStringSourceType“ festgelegten Wert wählen Sie eine Variable bzw. eine Dateiverbindung aus der Liste aus, erstellen eine neue Variable bzw. Dateiverbindung oder geben die Zeichenfolge für den äußeren XPath-Ausdruck (XML Path Language) ein.</span><span class="sxs-lookup"><span data-stu-id="5ff40-126">Depending on the value set for OuterXPathStringSourceType, select a variable or a file connection from the list, create a new variable or file connection, or type the string for the outer XML Path Language (XPath) expression.</span></span>  
  
         <span data-ttu-id="5ff40-127">Wenn EnumerationType den Wert **ElementCollection**hat, legen Sie OuterXPathStringSourceType und OuterXPathString wie oben beschrieben fest.</span><span class="sxs-lookup"><span data-stu-id="5ff40-127">If EnumerationType is **ElementCollection**,set OuterXPathStringSourceType and OuterXPathString as described above.</span></span> <span data-ttu-id="5ff40-128">Klicken Sie anschließend auf „InnerElementType“, und wählen Sie einen Enumerationstyp für die inneren Elemente aus. Klicken Sie dann auf „InnerXPathStringSourceType“.</span><span class="sxs-lookup"><span data-stu-id="5ff40-128">Then, click InnerElementType and select an enumeration type for the inner elements, and then click InnerXPathStringSourceType.</span></span> <span data-ttu-id="5ff40-129">Je nachdem, welchen Wert Sie für „InnerXPathStringSourceType“ festgelegt haben, wählen Sie eine Variable bzw. eine Dateiverbindung aus, erstellen eine neue Variable bzw. Dateiverbindung oder geben die Zeichenfolge für den inneren XPath-Ausdruck ein.</span><span class="sxs-lookup"><span data-stu-id="5ff40-129">Depending on the value set for InnerXPathStringSourceType, select a variable or a file connection, create a new variable or file connection, or type the string for the inner XPath expression.</span></span>  
  
    -   <span data-ttu-id="5ff40-130">Wenn Sie den Foreach-SMO-Enumerator verwenden möchten, wählen Sie eine vorhandene ADO.NET-Verbindung aus oder klicken in der Liste **Verbindung** auf **Neue Verbindung**. Dann geben Sie die zu verwendende Zeichenfolge ein oder klicken auf **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="5ff40-130">To use the Foreach SMO enumerator, select an existing ADO.NET connection or click **New connection** in the **Connection** list, and then either type the string to use or click **Browse**.</span></span> <span data-ttu-id="5ff40-131">**Dadurch** haben Sie im Dialogfeld **SMO-Enumeration auswählen** die Möglichkeit, den aufzuzählenden Objekttyp und den Enumerationstyp auszuwählen. Klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ff40-131">If you click **Browse**, in the **Select SMO Enumeration** dialog box, select the object type to enumerate and the enumeration type, and click **OK**.</span></span>  
  
6.  <span data-ttu-id="5ff40-132">Klicken Sie optional im Textfeld **Ausdrücke** auf der Seite **Sammlung** auf die Schaltfläche mit der Ellipse **(…)** , um Ausdrücke zu erstellen, mit denen Eigenschaftswerte aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="5ff40-132">Optionally, click the browse button **(...)** in the **Expressions** text box on the **Collection** page to create expressions that update property values.</span></span> <span data-ttu-id="5ff40-133">Weitere Informationen finden Sie unter [Hinzufügen oder Ändern eines Eigenschaftsausdrucks](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="5ff40-133">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5ff40-134"> Die in der Liste **Eigenschaft** aufgeführten Eigenschaften hängen vom Enumerator ab.</span><span class="sxs-lookup"><span data-stu-id="5ff40-134">The properties listed in the **Property** list varies by enumerator.</span></span>  
  
7.  <span data-ttu-id="5ff40-135">Klicken Sie optional auf **Variablenzuordnungen** , um Objekteigenschaften dem Auflistungswert zuzuordnen, und führen Sie dann folgende Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="5ff40-135">Optionally, click **Variable Mappings** to map object properties to the collection value, and then do the following:</span></span>  
  
    1.  <span data-ttu-id="5ff40-136">Wählen Sie in der Liste **Variablen** eine Variable aus, oder klicken Sie auf **\<New Variable>** , um eine neue Variable zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5ff40-136">In the **Variables** list, select a variable or click **\<New Variable>** to create a new variable.</span></span>  
  
    2.  <span data-ttu-id="5ff40-137">Wenn Sie eine neue Variable hinzufügen, legen Sie die Variableneigenschaften im Dialogfeld **Variable hinzufügen** fest, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ff40-137">If you add a new variable, set the variable properties in the **Add Variable** dialog box and click **OK**.</span></span>  
  
    3.  <span data-ttu-id="5ff40-138">Wenn Sie den Foreach-Element-Enumerator verwenden, können Sie den Indexwert in der Liste **Index** aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="5ff40-138">If you use the For Each Item enumerator, you can update the index value in the **Index** list.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="5ff40-139">Der Indexwert zeigt an, welche Spalte im Element der Variablen zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5ff40-139">The index value indicates which column in the item to map to the variable.</span></span> <span data-ttu-id="5ff40-140">Nur der Foreach-Element-Enumerator kann einen anderen Indexwert als 0 verwenden.</span><span class="sxs-lookup"><span data-stu-id="5ff40-140">Only the For Each Item enumerator can use an index value other than 0.</span></span>  
  
8.  <span data-ttu-id="5ff40-141">Klicken Sie optional auf **Ausdrücke**, und erstellen Sie auf der Seite **Ausdrücke** Eigenschaftsausdrücke für die Eigenschaften des Foreach-Schleifencontainers.</span><span class="sxs-lookup"><span data-stu-id="5ff40-141">Optionally, click **Expressions** and, on the **Expressions** page, create property expressions for the properties of the Foreach Loop container.</span></span> <span data-ttu-id="5ff40-142">Weitere Informationen finden Sie unter [Hinzufügen oder Ändern eines Eigenschaftsausdrucks](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="5ff40-142">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
9. <span data-ttu-id="5ff40-143">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ff40-143">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ff40-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ff40-144">See Also</span></span>  
 [<span data-ttu-id="5ff40-145">Foreach-Schleifencontainer</span><span class="sxs-lookup"><span data-stu-id="5ff40-145">Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
