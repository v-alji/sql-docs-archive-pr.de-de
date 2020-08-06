---
title: Hinzufügen von Spalten zu einer Mining Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], columns
- columns [data mining], mining structure columns
- adding columns
ms.assetid: 3f879344-9f66-4178-851a-e8c5ccccf4cb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 093d78b36ab3aae6600b890a8137025c9dc9134e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620061"
---
# <a name="add-columns-to-a-mining-structure"></a><span data-ttu-id="b02c1-102">Hinzufügen von Spalten zu einer Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="b02c1-102">Add Columns to a Mining Structure</span></span>
  <span data-ttu-id="b02c1-103">Mit dem Data Mining-Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] können Sie einer Miningstruktur Spalten hinzufügen, nachdem Sie die Miningstruktur im Data Mining-Assistenten erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="b02c1-103">Use Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to add columns to a mining structure after you have defined it in the Data Mining Wizard.</span></span> <span data-ttu-id="b02c1-104">Sie können jede Spalte hinzufügen, die in der zum Definieren der Miningstruktur verwendeten Datenquellensicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b02c1-104">You can add any column that exists in the data source view that was used to define the mining structure.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b02c1-105">Sie können einer Miningstruktur mehrere Kopien von Spalten hinzufügen. Sie sollten jedoch nicht mehrere Instanzen der Spalte innerhalb desselben Modells verwenden, um falsche Korrelationen zwischen der Quelle und der abgeleiteten Spalte zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="b02c1-105">You can add multiple copies of columns to a mining structure; however, you should avoid using more than one instance of the column within the same model, to avoid false correlations between the source and the derived column.</span></span>  
  
### <a name="to-add-a-column-to-a-mining-structure"></a><span data-ttu-id="b02c1-106">So fügen Sie einer Miningstruktur eine Spalte hinzu</span><span class="sxs-lookup"><span data-stu-id="b02c1-106">To add a column to a mining structure</span></span>  
  
1.  <span data-ttu-id="b02c1-107">Wählen Sie im Data Mining-Designer die Registerkarte **Miningstruktur** aus.</span><span class="sxs-lookup"><span data-stu-id="b02c1-107">Select the **Mining Structure** tab in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="b02c1-108">Klicken Sie mit der rechten Maustaste auf die Miningstruktur, und klicken Sie anschließend auf **Spalte hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b02c1-108">Right-click the mining structure and select **Add a Column**.</span></span>  
  
     <span data-ttu-id="b02c1-109">Das Dialogfeld **Spalte auswählen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="b02c1-109">The **Select a Column** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="b02c1-110">Wählen Sie unter **Quelltabelle**die Tabelle in der Datenquellensicht aus, in der sich die Spalte befindet.</span><span class="sxs-lookup"><span data-stu-id="b02c1-110">Under **Source table**, select the table in the data source view where the column resides.</span></span>  
  
4.  <span data-ttu-id="b02c1-111">Wählen Sie unter **Quellspalte**die Spalte aus, die Sie der Miningstruktur hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="b02c1-111">Under **Source column**, select the column that you want to add to the mining structure.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
> [!NOTE]  
>  <span data-ttu-id="b02c1-112">Wenn Sie eine bereits vorhandene Spalte hinzufügen, wird eine Kopie in die Struktur einbezogen, und dem Namen der Spalte wird dabei eine "1" angehängt.</span><span class="sxs-lookup"><span data-stu-id="b02c1-112">If you add a column that already exists, a copy will be included in the structure, and the name appended with a "1".</span></span> <span data-ttu-id="b02c1-113">Sie können den Namen der kopierten Spalte in einen aussagekräftigeren Namen ändern, indem Sie einen neuen Namen in die **Name** -Eigenschaft der Miningstruktur-Spalte eingeben.</span><span class="sxs-lookup"><span data-stu-id="b02c1-113">You can change the name of the copied column to something more descriptive by typing a new name in the **Name** property of the mining structure column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b02c1-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b02c1-114">See Also</span></span>  
 [<span data-ttu-id="b02c1-115">Tasks und Anweisungen für Miningstrukturen</span><span class="sxs-lookup"><span data-stu-id="b02c1-115">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
