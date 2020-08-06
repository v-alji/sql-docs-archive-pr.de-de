---
title: Beziehung zwischen zwei Tabellen erstellen (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.managereldb.f1
- sql12.asvs.bidtoolset.createrelatdb.f1
ms.assetid: 052d77b7-7922-408a-a200-786016ee4d15
author: minewiskan
ms.author: owend
ms.openlocfilehash: 33481b8d50be9ca632bcade932d51df86c1910a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616217"
---
# <a name="create-a-relationship-between-two-tables-ssas-tabular"></a><span data-ttu-id="c27f5-102">Erstellen einer Beziehung zwischen zwei Tabellen (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="c27f5-102">Create a Relationship Between Two Tables (SSAS Tabular)</span></span>
  <span data-ttu-id="c27f5-103">Wenn die Tabellen in der Datenquelle nicht über vorhandene Beziehungen verfügen oder wenn Sie neue Tabellen hinzufügen, können Sie zum Erstellen neuer Beziehungen die Tools im Modell-Designer verwenden.</span><span class="sxs-lookup"><span data-stu-id="c27f5-103">If the tables in your data source do not have existing relationships, or if you add new tables, you can use the tools in the model designer to create new relationships.</span></span> <span data-ttu-id="c27f5-104">Weitere Informationen darüber, wie Beziehungen in tabellarischen Modellen verwendet werden, finden Sie unter [Beziehungen &#40;SSAS – tabellarisch&#41;](relationships-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="c27f5-104">For information about how relationships are used in tabular models, see [Relationships &#40;SSAS Tabular&#41;](relationships-ssas-tabular.md).</span></span>  
  
## <a name="create-a-relationship-between-two-tables"></a><span data-ttu-id="c27f5-105">Erstellen einer Beziehung zwischen zwei Tabellen</span><span class="sxs-lookup"><span data-stu-id="c27f5-105">Create a relationship between two tables</span></span>  
  
#### <a name="to-create-a-relationship-between-two-tables-in-diagram-view-click-and-drag"></a><span data-ttu-id="c27f5-106">So erstellen Sie eine Beziehung zwischen zwei Tabellen in der Diagrammsicht (Klicken und Ziehen)</span><span class="sxs-lookup"><span data-stu-id="c27f5-106">To create a relationship between two tables in Diagram View (Click and drag)</span></span>  
  
1.  <span data-ttu-id="c27f5-107">Klicken Sie in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]auf das Menü **Modell** , auf **Modellansicht**und dann auf **Diagrammsicht**.</span><span class="sxs-lookup"><span data-stu-id="c27f5-107">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, then click **Model View**, and then click **Diagram View**.</span></span>  
  
2.  <span data-ttu-id="c27f5-108">Klicken Sie auf eine Spalte innerhalb einer Tabelle, und halten Sie die Maustaste gedrückt. Ziehen Sie dann den Cursor auf eine verknüpfte Suchspalte in einer verknüpften Suchtabelle, und lassen Sie die Maustaste wieder los.</span><span class="sxs-lookup"><span data-stu-id="c27f5-108">Click (and hold) on a column within a table, then drag the cursor to a related lookup column in a related lookup table, and then release.</span></span> <span data-ttu-id="c27f5-109">Die Beziehung wird automatisch in der richtigen Reihenfolge erstellt.</span><span class="sxs-lookup"><span data-stu-id="c27f5-109">The relationship will be created in the correct order automatically.</span></span>  
  
#### <a name="to-create-a-relationship-between-two-tables-in-diagram-view-right-click"></a><span data-ttu-id="c27f5-110">So erstellen Sie eine Beziehung zwischen zwei Tabellen in der Diagrammsicht (durch Rechtsklicken)</span><span class="sxs-lookup"><span data-stu-id="c27f5-110">To create a relationship between two tables in Diagram View (Right-click)</span></span>  
  
1.  <span data-ttu-id="c27f5-111">Klicken Sie in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]auf das Menü **Modell** , auf **Modellansicht**und dann auf **Diagrammsicht**.</span><span class="sxs-lookup"><span data-stu-id="c27f5-111">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, then click **Model View**, and then click **Diagram View**.</span></span>  
  
