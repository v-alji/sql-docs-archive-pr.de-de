---
title: Entwerfen der Abfrage | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptwizard.designquery.f1
ms.assetid: 2dad800f-10a1-453c-8761-2935b9826d84
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9b56d99ec11b50ce53ef223a01eb5fc2766238ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719678"
---
# <a name="design-the-query"></a><span data-ttu-id="ccbe5-102">Entwerfen der Abfrage</span><span class="sxs-lookup"><span data-stu-id="ccbe5-102">Design the Query</span></span>
  <span data-ttu-id="ccbe5-103">Auf dieser Seite des Berichts-Assistenten können Sie eine Abfrage erstellen, indem Sie die Abfrage entweder manuell eingeben, den Abfrage-Generator für die interaktive Erstellung der Abfrage nutzen oder indem Sie eine Abfrage aus einem anderen Bericht importieren.</span><span class="sxs-lookup"><span data-stu-id="ccbe5-103">Use this page of the Report Wizard to create a query by typing the query manually, by using Query Builder to interactively build a query, or by importing a query from another report.</span></span>  
  
 <span data-ttu-id="ccbe5-104">Der auf der Seite Datenquelle auswählen, einer vorhergehenden Seite im Berichts-Assistenten, von Ihnen ausgewählte Datenquellentyp bestimmt die Abfrage, die Sie auf dieser Seite eingeben können.</span><span class="sxs-lookup"><span data-stu-id="ccbe5-104">The data source type you chose on the Select the Data Source page, a previous page in the Report Wizard, determines the query you can enter on this page.</span></span> <span data-ttu-id="ccbe5-105">Wenn der Daten Quellentyp beispielsweise ist [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , können Sie- [!INCLUDE[tsql](../includes/tsql-md.md)] Anweisungen oder Namen gespeicherter Prozeduren eingeben.</span><span class="sxs-lookup"><span data-stu-id="ccbe5-105">For example, if the data source type is [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you can enter [!INCLUDE[tsql](../includes/tsql-md.md)] statements or stored procedure names.</span></span> <span data-ttu-id="ccbe5-106">Wenn der Daten Quellentyp ist [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , ist der Abfrage Bereich deaktiviert, und Sie können eine Abfrage nicht direkt eingeben.</span><span class="sxs-lookup"><span data-stu-id="ccbe5-106">If the data source type is [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], the Query pane is disabled and you cannot enter a query directly.</span></span> <span data-ttu-id="ccbe5-107">Sie können Abfragen mithilfe des Abfrage-Generators angeben.</span><span class="sxs-lookup"><span data-stu-id="ccbe5-107">You can specify the query by using Query Builder.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ccbe5-108">Tastatur</span><span class="sxs-lookup"><span data-stu-id="ccbe5-108">Options</span></span>  
 <span data-ttu-id="ccbe5-109">**Abfragezeichenfolge**</span><span class="sxs-lookup"><span data-stu-id="ccbe5-109">**Query string**</span></span>  
 <span data-ttu-id="ccbe5-110">Geben Sie eine Abfrage ein, die die Daten abruft, die Sie in Ihrem Bericht verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ccbe5-110">Type a query that retrieves the data you want to use in your report.</span></span>  
  
 <span data-ttu-id="ccbe5-111">**Abfrage-Generator**</span><span class="sxs-lookup"><span data-stu-id="ccbe5-111">**Query Builder**</span></span>  
 <span data-ttu-id="ccbe5-112">Klicken Sie auf **Abfrage-Generator** , um einen Abfrage-Designer für die Datenquelle zu öffnen oder eine Abfrage aus einem anderen Bericht zu importieren.</span><span class="sxs-lookup"><span data-stu-id="ccbe5-112">Click **Query Builder** to open a query designer for the data source, or to import a query from another report.</span></span>  
  
 <span data-ttu-id="ccbe5-113">Weitere Informationen zu Abfrage-Designern finden Sie unter [Reporting Services Query Designers](../../2014/reporting-services/reporting-services-query-designers.md).</span><span class="sxs-lookup"><span data-stu-id="ccbe5-113">For more information about query designers, see [Reporting Services Query Designers](../../2014/reporting-services/reporting-services-query-designers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ccbe5-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ccbe5-114">Example</span></span>  
 <span data-ttu-id="ccbe5-115">Für den Daten Quellentyp **Microsoft SQL Server**Ruft die folgende Abfrage eine Liste von Nachnamen aus der [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] Datenbanktabelle ab `Person` .</span><span class="sxs-lookup"><span data-stu-id="ccbe5-115">For the data source type **Microsoft SQL Server**, the following query retrieves a list of last names from the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database `Person` table.</span></span>  
  
```  
SELECT LastName FROM Person.Person;  
```  
  
 <span data-ttu-id="ccbe5-116">Für den Daten Quellentyp **Microsoft SQL Server**führt die folgende Abfrage die [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] gespeicherte Prozedur `uspGetEmployeeManagers` für den Mitarbeiter mit der ID 1 aus:</span><span class="sxs-lookup"><span data-stu-id="ccbe5-116">For the data source type **Microsoft SQL Server**, the following query runs the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] stored procedure `uspGetEmployeeManagers` for the employee with identification number 1:</span></span>  
  
```  
EXEC uspgetEmployeeManagers '1';  
```  
  
## <a name="see-also"></a><span data-ttu-id="ccbe5-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ccbe5-117">See Also</span></span>  
 <span data-ttu-id="ccbe5-118">[Hilfe zum Berichts-Assistenten](../../2014/reporting-services/report-wizard-help.md) </span><span class="sxs-lookup"><span data-stu-id="ccbe5-118">[Report Wizard Help](../../2014/reporting-services/report-wizard-help.md) </span></span>  
 <span data-ttu-id="ccbe5-119">[Melden Sie eingebettete Datasets und freigegebene Datasets &#40;Berichts-Generator und SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ccbe5-119">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ccbe5-120">Hinzufügen von Daten zu einem Bericht &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ccbe5-120">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-data/report-datasets-ssrs.md)  
  
  
