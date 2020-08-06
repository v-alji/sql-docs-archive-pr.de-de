---
title: Anzeigen des XML-Codes für ein Analysis Services-Projekt (SSDT) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- projects [Analysis Services], viewing XML
ms.assetid: dd1a4bc6-57b5-47df-8619-09f921aa6351
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1c320145be2073c741498bed0f10732ac8d528e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724237"
---
# <a name="view-the-xml-for-an-analysis-services-project-ssdt"></a><span data-ttu-id="ec965-102">Anzeigen des XML für ein Analysis Services-Projekt (SSDT)</span><span class="sxs-lookup"><span data-stu-id="ec965-102">View the XML for an Analysis Services Project (SSDT)</span></span>
  <span data-ttu-id="ec965-103">Wenn Sie eine [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank im Projektmodus verwenden, wird in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] eine XML-Definition für jedes im Projektordner enthaltene Objekt erstellt.</span><span class="sxs-lookup"><span data-stu-id="ec965-103">When you are working with an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in project mode, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] creates an XML definition for each object within the project folder.</span></span> <span data-ttu-id="ec965-104">Sie können die Inhalte der XML-Datei für jedes Objekt innerhalb von [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ec965-104">You can view the contents of the XML file for each object within [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="ec965-105">Die XML-Datei kann auch direkt bearbeitet werden, jedoch wird in den meisten Situationen davon abgeraten, da Sie Änderungen vornehmen können, die die Unlesbarkeit der XML-Datei in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]bewirken.</span><span class="sxs-lookup"><span data-stu-id="ec965-105">You can also edit the XML file directly; however, this is not recommended in most circumstances as you may make changes that make the XML unreadable by [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ec965-106">Sie können den XML-Code nicht für ein Gesamtprojekt, sondern nur für die jeweiligen Objekte anzeigen, da für jedes Objekt eine eigene Datei vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ec965-106">You cannot view the xml code for an entire project, but rather you view the code for each object because a separate file exists for each object.</span></span> <span data-ttu-id="ec965-107">Die einzige Möglichkeit, den Code für ein gesamtes Projekt anzuzeigen, besteht darin, das Projekt zu erstellen und den ASSL-Code in der \<project name> . asdatabase-Datei anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ec965-107">The only way to view the code for an entire project is to build the project and view the ASSL code in the \<project name>.asdatabase file.</span></span>  
  
### <a name="to-view-the-xml-code-for-an-object"></a><span data-ttu-id="ec965-108">So zeigen Sie den XML-Code für ein Objekt an</span><span class="sxs-lookup"><span data-stu-id="ec965-108">To view the XML code for an object</span></span>  
  
1.  <span data-ttu-id="ec965-109">Öffnen Sie das [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projekt in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ec965-109">Open the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="ec965-110">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Objekt, und klicken Sie dann auf **Code anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="ec965-110">Right-click the object in Solution Explorer and then click **View Code**.</span></span>  
  
     <span data-ttu-id="ec965-111">Der XML-Code des Objekts wird in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ec965-111">The XML code for the object appears in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec965-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ec965-112">See Also</span></span>  
 [<span data-ttu-id="ec965-113">Erstellen von Analysis Services-Projekten &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="ec965-113">Build Analysis Services Projects &#40;SSDT&#41;</span></span>](build-analysis-services-projects-ssdt.md)  
  
  