2.  <span data-ttu-id="c27f5-112">Klicken Sie mit der rechten Maustaste auf eine Tabellenüberschrift oder eine Spalte, und klicken Sie dann auf **Beziehung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="c27f5-112">Right-click a table heading or column, and then click **Create Relationship**.</span></span>  
  
3.  <span data-ttu-id="c27f5-113">Klicken Sie im Dialogfeld **Beziehung erstellen** auf den Pfeil nach unten für **Tabelle**, und wählen Sie aus der Dropdownliste eine Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="c27f5-113">In the **Create Relationship** dialog box, click the down arrow for **Table**, and select a table from the dropdown list.</span></span>  
  
     <span data-ttu-id="c27f5-114">Diese Tabelle sollte sich auf der n-Seite einer 1:n-Beziehung befinden.</span><span class="sxs-lookup"><span data-stu-id="c27f5-114">In a "one-to-many" relationship, this table should be on the "many" side.</span></span>  
  
4.  <span data-ttu-id="c27f5-115">Wählen Sie für **Spalte**die Spalte aus, die die Daten enthält, die sich auf **Verknüpfte Suchspalte**beziehen.</span><span class="sxs-lookup"><span data-stu-id="c27f5-115">For **Column**, select the column that contains the data that is related to **Related Lookup Column**.</span></span> <span data-ttu-id="c27f5-116">Die Spalte wird automatisch ausgewählt, wenn Sie mit der rechten Maustaste auf eine Spalte geklickt haben, um die Beziehung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c27f5-116">The column is automatically selected if you right-clicked on a column to create the relationship.</span></span>  
  
5.  <span data-ttu-id="c27f5-117">Wählen Sie unter **Verknüpfte Suchtabelle**eine Tabelle mit mindestens einer Spalte mit Daten aus, die sich auf die gerade ausgewählte **Tabelle**beziehen.</span><span class="sxs-lookup"><span data-stu-id="c27f5-117">For **Related Lookup Table**, select a table that has at least one column of data that is related to the table you just selected for **Table**.</span></span>  
  
     <span data-ttu-id="c27f5-118">Diese Tabelle sollte sich auf der 1-Seite einer 1:n-Beziehung befinden. Dies bedeutet, dass die Werte in der ausgewählten Spalte keine Duplikate enthalten.</span><span class="sxs-lookup"><span data-stu-id="c27f5-118">In a "one-to-many" relationship, this table should be on the "one" side, meaning that the values in the selected column do not contain duplicates.</span></span> <span data-ttu-id="c27f5-119">Wenn Sie versuchen, die Beziehung in der falschen Reihenfolge (1:n statt n:1) zu erstellen, wird ein Symbol neben dem Feld **Verknüpfte Suchspalte** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c27f5-119">If you attempt to create the relationship in the wrong order (one-to-many instead of many-to-one), an icon will appear next to the **Related Lookup Column** field.</span></span> <span data-ttu-id="c27f5-120">Kehren Sie die Reihenfolge um, um eine gültige Beziehung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c27f5-120">Reverse the order to create a valid relationship.</span></span>  
  
6.  <span data-ttu-id="c27f5-121">Wählen Sie für **Verknüpfte Suchspalte**eine Spalte mit eindeutigen Werten aus, die den Werten in der für **Spalte**ausgewählten Spalte entsprechen.</span><span class="sxs-lookup"><span data-stu-id="c27f5-121">For **Related Lookup Column**, select a column that has unique values that match the values in the column you selected for **Column**.</span></span>  
  
7.  <span data-ttu-id="c27f5-122">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="c27f5-122">Click **Create**.</span></span>  
  
