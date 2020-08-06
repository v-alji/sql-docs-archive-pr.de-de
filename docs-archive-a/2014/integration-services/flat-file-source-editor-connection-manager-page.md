---
title: Quellen-Editor für Flatfiles (Seite Verbindungs-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfilesourceadapter.connection.f1
helpviewer_keywords:
- Flat File Source Editor
ms.assetid: 2efd6baa-ed75-4f3f-b667-514024cebdb8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 03c1693c001dad2c8e90211b065eda208c42a07b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609345"
---
# <a name="flat-file-source-editor-connection-manager-page"></a><span data-ttu-id="525c0-102">Quellen-Editor für Flatfiles (Seite Verbindungs-Manager)</span><span class="sxs-lookup"><span data-stu-id="525c0-102">Flat File Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="525c0-103">Wählen Sie auf der Seite **Verbindungs-Manager** des Dialogfelds **Quellen-Editor für Flatfiles** den Verbindungs-Manager aus, den die Flatfilequelle verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="525c0-103">Use the **Connection Manager** page of the **Flat File Source Editor** dialog box to select the connection manager that the Flat File source will use.</span></span> <span data-ttu-id="525c0-104">Die Flatfilequelle liest die Daten aus einer Textdatei, die in den Formaten mit Trennzeichen, fester Breite oder mit gemischten Inhalten vorliegen kann.</span><span class="sxs-lookup"><span data-stu-id="525c0-104">The Flat File source reads data from a text file, which can be in a delimited, fixed width, or mixed format.</span></span>  
  
 <span data-ttu-id="525c0-105">Eine Flatfilequelle kann einen der folgenden Typen von Verbindungs-Manager verwenden:</span><span class="sxs-lookup"><span data-stu-id="525c0-105">A Flat File source can use one of the following types of connection managers:</span></span>  
  
-   <span data-ttu-id="525c0-106">Einen Verbindungs-Manager für Flatfiles, wenn es sich bei der Quelle um eine einzelne Flatfile handelt.</span><span class="sxs-lookup"><span data-stu-id="525c0-106">A Flat File connection manager if the source is a single flat file.</span></span> <span data-ttu-id="525c0-107">Weitere Informationen finden Sie unter [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="525c0-107">For more information, see [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span></span>  
  
-   <span data-ttu-id="525c0-108">Einen Verbindungs-Manager für mehrere Flatfiles, wenn es bei der Quelle um mehrere Flatfiles handelt und der Datenflusstask sich in einem Schleifencontainer wie dem For-Schleifencontainer befindet.</span><span class="sxs-lookup"><span data-stu-id="525c0-108">A Multiple Flat Files connection manager if the source is multiple flat files and the Data Flow task is inside a loop container, such as the For Loop container.</span></span> <span data-ttu-id="525c0-109">In jeder Schleife des Containers werden von der Flatfilequelle Daten vom nächsten Dateinamen geladen, der vom Verbindungs-Manager für mehrere Flatfiles bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="525c0-109">On each loop of the container, the Flat File source loads data from the next file name that the Multiple Flat Files connection manager provides.</span></span> <span data-ttu-id="525c0-110">Weitere Informationen finden Sie unter [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="525c0-110">For more information, see [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span></span>  
  
 <span data-ttu-id="525c0-111">Weitere Informationen zur Flatfilequelle finden Sie unter [Flat File Source](data-flow/flat-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="525c0-111">To learn more about the Flat File source, see [Flat File Source](data-flow/flat-file-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="525c0-112">Tastatur</span><span class="sxs-lookup"><span data-stu-id="525c0-112">Options</span></span>  
 <span data-ttu-id="525c0-113">**Verbindungs-Manager für Flatfiles**</span><span class="sxs-lookup"><span data-stu-id="525c0-113">**Flat file connection manager**</span></span>  
 <span data-ttu-id="525c0-114">Wählen Sie einen vorhandenen Verbindungs-Manager aus der Liste aus, oder erstellen Sie einen neuen Verbindungs-Manager, indem Sie auf **Neu**klicken.</span><span class="sxs-lookup"><span data-stu-id="525c0-114">Select an existing connection manager from the list, or create a new connection manager by clicking **New**.</span></span>  
  
 <span data-ttu-id="525c0-115">**Neu**</span><span class="sxs-lookup"><span data-stu-id="525c0-115">**New**</span></span>  
 <span data-ttu-id="525c0-116">Erstellen Sie mithilfe des Dialogfelds **Verbindungs-Manager-Editor für Flatfiles** einen neuen Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="525c0-116">Create a new connection manager by using the **Flat File Connection Manager Editor** dialog box.</span></span>  
  
 <span data-ttu-id="525c0-117">**NULL-Werte aus der Quelle als NULL-Werte im Datenfluss beibehalten**</span><span class="sxs-lookup"><span data-stu-id="525c0-117">**Retain null values from the source as null values in the data flow**</span></span>  
 <span data-ttu-id="525c0-118">Geben Sie an, ob NULL-Werte erhalten werden, wenn Daten extrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="525c0-118">Specify whether to keep null values when data is extracted.</span></span> <span data-ttu-id="525c0-119">Der Standardwert dieser Eigenschaft ist **false**.</span><span class="sxs-lookup"><span data-stu-id="525c0-119">The default value of this property is **false**.</span></span> <span data-ttu-id="525c0-120">Wenn dieser Wert f`alse` ist, ersetzt die Flatfilequelle die NULL-Werte aus den Quelldaten mit entsprechenden Standardwerten für jede Spalte, z. B. mit leeren Zeichenfolgen in Zeichenfolgenspalten und Nullen in numerischen Spalten.</span><span class="sxs-lookup"><span data-stu-id="525c0-120">When this value is f`alse`, the Flat File source replaces null values from the source data with appropriate default values for each column, such as empty strings for string columns and zero for numeric columns.</span></span>  
  
 <span data-ttu-id="525c0-121">**Vorschau**</span><span class="sxs-lookup"><span data-stu-id="525c0-121">**Preview**</span></span>  
 <span data-ttu-id="525c0-122">Zeigen Sie mithilfe des Dialogfelds **Datenansicht** eine Vorschau der Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="525c0-122">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="525c0-123">In der Vorschau können bis zu 200 Zeilen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="525c0-123">Preview can display up to 200 rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="525c0-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="525c0-124">See Also</span></span>  
 <span data-ttu-id="525c0-125">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="525c0-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="525c0-126">[Quellen-Editor für Flatfiles &#40;Seite "Spalten"&#41;](../../2014/integration-services/flat-file-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="525c0-126">[Flat File Source Editor &#40;Columns Page&#41;](../../2014/integration-services/flat-file-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="525c0-127">[Quellen-Editor für Flatfiles &#40;Seite Fehlerausgabe&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="525c0-127">[Flat File Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="525c0-128">Verbindungs-Manager für Flatfiles</span><span class="sxs-lookup"><span data-stu-id="525c0-128">Flat File Connection Manager</span></span>](connection-manager/file-connection-manager.md)  
  
  
