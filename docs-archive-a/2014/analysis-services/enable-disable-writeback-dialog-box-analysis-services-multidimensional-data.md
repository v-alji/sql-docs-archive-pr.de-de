---
title: Dialog Feld zum Aktivieren des Rück Schreibens aktivieren (Analysis Services Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitiondesigner.writebackenabledisable.f1
ms.assetid: 2d254393-3f0d-4b70-8b98-87159f9f3639
author: minewiskan
ms.author: owend
ms.openlocfilehash: 54ee4597ee78f45682730bd0e8d7119d204eaf2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622927"
---
# <a name="enable-disable-writeback-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="b3997-102">Aktivieren: Dialog Feld "Rück schreiben deaktivieren" (Analysis Services Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="b3997-102">Enable-Disable Writeback Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="b3997-103">Im Dialogfeld **Rückschreiben aktivieren/deaktivieren** wird das Rückschreiben für eine Measuregruppe in einem Cube aktiviert oder deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b3997-103">The **Enable/Disable Writeback** dialog box enables or disables writeback for a measure group in a cube.</span></span> <span data-ttu-id="b3997-104">Wenn Sie das Rückschreiben für eine Measuregruppe aktivieren, wird eine Rückschreibepartition definiert und eine Rückschreibetabelle für die Measuregruppe erstellt.</span><span class="sxs-lookup"><span data-stu-id="b3997-104">Enabling writeback on a measure group defines a writeback partition and creates a writeback table for that measure group.</span></span> <span data-ttu-id="b3997-105">Wenn Sie das Rückschreiben für eine Measuregruppe deaktivieren, wird die Rückschreibepartition entfernt; die Rückschreibetabelle wird jedoch nicht gelöscht, um einen unerwarteten Datenverlust zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="b3997-105">Disabling writeback on a measure group removes the writeback partition but does not delete the writeback table, to avoid unanticipated data loss.</span></span> <span data-ttu-id="b3997-106">Das Dialogfeld **Rückschreiben aktivieren/deaktivieren** kann folgendermaßen angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="b3997-106">The **Enable/Disable Writeback** dialog box is displayed by:</span></span>  
  
-   <span data-ttu-id="b3997-107">Klicken Sie im Cube-Designer auf der Registerkarte **Partitionen** im Bereich **Measuregruppen** auf **Rückschreibeeinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="b3997-107">Clicking **Writeback Settings** in the **Measure Groups** pane on the **Partitions** tab in Cube Designer.</span></span>  
  
-   <span data-ttu-id="b3997-108">Klicken Sie im Cube-Designer auf der Registerkarte **Partitionen** im Bereich **Measuregruppen** im Raster **Partitionen** mit der rechten Maustaste auf eine Partition, und wählen Sie im Kontextmenü **Rückschreibeeinstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="b3997-108">Right-clicking a partition in the **Partitions** grid in the **Measure Groups** pane on the **Partitions** tab in Cube Designer and selecting **Writeback Settings** from the context menu.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b3997-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="b3997-109">Options</span></span>  
 <span data-ttu-id="b3997-110">**Tabellenname**</span><span class="sxs-lookup"><span data-stu-id="b3997-110">**Table name**</span></span>  
 <span data-ttu-id="b3997-111">Geben Sie den Namen der Rückschreibetabelle ein, die für die ausgewählte Partition erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b3997-111">Type the name of the writeback table to create for the selected partition.</span></span> <span data-ttu-id="b3997-112">Die Rückschreibetabelle speichert die Änderungen, die an der Measuregruppe von einer Clientanwendung aus durchgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="b3997-112">The writeback table stores the changes made to the measure group from a client application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b3997-113">Diese Option ist deaktiviert, wenn das Rückschreiben nicht aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="b3997-113">This option is disabled if writeback is not enabled.</span></span>  
  
 <span data-ttu-id="b3997-114">**Datenquelle**</span><span class="sxs-lookup"><span data-stu-id="b3997-114">**Data source**</span></span>  
 <span data-ttu-id="b3997-115">Wählen Sie die Datenquelle zum Speichern der Rückschreibetabelle aus.</span><span class="sxs-lookup"><span data-stu-id="b3997-115">Select the data source to contain the writeback table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b3997-116">Diese Option ist deaktiviert, wenn das Rückschreiben nicht aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="b3997-116">This option is disabled if writeback is not enabled.</span></span>  
  
 <span data-ttu-id="b3997-117">**Neu**</span><span class="sxs-lookup"><span data-stu-id="b3997-117">**New**</span></span>  
 <span data-ttu-id="b3997-118">Klicken Sie auf diese Option, um das Dialogfeld **Verbindungs-Manager** anzuzeigen, und definieren Sie eine neue Datenquelle, die die Rückschreibetabelle enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="b3997-118">Click to display the **Connection Manager** dialog box and define a new data source to contain the writeback table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b3997-119">Diese Option ist deaktiviert, wenn das Rückschreiben nicht aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="b3997-119">This option is disabled if writeback is not enabled.</span></span>  
  
  
