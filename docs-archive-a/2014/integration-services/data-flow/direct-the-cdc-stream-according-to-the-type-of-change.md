---
title: Weiterleiten des CDC-Datenstroms gemäß Änderungstyp | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3afa531e-f425-40a4-a1bf-1c3e1727287e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4a9b4e0c6a196669e4cedafcecf0477b228f3001
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615491"
---
# <a name="direct-the-cdc-stream-according-to-the-type-of-change"></a><span data-ttu-id="b4d6d-102">Weiterleiten des CDC-Datenstroms gemäß Änderungstyp</span><span class="sxs-lookup"><span data-stu-id="b4d6d-102">Direct the CDC Stream According to the Type of Change</span></span>
  <span data-ttu-id="b4d6d-103">Um eine CDC-Splittertransformation hinzuzufügen und zu konfigurieren, muss das Paket mindestens einen Datenflusstask und eine CDC-Quelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="b4d6d-103">To add and configure a CDC splitter Transformation, the package must contain at least one Data Flow task and a CDC source.</span></span>  
  
 <span data-ttu-id="b4d6d-104">Für die dem Paket hinzugefügte CDC-Quelle muss ein NetCDC-Verarbeitungsmodus ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="b4d6d-104">The CDC source added to the package must have a NetCDC processing mode selected.</span></span> <span data-ttu-id="b4d6d-105">Weitere Informationen zum Auswählen von Verarbeitungsmodi finden Sie unter [Quellen-Editor für CDC &#40;Seite Verbindungs-Manager&#41;](../cdc-source-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="b4d6d-105">For more information on selecting processing modes, see [CDC Source Editor &#40;Connection Manager Page&#41;](../cdc-source-editor-connection-manager-page.md).</span></span>  
  
### <a name="to-direct-the-cdc-stream-according-to-the-type-of-change"></a><span data-ttu-id="b4d6d-106">So leiten Sie den CDC-Datenstrom gemäß Änderungstyp weiter</span><span class="sxs-lookup"><span data-stu-id="b4d6d-106">To direct the CDC stream according to the type of change</span></span>  
  
1.  <span data-ttu-id="b4d6d-107">Öffnen Sie in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] das [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="b4d6d-107">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="b4d6d-108">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b4d6d-108">In the Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="b4d6d-109">Klicken Sie auf die Registerkarte **Datenfluss** , und ziehen Sie den CDC-Splitter dann aus der **Toolbox**auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="b4d6d-109">Click the **Data Flow** tab, and then from the **Toolbox**, drag the CDC splitter to the design surface.</span></span>  
  
4.  <span data-ttu-id="b4d6d-110">Verbinden Sie die CDC-Quelle, die im Paket enthalten ist, mit dem CDC-Splitter.</span><span class="sxs-lookup"><span data-stu-id="b4d6d-110">Connect the CDC source that is included in the package to the CDC Splitter.</span></span>  
  
5.  <span data-ttu-id="b4d6d-111">Verbinden Sie den CDC-Splitter mit einem oder mehreren Zielen.</span><span class="sxs-lookup"><span data-stu-id="b4d6d-111">Connect the CDC splitter to one or more destinations.</span></span> <span data-ttu-id="b4d6d-112">Sie können Verbindungen für bis zu drei verschiedene Ausgaben herstellen.</span><span class="sxs-lookup"><span data-stu-id="b4d6d-112">You can connect up to three different outputs.</span></span>  
  
6.  <span data-ttu-id="b4d6d-113">Wählen Sie eine der folgenden Ausgaben aus:</span><span class="sxs-lookup"><span data-stu-id="b4d6d-113">Select one of the following outputs:</span></span>  
  
    -   <span data-ttu-id="b4d6d-114">Ausgabe löschen: Die Ausgabe, an die DELETE-Änderungszeilen geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="b4d6d-114">Delete output: The output where DELETE change rows are directed.</span></span>  
  
    -   <span data-ttu-id="b4d6d-115">Ausgabe einfügen: Die Ausgabe, an die INSERT-Änderungszeilen geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="b4d6d-115">Insert output: The output where INSERT change rows are directed.</span></span>  
  
    -   <span data-ttu-id="b4d6d-116">Ausgabe aktualisieren: Die Ausgabe, an die UPDATE-Änderungszeilen (vor/nach Update) und Merge-Änderungszeilen geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="b4d6d-116">Update output: The output where before/after UPDATE change rows and Merge change rows are directed.</span></span>  
  
7.  <span data-ttu-id="b4d6d-117">Optional können Sie die erweiterten Eigenschaften mithilfe des Dialogfelds **Erweiterter Editor** konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b4d6d-117">Optionally, you can configure the advanced properties using the **Advanced Editor** dialog box.</span></span>  
  
     <span data-ttu-id="b4d6d-118">Das Dialogfeld **Erweiterter Editor** enthält die Eigenschaften, die programmgesteuert festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="b4d6d-118">The **Advanced Editor** dialog box contains the properties that can be set programmatically.</span></span>  
  
     <span data-ttu-id="b4d6d-119">So öffnen Sie das Dialogfeld **Erweiterter Editor** :</span><span class="sxs-lookup"><span data-stu-id="b4d6d-119">To open the **Advanced Editor** dialog box:</span></span>  
  
    -   <span data-ttu-id="b4d6d-120">Klicken Sie auf dem Bildschirm **Datenfluss** des [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] -Projekts mit der rechten Maustaste auf den CDC-Splitter, und wählen Sie **Erweiterten Editor anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="b4d6d-120">In the **Data Flow** screen of your [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project, right click the CDC splitter and select **Show Advanced Editor**.</span></span>  
  
     <span data-ttu-id="b4d6d-121">Weitere Informationen zur Verwendung des CDC-Splitters finden Sie unter CDC-Komponenten für Microsoft SQL Server Integration Services.</span><span class="sxs-lookup"><span data-stu-id="b4d6d-121">For more information about using the CDC splitter see CDC Components for Microsoft SQL Server Integration Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4d6d-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b4d6d-122">See Also</span></span>  
 [<span data-ttu-id="b4d6d-123">CDC-Splitter</span><span class="sxs-lookup"><span data-stu-id="b4d6d-123">CDC Splitter</span></span>](cdc-splitter.md)  
  
  
