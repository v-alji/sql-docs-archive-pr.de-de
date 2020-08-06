---
title: Ausdrucksverweis (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: bb16e4ab-b13f-48f2-8cfe-1851656875ef
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7854aa2cc256d63fe93ddb049486e782bfaa0e11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616405"
---
# <a name="expression-reference-report-builder-and-ssrs"></a><span data-ttu-id="e968f-102">Ausdrucksverweis (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="e968f-102">Expression Reference (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e968f-103">Berichtsausdrücke unterstützen eine Vielzahl von Verweisen auf integrierte Funktionen und integrierte Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="e968f-103">Report expressions support a variety of references to built-in functions and built-in collections.</span></span> <span data-ttu-id="e968f-104">Ausdrücke müssen über eine gültige [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] -Syntax verfügen, bevor ein Bericht veröffentlicht oder verarbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e968f-104">Expressions must have valid [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] syntax before a report can be published or processed.</span></span>  
  
 <span data-ttu-id="e968f-105">Wenn Sie komplexe Ausdrücke oder Ausdrücke entwickeln möchten, die benutzerdefinierten Code oder benutzerdefinierte Assemblys verwenden, empfiehlt sich die Verwendung des Berichts-Designers in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e968f-105">To develop complex expressions or expressions that use custom code or custom assemblies, we recommend that you use Report Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="e968f-106">Weitere Informationen finden Sie unter [Benutzerdefinierter Code und Assemblyverweise in Ausdrücken in Berichts-Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md)-Ausdruck dar.</span><span class="sxs-lookup"><span data-stu-id="e968f-106">For more information, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="e968f-107">In den Themen in diesem Abschnitt erhalten Sie Hilfestellung zum Schreiben von Ausdrücken in einem Bericht.</span><span class="sxs-lookup"><span data-stu-id="e968f-107">Use the topics in this section to help write simple expressions in a report.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e968f-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e968f-108">In This Section</span></span>  
 [<span data-ttu-id="e968f-109">Datentypen in Ausdrücken &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e968f-109">Data Types in Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="e968f-110">Konstanten in Ausdrücken &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e968f-110">Constants in Expressions &#40;Report Builder and SSRS&#41;</span></span>](constants-in-expressions-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="e968f-111">Operatoren in Ausdrücken &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e968f-111">Operators in Expressions &#40;Report Builder and SSRS&#41;</span></span>](operators-in-expressions-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="e968f-112">Integrierte Sammlungen in Ausdrücken &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e968f-112">Built-in Collections in Expressions &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-in-expressions-report-builder.md)  
  
 [<span data-ttu-id="e968f-113">Integrierte globale Werte und Benutzerverweise &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e968f-113">Built-in Globals and Users References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-built-in-globals-and-users-references-report-builder.md)  
  
 [<span data-ttu-id="e968f-114">Verweise auf Parameters-Sammlungen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e968f-114">Parameters Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-parameters-collection-references-report-builder.md)  
  
 [<span data-ttu-id="e968f-115">Verweise auf Datasetfeld-Sammlungen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e968f-115">Dataset Fields Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-dataset-fields-collection-references-report-builder.md)  
  
 [<span data-ttu-id="e968f-116">Verweise auf DataSources- und DataSets-Sammlungen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e968f-116">DataSources and DataSets Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-datasources-and-datasets-references-report-builder.md)  
  
 [<span data-ttu-id="e968f-117">Verweise auf Berichts- und Gruppenvariablensammlungen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e968f-117">Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-report-and-group-variables-references-report-builder.md)  
  
 [<span data-ttu-id="e968f-118">Verweise auf ReportItems-Sammlungen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e968f-118">ReportItems Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-reportitems-collection-references-report-builder.md)  
  
## <a name="see-also"></a><span data-ttu-id="e968f-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e968f-119">See Also</span></span>  
 [<span data-ttu-id="e968f-120">Ausdrücke &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e968f-120">Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)  
  
  
