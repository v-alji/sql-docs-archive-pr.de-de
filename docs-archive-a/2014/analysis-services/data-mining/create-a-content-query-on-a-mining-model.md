---
title: Erstellen einer Inhalts Abfrage für ein Mining Modell | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content queries [DMX]
ms.assetid: a0ce837a-89ed-46cf-9ce1-801ccb75fa04
author: minewiskan
ms.author: owend
ms.openlocfilehash: 26af1100d6ba80185c1cc4de18548df0e387824c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694841"
---
# <a name="create-a-content-query-on-a-mining-model"></a><span data-ttu-id="c0d1a-102">Erstellen einer Miningmodell-Inhaltsabfrage</span><span class="sxs-lookup"><span data-stu-id="c0d1a-102">Create a Content Query on a Mining Model</span></span>
  <span data-ttu-id="c0d1a-103">Den Miningmodellinhalt können Sie programmgesteuert mit AMO oder XML/A abfragen. Das Erstellen von Abfragen ist jedoch mit DMX einfacher.</span><span class="sxs-lookup"><span data-stu-id="c0d1a-103">You can query the mining model content programmatically by using AMO or XML/A, but it is easier to create queries by using DMX.</span></span> <span data-ttu-id="c0d1a-104">Sie können auch Abfragen für die Data Mining-Schemarowsets erstellen, indem Sie eine Verbindung zur [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz herstellen und mit den von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]bereitgestellten DMVs eine Abfrage erstellen.</span><span class="sxs-lookup"><span data-stu-id="c0d1a-104">You can also create queries against the data mining schema rowsets by establishing a connection to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and creating a query using the DMVs provided by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c0d1a-105">Die folgenden Vorgehensweisen zeigen, wie Abfragen für ein Miningmodell mit DMX erstellt und wie Data Mining-Schemarowsets abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="c0d1a-105">The following procedures demonstrate how to create queries against a mining model by using DMX, and how to query the data mining schema rowsets.</span></span>  
  
 <span data-ttu-id="c0d1a-106">Ein Beispiel zum Erstellen einer ähnlichen Abfrage mit XML/A finden Sie unter [Erstellen einer Data Mining-Abfrage mit XMLA](create-a-data-mining-query-by-using-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="c0d1a-106">For an example of how to create a similar query by using XML/A, see [Create a Data Mining Query by Using XMLA](create-a-data-mining-query-by-using-xmla.md).</span></span>  
  
## <a name="querying-data-mining-model-content-by-using-dmx"></a><span data-ttu-id="c0d1a-107">Abfragen von Data Mining-Modellinhalt mit DMX</span><span class="sxs-lookup"><span data-stu-id="c0d1a-107">Querying Data Mining Model Content by Using DMX</span></span>  
  
#### <a name="to-create-a-dmx-model-content-query"></a><span data-ttu-id="c0d1a-108">So erstellen Sie eine DMX-Modellinhaltsabfrage</span><span class="sxs-lookup"><span data-stu-id="c0d1a-108">To create a DMX model content query</span></span>  
  
1.  <span data-ttu-id="c0d1a-109">Klicken Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]im Menü **Ansicht** auf **Vorlagen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="c0d1a-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="c0d1a-110">Klicken Sie im Bereich **Vorlagen-Explorer** auf das Cubesymbol, um die Liste zu ändern und Analysis Services-Vorlagen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c0d1a-110">In the **Template Explorer** pane, click the cube icon to change the list and display Analysis Services templates.</span></span>  
  
3.  <span data-ttu-id="c0d1a-111">Erweitern Sie in der Liste von Vorlagenkategorien **DMX**, erweitern Sie **Modellinhalt**, und doppelklicken Sie auf **Inhaltsabfrage**.</span><span class="sxs-lookup"><span data-stu-id="c0d1a-111">In the list of template categories, expand **DMX**, expand **Model Content**, and double-click **Content Query**.</span></span>  
  
