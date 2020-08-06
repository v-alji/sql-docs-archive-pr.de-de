---
title: DDL ausführen (Analysis Services-Task) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.asexecuteddltask.f1
helpviewer_keywords:
- Analysis Services Execute DDL task
- DDL
ms.assetid: 7f25c8c6-b601-41f2-9553-be0a2ee0751a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a75bae174c816cdabd07ce688e068cbadb016b45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618212"
---
# <a name="analysis-services-execute-ddl-task"></a><span data-ttu-id="31221-102">DDL ausführen (Analysis Services-Task)</span><span class="sxs-lookup"><span data-stu-id="31221-102">Analysis Services Execute DDL Task</span></span>
  <span data-ttu-id="31221-103">Der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Task DDL ausführen führt DLL-Anweisungen (Data Definition Language, Datendefinitionssprache) aus, mit denen Miningmodelle und mehrdimensionale Objekte, wie z. B. Cubes und Dimensionen, erstellt, gelöscht oder geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="31221-103">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Execute DDL task runs data definition language (DDL) statements that can create, drop, or alter mining models and multidimensional objects such as cubes and dimensions.</span></span> <span data-ttu-id="31221-104">Beispielsweise kann mit einer DDL-Anweisung eine Partition im **Adventure Works** -Cube erstellt oder eine Dimension in [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], der im Lieferumfang von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] enthaltenen Beispieldatenbank von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="31221-104">For example, a DDL statement can create a partition in the **Adventure Works** cube, or delete a dimension in [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], the sample [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="31221-105">Der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Task DDL ausführen stellt mithilfe eines Verbindungs-Managers von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] eine Verbindung mit einer Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] oder mit einem Projekt von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="31221-105">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Execute DDL task uses an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] connection manager to connect to an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] or an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="31221-106">Weitere Informationen finden Sie unter [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="31221-106">For more information, see [Analysis Services Connection Manager](../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="31221-107">schließt eine Reihe von Tasks ein, die Business Intelligence-Vorgänge ausführen, wie z. B. das Verarbeiten analytischer Objekte und das Ausführen von Data Mining-Vorhersageabfragen.</span><span class="sxs-lookup"><span data-stu-id="31221-107">includes a number of tasks that perform business intelligence operations, such as processing analytic objects and running data mining prediction queries.</span></span>  
  
 <span data-ttu-id="31221-108">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu verwandten Business Intelligence-Tasks zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="31221-108">For more information about related business intelligence tasks, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="31221-109">Analysis Services-Verarbeitungstask</span><span class="sxs-lookup"><span data-stu-id="31221-109">Analysis Services Processing Task</span></span>](analysis-services-processing-task.md)  
  
-   [<span data-ttu-id="31221-110">Data Mining-Abfragetask</span><span class="sxs-lookup"><span data-stu-id="31221-110">Data Mining Query Task</span></span>](data-mining-query-task.md)  
  
## <a name="ddl-statements"></a><span data-ttu-id="31221-111">DDL-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="31221-111">DDL Statements</span></span>  
 <span data-ttu-id="31221-112">Die DDL-Anweisungen werden als [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Scripting Language (ASSL) dargestellt und in einen XMLA-Befehl (XML for Analysis) eingebunden.</span><span class="sxs-lookup"><span data-stu-id="31221-112">The DDL statements are represented as statements in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Scripting Language (ASSL), and framed in an XML for Analysis (XMLA) command.</span></span>  
  
-   <span data-ttu-id="31221-113">Mit ASSL werden eine Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] und die darin enthaltenen Datenbanken und Datenbankobjekte definiert und beschrieben.</span><span class="sxs-lookup"><span data-stu-id="31221-113">ASSL is used to define and describe an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and the databases and database objects it contains.</span></span> <span data-ttu-id="31221-114">Weitere Informationen finden Sie unter [Analysis Services Skriptsprache &#40;ASSL&#41; Referenz](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla).</span><span class="sxs-lookup"><span data-stu-id="31221-114">For more information, see [Analysis Services Scripting Language &#40;ASSL&#41; Reference](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla).</span></span>  
  
-   <span data-ttu-id="31221-115">Bei XMLA handelt es sich um eine Befehlssprache, mit der Aktionsbefehle, wie z. B. Create, Alter oder Process, an eine Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="31221-115">XMLA is a command language that is used to send action commands, such as Create, Alter, or Process, to an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="31221-116">Weitere Informationen finden Sie in der [XML for Analysis-Referenz &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference).</span><span class="sxs-lookup"><span data-stu-id="31221-116">For more information, see [XML for Analysis  &#40;XMLA&#41; Reference](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference).</span></span>  
  
 <span data-ttu-id="31221-117">Wenn der DDL-Code in einer separaten Datei gespeichert ist, gibt der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Task DDL ausführen mithilfe eines Dateiverbindungs-Manager den Dateipfad an.</span><span class="sxs-lookup"><span data-stu-id="31221-117">If the DDL code is stored in a separate file, the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Execute DDL task uses a File connection manager to specify the path of the file.</span></span> <span data-ttu-id="31221-118">Weitere Informationen finden Sie unter [File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="31221-118">For more information, see [File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="31221-119">DDL-Anweisungen können Kennwörter und sonstige vertrauliche Informationen enthalten. Deshalb sollte für ein Paket, das [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Tasks DDL ausführen enthält, die Paketschutzebene `EncryptAllWithUserKey` oder `EncryptAllWithPassword` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="31221-119">Because DDL statements can contain passwords and other sensitive information, a package that contains one or more [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Execute DDL tasks should use the package protection level `EncryptAllWithUserKey` or `EncryptAllWithPassword`.</span></span> <span data-ttu-id="31221-120">Weitere Informationen finden Sie unter [Integration Services-Pakete &#40;SSIS&#41;](../integration-services-ssis-packages.md).</span><span class="sxs-lookup"><span data-stu-id="31221-120">For more information, see [Integration Services &#40;SSIS&#41; Packages](../integration-services-ssis-packages.md).</span></span>  
  
### <a name="ddl-examples"></a><span data-ttu-id="31221-121">DDL-Beispiele</span><span class="sxs-lookup"><span data-stu-id="31221-121">DDL Examples</span></span>  
 <span data-ttu-id="31221-122">Die folgenden drei DDL-Anweisungen wurden von Skripterstellungsobjekten in [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], der im Lieferumfang von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] enthaltenen Beispieldatenbank von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], generiert.</span><span class="sxs-lookup"><span data-stu-id="31221-122">The following three DDL statements were generated by scripting objects in the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="31221-123">Mit der folgenden DDL-Anweisung wird die **Höherstufungs** -Dimension gelöscht.</span><span class="sxs-lookup"><span data-stu-id="31221-123">The following DDL statement deletes the **Promotion** dimension.</span></span>  
  
```  
<Delete xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <DimensionID>Dim Promotion</DimensionID>  
    </Object>  
</Delete>  
  
```  
  
 <span data-ttu-id="31221-124">Mit der folgenden DDL-Anweisung wird der [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] -Cube verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="31221-124">The following DDL statement processes the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] cube.</span></span>  
  
```  
<Batch xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Parallel>  
    <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
      <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      </Object>  
      <Type>ProcessFull</Type>  
      <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
    </Process>  
  </Parallel>  
</Batch>  
  
```  
  
 <span data-ttu-id="31221-125">Mit der folgenden DDL-Anweisung wird das **Forecasting** -Miningmodell erstellt.</span><span class="sxs-lookup"><span data-stu-id="31221-125">The following DDL statement creates the **Forecasting** mining model.</span></span>  
  
```  
<Create xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <ParentObject>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <MiningStructureID>Forecasting</MiningStructureID>  
    </ParentObject>  
    <ObjectDefinition>  
        <MiningModel xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
            <ID>Forecasting</ID>  
            <Name>Forecasting</Name>  
            <Algorithm>Microsoft_Time_Series</Algorithm>  
            <AlgorithmParameters>  
                <AlgorithmParameter>  
                    <Name>PERIODICITY_HINT</Name>  
                    <Value xsi:type="xsd:string">{12}</Value>  
                </AlgorithmParameter>  
            </AlgorithmParameters>  
            <Columns>  
                <Column>  
                    <ID>Amount</ID>  
                    <Name>Amount</Name>  
                    <SourceColumnID>Amount</SourceColumnID>  
                    <Usage>Predict</Usage>  
                </Column>  
                <Column>  
                    <ID>Model Region</ID>  
                    <Name>Model Region</Name>  
                    <SourceColumnID>Model Region</SourceColumnID>  
                    <Usage>Key</Usage>  
                </Column>  
                <Column>  
                    <ID>Quantity</ID>  
                    <Name>Quantity</Name>  
                    <SourceColumnID>Quantity</SourceColumnID>  
                    <Usage>Predict</Usage>  
                </Column>  
                <Column>  
                    <ID>Time Index</ID>  
                    <Name>Time Index</Name>  
                    <SourceColumnID>Time Index</SourceColumnID>  
                    <Usage>Key</Usage>  
                </Column>  
            </Columns>  
            <Collation>Latin1_General_CS_AS_KS</Collation>  
        </MiningModel>  
    </ObjectDefinition>  
</Create>  
  
```  
  
 <span data-ttu-id="31221-126">Die folgenden drei DDL-Anweisungen wurden von Skripterstellungsobjekten in [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], der im Lieferumfang von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] enthaltenen Beispieldatenbank von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], generiert.</span><span class="sxs-lookup"><span data-stu-id="31221-126">The following three DDL statements were generated by scripting objects in the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)], the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="31221-127">Mit der folgenden DDL-Anweisung wird die **Höherstufungs** -Dimension gelöscht.</span><span class="sxs-lookup"><span data-stu-id="31221-127">The following DDL statement deletes the **Promotion** dimension.</span></span>  
  
```  
<Delete xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <DimensionID>Dim Promotion</DimensionID>  
    </Object>  
</Delete>  
  
```  
  
 <span data-ttu-id="31221-128">Mit der folgenden DDL-Anweisung wird der [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] -Cube verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="31221-128">The following DDL statement processes the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] cube.</span></span>  
  
