---
title: Erstellen einer Data Mining-Abfrage mit XMLA | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content queries [DMX]
ms.assetid: 8f6b6008-006c-4792-9bd1-64c30dc3fd41
author: minewiskan
ms.author: owend
ms.openlocfilehash: d0e85b17db0781671fab0874706f12fdac95b30b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621749"
---
# <a name="create-a-data-mining-query-by-using-xmla"></a><span data-ttu-id="ba70b-102">Erstellen einer Data Mining-Abfrage mit XMLA</span><span class="sxs-lookup"><span data-stu-id="ba70b-102">Create a Data Mining Query by Using XMLA</span></span>
  <span data-ttu-id="ba70b-103">Abfragen für Data Mining-Objekte können Sie mithilfe von AMO, DMX oder XML/A erstellen.</span><span class="sxs-lookup"><span data-stu-id="ba70b-103">You can create a variety of queries against data mining objects by using AMO, DMX, or XML/A.</span></span>  
  
 <span data-ttu-id="ba70b-104">XML wird für die Kommunikation zwischen dem Analysis Services-Server und allen Clients benötigt.</span><span class="sxs-lookup"><span data-stu-id="ba70b-104">XML is used for communication between the Analysis Services server and all clients.</span></span> <span data-ttu-id="ba70b-105">Obwohl Inhaltsabfragen im Allgemeinen einfacher mit DMX erstellt werden können, können Sie Abfragen mit der DISCOVER- und der COMMAND-Anweisung in XML/A schreiben, indem Sie entweder einen Client verwenden, der das SOAP-Protokoll unterstützt, oder indem Sie eine XML/A-Abfrage in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]erstellen.</span><span class="sxs-lookup"><span data-stu-id="ba70b-105">Therefore, although it is generally much easier to create content queries by using DMX, you can write queries by using the DISCOVER and COMMAND statements in XML/A, either by using a client that supports the SOAP protocol, or by creating an XML/A query in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="ba70b-106">In diesem Thema wird beschrieben, wie Sie mit in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] verfügbaren XML/A-Vorlagen eine Modellinhaltsabfrage für ein Miningmodell erstellen, das auf dem aktuellen Server gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="ba70b-106">This topic explains how to use the XML/A templates that are available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create a model content query against a mining model stored on the current server.</span></span>  
  
## <a name="querying-data-mining-schema-rowsets-by-using-xmla"></a><span data-ttu-id="ba70b-107">Abfragen der Data Mining-Schemarowsets mit XML/A</span><span class="sxs-lookup"><span data-stu-id="ba70b-107">Querying Data Mining Schema Rowsets by Using XML/A</span></span>  
  
#### <a name="to-open-an-xmla-template"></a><span data-ttu-id="ba70b-108">So öffnen Sie eine XML/A-Vorlage</span><span class="sxs-lookup"><span data-stu-id="ba70b-108">To open an XML/A template</span></span>  
  
1.  <span data-ttu-id="ba70b-109">Klicken Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]im Menü **Ansicht** auf **Vorlagen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="ba70b-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="ba70b-110">Klicken Sie auf das Cubesymbol, um die Liste mit den Analysis-Services-Vorlagen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ba70b-110">Click the cube icon to open the list of Analysis Services templates.</span></span>  
  
3.  <span data-ttu-id="ba70b-111">Erweitern Sie in der Liste der Vorlagenkategorien den Eintrag **XMLA**, erweitern Sie **Schemarowsets**, und doppelklicken Sie auf **Discover Schema Rowsets** , um die Vorlage im zugehörigen Code-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ba70b-111">In the list of template categories, expand **XMLA**, expand **Schema Rowsets**, and double-click **Discover Schema Rowsets** to open the template in the appropriate code editor.</span></span>  
  
4.  <span data-ttu-id="ba70b-112">Vervollständigen Sie im Dialogfeld **Verbindung mit Analysis Services herstellen** die Verbindungseinstellungen, und klicken Sie dann auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="ba70b-112">In the **Connect to Analysis Services** dialog box, complete the connection information and then click **Connect**.</span></span> <span data-ttu-id="ba70b-113">Ein neues Fenster des Abfrage-Editors wird mit der Vorlage **Discover Schema Rowsets** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="ba70b-113">A new query editor window opens, populated with the **Discover Schema Rowsets** template.</span></span>  
  
#### <a name="to-discover-column-names-from-the-mining-model-content-schema-rowset"></a><span data-ttu-id="ba70b-114">So ermitteln Sie Spaltennamen aus dem MINING MODEL CONTENT-Schemarowset</span><span class="sxs-lookup"><span data-stu-id="ba70b-114">To discover column names from the MINING MODEL CONTENT schema rowset</span></span>  
  
1.  <span data-ttu-id="ba70b-115">Klicken Sie bei geöffneter **Discover Schema Rowsets** -Vorlage auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ba70b-115">With the **Discover Schema Rowsets** template open, click **Execute**.</span></span>  
  
     <span data-ttu-id="ba70b-116">Eine Liste der Schemarowsets wird im Fenster **Ergebnisse** zurückgegeben. Diese Liste enthält die Rowsetnamen und Rowsetspalten für alle in der aktuellen Instanz verfügbaren Rowsets.</span><span class="sxs-lookup"><span data-stu-id="ba70b-116">A list of schema rowsets is returned in the **Results** pane that contains the rowset names and rowset columns for all rowsets available on the current instance.</span></span>  
  
