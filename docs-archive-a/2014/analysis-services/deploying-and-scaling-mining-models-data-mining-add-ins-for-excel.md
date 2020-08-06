---
title: Bereitstellen und Skalieren von Mining Modellen (Data Mining-Add-Ins für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- manage
ms.assetid: 4c617375-6b01-4a71-9680-de0cbf2cff05
author: minewiskan
ms.author: owend
ms.openlocfilehash: dd2839144d4d1667da09830aaabd1ec3f17a9c21
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620049"
---
# <a name="deploying-and-scaling-mining-models-data-mining-add-ins-for-excel"></a><span data-ttu-id="5c514-102">Bereitstellen und Skalieren von Miningmodellen (Data Mining-Add-Ins für Excel)</span><span class="sxs-lookup"><span data-stu-id="5c514-102">Deploying and Scaling Mining Models (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="5c514-103">Die Tools in der Gruppe **Modell Verwendung** und- **Verwaltung** werden bereitgestellt, um Sie beim Verwalten und Durchsuchen vorhandener Mining Modelle zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="5c514-103">The tools in the **Model Usage** and **Management** group are provided to help you manage and browse existing mining models.</span></span> <span data-ttu-id="5c514-104">Mithilfe der Tools können alle auf einer Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] gespeicherten Modelle angezeigt werden, nicht nur die mit den Add-Ins erstellten Modelle.</span><span class="sxs-lookup"><span data-stu-id="5c514-104">You can use these tools to view any models that are stored on an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], not just those created using the add-ins.</span></span>  
  
 <span data-ttu-id="5c514-105">Wenn Sie über die erforderlichen Berechtigungen verfügen, können Sie vorhandene Miningmodelle und -strukturen löschen, ändern, umbenennen oder verarbeiten, ohne dazu Excel verlassen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="5c514-105">If you have the necessary permissions, you can delete, modify, rename, or process existing mining models and structures without leaving Excel.</span></span>  
  
## <a name="model-usage-toolbar"></a><span data-ttu-id="5c514-106">Symbolleiste "Modellverwendung"</span><span class="sxs-lookup"><span data-stu-id="5c514-106">Model Usage Toolbar</span></span>  
  
### <a name="browse"></a><span data-ttu-id="5c514-107">Durchsuchen</span><span class="sxs-lookup"><span data-stu-id="5c514-107">Browse</span></span>  
 <span data-ttu-id="5c514-108">Verwenden Sie den Assistenten zum **Durchsuchen** , um ein vorhandenes Data Mining Modell auszuwählen und dann das Modell in einem Viewer anzuzeigen und zu durchsuchen, der mehrere Diagramme und Tools enthält.</span><span class="sxs-lookup"><span data-stu-id="5c514-108">Use the **Browse** wizard to select an existing data mining model, and then view and explore the model in a viewer that contains multiple graphs and tools.</span></span>  
  
 <span data-ttu-id="5c514-109">Weitere Informationen finden Sie unter durch [Suchen von Modellen in Excel &#40;SQL Server Data Mining-Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="5c514-109">For more information, see [Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span></span>  
  
### <a name="document-model"></a><span data-ttu-id="5c514-110">Dokumentmodell</span><span class="sxs-lookup"><span data-stu-id="5c514-110">Document Model</span></span>  
 <span data-ttu-id="5c514-111">Klicken Sie auf **Dokument Modell** , um einen Assistenten zu starten, der einen Bericht mit den von Ihnen erstellten Mining Strukturen und Mining Modellen erstellt.</span><span class="sxs-lookup"><span data-stu-id="5c514-111">Click **Document Model** to start a wizard that creates a report of the mining structures and mining models that you have created.</span></span> <span data-ttu-id="5c514-112">Sie können Basisberichte oder erweiterte Berichte erstellen.</span><span class="sxs-lookup"><span data-stu-id="5c514-112">You can create basic or advanced reports.</span></span> <span data-ttu-id="5c514-113">Die Berichte umfassen Spalten- und Modellmetadaten, die beim Dokumentieren der Arbeitsschritte und Nachverfolgen von Modelländerungen hilfreich sind.</span><span class="sxs-lookup"><span data-stu-id="5c514-113">The reports include column and model metadata, so are useful for documenting your work and tracking changes in models.</span></span>  
  
 <span data-ttu-id="5c514-114">Weitere Informationen finden Sie unter [Dokumentieren von Mining Modellen &#40;Data Mining-Add-Ins für Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="5c514-114">For more information, see [Documenting Mining Models &#40;Data Mining Add-ins for Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md).</span></span>  
  
### <a name="query"></a><span data-ttu-id="5c514-115">Abfrage</span><span class="sxs-lookup"><span data-stu-id="5c514-115">Query</span></span>  
 <span data-ttu-id="5c514-116">Klicken Sie zum Starten des **Abfrage** -Assistenten auf **Abfrage** .</span><span class="sxs-lookup"><span data-stu-id="5c514-116">Click **Query** to start the **Query** wizard.</span></span> <span data-ttu-id="5c514-117">Im Assistenten werden Sie interaktiv durch das Verfahren zur Erstellung einer Vorhersageabfrage für ein vorhandenes Data Mining-Modell geführt.</span><span class="sxs-lookup"><span data-stu-id="5c514-117">The wizard interactively walks you through the process of creating a prediction query against an existing data mining model.</span></span>  
  
 <span data-ttu-id="5c514-118">Zum weiteren Anpassen der Abfrage oder zum Erstellen von Abfragen, die nicht im Assistenten enthalten sind, klicken Sie einfach auf die Schaltfläche **erweitert** , um die **Data Mining-Abfrage Erweiterter Editor**zu starten.</span><span class="sxs-lookup"><span data-stu-id="5c514-118">To further customize the query, or build queries not included in the wizard, just click the **Advanced** button to start the **Data Mining Query Advanced Editor**.</span></span>  
  
 <span data-ttu-id="5c514-119">Weitere Informationen finden Sie unter [Abfrage &#40;SQL Server Data Mining-Add-ins&#41;](query-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="5c514-119">For more information, see [Query &#40;SQL Server Data Mining Add-ins&#41;](query-sql-server-data-mining-add-ins.md).</span></span>  
  
### <a name="data-mining-advanced-query-editor"></a><span data-ttu-id="5c514-120">Erweiterter Data Mining-Abfrage-Editor</span><span class="sxs-lookup"><span data-stu-id="5c514-120">Data Mining Advanced Query Editor</span></span>  
 <span data-ttu-id="5c514-121">In diesem Editor können Sie mithilfe von DMX-Vorlagen (Data Mining Extensions, Data Mining-Erweiterungen) schnell eine Abfrage erstellen und anschließend Eingaben, Ausgaben, Algorithmen und Parameter ändern, um benutzerdefinierte Miningmodelle, Miningstrukturen oder Vorhersageabfragen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5c514-121">In this editor, you can use Data Mining Extensions (DMX) templates to jumpstart a query, and then modify the inputs, outputs, algorithms, and parameters to create a custom mining model, mining structure, or prediction query.</span></span>  
  
 <span data-ttu-id="5c514-122">Weitere Informationen finden Sie unter Erweiterter [Data Mining-Abfrage-Editor](advanced-data-mining-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="5c514-122">For more information, see [Advanced Data Mining Query Editor](advanced-data-mining-query-editor.md).</span></span>  
  
## <a name="management"></a><span data-ttu-id="5c514-123">Verwaltung</span><span class="sxs-lookup"><span data-stu-id="5c514-123">Management</span></span>  
 <span data-ttu-id="5c514-124">Verwenden Sie den Assistenten zum **Verwalten von Modellen** , um vorhandene Modelle auf der aktuellen Verbindung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5c514-124">Use the **Manage Models** wizard to view existing models on the current connection.</span></span> <span data-ttu-id="5c514-125">Sie können Miningmodelle und -strukturen auch löschen, umbenennen, verarbeiten oder importieren und exportieren.</span><span class="sxs-lookup"><span data-stu-id="5c514-125">You can also delete, rename, process, or import and export mining models and structures.</span></span>  
  
 <span data-ttu-id="5c514-126">Weitere Informationen finden Sie unter [Verwalten von Modellen &#40;SQL Server Data Mining-Add-ins&#41;](manage-models-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="5c514-126">For more information, see [Manage Models &#40;SQL Server Data Mining Add-ins&#41;](manage-models-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c514-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5c514-127">See Also</span></span>  
 <span data-ttu-id="5c514-128">[Erstellen eines Data Mining-Modells](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="5c514-128">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 [<span data-ttu-id="5c514-129">Validieren von Modellen und Verwenden von Modellen für Vorhersage &#40;Data Mining-Add-Ins für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="5c514-129">Validating Models and Using Models for Prediction &#40;Data Mining Add-ins for Excel&#41;</span></span>](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md)  
  
  
