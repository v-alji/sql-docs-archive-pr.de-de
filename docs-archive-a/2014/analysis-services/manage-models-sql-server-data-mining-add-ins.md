---
title: Verwalten von Modellen (SQL Server Data Mining-Add-Ins) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, importing
- mining models, deleting
- mining models, managing
- mining models, training
- mining models, processing
- mining models, exporting
ms.assetid: c11380f0-7c24-4668-9cdf-9c53e4aff665
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5f4b5961ec79bb949bf7fa5f53a980f066e81379
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620632"
---
# <a name="manage-models-sql-server-data-mining-add-ins"></a><span data-ttu-id="8875a-102">Modelle verwalten (SQL Server Data Mining-Add-Ins)</span><span class="sxs-lookup"><span data-stu-id="8875a-102">Manage Models (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="8875a-103">![Modelle verwalten (Schaltfläche auf Data Mining-Menüband)](media/dmc-manage.gif "Modelle verwalten (Schaltfläche auf Data Mining-Menüband)")</span><span class="sxs-lookup"><span data-stu-id="8875a-103">![Manage Models button, Data Mining ribbon](media/dmc-manage.gif "Manage Models button, Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="8875a-104">Im Dialogfeld **Modelle verwalten** können Sie mit vorhandenen Mining Modellen und Mining Strukturen interagieren, die auf dem Server gespeichert sind, mit [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] dem Sie derzeit verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="8875a-104">The **Manage Models** dialog box enables you to interact with existing mining models and mining structures that are stored in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server to which you are currently connected.</span></span> <span data-ttu-id="8875a-105">Sie können auch temporäre Strukturen und Modelle anzeigen und verwalten, die während der aktuellen Sitzung erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="8875a-105">You can also view and manage temporary structures and models that have been created during the current session.</span></span> <span data-ttu-id="8875a-106">In diesem Dialogfeld werden sowohl Modelle angezeigt, die während der aktuellen Sitzung erstellt wurden, als auch Modelle, die auf dem Server gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="8875a-106">If you have used both session models and models stored on a server, both are visible in the dialog box.</span></span>  
  
## <a name="using-the-manage-models-wizard"></a><span data-ttu-id="8875a-107">Verwenden des Assistenten zum Verwalten von Modellen</span><span class="sxs-lookup"><span data-stu-id="8875a-107">Using the Manage Models Wizard</span></span>  
 <span data-ttu-id="8875a-108">Wenn Sie auf **Modelle verwalten**klicken, wird das Dialogfeld **Mining Strukturen und Modelle verwalten** geöffnet, in dem der Zugriff auf die folgenden Funktionen zum Verwalten vorhandener Data Mining Modelle und Strukturen bereitgestellt wird:</span><span class="sxs-lookup"><span data-stu-id="8875a-108">When you click **Manage Models**, the **Manage Mining Structures and Models** dialog box opens, providing access to the following functionality for managing existing data mining models and structures:</span></span>  
  
-   <span data-ttu-id="8875a-109">Umbenennen eines Miningmodells oder einer Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="8875a-109">Rename a mining model or structure</span></span>  
  
-   <span data-ttu-id="8875a-110">Löschen eines Miningmodells oder einer Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="8875a-110">Delete a mining model or structure</span></span>  
  
-   <span data-ttu-id="8875a-111">Entfernen eines Miningmodells oder einer Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="8875a-111">Clear a mining model or structure</span></span>  
  
-   <span data-ttu-id="8875a-112">Verarbeiten einer Miningstruktur mithilfe von neuen oder bereits vorhandenen Daten</span><span class="sxs-lookup"><span data-stu-id="8875a-112">Process a mining structure, using either new or existing data</span></span>  
  
-   <span data-ttu-id="8875a-113">Exportieren oder Importieren eines Miningmodells oder einer Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="8875a-113">Export or import a mining model or structure</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8875a-114">In diesem Dialogfeld können Sie keine Abfragen oder Modelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="8875a-114">You cannot create queries or models by using this dialog box.</span></span> <span data-ttu-id="8875a-115">Verwenden Sie zum Erstellen einer neuen Mining Struktur einen der im Data Mining-Client für Excel bereitgestellten Assistenten, oder verwenden Sie die **Data Mining-Abfrage Erweiterter Editor**.</span><span class="sxs-lookup"><span data-stu-id="8875a-115">To create a new mining structure, use one of the wizards provided in the Data Mining Client for Excel, or use the **Data Mining Query Advanced Editor**.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="8875a-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8875a-116">Requirements</span></span>  
 <span data-ttu-id="8875a-117">Sie müssen zunächst eine Verbindung mit einer Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] herstellen, um Data Mining-Modelle zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="8875a-117">To manage data mining models, you must first create a connection to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="8875a-118">Diese Verbindung ist auch dann erforderlich, wenn Sie mit Sitzungsmodellen arbeiten, die in einer temporären Datei gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="8875a-118">A connection is required even if you are working with session models stored in a temporary file.</span></span> <span data-ttu-id="8875a-119">Weitere Informationen zum Erstellen oder Ändern einer Verbindung finden Sie unter Herstellen einer Verbindung [mit Quelldaten &#40;Data Mining-Client für Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="8875a-119">For more information about how to create or change a connection, see [Connect to Source Data &#40;Data Mining Client for Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span></span>  
  
 <span data-ttu-id="8875a-120">Wenn die Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], mit der Sie eine Verbindung herstellen, nicht bereits Data Mining-Strukturen oder Data Mining-Modelle enthält, können Sie mithilfe der von diesem Add-In bereitgestellten Assistenten und Tools solche Strukturen und Modelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="8875a-120">If the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you connect to does not contain any existing data mining structures or data mining models, you can create them by using the wizards and other tools provided by this add-in.</span></span> <span data-ttu-id="8875a-121">Sie können auch neue Modelle erstellen, indem Sie das **Data Mining-Modell Erweiterter Editor**verwenden.</span><span class="sxs-lookup"><span data-stu-id="8875a-121">You can also create new models by using the **Data Mining Model Advanced Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8875a-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8875a-122">See Also</span></span>  
 <span data-ttu-id="8875a-123">[Dokumentieren von Mining Modellen &#40;Data Mining-Add-Ins für Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="8875a-123">[Documenting Mining Models &#40;Data Mining Add-ins for Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md) </span></span>  
 [<span data-ttu-id="8875a-124">Bereitstellen und Skalieren von Mining Modellen &#40;Data Mining-Add-Ins für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="8875a-124">Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;</span></span>](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md)   

  
