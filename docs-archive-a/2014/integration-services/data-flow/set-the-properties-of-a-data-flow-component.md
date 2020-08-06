---
title: Festlegen der Eigenschaften einer Datenflusskomponente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- components [Integration Services], properties
ms.assetid: 73000ef6-52a2-4dec-8320-0e79acf0c2c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1fd045ba076eed2d65d801015b881a477976f5d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621116"
---
# <a name="set-the-properties-of-a-data-flow-component"></a><span data-ttu-id="9243c-102">Festlegen der Eigenschaften einer Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="9243c-102">Set the Properties of a Data Flow Component</span></span>
  <span data-ttu-id="9243c-103">Die Eigenschaften von Datenflusskomponenten, z. B. Quellen, Ziele und Transformationen, können Sie mithilfe eine der folgenden Funktionen festlegen:</span><span class="sxs-lookup"><span data-stu-id="9243c-103">To set the properties of data flow components, which include sources, destinations, and transformations, use one of the following features:</span></span>  
  
-   <span data-ttu-id="9243c-104">Die von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] bereitgestellten Komponenten-Editoren.</span><span class="sxs-lookup"><span data-stu-id="9243c-104">The component editors that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides.</span></span> <span data-ttu-id="9243c-105">Diese Editoren schließen nur die benutzerdefinierten Eigenschaften jeder Datenflusskomponente ein.</span><span class="sxs-lookup"><span data-stu-id="9243c-105">These editors include only the custom properties of each data flow component.</span></span>  
  
-   <span data-ttu-id="9243c-106">Im Fenster **Eigenschaften** werden die benutzerdefinierten Eigenschaften auf Komponentenebene jedes Elements sowie die allen Datenflusselementen gemeinsamen Eigenschaften aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="9243c-106">The **Properties** window lists the component-level custom properties of each element, as well as the properties common to all data flow elements.</span></span>  
  
-   <span data-ttu-id="9243c-107">Das Dialogfeld **Erweiterter Editor** ermöglicht den Zugriff auf benutzerdefinierte Eigenschaften für jede Komponente.</span><span class="sxs-lookup"><span data-stu-id="9243c-107">The **Advanced Editor** dialog box provides access to custom properties for each component.</span></span> <span data-ttu-id="9243c-108">Das Dialogfeld **Erweiterter Editor** ermöglicht außerdem den Zugriff auf benutzerdefinierte Eigenschaften für die einzelnen Komponenten sowie auf die für alle Datenflusskomponenten gemeinsamen Eigenschaften, die Eigenschaften von Eingaben, Ausgaben, Fehlerausgaben, Spalten und externen Spalten.</span><span class="sxs-lookup"><span data-stu-id="9243c-108">The **Advanced Editor** dialog box also provides access to the properties common to all data flow components-the properties of inputs, outputs, error outputs, columns, and external columns.</span></span>  
  
### <a name="to-set-the-properties-of-a-data-flow-component-by-using-a-component-editor"></a><span data-ttu-id="9243c-109">So legen Sie die Eigenschaften einer Datenflusskomponente mithilfe eines Komponenten-Editors fest</span><span class="sxs-lookup"><span data-stu-id="9243c-109">To set the properties of a data flow component by using a component editor</span></span>  
  
1.  <span data-ttu-id="9243c-110">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="9243c-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="9243c-111">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9243c-111">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="9243c-112">Klicken Sie auf die Registerkarte **Ablaufsteuerung** , und doppelklicken Sie anschließend auf den Datenflusstask, der den Datenfluss mit der Komponente enthält, deren Eigenschaften Sie anzeigen und ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="9243c-112">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the data flow with the component whose properties you want to view and modify.</span></span>  
  
4.  <span data-ttu-id="9243c-113">Doppelklicken Sie auf die Datenflusskomponente.</span><span class="sxs-lookup"><span data-stu-id="9243c-113">Double-click the data flow component.</span></span>  
  
5.  <span data-ttu-id="9243c-114">Zeigen Sie im Komponenten-Editor die Eigenschaftswerte an, oder ändern Sie diese, und schließen Sie dann den Editor.</span><span class="sxs-lookup"><span data-stu-id="9243c-114">In the component editor, view or modify the property values, and then close the editor.</span></span>  
  
6.  <span data-ttu-id="9243c-115">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern**, um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9243c-115">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
### <a name="to-set-the-properties-of-a-data-flow-component-by-using-the-properties-window"></a><span data-ttu-id="9243c-116">So legen Sie die Eigenschaften einer Datenflusskomponente mithilfe des Eigenschaftenfensters fest</span><span class="sxs-lookup"><span data-stu-id="9243c-116">To set the properties of a data flow component by using the Properties window</span></span>  
  
1.  <span data-ttu-id="9243c-117">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="9243c-117">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="9243c-118">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9243c-118">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="9243c-119">Klicken Sie auf die Registerkarte **Ablaufsteuerung** , und doppelklicken Sie anschließend auf den Datenflusstask, der die Komponente enthält, deren Eigenschaften Sie anzeigen und ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="9243c-119">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the component whose properties you want to view and modify.</span></span>  
  
4.  <span data-ttu-id="9243c-120">Klicken Sie mit der rechten Maustaste auf die Datenflusskomponente, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="9243c-120">Right-click the data flow component, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="9243c-121">Zeigen Sie die Eigenschaftswerte an, oder ändern Sie diese, und schließen Sie dann das Fenster **Eigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="9243c-121">View or modify the property values, and then close the **Properties** window.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9243c-122">Viele Eigenschaften sind schreibgeschützt und können nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="9243c-122">Many properties are read-only, and cannot be modified.</span></span>  
  
