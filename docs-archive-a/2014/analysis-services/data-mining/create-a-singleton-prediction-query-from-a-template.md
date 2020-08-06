---
title: Erstellen einer SINGLETON-Vorhersage Abfrage aus einer Vorlage | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- singleton query predictions [DMX]
ms.assetid: e0a68ab0-bece-4d25-b464-47f1719302e6
author: minewiskan
ms.author: owend
ms.openlocfilehash: a80e853875cce349dd8623fab3c30f1ad09bfbf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609535"
---
# <a name="create-a-singleton-prediction-query-from-a-template"></a><span data-ttu-id="6596c-102">Erstellen einer SINGLETON-Vorhersageabfrage aus einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="6596c-102">Create a Singleton Prediction Query from a Template</span></span>
  <span data-ttu-id="6596c-103">Eine SINGLETON-Abfrage ist nützlich, wenn Sie ein Modell verwenden, das Sie für Vorhersagen verwenden möchten, aber nicht einem externen Eingabe DataSet zuordnen oder Massen Vorhersagen treffen möchten.</span><span class="sxs-lookup"><span data-stu-id="6596c-103">A singleton query is useful when you have a model that you want to use for prediction, but don't want to map it to an external input data set or make bulk predictions.</span></span> <span data-ttu-id="6596c-104">Mit einer SINGLETON-Abfrage können Sie einen Wert oder Werte für das Modell bereitstellen und sofort den vorhergesagten Wert anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6596c-104">With a singleton query, you can provide a value or values to the model and instantly see the predicted value.</span></span>  
  
 <span data-ttu-id="6596c-105">Zum Beispiel stellt die folgende DMX-Abfrage eine SINGLETON-Abfrage für das als Ziel verwendete Mailingmodell dar (TM_Decision_Tree).</span><span class="sxs-lookup"><span data-stu-id="6596c-105">For example, the following DMX query represents a singleton query against the targeted mailing model, TM_Decision_Tree.</span></span>  
  
```  
SELECT * FROM [TM_Decision_tree] ;  
NATURAL PREDICTION JOIN  
(SELECT '2' AS [Number Children At Home], '45' as [Age])  
AS [t]  
```  
  
 <span data-ttu-id="6596c-106">In der folgenden Vorgehensweise wird beschrieben, wie die Abfrage mit dem Vorlagen-Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] rasch erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="6596c-106">The procedure that follows describes how to use the Template Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to quickly create this query.</span></span>  
  
### <a name="to-open-the-analysis-services-templates-in-sql-server-management-studio"></a><span data-ttu-id="6596c-107">So öffnen Sie die Analysis Services-Vorlagen in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6596c-107">To open the Analysis Services templates in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="6596c-108">Klicken Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]im Menü **Ansicht** auf **Vorlagen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="6596c-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="6596c-109">Klicken Sie auf das Cubesymbol, um die **Analysis-Server**-Vorlagen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6596c-109">Click the cube icon to open the **Analysis Server**templates.</span></span>  
  
### <a name="to-open-a-prediction-query-template"></a><span data-ttu-id="6596c-110">So öffnen Sie eine Vorhersageabfragevorlage</span><span class="sxs-lookup"><span data-stu-id="6596c-110">To open a prediction query template</span></span>  
  
1.  <span data-ttu-id="6596c-111">Erweitern Sie im **Vorlagen-Explorer**in der Liste der Analysis-Server-Vorlagen **DMX**, und erweitern Sie dann **Vorhersageabfragen**.</span><span class="sxs-lookup"><span data-stu-id="6596c-111">In **Template Explorer**, in the list of Analysis Server templates, expand **DMX**, and thenexpand **Prediction Queries**.</span></span>  
  
2.  <span data-ttu-id="6596c-112">Doppelklicken Sie auf **Singleton-Vorhersage**.</span><span class="sxs-lookup"><span data-stu-id="6596c-112">Double-click **Singleton Prediction**.</span></span>  
  
