---
title: Interaktiver Microsoft-Replikationskonfliktlöser | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replconflictviewer.interactiveresolver.f1
ms.assetid: d3d4a480-782b-4b1d-b839-565c8cf6cb24
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c8cbd2231ab1ab357321f9887bced986e182e608
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725525"
---
# <a name="microsoft-replication-interactive-conflict-resolver"></a><span data-ttu-id="53f18-102">Interaktiver Microsoft-Replikationskonfliktlöser</span><span class="sxs-lookup"><span data-stu-id="53f18-102">Microsoft Replication Interactive Conflict Resolver</span></span>
  <span data-ttu-id="53f18-103">Der interaktive Replikationskonfliktlöser kann für Mergeabonnements verwendet werden, die mithilfe der Synchronisierungsverwaltung von Windows synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="53f18-103">The Interactive Conflict Resolver can be used for merge subscriptions that are synchronized using Windows Synchronization Manager.</span></span> <span data-ttu-id="53f18-104">Er ermöglicht es Ihnen, das Ergebnis von Datenkonflikten anzuzeigen, zu vergleichen, zu bearbeiten und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="53f18-104">It allows you to view, compare, edit, and select the outcome for data conflicts.</span></span> <span data-ttu-id="53f18-105">Die Replikation beinhaltet auch den Konflikt-Viewer, der es Ihnen ermöglicht, die Ergebnisse von Konflikten anzuzeigen und zu ändern, nachdem für sie ein Commit ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="53f18-105">Replication also includes the Conflict Viewer, which allows you to view and modify conflict outcomes after they have been committed.</span></span> <span data-ttu-id="53f18-106">Mithilfe des interaktiven Konfliktlösers können Sie das Ergebnis während der Synchronisierung auswählen.</span><span class="sxs-lookup"><span data-stu-id="53f18-106">The Interactive Conflict Resolver allows you to select the outcome during synchronization.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="53f18-107">Konflikte im Zusammenhang mit logischen Datensätzen werden nicht im interaktiven Konfliktlöser angezeigt.</span><span class="sxs-lookup"><span data-stu-id="53f18-107">Conflicts that involve logical records are not displayed in the Interactive Resolver.</span></span> <span data-ttu-id="53f18-108">Mit den gespeicherten Replikationsprozeduren können Informationen zu diesen Konflikten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="53f18-108">To view information about these conflicts, use replication stored procedures.</span></span> <span data-ttu-id="53f18-109">Weitere Informationen finden Sie unter [Anzeigen von Konfliktinformationen zu Mergeveröffentlichungen &#40;Replikationsprogrammierung mit Transact-SQL&#41;](view-conflict-information-for-merge-publications.md)</span><span class="sxs-lookup"><span data-stu-id="53f18-109">For more information, see [View Conflict Information for Merge Publications &#40;Replication Transact-SQL Programming&#41;](view-conflict-information-for-merge-publications.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="53f18-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="53f18-110">Options</span></span>  
 <span data-ttu-id="53f18-111">**Spaltenname**</span><span class="sxs-lookup"><span data-stu-id="53f18-111">**Column name**</span></span>  
 <span data-ttu-id="53f18-112">Der Name aller Spalten in der Tabelle</span><span class="sxs-lookup"><span data-stu-id="53f18-112">The name of all columns in the table.</span></span> <span data-ttu-id="53f18-113">Die Daten einer oder mehrerer Spalten können Konflikte verursachen.</span><span class="sxs-lookup"><span data-stu-id="53f18-113">One or more columns might have conflicting data.</span></span> <span data-ttu-id="53f18-114">Unabhängig davon, zwischen welchen Spalten es zu Konflikten kommt, überschreibt die gesamte gewinnende Zeile die gesamte verlierende Zeile.</span><span class="sxs-lookup"><span data-stu-id="53f18-114">Regardless of which columns conflict, the entire winning row will overwrite the entire losing row.</span></span>  
  
 <span data-ttu-id="53f18-115">**Vorgeschlagene Lösung**</span><span class="sxs-lookup"><span data-stu-id="53f18-115">**Suggested Resolution**</span></span>  
 <span data-ttu-id="53f18-116">Die vom Konfliktlöser für den Artikel vorgeschlagene Lösung.</span><span class="sxs-lookup"><span data-stu-id="53f18-116">The suggested resolution provided by the conflict resolver for the article.</span></span>  
  
 <span data-ttu-id="53f18-117">**Herausgeber**</span><span class="sxs-lookup"><span data-stu-id="53f18-117">**Publisher**</span></span>  
 <span data-ttu-id="53f18-118">Der Datenwert auf dem Verleger.</span><span class="sxs-lookup"><span data-stu-id="53f18-118">The data value at the Publisher.</span></span>  
  
 <span data-ttu-id="53f18-119">**Abonnent**</span><span class="sxs-lookup"><span data-stu-id="53f18-119">**Subscriber**</span></span>  
 <span data-ttu-id="53f18-120">Der Datenwert auf dem Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="53f18-120">The data value at the Subscriber.</span></span>  
  
 <span data-ttu-id="53f18-121">**Vorschläge akzeptieren**, **Verleger akzeptieren**und **Abonnenten akzeptieren**</span><span class="sxs-lookup"><span data-stu-id="53f18-121">**Accept Suggested**, **Accept Publisher**, and **Accept Subscriber**</span></span>  
 <span data-ttu-id="53f18-122">Klicken Sie, je nachdem wer den Konflikt verloren hat, entweder auf Abonnent oder Verleger, um die anzuwendende Zeile anzunehmen.</span><span class="sxs-lookup"><span data-stu-id="53f18-122">Click to accept the row that will be applied at either the Publisher or the Subscriber, depending on which one lost the conflict.</span></span> <span data-ttu-id="53f18-123">Wenn der Verleger den Konflikt verloren hat, empfangen alle anderen Abonnenten bei der nächsten Synchronisierung mit dem Verleger die gewinnende Zeile.</span><span class="sxs-lookup"><span data-stu-id="53f18-123">If the Publisher lost the conflict, all other Subscribers will receive the winning row the next time they synchronize with the Publisher.</span></span>  
  
 <span data-ttu-id="53f18-124">**Verbleibende Konflikte automatisch lösen**</span><span class="sxs-lookup"><span data-stu-id="53f18-124">**Resolve remaining conflicts automatically**</span></span>  
 <span data-ttu-id="53f18-125">Lösen Sie alle verbleibenden Konflikte anhand der für den Artikel vom Konfliktlöser vorgeschlagenen Lösung.</span><span class="sxs-lookup"><span data-stu-id="53f18-125">Resolve all remaining conflicts using the suggested resolution provided by the conflict resolver for the article.</span></span>  
  
 <span data-ttu-id="53f18-126">**Details dieses Konflikts zur späteren Bezugnahme protokollieren**</span><span class="sxs-lookup"><span data-stu-id="53f18-126">**Log the details of the conflict for later reference**</span></span>  
 <span data-ttu-id="53f18-127">Protokollieren Sie die Details des Konflikts in Systemtabellen.</span><span class="sxs-lookup"><span data-stu-id="53f18-127">Logs the details of the conflict in system tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53f18-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="53f18-128">See Also</span></span>  
 <span data-ttu-id="53f18-129">[Interaktive Konfliktlösung](merge/advanced-merge-replication-conflict-interactive-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="53f18-129">[Interactive Conflict Resolution](merge/advanced-merge-replication-conflict-interactive-resolution.md) </span></span>  
 <span data-ttu-id="53f18-130">[Anzeigen und Lösen von Datenkonflikten für Mergeveröffentlichungen &#40;SQL Server Management Studio&#41;](view-and-resolve-data-conflicts-for-merge-publications.md) </span><span class="sxs-lookup"><span data-stu-id="53f18-130">[View and Resolve Data Conflicts for Merge Publications &#40;SQL Server Management Studio&#41;](view-and-resolve-data-conflicts-for-merge-publications.md) </span></span>  
 <span data-ttu-id="53f18-131">[Synchronisieren eines Abonnements mithilfe der Synchronisierungsverwaltung von Windows &#40;Synchronisierungsverwaltung von Windows&#41;](synchronize-a-subscription-using-windows-synchronization-manager.md) </span><span class="sxs-lookup"><span data-stu-id="53f18-131">[Synchronize a Subscription Using Windows Synchronization Manager &#40;Windows Synchronization Manager&#41;](synchronize-a-subscription-using-windows-synchronization-manager.md) </span></span>  
 [<span data-ttu-id="53f18-132">Advanced Merge Replication Conflict Detection and Resolution (Erweiterte Konflikterkennung und -lösung bei der Mergereplikation)</span><span class="sxs-lookup"><span data-stu-id="53f18-132">Advanced Merge Replication Conflict Detection and Resolution</span></span>](merge/advanced-merge-replication-conflict-detection-and-resolution.md)  
  
  
