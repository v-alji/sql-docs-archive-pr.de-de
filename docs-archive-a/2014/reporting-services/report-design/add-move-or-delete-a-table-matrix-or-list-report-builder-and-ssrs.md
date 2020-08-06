---
title: Hinzufügen, Verschieben oder Löschen einer Tabelle, Matrix oder Liste (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4b97c470-cde0-4bb1-a46e-5f5f5553feaa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 43941639a41c897a49cd34662b74de26a27e3f07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723465"
---
# <a name="add-move-or-delete-a-table-matrix-or-list-report-builder-and-ssrs"></a><span data-ttu-id="0d05c-102">Hinzufügen, Verschieben oder Löschen einer Tabelle, Matrix oder Liste (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="0d05c-102">Add, Move, or Delete a Table, Matrix, or List (Report Builder and SSRS)</span></span>
  <span data-ttu-id="0d05c-103">Ein Datenbereich zeigt Daten aus einem Berichtsdataset an.</span><span class="sxs-lookup"><span data-stu-id="0d05c-103">A data region displays data from a report dataset.</span></span> <span data-ttu-id="0d05c-104">Zu den Datenbereichen gehören Tabelle, Matrix, Liste, Diagramm und Messgerät.</span><span class="sxs-lookup"><span data-stu-id="0d05c-104">Data regions include table, matrix, list, chart, and gauge.</span></span> <span data-ttu-id="0d05c-105">Um einen Datenbereich in einen anderen Datenbereich zu schachteln, fügen Sie die Datenbereiche getrennt hinzu, und ziehen Sie dann den Datenbereich, den Sie schachteln möchten, auf den anderen Datenbereich.</span><span class="sxs-lookup"><span data-stu-id="0d05c-105">To nest one data region inside another, add each data region separately, and then drag the child data region onto the parent data region.</span></span>  
  
 <span data-ttu-id="0d05c-106">Am einfachsten können Sie einen Tabellen- oder Matrixdatenbereich einem Bericht hinzufügen, indem Sie den Assistenten Neue Tabelle oder Neue Matrix ausführen.</span><span class="sxs-lookup"><span data-stu-id="0d05c-106">The simplest way to add a table or matrix data region to your report is to run the New Table or New Matrix Wizard.</span></span> <span data-ttu-id="0d05c-107">Diese Assistenten führen Sie durch die einzelnen Schritte bei der Auswahl einer Verbindung mit einer Datenquelle, dem Anordnen von Feldern und der Auswahl von Layout und Stil.</span><span class="sxs-lookup"><span data-stu-id="0d05c-107">These wizards will guide you through the process of choosing a connection to a data source, arranging fields, and choosing the layout and style.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0d05c-108">Der Assistent ist nur in Berichts-Generator verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0d05c-108">The wizard is available only in Report Builder.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-table-or-matrix-to-a-report-by-using-the-new-table-or-new-matrix-wizard"></a><span data-ttu-id="0d05c-109">So fügen Sie einem Bericht mit den Assistenten "Neue Tabelle" oder "Neue Matrix" eine Tabelle oder Matrix hinzu</span><span class="sxs-lookup"><span data-stu-id="0d05c-109">To add a table or matrix to a report by using the New Table or New Matrix Wizard</span></span>  
  
1.  <span data-ttu-id="0d05c-110">Klicken Sie auf der Registerkarte **Einfügen** auf **Tabelle** oder **Matrix**und dann auf **Tabellen-Assistent** oder **Matrix-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="0d05c-110">On the **Insert** tab, click **Table** or **Matrix**, and then click **Table Wizard** or **Matrix Wizard**.</span></span>  
  
2.  <span data-ttu-id="0d05c-111">Führen Sie die Schritte im Assistenten für neue **Tabellen** oder **neue Matrix** aus.</span><span class="sxs-lookup"><span data-stu-id="0d05c-111">Follow the steps in the **NewTable** or **New Matrix** wizard.</span></span>  
  
3.  <span data-ttu-id="0d05c-112">Klicken Sie auf der Registerkarte **Home** auf **Ausführen** , um den gerenderten Bericht anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0d05c-112">On the **Home** tab, click **Run** to see the rendered report.</span></span>  
  
4.  <span data-ttu-id="0d05c-113">Klicken Sie auf der Registerkarte **Ausführen** auf **Entwurf** , um den Bericht weiter zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="0d05c-113">On the **Run** tab, click **Design** to continue working on the report.</span></span>  
  
### <a name="to-add-a-data-region"></a><span data-ttu-id="0d05c-114">So fügen Sie einen Datenbereich hinzu</span><span class="sxs-lookup"><span data-stu-id="0d05c-114">To add a data region</span></span>  
  
1.  <span data-ttu-id="0d05c-115">Klicken Sie auf dem **Menüband**in der Gruppe **Datenbereiche** auf den hinzuzufügenden Datenbereich.</span><span class="sxs-lookup"><span data-stu-id="0d05c-115">On the **Ribbon**, in the **Data Regions** group, click the data region to add.</span></span>  
  
2.  <span data-ttu-id="0d05c-116">Klicken Sie auf die Entwurfsoberfläche, und erstellen Sie dann durch Ziehen ein Feld mit der gewünschten Datenbereichsgröße.</span><span class="sxs-lookup"><span data-stu-id="0d05c-116">Click the design surface, and then drag to create a box that is the desired size of the data region.</span></span>  
  
3.  <span data-ttu-id="0d05c-117">Ziehen Sie ein Berichtsdataset-Feld aus dem Berichtsdatenbereich auf eine Datenbereichszelle.</span><span class="sxs-lookup"><span data-stu-id="0d05c-117">Drag a report dataset field from the Report Data pane onto a data region cell.</span></span> <span data-ttu-id="0d05c-118">Jetzt ist der Datenbereich an Daten im Berichtsdataset gebunden.</span><span class="sxs-lookup"><span data-stu-id="0d05c-118">The data region is now bound to data from the report dataset.</span></span>  
  
### <a name="to-select-a-data-region"></a><span data-ttu-id="0d05c-119">So wählen Sie einen Datenbereich aus</span><span class="sxs-lookup"><span data-stu-id="0d05c-119">To select a data region</span></span>  
  
-   <span data-ttu-id="0d05c-120">Klicken Sie für einen Tablix-Datenbereich mit der rechten Maustaste auf den Eckziehpunkt.</span><span class="sxs-lookup"><span data-stu-id="0d05c-120">For a tablix data region, right-click the corner handle.</span></span> <span data-ttu-id="0d05c-121">Klicken Sie für einen Diagramm- oder Messgerät-Datenbereich in den Datenbereich.</span><span class="sxs-lookup"><span data-stu-id="0d05c-121">For a chart or gauge data region, click in the data region.</span></span>  
  
     <span data-ttu-id="0d05c-122">Ein Auswahlkästchen und acht Ziehpunkte werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0d05c-122">A selection handle and eight resizing handles appear.</span></span>  
  
     <span data-ttu-id="0d05c-123">Klicken Sie für geschachtelte Datenbereiche mit der rechten Maustaste in den geschachtelten Datenbereich, klicken Sie auf **Auswählen**, und wählen Sie anschließend das gewünschte Berichtselement aus.</span><span class="sxs-lookup"><span data-stu-id="0d05c-123">For nested data regions, right-click in the nested data region, click **Select**, and then select the report item you want.</span></span> <span data-ttu-id="0d05c-124">Im Eigenschaftenbereich können Sie überprüfen, welches Berichtselement ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="0d05c-124">To verify which report item is selected, use the Properties pane.</span></span> <span data-ttu-id="0d05c-125">Der Name des auf der Entwurfsoberfläche ausgewählten Elements wird in der Symbolleiste des Eigenschaftenbereichs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0d05c-125">The name of the selected item on the design surface appears in the toolbar of the Properties pane.</span></span>  
  
### <a name="to-move-a-data-region"></a><span data-ttu-id="0d05c-126">So verschieben Sie einen Datenbereich</span><span class="sxs-lookup"><span data-stu-id="0d05c-126">To move a data region</span></span>  
  
-   <span data-ttu-id="0d05c-127">Um einen Datenbereich zu verschieben, klicken Sie auf das Auswahlkästchen des Datenbereichs, und ziehen Sie ihn an die gewünschte Position.</span><span class="sxs-lookup"><span data-stu-id="0d05c-127">To move a data region, click the selection handle of the data region and drag it.</span></span> <span data-ttu-id="0d05c-128">Verwenden Sie Ausrichtungslinien, um den Bereich an vorhandenen Berichtselementen auszurichten.</span><span class="sxs-lookup"><span data-stu-id="0d05c-128">Use snaplines to align it to existing report items.</span></span>  
  
     <span data-ttu-id="0d05c-129">Wenn das Lineal nicht sichtbar ist, klicken Sie auf die Registerkarte Ansicht, und wählen Sie die Option **Lineal** aus.</span><span class="sxs-lookup"><span data-stu-id="0d05c-129">If the ruler is not visible, click the View tab and select the **Ruler** option.</span></span>  
  
     <span data-ttu-id="0d05c-130">Sie können den ausgewählten Datenbereich auf der Entwurfsoberfläche auch mit den Pfeiltasten verschieben.</span><span class="sxs-lookup"><span data-stu-id="0d05c-130">Alternatively, use the arrow keys to move the selected data region on the design surface.</span></span>  
  
### <a name="to-delete-a-data-region"></a><span data-ttu-id="0d05c-131">So löschen Sie einen Datenbereich</span><span class="sxs-lookup"><span data-stu-id="0d05c-131">To delete a data region</span></span>  
  
-   <span data-ttu-id="0d05c-132">Wählen Sie den Datenbereich aus, klicken Sie mit der rechten Maustaste in den Datenbereich, und klicken Sie anschließend auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="0d05c-132">Select the data region, right-click in the data region, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d05c-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0d05c-133">See Also</span></span>  
 <span data-ttu-id="0d05c-134">[Tablix-Datenbereich &#40;Berichts-Generator und SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0d05c-134">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0d05c-135">[Tabellen &#40;Berichts-Generator und SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0d05c-135">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0d05c-136">[Matrizen &#40;Berichts-Generator und SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0d05c-136">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="0d05c-137">[Listet &#40;Berichts-Generator und SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0d05c-137">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="0d05c-138">Tabellen, Matrizen und Listen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0d05c-138">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