6.  <span data-ttu-id="9243c-123">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern**, um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9243c-123">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
### <a name="to-set-the-properties-of-a-data-flow-component-by-using-the-advanced-editor"></a><span data-ttu-id="9243c-124">So legen Sie die Eigenschaften einer Datenflusskomponente mithilfe des erweiterten Editors fest</span><span class="sxs-lookup"><span data-stu-id="9243c-124">To set the properties of a data flow component by using the Advanced Editor</span></span>  
  
1.  <span data-ttu-id="9243c-125">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="9243c-125">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="9243c-126">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9243c-126">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="9243c-127">Klicken Sie auf die Registerkarte **Ablaufsteuerung** , und doppelklicken Sie anschließend auf den Datenflusstask, der die Komponente enthält, die Sie anzeigen oder ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="9243c-127">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the component you want to view or modify.</span></span>  
  
4.  <span data-ttu-id="9243c-128">Klicken Sie im Datenfluss-Designer mit der rechten Maustaste auf die Datenflusskomponente, und klicken Sie anschließend auf **Erweiterten Editor anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="9243c-128">In the data flow designer, right-click the data flow component, and then click **Show Advanced Editor**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9243c-129">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]kann **Erweiterter Editor**nicht für Datenflusskomponenten verwendet werden, die mehrere Eingaben unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9243c-129">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], data flow components that support multiple inputs cannot use the **Advanced Editor**.</span></span>  
  
5.  <span data-ttu-id="9243c-130">Führen Sie im Dialogfeld **Erweiterter Editor** einen beliebigen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="9243c-130">In the **Advanced Editor** dialog box, do any of the following steps:</span></span>  
  
    -   <span data-ttu-id="9243c-131">Klicken Sie auf die Registerkarte **Verbindungs-Manager** , um die von der Komponente verwendete Verbindung anzuzeigen und anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9243c-131">To view and specify the connection that the component uses, click the **Connection Managers** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="9243c-132">Die Registerkarte **Verbindungs-Manager** ist nur für Datenflusskomponenten verfügbar, die Verbindungs-Manager zum Herstellen einer Verbindung mit Datenquellen wie z.B. Dateien und Datenbanken verwenden.</span><span class="sxs-lookup"><span data-stu-id="9243c-132">The **Connection Managers** tab is available only to data flow components that use connection managers to connect to data sources such as files and databases</span></span>  
  
    -   <span data-ttu-id="9243c-133">Klicken Sie auf die Registerkarte **Komponenteneigenschaften** , um die Eigenschaften auf Komponentenebene anzuzeigen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9243c-133">To view and modify component-level properties, click the **Component Properties** tab.</span></span>  
  
    -   <span data-ttu-id="9243c-134">Klicken Sie auf die Registerkarte **Spaltenzuordnungen** , um Zuordnungen zwischen externen Spalten und der verfügbaren Ausgabe anzuzeigen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9243c-134">To view and modify mappings between external columns and the available output, click the **Column Mappings** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="9243c-135">Die Registerkarte **Spaltenzuordnungen** ist nur verfügbar, wenn Sie Quellen oder Ziele anzeigen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="9243c-135">The **Column Mappings** tab is available only when viewing or editing sources or destinations.</span></span>  
  
    -   <span data-ttu-id="9243c-136">Klicken Sie auf die Registerkarte **Eingabespalten** , um eine Liste der verfügbaren Eingabespalten anzuzeigen und die Namen von Ausgabespalten zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="9243c-136">To view a list of the available input columns and to update the names of output columns, click the **Input Columns** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="9243c-137">Die Registerkarte Eingabespalten ist nur verfügbar, wenn Sie mit Transformationen oder Zielen arbeiten.</span><span class="sxs-lookup"><span data-stu-id="9243c-137">The Input Columns tab is available only when working with transformations or destinations.</span></span> <span data-ttu-id="9243c-138">Weitere Informationen finden Sie unter [Integration Services Transformations](transformations/integration-services-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="9243c-138">For more information, see [Integration Services Transformations](transformations/integration-services-transformations.md).</span></span>  
  
    -   <span data-ttu-id="9243c-139">Klicken Sie auf die Registerkarte **Eingabe- und Ausgabeeigenschaften** , um die Eigenschaften von Eingaben, Ausgaben und Fehlerausgaben sowie die Eigenschaften der enthaltenen Spalten anzuzeigen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9243c-139">To view and modify the properties of inputs, outputs, and error outputs, and the properties of the columns they contain, click the **Input and Output Properties** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="9243c-140">Quellen weisen keine Eingaben auf.</span><span class="sxs-lookup"><span data-stu-id="9243c-140">Sources have no inputs.</span></span> <span data-ttu-id="9243c-141">Ziele haben keine Ausgaben, mit Ausnahme einer optionalen Fehlerausgabe.</span><span class="sxs-lookup"><span data-stu-id="9243c-141">Destinations have no outputs, except for an optional error output.</span></span>  
  
6.  <span data-ttu-id="9243c-142">Zeigen Sie die Eigenschaftswerte an, oder ändern Sie diese.</span><span class="sxs-lookup"><span data-stu-id="9243c-142">View or modify the property values.</span></span>  
  
7.  <span data-ttu-id="9243c-143">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9243c-143">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="9243c-144">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern**, um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9243c-144">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9243c-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9243c-145">See Also</span></span>  
 [<span data-ttu-id="9243c-146">SQL Server Integration Services-Transformationen</span><span class="sxs-lookup"><span data-stu-id="9243c-146">Integration Services Transformations</span></span>](transformations/integration-services-transformations.md)  
  
  
