---
title: Architektur des benutzerdefinierten Berichtselements | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, architecture
ms.assetid: 2a88ea46-c9f8-4dd7-aad1-16de11da4f06
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a053eb55547da9030eebe9036667cca2e14606f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608407"
---
# <a name="custom-report-item-architecture"></a><span data-ttu-id="f1d1d-102">Architektur des benutzerdefinierten Berichtselements</span><span class="sxs-lookup"><span data-stu-id="f1d1d-102">Custom Report Item Architecture</span></span>
  <span data-ttu-id="f1d1d-103">Ein benutzerdefiniertes Berichtselement ist eine Erweiterung von RDL (Report Definition Language), mit dem Entwickler Funktionen hinzufügen können, die ursprünglich nicht in RDL unterstützt werden oder mit denen die Funktionen bestehender Steuerelemente erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="f1d1d-103">A custom report item is an extension to the Report Definition Language (RDL) that allows developers to add functionality that's not natively supported in RDL or extend the functionality of existing controls.</span></span> <span data-ttu-id="f1d1d-104">Es gibt zwei Hauptkomponenten in einem benutzerdefinierten Berichtselement: die Laufzeitkomponente und die Entwurfszeitkomponente.</span><span class="sxs-lookup"><span data-stu-id="f1d1d-104">There are two main components to a custom report item: the run-time component and the design-time component.</span></span> <span data-ttu-id="f1d1d-105">Diese Komponenten sind als [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Assemblys implementiert und können in jeder CLS-konformen Sprache geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="f1d1d-105">These components are implemented as [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] assemblies, and can be written in any CLS-compliant language.</span></span>  
  
## <a name="the-run-time-component"></a><span data-ttu-id="f1d1d-106">Die Laufzeitkomponente</span><span class="sxs-lookup"><span data-stu-id="f1d1d-106">The Run-Time Component</span></span>  
 <span data-ttu-id="f1d1d-107">Die Laufzeitkomponente für ein benutzerdefiniertes Berichtselement wird vom Berichtsprozessor zur Laufzeit aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f1d1d-107">The run-time component for a custom report item is called by the report processor at run time.</span></span> <span data-ttu-id="f1d1d-108">Die Laufzeitkomponente akzeptiert Daten, die vom Berichtsprozessor zur Laufzeit übergeben werden, verarbeitet diese Daten und gibt ein Bild zurück, das das gerenderte, benutzerdefinierte Berichtselement enthält.</span><span class="sxs-lookup"><span data-stu-id="f1d1d-108">The run-time component accepts data passed by the report processor at run time, processes this data, and returns an image containing the rendered custom report item.</span></span>  
  
 <span data-ttu-id="f1d1d-109">![Laufzeitkomponente des benutzerdefinierten Berichtselements](../../../2014/reporting-services/media/customreportitemrun-timecomponentarchitecture.gif "Laufzeitkomponente des benutzerdefinierten Berichtselements")</span><span class="sxs-lookup"><span data-stu-id="f1d1d-109">![Custom report item run-time component](../../../2014/reporting-services/media/customreportitemrun-timecomponentarchitecture.gif "Custom report item run-time component")</span></span>  
  
## <a name="the-design-time-component"></a><span data-ttu-id="f1d1d-110">Die Entwurfszeitkomponente</span><span class="sxs-lookup"><span data-stu-id="f1d1d-110">The Design-Time Component</span></span>  
 <span data-ttu-id="f1d1d-111">Über die Entwurfszeitkomponente kann das benutzerdefinierte Berichtselement in der Berichts-Designer-Schnittstelle in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] definiert und bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="f1d1d-111">The design-time component allows the custom report item to be defined and manipulated in the Report Designer interface in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="f1d1d-112">Die Entwurfszeitkomponente besteht aus mehreren Untersteuerungselementen, die das Aussehen und die Eigenschaften des benutzerdefinierten Berichtselements in der Entwurfsumgebung steuern.</span><span class="sxs-lookup"><span data-stu-id="f1d1d-112">The design-time component consists of several sub-controls that control the appearance and properties of the custom report item in the design environment.</span></span>  
  
 <span data-ttu-id="f1d1d-113">![Entwurfszeitkomponente des benutzerdefinierten Berichtselements](../../../2014/reporting-services/media/customreportitemdesign-timecomponentarchitecture.gif "Entwurfszeitkomponente des benutzerdefinierten Berichtselements")</span><span class="sxs-lookup"><span data-stu-id="f1d1d-113">![Custom report item design-time component](../../../2014/reporting-services/media/customreportitemdesign-timecomponentarchitecture.gif "Custom report item design-time component")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1d1d-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f1d1d-114">See Also</span></span>  
 <span data-ttu-id="f1d1d-115">[Erstellen einer Laufzeitkomponente für ein benutzerdefiniertes Berichts Element](../custom-report-items/creating-a-custom-report-item-run-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="f1d1d-115">[Creating a Custom Report Item Run-Time Component](../custom-report-items/creating-a-custom-report-item-run-time-component.md) </span></span>  
 <span data-ttu-id="f1d1d-116">[Erstellen einer Entwurfszeit Komponente für ein benutzerdefiniertes Berichts Element](../custom-report-items/creating-a-custom-report-item-design-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="f1d1d-116">[Creating a Custom Report Item Design-Time Component](../custom-report-items/creating-a-custom-report-item-design-time-component.md) </span></span>  
 [<span data-ttu-id="f1d1d-117">Vorgehensweise: Bereitstellen eines benutzerdefinierten Berichtselements</span><span class="sxs-lookup"><span data-stu-id="f1d1d-117">How to: Deploy a Custom Report Item</span></span>](../custom-report-items/how-to-deploy-a-custom-report-item.md)  
  
  
