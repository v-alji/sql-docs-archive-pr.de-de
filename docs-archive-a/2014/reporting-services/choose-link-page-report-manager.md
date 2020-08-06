---
title: Link auswählen (Seite) (Berichts-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a89a555d-efa3-45d6-951e-db78ec6a2c8e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bc40fe726555babee8d9940e198a93577bd6a09f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615865"
---
# <a name="choose-link-page-report-manager"></a><span data-ttu-id="52b07-102">Link auswählen (Seite) (Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="52b07-102">Choose Link Page (Report Manager)</span></span>
  <span data-ttu-id="52b07-103">Mithilfe der Seite Link auswählen können Sie einen anderen Bericht als Grundlage für den aktuell ausgewählten verknüpften Bericht wählen.</span><span class="sxs-lookup"><span data-stu-id="52b07-103">Use the Choose Link page to choose a different report upon which to base the currently selected linked report.</span></span> <span data-ttu-id="52b07-104">Verknüpfte Berichte basieren auf anderen Berichten, die bereits auf einem Berichtsserver publiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="52b07-104">Linked reports are based on other reports already published to a report server.</span></span> <span data-ttu-id="52b07-105">Ein verknüpfter Bericht verwendet das Layout und die Daten des Basisberichts, besitzt aber eigene Eigenschaftenseiten, damit Sie Parametereigenschaften, Sicherheitseinstellungen, Name, Beschreibung und Speicherort anpassen können.</span><span class="sxs-lookup"><span data-stu-id="52b07-105">A linked report uses the layout and data of the base report, but has separate property pages so that you can customize parameter properties, security settings, name, description, and location.</span></span>  
  
 <span data-ttu-id="52b07-106">Mithilfe der Seite Link auswählen können Sie einen anderen veröffentlichten Bericht für die Verwendung mit dem verknüpften Bericht wählen.</span><span class="sxs-lookup"><span data-stu-id="52b07-106">Through the Choose Link page, you can choose a different published report to use with the linked report.</span></span> <span data-ttu-id="52b07-107">Auf andere Einstellungen des verknüpften Berichts (z. B. Sicherheits- und Parametereinstellungen) haben die Änderungen an den Linkinformationen keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="52b07-107">Other settings of the linked report (such as security and parameter settings) are unaffected by changes to the link information.</span></span> <span data-ttu-id="52b07-108">Der Berichtsserver überprüft Ihre Auswahl nicht. Vergewissern Sie sich also, dass der von Ihnen gewählte Bericht die gleichen Parameter besitzt wie die, die Sie für den verknüpften Bericht angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="52b07-108">The report server will not validate your selection, so be sure to choose a report that has the same parameters as those you specified on the linked report.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="52b07-109">Navigation</span><span class="sxs-lookup"><span data-stu-id="52b07-109">Navigation</span></span>  
 <span data-ttu-id="52b07-110">Verwenden Sie folgendes Verfahren, um zu dieser Position in der Benutzeroberfläche zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="52b07-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-choose-link-page"></a><span data-ttu-id="52b07-111">So öffnen Sie die Seite 'Link auswählen'</span><span class="sxs-lookup"><span data-stu-id="52b07-111">To open the Choose Link page</span></span>  
  
1.  <span data-ttu-id="52b07-112">Öffnen Sie den Berichts-Manager, und suchen Sie den verknüpften Bericht, den Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="52b07-112">Open Report Manager, and locate the linked report you want to change.</span></span>  
  
2.  <span data-ttu-id="52b07-113">Zeigen Sie auf den verknüpften Bericht, und klicken Sie auf den Dropdownpfeil.</span><span class="sxs-lookup"><span data-stu-id="52b07-113">Hover over the linked report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="52b07-114">Klicken Sie im Dropdownmenü auf **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="52b07-114">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="52b07-115">Dadurch wird die Seite **Allgemeine Eigenschaften** für den verknüpften Bericht geöffnet.</span><span class="sxs-lookup"><span data-stu-id="52b07-115">This opens the **General** properties page for the linked report.</span></span>  
  
4.  <span data-ttu-id="52b07-116">Klicken Sie auf der Registerkarte **Allgemein** auf der Eigenschaftenseite auf **Link ändern**.</span><span class="sxs-lookup"><span data-stu-id="52b07-116">On the **General** tab, on the properties page, click **Change Link**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="52b07-117">Tastatur</span><span class="sxs-lookup"><span data-stu-id="52b07-117">Options</span></span>  
 <span data-ttu-id="52b07-118">**Location**</span><span class="sxs-lookup"><span data-stu-id="52b07-118">**Location**</span></span>  
 <span data-ttu-id="52b07-119">Geben Sie den vollständigen Namen des veröffentlichten Berichts an, einschließlich des Ordnerpfads und des Berichtsnamens.</span><span class="sxs-lookup"><span data-stu-id="52b07-119">Specify the full name of the published report, including the folder path and report name.</span></span> <span data-ttu-id="52b07-120">Sie können den vollständigen Namen des Berichts eingeben oder die Strukturansicht verwenden, um zu dem gewünschten Bericht zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="52b07-120">You can type the full name of the report or use the tree view to navigate to the report you want to use.</span></span>  
  
 <span data-ttu-id="52b07-121">**Strukturansicht**</span><span class="sxs-lookup"><span data-stu-id="52b07-121">**Tree view**</span></span>  
 <span data-ttu-id="52b07-122">Zeigt alle Ordner in der Berichtsserver-Ordnerhierarchie an.</span><span class="sxs-lookup"><span data-stu-id="52b07-122">Shows all of the folders in the report server folder hierarchy.</span></span> <span data-ttu-id="52b07-123">Wenn Sie mithilfe der Strukturansicht einen Wert für das Feld **Speicherort** auswählen möchten, klicken Sie auf den Namen des Berichts.</span><span class="sxs-lookup"><span data-stu-id="52b07-123">To use the tree view to fill in the **Location** field, click the name of the report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52b07-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="52b07-124">See Also</span></span>  
 <span data-ttu-id="52b07-125">[Allgemeine Eigenschaften (Seite), Berichte &#40;Berichts-Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="52b07-125">[General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span></span>  
 <span data-ttu-id="52b07-126">[Die Seite "Neuer verknüpfter Bericht" &#40;Berichts-Manager&#41;](../../2014/reporting-services/new-linked-report-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="52b07-126">[New Linked Report Page &#40;Report Manager&#41;](../../2014/reporting-services/new-linked-report-page-report-manager.md) </span></span>  
 [<span data-ttu-id="52b07-127">Berichts-Manager (F1-Hilfe)</span><span class="sxs-lookup"><span data-stu-id="52b07-127">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
