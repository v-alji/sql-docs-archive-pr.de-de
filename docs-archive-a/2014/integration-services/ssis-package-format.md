---
title: SSIS-Paket Format | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: cfe0e5dc-5be3-4222-b721-fe83665edd94
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 524c65ac5682b8efe8c4191697eb540f9acca82b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700010"
---
# <a name="ssis-package-format"></a><span data-ttu-id="44d34-102">SSIS-Paketformat</span><span class="sxs-lookup"><span data-stu-id="44d34-102">SSIS Package Format</span></span>
  <span data-ttu-id="44d34-103">In der aktuellen Version von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]wurden wichtige Änderungen am Paketformat (DTSX-Datei) vorgenommen, um das Format besser lesbar zu machen und Pakete besser vergleichen zu können.</span><span class="sxs-lookup"><span data-stu-id="44d34-103">In the current release of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], significant changes were made to the package format (.dtsx file) to make it easier to read the format and to compare packages.</span></span> <span data-ttu-id="44d34-104">Außerdem können Sie Pakete zuverlässiger zusammenführen, die keine in Konflikt stehenden Änderungen oder im Binärformat gespeicherte Änderungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="44d34-104">You can also more reliably merge packages that don't contain conflicting changes or changes stored in binary format.</span></span>  
  
 <span data-ttu-id="44d34-105">Um das aktuelle dzx-Paketdatei Format anzuzeigen, finden Sie weitere Informationen unter [ \[ MS-dzx \] : Data Transformation Services-Paket-XML-Dateiformat Spezifikation](https://go.microsoft.com/fwlink/?LinkId=233251).</span><span class="sxs-lookup"><span data-stu-id="44d34-105">To view the current DTSX package file format, see [\[MS-DTSX\]: Data Transformation Services Package XML File Format Specification](https://go.microsoft.com/fwlink/?LinkId=233251).</span></span>  
  
 <span data-ttu-id="44d34-106">In der folgenden Liste werden die Dateiformatänderungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="44d34-106">The following list outlines the file format changes.</span></span> <span data-ttu-id="44d34-107">Um Codebeispiele für diese Änderungen anzuzeigen, finden Sie weitere Informationen unter [Paketformatänderungen in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=233255).</span><span class="sxs-lookup"><span data-stu-id="44d34-107">To view code examples of these changes, see [Package Format Changes in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=233255).</span></span>  
  
-   <span data-ttu-id="44d34-108">Formatierungskonventionen wurden übernommen, um die DTSX-Datei besser lesbar und verständlicher zu machen.</span><span class="sxs-lookup"><span data-stu-id="44d34-108">Formatting conventions have been applied to make it easier to read and understand the .dtsx file.</span></span>  
  
-   <span data-ttu-id="44d34-109">Das Format ist präziser.</span><span class="sxs-lookup"><span data-stu-id="44d34-109">The format is more concise.</span></span> <span data-ttu-id="44d34-110">Separate Elemente für jede Eigenschaft wurden als Attribute beibehalten, mit Ausnahme von PackageFormatVersion.</span><span class="sxs-lookup"><span data-stu-id="44d34-110">Separate elements for each property have been persisted as attributes, with the exception of the PackageFormatVersion.</span></span> <span data-ttu-id="44d34-111">Attribute sind alphabetisch aufgeführt, und Eigenschaften, die über Standardwerte verfügen, werden nicht mehr beibehalten.</span><span class="sxs-lookup"><span data-stu-id="44d34-111">Attributes are listed alphabetically, and properties that have default values are no longer persisted.</span></span> <span data-ttu-id="44d34-112">Außerdem sind Elemente, die mehrmals angezeigt werden können, jetzt innerhalb eines übergeordneten Elements enthalten.</span><span class="sxs-lookup"><span data-stu-id="44d34-112">Finally, elements that can appear multiple times, are now contained within a parent element.</span></span>  
  
-   <span data-ttu-id="44d34-113">Die meisten Objekte in einem Paket, auf die von anderen Objekten verwiesen werden kann, verfügen jetzt über ein im Paket-XML definiertes `refId`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="44d34-113">Most objects within a package that can be referred to by other objects now have a `refId` attribute defined in the package XML.</span></span> <span data-ttu-id="44d34-114">Statt persistenter Herkunfts-IDs wird die `refID` jetzt beibehalten.</span><span class="sxs-lookup"><span data-stu-id="44d34-114">Instead of persisting lineage IDs, the `refID` is now persisted.</span></span> <span data-ttu-id="44d34-115">Herkunfts-IDs werden immer noch zur Laufzeit verwendet und neu generiert, wenn das Paket geladen wird.</span><span class="sxs-lookup"><span data-stu-id="44d34-115">Lineage IDs are still used within the runtime and regenerated when the package is loaded.</span></span>  
  
     <span data-ttu-id="44d34-116">Der `refId`-Wert ist eine eindeutige Zeichenfolge, die im Vergleich zu GUIDS oder ganzzahligen Werten lesbar und verständlich ist.</span><span class="sxs-lookup"><span data-stu-id="44d34-116">The `refId` value is a unique string that is readable and understandable, compared to GUIDs or integer values.</span></span> <span data-ttu-id="44d34-117">Die Zeichenfolge ist ähnlich wie Pfadwerte, die in vorherigen Versionen von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]für die Paketkonfigurationen verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="44d34-117">The string is similar to path values used for package configurations in previous releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="44d34-118">Wenn Sie Änderungen zwischen zwei Versionen eines Pakets zusammenführen, kann die `refId` in Such-/Ersetzungsvorgängen verwendet werden, um sicherzustellen, dass alle Verweise auf dieses Objekt ordnungsgemäß aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="44d34-118">If you are merging changes between two versions of a package, the `refId` can be used in find/replace operations to ensure that all references to that object have been correctly updated.</span></span>  
  
-   <span data-ttu-id="44d34-119">Die Layoutinformationen sind in einem CDATA-Abschnitt enthalten.</span><span class="sxs-lookup"><span data-stu-id="44d34-119">The layout information is contained in a CData section.</span></span>  
  
-   <span data-ttu-id="44d34-120">Anmerkungen werden in Klartext beibehalten.</span><span class="sxs-lookup"><span data-stu-id="44d34-120">Annotations are persisted in cleartext.</span></span> <span data-ttu-id="44d34-121">Dies erleichtert es, die Informationen für die automatisierte Generierung der Dokumentation zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="44d34-121">This makes it easier to extract the information for automated generation of documentation.</span></span>  
  
  
