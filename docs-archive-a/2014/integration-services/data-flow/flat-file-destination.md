---
title: Flatfileziel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfiledest.f1
helpviewer_keywords:
- flat files
- Flat File destination
- text file writing [Integration Services]
- destinations [Integration Services], Flat File
ms.assetid: e0d6e356-8db4-48aa-ba66-029397f98f61
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a961b7528b13a4eaa3297343e91f1deaf2fa3226
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726098"
---
# <a name="flat-file-destination"></a><span data-ttu-id="e011f-102">Flatfileziel</span><span class="sxs-lookup"><span data-stu-id="e011f-102">Flat File Destination</span></span>
  <span data-ttu-id="e011f-103">Das Flatfileziel schreibt Daten in eine Textdatei.</span><span class="sxs-lookup"><span data-stu-id="e011f-103">The Flat File destination writes data to a text file.</span></span> <span data-ttu-id="e011f-104">Die Textdatei kann in verschiedenen Formaten vorliegen: mit Trennzeichen, mit fester Breite, mit fester Breite mit Zeilentrennzeichen oder mit rechtem Flatterrand.</span><span class="sxs-lookup"><span data-stu-id="e011f-104">The text file can be in delimited, fixed width, fixed width with row delimiter, or ragged right format.</span></span>  
  
 <span data-ttu-id="e011f-105">Es gibt folgende Möglichkeiten, um das Flatfileziel zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="e011f-105">You can configure the Flat File destination in the following ways:</span></span>  
  
-   <span data-ttu-id="e011f-106">Geben Sie einen Textblock an, der in die Datei eingefügt wird, bevor Daten geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="e011f-106">Provide a block of text that is inserted in the file before any data is written.</span></span> <span data-ttu-id="e011f-107">Der Text kann Informationen bereitstellen, wie z. B. Spaltenüberschriften.</span><span class="sxs-lookup"><span data-stu-id="e011f-107">The text can provide information such as column headings.</span></span>  
  
-   <span data-ttu-id="e011f-108">Geben Sie an, ob Daten in einer gleichnamigen Zieldatei überschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e011f-108">Specify whether to overwrite a data in a destination file that has the same name.</span></span>  
  
 <span data-ttu-id="e011f-109">Dieses Ziel verwendet für den Zugriff auf die Textdatei einen Verbindungs-Manager für Flatfiles.</span><span class="sxs-lookup"><span data-stu-id="e011f-109">This destination uses a Flat File connection manager to access the text file.</span></span> <span data-ttu-id="e011f-110">Durch Festlegen von Eigenschaften im Verbindungs-Manager für Flatfiles, der vom Flatfileziel verwendet wird, können Sie angeben, wie das Flatfileziel die Textdatei formatiert und schreibt.</span><span class="sxs-lookup"><span data-stu-id="e011f-110">By setting properties on the Flat File connection manager that the Flat File destination uses, you can specify how the Flat File destination formats and writes the text file.</span></span> <span data-ttu-id="e011f-111">Wenn Sie den Verbindungs-Manager für Flatfiles konfigurieren, geben Sie Informationen zur Datei und zu jeder Spalte in der Datei an.</span><span class="sxs-lookup"><span data-stu-id="e011f-111">When you configure the Flat File connection manager, you specify information about the file and about each column in the file.</span></span> <span data-ttu-id="e011f-112">Beispielsweise können Sie die Zeichen angeben, mit denen Spalten und Zeilen in der Datei getrennt werden, sowie den Datentyp und die Länge jeder Spalte.</span><span class="sxs-lookup"><span data-stu-id="e011f-112">For example, you specify the characters that delimit columns and rows in the file, and you specify the data type and the length of each column.</span></span> <span data-ttu-id="e011f-113">Weitere Informationen finden Sie unter [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="e011f-113">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="e011f-114">Das Flatfileziel schließt die benutzerdefinierte Header-Eigenschaft ein.</span><span class="sxs-lookup"><span data-stu-id="e011f-114">The Flat File destination includes the Header custom property.</span></span> <span data-ttu-id="e011f-115">Diese Eigenschaft kann beim Laden des Pakets mithilfe eines Eigenschaftsausdrucks aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e011f-115">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="e011f-116">Weitere Informationen finden Sie unter [Integration Services-Ausdrücke &#40;SSIS&#41;](../expressions/integration-services-ssis-expressions.md), [Verwenden von Eigenschaftsausdrücken in Paketen](../expressions/use-property-expressions-in-packages.md) und [Benutzerdefinierte Eigenschaften der Flatfile](flat-file-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="e011f-116">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../expressions/use-property-expressions-in-packages.md), and [Flat File Custom Properties](flat-file-custom-properties.md).</span></span>  
  
 <span data-ttu-id="e011f-117">Das Ziel weist eine Ausgabe auf.</span><span class="sxs-lookup"><span data-stu-id="e011f-117">This destination has one output.</span></span> <span data-ttu-id="e011f-118">Eine Fehlerausgabe wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e011f-118">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-flat-file-destination"></a><span data-ttu-id="e011f-119">Konfiguration des Flatfileziels</span><span class="sxs-lookup"><span data-stu-id="e011f-119">Configuration of the Flat File Destination</span></span>  
 <span data-ttu-id="e011f-120">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="e011f-120">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="e011f-121">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Quellen-Editor für Flatfiles** festlegen können:</span><span class="sxs-lookup"><span data-stu-id="e011f-121">For more information about the properties that you can set in the **Flat File Source Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="e011f-122">Ziel-Editor für Flatfiles &#40;Seite „Verbindungs-Manager“&#41;</span><span class="sxs-lookup"><span data-stu-id="e011f-122">Flat File Destination Editor &#40;Connection Manager Page&#41;</span></span>](../flat-file-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="e011f-123">Ziel-Editor für Flatfiles &#40;Seite „Zuordnungen“&#41;</span><span class="sxs-lookup"><span data-stu-id="e011f-123">Flat File Destination Editor &#40;Mappings Page&#41;</span></span>](../flat-file-destination-editor-mappings-page.md)  
  
 <span data-ttu-id="e011f-124">Das Dialogfeld **Erweiterter Editor** enthält die Eigenschaften, die programmgesteuert festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="e011f-124">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="e011f-125">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Erweiterter Editor** oder programmgesteuert festlegen können:</span><span class="sxs-lookup"><span data-stu-id="e011f-125">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="e011f-126">Common Properties</span><span class="sxs-lookup"><span data-stu-id="e011f-126">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="e011f-127">Benutzerdefinierte Eigenschaften der Flatfile</span><span class="sxs-lookup"><span data-stu-id="e011f-127">Flat File Custom Properties</span></span>](flat-file-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="e011f-128">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="e011f-128">Related Tasks</span></span>  
 <span data-ttu-id="e011f-129">Informationen zum Festlegen der Eigenschaften einer Datenflusskomponente finden Sie unter [Festlegen der Eigenschaften einer Datenflusskomponente](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="e011f-129">For information about how to set the properties of a data flow component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e011f-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e011f-130">See Also</span></span>  
 <span data-ttu-id="e011f-131">[Flatfilequelle](flat-file-source.md) </span><span class="sxs-lookup"><span data-stu-id="e011f-131">[Flat File Source](flat-file-source.md) </span></span>  
 [<span data-ttu-id="e011f-132">Datenfluss</span><span class="sxs-lookup"><span data-stu-id="e011f-132">Data Flow</span></span>](data-flow.md)  
  
  
