---
title: Tabellen Eigenschaften (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.tableprop.f1
ms.assetid: 16d3347b-7e43-4a6b-9956-fdd6ede092e6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9613609c42de8fd3a4aab7aec3208dfe3d31be4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723106"
---
# <a name="table-properties-ssas-tabular"></a><span data-ttu-id="486ec-102">Tabelleneigenschaften (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="486ec-102">Table Properties (SSAS Tabular)</span></span>
  <span data-ttu-id="486ec-103">In diesem Thema werden Tabelleneigenschaften für tabellarische Modelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="486ec-103">This topic describes tabular model table properties.</span></span> <span data-ttu-id="486ec-104">Die hier beschriebenen Eigenschaften unterscheiden sich von den Eigenschaften im Dialogfeld Tabelleneigenschaften bearbeiten, mit denen definiert wird, welche Spalten aus der Quelle importiert werden.</span><span class="sxs-lookup"><span data-stu-id="486ec-104">The properties described here are different from those in the Edit Table Properties dialog box, which define which columns from the source are imported.</span></span>  
  
 <span data-ttu-id="486ec-105">Abschnitte in diesem Thema:</span><span class="sxs-lookup"><span data-stu-id="486ec-105">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="486ec-106">Tabellen Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="486ec-106">Table Properties</span></span>](#bkmk_properties)  
  
-   [<span data-ttu-id="486ec-107">So konfigurieren Sie Einstellungen für Tabelleneigenschaften</span><span class="sxs-lookup"><span data-stu-id="486ec-107">To configure table property settings</span></span>](#bkmk_config_prop)  
  
##  <a name="table-properties"></a><a name="bkmk_properties"></a><span data-ttu-id="486ec-108">Tabellen Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="486ec-108">Table Properties</span></span>  
 <span data-ttu-id="486ec-109">**Grundlegend**</span><span class="sxs-lookup"><span data-stu-id="486ec-109">**Basic**</span></span>  
  
|<span data-ttu-id="486ec-110">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="486ec-110">Property</span></span>|<span data-ttu-id="486ec-111">Standardeinstellung</span><span class="sxs-lookup"><span data-stu-id="486ec-111">Default Setting</span></span>|<span data-ttu-id="486ec-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="486ec-112">Description</span></span>|  
|--------------|---------------------|-----------------|  
|<span data-ttu-id="486ec-113">**Verbindungsname**</span><span class="sxs-lookup"><span data-stu-id="486ec-113">**Connection Name**</span></span>|\<connection name>|<span data-ttu-id="486ec-114">Der Name der Verbindung mit der Datenquelle der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="486ec-114">The name of the connection to the table's data source.</span></span><br /><br /> <span data-ttu-id="486ec-115">Klicken Sie auf die Schaltfläche, um die Verbindung zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="486ec-115">To edit the connection, click the button.</span></span>|  
|<span data-ttu-id="486ec-116">**Hidden**</span><span class="sxs-lookup"><span data-stu-id="486ec-116">**Hidden**</span></span>|<span data-ttu-id="486ec-117">False</span><span class="sxs-lookup"><span data-stu-id="486ec-117">False</span></span>|<span data-ttu-id="486ec-118">Gibt an, ob die Tabelle in den Feldlisten von Berichtserstellungsclients ausgeblendet wird.</span><span class="sxs-lookup"><span data-stu-id="486ec-118">Specifies whether the table is hidden from reporting client field lists.</span></span>|  
|<span data-ttu-id="486ec-119">**Partitionen**</span><span class="sxs-lookup"><span data-stu-id="486ec-119">**Partitions**</span></span>||<span data-ttu-id="486ec-120">Partitionen für die Tabelle können nicht im **Eigenschaftenfenster** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="486ec-120">Partitions for the table cannot be displayed in the **Properties** window.</span></span> <span data-ttu-id="486ec-121">Klicken Sie zum Anzeigen, Erstellen oder Bearbeiten von Partitionen auf die Schaltfläche, um den Partitions-Manager zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="486ec-121">To view, create, or edit partitions, click the button to open the Partition Manager.</span></span>|  
|<span data-ttu-id="486ec-122">**Quelldaten**</span><span class="sxs-lookup"><span data-stu-id="486ec-122">**Source Data**</span></span>||<span data-ttu-id="486ec-123">Quelldaten für die Tabelle können nicht im **Eigenschaftenfenster** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="486ec-123">Source data for the table cannot be displayed in the **Properties** window.</span></span> <span data-ttu-id="486ec-124">Klicken Sie zum Anzeigen oder Bearbeiten der Quelldaten auf die Schaltfläche, um das Dialogfeld Tabelleneigenschaften bearbeiten zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="486ec-124">To view or edit the source data, click the button to open the Edit Table Properties dialog box.</span></span>|  
|<span data-ttu-id="486ec-125">**Tabellenbeschreibung**</span><span class="sxs-lookup"><span data-stu-id="486ec-125">**Table Description**</span></span>||<span data-ttu-id="486ec-126">Eine Textbeschreibung für die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="486ec-126">A text description for the table.</span></span><br /><br /> <span data-ttu-id="486ec-127">Wenn ein Endbenutzer in [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)]den Cursor über dieser Tabelle in der Feldliste platziert, wird die Beschreibung als QuickInfo angezeigt.</span><span class="sxs-lookup"><span data-stu-id="486ec-127">In [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], if an end-user places the cursor over this table in the field list, the description appears as a tooltip.</span></span>|  
|<span data-ttu-id="486ec-128">**Tabellenname**</span><span class="sxs-lookup"><span data-stu-id="486ec-128">**Table Name**</span></span>|\<friendly name>|<span data-ttu-id="486ec-129">Gibt den anzeigen amen der Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="486ec-129">Specifies the table's friendly name.</span></span> <span data-ttu-id="486ec-130">Der Tabellenname kann angegeben werden, wenn eine Tabelle mit dem Tabellenimport-Assistenten importiert wird, oder jederzeit nach dem Import.</span><span class="sxs-lookup"><span data-stu-id="486ec-130">The table name can be specified when a table is imported using the Table Import Wizard or at any time after import.</span></span> <span data-ttu-id="486ec-131">Der Tabellenname im Modell kann sich von der zugeordneten Tabelle am Quellort unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="486ec-131">The table name in the model can be different from the associated table at the source.</span></span> <span data-ttu-id="486ec-132">Der Anzeigename der Tabelle wird in der Feldliste einer Clientanwendung zur Berichterstellung sowie in der Modelldatenbank in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]angezeigt.</span><span class="sxs-lookup"><span data-stu-id="486ec-132">The table friendly name appears in the reporting client application field list as well as in the model database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>|  
  
 <span data-ttu-id="486ec-133">**Berichterstellungseigenschaften**</span><span class="sxs-lookup"><span data-stu-id="486ec-133">**Reporting Properties**</span></span>  
  
 <span data-ttu-id="486ec-134">Ausführliche Beschreibungen und Informationen zur Konfiguration für Berichterstellungseigenschaften finden Sie unter [Power View-Berichterstellungseigenschaften &#40;SSAS – tabellarisch&#41;](properties-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="486ec-134">For detailed descriptions and configuration information for reporting properties, see [Power View Reporting Properties &#40;SSAS Tabular&#41;](properties-ssas-tabular.md).</span></span>  
  
|<span data-ttu-id="486ec-135">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="486ec-135">Property</span></span>|<span data-ttu-id="486ec-136">Standardeinstellung</span><span class="sxs-lookup"><span data-stu-id="486ec-136">Default Setting</span></span>|<span data-ttu-id="486ec-137">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="486ec-137">Description</span></span>|  
|--------------|---------------------|-----------------|  
|<span data-ttu-id="486ec-138">**Standardfeldsatz**</span><span class="sxs-lookup"><span data-stu-id="486ec-138">**Default Field Set**</span></span>|||  
|<span data-ttu-id="486ec-139">Tabellenverhalten</span><span class="sxs-lookup"><span data-stu-id="486ec-139">Table Behavior</span></span>|||  
  
###  <a name="to-configure-table-property-settings"></a><a name="bkmk_config_prop"></a><span data-ttu-id="486ec-140">So konfigurieren Sie Einstellungen für Tabellen Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="486ec-140">To configure table property settings</span></span>  
  
1.  <span data-ttu-id="486ec-141">Klicken Sie im Modell-Designer in der Datensicht auf eine Tabelle (Registerkarte) oder in der Diagrammsicht auf einen Tabellenkopf.</span><span class="sxs-lookup"><span data-stu-id="486ec-141">In the model designer, in Data View, click a table (tab), or, in Diagram View, click a table header.</span></span>  
  
2.  <span data-ttu-id="486ec-142">Klicken Sie im **Eigenschaftenfenster** auf eine Eigenschaft, und geben Sie einen Wert ein, oder klicken Sie auf die Schaltfläche für weitere Konfigurationsoptionen.</span><span class="sxs-lookup"><span data-stu-id="486ec-142">In the **Properties** window, click on a property, and then type a value or click the button for additional configuration options.</span></span>  
  
  
