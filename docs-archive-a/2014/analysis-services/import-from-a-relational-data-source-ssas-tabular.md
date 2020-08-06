---
title: Importieren aus einer relationalen Datenquelle (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 043201cc-fbef-4ed0-bde8-dc5e3a3e8bea
author: minewiskan
ms.author: owend
ms.openlocfilehash: 93bb9ba9ba8d40262e4e90e840dcd15ac6826df3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621722"
---
# <a name="import-from-a-relational-data-source-ssas-tabular"></a><span data-ttu-id="a987c-102">Import von einer relationalen Datenquelle (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="a987c-102">Import from a Relational Data Source (SSAS Tabular)</span></span>
  <span data-ttu-id="a987c-103">Mit dem Tabellenimport-Assistenten können Sie Daten aus einer Vielzahl relationaler Datenbanken importieren:</span><span class="sxs-lookup"><span data-stu-id="a987c-103">You can import data from a variety of relational databases by using the Table Import Wizard.</span></span> <span data-ttu-id="a987c-104">Der Assistent ist in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]im Menü **Modell** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a987c-104">The wizard is available in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], on the **Model** menu.</span></span> <span data-ttu-id="a987c-105">Der entsprechende Anbieter muss auf dem Computer installiert sein, um eine Verbindung mit einer Datenquelle herzustellen.</span><span class="sxs-lookup"><span data-stu-id="a987c-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span> <span data-ttu-id="a987c-106">Weitere Informationen zu unterstützten Datenquellen und -anbietern finden Sie unter [Unterstützte Datenquellen &#40;SSAS – tabellarisch&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="a987c-106">For more information about supported data sources and providers, see [Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="a987c-107">Der Tabellenimport-Assistent unterstützt das Importieren von Daten aus den folgenden Datenquellen:</span><span class="sxs-lookup"><span data-stu-id="a987c-107">The Table Import Wizard supports importing data from the following data sources:</span></span>  
  
 <span data-ttu-id="a987c-108">**Relationale Datenbanken**</span><span class="sxs-lookup"><span data-stu-id="a987c-108">**Relational Databases**</span></span>  
  
-   <span data-ttu-id="a987c-109">Microsoft SQL Server-Datenbank</span><span class="sxs-lookup"><span data-stu-id="a987c-109">Microsoft SQL Server database</span></span>  
  
-   <span data-ttu-id="a987c-110">Microsoft SQL Azure</span><span class="sxs-lookup"><span data-stu-id="a987c-110">Microsoft SQL Azure</span></span>  
  
-   <span data-ttu-id="a987c-111">Microsoft Access-Datenbank</span><span class="sxs-lookup"><span data-stu-id="a987c-111">Microsoft Access database</span></span>  
  
-   <span data-ttu-id="a987c-112">Microsoft SQL Server Parallel Data Warehouse</span><span class="sxs-lookup"><span data-stu-id="a987c-112">Microsoft SQL Server Parallel Data Warehouse</span></span>  
  
-   <span data-ttu-id="a987c-113">Oracle</span><span class="sxs-lookup"><span data-stu-id="a987c-113">Oracle</span></span>  
  
-   <span data-ttu-id="a987c-114">Teradata</span><span class="sxs-lookup"><span data-stu-id="a987c-114">Teradata</span></span>  
  
-   <span data-ttu-id="a987c-115">Sybase</span><span class="sxs-lookup"><span data-stu-id="a987c-115">Sybase</span></span>  
  
-   <span data-ttu-id="a987c-116">Informix</span><span class="sxs-lookup"><span data-stu-id="a987c-116">Informix</span></span>  
  
-   <span data-ttu-id="a987c-117">IBM DB2</span><span class="sxs-lookup"><span data-stu-id="a987c-117">IBM DB2</span></span>  
  
-   <span data-ttu-id="a987c-118">OLE DB/ODBC</span><span class="sxs-lookup"><span data-stu-id="a987c-118">OLE DB/ODBC</span></span>  
  
 <span data-ttu-id="a987c-119">**Mehrdimensionale Quellen**</span><span class="sxs-lookup"><span data-stu-id="a987c-119">**Multidimensional Sources**</span></span>  
  
-   <span data-ttu-id="a987c-120">Microsoft SQL Server Analysis Services-Cube</span><span class="sxs-lookup"><span data-stu-id="a987c-120">Microsoft SQL Server Analysis Services cube</span></span>  
  
 <span data-ttu-id="a987c-121">Der Tabellenimport-Assistent unterstützt keine Datenimporte, bei denen eine [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] -Arbeitsmappe als Datenquelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a987c-121">The Table Import Wizard does not support importing data from a [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] Workbook as a data source.</span></span>  
  
### <a name="to-import-data-from-a-database"></a><span data-ttu-id="a987c-122">So importieren Sie Daten aus einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="a987c-122">To import data from a database</span></span>  
  
1.  <span data-ttu-id="a987c-123">Klicken Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]auf das Menü **Modell** und dann auf **Aus Datenquelle importieren**.</span><span class="sxs-lookup"><span data-stu-id="a987c-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click the **Model** menu, and then click **Import from Data Source**.</span></span>  
  
2.  <span data-ttu-id="a987c-124">Wählen Sie auf der Seite **Mit einer Datenquelle verbinden** den Typ der Datenbank aus, mit der eine Verbindung hergestellt werden soll, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a987c-124">On the **Connect to a Data Source** page, select the type of database to connect to, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="a987c-125">Führen Sie die Schritte im Tabellenimport-Assistenten aus.</span><span class="sxs-lookup"><span data-stu-id="a987c-125">Follow the steps in the Table Import Wizard.</span></span> <span data-ttu-id="a987c-126">Auf den nachfolgenden Seiten können Sie bestimmte Tabellen und Sichten auswählen, oder Sie können Filter anwenden, indem Sie die Seite **Tabellen und Sichten auswählen** verwenden oder eine SQL-Abfrage auf der Seite **SQL-Abfrage angeben** erstellen.</span><span class="sxs-lookup"><span data-stu-id="a987c-126">On subsequent pages, you will be able to select specific tables and views or apply filters by using the **Select Tables and Views** page or by creating a SQL query on **Specify a SQL Query** page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a987c-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a987c-127">See Also</span></span>  
 <span data-ttu-id="a987c-128">[Importieren von Daten &#40;tabellarischen SSAS-&#41;](import-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="a987c-128">[Import Data &#40;SSAS Tabular&#41;](import-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="a987c-129">Unterstützte Datenquellen &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="a987c-129">Data Sources Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-sources-supported-ssas-tabular.md)  
  
  