```  
<Batch xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Parallel>  
    <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
      <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      </Object>  
      <Type>ProcessFull</Type>  
      <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
    </Process>  
  </Parallel>  
</Batch>  
  
```  
  
 <span data-ttu-id="31221-129">Mit der folgenden DDL-Anweisung wird das **Forecasting** -Miningmodell erstellt.</span><span class="sxs-lookup"><span data-stu-id="31221-129">The following DDL statement creates the **Forecasting** mining model.</span></span>  
  
```  
<Create xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <ParentObject>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <MiningStructureID>Forecasting</MiningStructureID>  
    </ParentObject>  
    <ObjectDefinition>  
        <MiningModel xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
            <ID>Forecasting</ID>  
            <Name>Forecasting</Name>  
            <Algorithm>Microsoft_Time_Series</Algorithm>  
            <AlgorithmParameters>  
                <AlgorithmParameter>  
                    <Name>PERIODICITY_HINT</Name>  
                    <Value xsi:type="xsd:string">{12}</Value>  
                </AlgorithmParameter>  
            </AlgorithmParameters>  
            <Columns>  
                <Column>  
                    <ID>Amount</ID>  
                    <Name>Amount</Name>  
                    <SourceColumnID>Amount</SourceColumnID>  
                    <Usage>Predict</Usage>  
                </Column>  
                <Column>  
                    <ID>Model Region</ID>  
                    <Name>Model Region</Name>  
                    <SourceColumnID>Model Region</SourceColumnID>  
                    <Usage>Key</Usage>  
                </Column>  
                <Column>  
                    <ID>Quantity</ID>  
                    <Name>Quantity</Name>  
                    <SourceColumnID>Quantity</SourceColumnID>  
                    <Usage>Predict</Usage>  
                </Column>  
                <Column>  
                    <ID>Time Index</ID>  
                    <Name>Time Index</Name>  
                    <SourceColumnID>Time Index</SourceColumnID>  
                    <Usage>Key</Usage>  
                </Column>  
            </Columns>  
            <Collation>Latin1_General_CS_AS_KS</Collation>  
        </MiningModel>  
    </ObjectDefinition>  
</Create>  
  
```  
  
