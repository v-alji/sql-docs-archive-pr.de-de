---
title: 'Schritt 4: Hinzufügen eines Datenflusstasks zum Paket | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 96af3073-8f11-4444-b934-fe8613a2d084
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4fda1de99e9fcaa683f9063e2feb1b71886a5cd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618133"
---
# <a name="step-4-adding-a-data-flow-task-to-the-package"></a><span data-ttu-id="455af-102">Schritt 4: Hinzufügen eines Datenflusstasks zum Paket</span><span class="sxs-lookup"><span data-stu-id="455af-102">Step 4: Adding a Data Flow Task to the Package</span></span>
  <span data-ttu-id="455af-103">Nach dem Erstellen des Verbindungs-Managers für die Quell- und Zieldaten besteht die nächste Aufgabe im Hinzufügen eines Datenflusstasks zu Ihrem Paket.</span><span class="sxs-lookup"><span data-stu-id="455af-103">After you have created the connection managers for the source and destination data, the next task is to add a Data Flow task to your package.</span></span> <span data-ttu-id="455af-104">Der Datenflusstask kapselt die Datenfluss-Engine, von der Daten zwischen Quellen und Zielen verschoben werden, und bietet die Funktionalität für das Transformieren, das Cleanup und das Ändern von Daten beim Verschieben.</span><span class="sxs-lookup"><span data-stu-id="455af-104">The Data Flow task encapsulates the data flow engine that moves data between sources and destinations, and provides the functionality for transforming, cleaning, and modifying data as it is moved.</span></span> <span data-ttu-id="455af-105">Im Datenflusstask wird der Hauptteil eines ETL-Prozesses (Extract, Transform, Load - Extrahieren, Transformieren, Laden) durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="455af-105">The Data Flow task is where most of the work of an extract, transform, and load (ETL) process occurs.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]<span data-ttu-id="455af-106">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]trennt den Datenfluss von der Ablauf Steuerung.</span><span class="sxs-lookup"><span data-stu-id="455af-106">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] separates data flow from control flow.</span></span>  
  
### <a name="to-add-a-data-flow-task"></a><span data-ttu-id="455af-107">So fügen Sie einen Datenflusstask hinzu</span><span class="sxs-lookup"><span data-stu-id="455af-107">To add a Data Flow task</span></span>  
  
1.  <span data-ttu-id="455af-108">Klicken Sie auf die Registerkarte **Ablaufsteuerung** .</span><span class="sxs-lookup"><span data-stu-id="455af-108">Click the **Control Flow** tab.</span></span>  
  
2.  <span data-ttu-id="455af-109">Erweitern Sie in der **SSIS-Toolbox**die Option **Favoriten**, und ziehen Sie anschließend einen **Datenflusstask** auf die Entwurfsoberfläche der Registerkarte **Ablaufsteuerung** .</span><span class="sxs-lookup"><span data-stu-id="455af-109">In the **SSIS Toolbox**, expand **Favorites**, and drag a **Data Flow Task** onto the design surfaceof the **Control Flow** tab.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="455af-110">Wenn die SSIS-Toolbox nicht verfügbar ist, wählen Sie im Hauptmenü SSIS und dann SSIS-Toolbox aus, um die SSIS-Toolbox anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="455af-110">If the SSIS Toolbox isn't available, on the main menu select SSIS then SSIS Toolbox to display the SSIS Toolbox.</span></span>  
  
3.  <span data-ttu-id="455af-111">Klicken Sie auf der Entwurfs Oberfläche **Ablauf Steuerung** mit der rechten Maustaste auf den neu hinzugefügten **Datenfluss Task**, klicken Sie auf **Umbenennen**, und ändern Sie den Namen in `Extract Sample Currency Data` .</span><span class="sxs-lookup"><span data-stu-id="455af-111">On the **Control Flow** design surface, right-click the newly added **Data Flow Task**, click **Rename**, and change the name to `Extract Sample Currency Data`.</span></span>  
  
     <span data-ttu-id="455af-112">Es empfiehlt sich, eindeutige Namen für alle Komponenten bereitzustellen, die Sie einer Entwurfsoberfläche hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="455af-112">It is good practice to provide unique names to all components that you add to a design surface.</span></span> <span data-ttu-id="455af-113">Aus Gründen der Benutzer- und Wartungsfreundlichkeit sollten die Namen die Funktion beschreiben, die jede Komponente ausführt.</span><span class="sxs-lookup"><span data-stu-id="455af-113">For ease of use and maintainability, the names should describe the function that each component performs.</span></span> <span data-ttu-id="455af-114">Das Befolgen dieser Namensrichtlinien ermöglicht die Selbstdokumentierung Ihrer [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Pakete.</span><span class="sxs-lookup"><span data-stu-id="455af-114">Following these naming guidelines allows your [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages to be self-documenting.</span></span> <span data-ttu-id="455af-115">Eine andere Möglichkeit zur Dokumentation Ihrer Pakete besteht im Verwenden von Anmerkungen.</span><span class="sxs-lookup"><span data-stu-id="455af-115">Another way to document your packages is by using annotations.</span></span> <span data-ttu-id="455af-116">Weitere Informationen zum Verwenden von Anmerkungen finden Sie unter [Verwenden von Anmerkungen in Paketen](use-annotations-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="455af-116">For more information about annotations, see [Use Annotations in Packages](use-annotations-in-packages.md).</span></span>  
  
4.  <span data-ttu-id="455af-117">Klicken Sie mit der rechten Maustaste auf den Datenfluss Task, klicken Sie auf **Eigenschaften**, und überprüfen Sie im Eigenschaftenfenster, ob die- `LocaleID` Eigenschaft auf **Englisch (USA)** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="455af-117">Right-click the Data Flow task, click **Properties**, and in the Properties window, verify that the `LocaleID` property is set to **English (United States)**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="455af-118">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="455af-118">Next Task in Lesson</span></span>  
 [<span data-ttu-id="455af-119">Schritt 5: Hinzufügen und Konfigurieren der Flatfilequelle</span><span class="sxs-lookup"><span data-stu-id="455af-119">Step 5: Adding and Configuring the Flat File Source</span></span>](lesson-1-5-adding-and-configuring-the-flat-file-source.md)  
  
## <a name="see-also"></a><span data-ttu-id="455af-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="455af-120">See Also</span></span>  
 [<span data-ttu-id="455af-121">Datenflusstask</span><span class="sxs-lookup"><span data-stu-id="455af-121">Data Flow Task</span></span>](control-flow/data-flow-task.md)  
  
  
