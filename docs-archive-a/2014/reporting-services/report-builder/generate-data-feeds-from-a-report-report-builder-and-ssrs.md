---
title: Generieren von Datenfeeds aus einem Bericht (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e68baae2-9f2a-4f13-9179-9ac7f29111c5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 340191396aaaa92fe14fe8c3c6b42539a713eb45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608362"
---
# <a name="generate-data-feeds-from-a-report-report-builder-and-ssrs"></a><span data-ttu-id="d127f-102">Generieren von Datenfeeds aus einem Bericht (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="d127f-102">Generate Data Feeds from a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d127f-103">Sie können Atom-kompatible Datenfeeds aus Berichten generieren und dann die Datenfeeds in Anwendungen wie dem-Client verwenden, [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] die Datenfeeds nutzen können.</span><span class="sxs-lookup"><span data-stu-id="d127f-103">You can generate Atom-compliant data feeds from reports, and then use the data feeds in applications, such as the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] client, that can consume data feeds.</span></span>  
  
 <span data-ttu-id="d127f-104">Die [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Atom-Renderingerweiterung generiert ein Atom-Dienstdokument, in dem die aus einem Bericht verfügbaren Datenfeeds aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="d127f-104">The [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Atom rendering extension generates an Atom service document that lists the data feeds available from a report.</span></span> <span data-ttu-id="d127f-105">Im Dokument ist mindestens ein Datenfeed für jeden Datenbereich im Bericht enthalten.</span><span class="sxs-lookup"><span data-stu-id="d127f-105">The document lists at least one data feed for each data region in the report.</span></span> <span data-ttu-id="d127f-106">Abhängig vom Typ des Datenbereichs und den darin angezeigten Daten könnte [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] mehrere Datenfeeds aus einem Datenbereich generieren.</span><span class="sxs-lookup"><span data-stu-id="d127f-106">Depending on the type of data region and the data that the data region displays, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] might generate multiple data feeds from a data region.</span></span>  
  
 <span data-ttu-id="d127f-107">Ein Atom-Dienstdokument enthält einen eindeutigen Bezeichner für jeden Datenfeed. Sie verwenden den Bezeichner in einer URL, um den Inhalt des Datenfeeds anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d127f-107">Atom service document contains a unique identifier for each the data feed and you use the identifier in a URL to view the content of the data feed.</span></span>  
  
 <span data-ttu-id="d127f-108">Weitere Informationen finden Sie unter [Generieren von Datenfeeds aus Berichten &#40;Berichts-Generator und SSRS&#41;](generating-data-feeds-from-reports-report-builder-and-ssrs.md)mit den Daten arbeiten.</span><span class="sxs-lookup"><span data-stu-id="d127f-108">For more information, see [Generating Data Feeds from Reports &#40;Report Builder and SSRS&#41;](generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-generate-an-atom-service-document"></a><span data-ttu-id="d127f-109">So generieren Sie ein Atom-Dienstdokument</span><span class="sxs-lookup"><span data-stu-id="d127f-109">To generate an Atom service document</span></span>  
  
1.  <span data-ttu-id="d127f-110">Navigieren Sie auf der Seite **Home** des Berichts-Managers zu dem Bericht, aus dem Sie Datenfeeds generieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d127f-110">From the Report Manager **Home** page, navigate to the report from which you want to generate data feeds.</span></span>  
  
2.  <span data-ttu-id="d127f-111">Klicken Sie auf den Bericht.</span><span class="sxs-lookup"><span data-stu-id="d127f-111">Click the report.</span></span>  
  
     <span data-ttu-id="d127f-112">Der Bericht wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d127f-112">The report is run.</span></span>  
  
3.  <span data-ttu-id="d127f-113">Klicken Sie auf der Symbolleiste auf das Symbol In Datenfeed exportieren.</span><span class="sxs-lookup"><span data-stu-id="d127f-113">On the toolbar, click the Export to Data Feed icon.</span></span>  
  
     <span data-ttu-id="d127f-114">Sie werden in einer Meldung gefragt, ob Sie das Atom-Dokument, das den Datenfeed enthält, speichern oder öffnen möchten.</span><span class="sxs-lookup"><span data-stu-id="d127f-114">A message appears asking you if you want to save or open the atom document that contains the data feed.</span></span>  
  
4.  <span data-ttu-id="d127f-115">Klicken Sie auf **Speichern** , um das Dokument im Dateisystem zu speichern, oder auf **Öffnen** , um den Dokumentinhalt vor dem Speichern anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d127f-115">Click **Save** to save the document to the file system, or click **Open** to view the document content before saving.</span></span> <span data-ttu-id="d127f-116">**Das Dokument wird standardmäßig in einem Browser geöffnet.**</span><span class="sxs-lookup"><span data-stu-id="d127f-116">**By default, the document opens in a browser.**</span></span>  
  
5.  <span data-ttu-id="d127f-117">Navigieren Sie zum Speicherort, an dem das Dokument gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d127f-117">Browse to the location to save the document.</span></span>  
  
6.  <span data-ttu-id="d127f-118">Ändern Sie optional den Namen des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="d127f-118">Optionally, change the name of the document.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d127f-119">Standardmäßig entspricht der Dokumentname dem Berichtsnamen.</span><span class="sxs-lookup"><span data-stu-id="d127f-119">By default, the document name is the report name.</span></span>  
  
7.  <span data-ttu-id="d127f-120">Stellen Sie sicher, dass der Dokumenttyp einer **ATOMSVC-Datei**entspricht, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d127f-120">Verify the document type is **ATOMSVC File**, and then click **Save**.</span></span>  
  
8.  <span data-ttu-id="d127f-121">Öffnen Sie die ATOMSVC-Datei optional in einem Browser bzw. einem Text- oder XML-Editor.</span><span class="sxs-lookup"><span data-stu-id="d127f-121">Optionally, open the .atomsvc file in a browser or text or XML editor.</span></span>  
  
### <a name="to-view-an-atom-compliant-data-feed"></a><span data-ttu-id="d127f-122">So zeigen Sie einen Atom-kompatiblen Datenfeed an</span><span class="sxs-lookup"><span data-stu-id="d127f-122">To view an Atom-compliant data feed</span></span>  
  
1.  <span data-ttu-id="d127f-123">Falls das Atom-Dienstdokument noch nicht geöffnet ist, suchen Sie es und öffnen das Dokument in einem Browser wie Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="d127f-123">If the Atom service document is not already open, locate it and open it in a browser such as Internet Explorer.</span></span>  
  
2.  <span data-ttu-id="d127f-124">Kopieren Sie die URL des Datenfeeds, den Sie anzeigen möchten, aus dem Atom-Dienstdokument in den Browser.</span><span class="sxs-lookup"><span data-stu-id="d127f-124">Copy the URL of the data feed that you want to view from the Atom service document to the browser.</span></span>  
  
     <span data-ttu-id="d127f-125">Die URL hat folgendes Format:</span><span class="sxs-lookup"><span data-stu-id="d127f-125">The format of the URL is the following:</span></span>  
  
 `http://<server name>/ReportServer?%2f<ReportName>rs%3aCommand=Render&rs%3aFormat=ATOM&rc%3aDataFeed=<Identifier>`  
  
1.  <span data-ttu-id="d127f-126">Drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="d127f-126">Press ENTER.</span></span>  
  
     <span data-ttu-id="d127f-127">Sie werden in einer Meldung gefragt, ob Sie das Atom-Dokument, das den Datenfeed enthält, speichern oder öffnen möchten.</span><span class="sxs-lookup"><span data-stu-id="d127f-127">A message appears asking you if you want to save or open the atom document that contains the data feed.</span></span>  
  
2.  <span data-ttu-id="d127f-128">Klicken Sie auf **Speichern** , um das Dokument im Dateisystem zu speichern, oder auf **Öffnen** , um den Datenfeed vor dem Speichern anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d127f-128">Click **Save** to save the document to the file system, or click **Open** to view the data feed before saving.</span></span>  
  
3.  <span data-ttu-id="d127f-129">Navigieren Sie zum Speicherort, an dem das Dokument gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d127f-129">Browse to the location to save the document.</span></span>  
  
4.  <span data-ttu-id="d127f-130">Ändern Sie optional den Namen des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="d127f-130">Optionally, change the name of the document.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d127f-131">Standardmäßig entspricht der Dokumentname dem Berichtsnamen.</span><span class="sxs-lookup"><span data-stu-id="d127f-131">By default the document name is the report name.</span></span> <span data-ttu-id="d127f-132">Wenn das Atom-Dienstdokument mehrere Feeds enthält, verwenden alle standardmäßig den gleichen Namen, und zwar den Berichtsnamen.</span><span class="sxs-lookup"><span data-stu-id="d127f-132">If the Atom service document has multiple feeds, by default all use the same name, the report name.</span></span> <span data-ttu-id="d127f-133">Um zwischen den Datenfeeds zu unterscheiden, benennen Sie diese mit aussagekräftigen Namen um.</span><span class="sxs-lookup"><span data-stu-id="d127f-133">To differentiate them, rename them to use meaningful names.</span></span>  
  
5.  <span data-ttu-id="d127f-134">Stellen Sie sicher, dass der Dokumenttyp einer **ATOM-Datei**entspricht, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d127f-134">Verify the document type is **ATOM File**, and then click **Save**.</span></span>  
  
6.  <span data-ttu-id="d127f-135">Öffnen Sie die ATOM-Datei optional in einem Browser bzw. Text-Editor oder XML-Editor.</span><span class="sxs-lookup"><span data-stu-id="d127f-135">Optionally, open the .atom file in a browser or text editor or XML editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d127f-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d127f-136">See Also</span></span>  
 [<span data-ttu-id="d127f-137">Exportieren von Berichten &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d127f-137">Exporting Reports &#40;Report Builder and SSRS&#41;</span></span>](export-reports-report-builder-and-ssrs.md)  
  
  