## <a name="configuration-of-the-analysis-services-execute-ddl-task"></a><span data-ttu-id="31221-130">Konfiguration des Analysis Services-Tasks "DDL ausführen"</span><span class="sxs-lookup"><span data-stu-id="31221-130">Configuration of the Analysis Services Execute DDL Task</span></span>  
 <span data-ttu-id="31221-131">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="31221-131">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="31221-132">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können:</span><span class="sxs-lookup"><span data-stu-id="31221-132">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="31221-133">Editor für den Analysis Services-Task „DDL ausführen“ &#40;Seite „Allgemein“&#41;</span><span class="sxs-lookup"><span data-stu-id="31221-133">Analysis Services Execute DDL Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="31221-134">Editor für den Analysis Services-Task „DDL ausführen“ &#40;Seite „DDL“&#41;</span><span class="sxs-lookup"><span data-stu-id="31221-134">Analysis Services Execute DDL Task Editor &#40;DDL Page&#41;</span></span>](../analysis-services-execute-ddl-task-editor-ddl-page.md)  
  
-   [<span data-ttu-id="31221-135">Seite Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="31221-135">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="31221-136">Klicken Sie auf das folgende Thema, um weitere Informationen zum Festlegen dieser Eigenschaften im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="31221-136">For more information about setting these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="31221-137">Festlegen der Eigenschaften eines Tasks oder Containers</span><span class="sxs-lookup"><span data-stu-id="31221-137">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="programmatic-configuration-of-the-analysis-services-execute-ddl-task"></a><span data-ttu-id="31221-138">Programmgesteuerte Konfiguration des Analysis Services-Tasks "DDL ausführen"</span><span class="sxs-lookup"><span data-stu-id="31221-138">Programmatic Configuration of the Analysis Services Execute DDL Task</span></span>  
 <span data-ttu-id="31221-139">Klicken Sie auf das folgende Thema, um weitere Informationen zum programmgesteuerten Festlegen dieser Eigenschaften anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="31221-139">For more information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.DataTransformationServices.Tasks.DTSProcessingTask.ASExecuteDDLTask>  
  
  
