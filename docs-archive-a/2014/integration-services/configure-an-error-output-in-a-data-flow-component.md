---
title: Konfigurieren einer Fehlerausgabe in einer Datenfluss Komponente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- errors [Integration Services], data flow components
- components [Integration Services], data flow
- error outputs [Integration Services]
ms.assetid: 53d7eeea-927d-4b45-8ea9-084e65ad5390
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ebd44383e27daa465576bb056a67f6dacad87b0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724877"
---
# <a name="configure-an-error-output-in-a-data-flow-component"></a><span data-ttu-id="a4a6d-102">Konfigurieren einer Fehlerausgabe in einer Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="a4a6d-102">Configure an Error Output in a Data Flow Component</span></span>
  <span data-ttu-id="a4a6d-103">Viele Datenflusskomponenten unterstützen Fehlerausgaben, und [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer bietet je nach Komponente unterschiedliche Möglichkeiten für die Konfiguration einer Fehlerausgabe.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-103">Many data flow components support error outputs, and depending on the component, [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer provides different ways to configure an error output.</span></span> <span data-ttu-id="a4a6d-104">Sie können nicht nur eine Fehlerausgabe, sondern auch die Spalten einer Fehlerausgabe konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-104">In addition to configuring an error output, you can also configure the columns of an error output.</span></span> <span data-ttu-id="a4a6d-105">Dies schließt das Konfigurieren der von der Komponente hinzugefügten Spalten **ErrorCode** und **ErrorColumn** ein.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-105">This includes configuring the **ErrorCode** and **ErrorColumn** columns that are added by the component.</span></span>  
  
## <a name="configuring-an-error-output"></a><span data-ttu-id="a4a6d-106">Konfigurieren einer Fehlerausgabe</span><span class="sxs-lookup"><span data-stu-id="a4a6d-106">Configuring an Error Output</span></span>  
 <span data-ttu-id="a4a6d-107">Zum Konfigurieren einer Fehlerausgabe stehen Ihnen zwei Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="a4a6d-107">To configure an error output, you have two options:</span></span>  
  
-   <span data-ttu-id="a4a6d-108">Verwenden des Dialogfelds **Fehlerausgabe konfigurieren** .</span><span class="sxs-lookup"><span data-stu-id="a4a6d-108">Use the **Configure Error Output** dialog box.</span></span> <span data-ttu-id="a4a6d-109">Sie können dieses Dialogfeld zum Konfigurieren einer Fehlerausgabe für jede Datenflusskomponente verwenden, die eine Fehlerausgabe unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-109">You can use this dialog box to configure an error output on any data flow component that supports an error output.</span></span>  
  
-   <span data-ttu-id="a4a6d-110">Verwenden des Editordialogfelds für die Komponente.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-110">Use the editor dialog box for the component.</span></span> <span data-ttu-id="a4a6d-111">Die Fehlerausgaben können bei einigen Komponenten direkt in ihrem Editordialogfeld konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-111">Some components let you configure error outputs directly from their editor dialog box.</span></span> <span data-ttu-id="a4a6d-112">Es ist jedoch nicht möglich, Fehlerausgaben im Editordialogfeld für die ADO NET-Quelle, die Transformation für das Importieren von Spalten, die Transformation für OLE DB-Befehl oder das [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact-Ziel zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-112">However, you cannot configure error outputs from the editor dialog box for the ADO NET source, the Import Column transformation, the OLE DB Command transformation, or the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Compact destination.</span></span>  
  
 <span data-ttu-id="a4a6d-113">Im Folgenden wird die Verwendung dieser Dialogfelder zum Konfigurieren von Fehlerausgaben beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-113">The following procedures describe how to use these dialog boxes to configure error outputs.</span></span>  
  
#### <a name="to-configure-an-error-output-using-the-configure-error-output-dialog-box"></a><span data-ttu-id="a4a6d-114">So konfigurieren Sie eine Fehlerausgabe mit dem Dialogfeld "Fehlerausgabe konfigurieren"</span><span class="sxs-lookup"><span data-stu-id="a4a6d-114">To configure an error output using the Configure Error Output dialog box</span></span>  
  
1.  <span data-ttu-id="a4a6d-115">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-115">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="a4a6d-116">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-116">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="a4a6d-117">Klicken Sie im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer auf die Registerkarte **Datenfluss** .</span><span class="sxs-lookup"><span data-stu-id="a4a6d-117">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Data Flow** tab.</span></span>  
  
4.  <span data-ttu-id="a4a6d-118">Ziehen Sie die Fehlerausgabe, dargestellt durch einen roten Pfeil, von der Komponente, die die Fehlerquelle darstellt, zu einer anderen Komponente im Datenfluss.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-118">Drag the error output, represented by the red arrow, from the component that is the source of the errors to another component in the data flow.</span></span>  
  
5.  <span data-ttu-id="a4a6d-119">Wählen Sie im Dialogfeld **Fehlerausgabe konfigurieren** eine Aktion in den Spalten **Fehler** und **Abschneiden** für jede Spalte der Komponenteneingabe.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-119">In the **Configure Error Output** dialog box, select an action in the **Error** and **Truncation** columns for each column in the component input.</span></span>  
  
6.  <span data-ttu-id="a4a6d-120">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern**, um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-120">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
#### <a name="to-add-an-error-output-using-the-editor-dialog-box-for-the-component"></a><span data-ttu-id="a4a6d-121">So fügen Sie eine Fehlerausgabe mit dem Editordialogfeld für die Komponente hinzu</span><span class="sxs-lookup"><span data-stu-id="a4a6d-121">To add an error output using the editor dialog box for the component</span></span>  
  
1.  <span data-ttu-id="a4a6d-122">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-122">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="a4a6d-123">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-123">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="a4a6d-124">Klicken Sie im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer auf die Registerkarte **Datenfluss** .</span><span class="sxs-lookup"><span data-stu-id="a4a6d-124">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Data Flow** tab.</span></span>  
  
4.  <span data-ttu-id="a4a6d-125">Doppelklicken Sie auf die Datenflusskomponenten, für die Sie eine Fehlerausgabe konfigurieren möchten, und führen Sie je nach Komponente einen der folgenden Schritte durch:</span><span class="sxs-lookup"><span data-stu-id="a4a6d-125">Double-click the data flow components in which you want to configure an error output and, depending on the component, do one of the following steps:</span></span>  
  
    -   <span data-ttu-id="a4a6d-126">Klicken Sie auf **Fehlerausgabe konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-126">Click **Configure Error Output**.</span></span>  
  
    -   <span data-ttu-id="a4a6d-127">Klicken Sie auf **Fehlerausgabe**.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-127">Click **Error Output**.</span></span>  
  
5.  <span data-ttu-id="a4a6d-128">Legen Sie für jede Spalte die Option **Fehler** fest.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-128">Set the **Error** option for each column.</span></span>  
  
6.  <span data-ttu-id="a4a6d-129">Legen Sie für jede Spalte die Option **Abschneiden** fest.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-129">Set the **Truncation** option for each column.</span></span>  
  
7.  <span data-ttu-id="a4a6d-130">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-130">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="a4a6d-131">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern**, um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-131">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="configuring-error-output-columns"></a><span data-ttu-id="a4a6d-132">Konfigurieren von Fehlerausgabespalten</span><span class="sxs-lookup"><span data-stu-id="a4a6d-132">Configuring Error Output Columns</span></span>  
 <span data-ttu-id="a4a6d-133">Verwenden Sie die Registerkarte **Eingabe- und Ausgabeeigenschaften** im Dialogfeld **Erweiterter Editor** zum Konfigurieren von Fehlerausgabespalten.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-133">To configure the error output columns, you have to use the **Input and Output Properties** tab of the **Advanced Editor** dialog box.</span></span>  
  
#### <a name="to-configure-error-output-columns"></a><span data-ttu-id="a4a6d-134">So konfigurieren Sie Fehlerausgabespalten</span><span class="sxs-lookup"><span data-stu-id="a4a6d-134">To configure error output columns</span></span>  
  
1.  <span data-ttu-id="a4a6d-135">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-135">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="a4a6d-136">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-136">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="a4a6d-137">Klicken Sie im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer auf die Registerkarte **Datenfluss** .</span><span class="sxs-lookup"><span data-stu-id="a4a6d-137">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Data Flow** tab.</span></span>  
  
4.  <span data-ttu-id="a4a6d-138">Klicken Sie mit der rechten Maustaste auf die Komponente, deren Fehlerausgabespalten Sie konfigurieren möchten, und klicken Sie auf **Erweiterten Editor anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-138">Right-click the component whose error output columns you want to configure and click **Show Advanced Editor**.</span></span>  
  
5.  <span data-ttu-id="a4a6d-139">Klicken Sie auf die Registerkarte **Eingabe- und Ausgabeeigenschaften**, und erweitern Sie **\<component name>-Fehlerausgabe** und dann **Ausgabespalten**.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-139">Click the **Input and Output Properties** tab and expand **\<component name> Error Output** and then expand **Output Columns**.</span></span>  
  
6.  <span data-ttu-id="a4a6d-140">Klicken Sie auf eine Spalte, und aktualisieren Sie ihre Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-140">Click a column and update its properties.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a4a6d-141">Die Liste mit den Spalten enthält die Spalten in der Komponenteneingabe, die durch vorherige Fehlerausgaben hinzugefügten Spalten **ErrorCode** und **ErrorColumn** sowie die von dieser Komponente hinzugefügten Spalten **ErrorCode** und **ErrorColumn** .</span><span class="sxs-lookup"><span data-stu-id="a4a6d-141">The list of columns includes the columns in the component input, the **ErrorCode** and **ErrorColumn** columns added by previous error outputs, and the **ErrorCode** and **ErrorColumn** columns added by this component.</span></span>  
  
7.  <span data-ttu-id="a4a6d-142">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-142">Click **OK.**</span></span>  
  
8.  <span data-ttu-id="a4a6d-143">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern**, um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a4a6d-143">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4a6d-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a4a6d-144">See Also</span></span>  
 [<span data-ttu-id="a4a6d-145">Fehlerbehandlung in Daten</span><span class="sxs-lookup"><span data-stu-id="a4a6d-145">Error Handling in Data</span></span>](data-flow/error-handling-in-data.md)  
  
  
