---
title: Auschecken rückgängig machen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- VisualStudio.SourcControl.UndoCheckDialog
helpviewer_keywords:
- checking out files
- checkout source controls [SQL Server]
- undoing checkouts
ms.assetid: a6596b20-3aa5-4dc4-a4c5-3649f1f5a20e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ff6e6041b59caa75bf7f8530d915db48e0379338
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608801"
---
# <a name="undo-checkouts"></a><span data-ttu-id="48b91-102">Rückgängigmachen von Auscheckvorgängen</span><span class="sxs-lookup"><span data-stu-id="48b91-102">Undo Checkouts</span></span>
  <span data-ttu-id="48b91-103">Mit dem Befehl **Rückgängig** Auschecken können Sie ein vorhandenes Checkout abbrechen.</span><span class="sxs-lookup"><span data-stu-id="48b91-103">You can use the **Undo Checkout** command to cancel an existing checkout.</span></span> <span data-ttu-id="48b91-104">Dies bietet sich vor allem an, wenn Sie eine Datei geändert und gespeichert haben und zu einem späteren Zeitpunkt ein Rollback für die Änderungen ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="48b91-104">This is particularly useful when you have modified and saved a file, and then later need to roll back your changes.</span></span>  
  
 <span data-ttu-id="48b91-105">Abhängig von den Optionen, die Sie im Dialogfeld **Erweiterte Optionen rückgängig machen** festlegen, verlässt die Studio-Umgebung entweder die Arbeitskopie des Elements auf dem lokalen Datenträger oder ersetzt Sie durch die neueste Version der Quell Code Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="48b91-105">Depending on the options you set in the **Undo Checkout Advanced Options** dialog box, the Studio environment either leaves the working copy of the item on your local disk or replaces it with the latest source-controlled version.</span></span> <span data-ttu-id="48b91-106">Wenn ein Benutzer das Element außerhalb des Kontexts des Quellcodeverwaltungssystems geändert hat, handelt es sich bei der abgerufenen Version möglicherweise nicht um die letzte Version.</span><span class="sxs-lookup"><span data-stu-id="48b91-106">If someone has modified the item outside the context of the source control system, the retrieved version may not be the latest one.</span></span>  
  
### <a name="to-undo-a-checkout"></a><span data-ttu-id="48b91-107">So machen Sie einen Auscheckvorgang rückgängig</span><span class="sxs-lookup"><span data-stu-id="48b91-107">To undo a checkout</span></span>  
  
1.  <span data-ttu-id="48b91-108">Wählen Sie im Projektmappen-Explorer das Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="48b91-108">In Solution Explorer, select the project.</span></span>  
  
2.  <span data-ttu-id="48b91-109">Zeigen Sie im Menü **Datei** auf **Quell**Code Verwaltung, und klicken Sie dann auf Auschecken **rückgängig machen**.</span><span class="sxs-lookup"><span data-stu-id="48b91-109">On the **File** menu, point to **Source Control**, and then click **Undo Checkout**.</span></span>  
  
3.  <span data-ttu-id="48b91-110">Wählen Sie im Dialogfeld **rückgängig machen** die entsprechenden Optionen aus, und klicken Sie dann auf die Schaltfläche **rückgängig machen** .</span><span class="sxs-lookup"><span data-stu-id="48b91-110">In the **Undo Checkout** dialog box, select the appropriate options, and then click the **Undo Checkout** button.</span></span>  
  
     <span data-ttu-id="48b91-111">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="48b91-111">**Columns**</span></span>  
     <span data-ttu-id="48b91-112">Bestimmt die anzuzeigenden Spalten und die Reihenfolge, in der sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="48b91-112">Identify the columns to display and the order in which they are displayed.</span></span>  
  
     <span data-ttu-id="48b91-113">**Flache Ansicht**</span><span class="sxs-lookup"><span data-stu-id="48b91-113">**Flat View**</span></span>  
     <span data-ttu-id="48b91-114">Zeigt die Elemente als flache Listen unter der entsprechenden Verbindung mit der Quellcodeverwaltung an.</span><span class="sxs-lookup"><span data-stu-id="48b91-114">Display the items as flat lists under their source control connection.</span></span>  
  
     <span data-ttu-id="48b91-115">**Name**</span><span class="sxs-lookup"><span data-stu-id="48b91-115">**Name**</span></span>  
     <span data-ttu-id="48b91-116">Zeigt die Namen der Elemente an, für die das Auschecken rückgängig gemacht werden soll.</span><span class="sxs-lookup"><span data-stu-id="48b91-116">Displays the names of the items for which to undo the checkout.</span></span> <span data-ttu-id="48b91-117">Die Elemente werden mit einem aktivierten Kontrollkästchen neben dem Namen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="48b91-117">Items appear with the check boxes next to them selected.</span></span> <span data-ttu-id="48b91-118">Wenn für ein Element das Auschecken nicht rückgängig gemacht werden soll, deaktivieren Sie das entsprechende Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="48b91-118">If you do not want to undo the checkout of an item, clear its check box.</span></span>  
  
     <span data-ttu-id="48b91-119">**Optionen**</span><span class="sxs-lookup"><span data-stu-id="48b91-119">**Options**</span></span>  
     <span data-ttu-id="48b91-120">Zeigt die für das Quellcodeverwaltungs-Plug-In spezifischen Optionen zum Rückgängigmachen des Auscheckens, wenn Sie auf den Pfeil rechts neben der Schaltfläche klicken.</span><span class="sxs-lookup"><span data-stu-id="48b91-120">Displays source control plug-in-specific undo checkout options when the arrow to the right of the button is clicked.</span></span>  
  
     <span data-ttu-id="48b91-121">**Sort**</span><span class="sxs-lookup"><span data-stu-id="48b91-121">**Sort**</span></span>  
     <span data-ttu-id="48b91-122">Sortiert die Reihenfolge der Anzeigespalten.</span><span class="sxs-lookup"><span data-stu-id="48b91-122">Sort the order of the display columns.</span></span>  
  
     <span data-ttu-id="48b91-123">**Strukturansicht**</span><span class="sxs-lookup"><span data-stu-id="48b91-123">**Tree View**</span></span>  
     <span data-ttu-id="48b91-124">Zeigt den Ordner und die Elementhierarchie für die Elemente an, für die das Auschecken rückgängig gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="48b91-124">Display the folder and item hierarchy for items on which you are reversing the checkout.</span></span>  
  
     <span data-ttu-id="48b91-125">**Rückgängig machen**</span><span class="sxs-lookup"><span data-stu-id="48b91-125">**Undo Checkout**</span></span>  
     <span data-ttu-id="48b91-126">Macht das Auschecken rückgängig, wobei alle Änderungen an der ausgecheckten Datei verworfen werden.</span><span class="sxs-lookup"><span data-stu-id="48b91-126">Revert the checkout, discarding any changes to the checked-out file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48b91-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="48b91-127">See Also</span></span>  
 <span data-ttu-id="48b91-128">[Auschecken von Dateien](../../2014/database-engine/check-out-files.md) </span><span class="sxs-lookup"><span data-stu-id="48b91-128">[Check Out Files](../../2014/database-engine/check-out-files.md) </span></span>  
 [<span data-ttu-id="48b91-129">Verwalten von Auscheckvorgängen</span><span class="sxs-lookup"><span data-stu-id="48b91-129">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  
