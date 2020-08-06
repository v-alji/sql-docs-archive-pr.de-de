---
title: Sortierung (Dialogfeld) (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.definecolumncollation
- vdtsql.chm:65561
ms.assetid: e4020f79-7abf-4839-b9b2-984ef7049817
author: stevestein
ms.author: sstein
ms.openlocfilehash: d551b2ae7ca27250c144afedf13038efd78ad6ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630449"
---
# <a name="collation-dialog-box-visual-database-tools"></a><span data-ttu-id="4c309-102">Sortierreihenfolge (Dialogfeld) (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="4c309-102">Collation Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="4c309-103">Mit diesem Dialogfeld können Sie eine Sortierreihenfolge für die Spalte angeben.</span><span class="sxs-lookup"><span data-stu-id="4c309-103">This dialog box lets you specify a collation sequence for the column.</span></span> <span data-ttu-id="4c309-104">Die Sortierreihenfolge einer Spalte wird bei jedem Vorgang verwendet, bei dem die Werte der Spalte mit einer anderen Spalte oder mit konstanten Werten verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="4c309-104">A column's collation sequence is used in any operation that compares values of the column to another column or to constant values.</span></span> <span data-ttu-id="4c309-105">Gleichzeitig wird dadurch das Verhalten einiger Zeichenfolgenfunktionen beeinflusst, z. B. SUBSTRING und CHARINDEX.</span><span class="sxs-lookup"><span data-stu-id="4c309-105">It also affects the behavior of some string functions, such as SUBSTRING and CHARINDEX.</span></span> <span data-ttu-id="4c309-106">Eine vollständige Liste der Auswirkungen der Einstellung der Sortierreihenfolge einer Spalte finden Sie in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="4c309-106">For a complete list of the effects of a column's collation setting, see the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] documentation.</span></span>  
  
 <span data-ttu-id="4c309-107">Das Dialogfeld wird in den folgenden Fällen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="4c309-107">This dialog box appears:</span></span>  
  
-   <span data-ttu-id="4c309-108">Wenn Sie auf der Registerkarte **Spalteneigenschaften** im Feld **Sortierung** einen ungültigen Sortierungsnamen eingeben.</span><span class="sxs-lookup"><span data-stu-id="4c309-108">If you enter an invalid collation name in the **Collation** field on the **Column Properties** tab.</span></span>  
  
-   <span data-ttu-id="4c309-109">Wenn Sie in der Registerkarte **Spalteneigenschaften** in das Feld **Sortierreihenfolge** klicken, und dann auf die Schaltfläche mit den Auslassungspunkten ( **...** ) rechts neben dem Feld klicken.</span><span class="sxs-lookup"><span data-stu-id="4c309-109">If you click in the **Collation** field on the **Column Properties** tab, and then click the ellipsis button (**...**) to the right of the field.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4c309-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="4c309-110">Options</span></span>  
 <span data-ttu-id="4c309-111">**SQL-Sortierung**</span><span class="sxs-lookup"><span data-stu-id="4c309-111">**SQL Collation**</span></span>  
 <span data-ttu-id="4c309-112">Wählen Sie aus der Dropdownliste eine in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] definierte Sortierreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="4c309-112">Choose among the collation sequences defined by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the drop-down list.</span></span>  
  
 <span data-ttu-id="4c309-113">**Windows-Sortierreihenfolge**</span><span class="sxs-lookup"><span data-stu-id="4c309-113">**Windows Collation**</span></span>  
 <span data-ttu-id="4c309-114">Wählen Sie aus den Sortierreihenfolgen, die in Windows in der Dropdownliste definiert sind.</span><span class="sxs-lookup"><span data-stu-id="4c309-114">Choose among the collation sequences defined by Windows from the drop-down list.</span></span>  
  
 <span data-ttu-id="4c309-115">**Binäre Sortierung**</span><span class="sxs-lookup"><span data-stu-id="4c309-115">**Binary Sort**</span></span>  
 <span data-ttu-id="4c309-116">Verwenden Sie die Binärcodes der Zeichenwerte für Vergleiche.</span><span class="sxs-lookup"><span data-stu-id="4c309-116">Use the binary codes of character values for comparisons.</span></span> <span data-ttu-id="4c309-117">Wenn Sie diese Option auswählen, sind bestimmte Optionen der alphabetischen Vergleiche nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4c309-117">If you select this option, certain alphabetic comparison options become unavailable.</span></span> <span data-ttu-id="4c309-118">Beispielsweise ist das Vergleichen ohne Unterscheidung von Groß- und Kleinschreibung nicht möglich, da Groß- und Kleinbuchstaben eine unterschiedliche binäre Codierung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="4c309-118">For example, case-insensitive comparisons become unavailable because uppercase letters and lowercase letters have different binary encodings.</span></span> <span data-ttu-id="4c309-119">Diese Option wird nur verwendet, wenn Sie **Windows-Sortierreihenfolge**ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="4c309-119">Applies only if you select **Windows collation**.</span></span>  
  
 <span data-ttu-id="4c309-120">**Lexikalische Sortierung**</span><span class="sxs-lookup"><span data-stu-id="4c309-120">**Dictionary Sort**</span></span>  
 <span data-ttu-id="4c309-121">Verwenden Sie alphabetische Vergleichsoptionen.</span><span class="sxs-lookup"><span data-stu-id="4c309-121">Use alphabetic comparison options.</span></span> <span data-ttu-id="4c309-122">Diese Option wird nur verwendet, wenn Sie **Windows-Sortierreihenfolge**ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="4c309-122">Applies only if you select **Windows collation**.</span></span> <span data-ttu-id="4c309-123">Zu den alphabetischen Vergleichsoptionen gehören folgende:</span><span class="sxs-lookup"><span data-stu-id="4c309-123">The alphabetic comparisons options are:</span></span>  
  
