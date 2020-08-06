---
title: Datenquellen (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 6908998b-9302-4a90-976e-770106b48d18
author: minewiskan
ms.author: owend
ms.openlocfilehash: d686d8100e30d7608e8d90f135022bdf46785723
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702110"
---
# <a name="data-sources-ssas-tabular"></a><span data-ttu-id="cf94a-102">Datenquellen (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="cf94a-102">Data Sources (SSAS Tabular)</span></span>
  <span data-ttu-id="cf94a-103">Über Datenquellen werden die Daten bereitgestellt, die in eine Projektmappe für tabellarische Modelle aufgenommen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cf94a-103">Data sources provide the data to be included in a tabular model solution.</span></span> <span data-ttu-id="cf94a-104">Sie können Daten aus einer Vielzahl von relationalen Datenbanken in das Modell aufnehmen, z. B. relationale Datenbanken, Datenfeeds, mehrdimensionale Datenquellen wie ein Analysis Services-Cube und Textdateien wie eine Microsoft Excel-Arbeitsmappe.</span><span class="sxs-lookup"><span data-stu-id="cf94a-104">You can import data into your model from a wide variety of sources such as relational databases, data feeds, multidimensional data sources such as an Analysis Services cube, and from text files such as a Microsoft Excel workbook.</span></span> <span data-ttu-id="cf94a-105">Dieser Abschnitt enthält Informationen über die Arten von Datenquellen, aus denen Sie importieren können, und die verschiedenen für den Import unterstützten Datentypen, sowie Aufgaben, in denen das Importieren von Daten aus diesen Quellen beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="cf94a-105">Topics in this section provide information about the types of data sources you can import from, the various data types you can import, and tasks describing how to import data from those sources.</span></span>  
  
## <a name="related-topics-and-tasks"></a><span data-ttu-id="cf94a-106">Verwandte Themen und Tasks</span><span class="sxs-lookup"><span data-stu-id="cf94a-106">Related Topics and Tasks</span></span>  
  
|<span data-ttu-id="cf94a-107">Thema</span><span class="sxs-lookup"><span data-stu-id="cf94a-107">Topic</span></span>|<span data-ttu-id="cf94a-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cf94a-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="cf94a-109">Unterstützte Datenquellen &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="cf94a-109">Data Sources Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-sources-supported-ssas-tabular.md)|<span data-ttu-id="cf94a-110">Dieses Thema enthält Informationen zu den verschiedenen Datenquellen, aus denen Sie importieren können.</span><span class="sxs-lookup"><span data-stu-id="cf94a-110">This topic provides information about the different data sources that you can import data from.</span></span>|  
|[<span data-ttu-id="cf94a-111">Unterstützte Datentypen &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="cf94a-111">Data Types Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-types-supported-ssas-tabular.md)|<span data-ttu-id="cf94a-112">Dieses Thema enthält Informationen zu den verschiedenen Datentypen, die in einem tabellarischen Modell unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="cf94a-112">This topic provides information about the various data types that are supported in a Tabular Model.</span></span>|  
|[<span data-ttu-id="cf94a-113">Identitätswechsel &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="cf94a-113">Impersonation &#40;SSAS Tabular&#41;</span></span>](tabular-models/impersonation-ssas-tabular.md)|<span data-ttu-id="cf94a-114">Dieses Thema enthält Informationen zum Identitätswechsel, durch den Anmeldedaten bereitgestellt werden, die von Analysis Services beim Herstellen einer Verbindung mit einer Datenquelle zum Importieren und Aktualisieren von Daten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cf94a-114">This topic provides information about impersonation, which provides logon credentials that are used by Analysis Services when connecting to a data source to import and refresh data.</span></span>|  
|[<span data-ttu-id="cf94a-115">Importieren von Daten &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="cf94a-115">Import Data &#40;SSAS Tabular&#41;</span></span>](import-data-ssas-tabular.md)|<span data-ttu-id="cf94a-116">In den Tasks in diesem Abschnitt wird beschrieben, wie Daten aus unterschiedlichen Datenquellen importiert werden.</span><span class="sxs-lookup"><span data-stu-id="cf94a-116">Tasks in this section describe how to import data from different data sources.</span></span>|  
|[<span data-ttu-id="cf94a-117">Verarbeiten von Daten &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="cf94a-117">Process Data &#40;SSAS Tabular&#41;</span></span>](process-data-ssas-tabular.md)|<span data-ttu-id="cf94a-118">In den Tasks in diesem Abschnitt wird beschrieben, wie Daten, die bereits in ein Modell importiert wurden, verarbeitet (aktualisiert) werden.</span><span class="sxs-lookup"><span data-stu-id="cf94a-118">Tasks in this section describe how to process (refresh) or change data that has already been imported into a model.</span></span>|  
|[<span data-ttu-id="cf94a-119">Bearbeiten einer vorhandenen Datenquellenverbindung &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="cf94a-119">Edit an Existing Data Source Connection &#40;SSAS Tabular&#41;</span></span>](edit-an-existing-data-source-connection-ssas-tabular.md)|<span data-ttu-id="cf94a-120">Beschreibt, wie eine Datenquellenverbindung bearbeitet wird, die bereits erstellt wurde und verwendet wurde, um Daten aus einer Quelle zu importieren.</span><span class="sxs-lookup"><span data-stu-id="cf94a-120">Describes how to edit a data source connection that has already been created and used to import data from a source.</span></span>|  
  
  
