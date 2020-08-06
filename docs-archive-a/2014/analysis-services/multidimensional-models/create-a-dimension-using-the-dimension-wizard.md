---
title: Erstellen einer Dimension mit dem Dimensions-Assistenten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], creating
ms.assetid: d84f66ae-7551-49bf-99d0-88368ca2dd0e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9ec38dc7170b915dce0cedea60c93385560e11f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721933"
---
# <a name="create-a-dimension-using-the-dimension-wizard"></a><span data-ttu-id="8f2ae-102">Erstellen einer Dimension mit dem Dimensions-Assistenten</span><span class="sxs-lookup"><span data-stu-id="8f2ae-102">Create a Dimension Using the Dimension Wizard</span></span>
  <span data-ttu-id="8f2ae-103">Sie können eine neue Dimension erstellen, indem Sie den Dimensions-Assistenten von [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]verwenden.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-103">You can create a new dimension by using the Dimension Wizard in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
### <a name="to-create-a-new-dimension"></a><span data-ttu-id="8f2ae-104">So erstellen Sie eine neue Dimension</span><span class="sxs-lookup"><span data-stu-id="8f2ae-104">To create a new dimension</span></span>  
  
1.  <span data-ttu-id="8f2ae-105">Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf **Dimensionen**, und klicken Sie dann auf **Neue Dimension**.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-105">In **Solution Explorer**, right-click **Dimensions**, and then click **New Dimension**.</span></span>  
  
2.  <span data-ttu-id="8f2ae-106">Wählen Sie auf der Seite **Erstellungsmethode auswählen** des Dimensions-Assistenten die Option **Vorhandene Tabelle verwenden**aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-106">On the **Select Creation Method** page of the Dimension Wizard, select **Use an existing table**, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8f2ae-107">Möglicherweise müssen Sie gelegentlich eine Dimension ohne eine vorhandene Tabelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-107">You might occasionally have to create a dimension without using an existing table.</span></span> <span data-ttu-id="8f2ae-108">Weitere Informationen finden Sie unter [Erstellen einer Dimension durch Generieren einer Nichtzeittabelle in der Datenquelle](create-a-dimension-by-generating-a-non-time-table-in-the-data-source.md) und [Erstellen einer Zeitdimension durch Generieren einer Zeittabelle](create-a-time-dimension-by-generating-a-time-table.md).</span><span class="sxs-lookup"><span data-stu-id="8f2ae-108">For more information, see [Create a Dimension by Generating a Non-Time Table in the Data Source](create-a-dimension-by-generating-a-non-time-table-in-the-data-source.md) and [Create a Time Dimension by Generating a Time Table](create-a-time-dimension-by-generating-a-time-table.md).</span></span>  
  
3.  <span data-ttu-id="8f2ae-109">Führen Sie auf der Seite **Quellinformationen angeben** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="8f2ae-109">On the **Specify Source Information** page, do the following procedures:</span></span>  
  
    1.  <span data-ttu-id="8f2ae-110">Wählen Sie in der Liste **Datenquellensicht** eine Datenquellensicht aus.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-110">In the **Data source view** list, select a data source view.</span></span>  
  
    2.  <span data-ttu-id="8f2ae-111">Wählen Sie in der Liste **Haupttabelle** die Hauptdimensionstabelle aus.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-111">In the **Main table** list, select the main dimension table.</span></span>  
  
    3.  <span data-ttu-id="8f2ae-112">Überprüfen Sie in der Liste **Schlüsselspalten** die Schlüsselspalten, die der Assistent automatisch auf Basis des Primärschlüssels ausgewählt hat, der in der Hauptdimensionstabelle definiert ist.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-112">In the **Key columns** list, review the key columns that the wizard has automatically selected based on the primary key that is defined in the main dimension table.</span></span> <span data-ttu-id="8f2ae-113">Um diese Standardeinstellung zu ändern, geben Sie die Schlüsselspalten an, die die Dimensionstabelle mit der Faktentabelle verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-113">To change this default setting, specify the key columns that link the dimension table to the fact table.</span></span>  
  
    4.  <span data-ttu-id="8f2ae-114">Überprüfen Sie in der Dropdownliste **Namensspalte** die Namensspalte, die der Assistent automatisch ausgewählt hat.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-114">In the **Name column** drop-down list, review the name column that the wizard has automatically selected.</span></span>  
  
         <span data-ttu-id="8f2ae-115">Dieser Standardname ist angemessen, wenn die Spalte beschreibende Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-115">This default name is appropriate when the column contains descriptive information.</span></span> <span data-ttu-id="8f2ae-116">Möglicherweise möchten Sie aber einen Namen angeben, der für den Endbenutzer mehr Aussagekraft besitzt.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-116">However, you might want to specify a name that contains values that are more meaningful for the end user.</span></span> <span data-ttu-id="8f2ae-117">Falls von einem Produktkategorieattribut in einer &lt;localizedText&gt;Products&lt;/localizedText&gt;-Dimension z. B. die **ProductCategoryKey** -Spalte als Schlüsselspalte verwendet wird, können Sie die **ProductCategoryName** -Spalte als Namensspalte angeben.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-117">For example, if a product category attribute in a Products dimension uses the **ProductCategoryKey** column as its key column, you can specify the **ProductCategoryName** column as its name column.</span></span>  
  
         <span data-ttu-id="8f2ae-118">Wenn die Liste **Schlüsselspalten** mehrere Schlüsselspalten enthält, müssen Sie eine Namensspalte angeben, die die Elementwerte für das Schlüsselattribut bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-118">If the **Key columns** list contains multiple key columns, you must specify a name column that provides the member values for the key attribute.</span></span> <span data-ttu-id="8f2ae-119">Hierzu können Sie eine benannte Berechnung in der Datenquellensicht erstellen und diese als Namensspalte verwenden.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-119">To do this, you can create a named calculation in the data source view and use that as the name column.</span></span>  
  
    5.  <span data-ttu-id="8f2ae-120">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-120">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="8f2ae-121">Wählen Sie auf der Seite **Verknüpfte Tabellen auswählen** die verknüpften Tabellen aus, die Sie in die Dimension einschließen möchten, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-121">On the **Select Related Tables** page, select the related tables that you want to include in your dimension, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8f2ae-122"> Wenn die angegebene Hauptdimensionstabelle Beziehungen zu anderen Dimensionstabellen hat, wird die Seite **Verknüpfte Tabellen auswählen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-122">The **Select Related Tables** page appears if the main dimension table that you specified has relationships to other dimension tables.</span></span>  
  
