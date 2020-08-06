---
title: Entfernen von Spalten aus einer Mining Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], columns
- removing columns
- deleting columns
- columns [data mining], mining structure columns
ms.assetid: 41073ffe-9351-416b-9f0c-62634bc213f9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44ad1de08d57d00fd9798e1ceeddb85d146d7111
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608094"
---
# <a name="remove-columns-from-a-mining-structure"></a><span data-ttu-id="69bc1-102">Entfernen von Spalten aus einer Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="69bc1-102">Remove Columns from a Mining Structure</span></span>
  <span data-ttu-id="69bc1-103">Sie können mit dem Data Mining-Designer Spalten aus einer Miningstruktur entfernen, nachdem die Struktur bereits erstellt worden ist.</span><span class="sxs-lookup"><span data-stu-id="69bc1-103">You can use Data Mining Designer to remove columns from a mining structure after the structure has already been created.</span></span> <span data-ttu-id="69bc1-104">Folgende Gründe könnten dafür sprechen, eine Miningstrukturspalte zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="69bc1-104">Reasons to remove a mining structure column might include the following:</span></span>  
  
-   <span data-ttu-id="69bc1-105">Die Miningstruktur enthält mehrere Kopien einer Spalte, und Sie möchten die Verwendung doppelter Daten in einem Modell vermeiden.</span><span class="sxs-lookup"><span data-stu-id="69bc1-105">The mining structure contains multiple copies of a column and you want to avoid the use of duplicate data in a model.</span></span>  
  
-   <span data-ttu-id="69bc1-106">Die Daten sollten geschützt werden, doch Drillthrough wurde aktiviert.</span><span class="sxs-lookup"><span data-stu-id="69bc1-106">The data should be protected, but drillthrough has been enabled.</span></span>  
  
-   <span data-ttu-id="69bc1-107">Die Daten werden nicht für Modellierungen verwendet und sollten nicht verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="69bc1-107">The data is unused in modeling and should not be processed.</span></span>  
  
 <span data-ttu-id="69bc1-108">Durch Löschen einer Spalte aus der Miningstruktur wird die Spalte in der Datenquellensicht oder in den externen Daten nicht geändert. Nur Metadaten werden gelöscht.</span><span class="sxs-lookup"><span data-stu-id="69bc1-108">Deleting a column from the mining structure does not change the column in the data source view or in the external data; only metadata is deleted.</span></span> <span data-ttu-id="69bc1-109">Wenn Sie jedoch die Spalten ändern, die in einer Miningstruktur verwendet werden, müssen Sie die Struktur und alle darauf basierenden Modelle erneut verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="69bc1-109">However, when you change the columns used in a mining structure, you must reprocess the structure and any models based on it.</span></span>  
  
### <a name="to-remove-a-column-from-the-mining-structure"></a><span data-ttu-id="69bc1-110">So entfernen Sie eine Spalte aus der Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="69bc1-110">To remove a column from the mining structure</span></span>  
  
1.  <span data-ttu-id="69bc1-111">Wählen Sie im Data Mining-Designer die Registerkarte **Miningstruktur** aus.</span><span class="sxs-lookup"><span data-stu-id="69bc1-111">Select the **Mining Structure** tab in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="69bc1-112">Erweitern Sie die Struktur für die Miningstruktur, um alle Spalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="69bc1-112">Expand the tree for the mining structure, to show all the columns.</span></span>  
  
3.  <span data-ttu-id="69bc1-113">Klicken Sie mit der rechten Maustaste auf die Spalte, die Sie löschen möchten, und wählen Sie anschließend **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="69bc1-113">Right-click the column that you want to delete, and then select **Delete**.</span></span>  
  
4.  <span data-ttu-id="69bc1-114">Klicken Sie im Dialogfeld **Objekte löschen** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="69bc1-114">In the **Delete Objects** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69bc1-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="69bc1-115">See Also</span></span>  
 [<span data-ttu-id="69bc1-116">Tasks und Anweisungen für Miningstrukturen</span><span class="sxs-lookup"><span data-stu-id="69bc1-116">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
