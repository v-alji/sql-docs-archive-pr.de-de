---
title: Editor zum Auflösen von Spaltenverweisen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.resolvereferences.mapper.F1
- sql12.dts.designer.resolvereferences.preview.F1
ms.assetid: bb3ee33c-79c4-4c76-a82f-71581b4a60f1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 600b6f4d5ec12290d654f0854cc548a5bbcf4335
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618817"
---
# <a name="resolve-column-reference-editor"></a><span data-ttu-id="9637e-102">Editor zum Auflösen von Spaltenverweisen</span><span class="sxs-lookup"><span data-stu-id="9637e-102">Resolve Column Reference Editor</span></span>
  <span data-ttu-id="9637e-103">Wenn ein Eingabepfad getrennt wurde, oder nicht zugeordnete Spalten im Pfad vorhanden sind, wird neben dem entsprechenden Datenpfad ein Fehlersymbol angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9637e-103">When an input path is disconnected or if there are any unmapped columns in the path, an error icon is displayed beside the corresponding data path.</span></span> <span data-ttu-id="9637e-104">Der neue Editor zum Auflösen von Verweisen ermöglicht es, für alle Pfade in der Ausführungsstruktur nicht zugeordnete Eingabespalten mit zugeordneten Ausgabespalten zu verknüpfen, und vereinfacht dadurch die Lösung von Spaltenverweisfehlern.</span><span class="sxs-lookup"><span data-stu-id="9637e-104">To simplify the resolution of column reference errors, the new Resolve References editor allows you to link unmapped output columns with unmapped input columns for all paths in the execution tree.</span></span> <span data-ttu-id="9637e-105">Der Editor zum Auflösen von Verweisen markiert auch die Pfade, um zu kennzeichnen, welche Pfade aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="9637e-105">The Resolve References editor will also highlight the paths to indicate which paths are being resolved.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9637e-106">Es ist nun möglich, eine Komponente zu bearbeiten, selbst wenn deren Eingabepfad getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="9637e-106">It is now possible to edit a component even when its input path is disconnected</span></span>  
  
 <span data-ttu-id="9637e-107">Nachdem alle Spaltenverweise aufgelöst wurden und keine weiteren Datenpfadfehler auftreten, werden neben den Datenpfaden keine Fehlersymbole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9637e-107">After all column references have been resolved, if there are no other data path errors, no error icons will be displayed beside the data paths.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9637e-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="9637e-108">Options</span></span>  
 <span data-ttu-id="9637e-109">Nicht zugeordnete Ausgabespalten (Quelle):</span><span class="sxs-lookup"><span data-stu-id="9637e-109">Unmapped Output Columns (Source):</span></span>  
 <span data-ttu-id="9637e-110">Spalten vom Upstreampfad, die derzeit nicht zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="9637e-110">Columns from the upstream path that are not currently mapped</span></span>  
  
 <span data-ttu-id="9637e-111">Zugeordnete Spalten (Quelle):</span><span class="sxs-lookup"><span data-stu-id="9637e-111">Mapped Columns (Source):</span></span>  
 <span data-ttu-id="9637e-112">Spalten vom Upstreampfad, die Spalten vom Downstreampfad zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="9637e-112">Columns from the upstream path that are mapped to columns from the downstream path</span></span>  
  
 <span data-ttu-id="9637e-113">Zugeordnete Spalten (Ziel):</span><span class="sxs-lookup"><span data-stu-id="9637e-113">Mapped Columns (Destination):</span></span>  
 <span data-ttu-id="9637e-114">Spalten vom Upstreampfad, die Spalten vom Downstreampfad zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="9637e-114">Columns from the upstream path that are mapped to columns from the downstream path</span></span>  
  
 <span data-ttu-id="9637e-115">Nicht zugeordnete Eingabespalten (Ziel):</span><span class="sxs-lookup"><span data-stu-id="9637e-115">Unmapped Input Columns (Destination):</span></span>  
 <span data-ttu-id="9637e-116">Spalten vom Downstreampfad, die derzeit nicht zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="9637e-116">Columns from the downstream path that are not currently mapped</span></span>  
  
 <span data-ttu-id="9637e-117">Nicht zugeordnete Eingabespalten löschen</span><span class="sxs-lookup"><span data-stu-id="9637e-117">Delete Unmapped Input Columns</span></span>  
 <span data-ttu-id="9637e-118">Aktivieren Sie "Nicht zugeordnete Eingabespalten löschen", um nicht zugeordnete Spalten am Ziel des Datenpfads zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="9637e-118">Check Delete Unmapped Input Columns to ignore unmapped columns at the destination of the data path.</span></span> <span data-ttu-id="9637e-119">Die Schaltfläche "Vorschau der Änderungen" zeigt eine Liste der Änderungen an, die auftreten, wenn Sie auf die Schaltfläche "OK" klicken.</span><span class="sxs-lookup"><span data-stu-id="9637e-119">The Preview Changes button displays a list of the changes that will occur when you press the OK button.</span></span>  
  
  
