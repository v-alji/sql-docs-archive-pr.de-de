---
title: Erweiterte Modellierung (Data Mining-Add-Ins für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures, creating
ms.assetid: 042270a3-6ec7-4b52-b2ba-2adb6c4740d5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 771eb6111765b558995ee3b0eb98196c63951567
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615237"
---
# <a name="advanced-modeling-data-mining-add-ins-for-excel"></a><span data-ttu-id="1e59e-102">Erweiterte Modellierung (Data Mining-Add-Ins für Excel)</span><span class="sxs-lookup"><span data-stu-id="1e59e-102">Advanced Modeling (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="1e59e-103">Mithilfe der **erweiterten** Optionen für die Datenmodellierung können Sie benutzerdefinierte Data Mining Strukturen und Modelle mit Parametern erstellen, die sich von den von den Assistenten erstellten Parametern unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="1e59e-103">You can use the **Advanced** data modeling options to create custom data mining structures and models with parameters different from those created by the wizards.</span></span> <span data-ttu-id="1e59e-104">Mit den beiden in diesem Abschnitt beschriebenen Assistenten können Sie eine völlig neue Data Mining-Struktur und ein neues Miningmodell erstellen, das auf eine vorhandene Data Mining-Struktur angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="1e59e-104">The two wizards described in this section help you create a completely new data mining structure, and a new mining model to apply to an existing data mining structure.</span></span>  
  
## <a name="create-mining-structure"></a><span data-ttu-id="1e59e-105">Erstellen einer Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="1e59e-105">Create Mining Structure</span></span>  
 <span data-ttu-id="1e59e-106">![Miningstruktur erstellen (Schaltfläche auf Data Mining-Menüband)](media/dmc-createstruct.gif "Miningstruktur erstellen (Schaltfläche auf Data Mining-Menüband)")</span><span class="sxs-lookup"><span data-stu-id="1e59e-106">![Create Mining Structure button, Data Mining ribbon](media/dmc-createstruct.gif "Create Mining Structure button, Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="1e59e-107">Der **Assistent zum Erstellen von Mining Strukturen** unterstützt Sie beim Erstellen einer neuen Data Mining Struktur.</span><span class="sxs-lookup"><span data-stu-id="1e59e-107">The **Create Mining Structure Wizard** helps you build a new data mining structure.</span></span> <span data-ttu-id="1e59e-108">Eine Struktur ist eine Sammlung von Daten, die aus einer bestimmten Datenquelle extrahiert wurden.</span><span class="sxs-lookup"><span data-stu-id="1e59e-108">A structure is a collection of data extracted from a specified data source.</span></span>  <span data-ttu-id="1e59e-109">Eine Miningstruktur kann anhand neuer Daten aus der Quelle aktualisiert werden; beim Erstellen der Miningstruktur definieren Sie jedoch Datentypen und Namen, die festlegen, wie die Daten zu Analysezwecken verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1e59e-109">A mining structure can be updated with new data at the source, but when you create the mining structure, you define data types and names that define how the data is used for analysis.</span></span>  
  
 <span data-ttu-id="1e59e-110">Zum Erstellen der Struktur können Sie die folgenden Datenquellen verwenden: eine Excel-Tabelle, einen Excel-Bereich oder Daten aus einer externen Datenquelle, die bereits als [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Datenquellensicht definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="1e59e-110">You can use the following data sources to build your structure: an Excel table, an Excel range, or any data in an external data source that has already been defined as an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source view.</span></span>  
  
 <span data-ttu-id="1e59e-111">Für jede Struktur können Sie einige Daten bestimmen, die zum Testen und Überprüfen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1e59e-111">For each structure, you have the option of setting aside some of the data to use for testing and validation.</span></span> <span data-ttu-id="1e59e-112">Wenn Sie dieses Dataset für zurück *gehaltene Daten erstellen* , wenn Sie Ihre Datenquellen einrichten, können Sie sicherstellen, dass alle Modelle, die auf der Struktur basieren, ein konsistentes DataSet zum Testen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="1e59e-112">By creating this *holdout data set* when you set up your data sources, you can ensure that all models that are based on the structure are able to use a consistent data set for testing.</span></span>  
  
 <span data-ttu-id="1e59e-113">Nachdem Sie eine Miningstruktur erstellt haben, können Sie mehrere Modelle hinzufügen, um verschiedene Analysemethoden anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="1e59e-113">After you have created a mining structure, you can add multiple models to apply different methods of analysis.</span></span>  
  
 <span data-ttu-id="1e59e-114">Weitere Informationen zur Verwendung des **Assistenten zum Erstellen von Mining Strukturen**finden Sie unter [Erstellen einer Mining Struktur &#40;SQL Server Data Mining-Add-ins&#41;](create-mining-structure-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="1e59e-114">For more information about how to use the **Create Mining Structure Wizard**, see [Create Mining Structure &#40;SQL Server Data Mining Add-ins&#41;](create-mining-structure-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="add-model-to-structure"></a><span data-ttu-id="1e59e-115">Hinzufügen eines Modells zu einer Struktur</span><span class="sxs-lookup"><span data-stu-id="1e59e-115">Add Model to Structure</span></span>  
 <span data-ttu-id="1e59e-116">![Schaltfläche "Modell einer Struktur hinzufügen"](media/dmc-addmodel.gif "Schaltfläche "Modell einer Struktur hinzufügen"")</span><span class="sxs-lookup"><span data-stu-id="1e59e-116">![Add Model to Structure button](media/dmc-addmodel.gif "Add Model to Structure button")</span></span>  
  
 <span data-ttu-id="1e59e-117">Wenn Sie einer Struktur ein neues Modell hinzufügen, analysieren Sie die Daten mithilfe eines anderen Algorithmus oder mit anderen Parametern.</span><span class="sxs-lookup"><span data-stu-id="1e59e-117">When you add a new model to a structure, you analyze the data by using a different algorithm, or with different parameters.</span></span> <span data-ttu-id="1e59e-118">Diese Option ist insbesondere dann hilfreich, wenn Sie ein Modell mithilfe eines der Algorithmen erstellen möchten, die nicht über Tools des Data Mining-Clients verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="1e59e-118">This option is particularly useful if you want to create a model using one of the algorithms not exposed in the Data Mining Client tools.</span></span>  
  
 <span data-ttu-id="1e59e-119">Beispielsweise können Sie einen beliebigen, von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]unterstützten Algorithmus verwenden, z. B.:</span><span class="sxs-lookup"><span data-stu-id="1e59e-119">For example, you can use any of the algorithms supported by [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], such as:</span></span>  
  
-   <span data-ttu-id="1e59e-120">Lineare Regression</span><span class="sxs-lookup"><span data-stu-id="1e59e-120">Linear regression</span></span>  
  
-   <span data-ttu-id="1e59e-121">Sequenzclustering</span><span class="sxs-lookup"><span data-stu-id="1e59e-121">Sequence clustering</span></span>  
  
-   <span data-ttu-id="1e59e-122">Zuordnungsanalyse für geschachtelte Datasets</span><span class="sxs-lookup"><span data-stu-id="1e59e-122">Association analysis on nested data sets</span></span>  
  
 <span data-ttu-id="1e59e-123">Um zu sehen, welche Art von Mining Strukturen verfügbar ist, können Sie die in gespeicherten Modelle und Strukturen durchsuchen, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] indem Sie entweder auf **Modelle verwalten** oder auf **Durchsuchen**klicken.</span><span class="sxs-lookup"><span data-stu-id="1e59e-123">To see what kind of mining structures are available, you can browse the models and structures stored in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] by clicking either **Manage Models** or **Browse**.</span></span>  
  
 <span data-ttu-id="1e59e-124">Dabei sind Sie auf die Data Mining-Strukturen beschränkt, die während der aktuellen Sitzung erstellt wurden, bzw. die Miningstrukturen, die in einer Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="1e59e-124">You are limited to data mining structures that were created during the current session, or mining structures that were saved to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="1e59e-125">Weitere Informationen finden Sie unter [Hinzufügen eines Modells zu einer Struktur &#40;Data Mining-Add-Ins für Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="1e59e-125">For more information, see [Add Model to Structure &#40;Data Mining Add-ins for Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e59e-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1e59e-126">See Also</span></span>  
 <span data-ttu-id="1e59e-127">[Verwalten von Modellen &#40;SQL Server Data Mining-Add-ins&#41;](manage-models-sql-server-data-mining-add-ins.md) </span><span class="sxs-lookup"><span data-stu-id="1e59e-127">[Manage Models &#40;SQL Server Data Mining Add-ins&#41;](manage-models-sql-server-data-mining-add-ins.md) </span></span>  
 [<span data-ttu-id="1e59e-128">Durchsuchen von Modellen in Excel &#40;SQL Server Data Mining-Add-ins&#41;</span><span class="sxs-lookup"><span data-stu-id="1e59e-128">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