-   <span data-ttu-id="4c309-124">**Groß-/Kleinschreibung beachten** Aktivieren Sie diese Option, wenn beim Vergleichen die Groß- und Kleinschreibung berücksichtigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4c309-124">**Case Sensitive** Select this if you want comparisons to consider uppercase and lowercase letters to be unequal.</span></span>  
  
-   <span data-ttu-id="4c309-125">**Akzente berücksichtigen** Aktivieren Sie diese Option, wenn beim Vergleichen zwischen Buchstaben mit Akzent und Buchstaben ohne Akzent unterschieden werden soll.</span><span class="sxs-lookup"><span data-stu-id="4c309-125">**Accent Sensitive** Select this if you want comparisons to consider accented and unaccented letters to be unequal.</span></span> <span data-ttu-id="4c309-126">Wenn Sie diese Option aktivieren, werden beim Vergleichen außerdem gleiche Buchstaben mit unterschiedlichen Akzenten unterschieden.</span><span class="sxs-lookup"><span data-stu-id="4c309-126">If you select this, comparisons will also consider differently accented letters to be unequal.</span></span>  
  
-   <span data-ttu-id="4c309-127">**Kana berücksichtigen** Aktivieren Sie diese Option, wenn beim Vergleichen Unterschiede zwischen Katakana- und Hiragana-Japanisch berücksichtigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4c309-127">**Kana Sensitive** Select this if you want comparisons to consider katakana and hiragana Japanese syllables to be unequal.</span></span>  
  
-   <span data-ttu-id="4c309-128">**Breite berücksichtigen** Aktivieren Sie diese Option, wenn beim Vergleichen der Unterschied zwischen Zeichen halber Breite und Zeichen normaler Breite berücksichtigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4c309-128">**Width Sensitive** Select this if you want comparisons to consider half-width and full-width characters to be unequal.</span></span>  
  
 <span data-ttu-id="4c309-129">**Schaltfläche Standard wiederherstellen**</span><span class="sxs-lookup"><span data-stu-id="4c309-129">**Restore Default Button**</span></span>  
 <span data-ttu-id="4c309-130">Wenden Sie die Standardsortierreihenfolge für die Datenbank auf die Spalte an.</span><span class="sxs-lookup"><span data-stu-id="4c309-130">Apply the default collation sequence for the database to the column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c309-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4c309-131">See Also</span></span>  
 [<span data-ttu-id="4c309-132">Verwenden von Spalten in Aggregatabfragen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4c309-132">Work with Columns in Aggregate Queries &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
