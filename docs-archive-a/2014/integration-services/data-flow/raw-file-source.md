---
title: Rohdatendatei-Quelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rawfilesource.f1
helpviewer_keywords:
- sources [Integration Services], Raw File
- raw data [Integration Services]
- Raw File source
ms.assetid: 5b4daea5-7f76-4674-aa77-0a79f9f97f7d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4cbc5800c4fb2b90b74e66b6ff161118b2b550f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615461"
---
# <a name="raw-file-source"></a><span data-ttu-id="2b67e-102">Rohdatendatei-Quelle</span><span class="sxs-lookup"><span data-stu-id="2b67e-102">Raw File Source</span></span>
  <span data-ttu-id="2b67e-103">Die Rohdatendatei-Quelle liest Rohdaten aus einer Datei.</span><span class="sxs-lookup"><span data-stu-id="2b67e-103">The Raw File source reads raw data from a file.</span></span> <span data-ttu-id="2b67e-104">Die Darstellung der Daten erfolgt im systemeigenen Quellformat, sodass die Daten nicht übersetzt und fast nicht analysiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="2b67e-104">Because the representation of the data is native to the source, the data requires no translation and almost no parsing.</span></span> <span data-ttu-id="2b67e-105">Dies bedeutet, dass die Rohdatendatei-Quelle Daten schneller als andere Quellen, wie z. B. Flatfile- und OLE DB-Quellen, lesen kann.</span><span class="sxs-lookup"><span data-stu-id="2b67e-105">This means that the Raw File source can read data more quickly than other sources such as the Flat File and the OLE DB sources.</span></span>  
  
 <span data-ttu-id="2b67e-106">Mithilfe der Rohdatendatei-Quelle werden Rohdaten abgerufen, die zuvor vom Rohdatendatei-Ziel geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="2b67e-106">The Raw File source is used to retrieve raw data that was previously written by the Raw File destination.</span></span> <span data-ttu-id="2b67e-107">Sie können die Rohdatendatei-Quelle auch auf eine leere Rohdatendatei verweisen, die nur die Spalten (Nur-Metadatendatei) enthält.</span><span class="sxs-lookup"><span data-stu-id="2b67e-107">You can also point the Raw File source to an empty raw file that contains only the columns (metadata-only file).</span></span> <span data-ttu-id="2b67e-108">Sie verwenden das Rohdatendatei-Ziel, um die Nur-Metadatendatei zu generieren, ohne das Paket ausführen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="2b67e-108">You use the Raw File destination to generate the metadata-only file without having to run the package.</span></span> <span data-ttu-id="2b67e-109">Weitere Informationen finden Sie unter [Raw File Destination](raw-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="2b67e-109">For more information, see [Raw File Destination](raw-file-destination.md).</span></span>  
  
 <span data-ttu-id="2b67e-110">Das Format der Rohdatendatei enthält Sortierungsinformationen:</span><span class="sxs-lookup"><span data-stu-id="2b67e-110">The raw file format contains sort information.</span></span> <span data-ttu-id="2b67e-111">Das Rohdatendatei-Ziel speichert alle Sortierungsinformationen, einschließlich der Vergleichsflags für Zeichenfolgenspalten.</span><span class="sxs-lookup"><span data-stu-id="2b67e-111">The Raw File Destination saves all the sort information including the comparison flags for string columns.</span></span> <span data-ttu-id="2b67e-112">Die Rohdatendatei-Quelle liest und beachtet die Sortierungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="2b67e-112">The Raw File source reads and honors the sort information.</span></span> <span data-ttu-id="2b67e-113">Sie können die Rohdatendatei-Quelle dergestalt konfigurieren, dass die Sortierflags in der Datei mit dem erweiterten Editor ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="2b67e-113">You do have the option of configuring the Raw File Source to ignore the sort flags in the file, using the Advanced Editor.</span></span> <span data-ttu-id="2b67e-114">Weitere Informationen zu Vergleichsflags finden Sie unter [Comparing String Data](comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="2b67e-114">For more information about comparison flags, see [Comparing String Data](comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="2b67e-115">Zum Konfigurieren der Rohdatendatei geben Sie den Namen der Datei an, die die Rohdatendatei-Quelle liest.</span><span class="sxs-lookup"><span data-stu-id="2b67e-115">You configure the Raw File by specifying the name of the name of the file that the Raw File source reads.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b67e-116">Für diese Quelle wird kein Verbindungs-Manager verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b67e-116">This source does not use a connection manager.</span></span>  
  
 <span data-ttu-id="2b67e-117">Diese Quelle erzeugt nur eine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="2b67e-117">This source has one output.</span></span> <span data-ttu-id="2b67e-118">Eine Fehlerausgabe wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2b67e-118">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-raw-file-source"></a><span data-ttu-id="2b67e-119">Konfiguration der Rohdatendatei-Quelle</span><span class="sxs-lookup"><span data-stu-id="2b67e-119">Configuration of the Raw File Source</span></span>  
 <span data-ttu-id="2b67e-120">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="2b67e-120">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="2b67e-121">Das Dialogfeld **Erweiterter Editor** enthält die Eigenschaften, die programmgesteuert festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="2b67e-121">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="2b67e-122">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Erweiterter Editor** oder programmgesteuert festlegen können:</span><span class="sxs-lookup"><span data-stu-id="2b67e-122">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="2b67e-123">Common Properties</span><span class="sxs-lookup"><span data-stu-id="2b67e-123">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="2b67e-124">Benutzerdefinierte Eigenschaften der Rohdatendatei</span><span class="sxs-lookup"><span data-stu-id="2b67e-124">Raw File Custom Properties</span></span>](raw-file-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="2b67e-125">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="2b67e-125">Related Tasks</span></span>  
 <span data-ttu-id="2b67e-126">Informationen zum Festlegen der Eigenschaften der Komponente finden Sie unter [Festlegen der Eigenschaften einer Datenflusskomponente](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="2b67e-126">For information about how to set the properties of the component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="2b67e-127">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="2b67e-127">Related Content</span></span>  
  
-   <span data-ttu-id="2b67e-128">Blogeintrag, [Raw Files Are Awesome](https://www.sqlservercentral.com/blogs/31-days-of-ssis-%e2%80%93-raw-files-are-awesome-131), auf sqlservercentral.com</span><span class="sxs-lookup"><span data-stu-id="2b67e-128">Blog entry, [Raw Files Are Awesome](https://www.sqlservercentral.com/blogs/31-days-of-ssis-%e2%80%93-raw-files-are-awesome-131), on sqlservercentral.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b67e-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2b67e-129">See Also</span></span>  
 <span data-ttu-id="2b67e-130">[Rohdatendatei-Ziel](raw-file-destination.md) </span><span class="sxs-lookup"><span data-stu-id="2b67e-130">[Raw File Destination](raw-file-destination.md) </span></span>  
 [<span data-ttu-id="2b67e-131">Datenfluss</span><span class="sxs-lookup"><span data-stu-id="2b67e-131">Data Flow</span></span>](data-flow.md)  
  
  
