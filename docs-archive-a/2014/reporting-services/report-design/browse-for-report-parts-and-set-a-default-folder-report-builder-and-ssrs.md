---
title: Suchen nach Berichtsteilen und Festlegen eines Standardordners (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5cf38068-65d1-4fe8-81f3-a404d8fbc663
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6605a23732799ec07b3dbe8481e88c91b18ebe5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609651"
---
# <a name="browse-for-report-parts-and-set-a-default-folder-report-builder-and-ssrs"></a><span data-ttu-id="52f1b-102">Suchen nach Berichtsteilen und Festlegen eines Standardordners (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="52f1b-102">Browse for Report Parts and Set a Default Folder (Report Builder and SSRS)</span></span>
  <span data-ttu-id="52f1b-103">Die einfachste Möglichkeit, einen Bericht zu erstellen, besteht darin, vorhandene Berichtsteile wie Tabellen und Diagramme dem Bericht mithilfe des Berichtsteilkatalogs hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="52f1b-103">The easiest way to create a report is to add existing report parts, such as tables and charts, to your report from the Report Part Gallery.</span></span> <span data-ttu-id="52f1b-104">Wenn Sie dem Bericht einen Berichtsteil hinzufügen, werden damit auch alle für die Verarbeitung erforderlichen Elemente hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="52f1b-104">When you add a report part to your report, you are also adding everything it must have to work.</span></span> <span data-ttu-id="52f1b-105">Beispielsweise ist jeder Berichtsteil von einem Dataset (d. h., einer Abfrage und einer Verbindung zu einer Datenquelle) abhängig.</span><span class="sxs-lookup"><span data-stu-id="52f1b-105">For example, any report part that displays data depends on a dataset, that is, a query and a connection to a data source.</span></span> <span data-ttu-id="52f1b-106">Nachdem Sie dem Bericht den Berichtsteil hinzugefügt haben, können Sie diesen nach Bedarf ändern.</span><span class="sxs-lookup"><span data-stu-id="52f1b-106">After you add the report part to your report, you can modify it as much as you need.</span></span>  
  
 <span data-ttu-id="52f1b-107">Sie können einen Standardordner für das Veröffentlichen von Berichtsteilen auf dem Berichtsserver oder auf einer in einen Berichtsserver integrierten SharePoint-Website festlegen.</span><span class="sxs-lookup"><span data-stu-id="52f1b-107">You can set a default folder to publish report parts to the report server or SharePoint site integrated with a report server.</span></span>  
  
 <span data-ttu-id="52f1b-108">Weitere Informationen finden Sie unter [Berichtsteile &#40;Berichts-Generator und SSRS&#41;](../report-parts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="52f1b-108">For more information, see [Report Parts &#40;Report Builder and SSRS&#41;](../report-parts-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-browse-for-report-parts"></a><span data-ttu-id="52f1b-109">So suchen Sie nach Berichtsteilen</span><span class="sxs-lookup"><span data-stu-id="52f1b-109">To browse for report parts</span></span>  
  
1.  <span data-ttu-id="52f1b-110">Klicken Sie im Menü **Einfügen** auf **Berichtsteile**.</span><span class="sxs-lookup"><span data-stu-id="52f1b-110">On the **Insert** menu, click **Report Parts**.</span></span>  
  
     <span data-ttu-id="52f1b-111">Wurde noch keine Verbindung hergestellt, klicken Sie auf **Stellen Sie eine Verbindung mit einem Berichtsserver her**, und geben Sie den Namen des Berichtsservers ein.</span><span class="sxs-lookup"><span data-stu-id="52f1b-111">If you are not already connected, click **Connect to a report server**, and enter the name.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="52f1b-112">Für die Suche nach Berichtsteilen muss eine Verbindung mit einem Berichtsserver bestehen.</span><span class="sxs-lookup"><span data-stu-id="52f1b-112">You must be connected to a report server to browse for report parts.</span></span>  
  
2.  <span data-ttu-id="52f1b-113">Sie können die Suche eingrenzen, indem Sie Details zum Berichtsteil angeben.</span><span class="sxs-lookup"><span data-stu-id="52f1b-113">You can narrow your search by specifying details about the report part.</span></span> <span data-ttu-id="52f1b-114">Geben Sie Namen und Beschreibung ganz oder teilweise in das Feld **Suchen** ein, oder klicken Sie auf **Kriterien hinzufügen** , und fügen Sie Werte für einige oder alle diese Felder hinzu:</span><span class="sxs-lookup"><span data-stu-id="52f1b-114">Type all or part of the name and description in the **Search** box, or click **Add Criteria** and add values for any or all of these fields:</span></span>  
  
    -   <span data-ttu-id="52f1b-115">Erstellt von</span><span class="sxs-lookup"><span data-stu-id="52f1b-115">Created by</span></span>  
  
    -   <span data-ttu-id="52f1b-116">Erstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="52f1b-116">Date created</span></span>  
  
    -   <span data-ttu-id="52f1b-117">Datum der letzten Änderung</span><span class="sxs-lookup"><span data-stu-id="52f1b-117">Date last modified</span></span>  
  
    -   <span data-ttu-id="52f1b-118">Zuletzt geändert von</span><span class="sxs-lookup"><span data-stu-id="52f1b-118">Last modified by</span></span>  
  
    -   <span data-ttu-id="52f1b-119">Serverordner</span><span class="sxs-lookup"><span data-stu-id="52f1b-119">Server folder</span></span>  
  
    -   <span data-ttu-id="52f1b-120">type</span><span class="sxs-lookup"><span data-stu-id="52f1b-120">Type</span></span>  
  
     <span data-ttu-id="52f1b-121">Klicken Sie zum Suchen nach einem Bild beispielsweise auf **Kriterien hinzufügen**und anschließend auf **Typ**.</span><span class="sxs-lookup"><span data-stu-id="52f1b-121">For example, to find an image, click **Add Criteria**, and then click **Type**.</span></span> <span data-ttu-id="52f1b-122">Aktivieren Sie im Dropdownfeld das Kontrollkästchen **Bild** , drücken Sie die EINGABETASTE, und klicken Sie anschließend auf die Suchlupe.</span><span class="sxs-lookup"><span data-stu-id="52f1b-122">In the dropdown box, select the **Image** check box, press ENTER, and then click the Search magnifying glass.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="52f1b-123">Suchen Sie für die Werte **Erstellt von** und **Zuletzt geändert von** nach dem Benutzernamen der Person, wie er auf dem Berichtsserver angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="52f1b-123">For the **Created by** and **Last modified by** values, search for the person's user name as it is represented on the report server.</span></span>  
  
### <a name="to-set-a-default-folder-for-report-parts"></a><span data-ttu-id="52f1b-124">So legen Sie einen Standardordner für Berichtsteile fest</span><span class="sxs-lookup"><span data-stu-id="52f1b-124">To set a default folder for report parts</span></span>  
  
1.  <span data-ttu-id="52f1b-125">Klicken Sie auf **Berichts-Generator**, und klicken Sie dann auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="52f1b-125">Click **Report Builder**, and then click **Options**.</span></span>  
  
2.  <span data-ttu-id="52f1b-126">Geben Sie im Dialogfeld **Optionen** auf der Registerkarte **Einstellungen** einen Ordnernamen in das Textfeld **Berichtselemente standardmäßig in diesem Ordner veröffentlichen** ein.</span><span class="sxs-lookup"><span data-stu-id="52f1b-126">In the **Options** dialog box, on the **Settings** tab, type a folder name in the **Publish report parts to this folder by default** textbox.</span></span>  
  
 <span data-ttu-id="52f1b-127">Der Berichts-Generator erstellt diesen Ordner, wenn er noch nicht vorhanden ist und Sie über die Berechtigung verfügen, Ordner auf dem Berichtsserver zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="52f1b-127">Report Builder will create this folder if you have permissions to create folders on the report server and the folder does not exist yet.</span></span>  
  
 <span data-ttu-id="52f1b-128">Sie müssen den Berichts-Generator nicht neu starten, damit diese Einstellung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="52f1b-128">You do not need to restart Report Builder for this setting to take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52f1b-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="52f1b-129">See Also</span></span>  
 <span data-ttu-id="52f1b-130">[Suchen nach Updates oder Deaktivieren von Updates &#40;Berichts-Generator und SSRS&#41;](../check-for-updates-or-turn-updates-off-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="52f1b-130">[Check for Updates or Turn Updates Off &#40;Report Builder and SSRS&#41;](../check-for-updates-or-turn-updates-off-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="52f1b-131">[Berichtsteile &#40;Berichts-Generator und SSRS&#41;](../report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="52f1b-131">[Report Parts &#40;Report Builder and SSRS&#41;](../report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="52f1b-132">[Berichtsteile und Datasets in Berichts-Generator](../report-data/report-parts-and-datasets-in-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="52f1b-132">[Report Parts and Datasets in Report Builder](../report-data/report-parts-and-datasets-in-report-builder.md) </span></span>  
 <span data-ttu-id="52f1b-133">[Problembehandlung bei Berichts teilen &#40;Berichts-Generator und SSRS&#41;](../troubleshoot-report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="52f1b-133">[Troubleshoot Report Parts &#40;Report Builder and SSRS&#41;](../troubleshoot-report-parts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="52f1b-134">Veröffentlichen und erneutes Veröffentlichen von Berichtsteilen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="52f1b-134">Publish and Republish Report Parts &#40;Report Builder and SSRS&#41;</span></span>](publish-and-republish-report-parts-report-builder-and-ssrs.md)  
  
  
