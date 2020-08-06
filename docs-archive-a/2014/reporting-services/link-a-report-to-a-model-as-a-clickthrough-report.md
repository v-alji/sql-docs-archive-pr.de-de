---
title: Verknüpfen eines Berichts mit einem Modell als Bericht mit durch Klicken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- customizing clickthrough reports
- clickthrough reports, customizing
- clickthrough reports, templates
ms.assetid: 3af42de3-67ef-41c2-bc8a-7045baec6f63
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cb84f8036dbe5a1694628144f0b948452261ca75
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609703"
---
# <a name="link-a-report-to-a-model-as-a-clickthrough-report"></a><span data-ttu-id="352cd-102">Verknüpfen eines Berichts mit einem Modell als Bericht mit Durchklicken</span><span class="sxs-lookup"><span data-stu-id="352cd-102">Link a Report to a Model as a Clickthrough Report</span></span>
  <span data-ttu-id="352cd-103">Statt die Standardvorlagen für Berichte mit Durchklicken zu verwenden, können Sie einen Bericht im Berichts-Generator erstellen und dann mit einer bestimmten Entität im Berichtsmodell verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="352cd-103">Instead of using the default clickthrough report templates, you can create a Report Builder report and then link it to a specific entity in the report model.</span></span> <span data-ttu-id="352cd-104">Wenn ein Benutzer beim Anzeigen des Berichts auf die interaktiven Daten im Hauptbericht klickt, wird der Bericht als Bericht mit Durchklicken angezeigt.</span><span class="sxs-lookup"><span data-stu-id="352cd-104">When the person viewing the report clicks the interactive data in the main report, this report is displayed as a clickthrough report.</span></span> <span data-ttu-id="352cd-105">Um einen Bericht mit einer Entität zu verknüpfen, verwenden Sie den [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -Berichts-Manager.</span><span class="sxs-lookup"><span data-stu-id="352cd-105">To link a report to an entity, use [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Report Manager.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="352cd-106">Der Bericht muss mit der Entität verknüpft werden, die im Bericht als primäre oder Basisentität verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="352cd-106">The primary, or base, entity that is used in the report must to be the same entity to which the report is linked.</span></span>  
  
### <a name="to-start-report-manager-from-a-browser"></a><span data-ttu-id="352cd-107">So starten Sie den Berichts-Manager aus einem Browser</span><span class="sxs-lookup"><span data-stu-id="352cd-107">To start Report Manager from a browser</span></span>  
  
1.  <span data-ttu-id="352cd-108">Öffnen Sie [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Explorer 6.0 oder höher.</span><span class="sxs-lookup"><span data-stu-id="352cd-108">Open [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Explorer 6.0 or later.</span></span>  
  
2.  <span data-ttu-id="352cd-109">Geben Sie die URL des Berichts-Managers in die Adressleiste des Webbrowsers ein.</span><span class="sxs-lookup"><span data-stu-id="352cd-109">In the address bar of the Web browser, type the Report Manager URL.</span></span> <span data-ttu-id="352cd-110">Standardmäßig lautet die URL http:// \<*ComputerName*> /Reports.</span><span class="sxs-lookup"><span data-stu-id="352cd-110">By default, the URL is http://\<*ComputerName*>/reports.</span></span>  
  
### <a name="to-create-a-customized-clickthrough-report"></a><span data-ttu-id="352cd-111">So erstellen Sie einen benutzerdefinierten Bericht mit Durchklicken</span><span class="sxs-lookup"><span data-stu-id="352cd-111">To create a customized clickthrough report</span></span>  
  
1.  <span data-ttu-id="352cd-112">Navigieren Sie zum Berichtsmodell, dem Sie den benutzerdefinierten Bericht mit Durchklicken hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="352cd-112">Navigate to the report model to which you want to add the customized clickthrough report.</span></span>  
  
2.  <span data-ttu-id="352cd-113">Doppelklicken Sie auf das Berichtsmodell.</span><span class="sxs-lookup"><span data-stu-id="352cd-113">Double-click the report model.</span></span>  
  
3.  <span data-ttu-id="352cd-114">Klicken Sie auf **Durchklicken**.</span><span class="sxs-lookup"><span data-stu-id="352cd-114">Click **Clickthrough**.</span></span>  
  
4.  <span data-ttu-id="352cd-115">Wählen Sie die Entität aus, an die Sie den benutzerdefinierten Bericht mit Durchklicken anhängen möchten.</span><span class="sxs-lookup"><span data-stu-id="352cd-115">Select the entity to which you want to attach the customized clickthrough report.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="352cd-116">Diese Entität muss mit der Basisentität des benutzerdefinierten Berichts mit Durchklicken identisch sein.</span><span class="sxs-lookup"><span data-stu-id="352cd-116">This entity must be the same as the base entity of the customized clickthrough report.</span></span>  
  
5.  <span data-ttu-id="352cd-117">Um den benutzerdefinierten Bericht anzuzeigen, wenn auf eine Instanz der ausgewählten Entität geklickt wird, klicken Sie auf die Schaltfläche **Durchsuchen** des Berichts mit einer einzigen Instanz.</span><span class="sxs-lookup"><span data-stu-id="352cd-117">To display the customized report when a single instance of the selected entity is clicked, click the Single instance report **Browse** button.</span></span>  
  
     <span data-ttu-id="352cd-118">Oder</span><span class="sxs-lookup"><span data-stu-id="352cd-118">-or-</span></span>  
  
     <span data-ttu-id="352cd-119">Um den benutzerdefinierten Bericht anzuzeigen, wenn auf eine Multiinstanz der ausgewählten Entität geklickt wird, klicken Sie auf die Schaltfläche **Durchsuchen** des Multiinstanzberichts.</span><span class="sxs-lookup"><span data-stu-id="352cd-119">To display the customized report when a multiple instance of the selected entity is clicked, click the Multiple instance report **Browse** button.</span></span>  
  
6.  <span data-ttu-id="352cd-120">Wählen Sie den Bericht aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="352cd-120">Select the report and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="352cd-121">Klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="352cd-121">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="352cd-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="352cd-122">See Also</span></span>  
 [<span data-ttu-id="352cd-123">Berichte mit durch Klicken &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="352cd-123">Clickthrough Reports &#40;SSRS&#41;</span></span>](reports/clickthrough-reports-ssrs.md)  
  
  
