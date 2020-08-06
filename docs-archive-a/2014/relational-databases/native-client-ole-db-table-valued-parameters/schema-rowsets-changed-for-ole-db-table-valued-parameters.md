---
title: Schemarowsets für OLE DB-Tabellenwertparameter geändert | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- schema rowsets [OLE DB]
- table-valued parameters (OLE DB), schema rowsets changed for (OLE DB)
ms.assetid: 581e3ead-53db-44da-8718-f3fc4b5108f1
author: rothja
ms.author: jroth
ms.openlocfilehash: e09d5127f332c8b6cc948be3eeb74e600bb856f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723761"
---
# <a name="schema-rowsets-changed-for-ole-db-table-valued-parameters"></a><span data-ttu-id="60422-102">Schemarowsets für OLE DB-Tabellenwertparameter geändert</span><span class="sxs-lookup"><span data-stu-id="60422-102">Schema Rowsets Changed for OLE DB Table-Valued Parameters</span></span>
  <span data-ttu-id="60422-103">Folgende Schemarowsets wurden zur Unterstützung von Tabellenwertparametern geändert oder hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="60422-103">The following are the schema rowsets that have been changed or added to support table-valued parameters.</span></span>  
  
|<span data-ttu-id="60422-104">Schemarowset</span><span class="sxs-lookup"><span data-stu-id="60422-104">Schema rowset</span></span>|<span data-ttu-id="60422-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="60422-105">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="60422-106">DBSCHEMA_PROCEDURE_PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="60422-106">DBSCHEMA_PROCEDURE_PARAMETERS</span></span>|<span data-ttu-id="60422-107">Zwei neue Spalten namens SS_TYPE_CATALOG_NAME und SS_TYPE_SCHEMANAME wurden am Ende des Rowsets hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="60422-107">Two new columns were added at the end of the rowset named SS_TYPE_CATALOG_NAME and SS_TYPE_SCHEMANAME.</span></span> <span data-ttu-id="60422-108">Die folgenden Spalten konnten für zukünftige Typen wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="60422-108">These columns could be re-used for future types.</span></span> <span data-ttu-id="60422-109">Die Spalten TYPE_NAME und LOCAL_TYPE_NAME enthalten in Zukunft den Namen des TABLE-Tabellenwertparametertyps.</span><span class="sxs-lookup"><span data-stu-id="60422-109">The TYPE_NAME and LOCAL_TYPE_NAME columns will contain the name of the table-valued parameter TABLE type.</span></span> <span data-ttu-id="60422-110">Die DATA_TYPE-Spalte weist den Wert DBTYPE_TABLE = 143 für Tabellenwertparameter auf.</span><span class="sxs-lookup"><span data-stu-id="60422-110">The DATA_TYPE column will have value DBTYPE_TABLE = 143 for table-valued parameters.</span></span>|  
|<span data-ttu-id="60422-111">DBSCHEMA_TABLE_TYPES</span><span class="sxs-lookup"><span data-stu-id="60422-111">DBSCHEMA_TABLE_TYPES</span></span>|<span data-ttu-id="60422-112">Dieses Rowset wurde hinzugefügt, um die Unterstützung von Tabellenwertparametern zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="60422-112">This rowset was added to support table-valued parameters.</span></span> <span data-ttu-id="60422-113">Es ist mit DBSCHEMA_TABLES nahezu identisch, mit der Ausnahme, dass es Metadaten nur für Tabellentypen, nicht aber für Tabellen, Sichten oder Synonyme zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="60422-113">It is identical to DBSCHEMA_TABLES, except that it returns metadata only for table types, rather than for tables, views, or synonyms.</span></span> <span data-ttu-id="60422-114">Die TABLE_TYPE-Spalte weist den Wert 'TABLE TYPE' auf.</span><span class="sxs-lookup"><span data-stu-id="60422-114">The TABLE_TYPE column will have the value 'TABLE TYPE'.</span></span>|  
|<span data-ttu-id="60422-115">DBSCHEMA_TABLE_TYPE_PRIMARY_KEYS</span><span class="sxs-lookup"><span data-stu-id="60422-115">DBSCHEMA_TABLE_TYPE_PRIMARY_KEYS</span></span>|<span data-ttu-id="60422-116">Dieses Rowset wurde hinzugefügt, um die Unterstützung von Tabellenwertparametern zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="60422-116">This rowset was added to support table-valued parameters.</span></span> <span data-ttu-id="60422-117">Es ist mit DBSCHEMA_PRIMARY_KEYS identisch, mit der Ausnahme, dass es Primärschlüsselmetadaten nur für Tabellentypen, nicht aber für Tabellen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="60422-117">It is identical to DBSCHEMA_PRIMARY_KEYS, except that it returns primary keys metadata only for table types, rather than for tables.</span></span>|  
|<span data-ttu-id="60422-118">DBSCHEMA_TABLE_TYPE_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="60422-118">DBSCHEMA_TABLE_TYPE_COLUMNS</span></span>|<span data-ttu-id="60422-119">Dieses Rowset wurde hinzugefügt, um die Unterstützung von Tabellenwertparametern zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="60422-119">This rowset was added to support table-valued parameters.</span></span> <span data-ttu-id="60422-120">Es ist mit DBSCHEMA_COLUMNS identisch, mit der Ausnahme, dass es Spaltenmetadaten nur für Tabellentypen, nicht aber für Tabellen, Sichten oder Synonyme zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="60422-120">It is identical to DBSCHEMA_COLUMNS, except that it returns column metadata only for table types, rather than for tables, views, or synonyms.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="60422-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="60422-121">See Also</span></span>  
 <span data-ttu-id="60422-122">[Tabellenwert Parameter &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="60422-122">[Table-Valued Parameters &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span></span>  
 [<span data-ttu-id="60422-123">Verwenden von Tabellenwertparametern &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="60422-123">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
