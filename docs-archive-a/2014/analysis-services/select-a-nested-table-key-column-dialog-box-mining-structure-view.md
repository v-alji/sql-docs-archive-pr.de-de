---
title: Schlüssel Spalte für eine Schlüssel Spalte auswählen (Dialog Feld) (Mining Struktur-Ansicht) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.structure.addnestedtable.f1
helpviewer_keywords:
- Select a Nested Table Key Column dialog box
ms.assetid: f68b89a7-17df-45f8-ba7f-b458cd9b1ec3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4dc524f6913b7be15e87869355515397a3e0b65c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620567"
---
# <a name="select-a-nested-table-key-column-dialog-box-mining-structure-view"></a><span data-ttu-id="b01dd-102">Schlüsselspalte für eine geschachtelte Tabelle auswählen (Dialogfeld) (Miningstruktur-Ansicht)</span><span class="sxs-lookup"><span data-stu-id="b01dd-102">Select a Nested Table Key Column Dialog Box (Mining Structure View)</span></span>
  <span data-ttu-id="b01dd-103">Verwenden Sie das Dialogfeld **Schlüsselspalte für eine geschachtelte Tabelle auswählen** , um eine Spalte zu bestimmen, die als Schlüssel für die neue geschachtelte Tabelle fungieren soll.</span><span class="sxs-lookup"><span data-stu-id="b01dd-103">Use the **Select a Nested Table Key Column** dialog box to designate a column that will act as the key for the new nested table.</span></span> <span data-ttu-id="b01dd-104">Sobald Sie das Dialogfeld schließen, wird der Miningstruktur eine neue Tabelle mit der designierten Schlüsselspalte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b01dd-104">When you exit the dialog box, a new table is added to the mining structure that contains the designated key column.</span></span> <span data-ttu-id="b01dd-105">Sie können der geschachtelten Tabelle zusätzliche Spalten hinzufügen, indem Sie mit der rechten Maustaste auf die Struktur klicken und dann auf **Spalte hinzufügen**klicken.</span><span class="sxs-lookup"><span data-stu-id="b01dd-105">You can add additional columns to the nested table by right-clicking the structure and selecting **Add a Column**.</span></span> <span data-ttu-id="b01dd-106">Das Dialogfeld enthält unterschiedliche Optionen, abhängig davon, ob Sie mit einem OLAP-Miningmodell oder einem relationalen Miningmodell arbeiten.</span><span class="sxs-lookup"><span data-stu-id="b01dd-106">The dialog box contains different options depending on whether you are working with an OLAP mining model or a relational mining model.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b01dd-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="b01dd-107">Options</span></span>  
 <span data-ttu-id="b01dd-108">**Quell Tabelle**</span><span class="sxs-lookup"><span data-stu-id="b01dd-108">**Source table**</span></span>  
 <span data-ttu-id="b01dd-109">Die Tabelle, auf der das Miningmodell basiert.</span><span class="sxs-lookup"><span data-stu-id="b01dd-109">The table on which the mining model is based.</span></span>  
  
 <span data-ttu-id="b01dd-110">Diese Option wird nur bei relationalen Miningmodellen verwendet.</span><span class="sxs-lookup"><span data-stu-id="b01dd-110">This is only used for relational mining models.</span></span>  
  
 <span data-ttu-id="b01dd-111">**Quell Spalte**</span><span class="sxs-lookup"><span data-stu-id="b01dd-111">**Source column**</span></span>  
 <span data-ttu-id="b01dd-112">Eine Liste aller verfügbaren Spalten in der Quelltabelle, die Sie als Schlüssel der geschachtelten Tabelle verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b01dd-112">A list of all the available columns in the source table that you can use as the key of the nested table.</span></span>  
  
 <span data-ttu-id="b01dd-113">Diese Option wird nur bei relationalen Miningmodellen verwendet.</span><span class="sxs-lookup"><span data-stu-id="b01dd-113">This is only used for relational mining models.</span></span>  
  
 <span data-ttu-id="b01dd-114">**Spaltentypen anzeigen**</span><span class="sxs-lookup"><span data-stu-id="b01dd-114">**Show column types**</span></span>  
 <span data-ttu-id="b01dd-115">Eine Liste der für die Spalten verfügbaren Datentypen.</span><span class="sxs-lookup"><span data-stu-id="b01dd-115">A list of available column data types.</span></span> <span data-ttu-id="b01dd-116">Wählen Sie Datentypen aus, bzw. machen Sie die Auswahl rückgängig, um die Liste der Spalten in **Quellspalte**zu filtern.</span><span class="sxs-lookup"><span data-stu-id="b01dd-116">Select or clear data types to filter the list of columns in **Source column**.</span></span> <span data-ttu-id="b01dd-117">In der Liste **Quellspalte** werden nur die Spalten angezeigt, die mit den ausgewählten Datentypen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="b01dd-117">Only columns that match the checked data types will be shown in the **Source column** list.</span></span>  
  
 <span data-ttu-id="b01dd-118">Diese Option wird nur bei relationalen Miningmodellen verwendet.</span><span class="sxs-lookup"><span data-stu-id="b01dd-118">This is only used for relational mining models.</span></span>  
  
 <span data-ttu-id="b01dd-119">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="b01dd-119">**Attributes**</span></span>  
 <span data-ttu-id="b01dd-120">Eine Liste der Attribute, die Sie als Schlüssel der geschachtelten Tabelle verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b01dd-120">A list of attributes that you can use as the key of the nested table.</span></span>  
  
 <span data-ttu-id="b01dd-121">Diese Option wird nur bei OLAP-Miningmodellen verwendet.</span><span class="sxs-lookup"><span data-stu-id="b01dd-121">This is only used for OLAP mining models.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b01dd-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b01dd-122">See Also</span></span>  
 [<span data-ttu-id="b01dd-123">Mining Strukturansicht &#40;Data Mining-Modell-Designer&#41;</span><span class="sxs-lookup"><span data-stu-id="b01dd-123">Mining Structure View &#40;Data Mining Model Designer&#41;</span></span>](mining-structure-view-data-mining-model-designer.md)  
  
  
