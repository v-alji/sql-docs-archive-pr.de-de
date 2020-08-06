---
title: Vorschau der ausgewählten Tabelle (SSAS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.previewselecttable.f1
ms.assetid: b6b34b5a-43b3-4a75-9f3b-b2ad1084b1b6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25eb4d4424223449052ab1f65b41cf270da81fb0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725057"
---
# <a name="preview-selected-table-ssas"></a><span data-ttu-id="276f4-102">Vorschau der ausgewählten Tabelle (SSAS)</span><span class="sxs-lookup"><span data-stu-id="276f4-102">Preview Selected Table (SSAS)</span></span>
  <span data-ttu-id="276f4-103">Auf dieser Seite des **Tabellenimport-Assistenten** können Sie die Daten in der ausgewählten Tabelle in der Vorschau anzeigen, die Spalten auswählen, die im Datenimport enthalten sein sollen, und Daten in den ausgewählten Spalten filtern.</span><span class="sxs-lookup"><span data-stu-id="276f4-103">This page of the **Table Import Wizard** enables you to preview the data in the selected table, to select the columns to include in the data import, and to filter data in the selected columns.</span></span> <span data-ttu-id="276f4-104">Um im [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf den Assistenten zuzugreifen, klicken Sie im Menü **Modell** auf **Aus Datenquelle importieren**.</span><span class="sxs-lookup"><span data-stu-id="276f4-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="276f4-105">Nicht alle Zeilen in der Tabelle werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="276f4-105">Not all the rows in the table are displayed.</span></span> <span data-ttu-id="276f4-106">Die festgelegten Filter werden jedoch während des Imports auf alle Daten in der Tabelle angewendet.</span><span class="sxs-lookup"><span data-stu-id="276f4-106">However, the filters that you set will be applied to all of the data in the table during import.</span></span>  
  
 <span data-ttu-id="276f4-107">Für Datenquellen mit Windows-Authentifizierung werden die Anmeldeinformationen des aktuellen Benutzers verwendet, um die im Dialogfeld Vorschau anzeigen und filtern angezeigten Daten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="276f4-107">For data sources using Windows authentication, the credentials of the current user are used to fetch the data displayed in the Preview and Filter dialog.</span></span> <span data-ttu-id="276f4-108">Für andere Datenquellen werden die in der Verbindungszeichenfolge angegebenen Anmeldeinformationen zum Abrufen der Daten verwendet.</span><span class="sxs-lookup"><span data-stu-id="276f4-108">For other data sources, the credentials supplied in the connection string are used to fetch the data.</span></span>  
  
 <span data-ttu-id="276f4-109">Die Darstellung der Daten auf dieser Seite garantiert nicht, dass der Import erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="276f4-109">The appearance of data on this page does not guarantee import will succeed.</span></span> <span data-ttu-id="276f4-110">Der Import ist nicht erfolgreich, wenn der auf der Seite Identitätswechselinformationen angegebene Benutzername nicht über ausreichend Berechtigungen zum Lesen aus der ausgewählten Datenbank verfügt.</span><span class="sxs-lookup"><span data-stu-id="276f4-110">If the user name specified in the Impersonation Information page does not have sufficient privileges to read from the selected database, import will fail.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="276f4-111">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="276f4-111">UI element list</span></span>  
 <span data-ttu-id="276f4-112">**Kontrollkästchen in der Spaltenüberschrift**</span><span class="sxs-lookup"><span data-stu-id="276f4-112">**Checkbox in the column header**</span></span>  
 <span data-ttu-id="276f4-113">Aktivieren Sie das Kontrollkästchen, um die Spalte in den Datenimport einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="276f4-113">Select the checkbox to include the column in the data import.</span></span> <span data-ttu-id="276f4-114">Deaktivieren Sie das Kontrollkästchen, um die Spalte aus dem Datenimport zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="276f4-114">Clear the checkbox to remove the column from the data import.</span></span>  
  
 <span data-ttu-id="276f4-115">**Schaltfläche mit Abwärtspfeil in der Spaltenüberschrift**</span><span class="sxs-lookup"><span data-stu-id="276f4-115">**Down-arrow button in the column header**</span></span>  
 <span data-ttu-id="276f4-116">Filtern Sie Daten in der Spalte.</span><span class="sxs-lookup"><span data-stu-id="276f4-116">Filter data in the column.</span></span>  
  
 <span data-ttu-id="276f4-117">**Zeilenfilter löschen**</span><span class="sxs-lookup"><span data-stu-id="276f4-117">**Clear Row Filters**</span></span>  
 <span data-ttu-id="276f4-118">Entfernen Sie alle Filter, die auf die Daten in den Spalten angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="276f4-118">Remove all filters that were applied to the data in the columns.</span></span>  
  
  
