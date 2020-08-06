---
title: Eigenschaftenseiten in SQL Server Management Studio | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- property pages [SQL Server Management Studio]
ms.assetid: 719282c3-e9cc-4e0e-9a83-7fb8b8b17f67
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3fae6a07fbaa2a259fcca5c3807094b31e0d52d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722170"
---
# <a name="property-pages-in-sql-server-management-studio"></a><span data-ttu-id="25b5e-102">Eigenschaftenseiten in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="25b5e-102">Property Pages in SQL Server Management Studio</span></span>
  <span data-ttu-id="25b5e-103">Die Dialogfelder für Eigenschaftenseiten in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] verwenden alle ein einheitliches Format, bei dem Informationen in Kategorien angezeigt werden, die ein- und ausklappbar sind.</span><span class="sxs-lookup"><span data-stu-id="25b5e-103">Property page dialog boxes in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] all use a common format displaying information with expanding and collapsing categories.</span></span> <span data-ttu-id="25b5e-104">Die angezeigten Felder hängen von der jeweiligen Eigenschaft ab.</span><span class="sxs-lookup"><span data-stu-id="25b5e-104">The fields shown depend on the particular property.</span></span> <span data-ttu-id="25b5e-105">Die in Grau angezeigten Eigenschaften sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="25b5e-105">Properties shown in gray are read-only.</span></span> <span data-ttu-id="25b5e-106">Die Schaltflächen Nach Kategorien und Alphabetisch befinden sich oben auf den einzelnen Eigenschaftenseiten.</span><span class="sxs-lookup"><span data-stu-id="25b5e-106">Categorized and Alphabetic buttons are near the top of each property page.</span></span>  
  
 <span data-ttu-id="25b5e-107">Die folgende Tabelle enthält die gemeinsamen Elemente von Dialogfeldern für Eigenschaftenseiten in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25b5e-107">The following table describes the common elements of [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] property page dialog boxes.</span></span>  
  
|<span data-ttu-id="25b5e-108">Element</span><span class="sxs-lookup"><span data-stu-id="25b5e-108">Element</span></span>|<span data-ttu-id="25b5e-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="25b5e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="25b5e-110">**Nach Kategorien**</span><span class="sxs-lookup"><span data-stu-id="25b5e-110">**Categorized**</span></span>|<span data-ttu-id="25b5e-111">Listet alle Eigenschaften und Eigenschaftswerte für das ausgewählte Objekt nach Kategorie sortiert auf.</span><span class="sxs-lookup"><span data-stu-id="25b5e-111">Lists all properties and property values for the selected object, sorted by category.</span></span> <span data-ttu-id="25b5e-112">In der Kategorieansicht können Sie eine Kategorie reduzieren, um die Anzahl von angezeigten Eigenschaften zu verringern.</span><span class="sxs-lookup"><span data-stu-id="25b5e-112">In category view, you can collapse a category to reduce the number of visible properties.</span></span> <span data-ttu-id="25b5e-113">Wenn Sie eine Kategorie erweitern oder reduzieren, wird ein Pluszeichen (+) oder Minuszeichen (-) auf der linken Seite des Kategorienamens angezeigt.</span><span class="sxs-lookup"><span data-stu-id="25b5e-113">When you expand or collapse a category, you see a plus sign (+) or minus sign (-) to the left of the category name.</span></span> <span data-ttu-id="25b5e-114">Kategorien sind in alphabetischer Reihenfolge aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="25b5e-114">Categories are listed alphabetically.</span></span>|  
|<span data-ttu-id="25b5e-115">**Alphabetisch**</span><span class="sxs-lookup"><span data-stu-id="25b5e-115">**Alphabetic**</span></span>|<span data-ttu-id="25b5e-116">Listet alle Eigenschaften und Eigenschaftswerte für das ausgewählte Objekt alphabetisch sortiert auf.</span><span class="sxs-lookup"><span data-stu-id="25b5e-116">Lists all properties and property values for the selected object, sorted alphabetically.</span></span>|  
|<span data-ttu-id="25b5e-117">Eigenschaftenname</span><span class="sxs-lookup"><span data-stu-id="25b5e-117">Property name</span></span>|<span data-ttu-id="25b5e-118">In der ersten Spalte im Raster sind die Eigenschaftsnamen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="25b5e-118">The first column in the grid lists the property names.</span></span>|  
|<span data-ttu-id="25b5e-119">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="25b5e-119">Properties</span></span>|<span data-ttu-id="25b5e-120">In der zweiten Spalte im Raster sind die Eigenschaftswerte aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="25b5e-120">The second column in the grid lists the property values.</span></span>|  
|<span data-ttu-id="25b5e-121">Beschreibungsbereich</span><span class="sxs-lookup"><span data-stu-id="25b5e-121">Description pane</span></span>|<span data-ttu-id="25b5e-122">Der Beschreibungsbereich befindet sich unten auf der Seite und zeigt den Eigenschaftentyp und eine kurze Beschreibung der Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="25b5e-122">The description pane appears at the bottom of the page and shows the property type and a short description of the property.</span></span> <span data-ttu-id="25b5e-123">Sie können die Beschreibung der Eigenschaft ein- und ausschalten, indem Sie den Befehl **Beschreibung** im Kontextmenü verwenden.</span><span class="sxs-lookup"><span data-stu-id="25b5e-123">You can turn the description of the property off and on using the **Description** command on the shortcut menu.</span></span>|  
  
  
