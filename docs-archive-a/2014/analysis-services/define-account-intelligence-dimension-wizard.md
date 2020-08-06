---
title: Konto Intelligenz definieren (Dimensions-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.accountintelligencetypemapping.f1
ms.assetid: cbcff072-3a7e-4e98-858f-1b4265461561
author: minewiskan
ms.author: owend
ms.openlocfilehash: 90871e2299d1531db1b678b1f4b16ddd7f1db767
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620052"
---
# <a name="define-account-intelligence-dimension-wizard"></a><span data-ttu-id="98393-102">Kontointelligenz definieren (Dimensions-Assistent)</span><span class="sxs-lookup"><span data-stu-id="98393-102">Define Account Intelligence (Dimension Wizard)</span></span>
  <span data-ttu-id="98393-103">Auf der Seite **Kontointelligenz definieren** können Sie die auf der [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Instanz definierten Kontotypen den Kontotypen zuordnen, die in dem Dimensionsattribut definiert sind, das in der Dimension dem Attributtyp unter **Kontotyp** zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="98393-103">Use the **Define Account Intelligence** page to map account types defined on the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance to account types defined in the dimension attribute associated with the **Account Type** attribute type in the dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98393-104"> Diese Seite wird nur angezeigt, wenn Sie **Standarddimension** auf der Seite **Dimensionstyp auswählen** ausgewählt haben und wenn Sie dem **Kontotyp** -Attributtyp auf der Seite **Dimensionstyp angeben** ein Dimensionsattribut zugeordnet haben.</span><span class="sxs-lookup"><span data-stu-id="98393-104">This page is displayed only if you selected **Standard dimension** on the **Select the Dimension Type** page and if you mapped a dimension attribute to the **Account Type** attribute type on the **Specify Dimension Type** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="98393-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="98393-105">Options</span></span>  
 <span data-ttu-id="98393-106">**Kontotypen der Quelltabelle**</span><span class="sxs-lookup"><span data-stu-id="98393-106">**Source Table Account Types**</span></span>  
 <span data-ttu-id="98393-107">Zeigt die Werte an, die im Dimensionsattribut enthalten sind, das dem Attributtyp **Kontotyp** auf der Seite **Dimensionsschlüssel und -typ angeben** zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="98393-107">Displays the values contained in the dimension attribute assigned to the **Account Type** attribute type in the **Specify Dimension Key and Type** page.</span></span>  
  
 <span data-ttu-id="98393-108">**Integrierte Kontotypen**</span><span class="sxs-lookup"><span data-stu-id="98393-108">**Built-In Account Types**</span></span>  
 <span data-ttu-id="98393-109">Wählen Sie den auf der [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Instanz definierten Kontotyp aus, der den Kontotypen in der Quelltabelle zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="98393-109">Select the account type defined on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that maps to the account types in the source table.</span></span>  
  
 <span data-ttu-id="98393-110">In der folgenden Tabelle sind die Kontotypen aufgelistet, die auf einer [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Instanz definiert sind.</span><span class="sxs-lookup"><span data-stu-id="98393-110">The following table lists the account types that are defined on an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span>  
  
|<span data-ttu-id="98393-111">Wert</span><span class="sxs-lookup"><span data-stu-id="98393-111">Value</span></span>|<span data-ttu-id="98393-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="98393-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="98393-113">**Asset**</span><span class="sxs-lookup"><span data-stu-id="98393-113">**Asset**</span></span>|<span data-ttu-id="98393-114">Wert des Besitzes zu einem bestimmten Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="98393-114">Value of things owned at a specific time.</span></span>|  
|<span data-ttu-id="98393-115">**Balance**</span><span class="sxs-lookup"><span data-stu-id="98393-115">**Balance**</span></span>|<span data-ttu-id="98393-116">Anzahl von etwas zu einem bestimmten Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="98393-116">Count of something at a specific time.</span></span>|  
|<span data-ttu-id="98393-117">**Expense**</span><span class="sxs-lookup"><span data-stu-id="98393-117">**Expense**</span></span>|<span data-ttu-id="98393-118">Ausgabenbetrag.</span><span class="sxs-lookup"><span data-stu-id="98393-118">Value of things spent.</span></span>|  
|<span data-ttu-id="98393-119">**Flow**</span><span class="sxs-lookup"><span data-stu-id="98393-119">**Flow**</span></span>|<span data-ttu-id="98393-120">Schrittweise Auszählung von Objekten.</span><span class="sxs-lookup"><span data-stu-id="98393-120">Incremental count of things.</span></span>|  
|<span data-ttu-id="98393-121">**Income**</span><span class="sxs-lookup"><span data-stu-id="98393-121">**Income**</span></span>|<span data-ttu-id="98393-122">Einnahmenbetrag.</span><span class="sxs-lookup"><span data-stu-id="98393-122">Value of things received.</span></span>|  
|<span data-ttu-id="98393-123">**Liability**</span><span class="sxs-lookup"><span data-stu-id="98393-123">**Liability**</span></span>|<span data-ttu-id="98393-124">Der zu einem bestimmten Zeitpunkt geschuldete Betrag.</span><span class="sxs-lookup"><span data-stu-id="98393-124">Value of things owed at a specific time.</span></span>|  
|<span data-ttu-id="98393-125">**Statistisch**</span><span class="sxs-lookup"><span data-stu-id="98393-125">**Statistical**</span></span>|<span data-ttu-id="98393-126">Berechnetes Verhältnis von Werten oder Anzahl von Objekten, die nicht aggregiert wird.</span><span class="sxs-lookup"><span data-stu-id="98393-126">Calculated ratio of something, or count of something that does not aggregate.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="98393-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="98393-127">See Also</span></span>  
 <span data-ttu-id="98393-128">[Dimensions-Assistent F1-Hilfe](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="98393-128">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="98393-129">[Dimensionen &#40;Analysis Services Mehrdimensionale Daten&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="98393-129">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="98393-130">Dimensionen in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="98393-130">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
