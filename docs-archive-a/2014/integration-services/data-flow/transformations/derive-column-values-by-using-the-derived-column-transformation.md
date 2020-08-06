---
title: Ableiten von Spaltenwerten mithilfe der Transformation für abgeleitete Spalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- columns [Integration Services]
- derived columns
- columns [Integration Services], values
- Derived Column transformation
ms.assetid: 28b07746-fc6f-42b2-b741-9de6fac3f29c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 837ec552144697b40cf649bc0403edfe4dc57a57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608769"
---
# <a name="derive-column-values-by-using-the-derived-column-transformation"></a><span data-ttu-id="37c5a-102">Ableiten von Spaltenwerten mithilfe der Transformation für abgeleitete Spalten</span><span class="sxs-lookup"><span data-stu-id="37c5a-102">Derive Column Values by Using the Derived Column Transformation</span></span>
  <span data-ttu-id="37c5a-103">Das Paket muss bereits mindestens einen Datenflusstask und eine Quelle enthalten, damit Sie eine Transformation für abgeleitete Spalten hinzufügen und konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="37c5a-103">To add and configure a Derived Column transformation, the package must already include at least one Data Flow task and one source.</span></span>  
  
 <span data-ttu-id="37c5a-104">Die Transformation für abgeleitete Spalten verwendet Ausdrücke, um vorhandene Werte zu aktualisieren oder Werte neuen Spalten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="37c5a-104">The Derived Column transformation uses expressions to update the values of existing or to add values to new columns.</span></span> <span data-ttu-id="37c5a-105">Wenn Sie das Hinzufügen von neuen Werten zu neuen Spalten auswählen, wird mithilfe des Dialogfelds **Transformations-Editor für abgeleitete Spalte** der Ausdruck ausgewertet, und danach werden die Metadaten der Spalten definiert.</span><span class="sxs-lookup"><span data-stu-id="37c5a-105">When you choose to add values to new columns, the **Derived Column Transformation Editor** dialog box evaluates the expression and defines the metadata of the columns accordingly.</span></span> <span data-ttu-id="37c5a-106">Wenn beispielsweise ein Ausdruck zwei Spalten verkettet, die beide den DT_WSTR-Datentyp sowie eine Länge von 50 aufweisen und sich ein Leerzeichen zwischen den zwei Spaltenwerten befindet, dann weist die neue Spalte den DT_WSTR-Datentyp und eine Länge von 101 auf.</span><span class="sxs-lookup"><span data-stu-id="37c5a-106">For example, if an expression concatenates two columns-each with the DT_WSTR data type and a length of 50-with a space between the two column values, the new column has the DT_WSTR data type and a length of 101.</span></span> <span data-ttu-id="37c5a-107">Sie können den Datentyp neuer Spalten aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="37c5a-107">You can update the data type of new columns.</span></span> <span data-ttu-id="37c5a-108">Als einzige Vorraussetzung muss der Datentyp mit den eingefügten Daten kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="37c5a-108">The only requirement is that data type be compatible with the inserted data.</span></span> <span data-ttu-id="37c5a-109">Wenn beispielsweise das Dialogfeld **Transformations-Editor für abgeleitete Spalte** eine Fehlermeldung generiert, müssen Sie einer Spalte mit einem integer-Datentyp einen Datenwert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="37c5a-109">For example, the **Derived Column Transformation Editor** dialog box generates a validation error when you assign a date value to a column with an integer data type.</span></span> <span data-ttu-id="37c5a-110">Abhängig von dem ausgewählten Datentyp, können Sie die Länge, Genauigkeit, Dezimalstellen und Codepage jeder Spalte angeben.</span><span class="sxs-lookup"><span data-stu-id="37c5a-110">Depending on the data type that you selected, you can specify the length, precision, scale, and code page of the column.</span></span>  
  
### <a name="to-derive-column-values"></a><span data-ttu-id="37c5a-111">So leiten Sie Spaltenwerte ab</span><span class="sxs-lookup"><span data-stu-id="37c5a-111">To derive column values</span></span>  
  
1.  <span data-ttu-id="37c5a-112">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="37c5a-112">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="37c5a-113">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="37c5a-113">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="37c5a-114">Klicken Sie auf die Registerkarte **Datenfluss** , und ziehen Sie dann aus **Toolbox**die Transformation für abgeleitete Spalten auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="37c5a-114">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Derived Column transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="37c5a-115">Verbinden Sie die Transformation für abgeleitete Spalten mit dem Datenfluss, indem Sie den Konnektor von der Quelle oder der vorherigen Transformation auf die Transformation für abgeleitete Spalten ziehen.</span><span class="sxs-lookup"><span data-stu-id="37c5a-115">Connect the Derived Column transformation to the data flow by dragging the connector from the source or the previous transformation to the Derived Column transformation.</span></span>  
  
5.  <span data-ttu-id="37c5a-116">Doppelklicken Sie auf die Transformation für abgeleitete Spalten.</span><span class="sxs-lookup"><span data-stu-id="37c5a-116">Double-click the Derived Column transformation.</span></span>  
  
