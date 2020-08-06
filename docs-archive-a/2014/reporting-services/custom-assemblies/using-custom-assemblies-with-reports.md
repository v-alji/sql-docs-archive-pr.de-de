---
title: Verwenden benutzerdefinierter Assemblys mit Berichten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom assemblies [Reporting Services]
- assemblies [Reporting Services], custom
- custom assemblies [Reporting Services], about custom assemblies
ms.assetid: 53d141d0-2185-466a-84dc-7b90d284da3d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f77b9da44ebb57617bd45e43d1e1e847e9074662
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697581"
---
# <a name="using-custom-assemblies-with-reports"></a><span data-ttu-id="0327f-102">Verwenden benutzerdefinierter Assemblys mit Berichten</span><span class="sxs-lookup"><span data-stu-id="0327f-102">Using Custom Assemblies with Reports</span></span>
  <span data-ttu-id="0327f-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] können Sie benutzerdefinierten Code für Werte, Formate und Formatierungen von Berichtselementen schreiben.</span><span class="sxs-lookup"><span data-stu-id="0327f-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can write custom code for report item values, styles, and formatting.</span></span> <span data-ttu-id="0327f-104">Beispielsweise können Sie mit benutzerdefiniertem Code Währungen entsprechend einem Gebietsschema formatieren, bestimmte Werte mit speziellen Formatierungen belegen oder andere Geschäftsregeln anwenden, die in Ihrem Unternehmen praktiziert werden.</span><span class="sxs-lookup"><span data-stu-id="0327f-104">For example, you can use custom code to format currencies based on locale, flag certain values with special formatting, or apply other business rules that are in practice for your company.</span></span> <span data-ttu-id="0327f-105">Eine Möglichkeit, diesen Code in Ihre Berichte einzubinden, besteht darin, eine benutzerdefinierte Codeassembly mithilfe von zu erstellen, auf die [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Sie in ihren Berichts Definitions Dateien verweisen können.</span><span class="sxs-lookup"><span data-stu-id="0327f-105">One way to include this code in your reports is to create a custom code assembly using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] that you can reference from within your report definition files.</span></span> <span data-ttu-id="0327f-106">Der Server ruft die Funktionen in Ihren benutzerdefinierten Assemblys auf, wenn ein Bericht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0327f-106">The server calls the functions in your custom assemblies when a report is run.</span></span> <span data-ttu-id="0327f-107">Mithilfe von benutzerdefinierten Assemblys können spezielle Funktionen abgerufen werden, die Sie in den Berichten verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="0327f-107">Custom assemblies can be used to retrieve specialized functions that you plan to use in your reports.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0327f-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0327f-108">In This Section</span></span>  
 [<span data-ttu-id="0327f-109">Verweisen auf Assemblys in einer RDL-Datei</span><span class="sxs-lookup"><span data-stu-id="0327f-109">Referencing Assemblies in an RDL File</span></span>](referencing-assemblies-in-an-rdl-file.md)  
 <span data-ttu-id="0327f-110">Beschreibt, wie in einer Sprachdatei der Berichtsdefinition auf die benutzerdefinierten Assemblys verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="0327f-110">Describes how to reference your custom assemblies in a report definition language file.</span></span>  
  
 [<span data-ttu-id="0327f-111">Bereitstellen einer benutzerdefinierten Assembly</span><span class="sxs-lookup"><span data-stu-id="0327f-111">Deploying a Custom Assembly</span></span>](deploying-a-custom-assembly.md)  
 <span data-ttu-id="0327f-112">Beschreibt den Einsatz einer benutzerdefinierten Assembly im Berichtsserver und im Berichts-Manager.</span><span class="sxs-lookup"><span data-stu-id="0327f-112">Describes how to deploy a custom assembly to Report Designer and the report server.</span></span>  
  
 [<span data-ttu-id="0327f-113">Verwenden von benutzerdefinierten Assemblys mit starken Namen</span><span class="sxs-lookup"><span data-stu-id="0327f-113">Using Strong-Named Custom Assemblies</span></span>](using-strong-named-custom-assemblies.md)  
 <span data-ttu-id="0327f-114">Beschreibt die Verwendung benutzerdefinierter Assemblys zusammen mit starken Namen.</span><span class="sxs-lookup"><span data-stu-id="0327f-114">Describes how to use custom assemblies with strong names.</span></span>  
  
 [<span data-ttu-id="0327f-115">Berechtigungserteilung in benutzerdefinierten Assemblys</span><span class="sxs-lookup"><span data-stu-id="0327f-115">Asserting Permissions in Custom Assemblies</span></span>](asserting-permissions-in-custom-assemblies.md)  
 <span data-ttu-id="0327f-116">Beschreibt, wie benutzerdefinierte Assemblys mit beschränkten und speziellen Berechtigungen eingesetzt werden und wie diese Berechtigungen im Code erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="0327f-116">Describes how to deploy custom assemblies with limited and specific permissions and how to assert those permissions in code.</span></span>  
  
 [<span data-ttu-id="0327f-117">Zugriff auf benutzerdefinierte Assemblys über Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="0327f-117">Accessing Custom Assemblies Through Expressions</span></span>](accessing-custom-assemblies-through-expressions.md)  
 <span data-ttu-id="0327f-118">Beschreibt, wie benutzerdefinierte Assemblymethoden als Berichtsausdrücke in den Berichtsdefinitionen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0327f-118">Describes how to call custom assembly methods as report expressions in your report definitions.</span></span>  
  
 [<span data-ttu-id="0327f-119">Initialisieren von Objekten benutzerdefinierter Assemblys</span><span class="sxs-lookup"><span data-stu-id="0327f-119">Initializing Custom Assembly Objects</span></span>](initializing-custom-assembly-objects.md)  
 <span data-ttu-id="0327f-120">Beschreibt, wie Werte für benutzerdefinierte Assemblyobjekte initialisiert werden, die von einem Bericht aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0327f-120">Describes how to initialize values for custom assembly objects called from a report.</span></span>  
  
 [<span data-ttu-id="0327f-121">Gewusst wie: Debuggen von benutzerdefinierten Assemblys</span><span class="sxs-lookup"><span data-stu-id="0327f-121">How to: Debug Custom Assemblies</span></span>](how-to-debug-custom-assemblies.md)  
 <span data-ttu-id="0327f-122">Beschreibt das Debuggen von benutzerdefiniertem Assemblycode.</span><span class="sxs-lookup"><span data-stu-id="0327f-122">Describes how to debug your custom assembly code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0327f-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0327f-123">See Also</span></span>  
 [<span data-ttu-id="0327f-124">Berichtsdefinitionssprache (SSRS)</span><span class="sxs-lookup"><span data-stu-id="0327f-124">Report Definition Language &#40;SSRS&#41;</span></span>](../reports/report-definition-language-ssrs.md)  
  
  
