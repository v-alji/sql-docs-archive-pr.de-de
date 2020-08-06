---
title: Definieren von Fakten Beziehungen und Fakten Beziehungs Eigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- fact dimensions [Analysis Services]
ms.assetid: d8e41724-da77-4ac1-bc42-956b5d91ea5d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 15f67a4bdf699bbc6443fc76ce54bcfb35831827
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698643"
---
# <a name="define-a-fact-relationship-and-fact-relationship-properties"></a><span data-ttu-id="e4202-102">Definieren von Faktenbeziehungen und Faktenbeziehungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="e4202-102">Define a Fact Relationship and Fact Relationship Properties</span></span>
  <span data-ttu-id="e4202-103">Wenn Sie eine neue Cubedimension oder eine neue Measuregruppe definieren, versucht [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], zu erkennen, ob eine Faktendimensionsbeziehung vorhanden ist, und legt dann die Einstellung für die Dimensionsverwendung auf `Fact` fest.</span><span class="sxs-lookup"><span data-stu-id="e4202-103">When you define a new cube dimension or a new measure group, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will try to detect if a fact dimension relationship exists and then set the dimension usage setting to `Fact`.</span></span> <span data-ttu-id="e4202-104">Sie können eine Faktendimensionsbeziehung im Cube-Designer auf der Registerkarte **Dimensionsverwendung** anzeigen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="e4202-104">You can view or edit a fact dimension relationship on the **Dimension Usage** tab of Cube Designer.</span></span> <span data-ttu-id="e4202-105">Die Faktenbeziehung zwischen einer Dimension und einer Measuregruppe besitzt die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="e4202-105">The fact relationship between a dimension and a measure group has the following constraints:</span></span>  
  
-   <span data-ttu-id="e4202-106">Eine Cubedimension kann nur über eine Faktenbeziehung zu einer bestimmten Measuregruppe verfügen.</span><span class="sxs-lookup"><span data-stu-id="e4202-106">A cube dimension can have only one fact relationship to a particular measure group.</span></span>  
  
-   <span data-ttu-id="e4202-107">Eine Cubedimension kann über separate Faktenbeziehungen zu mehreren Measuregruppen verfügen.</span><span class="sxs-lookup"><span data-stu-id="e4202-107">A cube dimension can have separate fact relationships to multiple measure groups.</span></span>  
  
-   <span data-ttu-id="e4202-108">Beim Granularitätsattribut der Beziehung muss es sich um das Schlüsselattribut (z. B. Transaction Number) für die Dimension handeln.</span><span class="sxs-lookup"><span data-stu-id="e4202-108">The granularity attribute for the relationship must be the key attribute (such as Transaction Number) for the dimension.</span></span> <span data-ttu-id="e4202-109">Hierdurch wird eine 1:1-Beziehung zwischen der Dimension und den Fakten in der Faktentabelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="e4202-109">This creates a one-to-one relationship between the dimension and facts in the fact table.</span></span>  
  
  