5.  <span data-ttu-id="8f2ae-123">Wählen Sie auf der Seite **Dimensionsattribute auswählen** die Attribute aus, die Sie in die Dimension einschließen möchten, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-123">On the **Select Dimension Attributes** page, select the attributes that you want to include in the dimension, and then click **Next**.</span></span>  
  
     <span data-ttu-id="8f2ae-124">Optional können Sie die Attributnamen ändern, das Durchsuchen aktivieren oder deaktivieren und den Attributtyp angeben.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-124">Optionally, you can change the attribute names, enable or disable browsing, and specify the attribute type.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8f2ae-125"> Um die Felder **Durchsuchen aktivieren** und **Attributtyp** eines Attributs zu aktivieren, muss das Attribut zum Einschließen in die Dimension ausgewählt sein.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-125">To make the **Enable Browsing** and **Attribute Type** fields of an attribute active, the attribute must be selected for inclusion in the dimension.</span></span>  
  
6.  <span data-ttu-id="8f2ae-126">Wählen Sie auf der Seite **Kontointelligenz definieren** in der Spalte **Integrierte Kontotypen** den Kontotyp aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-126">On the **Define Account Intelligence** page, in the **Built-In Account Types** column, select the account type, and then click **Next**.</span></span>  
  
     <span data-ttu-id="8f2ae-127">Der Kontotyp muss dem Kontotyp der Quelltabelle entsprechen, der in der Spalte **Kontotypen der Quelltabelle** aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-127">The account type must correspond to the account type of the source table that is listed in the **Source Table Account Types** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8f2ae-128"> Wenn Sie auf der Seite **Dimensionsattribute auswählen** des Assistenten ein **Kontotyp** -Dimensionsattribut ausgewählt haben, wird die Seite **Kontointelligenz definieren** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-128">The **Define Account Intelligence** page appears if you defined an **Account Type** dimension attribute on the **Select Dimension Attributes** page of the wizard.</span></span>  
  
7.  <span data-ttu-id="8f2ae-129">Geben Sie auf der Seite **Assistenten abschließen** einen Namen für die neue Dimension ein, und überprüfen Sie die Dimensionsstruktur.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-129">On the **Completing the Wizard** page, enter a name for the new dimension and review the dimension structure.</span></span> <span data-ttu-id="8f2ae-130">Wenn Sie Änderungen vornehmen möchten, klicken Sie auf **Zurück**, andernfalls auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-130">If you want to make changes, click **Back**; otherwise, click **Finish**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8f2ae-131">Nach Abschluss des Dimensions-Assistenten können Sie den Dimensions-Designer zum Hinzufügen, Entfernen und Konfigurieren von Attributen und Hierarchien in der Dimension verwenden.</span><span class="sxs-lookup"><span data-stu-id="8f2ae-131">You can use Dimension Designer after you complete the Dimension Wizard to add, remove, and configure attributes and hierarchies in the dimension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f2ae-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8f2ae-132">See Also</span></span>  
 [<span data-ttu-id="8f2ae-133">Erstellen einer Dimension anhand einer vorhandenen Tabelle</span><span class="sxs-lookup"><span data-stu-id="8f2ae-133">Create a Dimension by Using an Existing Table</span></span>](create-a-dimension-by-using-an-existing-table.md)  
  
  
