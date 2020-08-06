---
title: 'Schritt 3: Hinzufügen von Fehlerflussumleitungen | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5683a45d-9e73-4cd5-83ca-fae8b26b488c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ceaea310cba05a940f310c01b52d5f912a53bea8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617176"
---
# <a name="step-3-adding-error-flow-redirection"></a><span data-ttu-id="d7014-102">Schritt 3: Hinzufügen der Fehlerflussumleitung</span><span class="sxs-lookup"><span data-stu-id="d7014-102">Step 3: Adding Error Flow Redirection</span></span>
  <span data-ttu-id="d7014-103">Wie in der vorhergehenden Aufgabe gezeigt, kann von der Lookup Currency Key-Transformation keine Übereinstimmung generiert werden, wenn die Transformation versucht, die beschädigte Beispielflatfile, die einen Fehler produziert hat, zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d7014-103">As demonstrated in the previous task, the Lookup Currency Key transformation cannot generate a match when the transformation tries to process the corrupted sample flat file, which produced an error.</span></span> <span data-ttu-id="d7014-104">Da die Transformation die Standardeinstellungen für die Fehlerausgabe verwendet, führt jeder Fehler dazu, dass die Transformation fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="d7014-104">Because the transformation uses the default settings for error output, any error causes the transformation to fail.</span></span> <span data-ttu-id="d7014-105">Wenn die Transformation fehlschlägt, schlägt auch der Rest des Pakets fehl.</span><span class="sxs-lookup"><span data-stu-id="d7014-105">When the transformation fails, the rest of the package also fails.</span></span>  
  
 <span data-ttu-id="d7014-106">Anstatt ein Fehlschlagen der Transformation zuzulassen, können Sie die Komponente so konfigurieren, dass die fehlerverursachende Zeile mithilfe der Fehlerausgabe in einen anderen Verarbeitungspfad umgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="d7014-106">Instead of permitting the transformation to fail, you can configure the component to redirect the failed row to another processing path by using the error output.</span></span> <span data-ttu-id="d7014-107">Die Verwendung eines separaten Fehlerverarbeitungspfades gibt Ihnen die Möglichkeit, mehrere Vorgänge auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d7014-107">Use of a separate error processing path lets you do a number of things.</span></span> <span data-ttu-id="d7014-108">Sie können beispielsweise die Daten säubern und dann die fehlerhafte Zeile erneut verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d7014-108">For instance, you might try to clean the data and then reprocess the failed row.</span></span> <span data-ttu-id="d7014-109">Oder Sie speichern die fehlerhafte Zeile zusammen mit zusätzlichen Fehlerinformationen zum späteren Überprüfen und erneutem Verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d7014-109">Or, you might save the failed row along with additional error information for later verification and reprocessing.</span></span>  
  
 <span data-ttu-id="d7014-110">In dieser Aufgabe konfigurieren Sie die Lookup Currency Key-Transformation so, dass alle fehlerverursachenden Zeilen in die Fehlerausgabe umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="d7014-110">In this task, you will configure the Lookup Currency Key transformation to redirect any rows that fail to the error output.</span></span> <span data-ttu-id="d7014-111">In der Fehlerverzweigung des Datenflusses werden diese Zeilen in eine Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="d7014-111">In the error branch of the data flow, these rows will be written to a file.</span></span>  
  
 <span data-ttu-id="d7014-112">Standardmäßig enthalten die beiden zusätzlichen Spalten in einer [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Fehlerausgabe **ErrorCode** und **ErrorColumn**nur numerische Codes, die eine Fehlernummer darstellen, und die ID der Spalte, in der der Fehler auftrat.</span><span class="sxs-lookup"><span data-stu-id="d7014-112">By default the two extra columns in an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] error output, **ErrorCode** and **ErrorColumn**, contain only numeric codes that represent an error number, and the ID of the column in which the error occurred.</span></span> <span data-ttu-id="d7014-113">Diese numerischen Werte sind ohne die entsprechende Fehlerbeschreibung nur von begrenztem Nutzen.</span><span class="sxs-lookup"><span data-stu-id="d7014-113">These numeric values may be of limited use without the corresponding error description.</span></span>  
  
 <span data-ttu-id="d7014-114">Um die Nützlichkeit der Fehlerausgabe zu verbessern, werden Sie mithilfe einer Skriptkomponente auf die [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -API zugreifen und eine Beschreibung des Fehlers abrufen, bevor das Paket die fehlerverursachenden Zeilen in die Datei schreibt.</span><span class="sxs-lookup"><span data-stu-id="d7014-114">To enhance the usefulness of the error output, before the package writes the failed rows to the file, you will use a Script component to access the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] API and get a description of the error.</span></span>  
  
