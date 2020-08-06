---
title: Löschen von Katalogelementen (Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.deleteitems.f1
ms.assetid: b0599e01-6dc3-4484-80d4-022a412e0ebd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d2a1824f2611165c9ae891fcb702418244f3621e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616934"
---
# <a name="delete-catalog-items-management-studio"></a><span data-ttu-id="6bcb6-102">Katalogelemente löschen (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="6bcb6-102">Delete Catalog Items (Management Studio)</span></span>
  <span data-ttu-id="6bcb6-103">Verwenden Sie diese Seite, um freigegebene Zeitpläne und Rollendefinitionen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="6bcb6-103">Use this page to delete shared schedules and role definitions.</span></span>  
  
 <span data-ttu-id="6bcb6-104">Wenn Sie einen freigegebenen Zeitplan löschen, der von mehreren Berichten und Abonnements verwendet wird, erstellt der Berichtsserver für Berichte und Abonnements, die vorher den freigegebenen Zeitplan verwendet haben, eigene Zeitpläne.</span><span class="sxs-lookup"><span data-stu-id="6bcb6-104">If you delete a shared schedule that is used by multiple reports and subscriptions, the report server will create individual schedules for each report and subscription that previously used the shared schedule.</span></span> <span data-ttu-id="6bcb6-105">Jeder dieser neuen Zeitpläne enthält das Datum, die Zeit und die Wiederholungsoption, die in dem freigegebenen Zeitplan angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="6bcb6-105">Each new individual schedule will contain the date, time, and recurrence pattern that was specified in the shared schedule.</span></span> <span data-ttu-id="6bcb6-106">Beachten Sie, dass [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] keine zentrale Verwaltung für einzelne Zeitpläne bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="6bcb6-106">Note that [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not provide central management of individual schedules.</span></span> <span data-ttu-id="6bcb6-107">Wenn Sie einen freigegebenen Zeitplan löschen, müssen Sie jetzt die Zeitplaninformationen für jedes einzelne Element verwalten.</span><span class="sxs-lookup"><span data-stu-id="6bcb6-107">If you delete a shared schedule, you will now need to maintain the schedule information for each individual item.</span></span> <span data-ttu-id="6bcb6-108">Bevor Sie einen freigegebenen Zeitplan löschen, verwenden Sie die [Seite Berichte](schedule-properties-reports-page.md) , um zu ermitteln, welche Berichte den freigegebenen Zeitplan gerade verwenden.</span><span class="sxs-lookup"><span data-stu-id="6bcb6-108">Before deleting a shared schedule, use the [Reports page](schedule-properties-reports-page.md) to determine which reports are currently using the shared schedule.</span></span>  
  
 <span data-ttu-id="6bcb6-109">Von den Rollendefinitionen können Sie nur jene löschen, die aktuell nicht in einer Rollenzuweisung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6bcb6-109">For role definitions, you can only delete those that are not actively used in a role assignment.</span></span> <span data-ttu-id="6bcb6-110">Wenn Sie versuchen, eine Rolle zu löschen, die gerade verwendet wird, weist der Berichtsserver diesen Löschversuch ab und zeigt stattdessen eine Fehlermeldung an.</span><span class="sxs-lookup"><span data-stu-id="6bcb6-110">If you try to delete a role that is currently in use, the report server will not delete the role and you will see an error message to that effect.</span></span> <span data-ttu-id="6bcb6-111">Wenn die Seite eine einzelne Rollendefinition enthält, die aktuell nicht verwendet wird, wird diese gelöscht, sobald Sie auf **OK**klicken.</span><span class="sxs-lookup"><span data-stu-id="6bcb6-111">If this page contains a single role definition that is not currently in use, it will be deleted when you click **OK**.</span></span> <span data-ttu-id="6bcb6-112">Wenn diese Seite mehrere Rollen enthält, können Sie nicht auswählen, welche Rollen gelöscht und welche beibehalten werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6bcb6-112">If this page contains multiple roles, you cannot select which roles to keep or remove.</span></span> <span data-ttu-id="6bcb6-113">Alle nicht verwendeten Rollendefinitionen werden gelöscht, wenn Sie auf **OK**klicken.</span><span class="sxs-lookup"><span data-stu-id="6bcb6-113">All unused role definitions will be deleted when you click **OK**.</span></span>  
  
 <span data-ttu-id="6bcb6-114">Einen Löschvorgang können Sie nicht rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="6bcb6-114">You cannot undo a delete operation.</span></span> <span data-ttu-id="6bcb6-115">Wenn Sie ein bereits gelöschtes Element wiederherstellen möchten, müssen Sie dieses entweder erneut erstellen oder eine Sicherungskopie der Berichtsserver-Datenbank wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="6bcb6-115">If you want to recover an item that you deleted, you must either recreate it or restore a backup copy of the report server database.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6bcb6-116">Tastatur</span><span class="sxs-lookup"><span data-stu-id="6bcb6-116">Options</span></span>  
 <span data-ttu-id="6bcb6-117">**Name**</span><span class="sxs-lookup"><span data-stu-id="6bcb6-117">**Name**</span></span>  
 <span data-ttu-id="6bcb6-118">Gibt den Namen des Elements an, das Sie gerade löschen.</span><span class="sxs-lookup"><span data-stu-id="6bcb6-118">Specifies the name of the item you are deleting.</span></span>  
  
 <span data-ttu-id="6bcb6-119">**Typ**</span><span class="sxs-lookup"><span data-stu-id="6bcb6-119">**Type**</span></span>  
 <span data-ttu-id="6bcb6-120">Zeigt den Typ des Elements an, das Sie gerade löschen.</span><span class="sxs-lookup"><span data-stu-id="6bcb6-120">Shows the type of item you are deleting.</span></span>  
  
 <span data-ttu-id="6bcb6-121">**Besitzer**</span><span class="sxs-lookup"><span data-stu-id="6bcb6-121">**Owner**</span></span>  
 <span data-ttu-id="6bcb6-122">Zeigt den Namen des Besitzers an.</span><span class="sxs-lookup"><span data-stu-id="6bcb6-122">Shows the name of the owner.</span></span> <span data-ttu-id="6bcb6-123">In den meisten Fällen lautet dieser System.</span><span class="sxs-lookup"><span data-stu-id="6bcb6-123">In most cases, this is System.</span></span>  
  
 <span data-ttu-id="6bcb6-124">**Status**</span><span class="sxs-lookup"><span data-stu-id="6bcb6-124">**Status**</span></span>  
 <span data-ttu-id="6bcb6-125">Zeigt die Fortschrittsinformationen für einen Löschvorgang an.</span><span class="sxs-lookup"><span data-stu-id="6bcb6-125">Shows progress information for a delete operation.</span></span>  
  
 <span data-ttu-id="6bcb6-126">**Fehler**</span><span class="sxs-lookup"><span data-stu-id="6bcb6-126">**Error**</span></span>  
 <span data-ttu-id="6bcb6-127">Zeigt einen Fehlercode an, wenn beim Löschen eines Elements ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="6bcb6-127">Displays an error code if an error occurs while deleting an item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bcb6-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6bcb6-128">See Also</span></span>  
 <span data-ttu-id="6bcb6-129">[Löschen eines Elements &#40;Management Studio&#41;](delete-an-item-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="6bcb6-129">[Delete an Item &#40;Management Studio&#41;](delete-an-item-management-studio.md) </span></span>  
 <span data-ttu-id="6bcb6-130">[Berichtsserver im Management Studio (F1-Hilfe)](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="6bcb6-130">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="6bcb6-131">Create, Modify, and Delete Schedules (Erstellen, Ändern oder Löschen von Zeitplänen)</span><span class="sxs-lookup"><span data-stu-id="6bcb6-131">Create, Modify, and Delete Schedules</span></span>](../subscriptions/create-modify-and-delete-schedules.md)  
  
  
