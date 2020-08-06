---
title: Analysis Services Editor für den Task ' DDL ausführen ' (DDL-Seite) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.asexecuteddltask.ddl.f1
helpviewer_keywords:
- Analysis Services Execute DDL Task Editor
ms.assetid: f21bf8d0-ec5f-4c18-9de0-8875addb927b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d207afe666e582c44f1014a6c80f4f4984fd5410
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615522"
---
# <a name="analysis-services-execute-ddl-task-editor-ddl-page"></a><span data-ttu-id="062a9-102">Editor für den Analysis Services-Task 'DDL ausführen' (Seite DDL)</span><span class="sxs-lookup"><span data-stu-id="062a9-102">Analysis Services Execute DDL Task Editor (DDL Page)</span></span>
  <span data-ttu-id="062a9-103">Auf der Seite **DDL** des Dialogfelds **Editor für den Analysis Services-Task „DDL ausführen“** können Sie eine Verbindung mit einem [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Projekt oder einer [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Datenbank angeben sowie Informationen zur Quelle der DDL-Anweisungen (Data Definition Language) angeben.</span><span class="sxs-lookup"><span data-stu-id="062a9-103">Use the **DDL** page of the **Analysis Services Execute DDL Task Editor** dialog box to specify a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project or an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database and to provide information about the source of data definition language (DDL) statements.</span></span>  
  
 <span data-ttu-id="062a9-104">Informationen, um sich mit diesem Thema vertraut zu machen, finden Sie unter [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md).</span><span class="sxs-lookup"><span data-stu-id="062a9-104">To learn about this task, see [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="062a9-105">Statische Optionen</span><span class="sxs-lookup"><span data-stu-id="062a9-105">Static Options</span></span>  
 <span data-ttu-id="062a9-106">**Connection**</span><span class="sxs-lookup"><span data-stu-id="062a9-106">**Connection**</span></span>  
 <span data-ttu-id="062a9-107">Wählen Sie ein [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Projekt oder einen [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Verbindungs-Manager aus der Liste aus, oder klicken Sie auf \<**New connection...**>, und erstellen Sie im Dialogfeld **Analysis Services-Verbindungs-Manager hinzufügen** eine neue Verbindung.</span><span class="sxs-lookup"><span data-stu-id="062a9-107">Select an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project or an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] connection manager in the list, or click \<**New connection...**> and use the **Add Analysis Services Connection Manager** dialog box to create a new connection.</span></span>  
  
 <span data-ttu-id="062a9-108">**Verwandte Themen:** [Referenz zur Benutzeroberfläche des Dialogfelds Analysis Services-Verbindungs-Manager hinzufügen](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md), [Analysis Services-Verbindungs-Manager](connection-manager/analysis-services-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="062a9-108">**Related Topics:** [Add Analysis Services Connection Manager Dialog Box UI Reference](connection-manager/add-analysis-services-connection-manager-dialog-box-ui-reference.md), [Analysis Services Connection Manager](connection-manager/analysis-services-connection-manager.md)</span></span>  
  
 <span data-ttu-id="062a9-109">**SourceType**</span><span class="sxs-lookup"><span data-stu-id="062a9-109">**SourceType**</span></span>  
 <span data-ttu-id="062a9-110">Geben Sie den Quelltyp der DDL-Anweisung an.</span><span class="sxs-lookup"><span data-stu-id="062a9-110">Specify the source type of the DDL statements.</span></span> <span data-ttu-id="062a9-111">Für diese Eigenschaft sind die in der folgenden Tabelle aufgeführten Optionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="062a9-111">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="062a9-112">Wert</span><span class="sxs-lookup"><span data-stu-id="062a9-112">Value</span></span>|<span data-ttu-id="062a9-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="062a9-113">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="062a9-114">**Direct Input**</span><span class="sxs-lookup"><span data-stu-id="062a9-114">**Direct Input**</span></span>|<span data-ttu-id="062a9-115">Legen Sie die Quelle der im Textfeld **SourceDirect** gespeicherten DDL-Anweisung fest.</span><span class="sxs-lookup"><span data-stu-id="062a9-115">Set the source to the DDL statement stored in the **SourceDirect** text box.</span></span> <span data-ttu-id="062a9-116">Wenn Sie diesen Wert auswählen, werden im folgenden Abschnitt die dynamischen Optionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="062a9-116">Selecting this value displays the dynamic options in the following section.</span></span>|  
|<span data-ttu-id="062a9-117">**File Connection**</span><span class="sxs-lookup"><span data-stu-id="062a9-117">**File Connection**</span></span>|<span data-ttu-id="062a9-118">Legen Sie die Quelle für eine Datei fest, in der die DDL-Anweisung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="062a9-118">Set the source to a file that contains the DDL statement.</span></span> <span data-ttu-id="062a9-119">Wenn Sie diesen Wert auswählen, werden im folgenden Abschnitt die dynamischen Optionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="062a9-119">Selecting this value displays the dynamic options in the following section.</span></span>|  
|<span data-ttu-id="062a9-120">**Variable**</span><span class="sxs-lookup"><span data-stu-id="062a9-120">**Variable**</span></span>|<span data-ttu-id="062a9-121">Legen Sie die Quelle für eine Variable fest.</span><span class="sxs-lookup"><span data-stu-id="062a9-121">Set the source to a variable.</span></span> <span data-ttu-id="062a9-122">Wenn Sie diesen Wert auswählen, werden im folgenden Abschnitt die dynamischen Optionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="062a9-122">Selecting this value displays the dynamic options in the following section.</span></span>|  
  
## <a name="dynamic-options"></a><span data-ttu-id="062a9-123">Dynamische Optionen</span><span class="sxs-lookup"><span data-stu-id="062a9-123">Dynamic Options</span></span>  
  
### <a name="sourcetype--direct-input"></a><span data-ttu-id="062a9-124">SourceType = Direkteingabe</span><span class="sxs-lookup"><span data-stu-id="062a9-124">SourceType = Direct Input</span></span>  
 <span data-ttu-id="062a9-125">**Quelle**</span><span class="sxs-lookup"><span data-stu-id="062a9-125">**Source**</span></span>  
 <span data-ttu-id="062a9-126">Geben Sie die DDL-Anweisungen ein, oder klicken Sie auf die Schaltfläche mit den **Auslassungspunkten (...)** , und geben Sie dann die Anweisungen im Dialogfeld **DDL-Anweisungen** ein.</span><span class="sxs-lookup"><span data-stu-id="062a9-126">Type the DDL statements or click the ellipsis **(...)** and then type the statements in the **DDL Statements** dialog box.</span></span>  
  
### <a name="sourcetype--file-connection"></a><span data-ttu-id="062a9-127">SourceType = File Connection</span><span class="sxs-lookup"><span data-stu-id="062a9-127">SourceType = File Connection</span></span>  
 <span data-ttu-id="062a9-128">**Quelle**</span><span class="sxs-lookup"><span data-stu-id="062a9-128">**Source**</span></span>  
 <span data-ttu-id="062a9-129">Wählen Sie eine Dateiverbindung aus der Liste aus, oder klicken Sie auf \<**New connection...**>, und erstellen Sie im Dialogfeld **Dateiverbindungs-Manager** eine neue Verbindung.</span><span class="sxs-lookup"><span data-stu-id="062a9-129">Select a File connection in the list, or click \<**New connection...**> and use the **File Connection Manager** dialog box to create a new connection.</span></span>  
  
 <span data-ttu-id="062a9-130">**Verwandte Themen:** [Dateiverbindungs-Manager](connection-manager/file-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="062a9-130">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md)</span></span>  
  
### <a name="sourcetype--variable"></a><span data-ttu-id="062a9-131">SourceType = Variable</span><span class="sxs-lookup"><span data-stu-id="062a9-131">SourceType = Variable</span></span>  
 <span data-ttu-id="062a9-132">**Quelle**</span><span class="sxs-lookup"><span data-stu-id="062a9-132">**Source**</span></span>  
 <span data-ttu-id="062a9-133">Wählen Sie eine Variable aus der Liste aus, oder klicken Sie auf \<**New variable...**>, und erstellen Sie im Dialogfeld **Variable hinzufügen** eine neue Variable.</span><span class="sxs-lookup"><span data-stu-id="062a9-133">Select a variable in the list, or click \<**New variable...**> and use the **Add Variable** dialog box to create a new variable.</span></span>  
  
 <span data-ttu-id="062a9-134">**Verwandte Themen:** [Integration Services-Variablen &#40;SSIS&#41;](integration-services-ssis-variables.md)</span><span class="sxs-lookup"><span data-stu-id="062a9-134">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="062a9-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="062a9-135">See Also</span></span>  
 <span data-ttu-id="062a9-136">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="062a9-136">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="062a9-137">[Analysis Services Editor für den Task ' DDL ausführen ' &#40;Seite Allgemein&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="062a9-137">[Analysis Services Execute DDL Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="062a9-138">[Seite Ausdrücke](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="062a9-138">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="062a9-139">[Ablaufsteuerung](control-flow/control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="062a9-139">[Control Flow](control-flow/control-flow.md) </span></span>  
 <span data-ttu-id="062a9-140">[Analysis Services Skriptsprache &#40;ASSL&#41; Referenz](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla) </span><span class="sxs-lookup"><span data-stu-id="062a9-140">[Analysis Services Scripting Language &#40;ASSL&#41; Reference](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla) </span></span>  
 [<span data-ttu-id="062a9-141">XML for Analysis-Referenz &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="062a9-141">XML for Analysis  &#40;XMLA&#41; Reference</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference)  
  
  