3.  <span data-ttu-id="6596c-113">Geben Sie im Dialogfeld **Verbindung mit Analysis Services herstellen** den Namen des Servers ein, auf dem sich die Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] befindet, die das abzufragende Miningmodell enthält.</span><span class="sxs-lookup"><span data-stu-id="6596c-113">In the **Connect to Analysis Services** dialog box, type the name of the server that has the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the mining model to be queried.</span></span>  
  
4.  <span data-ttu-id="6596c-114">Klicken Sie auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="6596c-114">Click **Connect**.</span></span>  
  
5.  <span data-ttu-id="6596c-115">Die Vorlage wird in der angegebenen Datenbank geöffnet, zusammen mit einem Miningmodell-Objektkatalog, der Data Mining-Funktionen und eine Liste von Data Mining-Strukturen und zugehörige Modelle enthält.</span><span class="sxs-lookup"><span data-stu-id="6596c-115">The template opens in the specified database, together with a mining model Object Browser that contains data mining functions and a list of data mining structures and related models.</span></span>  
  
### <a name="to-customize-the-singleton-query-template"></a><span data-ttu-id="6596c-116">So passen Sie die SINGLETON-Abfragevorlage an</span><span class="sxs-lookup"><span data-stu-id="6596c-116">To customize the singleton query template</span></span>  
  
1.  <span data-ttu-id="6596c-117">Klicken Sie in der Vorlage auf die Dropdownliste **Verfügbare Datenbanken** , und wählen Sie in der Liste eine Instanz von Analysis Service aus.</span><span class="sxs-lookup"><span data-stu-id="6596c-117">In the template, click the **Available Databases** drop-down list, and then select an instance of Analysis Service from the list.</span></span>  
  
2.  <span data-ttu-id="6596c-118">Wählen Sie in der Liste **Miningmodell** das Miningmodell aus, das Sie abfragen möchten.</span><span class="sxs-lookup"><span data-stu-id="6596c-118">In the **Mining Model** list, select the mining model that you want to query.</span></span>  
  
     <span data-ttu-id="6596c-119">Die Liste der Spalten im Miningmodell wird im Bereich **Metadaten** des Objektkatalogs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6596c-119">The list of columns in the mining model appears in the **Metadata** pane of the object browser.</span></span>  
  
3.  <span data-ttu-id="6596c-120">Wählen Sie im Menü **Abfrage** die Option **Werte für Vorlagenparameter angeben**aus.</span><span class="sxs-lookup"><span data-stu-id="6596c-120">On the **Query** menu, select **Specify Values for Template Parameters**.</span></span>  
  
4.  <span data-ttu-id="6596c-121">Geben Sie in der Zeile **Liste auswählen** das Platzhalterzeichen \* ein, um alle Spalten zurückzugeben, oder geben Sie eine durch Komma getrennte Liste von Spalten und Ausdrücken ein, um bestimmte Spalten zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="6596c-121">In the **select list** row, type \* to return all columns, or type a comma-delimited list of columns and expressions to return specific columns.</span></span>  
  
     <span data-ttu-id="6596c-122">Wenn Sie \* eingeben, wird die vorhersagbare Spalte zurückgegeben sowie alle Spalten, für die Sie in Schritt 6 neue Werte eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="6596c-122">If you type \*, the predictable column is returned, together with any columns for which you provide new values for in step 6.</span></span>  
  
     <span data-ttu-id="6596c-123">In dem Beispielcode am Beginn dieses Themas wurde \* in die Zeile **Liste auswählen** eingegeben.</span><span class="sxs-lookup"><span data-stu-id="6596c-123">For the sample code shown at the start of this topic, the **select list** row was set to \*.</span></span>  
  
5.  <span data-ttu-id="6596c-124">Geben Sie in der Zeile **Miningmodell** den Namen eines Miningmodells aus der Liste der Miningmodelle im **Objekt-Explorer**ein.</span><span class="sxs-lookup"><span data-stu-id="6596c-124">In the **mining model** row, type the name of the mining model from among the list of mining models that appear in **Object Explorer**.</span></span>  
  
     <span data-ttu-id="6596c-125">Für den Beispielcode, der am Anfang dieses Themas gezeigt wird, wurde die **Mining Modell** Zeile auf den Namen festgelegt `TM_Decision_Tree` .</span><span class="sxs-lookup"><span data-stu-id="6596c-125">For the sample code shown at the start of this topic, the **mining model** row was set to the name, `TM_Decision_Tree`.</span></span>  
  
