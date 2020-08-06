---
title: DQS-Bereinigungstransformation | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data correction
- correct data
ms.assetid: d2ec1b1a-c745-4741-b57c-6fdb524a154c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5e980497905b8fa96a73516916af17f934221992
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608767"
---
# <a name="dqs-cleansing-transformation"></a><span data-ttu-id="a93c6-102">DQS-Bereinigungstransformation</span><span class="sxs-lookup"><span data-stu-id="a93c6-102">DQS Cleansing Transformation</span></span>
  <span data-ttu-id="a93c6-103">Die DQS-Bereinigungstransformation korrigiert Daten aus einer verbundenen Datenquelle mithilfe von Data Quality Services (DQS), indem sie genehmigte Regeln anwendet, die für die verbundene Datenquelle oder eine ähnliche Datenquelle erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="a93c6-103">The DQS Cleansing transformation uses Data Quality Services (DQS) to correct data from a connected data source, by applying approved rules that were created for the connected data source or a similar data source.</span></span> <span data-ttu-id="a93c6-104">Weitere Informationen zu Datenkorrekturregeln finden Sie unter [DQS Knowledge Bases and Domains](../../../data-quality-services/dqs-knowledge-bases-and-domains.md).</span><span class="sxs-lookup"><span data-stu-id="a93c6-104">For more information about data correction rules, see [DQS Knowledge Bases and Domains](../../../data-quality-services/dqs-knowledge-bases-and-domains.md).</span></span> <span data-ttu-id="a93c6-105">Weitere Informationen zu DQS finden Sie unter [Data Quality Services Concepts](../../../data-quality-services/data-quality-services-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="a93c6-105">For more information DQS, see [Data Quality Services Concepts](../../../data-quality-services/data-quality-services-concepts.md).</span></span>  
  
 <span data-ttu-id="a93c6-106">Die DQS-Bereinigungstransformation bestimmt, ob die Daten korrigiert werden müssen, indem sie die Daten in einer Eingabespalte verarbeitet. Dabei gelten folgende Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="a93c6-106">To determine whether the data has to be corrected, the DQS Cleansing transformation processes data from an input column when the following conditions are true:</span></span>  
  
-   <span data-ttu-id="a93c6-107">Die Spalte ist für die Datenkorrektur ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="a93c6-107">The column is selected for data correction.</span></span>  
  
-   <span data-ttu-id="a93c6-108">Der Datentyp der Spalte wird in der Datenkorrektur unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a93c6-108">The column data type is supported for data correction.</span></span>  
  
-   <span data-ttu-id="a93c6-109">Der Spalte ist eine Domäne mit einem kompatiblen Datentyp zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a93c6-109">The column is mapped a domain that has a compatible data type.</span></span>  
  
 <span data-ttu-id="a93c6-110">Die Transformation umfasst auch eine Fehlerausgabe, die Sie zur Behandlung von Fehlern auf Zeilenebene konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="a93c6-110">The transformation also includes an error output that you configure to handle row-level errors.</span></span> <span data-ttu-id="a93c6-111">Die Fehlerausgabe wird mit dem **Transformations-Editor für die DQS-Bereinigung**konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="a93c6-111">To configure the error output, use the **DQS Cleansing Transformation Editor**.</span></span>  
  
 <span data-ttu-id="a93c6-112">Sie können die [Fuzzy Grouping Transformation](fuzzy-grouping-transformation.md) in den Datenfluss einschließen, um Zeilen mit Daten zu ermitteln, bei denen es sich wahrscheinlich um Duplikate handelt.</span><span class="sxs-lookup"><span data-stu-id="a93c6-112">You can include the [Fuzzy Grouping Transformation](fuzzy-grouping-transformation.md) in the data flow to identify rows of data that are likely to be duplicates.</span></span>  
  
## <a name="data-quality-projects-and-values"></a><span data-ttu-id="a93c6-113">Data Quality-Projekte und -Werte</span><span class="sxs-lookup"><span data-stu-id="a93c6-113">Data Quality Projects and Values</span></span>  
 <span data-ttu-id="a93c6-114">Wenn Sie Daten mit der DQS-Bereinigungstransformation verarbeiten, wird ein Bereinigungsprojekt auf dem Data Quality-Server erstellt.</span><span class="sxs-lookup"><span data-stu-id="a93c6-114">When you process data with the DQS Cleansing transformation, a cleansing project is created on the Data Quality Server.</span></span> <span data-ttu-id="a93c6-115">Das Projekt wird mit dem Data Quality Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="a93c6-115">You use the Data Quality Client to manage the project.</span></span> <span data-ttu-id="a93c6-116">Mit dem Data Quality Client können Sie außerdem die Projektwerte in eine DQS-Wissensdatenbankdomäne importieren.</span><span class="sxs-lookup"><span data-stu-id="a93c6-116">In addition, you can use the Data Quality Client to import the project values into a DQS knowledge base domain.</span></span> <span data-ttu-id="a93c6-117">Sie können die Werte nur in eine Domäne (oder verknüpfte Domäne) importieren, für deren Verwendung die DQS-Bereinigungstransformation konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="a93c6-117">You can import the values only to a domain (or linked domain) that the DQS Cleansing transformation was configured to use.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="a93c6-118">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="a93c6-118">Related Tasks</span></span>  
  
-   [<span data-ttu-id="a93c6-119">Öffnen von Integration Services-Projekten im Data Quality-Client</span><span class="sxs-lookup"><span data-stu-id="a93c6-119">Open Integration Services Projects in Data Quality Client</span></span>](../../../data-quality-services/open-integration-services-projects-in-data-quality-client.md)  
  
-   [<span data-ttu-id="a93c6-120">Importieren von Bereinigungsprojektwerten in eine Domäne</span><span class="sxs-lookup"><span data-stu-id="a93c6-120">Import Cleansing Project Values into a Domain</span></span>](../../../data-quality-services/import-cleansing-project-values-into-a-domain.md)  
  
-   [<span data-ttu-id="a93c6-121">Anwenden von Datenqualitätsregeln auf eine Datenquelle</span><span class="sxs-lookup"><span data-stu-id="a93c6-121">Apply Data Quality Rules to Data Source</span></span>](apply-data-quality-rules-to-data-source.md)  
  
## <a name="related-content"></a><span data-ttu-id="a93c6-122">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="a93c6-122">Related Content</span></span>  
  
-   [<span data-ttu-id="a93c6-123">Verwalten von &#40;öffnen, entsperren, umbenennen und löschen&#41; eines Data Quality-Projekts</span><span class="sxs-lookup"><span data-stu-id="a93c6-123">Manage &#40;Open, Unlock, Rename, and Delete&#41; a Data Quality Project</span></span>](../../../data-quality-services/manage-open-unlock-rename-and-delete-a-data-quality-project.md)  
  
-   <span data-ttu-id="a93c6-124">Artikel [Bereinigung komplexer Daten unter Verwendung von Verbunddomänen](https://social.technet.microsoft.com/wiki/contents/articles/13324.using-dqs-cleansing-complex-data-using-composite-domains.aspx)auf social.technet.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="a93c6-124">Article, [Cleansing complex data using composite domains](https://social.technet.microsoft.com/wiki/contents/articles/13324.using-dqs-cleansing-complex-data-using-composite-domains.aspx), on social.technet.microsoft.com.</span></span>  
  
  
