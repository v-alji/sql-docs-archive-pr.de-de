---
title: Hinzufügen oder Entfernen von Tabellen oder Sichten in einer Datenquellen Sicht (Analysis Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dsvdesigner.tablespane.f1
helpviewer_keywords:
- deleting tables
- tables [Analysis Services]
- removing tables
- adding tables
- data source views [Analysis Services], tables
- tables [Analysis Services], data source views
ms.assetid: 98307d04-6548-4d7d-9244-2371dd165249
author: minewiskan
ms.author: owend
ms.openlocfilehash: da1bc2b1ac0af7576cfe3c3593b451f78d6a9fae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622256"
---
# <a name="adding-or-removing-tables-or-views-in-a-data-source-view-analysis-services"></a><span data-ttu-id="36885-102">Hinzufügen oder Entfernen von Tabellen oder Sichten in einer Datenquellensicht (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="36885-102">Adding or Removing Tables or Views in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="36885-103">Nachdem Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]eine Datenquellensicht (Data Source View, DSV) erstellt haben, können Sie sie im Datenquellensicht-Designer ändern, indem Sie Tabellen und Spalten hinzufügen oder entfernen. Dies schließt auch Tabellen und Spalten aus einer anderen Datenquelle ein.</span><span class="sxs-lookup"><span data-stu-id="36885-103">After you have created a data source view (DSV) in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you can modify it in Data Source View Designer by adding or removing tables and columns, including tables and columns from another data source.</span></span>  
  
 <span data-ttu-id="36885-104">Um die DSV im Datenquellensicht-Designer zu öffnen, doppelklicken Sie im Projektmappen-Explorer auf die DSV.</span><span class="sxs-lookup"><span data-stu-id="36885-104">To open the DSV in Data Source View Designer, you double-click the DSV in Solution Explorer.</span></span> <span data-ttu-id="36885-105">Sobald die DSV geöffnet ist, können Sie sie mit dem Befehl **Tabellen hinzufügen/entfernen** auf der Schaltflächenleiste oder im Menü ändern oder erweitern.</span><span class="sxs-lookup"><span data-stu-id="36885-105">Once you open the DSV, you can use the **Add/Remove Tables** command on the button bar or menu to modify or extend the DSV.</span></span> <span data-ttu-id="36885-106">Sie können auch mit den Objekten im Diagramm arbeiten.</span><span class="sxs-lookup"><span data-stu-id="36885-106">You can also work with the objects in the diagram.</span></span> <span data-ttu-id="36885-107">Sie können z. B. ein Objekt auswählen und es dann mit der ENTF-TASTE auf der Tastatur entfernen.</span><span class="sxs-lookup"><span data-stu-id="36885-107">For example, you can select an object and then use the Delete key on your keyboard to remove an object.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="36885-108">Gehen Sie beim Entfernen einer Tabelle mit Bedacht vor.</span><span class="sxs-lookup"><span data-stu-id="36885-108">Use caution when removing a table.</span></span> <span data-ttu-id="36885-109">Beim Entfernen einer Tabelle werden alle zugeordneten Spalten und Beziehungen aus der DSV gelöscht und alle an die Tabelle gebundenen Objekte ungültig.</span><span class="sxs-lookup"><span data-stu-id="36885-109">Removing a table deletes all the associated columns and relationships from the DSV and invalidates all objects bound to that table.</span></span>  
  
## <a name="selecting-tables-or-views-to-add-or-remove"></a><span data-ttu-id="36885-110">Auswählen von Tabellen oder Sichten für das Hinzufügen oder Entfernen</span><span class="sxs-lookup"><span data-stu-id="36885-110">Selecting Tables or Views to Add or Remove</span></span>  
 <span data-ttu-id="36885-111">Im Dialogfeld **Tabellen hinzufügen/entfernen** können Sie Tabellen oder Sichten zwischen den Listen **Verfügbare Objekte** und **Eingeschlossene Objekte** verschieben.</span><span class="sxs-lookup"><span data-stu-id="36885-111">Using the **Add/Remove Tables** dialog box, you can move tables or views between the **Available objects** and **Included objects** lists.</span></span> <span data-ttu-id="36885-112">Die Liste **Verfügbare Objekte** enthält zunächst alle Tabellen oder Sichten der Primärdatenquelle, die nicht bereits in der Datenquellensicht enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="36885-112">The **Available objects** list initially includes any tables or views in the primary data source that are not already in the data source view.</span></span> <span data-ttu-id="36885-113">Falls die primäre Datenquelle die `OPENROWSET`-Funktion unterstützt, können Sie auch Tabellen oder Sichten aus anderen Datenquellen des Projekts oder der Datenbank hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="36885-113">If the primary data source supports the `OPENROWSET` function, you can also add tables or views from other data sources in the project or database.</span></span>  
  
 <span data-ttu-id="36885-114">Wenn in einer DSV eine Tabelle hinzugefügt oder entfernt wird, wird die Tabelle ebenfalls im aktuell ausgewählten Diagramm in der DSV hinzugefügt bzw. entfernt.</span><span class="sxs-lookup"><span data-stu-id="36885-114">Adding or removing a table to the DSV also adds or removes the table to the currently selected diagram in the DSV.</span></span> <span data-ttu-id="36885-115">Weitere Informationen finden Sie unter [Verwenden von Diagrammen im Datenquellensicht-Designer &#40;Analysis Services&#41;](work-with-diagrams-in-data-source-view-designer-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="36885-115">For more information on diagrams, see [Work with Diagrams in Data Source View Designer &#40;Analysis Services&#41;](work-with-diagrams-in-data-source-view-designer-analysis-services.md).</span></span>  
  
 <span data-ttu-id="36885-116">Nach dem Verschieben einer Tabelle in die Liste **Eingeschlossene Objekte** des Dialogfelds **Tabellen hinzufügen/entfernen** können Sie alle verknüpften Tabellen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="36885-116">After you move a table to the **Included objects** list in the **Add/Remove Tables** dialog box, you can add all related tables.</span></span> <span data-ttu-id="36885-117">Durch diesen Vorgang werden der Datenquelle Tabellen nach Maßgabe von Fremdschlüsseleinschränkungen (soweit vorhanden) hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="36885-117">This operation adds tables according to foreign key constraints in the data source, if such constraints exist.</span></span> <span data-ttu-id="36885-118">Sind keine Fremdschlüsseleinschränkungen vorhanden, können Sie mithilfe der `NameMatchingCriteria`-Eigenschaft der Datenquellensicht Beziehungen festlegen, indem Sie ein Kriterium für die Zuordnung von Spaltennamen in Tabellen zur Generierung möglicher Beziehungen angeben.</span><span class="sxs-lookup"><span data-stu-id="36885-118">If foreign key constraints do not exist, you can use the `NameMatchingCriteria` property of the data source view to determine relationships by specifying a criterion for matching column names in tables to generate likely relationships.</span></span> <span data-ttu-id="36885-119">Wenn die `NameMatchingCriteria` Eigenschaft für die Datenquellen Sicht angegeben ist, klicken Sie auf verknüpfte **Tabellen hinzufügen** , um Tabellen aus der Datenquelle hinzuzufügen, die über übereinstimmende Spaltennamen verfügen.</span><span class="sxs-lookup"><span data-stu-id="36885-119">If the `NameMatchingCriteria`property is specified for the data source view, click **Add Related Tables** to add tables from the data source that have matching column names.</span></span> <span data-ttu-id="36885-120">Weitere Informationen zum Festlegen der- `NameMatchingCriteria` Eigenschaft finden Sie unter [Datenquellen Sichten in mehrdimensionalen Modellen](data-source-views-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="36885-120">For more information about setting the `NameMatchingCriteria` property, see [Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="36885-121">Das Hinzufügen oder Entfernen von Objekten in einer Datenquellensicht hat keine Auswirkungen auf die zugrunde liegende Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="36885-121">Adding or removing objects in a data source view does not affect the underlying data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36885-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="36885-122">See Also</span></span>  
 <span data-ttu-id="36885-123">[Datenquellen Sichten in mehrdimensionalen Modellen](data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="36885-123">[Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="36885-124">Verwenden von Diagrammen im Datenquellensicht-Designer &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="36885-124">Work with Diagrams in Data Source View Designer &#40;Analysis Services&#41;</span></span>](work-with-diagrams-in-data-source-view-designer-analysis-services.md)  
  
  
