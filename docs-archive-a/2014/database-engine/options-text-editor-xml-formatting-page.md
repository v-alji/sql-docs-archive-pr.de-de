---
title: Optionen (Text-Editor-XML-Formatierungs Seite) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 97373178-d288-4127-af37-d9f5fe1b8607
author: rothja
ms.author: jroth
ms.openlocfilehash: dce36142fe9974c0167fca700c509642e05d89b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701540"
---
# <a name="options-text-editor---xml---formatting-page"></a><span data-ttu-id="41fa1-102">Optionen (Text-Editor – XML – Seite „Formatierung“)</span><span class="sxs-lookup"><span data-stu-id="41fa1-102">Options (Text Editor - XML - Formatting Page)</span></span>

<span data-ttu-id="41fa1-103">In diesem Dialogfeld können Sie die Formatierungseinstellungen für den XML-Editor festlegen.</span><span class="sxs-lookup"><span data-stu-id="41fa1-103">This dialog box allows you to specify the formatting settings for the XML Editor.</span></span> <span data-ttu-id="41fa1-104">Sie können über das Menü **Extras** auf das Dialogfeld **Optionen** zugreifen.</span><span class="sxs-lookup"><span data-stu-id="41fa1-104">You can access the **Options** dialog box from the **Tools** menu.</span></span>  
  
> [!NOTE]  
> <span data-ttu-id="41fa1-105">Zum Anzeigen dieser Einstellungen wählen Sie zunächst den Ordner **Text-Editor** und anschließend den Ordner **XML** aus. Wählen Sie dann im Dialogfeld **Optionen** die Option **Formatierung** aus.</span><span class="sxs-lookup"><span data-stu-id="41fa1-105">These settings are available when you select the **Text Editor** folder, the **XML** folder, and then the **Formatting** option from the **Options** dialog box.</span></span>  
  
## <a name="attributes"></a><span data-ttu-id="41fa1-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="41fa1-106">Attributes</span></span>  
 <span data-ttu-id="41fa1-107">**Manuelle Attributformatierung beibehalten**</span><span class="sxs-lookup"><span data-stu-id="41fa1-107">**Preserve manual attribute formatting**</span></span>  
 <span data-ttu-id="41fa1-108">Nimmt keine Neuformatierung von Attributen vor.</span><span class="sxs-lookup"><span data-stu-id="41fa1-108">Do not reformat attributes.</span></span> <span data-ttu-id="41fa1-109">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="41fa1-109">This is the default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="41fa1-110">Wenn die Attribute auf mehrere Zeilen verteilt sind, richtet der Editor jede Attributzeile am Einzug des jeweils übergeordneten Elements aus.</span><span class="sxs-lookup"><span data-stu-id="41fa1-110">If the attributes are on multiple lines, the editor indents each line of attributes to match the indentation of the parent element.</span></span>  
  
 <span data-ttu-id="41fa1-111">**Attribute jeweils in einer eigenen Zeile ausrichten**</span><span class="sxs-lookup"><span data-stu-id="41fa1-111">**Align attributes each on a separate line**</span></span>  
 <span data-ttu-id="41fa1-112">Richtet das zweite und alle nachfolgenden Attribute vertikal am Einzug des ersten Attributs aus.</span><span class="sxs-lookup"><span data-stu-id="41fa1-112">Align the second and subsequent attributes vertically to match the indentation of the first attribute.</span></span> <span data-ttu-id="41fa1-113">Der folgende XML-Text verkörpert ein Beispiel für die Ausrichtung der Attribute.</span><span class="sxs-lookup"><span data-stu-id="41fa1-113">The following XML text is an example of how the attributes would be aligned.</span></span>  
  
```  
<item id = "123-A"  
      name = "hammer"  
      price = "9.95"  
</item>  
```  
  
## <a name="auto-reformat"></a><span data-ttu-id="41fa1-114">Automatisch neu formatieren</span><span class="sxs-lookup"><span data-stu-id="41fa1-114">Auto Reformat</span></span>  
 <span data-ttu-id="41fa1-115">**Bei Einfügen aus der Zwischenablage**</span><span class="sxs-lookup"><span data-stu-id="41fa1-115">**On paste from clipboard.**</span></span>  
 <span data-ttu-id="41fa1-116">Formatiert den aus der Zwischenablage eingefügten XML-Text neu.</span><span class="sxs-lookup"><span data-stu-id="41fa1-116">Reformat XML text pasted from the clipboard.</span></span>  
  
 <span data-ttu-id="41fa1-117">**Bei Komplettierung des Endtags**</span><span class="sxs-lookup"><span data-stu-id="41fa1-117">**On completion of end tag**</span></span>  
 <span data-ttu-id="41fa1-118">Formatiert das Element nach Abschluss des Endtags neu.</span><span class="sxs-lookup"><span data-stu-id="41fa1-118">Reformat the element when the end tag is completed.</span></span>  
  
## <a name="mixed-content"></a><span data-ttu-id="41fa1-119">Gemischter Inhalt</span><span class="sxs-lookup"><span data-stu-id="41fa1-119">Mixed Content</span></span>  
 <span data-ttu-id="41fa1-120">**Standardformat: gemischter Inhalt**</span><span class="sxs-lookup"><span data-stu-id="41fa1-120">**Format mixed content by default.**</span></span>  
 <span data-ttu-id="41fa1-121">Versucht, gemischten Inhalt neu zu formatieren. Der Inhalt von `xml:space="preserve"`-Bereichen wird dabei jedoch nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="41fa1-121">Attempt to reformat mixed content, except when the content is found in an `xml:space="preserve"` scope.</span></span> <span data-ttu-id="41fa1-122">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="41fa1-122">This is the default.</span></span>  
  
 <span data-ttu-id="41fa1-123">Wenn ein Element sowohl Text als auch Markup enthält, wird sein Inhalt wie gemischter Inhalt behandelt.</span><span class="sxs-lookup"><span data-stu-id="41fa1-123">If an element contains a mix of text and markup, the contents are considered to be mixed content.</span></span> <span data-ttu-id="41fa1-124">Das folgende Beispiel zeigt ein Element mit gemischtem Inhalt.</span><span class="sxs-lookup"><span data-stu-id="41fa1-124">Following is an example of an element with mixed content.</span></span>  
  
```  
<dir>c:\data\AlphaProject\  
  <file readOnly="false">test1.txt</file>  
  <file readOnly="false">test2.txt</file>  
```  
  
 \</dir>  
  
## <a name="see-also"></a><span data-ttu-id="41fa1-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="41fa1-125">See Also</span></span>  
 [<span data-ttu-id="41fa1-126">XML-Editor &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="41fa1-126">XML Editor &#40;SQL Server Management Studio&#41;</span></span>](../ssms/sql-server-management-studio-ssms.md)  
