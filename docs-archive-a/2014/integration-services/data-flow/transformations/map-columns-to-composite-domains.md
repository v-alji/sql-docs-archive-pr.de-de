---
title: Zuordnen von Spalten zu Verbunddomänen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: d9422412-8a3d-45ae-af7f-072c902a09ba
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6a665b2096579c9da35a1b69be46c4ba6103610f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621093"
---
# <a name="map-columns-to-composite-domains"></a><span data-ttu-id="f2bee-102">Zuordnen von Spalten zu Verbunddomänen</span><span class="sxs-lookup"><span data-stu-id="f2bee-102">Map Columns to Composite Domains</span></span>
  <span data-ttu-id="f2bee-103">Eine Verbunddomäne besteht aus mindestens zwei einzelnen Domänen.</span><span class="sxs-lookup"><span data-stu-id="f2bee-103">A composite domain consists of two or more single domains.</span></span> <span data-ttu-id="f2bee-104">Sie können der Domäne mehrere Spalten oder eine einzelne Spalte mit durch Trennzeichen getrennten Werten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="f2bee-104">You can map multiple columns to the domain, or you can map a single column with delimited values to the domain.</span></span>  
  
 <span data-ttu-id="f2bee-105">Bei Verwendung mehrerer Spalten müssen Sie jeder einzelnen Domäne in der Verbunddomäne eine Spalte zuordnen, um die Verbunddomänenregeln auf die Datenbereinigung anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="f2bee-105">When you have multiple columns, you must map a column to each single domain in the composite domain to apply the composite domain rules to data cleansing.</span></span> <span data-ttu-id="f2bee-106">Sie wählen die einzelnen, in der Verbunddomäne enthaltenen Domänen im Data Quality-Client aus.</span><span class="sxs-lookup"><span data-stu-id="f2bee-106">You select the single domains contained in the composite domain, in the Data Quality Client.</span></span> <span data-ttu-id="f2bee-107">Weitere Informationen finden Sie unter [Erstellen einer Verbunddomäne](../../../data-quality-services/create-a-composite-domain.md).</span><span class="sxs-lookup"><span data-stu-id="f2bee-107">For more information, see [Create a Composite Domain](../../../data-quality-services/create-a-composite-domain.md).</span></span>  
  
 <span data-ttu-id="f2bee-108">Bei Verwendung einer einzelnen Spalte mit durch Trennzeichen getrennten Werten müssen Sie die einzelne Spalte der Verbunddomäne zuordnen.</span><span class="sxs-lookup"><span data-stu-id="f2bee-108">When you have a single column with delimited values, you must map the single column to the composite domain.</span></span> <span data-ttu-id="f2bee-109">Die Werte müssen dieselbe Reihenfolge wie die einzelnen Domänen in der Verbunddomäne aufweisen.</span><span class="sxs-lookup"><span data-stu-id="f2bee-109">The values must appear in the same order as the single domains appear in the composite domain.</span></span> <span data-ttu-id="f2bee-110">Das Trennzeichen in der Datenquelle muss mit dem zum Analysieren der Verbunddomänenwerte verwendeten Trennzeichen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f2bee-110">The delimiter in the data source must match the delimiter that is used to parse the composite domain values.</span></span> <span data-ttu-id="f2bee-111">Zum Auswählen des Trennzeichens für die Verbunddomäne sowie zum Festlegen anderer Eigenschaften verwenden Sie den Data Quality-Client.</span><span class="sxs-lookup"><span data-stu-id="f2bee-111">You select the delimiter for the composite domain, as well as set other properties, in the Data Quality Client.</span></span> <span data-ttu-id="f2bee-112">Weitere Informationen finden Sie unter [Erstellen einer Verbunddomäne](../../../data-quality-services/create-a-composite-domain.md).</span><span class="sxs-lookup"><span data-stu-id="f2bee-112">For more information, see [Create a Composite Domain](../../../data-quality-services/create-a-composite-domain.md).</span></span>  
  
### <a name="to-map-multiple-columns-to-a-composite-domain"></a><span data-ttu-id="f2bee-113">So ordnen Sie einer Verbunddomäne mehrere Spalten zu</span><span class="sxs-lookup"><span data-stu-id="f2bee-113">To map multiple columns to a composite domain</span></span>  
  
