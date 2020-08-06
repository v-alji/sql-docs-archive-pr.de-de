---
title: Benutzerdefinierte Workflow-XML-Beschreibung (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: e267e5f4-38bb-466d-82e8-871eabeec07e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 77906426ddb901ec422367bf30aabef2e532ad06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630683"
---
# <a name="custom-workflow-xml-description-master-data-services"></a><span data-ttu-id="ba958-102">Benutzerdefinierte Workflow-XML-Beschreibung (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ba958-102">Custom Workflow XML Description (Master Data Services)</span></span>
  <span data-ttu-id="ba958-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] wird die [Microsoft. masterdataservices. workflowtypeextender. iworkflowtypeextender. StartWorkflow \*](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)) -Methode von SQL Server MDS Workflow Integration Service aufgerufen, wenn ein Workflow gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="ba958-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)], the [Microsoft.MasterDataServices.WorkflowTypeExtender.IWorkflowTypeExtender.StartWorkflow\*](/previous-versions/sql/sql-server-2016/hh759009(v=sql.130)) method is called by SQL Server MDS Workflow Integration Service when a workflow starts.</span></span> <span data-ttu-id="ba958-104">Diese Methode empfängt Metadaten und Daten zum Element, das die Workflowgeschäftsregel als XML-Block ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="ba958-104">This method receives metadata and data about the item that triggered the workflow business rule as a block of XML.</span></span> <span data-ttu-id="ba958-105">Beispielcode zum Implementieren eines Workflowhandlers finden Sie unter [Beispiel für einen benutzerdefinierten Workflow &#40;Master Data Services&#41;](create-a-custom-workflow-example.md).</span><span class="sxs-lookup"><span data-stu-id="ba958-105">For example code that implements a workflow handler, see [Custom Workflow Example &#40;Master Data Services&#41;](create-a-custom-workflow-example.md).</span></span>  
  
 <span data-ttu-id="ba958-106">Das folgende Beispiel zeigt eine mögliche Darstellung der XML, die an den Workflowhandler gesendet wird:</span><span class="sxs-lookup"><span data-stu-id="ba958-106">The following example shows what the XML that is sent to the workflow handler might look like:</span></span>  
  
```scr  
<ExternalAction>  
  <Type>TEST</Type>  
  <SendData>1</SendData>  
  <Server_URL>This is my test!</Server_URL>  
  <Action_ID>Test Workflow</Action_ID>  
  <Model_ID>5</Model_ID>  
  <Model_Name>Customer</Model_Name>  
  <Entity_ID>34</Entity_ID>  
  <Entity_Name>Customer</Entity_Name>  
  <Version_ID>8</Version_ID>  
  <MemberType_ID>1</MemberType_ID>  
  <Member_ID>12</Member_ID>  
  <MemberData>  
    <ID>12</ID>  
    <Version_ID>8</Version_ID>  
    <ValidationStatus_ID>3</ValidationStatus_ID>  
    <ChangeTrackingMask>0</ChangeTrackingMask>  
    <EnterDTM>2011-02-25T20:16:36.650</EnterDTM>  
    <EnterUserID>2</EnterUserID>  
    <EnterUserName>MyUserName</EnterUserName>  
    <EnterUserMuid>EEF91D48-B673-4D83-B95F-5A363C11DE91</EnterUserMuid>  
    <EnterVersionId>8</EnterVersionId>  
    <EnterVersionName>VERSION_1</EnterVersionName>  
    <EnterVersionMuid>52B788C2-2750-4651-9DB0-2CB05A88AA5A</EnterVersionMuid>  
    <LastChgDTM>2011-02-25T20:16:36.650</LastChgDTM>  
    <LastChgUserID>2</LastChgUserID>  
    <LastChgUserName>MyUserName</LastChgUserName>  
    <LastChgUserMuid>EEF91D48-B673-4D83-B95F-5A363C11DE91</LastChgUserMuid>  
    <LastChgVersionId>8</LastChgVersionId>  
    <LastChgVersionName>VERSION_1</LastChgVersionName>  
    <LastChgVersionMuid>52B788C2-2750-4651-9DB0-2CB05A88AA5A</LastChgVersionMuid>  
    <Name>Test Customer</Name>  
    <Code>TC</Code>  
  </MemberData>  
</ExternalAction>  
```  
  
 <span data-ttu-id="ba958-107">In der folgenden Tabelle werden einige der Tags beschrieben, die in dieser XML enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="ba958-107">The following table describes some of the tags contained in this XML:</span></span>  
  
|<span data-ttu-id="ba958-108">Tag</span><span class="sxs-lookup"><span data-stu-id="ba958-108">Tag</span></span>|<span data-ttu-id="ba958-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ba958-109">Description</span></span>|  
|---------|-----------------|  
|\<Type>|<span data-ttu-id="ba958-110">Der von Ihnen im Textfeld **Workflowtyp** in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] eingegebene Text, der zum Identifizieren der zu ladenden benutzerdefinierten Workflowassembly dient.</span><span class="sxs-lookup"><span data-stu-id="ba958-110">The text you entered in the **Workflow type** text box in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] to identify which custom workflow assembly to load.</span></span>|  
|\<SendData>|<span data-ttu-id="ba958-111">Ein boolescher Wert, der mithilfe des Kontrollkästchens **Elementdaten in die Meldung einschließen** in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="ba958-111">A Boolean value controlled by the **Include member data in the message** checkbox in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span> <span data-ttu-id="ba958-112">Der Wert 1 bedeutet, dass der \<MemberData> Abschnitt gesendet wird \<MemberData> . andernfalls wird der Abschnitt nicht gesendet.</span><span class="sxs-lookup"><span data-stu-id="ba958-112">A value of 1 means that the \<MemberData> section is sent; otherwise the \<MemberData> section is not sent.</span></span>|  
|<span data-ttu-id="ba958-113"><Server_URL></span><span class="sxs-lookup"><span data-stu-id="ba958-113"><Server_URL></span></span>|<span data-ttu-id="ba958-114">Der Text, den Sie im Textfeld **Workflowsite** in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="ba958-114">The text you entered in the **Workflow site** text box in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span>|  
|<span data-ttu-id="ba958-115"><Action_ID></span><span class="sxs-lookup"><span data-stu-id="ba958-115"><Action_ID></span></span>|<span data-ttu-id="ba958-116">Der Text, den Sie im Textfeld **Workflowname** in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="ba958-116">The text you entered in the **Workflow name** text box in [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span>|  
|\<MemberData>|<span data-ttu-id="ba958-117">Enthält die Daten des Elements, das die Workflowaktion ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="ba958-117">Contains the data of the member that triggered the workflow action.</span></span> <span data-ttu-id="ba958-118">Diese ist nur enthalten, wenn der Wert von \<SendData> 1 ist.</span><span class="sxs-lookup"><span data-stu-id="ba958-118">This is included only if the value of \<SendData> is 1.</span></span>|  
|\<Enter*xxx*>|<span data-ttu-id="ba958-119">Dieser Tagsatz enthält Metadaten zur Erstellung des Elements, beispielsweise den Zeitpunkt der Erstellung und den Ersteller.</span><span class="sxs-lookup"><span data-stu-id="ba958-119">This set of tags contains metadata about the creation of the member, such as when it was created and who created it.</span></span>|  
|\<LastChg*xxx*>|<span data-ttu-id="ba958-120">Dieser Tagsatz enthält Metadaten zur letzten Änderung des Elements, beispielsweise den Zeitpunkt und Autor.</span><span class="sxs-lookup"><span data-stu-id="ba958-120">This set of tags contains metadata about the last change made to the member, such as when the change was made and who made it.</span></span>|  
|\<Name>|<span data-ttu-id="ba958-121">Das erste Attribut des Elements, das geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="ba958-121">The first attribute of the member that was changed.</span></span> <span data-ttu-id="ba958-122">Dieses Beispielelement enthält nur Namens- und Codeattribute.</span><span class="sxs-lookup"><span data-stu-id="ba958-122">This example member contains only Name and Code attributes.</span></span>|  
|\<Code>|<span data-ttu-id="ba958-123">Das nächste Attribut des Elements, das geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="ba958-123">The next attribute of the member that was changed.</span></span> <span data-ttu-id="ba958-124">Enthielt dieses Beispielelement mehr Attribute, würden sie diesem nachfolgen.</span><span class="sxs-lookup"><span data-stu-id="ba958-124">If this example member contained more attributes, they would follow this one.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ba958-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ba958-125">See Also</span></span>  
 <span data-ttu-id="ba958-126">[Erstellen Sie einen benutzerdefinierten Workflow &#40;Master Data Services&#41;](create-a-custom-workflow-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ba958-126">[Create a Custom Workflow &#40;Master Data Services&#41;](create-a-custom-workflow-master-data-services.md) </span></span>  
 [<span data-ttu-id="ba958-127">Beispiel für einen benutzerdefinierten Workflow &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ba958-127">Custom Workflow Example &#40;Master Data Services&#41;</span></span>](create-a-custom-workflow-example.md)  
  
  
