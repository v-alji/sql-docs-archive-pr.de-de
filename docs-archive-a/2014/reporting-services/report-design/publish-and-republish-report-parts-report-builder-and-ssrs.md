---
title: Veröffentlichen und erneutes Veröffentlichen von Berichtsteilen (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 92dce484-f39b-403c-9caf-d8772bc3aca3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 95fd5e3f7519c6a0d4a6f08cb9bcbf2507d32aaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616382"
---
# <a name="publish-and-republish-report-parts-report-builder-and-ssrs"></a><span data-ttu-id="291dc-102">Veröffentlichen und erneutes Veröffentlichen von Berichtsteilen (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="291dc-102">Publish and Republish Report Parts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="291dc-103">Sie können einen Berichtsteil mit den Standardeinstellungen an einem Standardspeicherplatz veröffentlichen oder Metadaten eines Berichtsteils wie Name und Beschreibung bearbeiten und danach an einem anderen Ort auf dem Berichtsserver speichern.</span><span class="sxs-lookup"><span data-stu-id="291dc-103">You can publish a report part with default settings in a default location, or you can edit report part metadata such as name and description, and save it somewhere else on a report server.</span></span> <span data-ttu-id="291dc-104">Außerdem können Sie ihn auf einer SharePoint-Website speichern, die in einen Berichtsserver integriert ist, wenn Sie die erforderlichen Berechtigungen dafür haben.</span><span class="sxs-lookup"><span data-stu-id="291dc-104">You can also save it to a SharePoint site that is integrated with a report server if you have the correct permissions.</span></span>  
  
 <span data-ttu-id="291dc-105">Sie können nur den Berichtsteil oder den Berichtsteil mit dem davon abhängigen Dataset, das darin eingebettet wurde, veröffentlichen. Sie können jedoch auch das Dataset getrennt davon veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="291dc-105">You can publish just the report part, with the dataset that it depends on embedded in it, or you can publish the dataset separately.</span></span> <span data-ttu-id="291dc-106">Wenn Sie das Dataset separat veröffentlichen, wird es zu einem freigegebenen Dataset, und der Berichtsteil wird damit verknüpft.</span><span class="sxs-lookup"><span data-stu-id="291dc-106">If you publish the dataset separately, it becomes a shared dataset, and the report part links to it.</span></span> <span data-ttu-id="291dc-107">Weitere Informationen finden Sie unter [Berichtsteile und Datasets](../report-data/report-parts-and-datasets-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="291dc-107">For more information, see [Report Parts and Datasets in Report Builder](../report-data/report-parts-and-datasets-in-report-builder.md).</span></span>  
  
 <span data-ttu-id="291dc-108">Sie können einen vorhandenen Berichtsteil erneut veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="291dc-108">You can republish an existing report part.</span></span> <span data-ttu-id="291dc-109">Wenn Sie über die entsprechenden Berechtigungen verfügen, können Sie die ursprüngliche Instanz des Berichtsteils auf dem Server überschreiben, auch wenn Sie diese nicht erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="291dc-109">If you have permissions, you can save over the original instance of the report part on the server, even if you didn't create it.</span></span> <span data-ttu-id="291dc-110">Sie können ihn auch als neuen Berichtsteil veröffentlichen und am gleichen Speicherort oder einem anderen Speicherort speichern.</span><span class="sxs-lookup"><span data-stu-id="291dc-110">You can also publish it as a new report part and save it either in the same or a different location.</span></span>  
  
### <a name="to-publish-a-report-part"></a><span data-ttu-id="291dc-111">So veröffentlichen Sie einen Berichtsteil</span><span class="sxs-lookup"><span data-stu-id="291dc-111">To publish a report part</span></span>  
  
1.  <span data-ttu-id="291dc-112">Klicken Sie im Menü von Berichts-Generator auf **Berichtselemente veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="291dc-112">On the Report Builder menu, click **Publish Report Parts**.</span></span>  
  
     <span data-ttu-id="291dc-113">Wenn Sie keine Verbindung mit einem Berichtsserver hergestellt haben, werden Sie dazu aufgefordert, eine Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="291dc-113">If you are not connected to a report server, you will be prompted to connect.</span></span> <span data-ttu-id="291dc-114">Wenn Sie keine Verbindung mit einem Berichtsserver herstellen können, können Sie auch keine Berichtsteile veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="291dc-114">If you cannot connect to a report server, you cannot publish report parts.</span></span>  
  
2.  <span data-ttu-id="291dc-115">Um die Berichtsteile mit den Standardeinstellungen am Standardspeicherort zu speichern, klicken Sie auf **Alle Berichtselemente mit Standardeinstellungen verwenden**.</span><span class="sxs-lookup"><span data-stu-id="291dc-115">To save your report parts with default settings to the default location, click **Publish all report parts with default settings**.</span></span>  
  
     <span data-ttu-id="291dc-116">Klicken Sie andernfalls auf **Überprüfen und ändern Sie Berichtselemente vor der Veröffentlichung**.</span><span class="sxs-lookup"><span data-stu-id="291dc-116">Otherwise, click **Review and modify report parts before publishing**.</span></span>  
  
3.  <span data-ttu-id="291dc-117">Bearbeiten Sie den Namen und die Beschreibung des Berichtsteils. Doppelklicken Sie dazu auf den Namen, um ihn zu bearbeiten, und klicken Sie in das Feld **Beschreibung** , um eine Beschreibung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="291dc-117">Edit the report part name and description: Double-click the name to edit it and click in the **Description** field to add a description.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="291dc-118">Es empfiehlt sich, einen Namen und eine Beschreibung für den Berichtsteil zu erstellen, damit er bei einer Suche von anderen Personen leichter gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="291dc-118">It is a good idea to give the report part name and description, to help people identify it when searching.</span></span> <span data-ttu-id="291dc-119">Die maximale Länge des Namens eines Berichtsteils beträgt 260 Zeichen für den gesamten Pfad einschließlich der Namen der Ordner auf dem Server, gefolgt von dem tatsächlichen Namen des Berichtsteils.</span><span class="sxs-lookup"><span data-stu-id="291dc-119">The maximum length for the name of a report part is 260 characters for the entire path, including the names of the folders on the server, followed by the actual name of the report part.</span></span>  
  
4.  <span data-ttu-id="291dc-120">Wenn Sie den Berichtsteil nicht im Standardordner speichern möchten, klicken Sie auf die Schaltfläche **Durchsuchen** .</span><span class="sxs-lookup"><span data-stu-id="291dc-120">To save your report part to a folder other than the default, click the **Browse** button.</span></span>  
  
5.  <span data-ttu-id="291dc-121">Klicken Sie auf **Veröffentlichen**, nachdem Sie die Optionen für alle Berichtsteile im Bericht festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="291dc-121">When you have set the options for all the report parts in the report, click **Publish**.</span></span>  
  
     <span data-ttu-id="291dc-122">Nach dem Veröffentlichen der Berichtsteile wird im Dialogfeld angezeigt, welche Berichtsteile erfolgreich veröffentlicht wurden und welche nicht.</span><span class="sxs-lookup"><span data-stu-id="291dc-122">After you publish the report parts, the dialog box shows which were successfully published and which were not.</span></span> <span data-ttu-id="291dc-123">Details zu den Berichtsteilen, die nicht veröffentlicht werden konnten, können im Dialogfeld **Berichtsteile veröffentlichen** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="291dc-123">You can view details in the **Publish Report Parts** dialog box for the report parts that failed to publish.</span></span>  
  
6.  <span data-ttu-id="291dc-124">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="291dc-124">Click **Close**.</span></span>  
  
### <a name="to-republish-a-report-part"></a><span data-ttu-id="291dc-125">So veröffentlichen Sie einen Berichtsteil erneut</span><span class="sxs-lookup"><span data-stu-id="291dc-125">To republish a report part</span></span>  
  
1.  <span data-ttu-id="291dc-126">Gehen Sie wie im Folgenden beschrieben vor, um einen Berichtsteil erneut zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="291dc-126">Follow the previous procedure for publishing a report part.</span></span>  
  
2.  <span data-ttu-id="291dc-127">Wenn Sie im Dialogfeld **Berichtselemente veröffentlichen** auf **Als neue Kopie des Berichtselements veröffentlichen**klicken, überschreibt Berichts-Generator beim Speichern den vorhandenen Berichtsteil auf dem Server nicht, sondern erstellt stattdessen einen anderen Berichtsteil.</span><span class="sxs-lookup"><span data-stu-id="291dc-127">In the **Publish Report Parts** dialog box, if you click **Publish as a New Copy of the Report Part**, Report Builder will not save over the existing report part on the server, but will create another report part instead.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="291dc-128">Wenn Sie diesen als neuen Berichtsteil veröffentlichen, verfügt er über eine neue eindeutige ID.</span><span class="sxs-lookup"><span data-stu-id="291dc-128">If you publish it as a new report part, it will have a new unique ID.</span></span> <span data-ttu-id="291dc-129">Er wird nicht mehr aktualisiert, wenn sich der ursprüngliche Berichtsteil ändert.</span><span class="sxs-lookup"><span data-stu-id="291dc-129">It will no longer receive updates if the original report part changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="291dc-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="291dc-130">See Also</span></span>  
 <span data-ttu-id="291dc-131">[Berichts Teile &#40;Berichts-Generator und SSRS&#41;](../report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="291dc-131">[Report Parts &#40;Report Builder and SSRS&#41;](../report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="291dc-132">[Berichts Teile und Datasets in Berichts-Generator](../report-data/report-parts-and-datasets-in-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="291dc-132">[Report Parts and Datasets in Report Builder](../report-data/report-parts-and-datasets-in-report-builder.md) </span></span>  
 <span data-ttu-id="291dc-133">[Problembehandlung bei Berichts teilen &#40;Berichts-Generator und SSRS&#41;](../troubleshoot-report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="291dc-133">[Troubleshoot Report Parts &#40;Report Builder and SSRS&#41;](../troubleshoot-report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="291dc-134">[Suchen nach Updates oder Deaktivieren von Updates &#40;Berichts-Generator und SSRS&#41;](../check-for-updates-or-turn-updates-off-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="291dc-134">[Check for Updates or Turn Updates Off &#40;Report Builder and SSRS&#41;](../check-for-updates-or-turn-updates-off-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="291dc-135">Suchen nach Berichtsteilen und Festlegen eines Standardordners &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="291dc-135">Browse for Report Parts and Set a Default Folder &#40;Report Builder and SSRS&#41;</span></span>](browse-for-report-parts-and-set-a-default-folder-report-builder-and-ssrs.md)  
  
  