2.  <span data-ttu-id="ba70b-117">Platzieren Sie den Cursor im **Abfrage** Bereich nach, **\<Restriction List>** und drücken Sie die EINGABETASTE, um eine neue Zeile hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ba70b-117">In the **Query** pane, place the cursor after **\<Restriction List>** and press ENTER to add a new line.</span></span>  
  
3.  <span data-ttu-id="ba70b-118">Platzieren Sie den Cursor in die leere Zeile, und geben Sie \*\* \<SchemaName> DMSCHEMA_MINING_MODEL_CONTENT \</SchemaName> \*\*</span><span class="sxs-lookup"><span data-stu-id="ba70b-118">Place the cursor on the blank line and type **\<SchemaName>DMSCHEMA_MINING_MODEL_CONTENT\</SchemaName>**</span></span>  
  
     <span data-ttu-id="ba70b-119">Der vollständige Abschnitt für Einschränkungen sollte wie folgt angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="ba70b-119">The complete section for restrictions should appear as follows:</span></span>  
  
     `<Restrictions>`  
  
     `<RestrictionList>`  
  
     `<SchemaName>DMSCHEMA_MINING_MODEL_CONTENT</SchemaName>`  
  
     `</RestrictionList>`  
  
     `</Restrictions>`  
  
4.  <span data-ttu-id="ba70b-120">Klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ba70b-120">Click **Execute**.</span></span>  
  
     <span data-ttu-id="ba70b-121">Im Fenster **Ergebnisse** wird eine Liste der Spaltennamen für das angegebene Schemarowset angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba70b-121">The **Results** pane shows a list of column names for the specified schema rowset.</span></span>  
  
#### <a name="to-create-a-content-query-using-the-mining-model-content-schema-rowset"></a><span data-ttu-id="ba70b-122">So erstellen Sie eine Inhaltsabfrage mit dem MINING MODEL CONTENT-Schemarowset</span><span class="sxs-lookup"><span data-stu-id="ba70b-122">To create a content query using the MINING MODEL CONTENT schema rowset</span></span>  
  
1.  <span data-ttu-id="ba70b-123">Ändern Sie in der Vorlage **Discover Schema Rowsets** den Anforderungstyp, indem Sie den Text innerhalb der Tags für den Anforderungstyp ersetzen.</span><span class="sxs-lookup"><span data-stu-id="ba70b-123">In the **Discover Schema Rowsets** template, change the request type by replacing the text inside the request type tags.</span></span>  
  
     <span data-ttu-id="ba70b-124">Ersetzen Sie die Zeile:</span><span class="sxs-lookup"><span data-stu-id="ba70b-124">Replace this line:</span></span>  
  
     `<RequestType>DISCOVER_SCHEMA_ROWSETS</RequestType>`  
  
     <span data-ttu-id="ba70b-125">durch folgende Zeile:</span><span class="sxs-lookup"><span data-stu-id="ba70b-125">with the following line:</span></span>  
  
     <span data-ttu-id="ba70b-126">**\<RequestType>DMSCHEMA_MINING_MODEL_CONTENT\</RequestType>**</span><span class="sxs-lookup"><span data-stu-id="ba70b-126">**\<RequestType>DMSCHEMA_MINING_MODEL_CONTENT\</RequestType>**</span></span>  
  
2.  <span data-ttu-id="ba70b-127">Ändern Sie die Einschränkungsliste, um ein Miningmodell mit Namen anzugeben, indem Sie eine neue Bedingung zu den Einschränkungslisten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ba70b-127">Change the restriction list to specify a mining model by name, by adding a new condition to the restriction lists.</span></span>  
  
3.  <span data-ttu-id="ba70b-128">Positionieren Sie den Cursor in der Vorlage hinter `<Restriction List>` , und drücken Sie die Eingabetaste, um eine neue Zeile hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ba70b-128">In the template, place the cursor after `<Restriction List>` and press ENTER to add a new line.</span></span>  
  
4.  <span data-ttu-id="ba70b-129">Setzen Sie den Cursor in die leere Zeile, und geben Sie **<MODEL_NAME>My model name</MODEL_NAME>** ein.</span><span class="sxs-lookup"><span data-stu-id="ba70b-129">Place the cursor on the blank line and type **<MODEL_NAME>My model name</MODEL_NAME>**</span></span>  
  
     <span data-ttu-id="ba70b-130">Der vollständige Abschnitt für Einschränkungen sollte wie folgt angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="ba70b-130">The complete section for restrictions should appear as follows:</span></span>  
  
     `<Restrictions>`  
  
     `<RestrictionList>`  
  
     `<MODEL_NAME>My model name</MODEL_NAME>`  
  
     `</RestrictionList>`  
  
     `</Restrictions>`  
  
5.  <span data-ttu-id="ba70b-131">Klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ba70b-131">Click **Execute**.</span></span>  
  
     <span data-ttu-id="ba70b-132">Im Ergebnisbereich wird die Schemadefinition zusammen mit den Werten für das angegebene Modell angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba70b-132">The Results pane displays the schema definition, together with the values for the specified model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba70b-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ba70b-133">See Also</span></span>  
 <span data-ttu-id="ba70b-134">[Mining Modell Inhalt &#40;Analysis Services Data Mining-&#41;](mining-model-content-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="ba70b-134">[Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="ba70b-135">Data Mining Schema Rowsets</span><span class="sxs-lookup"><span data-stu-id="ba70b-135">Data Mining Schema Rowsets</span></span>](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/data-mining-schema-rowsets) 
  
  
