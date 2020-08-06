---
title: Berechnungen (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 738816e3-0e1d-44a5-8d1b-81068dce8ac0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2da86ae5c5652c8b2614cae4bbb721802700d973
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616713"
---
# <a name="calculations-ssas-tabular"></a><span data-ttu-id="1089a-102">Berechnungen (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="1089a-102">Calculations (SSAS Tabular)</span></span>
  <span data-ttu-id="1089a-103">Nachdem Sie Daten in das Modell importiert haben, können Sie Berechnungen hinzufügen, um Daten zu aggregieren, filtern, erweitern, kombinieren und schützen.</span><span class="sxs-lookup"><span data-stu-id="1089a-103">After you have imported data into your model, you can add calculations to aggregate, filter, extend, combine, and secure that data.</span></span> <span data-ttu-id="1089a-104">Tabellarische Modelle verwenden Data Analysis Expressions (DAX), eine neue Formelsprache zum Erstellen von benutzerdefinierten Berechnungen.</span><span class="sxs-lookup"><span data-stu-id="1089a-104">Tabular models use Data Analysis Expressions (DAX), a formula language for creating custom calculations.</span></span> <span data-ttu-id="1089a-105">In tabellarischen Modellen werden die Berechnungen, die Sie mit DAX-Formeln erstellen, in *berechneten Spalten*, *Measures*und *Zeilenfiltern*verwendet.</span><span class="sxs-lookup"><span data-stu-id="1089a-105">In tabular models, the calculations you create by using DAX formulas are used in *Calculated Columns*, *Measures*, and *Row Filters*.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1089a-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1089a-106">In This Section</span></span>  
  
|<span data-ttu-id="1089a-107">Thema</span><span class="sxs-lookup"><span data-stu-id="1089a-107">Topic</span></span>|<span data-ttu-id="1089a-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1089a-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="1089a-109">Grundlegendes zu DAX in tabellarischen Modellen &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="1089a-109">Understanding DAX in Tabular Models &#40;SSAS Tabular&#41;</span></span>](understanding-dax-in-tabular-models-ssas-tabular.md)|<span data-ttu-id="1089a-110">Beschreibt die Data Analysis Expressions (DAX)-Formelsprache, die zum Erstellen von Berechnungen für berechnete Spalten, Measures und Zeilenfilter in tabellarischen Modellen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1089a-110">Describes the Data Analysis Expressions (DAX) formula language used to create calculations for calculated columns, measures, and row filters in tabular models.</span></span>|  
|[<span data-ttu-id="1089a-111">Formelkompatibilität im DirectQuery-Modus</span><span class="sxs-lookup"><span data-stu-id="1089a-111">Formula Compatibility in DirectQuery Mode</span></span>](../dax-formula-compatibility-in-directquery-mode-ssas-2014.md)|<span data-ttu-id="1089a-112">Beschreibt die Unterschiede und listet die Funktionen auf, die nicht im DirectQuery-Modus unterstützt werden. Des Weiteren werden die Funktionen aufgelistet, die unterstützt werden, aber andere Ergebnisse zurückgeben können.</span><span class="sxs-lookup"><span data-stu-id="1089a-112">Describes the differences, lists the functions that are not supported in DirectQuery mode, and lists the functions that are supported but could return different results.</span></span>|  
|[<span data-ttu-id="1089a-113">Data Analysis Expressions &#40;DAX-&#41; Referenz</span><span class="sxs-lookup"><span data-stu-id="1089a-113">Data Analysis Expressions &#40;DAX&#41; Reference</span></span>](/dax/data-analysis-expressions-dax-reference)|<span data-ttu-id="1089a-114">Dieser Abschnitt enthält ausführliche Beschreibungen der DAX-Syntax, -Operatoren und -Funktionen.</span><span class="sxs-lookup"><span data-stu-id="1089a-114">This section provides detailed descriptions of DAX syntax, operators, and functions.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="1089a-115">Dieser Abschnitt enthält keine Schritt-für-Schritt-Anweisungen zum Erstellen von Berechnungen.</span><span class="sxs-lookup"><span data-stu-id="1089a-115">Step-by-step tasks for creating calculations are not provided in this section.</span></span> <span data-ttu-id="1089a-116">Da Berechnungen in berechneten Spalten, Measures und Zeilenfiltern (in Rollen) angegeben werden, werden die Anweisungen zum Erstellen von DAX-Formeln in Aufgaben für diese Funktionen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1089a-116">Because calculations are specified in calculated columns, measures, and row filters (in roles), instructions on where to create DAX formulas are provided in tasks related to those features.</span></span> <span data-ttu-id="1089a-117">Weitere Informationen finden Sie unter [Erstellen einer berechneten Spalte &#40;SSAS – tabellarisch&#41;](ssas-calculated-columns-create-a-calculated-column.md), [Erstellen und Verwalten von Measures &#40;SSAS – tabellarisch&#41;](measures-ssas-tabular.md) und [Erstellen und Verwalten von Rollen &#40;SSAS – tabellarisch&#41;](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="1089a-117">For more information, see [Create a Calculated Column &#40;SSAS Tabular&#41;](ssas-calculated-columns-create-a-calculated-column.md), [Create and Manage Measures &#40;SSAS Tabular&#41;](measures-ssas-tabular.md), and [Create and Manage Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1089a-118">Obwohl DAX auch zum Abfragen eines tabellarischen Modells verwendet werden kann, wird in den Themen dieses Abschnitts schwerpunktmäßig das Erstellen von Berechnungen mithilfe von DAX-Formeln behandelt.</span><span class="sxs-lookup"><span data-stu-id="1089a-118">While DAX can also be used to query a tabular model, topics in this section focus specifically on using DAX formulas to create calculations.</span></span>  
  
  
