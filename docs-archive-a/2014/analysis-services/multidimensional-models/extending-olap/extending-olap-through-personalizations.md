---
title: Erweitern von OLAP durch Personalisierungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Analysis Services, extensibility
ms.assetid: 348e49fc-4390-43c1-9b6c-61b386ff4373
author: minewiskan
ms.author: owend
ms.openlocfilehash: 93669980e989b1cb11673f45c111de3609bbe920
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725074"
---
# <a name="extending-olap-through-personalizations"></a><span data-ttu-id="735fc-102">Erweitern von OLAP durch Personalisierungen</span><span class="sxs-lookup"><span data-stu-id="735fc-102">Extending OLAP through personalizations</span></span>
  <span data-ttu-id="735fc-103">Microsoft [!INCLUDE[ssASCurrent](../../../includes/ssascurrent-md.md)] stellt viele systeminterne Funktionen bereit, die mit den Sprachen Multidimensional Expressions (MDX) und Data Mining Extensions (DMX) verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="735fc-103">Microsoft  [!INCLUDE[ssASCurrent](../../../includes/ssascurrent-md.md)] supplies many intrinsic functions for use with the Multidimensional Expressions (MDX) and Data Mining Extensions (DMX) languages.</span></span> <span data-ttu-id="735fc-104">Diese Funktionen sind ebenso für herkömmliche statistische Berechnungen wie zum Durchlaufenden der Elemente einer Hierarchie geeignet.</span><span class="sxs-lookup"><span data-stu-id="735fc-104">These functions are designed to accomplish everything from standard statistical calculations to traversing members in a hierarchy.</span></span> <span data-ttu-id="735fc-105">Wie bei jedem anderen komplexen und robusten Produkt besteht jedoch immer die Notwendigkeit, die Funktionalität eines solchen Produkts weiter zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="735fc-105">However, as with any other complex and robust product, there is always the need to extend the functionality of such a product further.</span></span>  
  
 <span data-ttu-id="735fc-106">Deshalb können Sie einer Instanz des Diensts mithilfe der Analysis Services Assemblys und Personalisierungserweiterungen hinzufügen, um die Geschäftsanforderungen zu erfüllen, wenn die Standardfunktionalität einmal nicht ausreichen sollte.</span><span class="sxs-lookup"><span data-stu-id="735fc-106">Therefore, Analysis Services provides you with the ability to add assemblies and personalized extensions to an instance of the service, in order to complete your business needs whenever the standard functionality is not enough.</span></span>  
  
## <a name="assemblies"></a><span data-ttu-id="735fc-107">Assemblys</span><span class="sxs-lookup"><span data-stu-id="735fc-107">Assemblies</span></span>  
 <span data-ttu-id="735fc-108">Mit Assemblys können Sie die Geschäfts Funktionalität von MDX und DMX erweitern.</span><span class="sxs-lookup"><span data-stu-id="735fc-108">Assemblies enable you to extend the business functionality of MDX and DMX.</span></span> <span data-ttu-id="735fc-109">Sie integrieren die gewünschte Funktionalität in eine Bibliothek, z. B. eine DLL (Dynamic Link Library), und fügen dann die Bibliothek als Assembly einer Instanz von Analysis Services oder einer Analysis Services-Datenbank hinzu.</span><span class="sxs-lookup"><span data-stu-id="735fc-109">You build the functionality that you want into a library, such as a dynamic link library (DLL), then add the library as an assembly to an instance of Analysis Services or to an Analysis Services database.</span></span> <span data-ttu-id="735fc-110">Die öffentlichen Methoden in der Bibliothek werden dann als benutzerdefinierte Funktionen für MDX- und DMX-Ausdrücke, Prozeduren, Berechnungen, Aktionen und Clientanwendungen verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="735fc-110">The public methods in the library are then exposed as user-defined functions to MDX and DMX expressions, procedures, calculations, actions, and client applications.</span></span>  
  
## <a name="personalized-extensions"></a><span data-ttu-id="735fc-111">Personalisierte Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="735fc-111">Personalized Extensions</span></span>  
 <span data-ttu-id="735fc-112">SQL Server Analysis Services-Personalisierungserweiterungen sind die Grundlage für das Konzept der Implementierung einer Plug-In-Architektur.</span><span class="sxs-lookup"><span data-stu-id="735fc-112">SQL Server Analysis Services personalization extensions are the foundation of the idea of implementing a plug-in architecture.</span></span> <span data-ttu-id="735fc-113">Analysis Services Personalisierungs Erweiterungen sind eine einfache und elegante Änderung der vorhandenen Architektur der verwalteten Assembly und werden im Analysis Services [Microsoft. AnalysisServices. AdomdServer](/previous-versions/sql/sql-server-2014/ms131779(v=sql.120)) -Objektmodell, in der MDX-Syntax (Multidimensional Expressions) und in Schemarowsets verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="735fc-113">Analysis Services personalization extensions are a simple and elegant modification to the existing managed assembly architecture and are exposed throughout the Analysis Services [Microsoft.AnalysisServices.AdomdServer](/previous-versions/sql/sql-server-2014/ms131779(v=sql.120)) object model, Multidimensional Expressions (MDX) syntax, and schema rowsets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="735fc-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="735fc-114">See Also</span></span>  
 <span data-ttu-id="735fc-115">[Verwaltung von mehrdimensionalen Modellen](../multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="735fc-115">[Multidimensional Model Assemblies Management](../multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="735fc-116">Personalisierungserweiterungen für Analysis Services</span><span class="sxs-lookup"><span data-stu-id="735fc-116">Analysis Services Personalization Extensions</span></span>](analysis-services-personalization-extensions.md)  
  
  
