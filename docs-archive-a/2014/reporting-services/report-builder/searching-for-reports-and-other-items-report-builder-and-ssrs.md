---
title: Suchen nach Berichten und anderen Elementen (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6a586659-5c2b-453b-8f40-a3a469277b17
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a964cbdbc674fb3d29e18b5e5075695f0033801e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608349"
---
# <a name="searching-for-reports-and-other-items-report-builder--and-ssrs"></a><span data-ttu-id="5c835-102">Suchen nach Berichten und anderen Elementen (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="5c835-102">Searching for Reports and Other Items (Report Builder  and SSRS)</span></span>
  <span data-ttu-id="5c835-103">Mithilfe des Berichts-Managers können Sie auf einem Berichtsserver nach bestimmten Elementen anhand des Namens oder einer Beschreibung suchen.</span><span class="sxs-lookup"><span data-stu-id="5c835-103">You can use Report Manager to search a report server for specific items by name or description.</span></span> <span data-ttu-id="5c835-104">Sie haben die Möglichkeit, nach veröffentlichten Berichten, Berichtsmodellen, Ordnern, freigegebenen Datenquellen und Ressourcen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="5c835-104">You can search for published reports, report models, folders, shared data sources, and resources.</span></span> <span data-ttu-id="5c835-105">Es ist nicht möglich, nach Zeitplänen, Besitzern, Rollenzuweisungen, bestimmten Momentaufnahmen im Berichtsverlauf oder nach Abonnements zu suchen.</span><span class="sxs-lookup"><span data-stu-id="5c835-105">You cannot search for schedules, owners, role assignments, specific snapshots in report history, or subscriptions.</span></span> <span data-ttu-id="5c835-106">Die Suche wird in der Berichtsserver-Datenbank ausgeführt, in der die Elemente gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="5c835-106">The search is performed on the report server database where the items are stored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5c835-107">Bei einer Dateisystemsuche werden keine Suchergebnisse für Elemente zurückgegeben, die von einem Berichtsserver verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="5c835-107">Performing a file system search will not return search results for items managed by a report server.</span></span>  
  
-   <span data-ttu-id="5c835-108">Geben Sie für die Suche nach Elementen im Berichts-Manager oben auf der Seite in das Textfeld **Suchen nach** eine Suchzeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="5c835-108">To search for items in Report Manager, type a search string in the **Search for** text box at the top of the page.</span></span> <span data-ttu-id="5c835-109">Suchvorgänge beginnen in der Ordnerhierarchie im Knoten der obersten Ebene und werden in den untergeordneten Zweigen fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="5c835-109">Searches begin at the top node in the folder hierarchy and then proceed through every branch.</span></span> <span data-ttu-id="5c835-110">Falls Sie keine Zugriffsberechtigung für einen bestimmten Zweig haben, wird dieser ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="5c835-110">If you do not have permission to access a specific branch, that branch is skipped.</span></span> <span data-ttu-id="5c835-111">Dies ist der Fall bei Ordnern vom Typ Meine Berichte anderer Benutzer und bei anderen Ordnern, die nicht generell verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5c835-111">This applies to My Reports folders that belong to other users, and to other folders that are not generally available.</span></span> <span data-ttu-id="5c835-112">Nur Berichte und Elemente, die Sie anzeigen dürfen, werden in die Suchergebnisse einbezogen.</span><span class="sxs-lookup"><span data-stu-id="5c835-112">Only reports and items that you have permission to view are included in the search results.</span></span>  
  
-   <span data-ttu-id="5c835-113">Um anhand des Namens oder einer Beschreibung nach einem Element zu suchen, geben Sie den gesamten Text oder einen Teil davon an.</span><span class="sxs-lookup"><span data-stu-id="5c835-113">To search for an item by name or description, specify all or part of the text that you want to match.</span></span> <span data-ttu-id="5c835-114">Bei der Suchzeichenfolge wird die Groß/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="5c835-114">The search string is not case-sensitive.</span></span> <span data-ttu-id="5c835-115">Suchoperatoren wie z.B. Pluszeichen (+) oder Minuszeichen (–) zum Ein- oder Ausschließen von Suchkriterien sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="5c835-115">You cannot use search operators such as plus (+) or minus (-) symbols to require or exclude search criteria.</span></span>  
  
-   <span data-ttu-id="5c835-116">Verwenden Sie die Symbolleiste oben im Bericht, um nach Text in einem Bericht zu suchen.</span><span class="sxs-lookup"><span data-stu-id="5c835-116">To search for specific text within a report, use the toolbar at the top of the report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5c835-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5c835-117">See Also</span></span>  
 <span data-ttu-id="5c835-118">[Suchen und Anzeigen von Berichten in Berichts-Manager &#40;Berichts-Generator und SSRS&#41;](finding-and-viewing-reports-in-the-web-portal-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5c835-118">[Finding and Viewing Reports in Report Manager &#40;Report Builder and SSRS&#41;](finding-and-viewing-reports-in-the-web-portal-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5c835-119">[Verwenden von Meine Berichte &#40;Berichts-Generator und SSRS&#41;](using-my-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5c835-119">[Using My Reports &#40;Report Builder and SSRS&#41;](using-my-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5c835-120">[Suchen, anzeigen und Verwalten von Berichten &#40;Berichts-Generator und SSRS &#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5c835-120">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="5c835-121">Öffnen und Schließen eines Berichts (Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="5c835-121">Open and Close a Report &#40;Report Manager&#41;</span></span>](../reports/open-and-close-a-report-report-manager.md)  
  
  
