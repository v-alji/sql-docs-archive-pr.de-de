---
title: Hinzufügen eines BI-Semantik Modell-Verbindungs-Inhaltstyps zu einer Bibliothek (PowerPivot für SharePoint) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 145505ed-50bc-4528-912b-2a5cd2566011
author: minewiskan
ms.author: owend
ms.openlocfilehash: ecd40193b382aa692beeadd55ab8f9388c328620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621220"
---
# <a name="add-a-bi-semantic-model-connection-content-type-to-a-library-powerpivot-for-sharepoint"></a><span data-ttu-id="e7492-102">Hinzufügen eines BI-Semantikmodell-Verbindungs-Inhaltstyps zu einer Bibliothek (PowerPivot für SharePoint)</span><span class="sxs-lookup"><span data-stu-id="e7492-102">Add a BI Semantic Model Connection Content Type to a Library (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="e7492-103">Eine BI-Semantikmodellverbindung wird in SharePoint erstellt und stellt eine Umleitung zu den Business Intelligence-Semantikmodelldaten in einer PowerPivot-Arbeitsmappe oder einer Datenbank für ein tabellarisches Modell der Analysis Services auf einem Netzwerkserver bereit.</span><span class="sxs-lookup"><span data-stu-id="e7492-103">A BI semantic model connection is created in SharePoint and provides redirection to business intelligence semantic model data in a PowerPivot workbook or Analysis Services tabular model database on a network server.</span></span> <span data-ttu-id="e7492-104">Vor dem Erstellen einer BI-Semantikmodellverbindung in SharePoint müssen Sie eine Dokumentbibliothek erweitern, um das Erstellen einer BISM-Datei zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e7492-104">Before you can create a BI semantic model connection in SharePoint, you must extend a document library to allow the creation of a .bism file.</span></span> <span data-ttu-id="e7492-105">Dieser Schritt muss nur einmal für jede Bibliothek ausgeführt werden, jedoch für jede Bibliothek wiederholt werden, aus der BISM-Dateien erstellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e7492-105">This step only needs to be performed once for each library, but you will need to repeat it for any library from which you want to create .bism files.</span></span> <span data-ttu-id="e7492-106">Als bewährte Methode wird empfohlen, eine zentrale Bibliothek zum Speichern von BISM-Dateien zu erstellen, damit die Berechtigungen zentral verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="e7492-106">Best practices recommend that you create a centralized library for storing .bism files so that you can manage permissions in one place.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e7492-107">Wenn Sie bereits SharePoint-Datenverbindungsbibliotheken verwenden, wird der BI-Semantikmodell-Verbindungsinhaltstyp dieser Bibliotheksvorlage automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e7492-107">If you already use SharePoint Data Connection Libraries, the BI Semantic Model Connection content type is automatically added to that library template.</span></span> <span data-ttu-id="e7492-108">Sie können die Schritte in diesem Abschnitt überspringen, wenn Sie eine Datenverbindungsbibliothek verwenden, mit der Sie bereits neue BI-Semantikmodell-Verbindungsdokumente erstellen können.</span><span class="sxs-lookup"><span data-stu-id="e7492-108">You can skip the steps in this section if you use a data connection library that already lets you create new BI semantic model connection documents.</span></span>  
  
##  <a name="add-the-content-type-to-a-document-library"></a><a name="bkmk_addtype"></a> <span data-ttu-id="e7492-109">Hinzufügen des Inhaltstyps zu einer Dokumentbibliothek</span><span class="sxs-lookup"><span data-stu-id="e7492-109">Add the content type to a document library</span></span>  
 <span data-ttu-id="e7492-110">Sie müssen mindestens über die Listenverwaltungsberechtigung verfügen, um einen Inhaltstyp hinzuzufügen und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e7492-110">You must have at least the Manage Lists permission to add and configure a content type.</span></span> <span data-ttu-id="e7492-111">Diese Berechtigung ist in die Berechtigungsebene "Entwerfen" und höher integriert.</span><span class="sxs-lookup"><span data-stu-id="e7492-111">This permission is built into the Design permission level and above.</span></span>  
  
 <span data-ttu-id="e7492-112">Die Website, die die Dokumentbibliothek enthält, muss eine Funktionsaktivierung für PowerPivot für SharePoint aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e7492-112">The site that contains the document library must have feature activation for PowerPivot for SharePoint.</span></span> <span data-ttu-id="e7492-113">Weitere Informationen finden Sie unter [Aktivieren der Power Pivot-Funktions Integration für Website Sammlungen in der zentral Administration](activate-power-pivot-integration-for-site-collections-in-ca.md).</span><span class="sxs-lookup"><span data-stu-id="e7492-113">For more information, see [Activate PowerPivot Feature Integration for Site Collections in Central Administration](activate-power-pivot-integration-for-site-collections-in-ca.md).</span></span>  
  
1.  <span data-ttu-id="e7492-114">Öffnen Sie die Dokumentbibliothek, für die Sie den BI-Semantikmodell-Verbindungsinhaltstyp aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e7492-114">Open the document library for which you want to enable the BI Semantic Model Connection content type.</span></span>  
  
2.  <span data-ttu-id="e7492-115">Klicken Sie im SharePoint-Menüband in den Bibliothekstools auf **Bibliothek**.</span><span class="sxs-lookup"><span data-stu-id="e7492-115">On the SharePoint ribbon, in Library Tools, click **Library**.</span></span>  
  
3.  <span data-ttu-id="e7492-116">Klicken Sie auf **Bibliothekeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="e7492-116">Click **Library Settings**.</span></span>  
  
