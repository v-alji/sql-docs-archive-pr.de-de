---
title: OLE DB-Typunterstützung für Tabellenwertparameter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (OLE DB), API support (OLE DB)
ms.assetid: 147036a0-260e-4f81-8b3b-89209e023a32
author: rothja
ms.author: jroth
ms.openlocfilehash: 48d5fd780b2eaa2fc18e39071d3b10fde897b82c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616023"
---
# <a name="ole-db-table-valued-parameter-type-support"></a><span data-ttu-id="2893f-102">OLE DB-Typunterstützung für Tabellenwertparameter</span><span class="sxs-lookup"><span data-stu-id="2893f-102">OLE DB Table-Valued Parameter Type Support</span></span>
  <span data-ttu-id="2893f-103">In diesem Thema wird die OLE DB-Typunterstützung für Tabellenwertparameter beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2893f-103">This topic describes OLE DB type support for table-value parameters.</span></span>  
  
## <a name="table-valued-parameter-rowset-object"></a><span data-ttu-id="2893f-104">Tabellenwertparameter-Rowsetobjekt</span><span class="sxs-lookup"><span data-stu-id="2893f-104">Table-Valued Parameter Rowset Object</span></span>  
 <span data-ttu-id="2893f-105">Sie können ein spezielles Rowsetobjekt für Tabellenwertparameter erstellen.</span><span class="sxs-lookup"><span data-stu-id="2893f-105">You can create a specialized rowset object for table-valued parameters.</span></span> <span data-ttu-id="2893f-106">Sie können das Rowsetobjekt für Tabellenwertparameter mithilfe von ITableDefinitionWithConstraints::CreateTableWithConstraints oder IOpenRowset::OpenRowset erstellen.</span><span class="sxs-lookup"><span data-stu-id="2893f-106">You create the table-valued parameter rowset object by using ITableDefinitionWithConstraints::CreateTableWithConstraints or IOpenRowset::OpenRowset.</span></span> <span data-ttu-id="2893f-107">Legen Sie hierzu das *eKind*-Element des *pTableID*-Parameters auf DBKIND_GUID_NAME fest, und geben Sie für das *guid*-Element CLSID_ROWSET_INMEMORY an.</span><span class="sxs-lookup"><span data-stu-id="2893f-107">To do this, set the *eKind* member of the *pTableID* parameter to DBKIND_GUID_NAME, and provide the CLSID_ROWSET_INMEMORY as the *guid* member.</span></span> <span data-ttu-id="2893f-108">Der Servertypname für den Tabellenwertparameter muss bei Verwendung von IOpenRowset:: OPENROWSET im *pwszName*-Element von *pTableID* angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2893f-108">The server type name for the table-valued parameter must be specified in the *pwszName* member of *pTableID* when using IOpenRowset::OpenRowset.</span></span> <span data-ttu-id="2893f-109">Das Tabellenwertparameter-Rowsetobjekt verhält sich wie ein reguläres Objekt des OLE DB-Anbieters von SQL Server Native Client.</span><span class="sxs-lookup"><span data-stu-id="2893f-109">The table-valued parameter rowset object behaves like a regular SQL Server Native Client OLE DB Provider object.</span></span>  
  
```  
const GUID CLSID_ROWSET_TVP =   
{0xc7ef28d5, 0x7bee, 0x443f, {0x86, 0xda, 0xe3, 0x98, 0x4f, 0xcd, 0x4d, 0xf9}};  
  
CoType RowsetTVP  
{  
[mandatory] interface IAccessor;  
[mandatory] interface IColumnsInfo;  
[mandatory] interface IConvertType;  
[mandatory] interface IRowset;  
[mandatory] interface IRowsetInfo;  
[optional]  interface IColumnsRowset;  
[optional]  interface IRowsetChange;  
[optional]  interface ISupportErrorInfo;  
};  
```  
  
## <a name="dbtype_table"></a><span data-ttu-id="2893f-110">DBTYPE_TABLE</span><span class="sxs-lookup"><span data-stu-id="2893f-110">DBTYPE_TABLE</span></span>  
 <span data-ttu-id="2893f-111">Der neue Typ DBTYPE_TABLE stellt einen Tabellentyp dar.</span><span class="sxs-lookup"><span data-stu-id="2893f-111">A new type, DBTYPE_TABLE, represents a table type.</span></span> <span data-ttu-id="2893f-112">Dieser Typ gibt Tabellenwertparameter in verschiedenen OLE DB-Schnittstellen an, wo ein DBTYPE erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="2893f-112">This type specifies table-valued parameters in various OLE DB interfaces where a DBTYPE is required.</span></span>  
  
