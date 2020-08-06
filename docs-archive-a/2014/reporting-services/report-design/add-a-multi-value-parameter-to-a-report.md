---
title: Hinzufügen eines aus mehreren Werten bestehenden Parameters zu einem Bericht | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 12ad0e77-4c28-4bbb-ab11-473ae89ec9f1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5269293b6a21f3b1d82eb6835efbd275e3be9620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696438"
---
# <a name="add-a-multi-value-parameter-to-a-report"></a><span data-ttu-id="33b18-102">Hinzufügen eines aus mehreren Werten bestehenden Parameters zu einem Bericht</span><span class="sxs-lookup"><span data-stu-id="33b18-102">Add a multi-value parameter to a Report</span></span>
  <span data-ttu-id="33b18-103">Sie können einem Bericht einen Parameter hinzufügen, der dem Benutzer die Auswahl mehrerer Werte für den Parameter ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="33b18-103">You can add a parameter to a report that allows the user to select more than one value for the parameter.</span></span>  
  
 <span data-ttu-id="33b18-104">Sie können mehrere Parameterwerte innerhalb der Berichts-URL an den Bericht übergeben.</span><span class="sxs-lookup"><span data-stu-id="33b18-104">You can pass multiple parameter values to the report within the report URL.</span></span> <span data-ttu-id="33b18-105">Ein URL-Beispiel mit einem mehrwertigen Parameter finden Sie unter [Übergeben von Berichtsparametern innerhalb einer URL](../pass-a-report-parameter-within-a-url.md).</span><span class="sxs-lookup"><span data-stu-id="33b18-105">For a URL example includes a multi-value parameter, see [Pass a Report Parameter Within a URL](../pass-a-report-parameter-within-a-url.md).</span></span>  
  
 <span data-ttu-id="33b18-106">Informationen dazu, wie mehrere Parameterwerte an eine gespeicherte Prozedur übergeben werden, finden Sie unter [Verwenden von Mehrfachauswahl-Parametern für SSRS-Berichte](https://go.microsoft.com/fwlink/?LinkId=321529) auf mssqltips.com.</span><span class="sxs-lookup"><span data-stu-id="33b18-106">For information on how to pass multiple parameter values to a stored procedure, see [Working With Multi-Select Parameters for SSRS Reports](https://go.microsoft.com/fwlink/?LinkId=321529) on mssqltips.com.</span></span>  
  
### <a name="to-add-a-multi-value-parameter"></a><span data-ttu-id="33b18-107">So fügen Sie einen aus mehreren Werten bestehenden Parameter hinzu</span><span class="sxs-lookup"><span data-stu-id="33b18-107">To add a multi-value parameter</span></span>  
  
1.  <span data-ttu-id="33b18-108">Öffnen Sie im Berichts-Generator den Bericht, dem Sie den aus mehreren Werten bestehenden Parameter hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="33b18-108">In Report Builder, open the report that you want to add the multi-value parameter to.</span></span>  
  
2.  <span data-ttu-id="33b18-109">Klicken Sie mit der rechten Maustaste auf das Berichtsdataset, und klicken Sie dann auf **Dataseteigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="33b18-109">Right-click the report dataset, and then click **Dataset Properties**</span></span>  
  
3.  <span data-ttu-id="33b18-110">Fügen Sie der Datasetabfrage eine Variable hinzu, indem Sie entweder den Abfragetext im Feld **Abfrage** bearbeiten oder im Abfrage-Designer einen Filter hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="33b18-110">Add a variable to the dataset query by either editing the query text in the **Query** box, or by adding a filter by using the query designer.</span></span> <span data-ttu-id="33b18-111">Weitere Informationen finden Sie unter [Erstellen einer Abfrage im Relationalen Abfrage-Designer (Berichts-Generator und SSRS)](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="33b18-111">For more information, see [Build a Query in the Relational Query Designer &#40;Report Builder and SSRS&#41;](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="33b18-112">Der Abfragetext darf keine DECLARE-Anweisung für die Abfragevariable enthalten.</span><span class="sxs-lookup"><span data-stu-id="33b18-112">The query text must not include the DECLARE statement for the query variable.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="33b18-113">Der Text für die Abfragevariable muss den `IN`-Operator enthalten, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="33b18-113">The text for the query variable must include the `IN` operator, as shown in the following example.</span></span>  
  
    ```  
    WHERE  
      Production.ProductInventory.ProductID IN (@ProductID)  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="33b18-114">Wenn Sie die Variable nicht wie oben dargestellt in Klammern einschließen, wird der Bericht nicht mehr angezeigt, und der Fehler "die Skalarvariable muss deklariert werden" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="33b18-114">If you don't include the parentheses around the variable as shown above, the report fails to render and the "must declare the scalar variable" error is displayed.</span></span>  
  
     <span data-ttu-id="33b18-115">Für die Abfragevariable wird automatisch ein Datasetparameter für ein eingebettetes Dataset oder ein freigegebenes Dataset erstellt.</span><span class="sxs-lookup"><span data-stu-id="33b18-115">A dataset parameter for an embedded dataset or a shared dataset is created automatically for the query variable.</span></span> <span data-ttu-id="33b18-116">Für den Datasetparameter wird automatisch ein Berichtsparameter erstellt.</span><span class="sxs-lookup"><span data-stu-id="33b18-116">A report parameter is created automatically for the dataset parameter.</span></span>  
  
4.  <span data-ttu-id="33b18-117">Erweitern Sie im Bereich **Berichtsdaten** den Knoten **Parameter** , klicken Sie mit der rechten Maustaste auf den Berichtsparameter, der automatisch für den Datasetparameter erstellt wurde, und klicken Sie anschließend auf **Parametereigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="33b18-117">In the **Report Data** pane, expand the **Parameters** node, right-click the report parameter that was automatically created for the dataset parameter, and then click **Parameter Properties**.</span></span>  
  
5.  <span data-ttu-id="33b18-118">Wählen Sie auf der Registerkarte **Allgemein** die Option **Mehrere Werte zulassen** aus, um anzugeben, dass für den Parameter mehr als ein Wert ausgewählt werden darf.</span><span class="sxs-lookup"><span data-stu-id="33b18-118">In the **General** tab, select **Allow multiple values** to allow a user to select more than one value for the parameter.</span></span>  
  
6.  <span data-ttu-id="33b18-119">(Optional) Geben Sie auf der Registerkarte **Verfügbare Werte** eine Liste mit verfügbaren Werten an, die dem Benutzer angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="33b18-119">(Optionally) In the **Available** values tab, specify a list of available values to display to the user.</span></span>  
  
     <span data-ttu-id="33b18-120">Eine Liste verfügbarer Werte schränkt die Auswahl, die ein Benutzer treffen kann, auf die gültigen Werte für den Parameter ein.</span><span class="sxs-lookup"><span data-stu-id="33b18-120">An available values list limits the choices a user can make to only valid values for the parameter.</span></span> <span data-ttu-id="33b18-121">Bei mehreren Werten beginnt die Liste mit der Funktion **Alles auswählen** , sodass der Benutzer alle Werte mit einem einzigen Mausklick auswählen oder löschen kann.</span><span class="sxs-lookup"><span data-stu-id="33b18-121">For multiple values, the top of list begins with a **Select All** feature so the user can select or clear all values with a single click.</span></span> <span data-ttu-id="33b18-122">Wenn Sie die für den Berichtsparameter verfügbaren Werte mit einer Datasetabfrage abrufen möchten, achten Sie darauf, kein Dataset auszuwählen, das die demselben Berichtsparameter zugeordnete Abfragevariable enthält.</span><span class="sxs-lookup"><span data-stu-id="33b18-122">If you choose to get the available values for the report parameter from a dataset query, be sure to select a dataset that does not contain the query variable that is associated with the same report parameter.</span></span>  
  
     <span data-ttu-id="33b18-123">Weitere Informationen finden Sie unter [Hinzufügen, Ändern oder Löschen von verfügbaren Werten für einen Berichtsparameter (Berichts-Generator und SSRS)](add-change-or-delete-available-values-for-a-report-parameter.md).</span><span class="sxs-lookup"><span data-stu-id="33b18-123">For more information, see [Add, Change, or Delete Available Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span></span>  
  
### <a name="to-add-a-multi-value-parameter"></a><span data-ttu-id="33b18-124">So fügen Sie einen aus mehreren Werten bestehenden Parameter hinzu</span><span class="sxs-lookup"><span data-stu-id="33b18-124">To add a multi-value parameter</span></span>  
  
1.  <span data-ttu-id="33b18-125">Öffnen Sie im Berichts-Generator den Bericht, dem Sie den aus mehreren Werten bestehenden Parameter hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="33b18-125">In Report Builder, open the report that you want to add the multi-value parameter to.</span></span>  
  
2.  <span data-ttu-id="33b18-126">Klicken Sie mit der rechten Maustaste auf das Berichtsdataset, und klicken Sie dann auf **Dataseteigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="33b18-126">Right-click the report dataset, and then click **Dataset Properties**</span></span>  
  
3.  <span data-ttu-id="33b18-127">Fügen Sie der Datasetabfrage eine Variable hinzu, indem Sie entweder den Abfragetext im Feld **Abfrage** bearbeiten oder im Abfrage-Designer einen Filter hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="33b18-127">Add a variable to the dataset query by either editing the query text in the **Query** box, or by adding a filter by using the query designer.</span></span> <span data-ttu-id="33b18-128">Weitere Informationen finden Sie unter [Erstellen einer Abfrage im Relationalen Abfrage-Designer (Berichts-Generator und SSRS)](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="33b18-128">For more information, see [Build a Query in the Relational Query Designer &#40;Report Builder and SSRS&#41;](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="33b18-129">Der Abfragetext darf keine DECLARE-Anweisung für die Abfragevariable enthalten.</span><span class="sxs-lookup"><span data-stu-id="33b18-129">The query text must not include the DECLARE statement for the query variable.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="33b18-130">Der Text für die Abfragevariable muss den `IN`-Operator enthalten, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="33b18-130">The text for the query variable must include the `IN` operator, as shown in the following example.</span></span>  
  
    ```  
    WHERE  
      Production.ProductInventory.ProductID IN (@ProductID)  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="33b18-131">Wenn Sie die Variable nicht wie oben dargestellt in Klammern einschließen, wird der Bericht nicht mehr angezeigt, und der Fehler "die Skalarvariable muss deklariert werden" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="33b18-131">If you don't include the parentheses around the variable as shown above, the report fails to render and the "must declare the scalar variable" error is displayed.</span></span>  
  
     <span data-ttu-id="33b18-132">Für die Abfragevariable wird automatisch ein Datasetparameter für ein eingebettetes Dataset oder ein freigegebenes Dataset erstellt.</span><span class="sxs-lookup"><span data-stu-id="33b18-132">A dataset parameter for an embedded dataset or a shared dataset is created automatically for the query variable.</span></span> <span data-ttu-id="33b18-133">Für den Datasetparameter wird automatisch ein Berichtsparameter erstellt.</span><span class="sxs-lookup"><span data-stu-id="33b18-133">A report parameter is created automatically for the dataset parameter.</span></span>  
  
4.  <span data-ttu-id="33b18-134">Erweitern Sie im Bereich **Berichtsdaten** den Knoten **Parameter** , klicken Sie mit der rechten Maustaste auf den Berichtsparameter, der automatisch für den Datasetparameter erstellt wurde, und klicken Sie anschließend auf **Parametereigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="33b18-134">In the **Report Data** pane, expand the **Parameters** node, right-click the report parameter that was automatically created for the dataset parameter, and then click **Parameter Properties**.</span></span>  
  
5.  <span data-ttu-id="33b18-135">Wählen Sie auf der Registerkarte **Allgemein** die Option **Mehrere Werte zulassen** aus, um anzugeben, dass für den Parameter mehr als ein Wert ausgewählt werden darf.</span><span class="sxs-lookup"><span data-stu-id="33b18-135">In the **General** tab, select **Allow multiple values** to allow a user to select more than one value for the parameter.</span></span>  
  
6.  <span data-ttu-id="33b18-136">(Optional) Geben Sie auf der Registerkarte **Verfügbare Werte** eine Liste mit verfügbaren Werten an, die dem Benutzer angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="33b18-136">(Optionally) In the **Available** values tab, specify a list of available values to display to the user.</span></span>  
  
     <span data-ttu-id="33b18-137">Eine Liste verfügbarer Werte schränkt die Auswahl, die ein Benutzer treffen kann, auf die gültigen Werte für den Parameter ein.</span><span class="sxs-lookup"><span data-stu-id="33b18-137">An available values list limits the choices a user can make to only valid values for the parameter.</span></span> <span data-ttu-id="33b18-138">Bei mehreren Werten beginnt die Liste mit der Funktion **Alles auswählen** , sodass der Benutzer alle Werte mit einem einzigen Mausklick auswählen oder löschen kann.</span><span class="sxs-lookup"><span data-stu-id="33b18-138">For multiple values, the top of list begins with a **Select All** feature so the user can select or clear all values with a single click.</span></span> <span data-ttu-id="33b18-139">Wenn Sie die für den Berichtsparameter verfügbaren Werte mit einer Datasetabfrage abrufen möchten, achten Sie darauf, kein Dataset auszuwählen, das die demselben Berichtsparameter zugeordnete Abfragevariable enthält.</span><span class="sxs-lookup"><span data-stu-id="33b18-139">If you choose to get the available values for the report parameter from a dataset query, be sure to select a dataset that does not contain the query variable that is associated with the same report parameter.</span></span>  
  
     <span data-ttu-id="33b18-140">Weitere Informationen finden Sie unter [Hinzufügen, Ändern oder Löschen von verfügbaren Werten für einen Berichtsparameter (Berichts-Generator und SSRS)](add-change-or-delete-available-values-for-a-report-parameter.md).</span><span class="sxs-lookup"><span data-stu-id="33b18-140">For more information, see [Add, Change, or Delete Available Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33b18-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="33b18-141">See Also</span></span>  
 <span data-ttu-id="33b18-142">[Hinzufügen von kaskadierenden Parametern zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="33b18-142">[Add Cascading Parameters to a Report &#40;Report Builder and SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="33b18-143">Hinzufügen, Ändern oder Löschen von Berichtsparametern &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="33b18-143">Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;</span></span>](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md)  
  
  
