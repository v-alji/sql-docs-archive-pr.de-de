---
title: Erstellen und Verwalten von KPIs (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.kpi.f1
ms.assetid: c96026c2-4394-4c3c-986b-4c95a4421900
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8e9d7ef77939efe407ed6ab0d725a6d788c58b49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616210"
---
# <a name="create-and-manage-kpis-ssas-tabular"></a><span data-ttu-id="06e16-102">Erstellen und Verwalten von KPIs (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="06e16-102">Create and Manage KPIs (SSAS Tabular)</span></span>
  <span data-ttu-id="06e16-103">In diesem Thema wird beschrieben, wie ein KPI (Key Performance Indicator) in einem tabellarischen Modell erstellt, bearbeitet oder gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="06e16-103">This topic describes how to create, edit, or delete a KPI (Key Performance Indicator) in a tabular model.</span></span> <span data-ttu-id="06e16-104">Um einen KPI zu erstellen, wählen Sie ein Measure aus, das den Basiswert des KPIs ergibt.</span><span class="sxs-lookup"><span data-stu-id="06e16-104">To create a KPI, you select a measure that evaluates to the KPI's Base value.</span></span> <span data-ttu-id="06e16-105">Anschließend wählen Sie im Dialogfeld Key Performance Indicator ein zweites Measure oder einen absoluten Wert aus, das bzw. der einen Zielwert ergibt.</span><span class="sxs-lookup"><span data-stu-id="06e16-105">You then use the Key Performance Indicator dialog box to select a second measure or an absolute value that evaluates to a target value.</span></span> <span data-ttu-id="06e16-106">Sie können dann Statusschwellenwerte definieren, mit denen die Leistung zwischen dem Basis- und dem Zielmeasure gemessen wird.</span><span class="sxs-lookup"><span data-stu-id="06e16-106">You can then define status thresholds that measure the performance between the Base and Target measures.</span></span>  
  
 <span data-ttu-id="06e16-107">Dieses Thema umfasst folgende Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="06e16-107">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="06e16-108">So erstellen Sie einen KPI</span><span class="sxs-lookup"><span data-stu-id="06e16-108">To create a KPI</span></span>](#bkmk_create_KPI)  
  
-   [<span data-ttu-id="06e16-109">So bearbeiten Sie einen KPI</span><span class="sxs-lookup"><span data-stu-id="06e16-109">To edit a KPI</span></span>](#bkmk_edit_KPI)  
  
-   [<span data-ttu-id="06e16-110">So löschen Sie einen KPI und das basismeasure</span><span class="sxs-lookup"><span data-stu-id="06e16-110">To delete a KPI and the base measure</span></span>](#bkmk_delete)  
  
-   [<span data-ttu-id="06e16-111">So löschen Sie einen KPI, behalten aber das Basismeasure bei</span><span class="sxs-lookup"><span data-stu-id="06e16-111">To delete a KPI, but keep the base measure</span></span>](#bkmk_delete_KPI)  
  
## <a name="tasks"></a><span data-ttu-id="06e16-112">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="06e16-112">Tasks</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="06e16-113">Bevor Sie einen KPI erstellen, müssen Sie zuerst ein Basismeasure generieren, das einen Wert ergibt.</span><span class="sxs-lookup"><span data-stu-id="06e16-113">Before creating a KPI, you must first create a Base measure that evaluates to value.</span></span> <span data-ttu-id="06e16-114">Anschließend erweitern Sie das Basismeasure zu einem KPI.</span><span class="sxs-lookup"><span data-stu-id="06e16-114">You then extend the Base measure to a KPI.</span></span> <span data-ttu-id="06e16-115">Das Erstellen von Measures wird in einem anderen Thema beschrieben: [Erstellen und Verwalten von Measures &#40;SSAS – tabellarisch&#41;](measures-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="06e16-115">How to create measures are described in another topic, [Create and Manage Measures &#40;SSAS Tabular&#41;](measures-ssas-tabular.md).</span></span> <span data-ttu-id="06e16-116">Für einen KPI ist zudem ein Zielwert erforderlich.</span><span class="sxs-lookup"><span data-stu-id="06e16-116">A KPI also requires a target value.</span></span> <span data-ttu-id="06e16-117">Dieser Wert kann von einem anderen vordefinierten Measure stammen oder ein absoluter Wert sein.</span><span class="sxs-lookup"><span data-stu-id="06e16-117">This value can be from another pre-defined measure or an absolute value.</span></span> <span data-ttu-id="06e16-118">Nachdem Sie ein Basismeasure zu einem KPI erweitert haben, können Sie den Zielwert auswählen und die Statusschwellenwerte im Dialogfeld Key Performance Indicator definieren.</span><span class="sxs-lookup"><span data-stu-id="06e16-118">Once you have extended a Base measure to a KPI, you can then select the target value and define status thresholds in the Key Performance Indicator dialog box.</span></span>  
  
###  <a name="to-create-a-kpi"></a><a name="bkmk_create_KPI"></a> <span data-ttu-id="06e16-119">So erstellen Sie einen KPI</span><span class="sxs-lookup"><span data-stu-id="06e16-119">To create a KPI</span></span>  
  
1.  <span data-ttu-id="06e16-120">Klicken Sie im Measureraster mit der rechten Maustaste auf das Measure, das als Basismeasure (Wert) fungieren soll, und klicken Sie dann im Kontextmenü auf **KPI erstellen**.</span><span class="sxs-lookup"><span data-stu-id="06e16-120">In the measure grid, right-click the measure that will serve as the Base measure (value), and then click **Create KPI**.</span></span>  
  
2.  <span data-ttu-id="06e16-121">Wählen Sie im Dialogfeld **Key Performance Indicator** unter **Zielwert definieren**eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="06e16-121">In the **Key Performance Indicator** dialog box, in **Define target value**, select from one of the following:</span></span>  
  
     <span data-ttu-id="06e16-122">Klicken Sie auf **Measure**, und wählen Sie dann ein Zielmeasure aus dem Listenfeld aus.</span><span class="sxs-lookup"><span data-stu-id="06e16-122">Select **Measure**, and then select a target measure from the listbox.</span></span>  
  
     <span data-ttu-id="06e16-123">Wählen Sie **Absoluter Wert**aus, und geben Sie einen numerischen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="06e16-123">Select **Absolute value**, and then type a numerical value.</span></span>  
  
3.  <span data-ttu-id="06e16-124">Klicken Sie in **Statusschwellenwerte definieren**auf den Schieberegler, um den niedrigen und hohen Schwellenwert festzulegen.</span><span class="sxs-lookup"><span data-stu-id="06e16-124">In **Define status thresholds**, click and slide the low and high threshold values.</span></span>  
  
4.  <span data-ttu-id="06e16-125">Klicken Sie in **Symbolart auswählen**auf einen Bildtyp.</span><span class="sxs-lookup"><span data-stu-id="06e16-125">In **Select icon style**, click an image type.</span></span>  
  
5.  <span data-ttu-id="06e16-126">Klicken Sie auf **Beschreibungen**, und geben Sie Beschreibungen für KPI, Wert, Status und Ziel ein.</span><span class="sxs-lookup"><span data-stu-id="06e16-126">Click on **Descriptions**, and then type descriptions for KPI, Value, Status, and Target.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="06e16-127">Sie können die Funktion In Excel analysieren verwenden, um den KPI zu testen.</span><span class="sxs-lookup"><span data-stu-id="06e16-127">You can use the Analyze in Excel feature to test your KPI.</span></span> <span data-ttu-id="06e16-128">Weitere Informationen finden Sie weiter unten in diesem Thema unter [Analysieren in Excel &#40;SSAS – tabellarisch&#41;](analyze-in-excel-ssas-tabular.md)definieren.</span><span class="sxs-lookup"><span data-stu-id="06e16-128">For more information, see [Analyze in Excel &#40;SSAS Tabular&#41;](analyze-in-excel-ssas-tabular.md).</span></span>  
  
###  <a name="to-edit-a-kpi"></a><a name="bkmk_edit_KPI"></a> <span data-ttu-id="06e16-129">So bearbeiten Sie einen KPI</span><span class="sxs-lookup"><span data-stu-id="06e16-129">To edit a KPI</span></span>  
  
-   <span data-ttu-id="06e16-130">Klicken Sie im Measureraster mit der rechten Maustaste auf das Measure, das als Basismeasure (Wert) des KPI fungiert, und klicken Sie dann auf **KPI-Einstellungen bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="06e16-130">In the measure grid, right-click the measure that serves as the Base measure (value) of the KPI, and then click **Edit KPI Settings**.</span></span>  
  
###  <a name="to-delete-a-kpi-and-the-base-measure"></a><a name="bkmk_delete"></a> <span data-ttu-id="06e16-131">So löschen Sie einen KPI und das Basismeasure</span><span class="sxs-lookup"><span data-stu-id="06e16-131">To delete a KPI and the base measure</span></span>  
  
-   <span data-ttu-id="06e16-132">Klicken Sie im Measureraster mit der rechten Maustaste auf das Measure, das als Basismeasure (Wert) des KPI fungiert, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="06e16-132">In the measure grid, right-click the measure that serves as the Base measure (value) of the KPI, and then click **Delete**.</span></span>  
  
###  <a name="to-delete-a-kpi-but-keep-the-base-measure"></a><a name="bkmk_delete_KPI"></a><span data-ttu-id="06e16-133">So löschen Sie einen KPI, behalten aber das basismeasure bei</span><span class="sxs-lookup"><span data-stu-id="06e16-133">To delete a KPI, but keep the base measure</span></span>  
  
-   <span data-ttu-id="06e16-134">Klicken Sie im Measureraster mit der rechten Maustaste auf das Measure, das als Basismeasure (Wert) des KPI fungiert, und klicken Sie dann auf **KPI löschen**.</span><span class="sxs-lookup"><span data-stu-id="06e16-134">In the measure grid, right-click the measure that serves as the Base measure (value) of the KPI, and then click **Delete KPI**.</span></span>  
  
## <a name="alt-shortcuts"></a><span data-ttu-id="06e16-135">ALT-Tastenkombinationen</span><span class="sxs-lookup"><span data-stu-id="06e16-135">ALT Shortcuts</span></span>  
  
|<span data-ttu-id="06e16-136">Benutzeroberflächenabschnitt</span><span class="sxs-lookup"><span data-stu-id="06e16-136">UI section</span></span>|<span data-ttu-id="06e16-137">Tastaturbefehl</span><span class="sxs-lookup"><span data-stu-id="06e16-137">Key command</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="06e16-138">KPI-Basismeasure</span><span class="sxs-lookup"><span data-stu-id="06e16-138">KPI base measure</span></span>|<span data-ttu-id="06e16-139">ALT+B</span><span class="sxs-lookup"><span data-stu-id="06e16-139">ALT+B</span></span>|  
|<span data-ttu-id="06e16-140">KPI-Status</span><span class="sxs-lookup"><span data-stu-id="06e16-140">KPI Status</span></span>|<span data-ttu-id="06e16-141">ALT+S</span><span class="sxs-lookup"><span data-stu-id="06e16-141">ALT+S</span></span>|  
|<span data-ttu-id="06e16-142">"Measure"</span><span class="sxs-lookup"><span data-stu-id="06e16-142">Measure</span></span>|<span data-ttu-id="06e16-143">ALT+M</span><span class="sxs-lookup"><span data-stu-id="06e16-143">ALT+M</span></span>|  
|<span data-ttu-id="06e16-144">Absoluter Wert</span><span class="sxs-lookup"><span data-stu-id="06e16-144">Absolute value</span></span>|<span data-ttu-id="06e16-145">ALT+A</span><span class="sxs-lookup"><span data-stu-id="06e16-145">ALT+A</span></span>|  
|<span data-ttu-id="06e16-146">Statusschwellenwerte definieren</span><span class="sxs-lookup"><span data-stu-id="06e16-146">Define status thresholds</span></span>|<span data-ttu-id="06e16-147">ALT+C</span><span class="sxs-lookup"><span data-stu-id="06e16-147">ALT+U</span></span>|  
|<span data-ttu-id="06e16-148">Symbolart auswählen</span><span class="sxs-lookup"><span data-stu-id="06e16-148">Select icon style</span></span>|<span data-ttu-id="06e16-149">ALT+I</span><span class="sxs-lookup"><span data-stu-id="06e16-149">ALT+I</span></span>|  
|<span data-ttu-id="06e16-150">Trend</span><span class="sxs-lookup"><span data-stu-id="06e16-150">Trend</span></span>|<span data-ttu-id="06e16-151">ALT+T</span><span class="sxs-lookup"><span data-stu-id="06e16-151">ALT+T</span></span>|  
|<span data-ttu-id="06e16-152">Beschreibungen</span><span class="sxs-lookup"><span data-stu-id="06e16-152">Descriptions</span></span>|<span data-ttu-id="06e16-153">ALT+D</span><span class="sxs-lookup"><span data-stu-id="06e16-153">ALT+D</span></span>|  
|<span data-ttu-id="06e16-154">Trend</span><span class="sxs-lookup"><span data-stu-id="06e16-154">Trend</span></span>|<span data-ttu-id="06e16-155">ALT+T</span><span class="sxs-lookup"><span data-stu-id="06e16-155">ALT+T</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="06e16-156">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="06e16-156">See Also</span></span>  
 <span data-ttu-id="06e16-157">[KPIs &#40;tabellarischen SSAS-&#41;](kpis-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="06e16-157">[KPIs &#40;SSAS Tabular&#41;](kpis-ssas-tabular.md) </span></span>  
 <span data-ttu-id="06e16-158">[Measures &#40;tabellarischen SSAS-&#41;](measures-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="06e16-158">[Measures &#40;SSAS Tabular&#41;](measures-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="06e16-159">Erstellen und Verwalten von Measures &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="06e16-159">Create and Manage Measures &#40;SSAS Tabular&#41;</span></span>](create-and-manage-measures-ssas-tabular.md)  
  
  
