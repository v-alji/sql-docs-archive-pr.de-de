---
title: Power View von Bericht Erstellungs Eigenschaften (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 51205c2d-b6ce-4b92-afd2-58e399a81691
author: minewiskan
ms.author: owend
ms.openlocfilehash: e85d91578e5c3f4b47f56eeb86aa738e37e8f59b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696134"
---
# <a name="power-view-reporting-properties-ssas-tabular"></a><span data-ttu-id="3ace4-102">Power View-Berichterstellungseigenschaften (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="3ace4-102">Power View Reporting Properties (SSAS Tabular)</span></span>
  [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] <span data-ttu-id="3ace4-103">ermöglicht eine intuitive Ad-hoc-Berichterstellung für Fachanwender wie Datenanalysten, Entscheidungsträger und Information Worker.</span><span class="sxs-lookup"><span data-stu-id="3ace4-103">provides intuitive ad-hoc reporting for business users such as data analysts, business decision makers, and information workers.</span></span> <span data-ttu-id="3ace4-104">Sie können bequem Sichten von Daten aus Tabellenmodellen, die auf in einem PowerPivot-Katalog erstellten PowerPivot-Arbeitsmappen basieren, oder aus durch die Verwendung von [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] erstellten und anschließend für [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Analysis Services-Instanzen bereitgestellten Tabellenmodellen erstellen und mit diesen Sichten interagieren.</span><span class="sxs-lookup"><span data-stu-id="3ace4-104">They can easily create and interact with views of data from tabular models based on PowerPivot workbooks published in a PowerPivot Gallery, or tabular models authored by using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and then deployed to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Analysis Services instances.</span></span> [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] <span data-ttu-id="3ace4-105">ist eine browserbasierte Silverlight-Anwendung, die aus SharePoint Server 2010 oder später gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="3ace4-105">is a browser-based Silverlight application launched from SharePoint Server 2010 or later.</span></span>  
  
 <span data-ttu-id="3ace4-106">Beim Erstellen von Projekten für tabellarische Modelle in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]können Sie bestimmte Berichtseigenschaften konfigurieren, die im Hinblick auf [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] -Berichte eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="3ace4-106">When authoring tabular model projects in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], you can configure certain reporting properties unique to [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] reports.</span></span> <span data-ttu-id="3ace4-107">In den Themen dieses Abschnitts wird beschrieben, wie ein Modell optimiert werden kann, um das Berichtsverhalten in [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)]zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="3ace4-107">Topics in this section describe how to optimize a model to improve the reporting experience in [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="3ace4-108">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="3ace4-108">Related Tasks</span></span>  
  
|<span data-ttu-id="3ace4-109">Thema</span><span class="sxs-lookup"><span data-stu-id="3ace4-109">Topic</span></span>|<span data-ttu-id="3ace4-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3ace4-110">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="3ace4-111">Konfigurieren eines Standardfeldsatzes für Power View-Berichte &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="3ace4-111">Configure Default Field Set for Power View Reports &#40;SSAS Tabular&#41;</span></span>](power-view-configure-default-field-set-for-reports.md)|<span data-ttu-id="3ace4-112">Hier wird beschrieben, wie ein Standardfeldsatz konfiguriert werden kann. Bei diesem handelt es sich um eine vordefinierte Liste von Spalten und Measures, die einem [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] -Berichtszeichenbereich automatisch hinzugefügt werden, wenn Sie in der Berichtsfeldliste die Tabelle auswählen.</span><span class="sxs-lookup"><span data-stu-id="3ace4-112">Describes how to configure a Default Field Set; a predefined list of columns and measures that are automatically added to a [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] report canvas when the table is selected in the report field list.</span></span>|  
|[<span data-ttu-id="3ace4-113">Konfigurieren von Tabellenverhaltenseigenschaften für Power View-Berichte &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="3ace4-113">Configure Table Behavior Properties for Power View Reports &#40;SSAS Tabular&#41;</span></span>](power-view-configure-table-behavior-properties-for-reports.md)|<span data-ttu-id="3ace4-114">Hier wird beschrieben, wie Tabellenverhaltenseigenschaften, die Detailzeilen auf einer präziseren Ebene verfügbar machen, konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="3ace4-114">Describes how to configure table behavior properties that expose detail rows at a more granular level.</span></span> <span data-ttu-id="3ace4-115">Das Festlegen von Tabellenverhaltenseigenschaften ändert das Gruppierungsverhalten von Detailzeilen und erzeugt eine bessere Standardplatzierung bei der Identifizierung von Informationen in Kachel, Karten- und Diagrammlayouts.</span><span class="sxs-lookup"><span data-stu-id="3ace4-115">Setting table behavior properties changes the grouping behavior of detail rows and produces a better default placement of identifying information in tile, card, and chart layouts.</span></span>|  
  
  