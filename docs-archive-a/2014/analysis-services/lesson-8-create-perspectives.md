---
title: 'Lektion 9: Erstellen von Perspektiven | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 55b0f0d0-1cdf-4876-9c3d-d0c848be3f5d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 417b6a4d3b16857f48bcc2f39dc8ec4c010a2b10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723234"
---
# <a name="lesson-9-create-perspectives"></a><span data-ttu-id="39c30-102">Lektion 9: Erstellen von Perspektiven</span><span class="sxs-lookup"><span data-stu-id="39c30-102">Lesson 9: Create Perspectives</span></span>
  <span data-ttu-id="39c30-103">In dieser Lektion erstellen Sie eine Perspektive mit dem Namen Internet Sales.</span><span class="sxs-lookup"><span data-stu-id="39c30-103">In this lesson, you will create an Internet Sales perspective.</span></span> <span data-ttu-id="39c30-104">Durch eine Perspektive ist ein anzeigbarer Teil eines Modells definiert, in dem konzentrierte, geschäfts- oder anwendungsspezifische Sichtweisen geboten werden.</span><span class="sxs-lookup"><span data-stu-id="39c30-104">A perspective defines a viewable subset of a model that provides focused, business-specific, or application-specific viewpoints.</span></span> <span data-ttu-id="39c30-105">Wenn ein Benutzer unter Verwendung einer Perspektive eine Verbindung mit einem Modell herstellt, werden ihm nur die als Felder in dieser Perspektive definierten Modellobjekte (Tabellen, Spalten, Measures, Hierarchien und KPIs) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="39c30-105">When a user connects to a model using a perspective, they see only those model objects (tables, columns, measures, hierarchies, and KPIs) as fields defined in that perspective.</span></span>  
  
 <span data-ttu-id="39c30-106">Die Internet Sales-Perspektive, die Sie in dieser Lektion erstellen, enthält nicht das Customer-Tabellenobjekt.</span><span class="sxs-lookup"><span data-stu-id="39c30-106">The Internet Sales perspective you create in this lesson will exclude the Customer table object.</span></span> <span data-ttu-id="39c30-107">Wenn Sie eine Perspektive erstellen, die bestimmte Objekte aus der Sicht ausschließt, ist dieses Objekt immer noch im Modell vorhanden. Es ist jedoch in keiner Feldliste eines Berichterstellungsdiensts sichtbar.</span><span class="sxs-lookup"><span data-stu-id="39c30-107">When you create a perspective that excludes certain objects from view, that object still exists in the model; however, it is not visible in a reporting client field list.</span></span> <span data-ttu-id="39c30-108">In berechneten Spalten und Measures können Berechnungen mit ausgeschlossenen Objektdaten ausgeführt werden, unabhängig davon, ob die Spalten und Measures in einer Perspektive enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="39c30-108">Calculated columns and measures either included in a perspective or not can still calculate from object data that is excluded.</span></span>  
  
 <span data-ttu-id="39c30-109">In dieser Lektion wird beschrieben, wie Sie Perspektiven erstellen und sich mit den Erstellungstools der Tabellenmodelle vertraut machen.</span><span class="sxs-lookup"><span data-stu-id="39c30-109">The purpose of this lesson is to describe how to create perspectives and become familiar with the tabular model authoring tools.</span></span> <span data-ttu-id="39c30-110">Wenn Sie später dieses Modell erweitern, um zusätzliche Tabellen einzufügen, können Sie weitere Perspektiven erstellen, um verschiedene Blickpunkte des Modells zu definieren, beispielsweise Inventar und Außendienst.</span><span class="sxs-lookup"><span data-stu-id="39c30-110">If you later expand this model to include additional tables, you can create additional perspectives to define different viewpoints of the model, for example, Inventory and Sales Force.</span></span>  
  
 <span data-ttu-id="39c30-111">Weitere Informationen finden Sie unter [Perspektiven &#40;SSAS – tabellarisch&#41;](tabular-models/perspectives-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="39c30-111">To learn more, see [Perspectives &#40;SSAS Tabular&#41;](tabular-models/perspectives-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="39c30-112">Geschätzte Zeit zum Bearbeiten dieser Lektion: **5 Minuten**</span><span class="sxs-lookup"><span data-stu-id="39c30-112">Estimated time to complete this lesson: **5 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="39c30-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="39c30-113">Prerequisites</span></span>  
 <span data-ttu-id="39c30-114">Dieses Thema ist Teil eines Tutorials zur Tabellenmodellierung, das in der richtigen Reihenfolge absolviert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="39c30-114">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="39c30-115">Sie sollten vor dem Ausführen der Tasks in dieser Lektion die vorherige Lektion abgeschlossen haben: [Lektion 8: Erstellen von Leistungskennzahlen](lesson-7-create-key-performance-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="39c30-115">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 8: Create Key Performance Indicators](lesson-7-create-key-performance-indicators.md).</span></span>  
  
## <a name="create-perspectives"></a><span data-ttu-id="39c30-116">Erstellen von Perspektiven</span><span class="sxs-lookup"><span data-stu-id="39c30-116">Create Perspectives</span></span>  
  
#### <a name="to-create-an-internet-sales-perspective"></a><span data-ttu-id="39c30-117">So erstellen Sie eine Internet Sales-Perspektive</span><span class="sxs-lookup"><span data-stu-id="39c30-117">To create an Internet Sales perspective</span></span>  
  
1.  <span data-ttu-id="39c30-118">Klicken Sie im Modell-Designer auf das Menü **Modell** und dann auf **Perspektiven**.</span><span class="sxs-lookup"><span data-stu-id="39c30-118">In the model designer, click the **Model** menu, and then click **Perspectives**.</span></span>  
  
2.  <span data-ttu-id="39c30-119">Klicken Sie im Dialogfeld **Perspektiven** auf **Neue Perspektive**.</span><span class="sxs-lookup"><span data-stu-id="39c30-119">In the **Perspectives** dialog box, click **New Perspective**.</span></span>  
  
3.  <span data-ttu-id="39c30-120">Um die Perspektive umzubenennen, doppelklicken Sie auf die Spaltenüberschrift **neue Perspektive 1** , und geben Sie dann ein `Internet Sales` .</span><span class="sxs-lookup"><span data-stu-id="39c30-120">To rename the perspective, double-click the **New Perspective 1** column heading, and then type `Internet Sales`.</span></span>  
  
4.  <span data-ttu-id="39c30-121">Wählen Sie unter **Felder**die folgenden Tabellen **Date**, **geography**, **Product**, **Product Category**, **Product Subcategory**und aus `Internet Sales` .</span><span class="sxs-lookup"><span data-stu-id="39c30-121">In **Fields**, select the following tables **Date**, **Geography**, **Product**, **Product Category**, **Product Subcategory**, and `Internet Sales`.</span></span>  
  
     <span data-ttu-id="39c30-122">Beachten Sie, dass Sie die Tabelle Customer und alle ihre Spalten aus dieser Perspektive ausgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="39c30-122">Notice you excluded the Customer table and all of its columns from this perspective.</span></span> <span data-ttu-id="39c30-123">In Lektion 12 testen Sie dann diese Perspektive mit der Funktion In Excel analysieren.</span><span class="sxs-lookup"><span data-stu-id="39c30-123">Later, in Lesson 12, you will use the Analyze in Excel feature to test this perspective.</span></span> <span data-ttu-id="39c30-124">Die PivotTable-Feldliste von Excel enthält jede Tabelle außer der Tabelle Customer.</span><span class="sxs-lookup"><span data-stu-id="39c30-124">The Excel PivotTable Field List will include each table except the Customer table.</span></span>  
  
5.  <span data-ttu-id="39c30-125">Überprüfen Sie Ihre Auswahl, stellen Sie sicher, dass die Tabelle **Customer** nicht markiert ist, und klicken Sie anschließend auf **OK**</span><span class="sxs-lookup"><span data-stu-id="39c30-125">Verify your selections, making sure the **Customer** table is not checked, and then click **OK**</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="39c30-126">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="39c30-126">Next Steps</span></span>  
 <span data-ttu-id="39c30-127">Wenn Sie mit diesem Tutorial fortfahren möchten, wechseln Sie zur nächsten Lektion: [Lektion 10: Erstellen von Hierarchien](lesson-9-create-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="39c30-127">To continue this tutorial, go to the next lesson: [Lesson 10: Create Hierarchies](lesson-9-create-hierarchies.md).</span></span>  
  
  
