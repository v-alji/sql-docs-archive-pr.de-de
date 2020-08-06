---
title: Abfragen der Parameter, mit denen ein Mining Modell erstellt wurde | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content queries [DMX]
ms.assetid: ce7719e0-6127-4d9c-a753-0e0a3db065e1
author: minewiskan
ms.author: owend
ms.openlocfilehash: a3802a0d70579f613accbe6abd310da909751b23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717026"
---
# <a name="query-the-parameters-used-to-create-a-mining-model"></a><span data-ttu-id="7d9fe-102">Abfragen der Parameter, mit denen ein Miningmodell erstellt wird</span><span class="sxs-lookup"><span data-stu-id="7d9fe-102">Query the Parameters Used to Create a Mining Model</span></span>
  <span data-ttu-id="7d9fe-103">Die Zusammensetzung eines Miningmodells wird nicht nur von den Trainingsfällen beeinflusst, sondern auch von den Parametern, die bei der Erstellung des Modells festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="7d9fe-103">The composition of a mining model is affected not only by the training cases, but by the parameters that were set when the model was created.</span></span> <span data-ttu-id="7d9fe-104">Daher ist es unter Umständen hilfreich, die Parametereinstellungen eines vorhandenen Modells abzurufen, um das Verhalten des Modells besser zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="7d9fe-104">Therefore, you might find it useful to retrieve the parameter settings of an existing model to better understand the behavior of the model.</span></span> <span data-ttu-id="7d9fe-105">Das Abrufen der Parameter ist auch beim Dokumentieren einer bestimmten Version dieses Modells nützlich.</span><span class="sxs-lookup"><span data-stu-id="7d9fe-105">Retrieving parameters is also useful when documenting a particular version of that model.</span></span>  
  
 <span data-ttu-id="7d9fe-106">Um die Parameter zu finden, die bei der Erstellung des Modells verwendet wurden, erstellen Sie eine Abfrage für eines der Miningmodell-Schemarowsets.</span><span class="sxs-lookup"><span data-stu-id="7d9fe-106">To find the parameters that were used when the model was created, you create a query against one of the mining model schema rowsets.</span></span> <span data-ttu-id="7d9fe-107">In [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)]werden diese Schemarowsets als Gruppe von Systemsichten verfügbar gemacht, die einfach mit der Transact-SQL-Syntax abgefragt werden können.</span><span class="sxs-lookup"><span data-stu-id="7d9fe-107">In [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)], these schema rowsets are exposed as a set of system views that you can query easily by using Transact-SQL syntax.</span></span> <span data-ttu-id="7d9fe-108">In diesem Verfahren wird beschrieben, wie Sie eine Abfrage erstellen, die die Parameter zurückgibt, mit denen das angegebene Miningmodell erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7d9fe-108">This procedure describes how to create a query that returns the parameters that were used to create the specified mining model.</span></span>  
  
### <a name="to-open-a-query-window-for-a-schema-rowset-query"></a><span data-ttu-id="7d9fe-109">So öffnen Sie ein Abfragefenster für eine Schemarowsetabfrage</span><span class="sxs-lookup"><span data-stu-id="7d9fe-109">To open a Query window for a schema rowset query</span></span>  
  
