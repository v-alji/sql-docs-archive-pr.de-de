---
title: Kategorisierte Webdienstvorgänge (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: e3f346b5-7e26-481d-9821-1846e2e91289
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0f7dd682f55c16c6dcbff9f0f669593a10486da6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620496"
---
# <a name="categorized-web-service-operations-master-data-services"></a><span data-ttu-id="3e22f-102">Kategorisierte Webdienstvorgänge (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="3e22f-102">Categorized Web Service Operations (Master Data Services)</span></span>
  <span data-ttu-id="3e22f-103">Der [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] -Webdienst enthält einen vollständigen Satz an Vorgängen, mit dem Sie Code zum Steuern aller Funktionen schreiben können, die von [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] über die zugehörige Benutzeroberfläche ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3e22f-103">The [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web service contains a complete set of operations that let you write code to control all of the features that [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] does through its user interface.</span></span> <span data-ttu-id="3e22f-104">Die Webdienstvorgänge werden von der <xref:Microsoft.MasterDataServices.IService>-Schnittstelle definiert und als Methoden in der <xref:Microsoft.MasterDataServices.ServiceClient>-Klasse implementiert.</span><span class="sxs-lookup"><span data-stu-id="3e22f-104">The web service operations are defined by the <xref:Microsoft.MasterDataServices.IService> interface and are implemented as methods in the <xref:Microsoft.MasterDataServices.ServiceClient> class.</span></span> <span data-ttu-id="3e22f-105">Dieses Thema gruppiert die Webdienstvorgänge in konzeptionelle Kategorien, sodass Sie einen besseren Einblick in die Verwendung der Webdienst-API erhalten.</span><span class="sxs-lookup"><span data-stu-id="3e22f-105">This topic groups the web service operations into conceptual categories to help you understand how to use the web service API.</span></span>  
  
## <a name="model-operations"></a><span data-ttu-id="3e22f-106">Modellvorgänge</span><span class="sxs-lookup"><span data-stu-id="3e22f-106">Model Operations</span></span>  
 <span data-ttu-id="3e22f-107">Anhand dieser Vorgänge werden Modelle erstellt, aktualisiert und gelöscht und Aktionen für sämtliche Inhalte eines Modells wie Entitäten, Hierarchien und Versionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3e22f-107">These operations are used to create, update, and delete models, as well as to operate on all the contents of a model, such as entities, hierarchies, and versions.</span></span> <span data-ttu-id="3e22f-108">Weitere Informationen finden Sie unter [Modelle &#40;Master Data Services&#41;](../models-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3e22f-108">For more information, see [Models &#40;Master Data Services&#41;](../models-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataClone%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataUpdate%2A>|  
  
## <a name="entity-operations"></a><span data-ttu-id="3e22f-109">Entitätsvorgänge</span><span class="sxs-lookup"><span data-stu-id="3e22f-109">Entity Operations</span></span>  
 <span data-ttu-id="3e22f-110">Anhand dieser Vorgänge werden die Elemente einer einzelnen Entität erstellt, aktualisiert und gelöscht.</span><span class="sxs-lookup"><span data-stu-id="3e22f-110">These operations are used to create, update, and delete the members of a single entity.</span></span> <span data-ttu-id="3e22f-111">Weitere Informationen finden Sie unter [Entitäten (Master Data Services)](../entities-master-data-services.md) und [Elemente (Master Data Services)](../members-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3e22f-111">For more information, see [Entities &#40;Master Data Services&#41;](../entities-master-data-services.md) and [Members &#40;Master Data Services&#41;](../members-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMemberKeyLookup%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersCopy%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersMerge%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersUpdate%2A>|  
  
## <a name="member-operations"></a><span data-ttu-id="3e22f-112">Elementvorgänge</span><span class="sxs-lookup"><span data-stu-id="3e22f-112">Member Operations</span></span>  
 <span data-ttu-id="3e22f-113">Anhand dieser Vorgänge werden Elemente abgerufen, aktualisiert und gelöscht.</span><span class="sxs-lookup"><span data-stu-id="3e22f-113">These operations are used to get, update, and delete members.</span></span> <span data-ttu-id="3e22f-114">Der Elementsatz, für den Vorgänge ausgeführt werden, kann Elemente von mehreren Entitäten enthalten.</span><span class="sxs-lookup"><span data-stu-id="3e22f-114">The set of members operated on can contain members from multiple entities.</span></span> <span data-ttu-id="3e22f-115">Weitere Informationen finden Sie unter [Elemente &#40;Master Data Services&#41;](../members-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3e22f-115">For more information, see [Members &#40;Master Data Services&#41;](../members-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ModelMembersBulkDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ModelMembersBulkMerge%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ModelMembersBulkUpdate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ModelMembersGet%2A>|  
  
## <a name="attribute-and-hierarchy-operations"></a><span data-ttu-id="3e22f-116">Attribut- und Hierarchievorgänge</span><span class="sxs-lookup"><span data-stu-id="3e22f-116">Attribute and Hierarchy Operations</span></span>  
 <span data-ttu-id="3e22f-117">Anhand dieser Vorgänge werden Attribut- und Hierarchieinformationen abgerufen.</span><span class="sxs-lookup"><span data-stu-id="3e22f-117">These operations are used to get attribute and hierarchy information.</span></span> <span data-ttu-id="3e22f-118">Attribute und Hierarchien können auch mithilfe der Modellvorgänge geändert werden, z. B. <xref:Microsoft.MasterDataServices.ServiceClient.MetadataUpdate%2A>.</span><span class="sxs-lookup"><span data-stu-id="3e22f-118">Attributes and hierarchies can also be modified by using the model operations, such as <xref:Microsoft.MasterDataServices.ServiceClient.MetadataUpdate%2A>.</span></span> <span data-ttu-id="3e22f-119">Weitere Informationen finden Sie unter [Attribute &#40;Master Data Services&#41;](../attributes-master-data-services.md) und [Hierarchien &#40;Master Data Services&#41;](../hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3e22f-119">For more information, see [Attributes &#40;Master Data Services&#41;](../attributes-master-data-services.md) and [Hierarchies &#40;Master Data Services&#41;](../hierarchies-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMemberAttributesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.HierarchyMembersGet%2A>|  
  
## <a name="business-rule-operations"></a><span data-ttu-id="3e22f-120">Geschäftsregelvorgänge</span><span class="sxs-lookup"><span data-stu-id="3e22f-120">Business Rule Operations</span></span>  
 <span data-ttu-id="3e22f-121">Anhand dieser Vorgänge werden Geschäftsregeln erstellt, aktualisiert, gelöscht und veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="3e22f-121">These operations are used to create, update, delete, and publish business rules.</span></span> <span data-ttu-id="3e22f-122">Weitere Informationen finden Sie unter [Geschäftsregeln &#40;Master Data Services&#41;](../business-rules-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3e22f-122">For more information, see [Business Rules &#40;Master Data Services&#41;](../business-rules-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesClone%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesPaletteGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesPublish%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesUpdate%2A>|  
  
## <a name="annotation-operations"></a><span data-ttu-id="3e22f-123">Anmerkungsvorgänge</span><span class="sxs-lookup"><span data-stu-id="3e22f-123">Annotation Operations</span></span>  
 <span data-ttu-id="3e22f-124">Anhand dieser Vorgänge werden Anmerkungen erstellt, aktualisiert und gelöscht.</span><span class="sxs-lookup"><span data-stu-id="3e22f-124">These operations are used to create, update, and delete annotations.</span></span> <span data-ttu-id="3e22f-125">Weitere Informationen finden Sie unter [Anmerkungen &#40;Master Data Services&#41;](../annotations-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3e22f-125">For more information, see [Annotations &#40;Master Data Services&#41;](../annotations-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.AnnotationsDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.AnnotationsUpdate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMemberAnnotationsCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMemberAnnotationsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.TransactionAnnotationsCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.TransactionAnnotationsGet%2A>|  
  
## <a name="transaction-operations"></a><span data-ttu-id="3e22f-126">Transaktionsvorgänge</span><span class="sxs-lookup"><span data-stu-id="3e22f-126">Transaction Operations</span></span>  
 <span data-ttu-id="3e22f-127">Anhand dieser Vorgänge werden Transaktionen abgerufen und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="3e22f-127">These operations are used to get and reverse transactions.</span></span> <span data-ttu-id="3e22f-128">Weitere Informationen finden Sie unter [Transaktionen &#40;Master Data Services&#41;](../transactions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3e22f-128">For more information, see [Transactions &#40;Master Data Services&#41;](../transactions-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.TransactionsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.TransactionsReverse%2A>|  
  
## <a name="version-and-validation-operations"></a><span data-ttu-id="3e22f-129">Versions- und Validierungsvorgänge</span><span class="sxs-lookup"><span data-stu-id="3e22f-129">Version and Validation Operations</span></span>  
 <span data-ttu-id="3e22f-130">Anhand dieser Vorgänge werden Versionen kopiert und validiert.</span><span class="sxs-lookup"><span data-stu-id="3e22f-130">These operations are used to copy and validate versions.</span></span> <span data-ttu-id="3e22f-131">Weitere Informationen finden Sie unter [Versionen &#40;Master Data Services&#41;](../versions-master-data-services.md) und [Überprüfung &#40;Master Data Services&#41;](../validation-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3e22f-131">For more information, see [Versions &#40;Master Data Services&#41;](../versions-master-data-services.md) and [Validation &#40;Master Data Services&#41;](../validation-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.VersionCopy%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ValidationGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ValidationProcess%2A>|  
  
## <a name="data-quality-operations"></a><span data-ttu-id="3e22f-132">Datenqualitätsvorgänge</span><span class="sxs-lookup"><span data-stu-id="3e22f-132">Data Quality Operations</span></span>  
 <span data-ttu-id="3e22f-133">Anhand dieser Vorgänge werden Datenqualitätsaufgaben ausgeführt und zugehörige Ergebnisse überprüft.</span><span class="sxs-lookup"><span data-stu-id="3e22f-133">These operations are used to perform data quality tasks and to examine their results.</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityCleansingOperationCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityMatchingOperationCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityOperationStart%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityInstalledState%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityKnowledgeBasesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityOperationResultsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityOperationStatus%2A>|  
  
## <a name="data-import-operations"></a><span data-ttu-id="3e22f-134">Datenimportvorgänge</span><span class="sxs-lookup"><span data-stu-id="3e22f-134">Data Import Operations</span></span>  
 <span data-ttu-id="3e22f-135">Anhand dieser Vorgänge werden Daten in eine [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] -Datenbank importiert.</span><span class="sxs-lookup"><span data-stu-id="3e22f-135">These operations are used to import data into a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="3e22f-136">Weitere Informationen finden Sie unter [Datenimport &#40;Master Data Services&#41;](../overview-importing-data-from-tables-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3e22f-136">For more information, see [Data Import &#40;Master Data Services&#41;](../overview-importing-data-from-tables-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityStagingClear%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityStagingGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityStagingLoad%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityStagingProcess%2A>|  
  
 <span data-ttu-id="3e22f-137">Die folgenden Vorgänge werden verwendet, um Daten mithilfe des in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] integrierten Stagingprozesses zu importieren.</span><span class="sxs-lookup"><span data-stu-id="3e22f-137">The following operations are used to import data by using the staging process included in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="3e22f-138">Diese Vorgänge sind nur zur Unterstützung von vorhandenen Datenbanken zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3e22f-138">These operations should be used only to support existing databases.</span></span> <span data-ttu-id="3e22f-139">Greifen Sie für neue Entwicklungen auf die zuvor aufgelisteten Vorgänge zurück.</span><span class="sxs-lookup"><span data-stu-id="3e22f-139">For new development, use the previously listed operations.</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.StagingClear%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.StagingGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.StagingNameCheck%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.StagingProcess%2A>|  
  
## <a name="data-export-operations"></a><span data-ttu-id="3e22f-140">Datenexportvorgänge</span><span class="sxs-lookup"><span data-stu-id="3e22f-140">Data Export Operations</span></span>  
 <span data-ttu-id="3e22f-141">Anhand dieser Vorgänge werden Daten durch die Verwendung von Abonnementsichten exportiert.</span><span class="sxs-lookup"><span data-stu-id="3e22f-141">These operations are used to export data through the use of subscription views.</span></span> <span data-ttu-id="3e22f-142">Weitere Informationen finden Sie unter [Exportieren von Daten &#40;Master Data Services&#41;](../overview-exporting-data-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3e22f-142">For more information, see [Exporting Data &#40;Master Data Services&#41;](../overview-exporting-data-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ExportViewCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ExportViewDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ExportViewListGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ExportViewUpdate%2A>|  
  
## <a name="security-operations"></a><span data-ttu-id="3e22f-143">Sicherheitsvorgänge</span><span class="sxs-lookup"><span data-stu-id="3e22f-143">Security Operations</span></span>  
 <span data-ttu-id="3e22f-144">Diese Vorgänge werden verwendet, um die Sicherheitseinstellungen zu ändern, die den Zugriff auf die [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] -Datenbank steuern.</span><span class="sxs-lookup"><span data-stu-id="3e22f-144">These operations are used to modify the security settings that control access to the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="3e22f-145">Weitere Informationen finden Sie unter [Sicherheit &#40;Master Data Services&#41;](../security-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3e22f-145">For more information, see [Security &#40;Master Data Services&#41;](../security-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsClone%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsUpdate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesClone%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesUpdate%2A>|  
  
## <a name="system-operations"></a><span data-ttu-id="3e22f-146">Systemvorgänge</span><span class="sxs-lookup"><span data-stu-id="3e22f-146">System Operations</span></span>  
 <span data-ttu-id="3e22f-147">Diese Vorgänge werden verwendet, um System- und Benutzereinstellungen abzurufen und zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="3e22f-147">These operations are used to get and update system settings and user preferences.</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ServiceCheck%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ServiceVersionGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SystemDomainListGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SystemPropertiesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SystemSettingsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SystemSettingsUpdate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.UserPreferencesDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.UserPreferencesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.UserPreferencesUpdate%2A>|  
  
  
