---
title: 'Lektion 2: aufbauen einer Ziel-Mailing Struktur (Lernprogramm zu Data Mining-Grundlagen) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 9d0d6ceb-49b5-47c7-9ee6-464da43cc1f6
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 005baa09e802a9ffe98f87239070401f170ddfa9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608166"
---
# <a name="lesson-2-building-a-targeted-mailing-structure-basic-data-mining-tutorial"></a><span data-ttu-id="570e1-102">Lektion 2: Erstellen einer Targeted Mailing-Struktur (Lernprogramm zu Data Mining-Grundlagen)</span><span class="sxs-lookup"><span data-stu-id="570e1-102">Lesson 2: Building a Targeted Mailing Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="570e1-103">Die Marketingabteilung von [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] möchte den Umsatz steigern, indem bestimmte Kunden mit einer Mailing-Kampagne angesprochen werden.</span><span class="sxs-lookup"><span data-stu-id="570e1-103">The Marketing department of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] wants to increase sales by targeting specific customers for a mailing campaign.</span></span> <span data-ttu-id="570e1-104">Die Unternehmensdatenbank enthält eine Liste früherer Kunden sowie eine Liste potenzieller Neukunden.</span><span class="sxs-lookup"><span data-stu-id="570e1-104">The company's database contains a list of past customers and a list of potential new customers.</span></span> <span data-ttu-id="570e1-105">Durch die Prüfung der Merkmale früherer Kunden hofft das Unternehmen, Muster zu erkennen, die auf potenzielle Neukunden angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="570e1-105">By investigating the attributes of previous customers, the company hopes to discover patterns that they can then apply to potential customers.</span></span> <span data-ttu-id="570e1-106">Beispielsweise könnten Sie frühere Trends verwenden, um vorherzusagen, welche potenziellen Kunden am wahrscheinlichsten ein Fahrrad kaufen werden [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] , oder um Kundensegmente für künftige Marketingkampagnen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="570e1-106">For example, they might use past trends to predict which potential customers are most likely to purchase a bike from [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], or create customer segments for future marketing campaigns.</span></span>  
  
 <span data-ttu-id="570e1-107">In dieser Lektion verwenden Sie den **Data Mining-Assistenten** , um die Ziel-Mailing-Struktur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="570e1-107">In this lesson you will use the **Data Mining Wizard** to create the targeted mailing structure.</span></span> <span data-ttu-id="570e1-108">Nachdem Sie die Aufgaben in dieser Lektion ausgeführt haben, haben Sie eine Miningstruktur mit einem einzelnen Modell.</span><span class="sxs-lookup"><span data-stu-id="570e1-108">After you complete the tasks in this lesson, you will have a mining structure with a single model.</span></span> <span data-ttu-id="570e1-109">Da das Erstellen einer Struktur aus vielen Schritte und wichtigen Konzepten besteht, wurde dieser Prozess in die folgenden drei Aufgaben untergliedert:</span><span class="sxs-lookup"><span data-stu-id="570e1-109">Because there are many steps and important concepts involved in creating a structure, we have separated this process into the following three tasks:</span></span>  
  
 [<span data-ttu-id="570e1-110">Erstellen einer zielgerichteten Mailing-Mining Modellstruktur &#40;grundlegenden Data Mining-Lernprogramm&#41;</span><span class="sxs-lookup"><span data-stu-id="570e1-110">Creating a Targeted Mailing Mining Model Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-targeted-mailing-mining-model-structure-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="570e1-111">Angeben des Datentyps und des Inhaltstyps &#40;grundlegenden Data Mining-Lernprogramm&#41;</span><span class="sxs-lookup"><span data-stu-id="570e1-111">Specifying the Data Type and Content Type &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/specifying-the-data-type-and-content-type-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="570e1-112">Angeben eines Test Datasets für die Struktur &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="570e1-112">Specifying a Testing Data Set for the Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/specifying-a-testing-data-set-for-the-structure-basic-data-mining-tutorial.md)  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="570e1-113">Erste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="570e1-113">First Task in Lesson</span></span>  
 [<span data-ttu-id="570e1-114">Erstellen einer zielgerichteten Mailing-Mining Modellstruktur &#40;grundlegenden Data Mining-Lernprogramm&#41;</span><span class="sxs-lookup"><span data-stu-id="570e1-114">Creating a Targeted Mailing Mining Model Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-targeted-mailing-mining-model-structure-basic-data-mining-tutorial.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="570e1-115">Vorherige Lektion</span><span class="sxs-lookup"><span data-stu-id="570e1-115">Previous Lesson</span></span>  
 [<span data-ttu-id="570e1-116">Lektion 1: Vorbereiten der Analysis Services Datenbank &#40;Data Mining-Lernprogramm für grundlegende&#41;</span><span class="sxs-lookup"><span data-stu-id="570e1-116">Lesson 1: Preparing the Analysis Services Database &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-preparing-the-analysis-services-database-basic-data-mining-tutorial.md)  
  
## <a name="next--lesson"></a><span data-ttu-id="570e1-117">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="570e1-117">Next  Lesson</span></span>  
 [<span data-ttu-id="570e1-118">Lektion 3: Hinzufügen und Verarbeiten von Modellen</span><span class="sxs-lookup"><span data-stu-id="570e1-118">Lesson 3: Adding and Processing Models</span></span>](../../2014/tutorials/lesson-3-adding-and-processing-models.md)  
  
## <a name="see-also"></a><span data-ttu-id="570e1-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="570e1-119">See Also</span></span>  
 <span data-ttu-id="570e1-120">[Erstellen Sie die Data Mining-Struktur &#40;Data Mining-Assistenten&#41;](../../2014/analysis-services/create-the-data-mining-structure-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="570e1-120">[Create the Data Mining Structure &#40;Data Mining Wizard&#41;](../../2014/analysis-services/create-the-data-mining-structure-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="570e1-121">Erstellen einer relationalen Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="570e1-121">Create a Relational Mining Structure</span></span>](../../2014/analysis-services/data-mining/create-a-relational-mining-structure.md)  
  
  