### <a name="to-configure-an-error-output"></a><span data-ttu-id="d7014-115">So konfigurieren Sie eine Fehlerausgabe</span><span class="sxs-lookup"><span data-stu-id="d7014-115">To configure an error output</span></span>  
  
1.  <span data-ttu-id="d7014-116">Erweitern Sie in der **SSIS-Toolbox**die Option **Allgemein**, und ziehen Sie dann **Skript Komponente** auf die Entwurfs Oberfläche der Registerkarte **Datenfluss** . Platzieren Sie das **Skript** rechts von der **Lookup Currency Key** -Transformation.</span><span class="sxs-lookup"><span data-stu-id="d7014-116">In the **SSIS Toolbox**, expand **Common**, and then drag **Script Component** onto the design surface of the **Data Flow** tab. Place **Script** to the right of the **Lookup Currency Key** transformation.</span></span>  
  
2.  <span data-ttu-id="d7014-117">Klicken Sie im Dialogfeld **Skriptkomponententyp auswählen** auf **Transformation**und anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d7014-117">In the **Select Script Component Type** dialog box, click **Transformation**, and click **OK**.</span></span>  
  
3.  <span data-ttu-id="d7014-118">Klicken Sie auf die **Lookup Currency Key** -Transformation, und ziehen Sie anschließend den roten Pfeil auf die neu hinzugefügte **Skripttransformation** , um die zwei Komponenten zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="d7014-118">Click the **Lookup Currency Key** transformation and then drag the red arrow onto the newly added **Script** transformation to connect the two components.</span></span>  
  
     <span data-ttu-id="d7014-119">Der rote Pfeil stellt die Fehlerausgabe der **Lookup Currency Key** -Transformation dar.</span><span class="sxs-lookup"><span data-stu-id="d7014-119">The red arrow represents the error output of the **Lookup Currency Key** transformation.</span></span> <span data-ttu-id="d7014-120">Indem Sie den roten Pfeil zum Verbinden der Transformation mit der Skriptkomponente verwenden, können Sie alle Verarbeitungsfehler in die Skriptkomponente umleiten. Diese verarbeitet dann die Fehler und sendet sie an das Ziel.</span><span class="sxs-lookup"><span data-stu-id="d7014-120">By using the red arrow to connect the transformation to the Script component, you can redirect any processing errors to the Script component, which then processes the errors and sends them to the destination.</span></span>  
  
4.  <span data-ttu-id="d7014-121">Wählen Sie im Dialogfeld **Fehlerausgabe konfigurieren** in der **Fehler** -Spalte **Zeile umleiten**aus, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d7014-121">In the **Configure Error Output** dialog box, in the **Error** column, select **Redirect row**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="d7014-122">Klicken Sie auf der **Datenfluss** -Entwurfsoberfläche in der neu hinzugefügten **Skriptkomponente** auf **Skriptkomponente**, und ändern Sie den Namen in **Get Error Description**.</span><span class="sxs-lookup"><span data-stu-id="d7014-122">On the **Data Flow** design surface, click **Script Component** in the newly added **ScriptComponent**, and change the name to **Get Error Description**.</span></span>  
  
6.  <span data-ttu-id="d7014-123">Doppelklicken Sie auf die **Get Error Description** -Transformation.</span><span class="sxs-lookup"><span data-stu-id="d7014-123">Double-click the **Get Error Description** transformation.</span></span>  
  
7.  <span data-ttu-id="d7014-124">Wählen Sie im Dialogfeld **Transformations-Editor für Skripterstellung** auf der Seite **Eingabespalten** die **ErrorCode** -Spalte aus.</span><span class="sxs-lookup"><span data-stu-id="d7014-124">In the **Script Transformation Editor** dialog box, on the **Input Columns** page, select the **ErrorCode** column.</span></span>  
  
