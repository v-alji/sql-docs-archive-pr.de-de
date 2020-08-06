---
title: 'Schritt 5: Hinzufügen und Konfigurieren der Flatfilequelle | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5c95ce51-e0fe-4fc5-95eb-2945929f2b13
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 504cfb4bc722627eb8ee70ec1f2c562cef8f1f0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618128"
---
# <a name="step-5-adding-and-configuring-the-flat-file-source"></a><span data-ttu-id="2700c-102">Schritt 5: Hinzufügen und Konfigurieren der Flatfilequelle</span><span class="sxs-lookup"><span data-stu-id="2700c-102">Step 5: Adding and Configuring the Flat File Source</span></span>
  <span data-ttu-id="2700c-103">In dieser Aufgabe fügen Sie Ihrem Paket eine Flatfilequelle hinzu und konfigurieren sie.</span><span class="sxs-lookup"><span data-stu-id="2700c-103">In this task, you will add and configure a Flat File source to your package.</span></span> <span data-ttu-id="2700c-104">Eine Flatfilequelle ist eine Datenflusskomponente, die Metadaten verwendet, die durch einen Flatfile-Verbindungs-Manager definiert werden, um das Format und die Struktur der Daten anzugeben, die aus der Flatfile durch einen Transformationsprozess extrahiert werden.</span><span class="sxs-lookup"><span data-stu-id="2700c-104">A Flat File source is a data flow component that uses metadata defined by a Flat File connection manager to specify the format and structure of the data to be extracted from the flat file by a transform process.</span></span> <span data-ttu-id="2700c-105">Die Flatfilequelle kann zum Extrahieren von Daten aus einer einzigen Flatfile konfiguriert werden, indem die Dateiformatdefinition verwendet wird, die durch den Flatfile-Verbindungs-Manager zur Verfügung gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2700c-105">The Flat File source can be configured to extract data from a single flat file by using the file format definition provided by the Flat File connection manager.</span></span>  
  
 <span data-ttu-id="2700c-106">In diesem Tutorial konfigurieren Sie die Flatfilequelle `Sample Flat File Source Data` so, dass Sie den zuvor erstellten Verbindungs-Manager verwendet.</span><span class="sxs-lookup"><span data-stu-id="2700c-106">For this tutorial, you will configure the Flat File source to use the `Sample Flat File Source Data` connection manager that you previously created.</span></span>  
  
### <a name="to-add-a-flat-file-source-component"></a><span data-ttu-id="2700c-107">So fügen Sie eine Flatfilequellen-Komponente hinzu</span><span class="sxs-lookup"><span data-stu-id="2700c-107">To add a Flat File Source component</span></span>  
  
1.  <span data-ttu-id="2700c-108">Öffnen Sie den **Datenfluss** -Designer, indem Sie entweder auf den `Extract Sample Currency Data` Datenfluss Task doppelklicken oder auf die **Registerkarte Datenfluss**klicken.</span><span class="sxs-lookup"><span data-stu-id="2700c-108">Open the **Data Flow** designer, either by double-clicking the `Extract Sample Currency Data` data flow task or by clicking the **Data Flow tab**.</span></span>  
  
2.  <span data-ttu-id="2700c-109">Erweitern Sie in der **SSIS-Toolbox**die Option **Weitere Quellen**, und ziehen Sie anschließend **Flatfilequelle** auf die Entwurfsoberfläche der Registerkarte **Datenfluss** .</span><span class="sxs-lookup"><span data-stu-id="2700c-109">In the **SSIS Toolbox**, expand **OtherSources**, and then drag a **Flat File Source** onto the design surface of the **Data Flow** tab.</span></span>  
  
3.  <span data-ttu-id="2700c-110">Klicken Sie auf der Entwurfs Oberfläche **Datenfluss** mit der rechten Maustaste auf die neu hinzugefügte **Flatfilequelle**, klicken Sie auf **Umbenennen**, und ändern Sie den Namen in `Extract Sample Currency Data` .</span><span class="sxs-lookup"><span data-stu-id="2700c-110">On the **Data Flow** design surface, right-click the newly added **Flat File Source**, click **Rename**, and change the name to `Extract Sample Currency Data`.</span></span>  
  
4.  <span data-ttu-id="2700c-111">Doppelklicken Sie auf die Flatfilequelle, um das Dialogfeld Quellen-Editor für Flatfiles zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2700c-111">Double-click the Flat File source to open the Flat File Source Editor dialog box.</span></span>  
  
5.  <span data-ttu-id="2700c-112">Wählen Sie im Feld **Verbindungs-Manager für Flatfiles** die Option aus `Sample Flat File Source Data` .</span><span class="sxs-lookup"><span data-stu-id="2700c-112">In the **Flat file connection manager** box, select `Sample Flat File Source Data`.</span></span>  
  
6.  <span data-ttu-id="2700c-113">Klicken Sie auf **Spalten** , und überprüfen Sie, ob die Namen der Spalten ordnungsgemäß sind.</span><span class="sxs-lookup"><span data-stu-id="2700c-113">Click **Columns** and verify that the names of the columns are correct.</span></span>  
  
7.  <span data-ttu-id="2700c-114">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2700c-114">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="2700c-115">Klicken Sie mit der rechten Maustaste auf die Flatfilequelle, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="2700c-115">Right-click the Flat File source and click **Properties**.</span></span>  
  
9. <span data-ttu-id="2700c-116">Überprüfen Sie im Eigenschaftenfenster, ob die- `LocaleID` Eigenschaft auf **Englisch (USA)** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2700c-116">In the Properties window, verify that the `LocaleID` property is set to **English (United States)**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="2700c-117">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="2700c-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="2700c-118">Schritt 6: Hinzufügen und Konfigurieren der Transformationen zum Suchen</span><span class="sxs-lookup"><span data-stu-id="2700c-118">Step 6: Adding and Configuring the Lookup Transformations</span></span>](lesson-1-6-adding-and-configuring-the-lookup-transformations.md)  
  
## <a name="see-also"></a><span data-ttu-id="2700c-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2700c-119">See Also</span></span>  
 <span data-ttu-id="2700c-120">[Flatfilequelle](data-flow/flat-file-source.md) </span><span class="sxs-lookup"><span data-stu-id="2700c-120">[Flat File Source](data-flow/flat-file-source.md) </span></span>  
 [<span data-ttu-id="2700c-121">Verbindungs-Manager-Editor für Flatfiles &#40;Seite „Allgemein“&#41;</span><span class="sxs-lookup"><span data-stu-id="2700c-121">Flat File Connection Manager Editor &#40;General Page&#41;</span></span>](general-page-of-integration-services-designers-options.md)  
  
  
