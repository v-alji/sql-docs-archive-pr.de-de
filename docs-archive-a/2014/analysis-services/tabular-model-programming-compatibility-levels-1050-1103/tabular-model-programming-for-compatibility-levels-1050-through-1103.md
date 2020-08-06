---
title: Programmierung von tabellarischen Modellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 0ceb461e-12c1-44ea-97ac-b99bf308676b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2565ed28a882750ab9b37beadbce698d3a0abb19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727158"
---
# <a name="tabular-model-programming"></a><span data-ttu-id="c0605-102">Programmierung von tabellarischen Modellen</span><span class="sxs-lookup"><span data-stu-id="c0605-102">Tabular Model Programming</span></span>
  <span data-ttu-id="c0605-103">Tabellarische Modelle verwenden relationale Konstrukte, um die von Analyse- und Berichtsanwendungen verwendeten Analysis Services-Daten zu modellieren.</span><span class="sxs-lookup"><span data-stu-id="c0605-103">Tabular models use relational constructs to model the Analysis Services data used by analytical and reporting applications.</span></span> <span data-ttu-id="c0605-104">Diese Modelle werden auf einer Analysis Service-Instanz ausgeführt, die für den Tabellenmodus konfiguriert ist, und zwar mithilfe einer Engine für Datenanalyse im Arbeitsspeicher für einen Speicher und schnelle Tabellenscans, mit denen Daten nach Bedarf aggregiert und berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="c0605-104">These models run on an Analysis Service instance that is configured for tabular mode, using an in-memory analytics engine for storage and fast table scans that aggregate and calculate data as it is requested.</span></span>  
  
 <span data-ttu-id="c0605-105">Die Objekte, die Sie in AMO, ADOMD.NET, XMLA, oder OLE DB verwenden, sind programmiertechnisch im Grunde genommen sowohl für die tabellarischen als auch für die mehrdimensionalen Lösungen gleich.</span><span class="sxs-lookup"><span data-stu-id="c0605-105">Programmatically, the objects you work with in AMO, ADOMD.NET, XMLA, or OLE DB are fundamentally the same for both tabular and multidimensional solutions.</span></span> <span data-ttu-id="c0605-106">Wenn die Anforderungen der benutzerdefinierten BI-Lösung am besten von einer tabellarischen Modelldatenbank erfüllt werden, können Sie eine beliebige der Analysis Services-Clientbibliotheken und -Programmierschnittstellen verwenden, um die Anwendung auf einer Analysis Services-Instanz in tabellarische Modelle zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="c0605-106">If the requirements of your custom BI solution are best met by a tabular model database, you can use any of the Analysis Services client libraries and programming interfaces to integrate your application with tabular models on an Analysis Services instance.</span></span> <span data-ttu-id="c0605-107">Sie können entweder eingebettete MDX oder DAX im Code verwenden, um tabellarische Modelldaten abzufragen und zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="c0605-107">To query and calculate tabular model data, you can use either embedded MDX or DAX in your code.</span></span>  
  
 <span data-ttu-id="c0605-108">Dieser Abschnitt enthält weitere Informationen darüber, wie Sie programmgesteuert die Entitäten tabellarischer Modelle und ihre Eigenschaften verwenden können.</span><span class="sxs-lookup"><span data-stu-id="c0605-108">This section provides more information about how you can programmatically work with tabular model entities and their properties.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c0605-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c0605-109">In This Section</span></span>  
 [<span data-ttu-id="c0605-110">CSDL-Anmerkungen für Business Intelligence &#40;CSDLBI&#41;</span><span class="sxs-lookup"><span data-stu-id="c0605-110">CSDL Annotations for Business Intelligence &#40;CSDLBI&#41;</span></span>](/analysis-services/csdlbi/csdl-annotations-for-business-intelligence-csdlbi)  
  
 [<span data-ttu-id="c0605-111">Grundlegendes zum tabellarischen Objektmodell</span><span class="sxs-lookup"><span data-stu-id="c0605-111">Understanding the Tabular Object Model</span></span>](representation/understanding-tabular-object-model-at-levels-1050-through-1103.md)  
  
 [<span data-ttu-id="c0605-112">Technische Referenz für BI-Anmerkungen zu CSDL</span><span class="sxs-lookup"><span data-stu-id="c0605-112">Technical Reference for BI Annotations to CSDL</span></span>](/analysis-services/csdlbi/technical-reference-for-bi-annotations-to-csdl)  
  
 [<span data-ttu-id="c0605-113">IMDEmbedded-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0605-113">IMDEmbedded Interface</span></span>](imdembeddeddata-interface.md)  
  
## <a name="see-also"></a><span data-ttu-id="c0605-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c0605-114">See Also</span></span>  
 <span data-ttu-id="c0605-115">[Tabellarische Modellierung &#40;tabellarischen SSAS-&#41;](../tabular-models/tabular-models-ssas.md) </span><span class="sxs-lookup"><span data-stu-id="c0605-115">[Tabular Modeling &#40;SSAS Tabular&#41;](../tabular-models/tabular-models-ssas.md) </span></span>  
 [<span data-ttu-id="c0605-116">Tabellen Modell-Designer &#40;tabellarischen SSAS-&#41;</span><span class="sxs-lookup"><span data-stu-id="c0605-116">Tabular Model Designer &#40;SSAS Tabular&#41;</span></span>](../tabular-model-designer-ssas-tabular.md)  
  
  
