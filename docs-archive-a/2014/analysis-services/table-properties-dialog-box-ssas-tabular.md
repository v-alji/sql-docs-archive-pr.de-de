---
title: Tabellen Eigenschaften (Dialog Feld) (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.ssmsimbi.TableProperties.f1
ms.assetid: 77571ccd-bdba-4e07-af55-465509dc6a33
author: minewiskan
ms.author: owend
ms.openlocfilehash: e3ca6d787616821532b30af0fe3591f79d6dbea6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616717"
---
# <a name="table-properties-dialog-box-ssas---tabular"></a><span data-ttu-id="01ea4-102">Tabelleneigenschaften (Dialogfeld, SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="01ea4-102">Table Properties Dialog Box (SSAS - Tabular)</span></span>
  <span data-ttu-id="01ea4-103">Verwenden Sie das Dialogfeld **Tabelleneigenschaften** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , um die Eigenschaften einer Tabelle in einer Tabellenmodelldatenbank anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="01ea4-103">Use the **Table Properties** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to view the properties of a table in a tabular model database.</span></span> <span data-ttu-id="01ea4-104">Alle Eigenschaften sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="01ea4-104">All properties are read-only.</span></span>  
  
 <span data-ttu-id="01ea4-105">Zum Anzeigen des Dialogfelds **Tabelleneigenschaften** klicken Sie im Objekt-Explorer mit der rechten Maustaste auf eine Tabelle und wählen die Option **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="01ea4-105">You can display the **Table Properties** dialog box by right-clicking a table in Object Explorer and selecting **Properties**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="01ea4-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="01ea4-106">Options</span></span>  
  
|<span data-ttu-id="01ea4-107">Begriff</span><span class="sxs-lookup"><span data-stu-id="01ea4-107">Term</span></span>|<span data-ttu-id="01ea4-108">Definition</span><span class="sxs-lookup"><span data-stu-id="01ea4-108">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="01ea4-109">**Name**</span><span class="sxs-lookup"><span data-stu-id="01ea4-109">**Name**</span></span>|<span data-ttu-id="01ea4-110">Zeigt den Namen der Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="01ea4-110">Displays the name of the table.</span></span>|  
|<span data-ttu-id="01ea4-111">**ID**</span><span class="sxs-lookup"><span data-stu-id="01ea4-111">**ID**</span></span>|<span data-ttu-id="01ea4-112">Zeigt den Bezeichner der Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="01ea4-112">Displays the identifier of the table.</span></span>|  
|<span data-ttu-id="01ea4-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="01ea4-113">**Description**</span></span>|<span data-ttu-id="01ea4-114">Zeigt die Beschreibung der Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="01ea4-114">Displays the description of the table.</span></span>|  
|<span data-ttu-id="01ea4-115">**Timestamp erstellen**</span><span class="sxs-lookup"><span data-stu-id="01ea4-115">**Create Timestamp**</span></span>|<span data-ttu-id="01ea4-116">Zeigt das Datum und die Uhrzeit der Erstellung der Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="01ea4-116">Displays the date and time the table was created.</span></span>|  
|<span data-ttu-id="01ea4-117">**Letztes Schemaupdate**</span><span class="sxs-lookup"><span data-stu-id="01ea4-117">**Last Schema Update**</span></span>|<span data-ttu-id="01ea4-118">Zeigt das Datum und die Uhrzeit des letzten Updates der Metadaten für die Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="01ea4-118">Displays the date and time the metadata for the table was last updated.</span></span>|  
|<span data-ttu-id="01ea4-119">**State**</span><span class="sxs-lookup"><span data-stu-id="01ea4-119">**State**</span></span>|<span data-ttu-id="01ea4-120">Zeigt den Verarbeitungsstatus der Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="01ea4-120">Displays the processing state of the table.</span></span> <span data-ttu-id="01ea4-121">Weitere Informationen zu den Werten für diese Eigenschaft finden Sie unter <xref:Microsoft.AnalysisServices.ProcessableMajorObject.State%2A>.</span><span class="sxs-lookup"><span data-stu-id="01ea4-121">For more information about the values for this property, see <xref:Microsoft.AnalysisServices.ProcessableMajorObject.State%2A>.</span></span>|  
|<span data-ttu-id="01ea4-122">**Zuletzt verarbeitet**</span><span class="sxs-lookup"><span data-stu-id="01ea4-122">**Last Processed**</span></span>|<span data-ttu-id="01ea4-123">Zeigt das Datum und die Uhrzeit an, zu der die Tabelle zuletzt verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="01ea4-123">Displays the date and time the table was last processed.</span></span>|  
|<span data-ttu-id="01ea4-124">**Aktueller Speichermodus**</span><span class="sxs-lookup"><span data-stu-id="01ea4-124">**Current Storage Mode**</span></span>|<span data-ttu-id="01ea4-125">Zeigt den aktuellen Speichermodus der Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="01ea4-125">Displays the current storage mode for the table.</span></span> <span data-ttu-id="01ea4-126">Der Speichermodus wird auf Datenbankebene festgelegt und wird von allen Tabellen geerbt.</span><span class="sxs-lookup"><span data-stu-id="01ea4-126">Storage mode is set at the database level and inherited by all tables.</span></span> <span data-ttu-id="01ea4-127">Sie können keine anderen Speichermodi auf Tabellenebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="01ea4-127">You cannot use different storage modes at the table level.</span></span> <span data-ttu-id="01ea4-128">Gültige Werte sind InMemory (Standard), InMemoryWithDirectQuery, DirectQuery, DirectQueryWithinMemory.</span><span class="sxs-lookup"><span data-stu-id="01ea4-128">Valid values are InMemory (default), InMemoryWithDirectQuery, DirectQuery, DirectQueryWithinMemory.</span></span>|  
  
  
