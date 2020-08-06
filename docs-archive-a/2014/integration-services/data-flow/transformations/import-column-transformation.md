---
title: Transformation für das Importieren von Spalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.importcolumntrans.f1
helpviewer_keywords:
- Import Column transformation [Integration Services]
- columns [Integration Services], importing
- importing data, SSIS packages
- inserting data
ms.assetid: ac3b74c1-ef54-4297-8062-1734324fffcc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f4330438614cce7892e74dc9a1dcbb6680b72972
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621100"
---
# <a name="import-column-transformation"></a><span data-ttu-id="30291-102">Transformation für das Importieren von Spalten</span><span class="sxs-lookup"><span data-stu-id="30291-102">Import Column Transformation</span></span>
  <span data-ttu-id="30291-103">Die Transformation für das Importieren von Spalten liest Daten aus Dateien und fügt die Daten Spalten in einem Datenfluss hinzu.</span><span class="sxs-lookup"><span data-stu-id="30291-103">The Import Column transformation reads data from files and adds the data to columns in a data flow.</span></span> <span data-ttu-id="30291-104">Mit dieser Transformation kann ein Paket einem Datenfluss Text und Bilder hinzufügen, die in separaten Dateien gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="30291-104">Using this transformation, a package can add text and images stored in separate files to a data flow.</span></span> <span data-ttu-id="30291-105">Beispielsweise können in einem Datenfluss, der Daten in eine Tabelle mit Produktinformationen lädt, mit der Transformation für das Importieren von Spalten Kundenbeurteilungen für jedes Produkt aus Dateien importiert und die Beurteilungen dem Datenfluss hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="30291-105">For example, a data flow that loads data into a table that stores product information can include the Import Column transformation to import customer reviews of each product from files and add the reviews to the data flow.</span></span>  
  
 <span data-ttu-id="30291-106">Es gibt folgende Möglichkeiten, um die Transformation für das Importieren von Spalten zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="30291-106">You can configure the Import Column transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="30291-107">Geben Sie die Tabelle an, der die Transformation Daten hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="30291-107">Specify the columns to which the transformation adds data.</span></span>  
  
-   <span data-ttu-id="30291-108">Geben Sie an, ob die Transformation eine Bytereihenfolgemarke (BOM, Byte-Order Mark) erwartet.</span><span class="sxs-lookup"><span data-stu-id="30291-108">Specify whether the transformation expects a byte-order mark (BOM).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="30291-109">Eine BOM wird nur bei Daten vom DT_NTEXT-Datentyp erwartet.</span><span class="sxs-lookup"><span data-stu-id="30291-109">A BOM is only expected if the data has the DT_NTEXT data type.</span></span>  
  
 <span data-ttu-id="30291-110">Eine Spalte in der Transformationseingabe enthält die Namen von Dateien, in denen die Daten gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="30291-110">A column in the transformation input contains the names of files that hold the data.</span></span> <span data-ttu-id="30291-111">In jeder Zeile des Datasets kann eine andere Datei angegeben sein.</span><span class="sxs-lookup"><span data-stu-id="30291-111">Each row in the dataset can specify a different file.</span></span> <span data-ttu-id="30291-112">Wenn die Transformation für das Importieren von Spalten eine Zeile verarbeitet, wird der Dateiname gelesen, die entsprechende Datei im Dateisystem geöffnet und der Dateiinhalt in eine Ausgabespalte geladen.</span><span class="sxs-lookup"><span data-stu-id="30291-112">When the Import Column transformation processes a row, it reads the file name, opens the corresponding file in the file system, and loads the file content into an output column.</span></span> <span data-ttu-id="30291-113">Die Ausgabespalte muss den Datentyp DT_TEXT, DT_NTEXT oder DT_IMAGE aufweisen.</span><span class="sxs-lookup"><span data-stu-id="30291-113">The data type of the output column must be DT_TEXT, DT_NTEXT, or DT_IMAGE.</span></span> <span data-ttu-id="30291-114">Weitere Informationen finden Sie unter [Integration Services Datentypen](../integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="30291-114">For more information, see [Integration Services Data Types](../integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="30291-115">Diese Transformation weist eine Eingabe, eine Ausgabe und eine Fehlerausgabe auf.</span><span class="sxs-lookup"><span data-stu-id="30291-115">This transformation has one input, one output, and one error output.</span></span>  
  
## <a name="configuration-of-the-import-column-transformation"></a><span data-ttu-id="30291-116">Konfiguration der Transformation für das Importieren von Spalten</span><span class="sxs-lookup"><span data-stu-id="30291-116">Configuration of the Import Column Transformation</span></span>  
 <span data-ttu-id="30291-117">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="30291-117">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="30291-118">Das Dialogfeld **Erweiterter Editor** enthält die Eigenschaften, die programmgesteuert festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="30291-118">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="30291-119">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Erweiterter Editor** oder programmgesteuert festlegen können:</span><span class="sxs-lookup"><span data-stu-id="30291-119">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="30291-120">Common Properties</span><span class="sxs-lookup"><span data-stu-id="30291-120">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="30291-121">Benutzerdefinierte Eigenschaften von Transformationen</span><span class="sxs-lookup"><span data-stu-id="30291-121">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="30291-122">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="30291-122">Related Tasks</span></span>  
 <span data-ttu-id="30291-123">Informationen zum Festlegen der Eigenschaften dieser Komponente finden Sie unter [Festlegen der Eigenschaften einer Datenflusskomponente](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="30291-123">For information about how to set properties of this component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30291-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="30291-124">See Also</span></span>  
 <span data-ttu-id="30291-125">[Transformation für das Exportieren von Spalten](export-column-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="30291-125">[Export Column Transformation](export-column-transformation.md) </span></span>  
 <span data-ttu-id="30291-126">[Datenfluss](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="30291-126">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="30291-127">SQL Server Integration Services-Transformationen</span><span class="sxs-lookup"><span data-stu-id="30291-127">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