4.  <span data-ttu-id="c0d1a-112">Wählen Sie im Dialogfeld **Verbindung mit Analysis Services herstellen** die Instanz aus, die das Miningmodell enthält, das Sie abfragen möchten, und klicken Sie auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="c0d1a-112">In the **Connect to Analysis Services** dialog box, select the instance that contains the mining model you want to query, and click **Connect**.</span></span>  
  
     <span data-ttu-id="c0d1a-113">Die Vorlage **Inhaltsabfrage** wird im entsprechenden Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c0d1a-113">The **Content Query** template opens in the appropriate code editor.</span></span> <span data-ttu-id="c0d1a-114">Der Metadatenbereich listet die Modelle auf, die in der aktuellen Datenbank verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c0d1a-114">The metadata pane lists the models that are available in the current database.</span></span> <span data-ttu-id="c0d1a-115">Um die Datenbank zu ändern, wählen Sie eine andere Datenbank aus der Liste **Verfügbare Datenbanken** aus.</span><span class="sxs-lookup"><span data-stu-id="c0d1a-115">To change the database, select a different database from the **Available Databases** list.</span></span>  
  
5.  <span data-ttu-id="c0d1a-116">Geben Sie den Namen eines Mining Modells in die Zeile `FROM` [ *\<mining model, name, MyModel>* ] ein `.CONTENT` .</span><span class="sxs-lookup"><span data-stu-id="c0d1a-116">Enter the name of a mining model in the line, `FROM` [*\<mining model, name, MyModel>*]`.CONTENT`.</span></span> <span data-ttu-id="c0d1a-117">Wenn der Name des Miningmodells Leerzeichen enthält, muss der Name in Klammern eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="c0d1a-117">If the mining model name contains spaces, you must enclose the name in brackets.</span></span>  
  
     <span data-ttu-id="c0d1a-118">Wenn Sie den Namen nicht eingeben möchten, können Sie ein Miningmodell im **Objekt-Explorer** auswählen und in die Vorlage ziehen.</span><span class="sxs-lookup"><span data-stu-id="c0d1a-118">If you don't want to type the name, you can select a mining model in **Object Explorer** and drag it into the template.</span></span>  
  
6.  <span data-ttu-id="c0d1a-119">Geben Sie in der Zeile `SELECT` *\<select list, expr list, \*>* die Namen der Spalten im Schemarowset des Mining Modell Inhalts ein.</span><span class="sxs-lookup"><span data-stu-id="c0d1a-119">In the line, `SELECT`*\<select list, expr list, \*>*, type the names of columns in the mining model content schema rowset.</span></span>  
  
     <span data-ttu-id="c0d1a-120">Eine Liste von Spalten, die Sie in Miningmodellinhaltsabfragen zurückgeben können, finden Sie unter [Miningmodellinhalt &#40;Analysis Services – Data Mining&#41;](mining-model-content-analysis-services-data-mining.md)bereitgestellten DMVs eine Abfrage erstellen.</span><span class="sxs-lookup"><span data-stu-id="c0d1a-120">To view a list of columns that you can return in mining model content queries, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
7.  <span data-ttu-id="c0d1a-121">Geben Sie wahlweise eine Bedingung in der WHERE-Klausel der Vorlage ein, um die zurückgegebenen Zeilen auf bestimmte Knoten oder Werte zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="c0d1a-121">Optionally, type a condition in the WHERE clause of the template to restrict the rows returned to specific nodes or values.</span></span>  
  
8.  <span data-ttu-id="c0d1a-122">Klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c0d1a-122">Click **Execute**.</span></span>  
  
## <a name="querying-the-data-mining-schema-rowsets"></a><span data-ttu-id="c0d1a-123">Abfragen der Data Mining-Schemarowsets</span><span class="sxs-lookup"><span data-stu-id="c0d1a-123">Querying the Data Mining Schema Rowsets</span></span>  
  
#### <a name="to-create-a-query-against-the-data-mining-schema-rowset"></a><span data-ttu-id="c0d1a-124">So erstellen Sie eine Abfrage für das Data Mining-Schemarowset</span><span class="sxs-lookup"><span data-stu-id="c0d1a-124">To create a query against the data mining schema rowset</span></span>  
  
1.  <span data-ttu-id="c0d1a-125">Klicken Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]auf der Symbolleiste **Neue Abfrage** auf **DMX-Abfrage für Analysis Services**oder **MDX-Abfrage für Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="c0d1a-125">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **New Query** toolbar, click **Analysis Services DMX Query**, or **Analysis Services MDX query**.</span></span>  
  
