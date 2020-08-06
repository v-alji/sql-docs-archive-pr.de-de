---
title: Konto Intelligenz definieren (Business Intelligence-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.acctintelligence.mapaccounttype.f1
ms.assetid: fe4c204b-1031-4ac4-9916-8052ce2301cc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 17b8136e79097cd502d6b239ba6867c4e678c70f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696321"
---
# <a name="define-account-intelligence-business-intelligence-wizard"></a><span data-ttu-id="9fe7e-102">Definieren der Kontointelligenz (Business Intelligence-Assistent)</span><span class="sxs-lookup"><span data-stu-id="9fe7e-102">Define Account Intelligence (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="9fe7e-103">Auf der Seite **Kontointelligenz definieren** können Sie durch eine Quelltabelle in der Datenquelle für die Kontodimension definierte Kontotypen den auf der [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Instanz definierten Kontotypen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="9fe7e-103">Use the **Define Account Intelligence** page to map account types defined on the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance to account types defined by a source table in the data source that supplies the data for the account dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9fe7e-104"> Die Seite wird angezeigt, wenn dem Attributtyp **Kontotyp** auf der Seite **Dimensionsattribute konfigurieren** ein Dimensionsattribut zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="9fe7e-104">This page will appear if a dimension attribute was mapped to the **Account Type** attribute type on the **Configure Dimension Attributes** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9fe7e-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="9fe7e-105">Options</span></span>  
 <span data-ttu-id="9fe7e-106">**Kontotypen der Quelltabelle**</span><span class="sxs-lookup"><span data-stu-id="9fe7e-106">**Source Table Account Types**</span></span>  
 <span data-ttu-id="9fe7e-107">Zeigt die Werte an, die im Dimensionsattribut enthalten sind, das dem Attributtyp **Kontotyp** auf der Seite **Dimensionsattribute konfigurieren** zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="9fe7e-107">Displays the values that are contained in the dimension attribute assigned to the **Account Type** attribute type on the **Configure Dimension Attributes** page.</span></span>  
  
 <span data-ttu-id="9fe7e-108">**Integrierte Kontotypen**</span><span class="sxs-lookup"><span data-stu-id="9fe7e-108">**Built-In Account Types**</span></span>  
 <span data-ttu-id="9fe7e-109">Wählen Sie den auf der [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Instanz definierten Kontotyp aus, der den Kontotypen in der Quelltabelle zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="9fe7e-109">Select the account type defined on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that maps to the account types in the source table.</span></span>  
  
 <span data-ttu-id="9fe7e-110">In der folgenden Tabelle sind die Kontotypen aufgelistet, die auf einer [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Instanz definiert sind.</span><span class="sxs-lookup"><span data-stu-id="9fe7e-110">The following table lists the account types that are defined on an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span>  
  
|<span data-ttu-id="9fe7e-111">Wert</span><span class="sxs-lookup"><span data-stu-id="9fe7e-111">Value</span></span>|<span data-ttu-id="9fe7e-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9fe7e-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9fe7e-113">**Asset**</span><span class="sxs-lookup"><span data-stu-id="9fe7e-113">**Asset**</span></span>|<span data-ttu-id="9fe7e-114">Wert des Besitzes zu einem bestimmten Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="9fe7e-114">Value of things owned at a specific time.</span></span>|  
|<span data-ttu-id="9fe7e-115">**Balance**</span><span class="sxs-lookup"><span data-stu-id="9fe7e-115">**Balance**</span></span>|<span data-ttu-id="9fe7e-116">Anzahl von etwas zu einem bestimmten Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="9fe7e-116">Count of something at a specific time.</span></span>|  
|<span data-ttu-id="9fe7e-117">**Expense**</span><span class="sxs-lookup"><span data-stu-id="9fe7e-117">**Expense**</span></span>|<span data-ttu-id="9fe7e-118">Ausgabenbetrag.</span><span class="sxs-lookup"><span data-stu-id="9fe7e-118">Value of things spent.</span></span>|  
|<span data-ttu-id="9fe7e-119">**Flow**</span><span class="sxs-lookup"><span data-stu-id="9fe7e-119">**Flow**</span></span>|<span data-ttu-id="9fe7e-120">Schrittweise Auszählung von Objekten.</span><span class="sxs-lookup"><span data-stu-id="9fe7e-120">Incremental count of things.</span></span>|  
|<span data-ttu-id="9fe7e-121">**Income**</span><span class="sxs-lookup"><span data-stu-id="9fe7e-121">**Income**</span></span>|<span data-ttu-id="9fe7e-122">Einnahmenbetrag.</span><span class="sxs-lookup"><span data-stu-id="9fe7e-122">Value of things received.</span></span>|  
|<span data-ttu-id="9fe7e-123">**Liability**</span><span class="sxs-lookup"><span data-stu-id="9fe7e-123">**Liability**</span></span>|<span data-ttu-id="9fe7e-124">Der zu einem bestimmten Zeitpunkt geschuldete Betrag.</span><span class="sxs-lookup"><span data-stu-id="9fe7e-124">Value of things owed at a specific time.</span></span>|  
|<span data-ttu-id="9fe7e-125">**Statistisch**</span><span class="sxs-lookup"><span data-stu-id="9fe7e-125">**Statistical**</span></span>|<span data-ttu-id="9fe7e-126">Berechnetes Verhältnis von Werten oder Anzahl von Objekten, die nicht aggregiert wird.</span><span class="sxs-lookup"><span data-stu-id="9fe7e-126">Calculated ratio of something, or count of something that does not aggregate.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9fe7e-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9fe7e-127">See Also</span></span>  
 <span data-ttu-id="9fe7e-128">[Business Intelligence Wizard (F1-Hilfe)](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="9fe7e-128">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="9fe7e-129">[Cube-Designer &#40;Analysis Services Mehrdimensionale Daten&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="9fe7e-129">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="9fe7e-130">Der Dimensions-Designer &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="9fe7e-130">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