6.  <span data-ttu-id="37c5a-117">Erstellen Sie in **Transformations-Editor für abgeleitete Spalte** die Ausdrücke, die als Bedingungen verwendet werden sollen, indem Sie Variablen, Spalten, Funktionen und Operatoren in die **Ausdruck** -Spalte im Raster ziehen.</span><span class="sxs-lookup"><span data-stu-id="37c5a-117">In the **Derived Column Transformation Editor** dialog box, build the expressions to use as conditions by dragging variables, columns, functions, and operators to the **Expression** column in the grid.</span></span> <span data-ttu-id="37c5a-118">Sie können den Ausdruck auch in die **Ausdruck** -Spalte eingeben.</span><span class="sxs-lookup"><span data-stu-id="37c5a-118">Alternatively, you can type the expression in the **Expression** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="37c5a-119">Falls der Ausdruck ungültig ist, wird der Ausdruckstext hervorgehoben dargestellt, und die Fehler werden in einer QuickInfo in der Spalte beschrieben.</span><span class="sxs-lookup"><span data-stu-id="37c5a-119">If the expression is not valid, the expression text is highlighted and a ToolTip on the column describes the errors.</span></span>  
  
7.  <span data-ttu-id="37c5a-120">Wählen Sie in der Liste **Abgeleitete Spalte** **\<add as new column>** aus, um das Auswertungsergebnis des Ausdrucks in eine neue Spalte zu schreiben, oder wählen Sie eine vorhandene Spalte aus, um sie mit dem Auswertungsergebnis zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="37c5a-120">In the **Derived Column** list, select **\<add as new column>** to write the evaluation result of the expression to a new column, or select an existing column to update with the evaluation result.</span></span>  
  
     <span data-ttu-id="37c5a-121">Wenn Sie eine neue Spalte auswählen, wird mithilfe des Dialogfelds **Transformations-Editor für abgeleitete Spalte** der Ausdruck ausgewertet und ein Datentyp einer Spalte zugewiesen, abhängig von Datentyp, Länge, Genauigkeit, Dezimalzahlen und Codepage.</span><span class="sxs-lookup"><span data-stu-id="37c5a-121">If you chose to use a new column, the **Derived Column Transformation Editor** dialog box evaluates the expression and assigns a data type to the column, depending on the data type, length, precisions, scale, and code page.</span></span>  
  
8.  <span data-ttu-id="37c5a-122">Falls Sie eine neue Spalte verwenden, wählen Sie in der Liste **Datentyp** einen Datentyp aus.</span><span class="sxs-lookup"><span data-stu-id="37c5a-122">If using a new column, select a data type in the **Data Type** list.</span></span> <span data-ttu-id="37c5a-123">Aktualisieren Sie in Abhängigkeit vom ausgewählten Datentyp die Werte in den Spalten **Länge**, **Genauigkeit**, **Dezimalstellen**und **Codepage** .</span><span class="sxs-lookup"><span data-stu-id="37c5a-123">Depending on the selected data type, optionally update the values in the **Length**, **Precision**, **Scale**, and **Code Page** columns.</span></span> <span data-ttu-id="37c5a-124">Metadaten von vorhandenen Spalten können nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="37c5a-124">Metadata of existing columns cannot be changed.</span></span>  
  
9. <span data-ttu-id="37c5a-125">Optional können Sie die Werte in der **Name der abgeleiteten Spalte** -Spalte ändern.</span><span class="sxs-lookup"><span data-stu-id="37c5a-125">Optionally, modify the values in the **Derived Column Name** column.</span></span>  
  
10. <span data-ttu-id="37c5a-126">Um die Fehlerausgabe zu konfigurieren, klicken Sie auf **Fehlerausgabe konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="37c5a-126">To configure the error output, click **Configure Error Output**.</span></span> <span data-ttu-id="37c5a-127">Weitere Informationen finden Sie unter [Konfigurieren einer Fehlerausgabe in einer Datenflusskomponente](../../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="37c5a-127">For more information, see [Configure an Error Output in a Data Flow Component](../../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
11. <span data-ttu-id="37c5a-128">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="37c5a-128">Click **OK**.</span></span>  
  
12. <span data-ttu-id="37c5a-129">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="37c5a-129">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37c5a-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="37c5a-130">See Also</span></span>  
 <span data-ttu-id="37c5a-131">[Derived Column Transformation](derived-column-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="37c5a-131">[Derived Column Transformation](derived-column-transformation.md) </span></span>  
 <span data-ttu-id="37c5a-132">[SQL Server Integration Services-Datentypen](../integration-services-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="37c5a-132">[Integration Services Data Types](../integration-services-data-types.md) </span></span>  
 <span data-ttu-id="37c5a-133">[SQL Server Integration Services-Transformationen](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="37c5a-133">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="37c5a-134">[SQL Server Integration Services-Pfade](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="37c5a-134">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 <span data-ttu-id="37c5a-135">[Datenflusstask](../../control-flow/data-flow-task.md) </span><span class="sxs-lookup"><span data-stu-id="37c5a-135">[Data Flow Task](../../control-flow/data-flow-task.md) </span></span>  
 [<span data-ttu-id="37c5a-136">Integration Services-Ausdrücke &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="37c5a-136">Integration Services &#40;SSIS&#41; Expressions</span></span>](../../expressions/integration-services-ssis-expressions.md)  
  
  
