---
title: Dialog Feld "Datenquellen Eigenschaften", "Allgemein" | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.datasourceproperties.general.f1
- "10120"
ms.assetid: 44b5edd3-5c11-4d3d-91b8-5871aa0572ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c79ad70cdd4dcb10e1abce1102fa39eef4c67461
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608403"
---
# <a name="data-source-properties-dialog-box-general"></a><span data-ttu-id="2cd95-102">Datenquelleneigenschaften (Dialogfeld), Allgemein</span><span class="sxs-lookup"><span data-stu-id="2cd95-102">Data Source Properties Dialog Box, General</span></span>
  <span data-ttu-id="2cd95-103">Mithilfe der Registerkarte **Allgemein** im Dialogfeld **Datenquelleneigenschaften** können Sie die Verbindungsinformationen für eine Datenquelle im Bericht anzeigen und ändern.</span><span class="sxs-lookup"><span data-stu-id="2cd95-103">Select **General** on the **Data Source Properties** dialog box to display and modify connection information for a data source in the report.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2cd95-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="2cd95-104">Options</span></span>  
 <span data-ttu-id="2cd95-105">**Name**</span><span class="sxs-lookup"><span data-stu-id="2cd95-105">**Name**</span></span>  
 <span data-ttu-id="2cd95-106">Geben Sie den Namen der Datenquelle ein.</span><span class="sxs-lookup"><span data-stu-id="2cd95-106">Type the name of the data source.</span></span> <span data-ttu-id="2cd95-107">Der Datenquellenname muss innerhalb des Berichts eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="2cd95-107">The data source name must be unique within the report.</span></span> <span data-ttu-id="2cd95-108">Standardmäßig wird der Datenquelle ein allgemeiner Name, wie DataSource1 oder DataSource2, zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="2cd95-108">By default, a general name, such as DataSource1 or DataSource2, is assigned to the data source.</span></span>  
  
 <span data-ttu-id="2cd95-109">**Eingebettete Verbindung**</span><span class="sxs-lookup"><span data-stu-id="2cd95-109">**Embedded connection**</span></span>  
 <span data-ttu-id="2cd95-110">Aktivieren Sie diese Option, wenn Sie keine freigegebene Datenquelle verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="2cd95-110">Select this option when you do not want to use a shared data source.</span></span>  
  
 <span data-ttu-id="2cd95-111">**Type**</span><span class="sxs-lookup"><span data-stu-id="2cd95-111">**Type**</span></span>  
 <span data-ttu-id="2cd95-112">Wählen Sie eine Datenverarbeitungserweiterung aus.</span><span class="sxs-lookup"><span data-stu-id="2cd95-112">Select a data processing extension.</span></span> <span data-ttu-id="2cd95-113">In der Liste werden alle registrierten Erweiterungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="2cd95-113">The list displays all registered extensions.</span></span>  
  
 <span data-ttu-id="2cd95-114">**Verbindungszeichenfolge**</span><span class="sxs-lookup"><span data-stu-id="2cd95-114">**Connection string**</span></span>  
 <span data-ttu-id="2cd95-115">Geben Sie eine Verbindungszeichenfolge für die Datenquelle ein.</span><span class="sxs-lookup"><span data-stu-id="2cd95-115">Enter a connection string for the data source.</span></span> <span data-ttu-id="2cd95-116">Klicken Sie auf **Bearbeiten** , um die Verbindungszeichenfolge mithilfe des Dialogfeldes **Verbindungseigenschaften** zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2cd95-116">Click **Edit** to build the connection string using the **Connection Properties** dialog box.</span></span> <span data-ttu-id="2cd95-117">Klicken Sie auf die Schaltfläche **Ausdruck** (*fx*), um den Ausdruck zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="2cd95-117">Click the **Expressions** (*fx*) button to edit the expression.</span></span>  
  
 <span data-ttu-id="2cd95-118">**Freigegebenen Datenquellenverweis verwenden**</span><span class="sxs-lookup"><span data-stu-id="2cd95-118">**Use shared data source reference**</span></span>  
 <span data-ttu-id="2cd95-119">Wählen Sie diese Option aus, um einen Link zu einer freigegebenen Datenquelle herzustellen.</span><span class="sxs-lookup"><span data-stu-id="2cd95-119">Select this option to link to a shared data source.</span></span> <span data-ttu-id="2cd95-120">Wählen Sie in der Dropdownliste eine freigegebene Datenquelle aus.</span><span class="sxs-lookup"><span data-stu-id="2cd95-120">Select a shared data source from the drop-down list.</span></span> <span data-ttu-id="2cd95-121">Um die ausgewählte Datenquelle zu bearbeiten, klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="2cd95-121">To edit the selected data source, click **Edit**.</span></span> <span data-ttu-id="2cd95-122">Falls die Option **Freigegebenen Datenquellenverweis verwenden** aktiviert ist, sind die Optionen **Typ** und **Verbindungszeichenfolge** deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2cd95-122">If **Use shared data source reference** is selected, **Type** and **Connection string** are disabled.</span></span>  
  
 <span data-ttu-id="2cd95-123">**Einzelne Transaktion bei der Verarbeitung der Abfragen verwenden**</span><span class="sxs-lookup"><span data-stu-id="2cd95-123">**Use a single transaction when processing the queries**</span></span>  
 <span data-ttu-id="2cd95-124">Wählen Sie diese Option, um anzugeben, dass Datasets, die diese Datenquelle verwenden, in einer einzelnen Transaktion für die Datenbank ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2cd95-124">Select this option to indicate that datasets that use this data source are run in a single transaction against the database.</span></span> <span data-ttu-id="2cd95-125">Um Transaktionen für Unterberichte, die die gleiche Datenquelle verwenden, einzuschließen, setzen Sie die Option **MergeTransactions** im Eigenschaftenabschnitt **Sonstige** des Unterberichts im Bereich **Eigenschaften** auf **True** .</span><span class="sxs-lookup"><span data-stu-id="2cd95-125">To include transactions for subreports that use the same data source, set **MergeTransactions** to **True** in the subreport's **Other** properties section of the **Properties** pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cd95-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2cd95-126">See Also</span></span>  
 <span data-ttu-id="2cd95-127">[Hinzufügen von Daten zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2cd95-127">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-data/report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="2cd95-128">[Erstellen einer eingebetteten oder freigegebenen Datenquelle &#40;SSRS-&#41;](../../2014/reporting-services/create-an-embedded-or-shared-data-source-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2cd95-128">[Create an Embedded or Shared Data Source &#40;SSRS&#41;](../../2014/reporting-services/create-an-embedded-or-shared-data-source-ssrs.md) </span></span>  
 <span data-ttu-id="2cd95-129">[Datenverbindungen, Datenquellen und Verbindungs Zeichenfolgen in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="2cd95-129">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="2cd95-130">Datenquelleneigenschaften (Dialogfeld), Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="2cd95-130">Data Source Properties Dialog Box, Credentials</span></span>](../../2014/reporting-services/data-source-properties-dialog-box-credentials.md)  
  
  