```  
#define DBTYPE_TABLE (143)  
```  
  
 <span data-ttu-id="2893f-113">DBTYPE_TABLE hat das gleiche Format wie DBTYPE_IUNKNOWN.</span><span class="sxs-lookup"><span data-stu-id="2893f-113">DBTYPE_TABLE has the same format as DBTYPE_IUNKNOWN.</span></span> <span data-ttu-id="2893f-114">Es ist ein Zeiger auf ein Objekt im Datenpuffer.</span><span class="sxs-lookup"><span data-stu-id="2893f-114">It is a pointer to an object in the data buffer.</span></span> <span data-ttu-id="2893f-115">Um die Bindungen vollständig anzugeben, füllt der Consumer den DBOBJECT-Puffer, wobei *iid* auf eine der Schnittstellen des Rowsetobjekts (IID_IRowset) festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="2893f-115">For complete specification in the bindings, the consumer fills up the DBOBJECT buffer, with *iid* set to one of the rowset object interfaces (IID_IRowset).</span></span> <span data-ttu-id="2893f-116">Wenn in den Bindungen die Angabe von DBOBJECT fehlt, wird IID_IRowset angenommen.</span><span class="sxs-lookup"><span data-stu-id="2893f-116">If no DBOBJECT is specified in the bindings, IID_IRowset will be assumed.</span></span>  
  
 <span data-ttu-id="2893f-117">Konvertierungen zu und von DBTYPE_TABLE für andere Typen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2893f-117">Conversions to and from DBTYPE_TABLE for any other types are not supported.</span></span> <span data-ttu-id="2893f-118">Außer bei einer Konvertierung von DBTYPE_TABLE zu DBTYPE_TABLE gibt IConvertType::CanConvert bei einer nicht unterstützten Konvertierung für jede Anforderung S_FALSE zurück.</span><span class="sxs-lookup"><span data-stu-id="2893f-118">IConvertType::CanConvert will return S_FALSE for unsupported conversion for any request other than DBTYPE_TABLE to DBTYPE_TABLE conversion.</span></span> <span data-ttu-id="2893f-119">Hierbei wird die Angabe von DBCONVERTFLAGS_PARAMETER für das Command-Objekt angenommen.</span><span class="sxs-lookup"><span data-stu-id="2893f-119">This assumes DBCONVERTFLAGS_PARAMETER on the Command object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2893f-120">Methoden</span><span class="sxs-lookup"><span data-stu-id="2893f-120">Methods</span></span>  
 <span data-ttu-id="2893f-121">Weitere Informationen zu OLE DB-Methoden, die Tabellenwertparameter unterstützen, finden Sie unter [OLE DB-Unterstützung von Tabellenwertparametern &#40;Methoden&#41;](ole-db-table-valued-parameter-type-support-methods.md).</span><span class="sxs-lookup"><span data-stu-id="2893f-121">For information about OLE DB methods that support table-valued parameters, see [OLE DB Table-Valued Parameter Type Support &#40;Methods&#41;](ole-db-table-valued-parameter-type-support-methods.md).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2893f-122">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2893f-122">Properties</span></span>  
 <span data-ttu-id="2893f-123">Weitere Informationen zu OLE DB-Eigenschaften, die Tabellenwertparameter unterstützen, finden Sie unter [OLE DB-Unterstützung von Tabellenwertparametern &#40;Eigenschaften&#41;](ole-db-table-valued-parameter-type-support-properties.md).</span><span class="sxs-lookup"><span data-stu-id="2893f-123">For information about OLE DB properties that support table-valued parameters, see [OLE DB Table-Valued Parameter Type Support &#40;Properties&#41;](ole-db-table-valued-parameter-type-support-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2893f-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2893f-124">See Also</span></span>  
 <span data-ttu-id="2893f-125">[Tabellenwert Parameter &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="2893f-125">[Table-Valued Parameters &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span></span>  
 [<span data-ttu-id="2893f-126">Verwenden von Tabellenwertparametern &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="2893f-126">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
