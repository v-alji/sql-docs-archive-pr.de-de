---
title: Daten-Viewer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataviewer.f1
helpviewer_keywords:
- Data Viewer dialog box
ms.assetid: 6351309a-688f-4e82-9697-1712130f10a1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dc576981e875eade84dd3576f4ed93b66784411f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618821"
---
# <a name="data-viewer"></a><span data-ttu-id="53e64-102">Daten-Viewer</span><span class="sxs-lookup"><span data-stu-id="53e64-102">Data Viewer</span></span>
  <span data-ttu-id="53e64-103">Wenn ein Pfad zu einem Daten-Viewer konfiguriert ist, zeigt dieser Daten-Viewer die Daten pufferweise an, während sie zwischen zwei Datenflusskomponenten fließen.</span><span class="sxs-lookup"><span data-stu-id="53e64-103">If a path is configured to use a data viewer, the Data Viewer displays the data buffer by buffer as data moves between two data flow components.</span></span>  
  
## <a name="options"></a><span data-ttu-id="53e64-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="53e64-104">Options</span></span>  
 <span data-ttu-id="53e64-105">**Grüner Pfeil**</span><span class="sxs-lookup"><span data-stu-id="53e64-105">**Green arrow**</span></span>  
 <span data-ttu-id="53e64-106">Klicken Sie auf den Pfeil, um die Daten des nächsten Puffers anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="53e64-106">Click to display the data in the next buffer.</span></span> <span data-ttu-id="53e64-107">Wenn die Daten in einem einzigen Puffer verschoben werden können, ist diese Option nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="53e64-107">If the data can be moved in a single buffer, this option is not available.</span></span>  
  
 <span data-ttu-id="53e64-108">**Trennen**</span><span class="sxs-lookup"><span data-stu-id="53e64-108">**Detach**</span></span>  
 <span data-ttu-id="53e64-109">Trennt den Daten-Viewer.</span><span class="sxs-lookup"><span data-stu-id="53e64-109">Detach the data viewer.</span></span>  
  
 <span data-ttu-id="53e64-110">**Hinweis** Durch das Trennen des Daten-Viewers wird dieser nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="53e64-110">**Note** Detaching a data viewer does not delete the data viewer.</span></span> <span data-ttu-id="53e64-111">Wenn der Daten-Viewer getrennt wurde, fließen die Daten weiterhin durch den Pfad, aber der Daten-Viewer wird nicht mehr aktualisiert, um die Daten in den einzelnen Puffern anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="53e64-111">If the data viewer has been detached, data continues to flow through the path, but the data in the viewer is not updated to match the data in each buffer.</span></span>  
  
 <span data-ttu-id="53e64-112">**Anfügen**</span><span class="sxs-lookup"><span data-stu-id="53e64-112">**Attach**</span></span>  
 <span data-ttu-id="53e64-113">Fügt einen Daten-Viewer an.</span><span class="sxs-lookup"><span data-stu-id="53e64-113">Attach a data viewer.</span></span>  
  
 <span data-ttu-id="53e64-114">**Hinweis** Wenn der Daten-Viewer angefügt wird, zeigt er die Informationen der einzelnen Puffer des Datenflusses an und hält dann an.</span><span class="sxs-lookup"><span data-stu-id="53e64-114">**Note** When the data viewer is attached, it displays information from each buffer in the data flow and then pauses.</span></span> <span data-ttu-id="53e64-115">Mithilfe des grünen Pfeils können Sie durch die einzelnen Puffer klicken.</span><span class="sxs-lookup"><span data-stu-id="53e64-115">You can advance through the buffers by using the green arrow.</span></span>  
  
 <span data-ttu-id="53e64-116">**Daten kopieren**</span><span class="sxs-lookup"><span data-stu-id="53e64-116">**Copy Data**</span></span>  
 <span data-ttu-id="53e64-117">Kopiert die Daten des aktuellen Puffers in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="53e64-117">Copy data in the current buffer to the Clipboard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53e64-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="53e64-118">See Also</span></span>  
 [<span data-ttu-id="53e64-119">Debuggen des Datenflusses</span><span class="sxs-lookup"><span data-stu-id="53e64-119">Debugging Data Flow</span></span>](../troubleshooting/debugging-data-flow.md)  
  
  
