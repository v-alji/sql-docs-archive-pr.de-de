---
title: Konfigurieren allgemeiner Eigenschaften für einen Bericht (Berichts-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], properties
- properties [Reporting Services], general
ms.assetid: 10b941b2-28e6-4408-9ee4-acebc63c8496
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f30900158591afcd5997053dbb61cc22b495ed10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723598"
---
# <a name="configure-general-properties-for-a-report-report-manager"></a><span data-ttu-id="965e2-102">Konfigurieren allgemeiner Berichtseigenschaften (Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="965e2-102">Configure General Properties for a Report (Report Manager)</span></span>
  
### <a name="to-configure-general-report-properties"></a><span data-ttu-id="965e2-103">So konfigurieren Sie allgemeine Berichteigenschaften</span><span class="sxs-lookup"><span data-stu-id="965e2-103">To configure general report properties</span></span>

1.  <span data-ttu-id="965e2-104">Starten Sie den [Berichts-Manager &#40;einheitlicher SSRS-Modus&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="965e2-104">Start [Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span></span>

2.  <span data-ttu-id="965e2-105">Navigieren Sie in Berichts-Manager zur Seite **Inhalt** .</span><span class="sxs-lookup"><span data-stu-id="965e2-105">In Report Manager, navigate to the **Contents** page.</span></span> <span data-ttu-id="965e2-106">Navigieren Sie zu dem Bericht, für den Sie allgemeine Eigenschaften konfigurieren möchten, und öffnen Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="965e2-106">Navigate to the report that you want to configure general properties for and open it.</span></span>

3.  <span data-ttu-id="965e2-107">Klicken Sie auf die Registerkarte **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="965e2-107">Click the **Properties** tab.</span></span>

     <span data-ttu-id="965e2-108">Wenn die Seite **Inhalt** in der Detailansicht angezeigt wird, klicken Sie auf das Symbol für die Eigenschaften Seite:</span><span class="sxs-lookup"><span data-stu-id="965e2-108">Or, if the **Contents** page is in Details view, click the property page icon:</span></span>

     <span data-ttu-id="965e2-109">![Eigenschaftenseite (Symbol)](media/prop.gif "Eigenschaftenseite (Symbol)")</span><span class="sxs-lookup"><span data-stu-id="965e2-109">![Property page icon](media/prop.gif "Property page icon")</span></span>

4.  <span data-ttu-id="965e2-110">Die Seite **Allgemeine** Eigenschaften wird angezeigt, und Sie können Eigenschaften wie folgt konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="965e2-110">The **General** properties page is displayed, and you can configure properties as follows:</span></span>

    -   <span data-ttu-id="965e2-111">Im Abschnitt " **Eigenschaften** " können Sie den Namen und die Beschreibung des Berichts ändern.</span><span class="sxs-lookup"><span data-stu-id="965e2-111">In the **Properties** section, you can modify the report name and description.</span></span>

    -   <span data-ttu-id="965e2-112">Aktivieren Sie das Kontrollkästchen **in Listenansicht ausblenden** , um das Element auszublenden, wenn die Seite im Standardseiten Layout (Listenansicht) geöffnet wird, in der die Elemente auf der Seite und auf der Seite angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="965e2-112">You can select the **Hide in list view** checkbox to hide the item when the page is opened in the default page layout (list view) which arranges items across and down the page.</span></span>

    -   <span data-ttu-id="965e2-113">Klicken Sie im Abschnitt **Berichtsdefinition** auf **Bearbeiten** , um eine Kopie der Berichtsdefinition zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="965e2-113">In the **Report Definition** section, click **Edit** to extract a copy of the report definition.</span></span> <span data-ttu-id="965e2-114">Änderungen, die Sie lokal an der Berichtsdefinition vornehmen, werden nicht auf dem Berichtsserver gespeichert.</span><span class="sxs-lookup"><span data-stu-id="965e2-114">Modifications that you make locally to the report definition are not saved on the report server.</span></span>

         <span data-ttu-id="965e2-115">Oder klicken Sie auf **Aktualisieren**, um die Berichtsdefinition aus einer RDL-Datei zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="965e2-115">Or, to update the report definition from an .rdl file, click **Update**.</span></span>

        > [!NOTE]
        >  <span data-ttu-id="965e2-116">Wenn Sie eine Berichtsdefinition aktualisieren, müssen Sie die Einstellungen zur Datenquelle nach Abschluss des Updates zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="965e2-116">If you update a report definition, you must reset the data source settings after the update is completed.</span></span>

    -   <span data-ttu-id="965e2-117">Verwenden Sie die Schaltflächen **Löschen** oder **verschieben** , um den Bericht zu löschen oder zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="965e2-117">Use the **Delete** or **Move** buttons to delete or move the report.</span></span>

    -   <span data-ttu-id="965e2-118">Außerdem können Sie einen verknüpften Bericht erstellen.</span><span class="sxs-lookup"><span data-stu-id="965e2-118">You can also create a linked report.</span></span>

5.  <span data-ttu-id="965e2-119">Wenn Sie die Konfiguration der allgemeinen Eigenschaften für den Bericht abgeschlossen haben **, klicken Sie**auf übernehmen.</span><span class="sxs-lookup"><span data-stu-id="965e2-119">When you have finished configuring general properties for the report, click **Apply**.</span></span>

## <a name="see-also"></a><span data-ttu-id="965e2-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="965e2-120">See Also</span></span>
 <span data-ttu-id="965e2-121">[Verschieben oder löschen Sie ein Element &#40;Berichts-Manager&#41;](report-server/move-or-delete-an-item-report-manager.md) [Inhaltsseite &#40;Berichts-Manager](../../2014/reporting-services/contents-page-report-manager.md)&#41;&#40;suchen [, anzeigen und Verwalten von Berichten Berichts-Generator &#41;und SSRS &#40;](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) [Allgemeine Eigenschaften Seite, Berichte Berichts-Manager](../../2014/reporting-services/general-properties-page-reports-report-manager.md)&#41;</span><span class="sxs-lookup"><span data-stu-id="965e2-121">[Move or Delete an Item &#40;Report Manager&#41;](report-server/move-or-delete-an-item-report-manager.md) [Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) [Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) [General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md)</span></span>


