---
title: Spalten für Volltextindex (Dialogfeld) (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.fulltextcolumn
ms.assetid: a6f41c5c-d950-4d64-9e42-d062925917b6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7f1cd2c94739a13e1820d8c05b338abd91d8a908
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725210"
---
# <a name="full-text-index-columns-dialog-box-visual-database-tools"></a><span data-ttu-id="ae6c6-102">Spalten für Volltextindex (Dialogfeld) (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="ae6c6-102">Full-Text Index Columns Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="ae6c6-103">In diesem Dialogfeld werden die Spalten aufgelistet, die in den Volltextindex für die im Tabellen-Designer geöffnete Tabelle einbezogen sind.</span><span class="sxs-lookup"><span data-stu-id="ae6c6-103">This dialog box lists the columns participating in the full-text index for the table open in Table Designer.</span></span> <span data-ttu-id="ae6c6-104">Klicken Sie zum Zugreifen auf dieses Dialogfeld mit der rechten Maustaste auf die Tabelle im Tabellen-Designer, und wählen Sie **Volltextindex** aus. Klicken Sie im Dialogfeld **Volltextindex** auf den Index mit den anzuzeigenden bzw. zu bearbeitenden Spalten, klicken Sie im rechten Datenblatt auf das Feld **Spalten**, und klicken Sie auf die Auslassungspunkte ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="ae6c6-104">To access this dialog box, right-click the table in Table Designer, choose **Full-Text Index**, and in the **Full-Text Index** dialog box, click the index with columns you want to view or edit, click the **Columns** field in the grid to the right, and click the ellipses (**...**).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ae6c6-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="ae6c6-105">Options</span></span>  
 <span data-ttu-id="ae6c6-106">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="ae6c6-106">**Column**</span></span>  
 <span data-ttu-id="ae6c6-107">Zeigt die Namen der Spalten an, die in den Volltextindex einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="ae6c6-107">Shows the names of columns participating in the full-text index.</span></span> <span data-ttu-id="ae6c6-108">Um eine Spalte hinzuzufügen, klicken Sie auf die erste leere Zelle, und wählen Sie eine Spalte aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="ae6c6-108">To add a column, click in the first empty cell and choose a column from the drop-down list.</span></span> <span data-ttu-id="ae6c6-109">Sie können nur auf Spalten zugreifen, die textbasierte Datentypen bzw. Imagedatentypen enthalten.</span><span class="sxs-lookup"><span data-stu-id="ae6c6-109">Only columns with either text-based or image data types will be accessible.</span></span>  
  
 <span data-ttu-id="ae6c6-110">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="ae6c6-110">**Data Type**</span></span>  
 <span data-ttu-id="ae6c6-111">Zeigt den Datentyp für jede Spalte an.</span><span class="sxs-lookup"><span data-stu-id="ae6c6-111">Shows the data type for each column.</span></span> <span data-ttu-id="ae6c6-112">Dies ist eine schreibgeschützte Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ae6c6-112">This is a read-only property.</span></span> <span data-ttu-id="ae6c6-113">Öffnen Sie zum Ändern eines Datentyps die Tabelle im Tabellen-Designer, klicken Sie auf die Spalte, und bearbeiten Sie den Datentyp auf der Registerkarte **Spalteneigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="ae6c6-113">To change a data type, open the table in Table Designer, click the column, and edit the data type in the **Column Properties** tab.</span></span>  
  
 <span data-ttu-id="ae6c6-114">**Nach Spalte eingegeben**</span><span class="sxs-lookup"><span data-stu-id="ae6c6-114">**Typed by Column**</span></span>  
 <span data-ttu-id="ae6c6-115">Gilt nur für Spalten mit dem `image`-Datentyp.</span><span class="sxs-lookup"><span data-stu-id="ae6c6-115">Applies only to columns with the data type `image`.</span></span> <span data-ttu-id="ae6c6-116">Stellt eine Dropdownliste bereit, aus der Sie auswählen können, welche anderen Spalten den Datentyp dieser Spalte darstellen.</span><span class="sxs-lookup"><span data-stu-id="ae6c6-116">Provides a drop-down list from which you can choose which of the other columns represent the data type of this column.</span></span> <span data-ttu-id="ae6c6-117">Wenn diese Spalte nicht den `image`-Datentyp aufweist, wird der Wert None verwendet.</span><span class="sxs-lookup"><span data-stu-id="ae6c6-117">If this column is not of the `image` data type the value will be None.</span></span>  
  
 <span data-ttu-id="ae6c6-118">Spalten mit dem `image`-Datentyp können Microsoft Office-Dateien (DOC-, XLS- und PPT-Dateien), Textdateien (TXT-Dateien) sowie HTML-Dateien (HTM-Dateien) enthalten. Wenn der Datentyp für die Spalte auf "image" festgelegt wird, kann der Inhalt der Dateien bei der Volltextsuche durchsucht werden.</span><span class="sxs-lookup"><span data-stu-id="ae6c6-118">Columns with the data type `image` can contain Microsoft Office files (.doc, .xls, and .ppt files), text files (.txt files), and HTML files (.htm files), and setting the data type of that column to image allows the full-text search to search the contents of the files.</span></span>  
  
 <span data-ttu-id="ae6c6-119">**Sprache**</span><span class="sxs-lookup"><span data-stu-id="ae6c6-119">**Language**</span></span>  
 <span data-ttu-id="ae6c6-120">Listet verfügbare Sprachen auf.</span><span class="sxs-lookup"><span data-stu-id="ae6c6-120">Lists available languages.</span></span> <span data-ttu-id="ae6c6-121">Wählen Sie aus der Dropdownliste die für die Spaltendaten entsprechende Sprache aus.</span><span class="sxs-lookup"><span data-stu-id="ae6c6-121">Choose the language from the drop-down list appropriate for your column data.</span></span> <span data-ttu-id="ae6c6-122">Wenn Sie beispielsweise ein Betriebssystem in englischer Sprache verwenden, jedoch eine Spalte indizieren möchten, die deutschen Text enthält, wählen Sie aus der Dropdownliste Deutsch aus, um die Leistung des Index zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="ae6c6-122">For example, if you are using an English operating system, but you want to index a column that contains German text, choose German from the drop-down list to improve the index's performance.</span></span>  
  
 <span data-ttu-id="ae6c6-123">**Statistische Semantik**</span><span class="sxs-lookup"><span data-stu-id="ae6c6-123">**Statistical Semantics**</span></span>  
 <span data-ttu-id="ae6c6-124">Wählen Sie aus, ob die semantische Indizierung für die ausgewählte Spalte aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ae6c6-124">Select whether to enable semantic indexing for the selected column.</span></span> <span data-ttu-id="ae6c6-125">Weitere Informationen finden Sie unter [Semantische Suche &#40;SQL Server&#41;](../../relational-databases/search/semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ae6c6-125">For more information, see [Semantic Search &#40;SQL Server&#41;](../../relational-databases/search/semantic-search-sql-server.md).</span></span>  
  
 <span data-ttu-id="ae6c6-126">Wenn Sie eine **Sprache** vor der Option **Statistische Semantik**auswählen und die ausgewählte Sprache über kein zugeordnetes semantisches Sprachmodell verfügt, ist das Kontrollkästchen **Statistische Semantik** deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ae6c6-126">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** checkbox is disabled.</span></span> <span data-ttu-id="ae6c6-127">Wenn Sie **Statistische Semantik** vor einer **Sprache**auswählen, werden im Dropdown-Kombinationsfeld nur die Sprachen angezeigt, für die das semantische Sprachmodell unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="ae6c6-127">If you select **Statistical Semantics** prior to selecting a **Language**, the languages available in the drop-down combo box will be restricted to those for which there is Semantic Language Model support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae6c6-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ae6c6-128">See Also</span></span>  
 [<span data-ttu-id="ae6c6-129">Volltextindex (Dialogfeld) &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="ae6c6-129">Full-Text Index Dialog Box &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
