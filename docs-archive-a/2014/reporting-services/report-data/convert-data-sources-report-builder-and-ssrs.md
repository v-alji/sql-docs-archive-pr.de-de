---
title: Konvertieren einer Datenquelle aus Embedded in Shared (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- data sources [Reporting Services], embedded
- data sources [Reporting Services], shared
ms.assetid: 0e099c7e-8c03-43eb-9ea3-76e52d9ebbe3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5827bab564b58e7a2b7922f01a33f550a6f523f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609661"
---
# <a name="convert-a-data-source-from-embedded-to-shared-report-builder-and-ssrs"></a><span data-ttu-id="ac7c1-102">Konvertieren einer eingebetteten Datenquelle in eine freigegebene Datenquelle (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="ac7c1-102">Convert a Data Source from Embedded to Shared (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ac7c1-103">Jede Datenquelle im Berichtsdatenbereich ist eingebettet und bezieht sich speziell auf den Bericht, oder sie ist freigegeben.</span><span class="sxs-lookup"><span data-stu-id="ac7c1-103">Each data source in the Report Data pane is embedded and specific to the report or is shared.</span></span> <span data-ttu-id="ac7c1-104">In Berichts-Generator verweist eine freigegebene Datenquelle auf eine veröffentlichte freigegebene Datenquelle auf einem Berichtsserver oder einer SharePoint-Website.</span><span class="sxs-lookup"><span data-stu-id="ac7c1-104">In Report Builder, a shared data source points to a published shared data source on a report server or SharePoint site.</span></span> <span data-ttu-id="ac7c1-105">In Berichts-Designer verweist eine freigegebene Datenquellenreferenz auf eine freigegebene Datenquelle im Ordner **Freigegebene Datenquellen** in Projektmappen-Explorer.</span><span class="sxs-lookup"><span data-stu-id="ac7c1-105">In Report Designer, a shared data source points to a shared data source in the **Shared Data Sources** folder in Solution Explorer.</span></span>  
  
 <span data-ttu-id="ac7c1-106">Weitere Informationen zu den Unterschieden zwischen eingebetteten und freigegebenen Datenquellen finden Sie unter [Eingebettete und freigegebene Datenverbindungen oder Datenquellen (Berichts-Generator und SSRS)](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ac7c1-106">For more information about the differences between embedded and shared data sources, see [Embedded and Shared Data Connections or Data Sources &#40;Report Builder and SSRS&#41;](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="ac7c1-107">Weitere Informationen zum Erstellen einer freigegebenen Datenquelle finden Sie unter [Erstellen einer eingebetteten oder freigegebenen Datenquelle (SSRS)](../create-an-embedded-or-shared-data-source-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ac7c1-107">For more information on how to create a shared data source, see [Create an Embedded or Shared Data Source &#40;SSRS&#41;](../create-an-embedded-or-shared-data-source-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="report-designer"></a><span data-ttu-id="ac7c1-108">Berichts-Designer</span><span class="sxs-lookup"><span data-stu-id="ac7c1-108">Report Designer</span></span>  
  
#### <a name="to-convert-a-data-source-from-embedded-to-shared"></a><span data-ttu-id="ac7c1-109">So konvertieren Sie eine Datenquelle von "eingebettet" in "freigegeben"</span><span class="sxs-lookup"><span data-stu-id="ac7c1-109">To convert a data source from embedded to shared</span></span>  
  
-   <span data-ttu-id="ac7c1-110">Klicken Sie im Berichtsdatenbereich mit der rechten Maustaste auf die Datenquelle, und klicken Sie anschließend auf **In freigegebene Datenquelle konvertieren**.</span><span class="sxs-lookup"><span data-stu-id="ac7c1-110">In the Report Data pane, right-click the data source, and then click **Convert to Shared Data Source**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ac7c1-111">Zum Anzeigen des Berichtsdatenbereichs klicken Sie im Menü **Ansicht** auf **Berichtsdaten**.</span><span class="sxs-lookup"><span data-stu-id="ac7c1-111">If the Report Data pane is not visible, on the **View** menu, click **Report Data**.</span></span> <span data-ttu-id="ac7c1-112">Wenn der Bereich als unverankertes Fenster geöffnet wird, können Sie es andocken.</span><span class="sxs-lookup"><span data-stu-id="ac7c1-112">If the pane opens as a floating window, you can dock it.</span></span> <span data-ttu-id="ac7c1-113">Weitere Informationen finden Sie unter [Andocken des Berichtsdatenbereichs im Berichts-Designer &#40;SSRS&#41;](../tools/dock-the-report-data-pane-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ac7c1-113">For more information, see [Dock the Report Data Pane in Report Designer &#40;SSRS&#41;](../tools/dock-the-report-data-pane-in-report-designer-ssrs.md).</span></span>  
  
     <span data-ttu-id="ac7c1-114">Im Berichtsdatenbereich ändert sich das Datenquellensymbol in das Symbol für freigegebene Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="ac7c1-114">In the Report Data pane, the data source icon changes to the shared data source icon.</span></span> <span data-ttu-id="ac7c1-115">Im Projektmappen-Explorer wird eine freigegebene Datenquelle mit demselben Namen im Ordner **Freigegebene Datenquelle** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac7c1-115">In Solution Explorer, a shared data source with the same name appears under the **Shared Data Source** folder.</span></span>  
  
### <a name="to-convert-a-data-source-from-shared-to-embedded"></a><span data-ttu-id="ac7c1-116">So konvertieren Sie eine Datenquelle von "freigegeben" in "eingebettet"</span><span class="sxs-lookup"><span data-stu-id="ac7c1-116">To convert a data source from shared to embedded</span></span>  
  
-   <span data-ttu-id="ac7c1-117">Klicken Sie im Berichtsdatenbereich mit der rechten Maustaste auf die Datenquelle, öffnen Sie das Dialogfeld **Datenquelleneigenschaften** , und klicken Sie anschließend auf **Eingebettete Verbindung**.</span><span class="sxs-lookup"><span data-stu-id="ac7c1-117">In the Report Data pane, right-click the data source, open the **Data Source Properties** dialog box, and then click **Embedded Connection**.</span></span> <span data-ttu-id="ac7c1-118">Geben Sie die erforderlichen Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="ac7c1-118">Enter the required information.</span></span>  
  
     <span data-ttu-id="ac7c1-119">Im Berichtsdatenbereich ändert sich das Datenquellensymbol in das Symbol für freigegebene Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="ac7c1-119">In the Report Data pane, the data source icon changes to the shared data source icon.</span></span>  
  
## <a name="report-builder"></a><span data-ttu-id="ac7c1-120">Berichts-Generator</span><span class="sxs-lookup"><span data-stu-id="ac7c1-120">Report Builder</span></span>  
  
#### <a name="to-convert-a-data-source-from-embedded-to-shared"></a><span data-ttu-id="ac7c1-121">So konvertieren Sie eine Datenquelle von "eingebettet" in "freigegeben"</span><span class="sxs-lookup"><span data-stu-id="ac7c1-121">To convert a data source from embedded to shared</span></span>  
  
-   <span data-ttu-id="ac7c1-122">Klicken Sie im Berichtsdatenbereich mit der rechten Maustaste auf die Datenquelle, öffnen Sie das Dialogfeld **Datenquelleneigenschaften** , und klicken Sie anschließend auf **Eingebettete Verbindung**.</span><span class="sxs-lookup"><span data-stu-id="ac7c1-122">In the Report Data pane, right-click the data source to open the **Data Source Properties** dialog box, and then click **Embedded Connection**.</span></span> <span data-ttu-id="ac7c1-123">Geben Sie die erforderlichen Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="ac7c1-123">Enter the required information.</span></span>  
  
     <span data-ttu-id="ac7c1-124">Im Berichtsdatenbereich ändert sich das Datenquellensymbol in das Symbol für freigegebene Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="ac7c1-124">In the Report Data pane, the data source icon changes to the shared data source icon.</span></span>  
  
#### <a name="to-convert-a-data-source-from-shared-to-embedded"></a><span data-ttu-id="ac7c1-125">So konvertieren Sie eine Datenquelle von "freigegeben" in "eingebettet"</span><span class="sxs-lookup"><span data-stu-id="ac7c1-125">To convert a data source from shared to embedded</span></span>  
  
-   <span data-ttu-id="ac7c1-126">Klicken Sie im Berichtsdatenbereich mit der rechten Maustaste auf die Datenquelle, öffnen Sie das Dialogfeld **Datenquelleneigenschaften** , und klicken Sie anschließend auf **Eingebettete Verbindung**.</span><span class="sxs-lookup"><span data-stu-id="ac7c1-126">In the Report Data pane, right-click the data source, open the **Data Source Properties** dialog box, and then click **Embedded Connection**.</span></span> <span data-ttu-id="ac7c1-127">Geben Sie die erforderlichen Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="ac7c1-127">Enter the required information.</span></span>  
  
     <span data-ttu-id="ac7c1-128">Im Berichtsdatenbereich ändert sich das Datenquellensymbol in das Symbol für freigegebene Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="ac7c1-128">In the Report Data pane, the data source icon changes to the shared data source icon.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac7c1-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ac7c1-129">See Also</span></span>  
 <span data-ttu-id="ac7c1-130">[Verwalten von Berichtsdatenquellen](manage-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="ac7c1-130">[Manage Report Data Sources](manage-report-data-sources.md) </span></span>  
 [<span data-ttu-id="ac7c1-131">Datenverbindungen, Datenquellen und Verbindungszeichenfolgen in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="ac7c1-131">Data Connections, Data Sources, and Connection Strings in Reporting Services</span></span>](../data-connections-data-sources-and-connection-strings-in-reporting-services.md)  
  
  