1.  <span data-ttu-id="f2bee-114">Klicken Sie mit der rechten Maustaste auf die Transformation für die DQS-Bereinigung, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="f2bee-114">Right-click the DQS Cleansing transformation, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="f2bee-115">Vergewissern Sie sich auf der Registerkarte **Verbindungs-Manager** , dass die Verbunddomäne in der Liste verfügbarer Domänen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f2bee-115">On the **Connection Manager** tab, confirm that the composite domain appears in the list of available domains.</span></span>  
  
3.  <span data-ttu-id="f2bee-116">Wählen Sie auf der Registerkarte **Zuordnung** die Spalten im Bereich **Verfügbare Eingabespalten** aus.</span><span class="sxs-lookup"><span data-stu-id="f2bee-116">On the **Mapping** tab, select the columns in the **Available Input Columns** area.</span></span>  
  
4.  <span data-ttu-id="f2bee-117">Wählen Sie für jede im Feld **Eingabespalte** aufgelistete Spalte eine einzelne Domäne im Feld **Domäne** aus.</span><span class="sxs-lookup"><span data-stu-id="f2bee-117">For each column listed in the **Input Column** field, select a single domain in the **Domain** field.</span></span> <span data-ttu-id="f2bee-118">Wählen Sie nur einzelne Domänen aus, die in der Verbunddomäne enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="f2bee-118">Select only single domains that are in the composite domain.</span></span>  
  
5.  <span data-ttu-id="f2bee-119">Ändern Sie ggf. die Namen in den Feldern **Alias - Quelle**, **Alias - Ausgabe**und **Alias - Status** .</span><span class="sxs-lookup"><span data-stu-id="f2bee-119">As needed, modify the names that appear in the **Source Alias**, **Output Alias**, and **Status Alias** fields.</span></span>  
  
6.  <span data-ttu-id="f2bee-120">Legen Sie nach Bedarf Eigenschaften auf der Registerkarte **Erweitert** fest. Weitere Informationen zu den Eigenschaften finden Sie unter [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="f2bee-120">As needed, set properties on the **Advanced** tab. For more information about the properties, see [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span></span>  
  
### <a name="to-map-a-column-with-delimited-values-to-a-composite-domain"></a><span data-ttu-id="f2bee-121">So ordnen Sie einer Verbunddomäne eine Spalte mit durch Trennzeichen getrennten Werten zu</span><span class="sxs-lookup"><span data-stu-id="f2bee-121">To map a column with delimited values to a composite domain</span></span>  
  
1.  <span data-ttu-id="f2bee-122">Klicken Sie mit der rechten Maustaste auf die Transformation für die DQS-Bereinigung, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="f2bee-122">Right-click the DQS Cleansing transformation, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="f2bee-123">Vergewissern Sie sich auf der Registerkarte **Verbindungs-Manager** , dass die Verbunddomäne in der Liste verfügbarer Domänen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f2bee-123">On the **Connection Manager** tab, confirm that the composite domain appears in the list of available domains.</span></span>  
  
3.  <span data-ttu-id="f2bee-124">Wählen Sie auf der Registerkarte **Zuordnung** die Spalte im Bereich **Verfügbare Eingabespalten** aus.</span><span class="sxs-lookup"><span data-stu-id="f2bee-124">On the **Mapping** tab, select the column in the **Available Input Columns** area.</span></span>  
  
4.  <span data-ttu-id="f2bee-125">Wählen Sie für die im Feld **Eingabespalte** aufgelistete Spalte die Verbunddomäne im Feld **Domäne** aus.</span><span class="sxs-lookup"><span data-stu-id="f2bee-125">For the column listed in the **Input Column** field, select the composite domain in the **Domain** field.</span></span>  
  
5.  <span data-ttu-id="f2bee-126">Ändern Sie ggf. die Namen in den Feldern **Alias - Quelle**, **Alias - Ausgabe**und **Alias - Status** .</span><span class="sxs-lookup"><span data-stu-id="f2bee-126">As needed, modify the names that appear in the **Source Alias**, **Output Alias**, and **Status Alias** fields.</span></span>  
  
6.  <span data-ttu-id="f2bee-127">Legen Sie nach Bedarf Eigenschaften auf der Registerkarte **Erweitert** fest. Weitere Informationen zu den Eigenschaften finden Sie unter [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="f2bee-127">As needed, set properties on the **Advanced** tab. For more information about the properties, see [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2bee-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f2bee-128">See Also</span></span>  
 [<span data-ttu-id="f2bee-129">DQS-Bereinigungstransformation</span><span class="sxs-lookup"><span data-stu-id="f2bee-129">DQS Cleansing Transformation</span></span>](dqs-cleansing-transformation.md)  
  
  