6.  <span data-ttu-id="6596c-126">Geben Sie in der Zeile **Wert** den neuen Datenwert ein, für den Sie eine Vorhersage machen möchten.</span><span class="sxs-lookup"><span data-stu-id="6596c-126">In the **value** row, type the new data value for which you want to make a prediction.</span></span>  
  
     <span data-ttu-id="6596c-127">Für den Beispielcode am Anfang dieses Themas wurde die Zeile **Wert** auf festgelegt, um das `2` Fahrradkauf Verhalten basierend auf der Anzahl der zu Hause enden Kinder vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="6596c-127">For the sample code shown at the start of this topic, the **value** row was set to `2` to predict bike buying behavior based on the number of children at home.</span></span>  
  
7.  <span data-ttu-id="6596c-128">Geben Sie in der Zeile **Spalte** den Namen der Spalte im Miningmodell ein, der die neuen Daten zugeordnet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6596c-128">In the **column** row, type the name of the column in the mining model to which the new data should be mapped.</span></span>  
  
     <span data-ttu-id="6596c-129">Für den Beispielcode am Anfang dieses Themas wurde die **Spalten** Zeile auf festgelegt `Number Children at Home` .</span><span class="sxs-lookup"><span data-stu-id="6596c-129">For the sample code shown at the start of this topic, the **column** row was set to `Number Children at Home`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6596c-130">Wenn Sie das Dialogfeld **Werte für Vorlagenparameter angeben** verwenden, müssen Sie den Spaltennamen nicht in eckige Klammern einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="6596c-130">When you use the **Specify Values for Template Parameters** dialog box, you do not have to add square brackets around the column name.</span></span> <span data-ttu-id="6596c-131">Die Klammern werden automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6596c-131">The brackets will automatically be added for you.</span></span>  
  
8.  <span data-ttu-id="6596c-132">Belassen Sie den **Eingabealias** als `t` .</span><span class="sxs-lookup"><span data-stu-id="6596c-132">Leave the **input alias** as `t`.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
10. <span data-ttu-id="6596c-133">Suchen Sie im Abfragetextbereich nach einer roten Wellenlinie unter dem Komma und den Auslassungspunkten, die Syntaxfehler anzeigt.</span><span class="sxs-lookup"><span data-stu-id="6596c-133">In the query text pane, find the red squiggle under the comma and ellipsis that indicates a syntax error.</span></span> <span data-ttu-id="6596c-134">Löschen Sie die Auslassungspunkte, und fügen Sie alle weiteren gewünschten Abfragebedingungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="6596c-134">Delete the ellipsis, and add any additional query condition that you want.</span></span> <span data-ttu-id="6596c-135">Wenn Sie keine weiteren Bedingungen hinzufügen, löschen Sie das Komma.</span><span class="sxs-lookup"><span data-stu-id="6596c-135">If you do not add any other conditions, delete the comma.</span></span>  
  
     <span data-ttu-id="6596c-136">In dem Beispielcode am Beginn dieses Themas wurde für die zusätzliche Abfragebedingung `'45' as [Age]` eingegeben.</span><span class="sxs-lookup"><span data-stu-id="6596c-136">For the sample code shown at the start of this topic, the additional query condition was set to `'45' as [Age]`.</span></span>  
  
11. <span data-ttu-id="6596c-137">Klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6596c-137">Click **Execute**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6596c-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6596c-138">See Also</span></span>  
 [<span data-ttu-id="6596c-139">Erstellen von Vorhersagen &#40;Tutorial zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="6596c-139">Creating Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../tutorials/creating-predictions-basic-data-mining-tutorial.md)  
  
  
