---
title: Speichern von Berichten auf einem Berichtsserver (Berichts-Generator) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 48dfef01-ed8c-4f23-90c3-de67c90a97dd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d80e35c447593e89d422e72ea31ec6be34c3619f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723517"
---
# <a name="save-reports-to-a-report-server-report-builder"></a><span data-ttu-id="771fb-102">Speichern von Berichten auf einem Berichtsserver (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="771fb-102">Save Reports to a Report Server (Report Builder)</span></span>
  <span data-ttu-id="771fb-103">Im Berichts-Generator können Sie eine Berichtsdefinition auf einem Berichtsserver speichern (auch bekannt als Bericht veröffentlichen).</span><span class="sxs-lookup"><span data-stu-id="771fb-103">In Report Builder, you can save a report definition to a report server (also known as publishing a report).</span></span> <span data-ttu-id="771fb-104">Wenn der Bericht auf einem Berichtsserver gespeichert wird, können andere Benutzer den Bericht anzeigen.</span><span class="sxs-lookup"><span data-stu-id="771fb-104">When the report is saved to a report server, other users can view the report.</span></span> <span data-ttu-id="771fb-105">Bei jeder Ausführung des veröffentlichten Berichts rufen Sie die aktuellen Daten ab.</span><span class="sxs-lookup"><span data-stu-id="771fb-105">Each time you run the published report, you will retrieve the most current data.</span></span> <span data-ttu-id="771fb-106">Exportieren Sie den Bericht in ein anderes Dateiformat, und speichern Sie es, um eine statische Kopie eines gerenderten Berichts zu speichern, oder speichern Sie Versionen von gerenderten Berichten mit der Funktion zum Berichtsverlauf.</span><span class="sxs-lookup"><span data-stu-id="771fb-106">To save a static copy of a rendered report, export the report to a different file format and save it or use the report history feature to save versions of rendered reports.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="771fb-107">Der Speicherort der gespeicherten Berichtsdefinition wirkt sich nicht darauf aus, ob der Bericht auf dem Server oder lokal bei der Vorschau des Berichts verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="771fb-107">The location of the saved report definition does not affect whether the report is processed on the server or processed locally when you preview the report.</span></span>  
  
### <a name="to-save-a-report-to-a-report-server"></a><span data-ttu-id="771fb-108">So speichern Sie einen Bericht auf einem Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="771fb-108">To save a report to a report server</span></span>  
  
1.  <span data-ttu-id="771fb-109">Klicken Sie über die Schaltfläche Berichts-Generator auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="771fb-109">From the Report Builder button, click **Save**.</span></span> <span data-ttu-id="771fb-110">Das **Save As** _\<Report Item\>_ Dialogfeld Speichern unter wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="771fb-110">The **Save As**_\<Report Item\>_ dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="771fb-111">Wenn Sie einen Bericht erneut speichern, wird er automatisch am vorherigen Speicherort erneut gespeichert.</span><span class="sxs-lookup"><span data-stu-id="771fb-111">If you are resaving a report, it is automatically resaved to its previous location.</span></span> <span data-ttu-id="771fb-112">Verwenden Sie die Option Speichern unter, um den Speicherort zu ändern.</span><span class="sxs-lookup"><span data-stu-id="771fb-112">Use the Save As option to change location.</span></span>  
  
2.  <span data-ttu-id="771fb-113">Klicken Sie optional auf **Letzte Sites und Server** , um eine Liste der zuletzt verwendeten Berichtsserver und SharePoint-Websites anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="771fb-113">Optionally, click **Recent Sites and Servers** to show a list of recently used report servers and SharePoint sites.</span></span>  
  
3.  <span data-ttu-id="771fb-114">Navigieren Sie zum Speicherort auf dem Berichtsserver, an dem Sie den Bericht speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="771fb-114">Browse to the report server location where you want to save the report.</span></span>  
  
4.  <span data-ttu-id="771fb-115">Geben Sie unter **Name**den Namen des Berichts ein.</span><span class="sxs-lookup"><span data-stu-id="771fb-115">In **Name**, type the name of the report.</span></span>  
  
5.  <span data-ttu-id="771fb-116">Wählen Sie unter **Elemente des Typs**den Typ des Berichtselements aus, das Sie speichern.</span><span class="sxs-lookup"><span data-stu-id="771fb-116">In **Items of type**, select the type of report item you are saving.</span></span> <span data-ttu-id="771fb-117">Der Typ für Berichte ist Berichte (\* .rdl).</span><span class="sxs-lookup"><span data-stu-id="771fb-117">The type for reports is Reports(\*.rdl).</span></span>  
  
### <a name="to-save-a-report-as-a-different-name"></a><span data-ttu-id="771fb-118">So speichern Sie einen Bericht unter einem anderen Namen</span><span class="sxs-lookup"><span data-stu-id="771fb-118">To save a report as a different name</span></span>  
  
1.  <span data-ttu-id="771fb-119">Klicken Sie auf die Schaltfläche Berichts-Generator und anschließend auf **Speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="771fb-119">From the Report Builder button, click **Save As**.</span></span> <span data-ttu-id="771fb-120">Das **Save As** _\<Report Item\>_ Dialogfeld Speichern unter wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="771fb-120">The **Save As**_\<Report Item\>_ dialog box opens.</span></span>  
  
2.  <span data-ttu-id="771fb-121">Wechseln Sie zu dem Speicherort auf dem Berichtsserver oder zu der Dateifreigabe, in der Sie den Bericht speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="771fb-121">Browse to the report server location or to the file share where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="771fb-122">Geben Sie unter **Name**den Namen des Berichts ein.</span><span class="sxs-lookup"><span data-stu-id="771fb-122">In **Name**, type the name of the report.</span></span>  
  
4.  <span data-ttu-id="771fb-123">Wählen Sie unter **Elemente des Typs**den Typ des Berichtselements aus, das Sie speichern.</span><span class="sxs-lookup"><span data-stu-id="771fb-123">In **Items of type**, select the type of report item you are saving.</span></span> <span data-ttu-id="771fb-124">Der Typ für Berichte ist Berichte (\* .rdl).</span><span class="sxs-lookup"><span data-stu-id="771fb-124">The type for reports is Reports(\*.rdl).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="771fb-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="771fb-125">See Also</span></span>  
 <span data-ttu-id="771fb-126">[Suchen, anzeigen und Verwalten von Berichten &#40;Berichts-Generator und SSRS &#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="771fb-126">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="771fb-127">[Exportieren von Berichten &#40;Berichts-Generator und SSRS&#41;](export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="771fb-127">[Exporting Reports &#40;Report Builder and SSRS&#41;](export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="771fb-128">[Die Berichte &#40;Berichts-Generator werden gespeichert&#41;](saving-reports-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="771fb-128">[Saving Reports &#40;Report Builder&#41;](saving-reports-report-builder.md) </span></span>  
 [<span data-ttu-id="771fb-129">Exportieren eines Berichts in ein anderes Dateiformat (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="771fb-129">Export a Report as Another File Type &#40;Report Builder and SSRS&#41;</span></span>](../export-a-report-as-another-file-type-report-builder-and-ssrs.md)  
  
  
