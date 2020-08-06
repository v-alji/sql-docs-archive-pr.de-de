---
title: Tabellenwertparameter-Typermittlung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- table-valued parameters, type discovery
ms.assetid: f55818c2-ebb5-4cf6-8c0c-0da41f592560
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ab8d837e4ddf74256e4bae70f772557ec8ff67f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701709"
---
# <a name="table-valued-parameter-type-discovery"></a><span data-ttu-id="6bc9d-102">Tabellenwertparameter-Typermittlung</span><span class="sxs-lookup"><span data-stu-id="6bc9d-102">Table-Valued Parameter Type Discovery</span></span>
  <span data-ttu-id="6bc9d-103">Der Consumer, d. h. die Client Anwendung, die den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter verwendet, kann den Typ jedes Befehls Parameters ermitteln, wenn der Befehls Text an den OLE DB Anbieter übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="6bc9d-103">The consumer-that is, the client application using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider-can discover the type of each command parameter if the command text has been given to the OLE DB Provider.</span></span> <span data-ttu-id="6bc9d-104">Nachdem der Typ des Tabellenwertparameters ermittelt wurde, kann der Consumer die Metadateninformationen für jede einzelne Spalte des Tabellenwertparameters ermitteln.</span><span class="sxs-lookup"><span data-stu-id="6bc9d-104">After the type of a table-valued parameter is known, the consumer can discover the metadata information for each individual column of the table-valued parameter.</span></span>  
  
 <span data-ttu-id="6bc9d-105">Die Typinformationen für Prozedurparameter werden von ICommandWithParameters::GetParameterInfo für die meisten Parametertypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6bc9d-105">The type information of procedure parameters is supported by ICommandWithParameters::GetParameterInfo for most parameter types.</span></span> <span data-ttu-id="6bc9d-106">Beginnend mit der [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Einführung von benutzerdefinierten Typen und des- `xml` Datentyps war die GetParameterInfo-Methode für diesen Zweck nicht ausreichend, weil es nicht möglich war, benutzerdefinierte Typinformationen (Name, Schema und Katalog) über ICommandWithParameters bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="6bc9d-106">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], with the introduction of user-defined types and the `xml` data type, the GetParameterInfo method was not sufficient for this purpose because it was not possible to provide user-defined type information (name, schema, and catalog) through ICommandWithParameters.</span></span> <span data-ttu-id="6bc9d-107">Es wurde eine neue Schnittstelle, ISSCommandWithParameters, definiert, um erweiterte Typinformationen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="6bc9d-107">A new interface, ISSCommandWithParameters, was defined to provide extended type information.</span></span>  
  
 <span data-ttu-id="6bc9d-108">Bei Tabellenwertparametern verwenden Sie auch die ISSCommandWithParameters-Schnittstelle, um ausführliche Informationen zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="6bc9d-108">For table-valued parameters, you also use the ISSCommandWithParameters interface to discover detailed information.</span></span> <span data-ttu-id="6bc9d-109">Der Client ruft ISSCommandWithParameters::GetParameterInfo nach der Vorbereitung des Befehlsobjekts auf.</span><span class="sxs-lookup"><span data-stu-id="6bc9d-109">The client calls ISSCommandWithParameters::GetParameterInfo after preparing the command object.</span></span> <span data-ttu-id="6bc9d-110">Bei Tabellenwertparametern wird das Element *wType* der Struktur DBPARAMINFO der DBPARAMINFO vom Anbieter auf DBTYPE_TABLE festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6bc9d-110">For table-valued parameters, the *wType* member of the DBPARAMINFO structure is set to DBTYPE_TABLE by the provider.</span></span> <span data-ttu-id="6bc9d-111">Das Feld *ulParamSize* der Struktur DBPARAMINFO hat den Wert ~0.</span><span class="sxs-lookup"><span data-stu-id="6bc9d-111">The *ulParamSize* field of DBPARAMINFO structure has a value of ~0.</span></span>  
  
 <span data-ttu-id="6bc9d-112">Der Consumer fordert dann mithilfe des Parameters „ISSCommandWithParameters::GetParameterProperties“ zusätzliche Eigenschaften an (Katalogname, Schemaname und Name des Tabellenwertparameter-Typs, Spaltensortierung und Standardspalten).</span><span class="sxs-lookup"><span data-stu-id="6bc9d-112">The consumer would then request additional properties (table-valued parameter type catalog name, table-valued parameter type schema name, table-valued parameter type name, column ordering, and default columns) by using ISSCommandWithParameters::GetParameterProperties.</span></span>  
  
 <span data-ttu-id="6bc9d-113">Nachdem der Typname ermittelt wurde, muss der Consumer entweder „IOpenRowset::OpenRowsetor“ aufrufen oder das DBSCHEMA_TABLE_TYPE_COLUMNS-Rowset durch Festlegen des Tabellenwertparameter-Typnamens als Tabellennamen abrufen, um Informationen zu den einzelnen Spalten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6bc9d-113">After the type name is known, to retrieve the individual column information the consumer must either call IOpenRowset::OpenRowsetor obtain the DBSCHEMA_TABLE_TYPE_COLUMNS rowset by specifying the table-valued parameter type name as the table name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bc9d-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6bc9d-114">See Also</span></span>  
 <span data-ttu-id="6bc9d-115">[Tabellenwert Parameter &#40;OLE DB&#41;](../../relational-databases/native-client-ole-db-table-valued-parameters/table-valued-parameters-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="6bc9d-115">[Table-Valued Parameters &#40;OLE DB&#41;](../../relational-databases/native-client-ole-db-table-valued-parameters/table-valued-parameters-ole-db.md) </span></span>  
 [<span data-ttu-id="6bc9d-116">Verwenden von Tabellenwertparametern &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="6bc9d-116">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../../relational-databases/native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