#### <a name="to-create-a-relationship-between-two-tables-in-data-view"></a><span data-ttu-id="c27f5-123">So erstellen Sie eine Beziehung zwischen Tabellen in der Datenansicht</span><span class="sxs-lookup"><span data-stu-id="c27f5-123">To create a relationship between two tables in Data View</span></span>  
  
1.  <span data-ttu-id="c27f5-124">Klicken Sie in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]auf das Menü **Tabelle** und dann auf **Beziehungen erstellen**.</span><span class="sxs-lookup"><span data-stu-id="c27f5-124">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Table** menu, and then click **Create Relationships**.</span></span>  
  
2.  <span data-ttu-id="c27f5-125">Klicken Sie im Dialogfeld **Beziehung erstellen** auf den Pfeil nach unten für **Tabelle**, und wählen Sie aus der Dropdownliste eine Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="c27f5-125">In the **Create Relationship** dialog box, click the down arrow for **Table**, and select a table from the dropdown list.</span></span>  
  
     <span data-ttu-id="c27f5-126">Diese Tabelle sollte sich auf der n-Seite einer 1:n-Beziehung befinden.</span><span class="sxs-lookup"><span data-stu-id="c27f5-126">In a "one-to-many" relationship, this table should be on the "many" side.</span></span>  
  
3.  <span data-ttu-id="c27f5-127">Wählen Sie für **Spalte**die Spalte aus, die die Daten enthält, die sich auf **Verknüpfte Suchspalte**beziehen.</span><span class="sxs-lookup"><span data-stu-id="c27f5-127">For **Column**, select the column that contains the data that is related to **Related Lookup Column**.</span></span>  
  
4.  <span data-ttu-id="c27f5-128">Wählen Sie unter **Verknüpfte Suchtabelle**eine Tabelle mit mindestens einer Spalte mit Daten aus, die sich auf die gerade ausgewählte **Tabelle**beziehen.</span><span class="sxs-lookup"><span data-stu-id="c27f5-128">For **Related Lookup Table**, select a table that has at least one column of data that is related to the table you just selected for **Table**.</span></span>  
  
     <span data-ttu-id="c27f5-129">Diese Tabelle sollte sich auf der 1-Seite einer 1:n-Beziehung befinden. Dies bedeutet, dass die Werte in der ausgewählten Spalte keine Duplikate enthalten.</span><span class="sxs-lookup"><span data-stu-id="c27f5-129">In a "one-to-many" relationship, this table should be on the "one" side, meaning that the values in the selected column do not contain duplicates.</span></span> <span data-ttu-id="c27f5-130">Wenn Sie versuchen, die Beziehung in der falschen Reihenfolge (1:n statt n:1) zu erstellen, wird ein Symbol neben dem Feld **Verknüpfte Suchspalte** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c27f5-130">If you attempt to create the relationship in the wrong order (one-to-many instead of many-to-one), an icon will appear next to the **Related Lookup Column** field.</span></span> <span data-ttu-id="c27f5-131">Kehren Sie die Reihenfolge um, um eine gültige Beziehung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c27f5-131">Reverse the order to create a valid relationship.</span></span>  
  
5.  <span data-ttu-id="c27f5-132">Wählen Sie für **Verknüpfte Suchspalte**eine Spalte mit eindeutigen Werten aus, die den Werten in der für **Spalte**ausgewählten Spalte entsprechen.</span><span class="sxs-lookup"><span data-stu-id="c27f5-132">For **Related Lookup Column**, select a column that has unique values that match the values in the column you selected for **Column**.</span></span>  
  
6.  <span data-ttu-id="c27f5-133">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="c27f5-133">Click **Create**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c27f5-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c27f5-134">See Also</span></span>  
 <span data-ttu-id="c27f5-135">[Löschen von Beziehungen &#40;tabellarischen SSAS-&#41;](delete-relationships-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="c27f5-135">[Delete Relationships &#40;SSAS Tabular&#41;](delete-relationships-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="c27f5-136">Beziehungen &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="c27f5-136">Relationships &#40;SSAS Tabular&#41;</span></span>](relationships-ssas-tabular.md)  
  
  
