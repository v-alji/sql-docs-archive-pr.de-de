---
title: Definieren von Filtern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replconflictviewer.definefilters.f1
helpviewer_keywords:
- Define Filters dialog box
ms.assetid: 1fa71d22-ce5a-4aae-ba05-4d755842aeac
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5154f002c5a35bc78e2eb6777f2cc7bb3d56b635
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609139"
---
# <a name="define-filters"></a><span data-ttu-id="17ff8-102">Filter definieren</span><span class="sxs-lookup"><span data-stu-id="17ff8-102">Define Filters</span></span>
  <span data-ttu-id="17ff8-103">Im Dialogfeld **Filter definieren** können Sie Filter definieren, die Sie anschließend bei Datenkonflikten anwenden, um eine Untermenge der Konflikte im Raster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="17ff8-103">The **Define Filters** dialog box allows you to define filters that you then apply to data conflicts to see a subset of the conflicts in the grid.</span></span> <span data-ttu-id="17ff8-104">Um einen Filter zu definieren, wählen Sie im Dropdownlistenfeld **Operator** einen Operator aus, und geben Sie dann einen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="17ff8-104">To define a filter, choose an operator from the **Operator** drop-down list box and then enter a value.</span></span> <span data-ttu-id="17ff8-105">Um beispielsweise nur die Konflikte anzuzeigen, in welchen Server **ReplTest1**der Konfliktverlierer ist, wählen Sie im Dropdown-Listenfeld **Operator** die Option **Gleich** aus, und geben Sie in die erste **Value** -Spalte den Wert **ReplTest1** ein.</span><span class="sxs-lookup"><span data-stu-id="17ff8-105">For example, to show only those conflicts in which the conflict loser is server **ReplTest1**, select **Equal to** from the **Operator** drop-down list box and enter **ReplTest1** in the first **Value** column.</span></span>  
  
## <a name="options"></a><span data-ttu-id="17ff8-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="17ff8-106">Options</span></span>  
 <span data-ttu-id="17ff8-107">**Operator**</span><span class="sxs-lookup"><span data-stu-id="17ff8-107">**Operator**</span></span>  
 <span data-ttu-id="17ff8-108">Wählen Sie für den Filter einen Operator wie **Kleiner als oder gleich**aus.</span><span class="sxs-lookup"><span data-stu-id="17ff8-108">Select an operator for the filter, such as **Less than or Equal to**.</span></span>  
  
 <span data-ttu-id="17ff8-109">**Wert**</span><span class="sxs-lookup"><span data-stu-id="17ff8-109">**Value**</span></span>  
 <span data-ttu-id="17ff8-110">Geben Sie einen Wert für den Filter ein.</span><span class="sxs-lookup"><span data-stu-id="17ff8-110">Enter a value for the filter.</span></span> <span data-ttu-id="17ff8-111">Für die meisten Operatoren muss nur in der ersten **Value** -Spalte ein Wert eingegeben werden. Für die Operatoren **Zwischen** und **Nicht zwischen** muss jedoch in beide **Value** -Spalten ein Wert eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="17ff8-111">Most operators only require a value in the first **Value** column, but the **Between** and **Not Between** operators require a value in both of the **Value** columns.</span></span>  
  
 <span data-ttu-id="17ff8-112">**Clear**</span><span class="sxs-lookup"><span data-stu-id="17ff8-112">**Clear**</span></span>  
 <span data-ttu-id="17ff8-113">Klicken Sie auf diese Schaltfläche, um alle zuvor definierten Filter zu löschen.</span><span class="sxs-lookup"><span data-stu-id="17ff8-113">Click this button to clear all filters that have been previously defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17ff8-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="17ff8-114">See Also</span></span>  
 <span data-ttu-id="17ff8-115">[Replikationskonflikt-Viewer von Microsoft &#40;Mergereplikation&#41;](microsoft-replication-conflict-viewer-merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="17ff8-115">[Microsoft Replication Conflict Viewer &#40;Merge Replication&#41;](microsoft-replication-conflict-viewer-merge-replication.md) </span></span>  
 [<span data-ttu-id="17ff8-116">Replikationskonflikt-Viewer von Microsoft &#40;Transaktionsreplikation&#41;</span><span class="sxs-lookup"><span data-stu-id="17ff8-116">Microsoft Replication Conflict Viewer &#40;Transactional Replication&#41;</span></span>](microsoft-replication-conflict-viewer-transactional-replication.md)  
  
  
