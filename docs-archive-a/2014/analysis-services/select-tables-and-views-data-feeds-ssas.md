---
title: Tabellen und Sichten auswählen (Daten Feeds) (SSAS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.seltablesviewsdf.f1
ms.assetid: 6c4fafe0-e02e-47d1-b8bc-e70e872690af
author: minewiskan
ms.author: owend
ms.openlocfilehash: 46c317ecf2a87adcde264e8d6d7e822eb833b8b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616720"
---
# <a name="select-tables-and-views-data-feeds-ssas"></a><span data-ttu-id="6c06a-102">Tabellen und Sichten auswählen (Datenfeeds) (SSAS)</span><span class="sxs-lookup"><span data-stu-id="6c06a-102">Select Tables and Views (Data Feeds) (SSAS)</span></span>
  <span data-ttu-id="6c06a-103">Auf dieser Seite des **Tabellenimport-Assistenten** können Sie die Tabellen und Sichten auswählen, aus denen Daten importiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6c06a-103">This page of the **Table Import Wizard** enables you to select the tables and views that you want to import data from.</span></span> <span data-ttu-id="6c06a-104">Um im [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf den Assistenten zuzugreifen, klicken Sie im Menü **Modell** auf **Aus Datenquelle importieren**.</span><span class="sxs-lookup"><span data-stu-id="6c06a-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="6c06a-105">Die Darstellung von Tabellen und Sichten auf dieser Seite garantiert nicht, dass der Import erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="6c06a-105">The appearance of tables and views on this page does not guarantee that import will succeed.</span></span> <span data-ttu-id="6c06a-106">Der Import ist nicht erfolgreich, wenn der auf der Seite Identitätswechselinformationen angegebene Benutzer nicht über ausreichend Berechtigungen zum Lesen aus der ausgewählten Datenbank verfügt.</span><span class="sxs-lookup"><span data-stu-id="6c06a-106">If the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database, import will fail.</span></span>  
  
 <span data-ttu-id="6c06a-107">Für Datenquellen mit Windows-Authentifizierung werden die Anmeldeinformationen des aktuellen Benutzers verwendet, um die Tabellen und die Sichten im Dialogfeld Tabellen und Sichten auswählen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="6c06a-107">For data sources using Windows authentication, the credentials of the current user are used to fetch the tables and views in the Select Tables and Views dialog.</span></span> <span data-ttu-id="6c06a-108">Für andere Datenquellen werden die in der Verbindungszeichenfolge angegebenen Anmeldeinformationen zum Abrufen der Daten verwendet.</span><span class="sxs-lookup"><span data-stu-id="6c06a-108">For other data sources, the credentials supplied in the connection string are used to fetch the data.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="6c06a-109">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="6c06a-109">UI element list</span></span>  
 <span data-ttu-id="6c06a-110">**Datenfeed-URL**</span><span class="sxs-lookup"><span data-stu-id="6c06a-110">**Data feed URL**</span></span>  
 <span data-ttu-id="6c06a-111">Zeigt die URL für den Datenfeed an, den Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="6c06a-111">Displays the URL for the data feed that you selected.</span></span>  
  
 <span data-ttu-id="6c06a-112">**Tabellen und Sichten**</span><span class="sxs-lookup"><span data-stu-id="6c06a-112">**Tables and views**</span></span>  
 <span data-ttu-id="6c06a-113">Führt die Tabellen und Sichten im Datenfeed auf.</span><span class="sxs-lookup"><span data-stu-id="6c06a-113">Lists the tables and views in the data feed.</span></span> <span data-ttu-id="6c06a-114">Aktivieren Sie das Kontrollkästchen neben jeder Tabelle und Sicht, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="6c06a-114">Select the checkbox beside each table and view that you want to import.</span></span>  
  
 <span data-ttu-id="6c06a-115">**Quell Tabelle**</span><span class="sxs-lookup"><span data-stu-id="6c06a-115">**Source Table**</span></span>  
 <span data-ttu-id="6c06a-116">Gibt den Namen der Quelltabelle auf Grundlage des Datenquellentyps an.</span><span class="sxs-lookup"><span data-stu-id="6c06a-116">Specifies the name of the source table based on the type of data source.</span></span>  
  
 <span data-ttu-id="6c06a-117">**Anzeigename**</span><span class="sxs-lookup"><span data-stu-id="6c06a-117">**Friendly Name**</span></span>  
 <span data-ttu-id="6c06a-118">Gibt den benutzerfreundlichen Namen der Quelltabelle an.</span><span class="sxs-lookup"><span data-stu-id="6c06a-118">Specifies the friendly name of the source table.</span></span> <span data-ttu-id="6c06a-119">Standardmäßig zeigt die Spalte den Namen der Quelltabelle aus der Spalte **Quelltabelle** an.</span><span class="sxs-lookup"><span data-stu-id="6c06a-119">By default, the column displays the name of the source table that appears in the **Source Table** column.</span></span>  
  
 <span data-ttu-id="6c06a-120">**Filterdetails**</span><span class="sxs-lookup"><span data-stu-id="6c06a-120">**Filter Details**</span></span>  
 <span data-ttu-id="6c06a-121">Wenn ein Filter auf die importierten Daten angewendet wurde, wird der Datenimportfilter im Dialogfeld **Filterdetails** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6c06a-121">Displays the data import filter in the **Filter Details** dialog box, when a filter has been applied to the data that is being imported.</span></span> <span data-ttu-id="6c06a-122">Weitere Informationen finden Sie unter [Filterdetails &#40;SSAS&#41;](filter-details-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="6c06a-122">For more information, see [Filter Details &#40;SSAS&#41;](filter-details-ssas.md).</span></span>  
  
 <span data-ttu-id="6c06a-123">**Vorschau anzeigen und filtern**</span><span class="sxs-lookup"><span data-stu-id="6c06a-123">**Preview and Filter**</span></span>  
 <span data-ttu-id="6c06a-124">Zeigt das Dialogfeld **Vorschau der ausgewählten Tabelle** an, das verwendet wird, um einen Filter auf die importierten Daten anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="6c06a-124">Displays the **Preview Selected Table** dialog box that is used to apply a filter to the data that is being imported.</span></span> <span data-ttu-id="6c06a-125">Weitere Informationen finden Sie unter [Vorschau der ausgewählten Tabelle &#40;SSAS&#41;](preview-selected-table-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="6c06a-125">For more information, see [Preview Selected Table &#40;SSAS&#41;](preview-selected-table-ssas.md).</span></span>  
  
 <span data-ttu-id="6c06a-126">**Verknüpfte Tabellen auswählen**</span><span class="sxs-lookup"><span data-stu-id="6c06a-126">**Select Related Tables**</span></span>  
 <span data-ttu-id="6c06a-127">Wählen Sie Tabellen aus, die mit den Tabellen und Sichten verknüpft sind, die Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="6c06a-127">Select tables that are related to the tables and views that you have selected.</span></span>  
  
  
