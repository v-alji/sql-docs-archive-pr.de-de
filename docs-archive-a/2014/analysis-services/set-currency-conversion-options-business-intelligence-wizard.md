---
title: Optionen für die Währungsumrechnung festlegen (Business Intelligence-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.currencyconversion.calculationsettings.f1
ms.assetid: a49d4e1f-bdda-4a83-ab4f-ce8c500e1d6d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 61877deb0bc422d65f977e3fc9de3e678f7d8477
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721834"
---
# <a name="set-currency-conversion-options-business-intelligence-wizard"></a><span data-ttu-id="0a868-102">Währungsumrechnung festlegen (Business Intelligence-Assistent) (SSAS)</span><span class="sxs-lookup"><span data-stu-id="0a868-102">Set Currency Conversion Options (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="0a868-103">Auf der Seite **Währungsumrechnung festlegen** können Sie Währungsumrechnungen für eine Measuregruppe definieren, die Wechselkurse enthält.</span><span class="sxs-lookup"><span data-stu-id="0a868-103">Use the **Set Currency Conversion** page to define currency conversion calculations for a measure group that contains exchange rates.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a868-104">Diese Seite wird nicht angezeigt, wenn der Business Intelligence-Assistent vom Dimensions-Designer aus oder durch Klicken mit der rechten Maustaste auf eine Dimension im Projektmappen-Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="0a868-104">This page does not appear if the Business Intelligence Wizard was started from Dimension Designer or by right-clicking a dimension in Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="0a868-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="0a868-105">Options</span></span>  
 <span data-ttu-id="0a868-106">**Wählen Sie die Measuregruppe aus, die Wechselkurse enthält**</span><span class="sxs-lookup"><span data-stu-id="0a868-106">**Select the measure group that contains exchange rates**</span></span>  
 <span data-ttu-id="0a868-107">Wählen Sie die Measuregruppe mit den Wechselkursen aus, die beim Berechnen der Währungsumrechnung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0a868-107">Select the measure group that contains the exchange rates that the currency conversion calculations should reference.</span></span>  
  
 <span data-ttu-id="0a868-108">**Geben Sie die Pivotwährung an**</span><span class="sxs-lookup"><span data-stu-id="0a868-108">**Specify the pivot currency**</span></span>  
 <span data-ttu-id="0a868-109">Wählen Sie das Element aus, das als Pivotwährung der Measuregruppe fungiert.</span><span class="sxs-lookup"><span data-stu-id="0a868-109">Select the member that serves as the pivot currency for the measure group.</span></span>  
  
 <span data-ttu-id="0a868-110">**Wählen Sie die Art der Wechselkurseingabe aus (Auswählen einer Beispielwährung)**</span><span class="sxs-lookup"><span data-stu-id="0a868-110">**Select how you entered your exchange rates (select a sample currency)**</span></span>  
 <span data-ttu-id="0a868-111">Wählen Sie in der Währungsdimension ein Element aus, das eine Beispielwährung darstellt, um den Text der Optionen X Einheiten der Pivotwährung entsprechen 1 Einheit der Beispielwährung und X Einheiten der Beispielwährung entsprechen 1 Einheit der Pivotwährung zu ändern und so die Richtung des Wechselkurses deutlicher anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0a868-111">Select a member representing a sample currency from the currency dimension to change the text for the X pivot currency per 1 sample currency and X sample currency per 1 pivot currency options to better display the exchange rate direction.</span></span>  
  
 <span data-ttu-id="0a868-112">**X Einheiten der Pivotwährung entsprechen 1 Einheit der Beispielwährung**</span><span class="sxs-lookup"><span data-stu-id="0a868-112">**X pivot currency per 1 sample currency**</span></span>  
 <span data-ttu-id="0a868-113">Wählen Sie diese Option aus, wenn die Wechselkurse in der Wechselkurs-Measuregruppe als Multiplikator für die angegebene Pivotwährung fungieren.</span><span class="sxs-lookup"><span data-stu-id="0a868-113">Select to indicate that the exchange rates in the rate measure group represent a multiplier for the specified pivot currency.</span></span>  
  
 <span data-ttu-id="0a868-114">**X Einheiten der Beispielwährung entsprechen 1 Einheit der Pivotwährung**</span><span class="sxs-lookup"><span data-stu-id="0a868-114">**X sample currency per 1 pivot currency**</span></span>  
 <span data-ttu-id="0a868-115">Wählen Sie diese Option aus, wenn die Wechselkurse in der Wechselkurs-Measuregruppe als Multiplikator für die angegebene Beispielwährung fungieren.</span><span class="sxs-lookup"><span data-stu-id="0a868-115">Select to indicate that the exchange rates in the rate measure group represent a multiplier for the specified sample currency.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a868-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0a868-116">See Also</span></span>  
 <span data-ttu-id="0a868-117">[Business Intelligence Wizard (F1-Hilfe)](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="0a868-117">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="0a868-118">[Cube-Designer &#40;Analysis Services Mehrdimensionale Daten&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="0a868-118">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="0a868-119">Der Dimensions-Designer &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="0a868-119">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
