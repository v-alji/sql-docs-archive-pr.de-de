---
title: Benutzerdefinierte Berichtselemente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- extending Reporting Services
- Reporting Services, extending
- custom report items
ms.assetid: 64dcaf2c-1af5-4937-8ff7-98f1ec3b367e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 86b819cb4d305e537a52a2e7f25cdfa3aefa5f9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725314"
---
# <a name="custom-report-items"></a><span data-ttu-id="2a6fd-102">Custom Report Items</span><span class="sxs-lookup"><span data-stu-id="2a6fd-102">Custom Report Items</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="2a6fd-103">enthält eine komplexe Sammlung von Tools für die Erstellung und Veröffentlichung von Unternehmensberichten, für die Verwaltung der Zugriffsrechte und Abonnements und die Erweiterung der Berichtsfunktionen durch eine umfassende API.</span><span class="sxs-lookup"><span data-stu-id="2a6fd-103">provides a rich set of tools for building and publishing enterprise reports, managing security and subscriptions, and extending the reporting functionality through a comprehensive API.</span></span> <span data-ttu-id="2a6fd-104">Die Berichte werden mit der XML-Sprache RDL (Report Definition Language) definiert.</span><span class="sxs-lookup"><span data-stu-id="2a6fd-104">Reports are defined using an XML-based language called Report Definition Language (RDL).</span></span> <span data-ttu-id="2a6fd-105">RDL verfügt über einen Satz von Anweisungen, die Layout, Abfrageinformationen und Elementtypen eines Berichts beschreiben.</span><span class="sxs-lookup"><span data-stu-id="2a6fd-105">RDL provides a set of instructions that describe layout, query information, and item types for a report.</span></span> <span data-ttu-id="2a6fd-106">Es ist möglich, RDL durch das Schreiben eines benutzerdefinierten Berichtselements zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="2a6fd-106">It is possible to extend RDL by writing a custom report item.</span></span> <span data-ttu-id="2a6fd-107">Das benutzerdefinierte Berichtselement besteht aus einer Laufzeitkomponente, die vom Berichtsprozessor zur Laufzeit aufgerufen wird, und einer Entwurfszeitkomponente, die das benutzerdefinierte Berichtselement im Berichts-Designer zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="2a6fd-107">The custom report item consists of a run-time component, which is called by the report processor at run time, and a design-time component, which allows the custom report item to be available in Report Designer.</span></span>  
  
 <span data-ttu-id="2a6fd-108">Ein Beispiel für ein vollständig implementiertes benutzerdefiniertes Berichtselement finden Sie unter [SQL Server Reporting Services-Produktbeispiele](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="2a6fd-108">For a sample of a fully implemented custom report item, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="custom-report-item-scenarios"></a><span data-ttu-id="2a6fd-109">Szenarien für benutzerdefinierte Berichtselemente</span><span class="sxs-lookup"><span data-stu-id="2a6fd-109">Custom Report Item Scenarios</span></span>  
 <span data-ttu-id="2a6fd-110">Es kann sein, dass Entwickler, die [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in Ihre Anwendungen integrieren müssen, Funktionen benötigen, die ursprünglich nicht in der RDL unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="2a6fd-110">Developers who need to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into their applications may require functionality that is not natively supported in RDL.</span></span> <span data-ttu-id="2a6fd-111">Dazu können folgende Elemente gehören: Zuordnungssteuerelemente, horizontale Listen, Spaltenlisten und Repivotable-Matrizen.</span><span class="sxs-lookup"><span data-stu-id="2a6fd-111">This may include items such as: map controls, horizontal lists, columnar lists, and repivotable matrixes.</span></span> <span data-ttu-id="2a6fd-112">Eine Laufzeitkomponente für ein benutzerdefiniertes Berichtselement kann zu diesem Zweck mit einer Anwendung entwickelt und verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="2a6fd-112">A run-time custom report item component can be developed and distributed with an application to fill this need.</span></span>  
  
 <span data-ttu-id="2a6fd-113">Möglicherweise möchten einige Entwickler zusätzlich zur Entwicklung von Funktionen, die ursprünglich nicht unterstützt wurden, bestehende Funktionen durch Alternativversionen der Steuerelemente erweitern, die bereits in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="2a6fd-113">In addition to providing functionality that isn't natively supported, some developers may want to extend existing functionality with alternative versions of controls that are already included with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="2a6fd-114">In diesem Szenario könnte ein Entwickler drei Komponenten anbieten: eine Laufzeitkomponente, eine Entwurfszeitkomponente und eine Laufzeitkonvertierungskomponente, mit der ein vorhandenes Berichtselement bei Bedarf in ein benutzerdefiniertes Berichtselement umgewandelt wird.</span><span class="sxs-lookup"><span data-stu-id="2a6fd-114">In this scenario, a developer could provide three components: a run-time component, a design-time component, and a design-time report item conversion component that converts an existing report item into a custom report item on demand.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2a6fd-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="2a6fd-115">In This Section</span></span>  
 [<span data-ttu-id="2a6fd-116">Architektur des benutzerdefinierten Berichtselements</span><span class="sxs-lookup"><span data-stu-id="2a6fd-116">Custom Report Item Architecture</span></span>](custom-report-item-architecture.md)  
 <span data-ttu-id="2a6fd-117">Erläutert die Komponenten, aus denen ein benutzerdefiniertes Berichtselement besteht.</span><span class="sxs-lookup"><span data-stu-id="2a6fd-117">Describes the components that make up a custom report item.</span></span>  
  
 [<span data-ttu-id="2a6fd-118">Implementierungsanforderungen für benutzerdefinierte Berichtselemente</span><span class="sxs-lookup"><span data-stu-id="2a6fd-118">Custom Report Item Implementation Requirements</span></span>](custom-report-item-implementation-requirements.md)  
 <span data-ttu-id="2a6fd-119">Beschreibt die Voraussetzungen für die Erstellung eines benutzerdefinierten Berichtselements.</span><span class="sxs-lookup"><span data-stu-id="2a6fd-119">Describes prerequisites for creating a custom report item.</span></span>  
  
 [<span data-ttu-id="2a6fd-120">Erstellen einer Laufzeitkomponente für ein benutzerdefiniertes Berichtselement</span><span class="sxs-lookup"><span data-stu-id="2a6fd-120">Creating a Custom Report Item Run-Time Component</span></span>](creating-a-custom-report-item-run-time-component.md)  
 <span data-ttu-id="2a6fd-121">Beschreibt, wie eine benutzerdefinierte Laufzeitkomponente für ein Berichtselement erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="2a6fd-121">Describes how to create a custom report item run-time component.</span></span>  
  
 [<span data-ttu-id="2a6fd-122">Erstellen einer Entwurfszeitkomponente für ein benutzerdefiniertes Berichtselement</span><span class="sxs-lookup"><span data-stu-id="2a6fd-122">Creating a Custom Report Item Design-Time Component</span></span>](creating-a-custom-report-item-design-time-component.md)  
 <span data-ttu-id="2a6fd-123">Beschreibt, wie eine benutzerdefinierte Entwurfszeitkomponente für ein Berichtselement erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="2a6fd-123">Describes how to create a custom report item design-time component.</span></span>  
  
 [<span data-ttu-id="2a6fd-124">Vorgehensweise: Bereitstellen eines benutzerdefinierten Berichtselements</span><span class="sxs-lookup"><span data-stu-id="2a6fd-124">How to: Deploy a Custom Report Item</span></span>](how-to-deploy-a-custom-report-item.md)  
 <span data-ttu-id="2a6fd-125">Beschreibt, wie ein benutzerdefiniertes Berichtselement angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="2a6fd-125">Describes how to deploy a custom report item.</span></span>  
  
 [<span data-ttu-id="2a6fd-126">Klassenbibliotheken für ein benutzerdefiniertes Berichtselement</span><span class="sxs-lookup"><span data-stu-id="2a6fd-126">Custom Report Item Class Libraries</span></span>](custom-report-item-class-libraries.md)  
 <span data-ttu-id="2a6fd-127">Beschreibt die Infrastrukturklassen benutzerdefinierter Berichtselemente und die verwalteten Wrapperklassen im `Microsoft.ReportDesigner`-Namespace.</span><span class="sxs-lookup"><span data-stu-id="2a6fd-127">Describes the custom report item infrastructure classes and managed wrapper classes in the `Microsoft.ReportDesigner` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a6fd-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2a6fd-128">See Also</span></span>  
 [<span data-ttu-id="2a6fd-129">Technische Referenz (SSRS)</span><span class="sxs-lookup"><span data-stu-id="2a6fd-129">Technical Reference &#40;SSRS&#41;</span></span>](../technical-reference-ssrs.md)  
  
  
