---
title: Tabellen und Sichten auswählen (SSAS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.seltablesviews.f1
ms.assetid: 5e8121cc-03f0-4168-98cf-63c5c032bb0b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 891da51478670122f5dbce8fdd7be55c98c898c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723154"
---
# <a name="select-tables-and-views-ssas"></a><span data-ttu-id="b2726-102">Tabellen und Sichten auswählen (SSAS)</span><span class="sxs-lookup"><span data-stu-id="b2726-102">Select Tables and Views (SSAS)</span></span>
  <span data-ttu-id="b2726-103">Auf dieser Seite des **Tabellenimport-Assistenten** können Sie die Tabellen und Sichten auswählen, aus denen Daten importiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b2726-103">This page of the **Table Import Wizard** enables you to select the tables and views that you want to import data from.</span></span> <span data-ttu-id="b2726-104">Um im [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf den Assistenten zuzugreifen, klicken Sie im Menü **Modell** auf **Aus Datenquelle importieren**.</span><span class="sxs-lookup"><span data-stu-id="b2726-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="b2726-105">Die Darstellung von Tabellen und Sichten auf dieser Seite garantiert nicht, dass der Import erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="b2726-105">The appearance of tables and views on this page does not guarantee that import will succeed.</span></span> <span data-ttu-id="b2726-106">Der Import ist nicht erfolgreich, wenn der auf der Seite Identitätswechselinformationen angegebene Benutzer nicht über ausreichend Berechtigungen zum Lesen aus der ausgewählten Datenbank verfügt.</span><span class="sxs-lookup"><span data-stu-id="b2726-106">If the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database, import will fail.</span></span>  
  
 <span data-ttu-id="b2726-107">Für Datenquellen mit Windows-Authentifizierung werden die Anmeldeinformationen des aktuellen Benutzers verwendet, um die Tabellen und die Sichten im Dialogfeld Tabellen und Sichten auswählen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b2726-107">For data sources using Windows authentication, the credentials of the current user are used to fetch the tables and views in the Select Tables and Views dialog.</span></span> <span data-ttu-id="b2726-108">Für andere Datenquellen werden die in der Verbindungszeichenfolge angegebenen Anmeldeinformationen zum Abrufen der Daten verwendet.</span><span class="sxs-lookup"><span data-stu-id="b2726-108">For other data sources, the credentials supplied in the connection string are used to fetch the data.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="b2726-109">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="b2726-109">UI element list</span></span>  
 <span data-ttu-id="b2726-110">**Server**</span><span class="sxs-lookup"><span data-stu-id="b2726-110">**Server**</span></span>  
 <span data-ttu-id="b2726-111">Zeigt den Server an, mit dem Sie verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="b2726-111">Displays the server that you are connected to.</span></span>  
  
 <span data-ttu-id="b2726-112">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="b2726-112">**Database**</span></span>  
 <span data-ttu-id="b2726-113">Zeigt die Datenbank an, die Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="b2726-113">Displays the database that you selected.</span></span>  
  
 <span data-ttu-id="b2726-114">**Tabellen und Sichten**</span><span class="sxs-lookup"><span data-stu-id="b2726-114">**Tables and Views**</span></span>  
 <span data-ttu-id="b2726-115">Führt die Tabellen und Sichten in der Datenbank auf.</span><span class="sxs-lookup"><span data-stu-id="b2726-115">Lists the tables and views in the database.</span></span> <span data-ttu-id="b2726-116">Aktivieren Sie das Kontrollkästchen neben jeder Tabelle und Sicht, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="b2726-116">Select the checkbox beside each table and view that you want to import.</span></span>  
  
 <span data-ttu-id="b2726-117">**Quell Tabelle**</span><span class="sxs-lookup"><span data-stu-id="b2726-117">**Source Table**</span></span>  
 <span data-ttu-id="b2726-118">Gibt den Namen der Quelltabelle auf Grundlage des Datenquellentyps an.</span><span class="sxs-lookup"><span data-stu-id="b2726-118">Specifies the name of the source table based on the type of data source.</span></span>  
  
 <span data-ttu-id="b2726-119">**Schema**</span><span class="sxs-lookup"><span data-stu-id="b2726-119">**Schema**</span></span>  
 <span data-ttu-id="b2726-120">Gibt das Schema an, in dem die Quelltabelle enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="b2726-120">Specifies the schema in which the source table is contained.</span></span> <span data-ttu-id="b2726-121">Je nach Typ der Datenbank funktioniert ein Schema als Container für andere Objekte, z. B. Tabellen, und kann auch den Besitzer dieser Objekte angeben.</span><span class="sxs-lookup"><span data-stu-id="b2726-121">Depending on the type of database, a schema functions as a container for other objects, such as tables, and can also indicate ownership of those objects.</span></span>  
  
 <span data-ttu-id="b2726-122">**Anzeigename**</span><span class="sxs-lookup"><span data-stu-id="b2726-122">**Friendly Name**</span></span>  
 <span data-ttu-id="b2726-123">Gibt den benutzerfreundlichen Namen der Quelltabelle an.</span><span class="sxs-lookup"><span data-stu-id="b2726-123">Specifies the friendly name of the source table.</span></span> <span data-ttu-id="b2726-124">Standardmäßig zeigt die Spalte den Namen der Quelltabelle aus der Spalte **Quelltabelle** an.</span><span class="sxs-lookup"><span data-stu-id="b2726-124">By default, the column displays the name of the source table that appears in the **Source Table** column.</span></span> <span data-ttu-id="b2726-125">Ändern Sie den Namen, wenn Sie einen anderen als den in der Quelldatenbank verwendeten Namen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="b2726-125">Change the name if you want to use a different name than the name used in the source database.</span></span>  
  
 <span data-ttu-id="b2726-126">**Filterdetails**</span><span class="sxs-lookup"><span data-stu-id="b2726-126">**Filter Details**</span></span>  
 <span data-ttu-id="b2726-127">Wenn ein Filter auf die importierten Daten angewendet wurde, wird der Datenimportfilter im Dialogfeld **Filterdetails** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b2726-127">When a filter has been applied to the data that is being imported, displays the data import filter in the **Filter Details** dialog box.</span></span> <span data-ttu-id="b2726-128">Weitere Informationen finden Sie unter [Filterdetails &#40;SSAS&#41;](filter-details-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="b2726-128">For more information, see [Filter Details &#40;SSAS&#41;](filter-details-ssas.md).</span></span>  
  
 <span data-ttu-id="b2726-129">**Vorschau anzeigen und filtern**</span><span class="sxs-lookup"><span data-stu-id="b2726-129">**Preview and Filter**</span></span>  
 <span data-ttu-id="b2726-130">Zeigt das Dialogfeld **Vorschau der ausgewählten Tabelle** an, das verwendet wird, um einen Filter auf die importierten Daten anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="b2726-130">Displays the **Preview Selected Table** dialog box that is used to apply a filter to the data that is being imported.</span></span> <span data-ttu-id="b2726-131">Weitere Informationen finden Sie unter [Vorschau der ausgewählten Tabelle &#40;SSAS&#41;](preview-selected-table-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="b2726-131">For more information, see [Preview Selected Table &#40;SSAS&#41;](preview-selected-table-ssas.md).</span></span>  
  
 <span data-ttu-id="b2726-132">**Verknüpfte Tabellen auswählen**</span><span class="sxs-lookup"><span data-stu-id="b2726-132">**Select Related Tables**</span></span>  
 <span data-ttu-id="b2726-133">Wählen Sie für den Import Tabellen und Sichten aus, die mit den Tabellen und Sichten verknüpft sind, die Sie bereits ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="b2726-133">Selects for import those tables and views that are related to the tables and views that you have already selected.</span></span>  
  
  