4.  <span data-ttu-id="e7492-117">Klicken Sie unter Allgemeine Einstellungen auf **Erweiterte Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="e7492-117">In General Settings, click **Advanced settings**.</span></span>  
  
5.  <span data-ttu-id="e7492-118">Klicken Sie unter Inhaltstypen im Abschnitt Verwaltung von Inhaltstypen zulassen?</span><span class="sxs-lookup"><span data-stu-id="e7492-118">In Content Types, in the "Allow management of content types?"</span></span> <span data-ttu-id="e7492-119">auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="e7492-119">section, click **Yes**.</span></span>  
  
6.  <span data-ttu-id="e7492-120">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7492-120">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="e7492-121">Klicken Sie im Abschnitt Inhaltstypen auf **Aus vorhandenen Websiteinhaltstypen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e7492-121">In the Content Types section, click **Add from existing site content types**.</span></span> <span data-ttu-id="e7492-122">Falls diese Seite nicht angezeigt wird, wechseln Sie zurück zur Website und klicken unter Bibliothekstools auf **Bibliothek** und dann auf **Bibliothekseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="e7492-122">If you do not see this page, go back to the site, click **Library** in Library Tools, and then click **Library Settings**.</span></span>  
  
8.  <span data-ttu-id="e7492-123">Klicken Sie unter Inhaltstypen auf **Aus vorhandenen Websiteinhaltstypen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e7492-123">In Content Types, click **Add from existing site content types**.</span></span>  
  
9. <span data-ttu-id="e7492-124">Wählen Sie unter Websiteinhaltstypen auswählen aus: die Option **Business Intelligence**aus.</span><span class="sxs-lookup"><span data-stu-id="e7492-124">In Select site content types from:, select **Business Intelligence**.</span></span>  
  
10. <span data-ttu-id="e7492-125">Klicken Sie in der Liste Verfügbare Websiteinhaltstypen auf BI-Semantikmodell-Verbindungsdatei, und klicken Sie dann auf **Hinzufügen**, um den ausgewählten Inhaltstyp in die Liste **Hinzuzufügende Inhaltstypen** zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="e7492-125">In Available Site Content Types, click **BI Semantic Model Connection File**, and then click **Add** to move the selected content type to the Content types to add list.</span></span>  
  
11. <span data-ttu-id="e7492-126">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7492-126">Click **OK**.</span></span>  
  
12. <span data-ttu-id="e7492-127">Um zu überprüfen, ob Sie den Inhaltstyp hinzugefügt haben, navigieren Sie zurück zur Bibliothek, und klicken Sie im Bereich zu den Dokumenten des Bibliotheksmenübands auf **Neues Dokument** .</span><span class="sxs-lookup"><span data-stu-id="e7492-127">To verify you added the content type, go back to the library and click **New Document** on the Documents area of the library ribbon.</span></span> <span data-ttu-id="e7492-128">Sie sollten **BI-Semantikmodell-Verbindungsdatei** in der Liste "Neue Dokumente" sehen.</span><span class="sxs-lookup"><span data-stu-id="e7492-128">You should see **BI Semantic Model Connection File** in the New Documents list.</span></span>  
  
     <span data-ttu-id="e7492-129">![Untermenü "Neues Dokument" in einer SharePoint-Bibliothek](../media/ssas-bismconnection-new.gif "Untermenü "Neues Dokument" in einer SharePoint-Bibliothek")</span><span class="sxs-lookup"><span data-stu-id="e7492-129">![New Document submenu in a SharePoint library](../media/ssas-bismconnection-new.gif "New Document submenu in a SharePoint library")</span></span>  
  
 <span data-ttu-id="e7492-130">Nachdem Sie den Inhaltstyp für die BI-Semantikmodellverbindung für eine Bibliothek aktiviert haben, können Sie eine Verbindung erstellen, die Umleitung für Geschäftssemantikmodelldaten bereitstellt, die von Excel- oder [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] -Berichten verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e7492-130">After you enable the BI semantic model connection content type for a library, you can create a connection that provides redirection to business semantic model data that can be used by Excel or [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] reports.</span></span> <span data-ttu-id="e7492-131">Wählen Sie die folgenden Links, um mehr über diesen nächsten Schritt zu erfahren:</span><span class="sxs-lookup"><span data-stu-id="e7492-131">Choose from the following links to learn more about this next step:</span></span>  
  
 [<span data-ttu-id="e7492-132">Herstellen einer BI-Semantikmodellverbindung mit einer PowerPivot-Arbeitsmappe</span><span class="sxs-lookup"><span data-stu-id="e7492-132">Create a BI Semantic Model Connection to a PowerPivot Workbook</span></span>](create-a-bi-semantic-model-connection-to-a-power-pivot-workbook.md)  
  
 [<span data-ttu-id="e7492-133">Erstellen einer BI-Semantikmodellverbindung mit einer tabellarischen Modelldatenbank</span><span class="sxs-lookup"><span data-stu-id="e7492-133">Create a BI Semantic Model Connection to a Tabular Model Database</span></span>](create-a-bi-semantic-model-connection-to-a-tabular-model-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="e7492-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e7492-134">See Also</span></span>  
 <span data-ttu-id="e7492-135">[Power Pivot BI-Semantik Modell Verbindung &#40;. bism-&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span><span class="sxs-lookup"><span data-stu-id="e7492-135">[PowerPivot BI Semantic Model Connection &#40;.bism&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span></span>  
 [<span data-ttu-id="e7492-136">Verwenden einer BI-Semantikmodellverbindung in Excel oder Reporting Services</span><span class="sxs-lookup"><span data-stu-id="e7492-136">Use a BI Semantic Model Connection in Excel or Reporting Services</span></span>](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md)  
  
  
