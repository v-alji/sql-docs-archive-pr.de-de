---
title: Binden eines Berichts oder Modells an eine freigegebene Datenquelle (SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- shared data sources [Reporting Services]
- data sources [Reporting Services], shared
ms.assetid: 23cc15f2-2883-48e2-bc6c-fa0ab61a2e21
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 596caba042d476173b3c49d1ad18e79d0827fe89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697561"
---
# <a name="bind-a-report-or-model-to-a-shared-data-source-ssrs"></a><span data-ttu-id="80bfe-102">Binden eines Berichts oder Modells an eine freigegebene Datenquelle (SSRS)</span><span class="sxs-lookup"><span data-stu-id="80bfe-102">Bind a Report or Model to a Shared Data Source (SSRS)</span></span>
  <span data-ttu-id="80bfe-103">In einigen Situationen, z. B., wenn Sie einen Bericht oder ein Modell von einem Testserver auf einen Produktionsserver verschieben, möchten Sie die Datei vielleicht auf dem lokalen Computer speichern und anschließend auf einen anderen Berichtsserver hochladen.</span><span class="sxs-lookup"><span data-stu-id="80bfe-103">In some situations, such as when you move a report or model from a test server to a production server, you might want to save the file to your local computer and then upload it to a different report server.</span></span> <span data-ttu-id="80bfe-104">Wenn Sie den Bericht oder das Modell auf den neuen Server hochladen, müssen Sie ihn oder es erneut an eine freigegebene, auf dem neuen Berichtsserver gespeicherte Datenquelle binden.</span><span class="sxs-lookup"><span data-stu-id="80bfe-104">When you upload the report or model to the new server, you need to rebind it to a shared data source that is stored on the new report server.</span></span> <span data-ttu-id="80bfe-105">Wenn Sie den Bericht oder das Modell nicht erneut binden, können sie bei einem Zugriff vom neuen Berichtsserver nicht ordnungsgemäß verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="80bfe-105">If you don't rebind the report or model, it will not work correctly when accessed from the new report server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="80bfe-106">Vor dem erneuten Binden eines Berichts oder Modells an eine freigegebene Datenquelle müssen die Daten bereits auf dem Berichtsserver oder in der SharePoint-Bibliothek vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="80bfe-106">Before rebinding a report or model to a shared data source, the data source must already exist on the report server or SharePoint library.</span></span> <span data-ttu-id="80bfe-107">Weitere Informationen zu Datenquellen finden Sie unter [Erstellen, Ändern und Löschen von freigegebenen Datenquellen (SSRS)](create-modify-and-delete-shared-data-sources-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="80bfe-107">For more information about data sources, see [Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span></span>  
  
### <a name="to-bind-a-report-or-model-to-a-shared-data-source-on-a-report-server-running-in-native-mode"></a><span data-ttu-id="80bfe-108">So binden Sie einen Bericht oder ein Modell an eine freigegebene Datenquelle auf einem Berichtsserver im einheitlichen Modus</span><span class="sxs-lookup"><span data-stu-id="80bfe-108">To bind a report or model to a shared data source on a report server running in native mode</span></span>  
  
1.  <span data-ttu-id="80bfe-109">Klicken Sie in **Berichts-Manager**auf den Namen des Berichts oder Modells, den oder das Sie auf den Server hochladen möchten.</span><span class="sxs-lookup"><span data-stu-id="80bfe-109">In **Report Manager**, click the name of the report or model that you uploaded to the server.</span></span>  
  
     <span data-ttu-id="80bfe-110">Die Registerkarte Eigenschaften wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="80bfe-110">The Properties tab opens.</span></span>  
  
2.  <span data-ttu-id="80bfe-111">Klicken Sie auf **Datenquellen**.</span><span class="sxs-lookup"><span data-stu-id="80bfe-111">Click **Data Sources**.</span></span>  
  
3.  <span data-ttu-id="80bfe-112">Klicken Sie auf **Durchsuchen**, und navigieren Sie dann zu der Datenquelle, an die Sie den Bericht oder das Modell binden möchten.</span><span class="sxs-lookup"><span data-stu-id="80bfe-112">Click **Browse**, and then navigate to the data source to which you want to bind the report or model.</span></span>  
  
4.  <span data-ttu-id="80bfe-113">Wählen Sie die Datenquelle aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="80bfe-113">Select the data source and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="80bfe-114">Klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="80bfe-114">Click **Apply**.</span></span>  
  
     <span data-ttu-id="80bfe-115">Der Bericht oder das Modell ist nun an die ausgewählte Datenquelle gebunden.</span><span class="sxs-lookup"><span data-stu-id="80bfe-115">The report or model is now bound to the data source that you selected.</span></span>  
  
### <a name="to-bind-a-report-or-model-to-a-shared-data-source-on-a-report-server-running-in-sharepoint-integrated-mode"></a><span data-ttu-id="80bfe-116">So binden Sie einen Bericht oder ein Modell an eine freigegebene Datenquelle auf einem Berichtsserver im integrierten SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="80bfe-116">To bind a report or model to a shared data source on a report server running in SharePoint integrated mode</span></span>  
  
1.  <span data-ttu-id="80bfe-117">Klicken Sie auf der Schnellstartleiste auf den Namen der Bibliothek, wenn sie nicht bereits geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="80bfe-117">If the library is not already open, click its name on the Quick Launch bar.</span></span> <span data-ttu-id="80bfe-118">Wenn der Name der Bibliothek nicht angezeigt wird, klicken Sie auf **Alle Websiteinhalte einblenden**und anschließend auf den Namen der Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="80bfe-118">If the name of your library does not appear, click **View All Site Content**, and then click the name of your library.</span></span>  
  
2.  <span data-ttu-id="80bfe-119">Zeigen Sie auf den Bericht oder das Modell, und klicken Sie auf den Pfeil nach unten.</span><span class="sxs-lookup"><span data-stu-id="80bfe-119">Point to the report or model and click the down arrow.</span></span>  
  
3.  <span data-ttu-id="80bfe-120">Klicken Sie auf **Datenquellen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="80bfe-120">Click **Manage Data Sources**.</span></span>  
  
4.  <span data-ttu-id="80bfe-121">Klicken Sie auf **dataSource1**.</span><span class="sxs-lookup"><span data-stu-id="80bfe-121">Click **dataSource1**.</span></span>  
  
5.  <span data-ttu-id="80bfe-122">Überprüfen Sie im Bereich **Verbindungstyp** , ob **Freigegebene Datenquelle** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="80bfe-122">In the **Connection Type** area, verify that **Shared data source** is selected.</span></span>  
  
6.  <span data-ttu-id="80bfe-123">Klicken Sie im Bereich **Datenquellenlink** auf die Schaltfläche mit den Auslassungspunkten (...).</span><span class="sxs-lookup"><span data-stu-id="80bfe-123">In the **Data Source Link** area, click the ellipsis (...) button.</span></span>  
  
7.  <span data-ttu-id="80bfe-124">Suchen Sie die Datenquelle, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="80bfe-124">Locate the data source you want to use.</span></span>  
  
8.  <span data-ttu-id="80bfe-125">Wählen Sie die Datenquelle aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="80bfe-125">Select the data source and **click OK**.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
10. <span data-ttu-id="80bfe-126">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="80bfe-126">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80bfe-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="80bfe-127">See Also</span></span>  
 <span data-ttu-id="80bfe-128">[Hochladen einer Datei oder eines Berichts &#40;Berichts-Manager&#41;](../reports/upload-a-file-or-report-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="80bfe-128">[Upload a File or Report &#40;Report Manager&#41;](../reports/upload-a-file-or-report-report-manager.md) </span></span>  
 <span data-ttu-id="80bfe-129">[Hochladen von Dokumenten in eine SharePoint-Bibliothek &#40;Reporting Services im SharePoint-Modus&#41;](../upload-documents-to-a-sharepoint-library-reporting-services-in-sharepoint-mode.md) </span><span class="sxs-lookup"><span data-stu-id="80bfe-129">[Upload Documents to a SharePoint Library &#40;Reporting Services in SharePoint Mode&#41;](../upload-documents-to-a-sharepoint-library-reporting-services-in-sharepoint-mode.md) </span></span>  
 <span data-ttu-id="80bfe-130">[Erstellen und Verwalten von freigegebenen Datenquellen &#40;Reporting Services im integrierten SharePoint-Modus&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md) </span><span class="sxs-lookup"><span data-stu-id="80bfe-130">[Create and Manage Shared Data Sources &#40;Reporting Services in SharePoint Integrated Mode&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md) </span></span>  
 <span data-ttu-id="80bfe-131">[Erstellen, löschen oder Ändern einer freigegebenen Datenquelle &#40;Berichts-Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="80bfe-131">[Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span></span>  
 <span data-ttu-id="80bfe-132">[Datenverbindungen, Datenquellen und Verbindungs Zeichenfolgen in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="80bfe-132">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="80bfe-133">Von Reporting Services unterstützte Datenquellen &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="80bfe-133">Data Sources Supported by Reporting Services &#40;SSRS&#41;</span></span>](../create-deploy-and-manage-mobile-and-paginated-reports.md)  
  
  
