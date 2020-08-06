---
title: Entwickeln mit Analysis Services Scripting Language (ASSL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Analysis Services Scripting Language
- ASSL
ms.assetid: ce9aca4d-b7ad-451e-bb7f-20c2b0c03f29
author: minewiskan
ms.author: owend
ms.openlocfilehash: fbb64c120e67d5b4ac12e7bd77f0e0c4e5736757
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618355"
---
# <a name="developing-with-analysis-services-scripting-language-assl"></a><span data-ttu-id="7c64d-102">Entwickeln mit Analysis Services Scripting Language (ASSL)</span><span class="sxs-lookup"><span data-stu-id="7c64d-102">Developing with Analysis Services Scripting Language (ASSL)</span></span>
  <span data-ttu-id="7c64d-103">Analysis Services Scripting Language (ASSL) ist eine Erweiterung, die XMLA durch eine Objektdefinitionssprache und Befehlssprache zum Erstellen und Verwalten von Analysis Services-Strukturen direkt auf dem Server ergänzt.</span><span class="sxs-lookup"><span data-stu-id="7c64d-103">Analysis Services Scripting Language (ASSL) is an extension to XMLA that adds an object definition language and command language for creating and managing Analysis Services structures directly on the server.</span></span> <span data-ttu-id="7c64d-104">Sie können ASSL in benutzerdefinierten Anwendung zur Kommunikation mit Analysis Services über das XMLA-Protokoll verwenden.</span><span class="sxs-lookup"><span data-stu-id="7c64d-104">You can use ASSL in custom application to communicate with Analysis Services over the XMLA protocol.</span></span> <span data-ttu-id="7c64d-105">ASSL umfasst zwei Teile:</span><span class="sxs-lookup"><span data-stu-id="7c64d-105">ASSL is made up of two parts:</span></span>  
  
-   <span data-ttu-id="7c64d-106">eine Datendefinitionssprache (Data Definition Language, DDL) oder Objektdefinitionssprache, mit der eine Instanz von [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]definiert und beschrieben wird, sowie die in der Instanz enthaltenen Datenbanken und Datenbankobjekte.</span><span class="sxs-lookup"><span data-stu-id="7c64d-106">A Data Definition Language (DDL), or object definition language, defines and describes an instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], as well as the databases and database objects that the instance contains.</span></span>  
  
-   <span data-ttu-id="7c64d-107">Eine Befehlssprache, mit der Aktionsbefehle wie `Create`, `Alter` oder `Process` an eine Instanz von Analysis Services gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="7c64d-107">A command language that sends action commands, such as `Create`, `Alter`, or `Process`, to an instance of Analysis Services.</span></span> <span data-ttu-id="7c64d-108">Diese Befehlssprache wird in der [XML for Analysis &#40;XMLA&#41; Referenz](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference)erläutert.</span><span class="sxs-lookup"><span data-stu-id="7c64d-108">This command language is discussed in the [XML for Analysis  &#40;XMLA&#41; Reference](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference).</span></span>  
  
 <span data-ttu-id="7c64d-109">Zur Anzeige der ASSL, durch die eine mehrdimensionale Lösung in [!INCLUDE[ssBIDevStudio](../../../includes/ssbidevstudio-md.md)]beschrieben wird, können Sie den Befehl Code anzeigen auf Projektebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="7c64d-109">To view the ASSL that describes a multidimensional solution in [!INCLUDE[ssBIDevStudio](../../../includes/ssbidevstudio-md.md)], you can use the View Code command at the project level.</span></span> <span data-ttu-id="7c64d-110">Sie können ein ASSL-Skript in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] auch mit dem XMLA-Abfrage-Editor erstellen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="7c64d-110">You can also create or edit ASSL script in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] using the XMLA query editor.</span></span> <span data-ttu-id="7c64d-111">Die erstellten Skripts können zum Verwalten von Objekten oder Ausführen von Befehlen auf dem Server verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7c64d-111">The scripts you build can be used to manage objects or run commands on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c64d-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7c64d-112">See Also</span></span>  
 <span data-ttu-id="7c64d-113">[ASSL-Objekte und Objektmerkmale](assl-objects-and-object-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="7c64d-113">[ASSL Objects and Object Characteristics](assl-objects-and-object-characteristics.md) </span></span>  
 <span data-ttu-id="7c64d-114">[ASSL-XML-Konventionen](assl-xml-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="7c64d-114">[ASSL XML Conventions](assl-xml-conventions.md) </span></span>  
 [<span data-ttu-id="7c64d-115">Datenquellen und Bindungen &#40;SSAS – mehrdimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="7c64d-115">Data Sources and Bindings &#40;SSAS Multidimensional&#41;</span></span>](../data-sources-and-bindings-ssas-multidimensional.md)  
  
  