1.  <span data-ttu-id="7d9fe-110">Öffnen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]die [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz, die das abzufragende Modell enthält.</span><span class="sxs-lookup"><span data-stu-id="7d9fe-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the model you want to query.</span></span>  
  
2.  <span data-ttu-id="7d9fe-111">Klicken Sie mit der rechten Maustaste auf den Instanznamen, wählen Sie **Neue Abfrage**und anschließend **DMX**aus.</span><span class="sxs-lookup"><span data-stu-id="7d9fe-111">Right-click the instance name, select **New Query**, and then select **DMX**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7d9fe-112"> Sie können auch mit der **MDX** -Vorlage eine Abfrage für ein Data Mining-Modell erstellen.</span><span class="sxs-lookup"><span data-stu-id="7d9fe-112">You can also create a query against a data mining model by using the **MDX** template.</span></span>  
  
3.  <span data-ttu-id="7d9fe-113">Wenn die Instanz mehrere Datenbanken enthält, wählen Sie aus der Liste **Verfügbare Datenbanken** in der Symbolleiste die Datenbank mit dem Modell aus, das Sie abfragen möchten.</span><span class="sxs-lookup"><span data-stu-id="7d9fe-113">If the instance contains multiple databases, select the database that contains the model you want to query from the **Available Databases** list in the toolbar.</span></span>  
  
### <a name="to-return-model-parameters-for-an-existing-mining-model"></a><span data-ttu-id="7d9fe-114">So geben Sie Modellparameter für ein vorhandenes Miningmodell zurück</span><span class="sxs-lookup"><span data-stu-id="7d9fe-114">To return model parameters for an existing mining model</span></span>  
  
1.  <span data-ttu-id="7d9fe-115">Geben oder fügen Sie im DMX-Abfragefenster den folgenden Text ein:</span><span class="sxs-lookup"><span data-stu-id="7d9fe-115">In the DMX query pane, type or paste the following text:</span></span>  
  
    ```  
    SELECT MINING_PARAMETERS  
    FROM $system.DMSCHEMA_MINING_MODELS  
    WHERE MODEL_NAME = ''  
    ```  
  
2.  <span data-ttu-id="7d9fe-116">Wählen Sie im Objekt-Explorer das gewünschte Miningmodell aus, und ziehen Sie es in das DMX-Abfragefenster zwischen die einfachen Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="7d9fe-116">In Object Explorer, select the mining model you want, and then drag it into the DMX Query pane, between the single quotation marks.</span></span>  
  
3.  <span data-ttu-id="7d9fe-117">Drücken Sie F5, oder klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7d9fe-117">Press F5, or click **Execute**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d9fe-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d9fe-118">Example</span></span>  
 <span data-ttu-id="7d9fe-119">Der folgende Code gibt eine Liste der Parameter zurück, mit denen das Miningmodell im [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md)erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7d9fe-119">The following code returns a list of the parameters that were used to create the mining model that you build in the [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md).</span></span> <span data-ttu-id="7d9fe-120">Diese Parameter umfassen die expliziten Werte für Standardwerte, die von den Miningdiensten verwendet werden, die von Anbietern auf dem Server bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="7d9fe-120">These parameters include the explicit values for any defaults used by the mining services available from providers on the server.</span></span>  
  
```  
SELECT MINING_PARAMETERS   
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'TM Clustering'  
```  
  
 <span data-ttu-id="7d9fe-121">Im Codebeispiel werden die folgenden Parameter für das Clustermodell zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="7d9fe-121">The code example returns the following parameters for the clustering model:</span></span>  
  
 <span data-ttu-id="7d9fe-122">eExample-Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="7d9fe-122">eExample Results:</span></span>  
  
 <span data-ttu-id="7d9fe-123">MINING_PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7d9fe-123">MINING_PARAMETERS</span></span>  
  
 <span data-ttu-id="7d9fe-124">CLUSTER_COUNT=10, CLUSTER_SEED=0, CLUSTERING_METHOD=1, MAXIMUM_INPUT_ATTRIBUTES=255, MAXIMUM_STATES=100, MINIMUM_SUPPORT=1, MODELLING_CARDINALITY=10, SAMPLE_SIZE=50000, STOPPING_TOLERANCE=10</span><span class="sxs-lookup"><span data-stu-id="7d9fe-124">CLUSTER_COUNT=10,CLUSTER_SEED=0,CLUSTERING_METHOD=1,MAXIMUM_INPUT_ATTRIBUTES=255,MAXIMUM_STATES=100,MINIMUM_SUPPORT=1,MODELLING_CARDINALITY=10,SAMPLE_SIZE=50000,STOPPING_TOLERANCE=10</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d9fe-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7d9fe-125">See Also</span></span>  
 <span data-ttu-id="7d9fe-126">[Data Mining-Abfrage Tasks und Anleitungen](data-mining-query-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="7d9fe-126">[Data Mining Query Tasks and How-tos](data-mining-query-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="7d9fe-127">Data Mining-Abfragen</span><span class="sxs-lookup"><span data-stu-id="7d9fe-127">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