2.  <span data-ttu-id="c0d1a-126">Wählen Sie im Dialogfeld **Verbindung mit Analysis Services herstellen** die Instanz aus, die die Objekte enthält, die Sie abfragen möchten, und klicken Sie auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="c0d1a-126">In the **Connect to Analysis Services** dialog box, select the instance that contains the objects you want to query, and click **Connect**.</span></span>  
  
     <span data-ttu-id="c0d1a-127">Die Vorlage **Inhaltsabfrage** wird im entsprechenden Code-Editor geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c0d1a-127">The **Content Query** template opens in the appropriate code editor.</span></span> <span data-ttu-id="c0d1a-128">Der Metadatenbereich listet die Objekte auf, die in der aktuellen Datenbank verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c0d1a-128">The metadata pane lists the objects that are available in the current database.</span></span> <span data-ttu-id="c0d1a-129">Um die Datenbank zu ändern, wählen Sie eine andere Datenbank aus der Liste **Verfügbare Datenbanken** aus.</span><span class="sxs-lookup"><span data-stu-id="c0d1a-129">To change the database, select a different database from the **Available Databases** list.</span></span>  
  
3.  <span data-ttu-id="c0d1a-130">Geben Sie im Abfrage-Editor Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="c0d1a-130">In the query editor, type the following:</span></span>  
  
     `SELECT *`  
  
     `FROM $system.DMSCHEMA_MINING_MODEL_CONTENT`  
  
     `WHERE MODEL_NAME = '<model name>'`  
  
4.  <span data-ttu-id="c0d1a-131">Klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c0d1a-131">Click **Execute**.</span></span>  
  
     <span data-ttu-id="c0d1a-132">Im Ergebnisbereich wird der Inhalt des Modells angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c0d1a-132">The Results pane displays the contents of the model.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c0d1a-133">Um eine Liste aller Schemarowsets anzuzeigen, die Sie für die aktuelle Instanz abfragen können, verwenden Sie die folgende Abfrage: `SELECT * FROM $system.`DISCOVER_SCHEMA_ROWSETS.</span><span class="sxs-lookup"><span data-stu-id="c0d1a-133">To view a list of all the schema rowsets that you can query on the current instance, use this query: `SELECT * FROM $system.`DISCOVER_SCHEMA_ROWSETS.</span></span> <span data-ttu-id="c0d1a-134">Eine Liste der für Data Mining spezifischen Schemarowsets finden Sie unter [Data Mining Schema Rowsets](../../relational-databases/native-client-ole-db-rowsets/rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="c0d1a-134">Or, for a list of schema rowsets specific to data mining, see [Data Mining Schema Rowsets](../../relational-databases/native-client-ole-db-rowsets/rowsets.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0d1a-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c0d1a-135">See Also</span></span>  
 <span data-ttu-id="c0d1a-136">[Mining Modell Inhalt &#40;Analysis Services Data Mining-&#41;](mining-model-content-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="c0d1a-136">[Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="c0d1a-137">Data Mining Schema Rowsets</span><span class="sxs-lookup"><span data-stu-id="c0d1a-137">Data Mining Schema Rowsets</span></span>](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/data-mining-schema-rowsets) 
  
  