8.  <span data-ttu-id="d7014-125">Erweitern Sie auf der Seite **Eingaben und Ausgaben** das Element **Ausgabe 0**, klicken Sie auf **Ausgabespalten**und anschließend auf **Spalte hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d7014-125">On the **Inputs and Outputs** page, expand **Output 0**, click **Output Columns**, and then click **Add Column**.</span></span>  
  
9. <span data-ttu-id="d7014-126">Geben Sie in der- `Name` Eigenschaft **ErrorDescription** ein, und legen Sie die- `DataType` Eigenschaft auf **Unicode-Zeichenfolge [DT_WSTR]** fest.</span><span class="sxs-lookup"><span data-stu-id="d7014-126">In the `Name` property, type **ErrorDescription** and set the `DataType` property to **Unicode string [DT_WSTR]**.</span></span>  
  
10. <span data-ttu-id="d7014-127">Überprüfen Sie auf der Seite **Skript** , ob die- `LocaleID` Eigenschaft auf **Englisch (USA** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d7014-127">On the **Script** page, verify that the `LocaleID` property is set to **English (United States.**</span></span>  
  
11. <span data-ttu-id="d7014-128">Klicken Sie auf **Skript bearbeiten**, um [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Tools for Applications (VSTA) zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d7014-128">Click **Edit Script** to open [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span> <span data-ttu-id="d7014-129">Geben Sie den folgenden Code in die `Input0_ProcessInputRow`-Methode ein, oder fügen Sie ihn mit Kopieren und Einfügen ein.</span><span class="sxs-lookup"><span data-stu-id="d7014-129">In the `Input0_ProcessInputRow` method, type or paste the following code.</span></span>  
  
     <span data-ttu-id="d7014-130">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="d7014-130">[Visual Basic]</span></span>  
  
    ```  
    Row.ErrorDescription =   
      Me.ComponentMetaData.GetErrorDescription(Row.ErrorCode)  
    ```  
  
     <span data-ttu-id="d7014-131">[Visual C#]</span><span class="sxs-lookup"><span data-stu-id="d7014-131">[Visual C#]</span></span>  
  
    ```  
    Row.ErrorDescription = this.ComponentMetaData.GetErrorDescription(Row.ErrorCode);  
    ```  
  
     <span data-ttu-id="d7014-132">Die fertige Unterroutine sieht wie der folgende Code aus.</span><span class="sxs-lookup"><span data-stu-id="d7014-132">The completed subroutine will look like the following code.</span></span>  
  
     <span data-ttu-id="d7014-133">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="d7014-133">[Visual Basic]</span></span>  
  
    ```  
    Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
      Row.ErrorDescription =   
        Me.ComponentMetaData.GetErrorDescription(Row.ErrorCode)  
  
    End Sub  
    ```  
  
     <span data-ttu-id="d7014-134">[Visual C#]</span><span class="sxs-lookup"><span data-stu-id="d7014-134">[Visual C#]</span></span>  
  
    ```  
    public override void Input0_ProcessInputRow(Input0Buffer Row)  
        {  
  
            Row.ErrorDescription = this.ComponentMetaData.GetErrorDescription(Row.ErrorCode);  
  
        }  
    ```  
  
12. <span data-ttu-id="d7014-135">Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen** , um das Skript zu erstellen und die Änderungen zu speichern, und schließen Sie anschließend VSTA.</span><span class="sxs-lookup"><span data-stu-id="d7014-135">On the **Build** menu, click **Build Solution** to build the script and save your changes, and then close VSTA.</span></span>  
  
13. <span data-ttu-id="d7014-136">Klicken Sie auf **OK** , um das Dialogfeld **Transformations-Editor für Skripterstellung** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="d7014-136">Click **OK** to close the **Script Transformation Editor** dialog box.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d7014-137">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d7014-137">Next Steps</span></span>  
 <span data-ttu-id="d7014-138">[Schritt 4: Hinzufügen eines Flatfileziels] (Lesson-4-4-Adding-a-Flat-File-Destination.MD</span><span class="sxs-lookup"><span data-stu-id="d7014-138">[Step 4: Adding a Flat File Destination](lesson-4-4-adding-a-flat-file-destination.md</span></span>  
  
  
