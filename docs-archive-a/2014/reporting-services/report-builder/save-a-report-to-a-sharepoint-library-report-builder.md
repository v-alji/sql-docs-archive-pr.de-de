---
title: Speichern eines Berichts in einer SharePoint-Bibliothek (Berichts-Generator) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4daa1eee-78b7-43d0-8b22-4a98e8fa66ba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 49878a0d7115a11e804382cb5139aa0ec7b3d254
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617775"
---
# <a name="save-a-report-to-a-sharepoint-library-report-builder"></a><span data-ttu-id="815a2-102">Speichern eines Berichts in einer SharePoint-Bibliothek (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="815a2-102">Save a Report to a SharePoint Library (Report Builder)</span></span>
  <span data-ttu-id="815a2-103">Wenn Sie einen Bericht auf einem für die SharePoint-Integration konfigurierten Berichtsserver speichern möchten, müssen Sie den SharePoint-Server suchen und eine Verbindung mit dem Berichtsserver herstellen.</span><span class="sxs-lookup"><span data-stu-id="815a2-103">To save a report to a report server configured for SharePoint integration, you must browse to the SharePoint server and establish a connection to the report server.</span></span> <span data-ttu-id="815a2-104">In der Berichtsdefinition müssen alle Referenzen auf Elemente, die im Zusammenhang mit dem Bericht stehen, Werte verwenden, die für einen SharePoint-Berichtsserver spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="815a2-104">In the report definition, all references to items related to the report must use values that are specific to a SharePoint report server.</span></span> <span data-ttu-id="815a2-105">Verwandte Elemente schließen Unterberichte, Drillthroughberichte und Ressourcen ein, wie webbasierte Bilder.</span><span class="sxs-lookup"><span data-stu-id="815a2-105">Related items include subreports, drillthrough reports, and resources such as Web-based images.</span></span> <span data-ttu-id="815a2-106">Weitere Informationen finden Sie unter [Angeben von Pfaden zu externen Elementen &#40;Berichts-Generator und SSRS&#41;](../report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="815a2-106">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](../report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="815a2-107">Sie müssen für die SharePoint-Website über die Berechtigung als **Mitglied** oder **Besitzer** verfügen, um die Eigenschaften für das Projekt festzulegen.</span><span class="sxs-lookup"><span data-stu-id="815a2-107">You must have **Member** or **Owner** permission on the SharePoint site to set the properties on the project.</span></span>  
  
### <a name="to-save-a-report-to-a-sharepoint-site"></a><span data-ttu-id="815a2-108">So speichern Sie eine Bericht auf einer SharePoint-Website</span><span class="sxs-lookup"><span data-stu-id="815a2-108">To save a report to a SharePoint site</span></span>  
  
1.  <span data-ttu-id="815a2-109">Klicken Sie über die Schaltfläche Berichts-Generator auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="815a2-109">From the Report Builder button, click **Save**.</span></span> <span data-ttu-id="815a2-110">Das **Save As** _\<Report Item>_ Dialogfeld Speichern unter wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="815a2-110">The **Save As**_\<Report Item>_ dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="815a2-111">Wenn Sie einen Bericht erneut speichern, wird er automatisch am vorherigen Speicherort erneut gespeichert.</span><span class="sxs-lookup"><span data-stu-id="815a2-111">If you are resaving a report, it is automatically resaved to its previous location.</span></span> <span data-ttu-id="815a2-112">Verwenden Sie die Option **Speichern unter** , um den Speicherort zu ändern.</span><span class="sxs-lookup"><span data-stu-id="815a2-112">Use the **Save As** option to change location.</span></span>  
  
2.  <span data-ttu-id="815a2-113">Klicken Sie optional auf **Letzte Sites und Server** , um eine Liste der zuletzt verwendeten Berichtsserver und SharePoint-Websites anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="815a2-113">Optionally, click **Recent Sites and Servers** to show a list of recently used report servers and SharePoint sites.</span></span>  
  
3.  <span data-ttu-id="815a2-114">Wechseln Sie zur SharePoint-Website, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="815a2-114">Browse to the SharePoint site, and then click **Save**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="815a2-115">Wenn Sie einen geänderten Bericht mehr als 10 Stunden lang nicht speichern, wird er vom Server getrennt, ohne gespeichert zu werden.</span><span class="sxs-lookup"><span data-stu-id="815a2-115">If you leave a changed report for more than 10 hours without saving it, it is disconnected from the server without being saved.</span></span> <span data-ttu-id="815a2-116">Klicken Sie in einem solchen Fall in der rechten unteren Statusleiste auf **Trennen**und anschließend auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="815a2-116">If that happens, in the lower-right status bar, click **Disconnect**, and then click **Connect**.</span></span> <span data-ttu-id="815a2-117">Der letzte Server befindet sich in der Liste der verfügbaren Server.</span><span class="sxs-lookup"><span data-stu-id="815a2-117">The most recent server will be in the list of available servers.</span></span> <span data-ttu-id="815a2-118">Wählen Sie ihn aus, damit der Bericht erneut eine Verbindung herstellt.</span><span class="sxs-lookup"><span data-stu-id="815a2-118">Select it and the report will reconnect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="815a2-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="815a2-119">See Also</span></span>  
 [<span data-ttu-id="815a2-120">Suchen, Anzeigen und Verwalten von Berichten (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="815a2-120">Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;</span></span>](finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
