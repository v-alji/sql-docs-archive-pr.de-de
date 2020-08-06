---
title: Gültigkeitswarnungen (Dialogfeld) (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:65556
- vdt.dlgbox.validationwarnings
ms.assetid: fc76e234-ec9c-4a19-a65b-cb558ec8268e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4f94c3ae91e077af853db949847bc8448f6a4753
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618963"
---
# <a name="validation-warnings-dialog-box-visual-database-tools"></a><span data-ttu-id="c9e63-102">Gültigkeitswarnungen (Dialogfeld) (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="c9e63-102">Validation Warnings Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="c9e63-103">Dieses Dialogfeld wird angezeigt, wenn Sie Änderungen zu speichern versuchen, die u. U. Schaden anrichten, oder wenn der Commit für die Datenbank vermutlich fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="c9e63-103">This dialog box appears if you attempt to save modifications with potentially damaging side effects, or if the database commit operation is likely to fail.</span></span> <span data-ttu-id="c9e63-104">In diesem Dialogfeld werden die möglichen Nebeneffekte bzw. die Gründe für das Fehlschlagen des Commitvorgangs angegeben.</span><span class="sxs-lookup"><span data-stu-id="c9e63-104">This dialog box indicates what those side effects might be or why the commit operation might fail.</span></span> <span data-ttu-id="c9e63-105">Sie können dann entweder mit der Änderung fortfahren oder den Vorgang abbrechen.</span><span class="sxs-lookup"><span data-stu-id="c9e63-105">It gives you the chance to continue with the modification or cancel the operation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9e63-106">Dieses Dialogfeld wird angezeigt, wenn Sie versuchen, vorgenommene Änderungen an die Datenbank zu übermitteln, oder wenn Sie ein Änderungsskript speichern.</span><span class="sxs-lookup"><span data-stu-id="c9e63-106">This dialog box appears when you attempt to transmit your modifications to the database or when you save a change script.</span></span>  
  
 <span data-ttu-id="c9e63-107">Das Dialogfeld kann aus folgenden Gründen angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="c9e63-107">The dialog box can appear for any of these reasons:</span></span>  
  
-   <span data-ttu-id="c9e63-108">Sie besitzen möglicherweise nicht die Datenbankberechtigungen zum Ausführen eines Commits für alle Änderungen.</span><span class="sxs-lookup"><span data-stu-id="c9e63-108">You might not have database permissions to commit all the modifications.</span></span>  
  
-   <span data-ttu-id="c9e63-109">Die Änderungen würden falsch formatierte abgeleitete Spalten, Standardeinschränkungen oder CHECK-Einschränkungen zur Folge haben.</span><span class="sxs-lookup"><span data-stu-id="c9e63-109">Your modifications would result in improperly formed derived columns, default constraints, or check constraints.</span></span>  
  
-   <span data-ttu-id="c9e63-110">Die Änderung des Datentyps für eine Spalte könnte zu Datenverlusten führen.</span><span class="sxs-lookup"><span data-stu-id="c9e63-110">A modification to a column's data type might cause data loss.</span></span>  
  
-   <span data-ttu-id="c9e63-111">Eine Änderung hätte einen Index von mehr als 900 Byte zur Folge.</span><span class="sxs-lookup"><span data-stu-id="c9e63-111">A modification would result in an index greater than 900 bytes.</span></span>  
  
-   <span data-ttu-id="c9e63-112">Eine Änderung würde eine Tabelle bzw. Spalte ändern und würde dadurch zu einer an ein Schema gebundenen Sicht oder einer benutzerdefinierten Funktion führen.</span><span class="sxs-lookup"><span data-stu-id="c9e63-112">A modification would change a table or column contributing to a schema-bound view or user-defined function.</span></span>  
  
-   <span data-ttu-id="c9e63-113">Eine Änderung würde zur Neuerstellung einer Tabelle mit mindestens einem verschlüsselten Trigger führen, wobei die Trigger gelöscht werden würden.</span><span class="sxs-lookup"><span data-stu-id="c9e63-113">A modification would result in the re-creation of a table that has one or more encrypted triggers; the triggers will be dropped.</span></span>  
  
-   <span data-ttu-id="c9e63-114">Die Änderungen ergeben besondere Einstellungen von ANSI_NULLS und/oder ANSI_PADDING für die Spalten innerhalb einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c9e63-114">Your modifications will yield noteworthy settings of ANSI_NULLS or ANSI_PADDING or both for the columns within one table.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c9e63-115">Tastatur</span><span class="sxs-lookup"><span data-stu-id="c9e63-115">Options</span></span>  
 <span data-ttu-id="c9e63-116">**Ja**</span><span class="sxs-lookup"><span data-stu-id="c9e63-116">**Yes**</span></span>  
 <span data-ttu-id="c9e63-117">Setzen Sie den Vorgang fort, und generieren Sie das Änderungsskript, oder übermitteln Sie die Änderungen an die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="c9e63-117">Proceed with the operation and generate the change script or transmit the modifications to the database.</span></span> <span data-ttu-id="c9e63-118">Der Commitvorgang kann trotzdem noch fehlschlagen, wenn Sie nicht über die Berechtigungen zum Ändern der Datenbank verfügen, wenn die Änderungen bewirken, dass der Index größer als 900 Bytes wird, oder wenn die Änderungen eine falsch formatierte berechnete Spalte, Standardeinschränkungen oder CHECK-Einschränkungen zur Folge haben.</span><span class="sxs-lookup"><span data-stu-id="c9e63-118">The commit operation can still fail if you do not have privileges to modify the database, if your modifications will result in an index greater than 900 bytes, or if your modifications will result in an improperly formed computed column, default constraint, or check constraint.</span></span>  
  
 <span data-ttu-id="c9e63-119">**Nein**</span><span class="sxs-lookup"><span data-stu-id="c9e63-119">**No**</span></span>  
 <span data-ttu-id="c9e63-120">Brechen Sie den Speichervorgang ab.</span><span class="sxs-lookup"><span data-stu-id="c9e63-120">Cancel the save action.</span></span>  
  
 <span data-ttu-id="c9e63-121">**Textdatei speichern**</span><span class="sxs-lookup"><span data-stu-id="c9e63-121">**Save Text File**</span></span>  
 <span data-ttu-id="c9e63-122">Zeigen Sie das Dialogfeld **Speichern unter** an, in dem Sie einen Speicherort für eine Textdatei angeben können, die eine Liste der Warnungen enthält.</span><span class="sxs-lookup"><span data-stu-id="c9e63-122">Display the **Save As** dialog box, where you can specify a location for a text file containing a list of the warnings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9e63-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c9e63-123">See Also</span></span>  
 <span data-ttu-id="c9e63-124">[Entwerfen von Tabellen &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="c9e63-124">[Design Tables &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="c9e63-125">Themen zur Vorgehensweise: Entwerfen von Abfragen und Sichten &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="c9e63-125">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
