---
title: Schnelle Analyse festlegen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: dcd1dc09-6eaf-440b-9ce6-fef779ff794f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e6ff2c6ecd536dd5ecc34dceb358ffcf578ff3a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607897"
---
# <a name="set-fast-parse"></a><span data-ttu-id="99f78-102">Festlegen der schnellen Analyse</span><span class="sxs-lookup"><span data-stu-id="99f78-102">Set Fast Parse</span></span>
  <span data-ttu-id="99f78-103">Die Fast Parse-Eigenschaft muss für jede Spalte der Quelle oder Transformation festgelegt werden, die die schnelle Analyse verwendet.</span><span class="sxs-lookup"><span data-stu-id="99f78-103">The fast parse property must be set for each column of the source or transformation that uses fast parse.</span></span> <span data-ttu-id="99f78-104">Verwenden Sie zum Festlegen der Eigenschaft den Erweiterten Editor der Flatfilequelle und der Transformation für Datenkonvertierung.</span><span class="sxs-lookup"><span data-stu-id="99f78-104">To set the property, use the Advanced editor of the Flat File source and Data Conversion transformation.</span></span>  
  
### <a name="to-set-fast-parse"></a><span data-ttu-id="99f78-105">So legen Sie die schnelle Analyse fest</span><span class="sxs-lookup"><span data-stu-id="99f78-105">To set fast parse</span></span>  
  
1.  <span data-ttu-id="99f78-106">Klicken Sie mit der rechten Maustaste auf die Flatfilequelle bzw. die Transformation für Datenkonvertierung, und klicken Sie anschließend auf **Erweiterten Editor anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="99f78-106">Right-click the Flat File source or Data Conversion transformation, and then click **Show Advanced Editor**.</span></span>  
  
2.  <span data-ttu-id="99f78-107">Klicken Sie im Dialogfeld **Erweiterter Editor** auf die Registerkarte **Eingabe- und Ausgabeeigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="99f78-107">In the **Advanced Editor** dialog box, click the **Input and Output Properties** tab.</span></span>  
  
3.  <span data-ttu-id="99f78-108">Klicken Sie im Bereich **Eingaben und Ausgaben** auf die Spalte, für die die schnelle Analyse aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="99f78-108">In the **Inputs and Outputs** pane, click the column for which you want to enable fast parse.</span></span>  
  
4.  <span data-ttu-id="99f78-109">Erweitern Sie im Eigenschaftenfenster den Knoten **benutzerdefinierte Eigenschaften** , und legen Sie dann die- `FastParse` Eigenschaft auf fest `True` .</span><span class="sxs-lookup"><span data-stu-id="99f78-109">In the Properties window, expand the **Custom Properties** node, and then set the `FastParse` property to `True`.</span></span>  
  
5.  <span data-ttu-id="99f78-110">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="99f78-110">Click **OK**.</span></span>  
  
  
