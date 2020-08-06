---
title: OLE DB-Typunterstützung für Tabellenwertparameter (Methoden) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (OLE DB), API support (methods)
ms.assetid: e3c2a450-8fd4-44cb-93d8-affe1b65c68e
author: rothja
ms.author: jroth
ms.openlocfilehash: 8c7ca5946228ea05708984fb89ebc603061d983d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616027"
---
# <a name="ole-db-table-valued-parameter-type-support-methods"></a><span data-ttu-id="df0c8-102">OLE DB-Unterstützung von Tabellenwertparameter-Typen (Methoden)</span><span class="sxs-lookup"><span data-stu-id="df0c8-102">OLE DB Table-Valued Parameter Type Support (Methods)</span></span>
  <span data-ttu-id="df0c8-103">Die folgenden Standard-OLE DB-Methoden unterstützen Tabellenwertparameter:</span><span class="sxs-lookup"><span data-stu-id="df0c8-103">The following standard OLE DB methods support table-valued parameters:</span></span>  
  
|<span data-ttu-id="df0c8-104">Methode</span><span class="sxs-lookup"><span data-stu-id="df0c8-104">Method</span></span>|<span data-ttu-id="df0c8-105">Tabellenwertparameter-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="df0c8-105">Table-valued parameter support</span></span>|  
|------------|-------------------------------------|  
|<span data-ttu-id="df0c8-106">ITableDefinitionWithConstraints::CreateTableWithConstraints</span><span class="sxs-lookup"><span data-stu-id="df0c8-106">ITableDefinitionWithConstraints::CreateTableWithConstraints</span></span>|<span data-ttu-id="df0c8-107">Wird verwendet, wenn Sie den Typ des Tabellenwertparameters kennen und ein Tabellenwertparameter-Rowsetobjekt anhand der Typinformation instanziieren möchten.</span><span class="sxs-lookup"><span data-stu-id="df0c8-107">Used when you know type information of table-valued parameter, and want to instantiate a table-valued parameter rowset object based on the type-information.</span></span><br /><br /> <span data-ttu-id="df0c8-108">Weitere Informationen finden Sie unter „Statisches Szenario“ im Artikel [Rowsetobjekte für Tabellenwertparameter](table-valued-parameter-rowset-creation.md).</span><span class="sxs-lookup"><span data-stu-id="df0c8-108">For more information, see "Static Scenario" in [Table-Valued Parameter Rowset Creation](table-valued-parameter-rowset-creation.md).</span></span>|  
|<span data-ttu-id="df0c8-109">IOpenRowset::OpenRowset</span><span class="sxs-lookup"><span data-stu-id="df0c8-109">IOpenRowset::OpenRowset</span></span>|<span data-ttu-id="df0c8-110">Wird verwendet, wenn Sie den Typ eines Tabellenwertparameters nicht kennen und ein Tabellenwertparameter-Rowsetobjekt anhand der vom Server abgerufenen Metadateninformationen instanziieren möchten.</span><span class="sxs-lookup"><span data-stu-id="df0c8-110">Used when you do not know the type information of a table-valued parameter, and want to instantiate a table-valued parameter rowset object based on metadata information retrieved from the server.</span></span><br /><br /> <span data-ttu-id="df0c8-111">Weitere Informationen finden Sie unter „Dynamisches Szenario“ im Artikel [Rowsetobjekte für Tabellenwertparameter](table-valued-parameter-rowset-creation.md).</span><span class="sxs-lookup"><span data-stu-id="df0c8-111">For more information, see "Dynamic Scenario" in [Table-Valued Parameter Rowset Creation](table-valued-parameter-rowset-creation.md).</span></span>|  
|<span data-ttu-id="df0c8-112">ISSCommandWithParameters::SetParameterInfo</span><span class="sxs-lookup"><span data-stu-id="df0c8-112">ISSCommandWithParameters::SetParameterInfo</span></span>|<span data-ttu-id="df0c8-113">Zur Bezeichnung eines Tabellenwert-Befehlsparameters gibt der Consumer im *pwszName*-Element der DBPARAMBINDINFO-Struktur den Typ des Parameters als „table“ oder DBTYPE_TABLE an.</span><span class="sxs-lookup"><span data-stu-id="df0c8-113">To specify a table-valued parameter command parameter, the consumer specifies the type of the parameter as "table" or "DBTYPE_TABLE" in the *pwszName* member of DBPARAMBINDINFO structure.</span></span> <span data-ttu-id="df0c8-114">*ulParamSize* ist auf ~0 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="df0c8-114">The *ulParamSize* is set to ~0.</span></span> <span data-ttu-id="df0c8-115">Weitere Informationen finden Sie unter „Tabellenwertparameter-Spezifikation“ im Artikel [Ausführen von Befehlen, die Tabellenwertparameter enthalten](executing-commands-containing-table-valued-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="df0c8-115">For more information, see "Table-Valued Parameter Specification" in [Executing Commands Containing Table-Valued Parameters](executing-commands-containing-table-valued-parameters.md).</span></span>|  
|<span data-ttu-id="df0c8-116">ISSCommandWithParameters::SetParameterProperties</span><span class="sxs-lookup"><span data-stu-id="df0c8-116">ISSCommandWithParameters::SetParameterProperties</span></span>|<span data-ttu-id="df0c8-117">Legt spezielle Eigenschaften für Tabellenwertparameter fest, z. B. Schemaname, Typname, Spaltenreihenfolge und Standardspalten.</span><span class="sxs-lookup"><span data-stu-id="df0c8-117">Sets properties specific to table-valued parameters, such as schema name, type name, column order, and default columns.</span></span><br /><br /> <span data-ttu-id="df0c8-118">Der Consumer gibt die Ordnungszahl des Parameterwerts unter *iOrdinal* in der SSPARAMPROPS-Struktur an.</span><span class="sxs-lookup"><span data-stu-id="df0c8-118">The consumer specifies the ordinal of the parameter in the *iOrdinal* of the SSPARAMPROPS structure.</span></span> <span data-ttu-id="df0c8-119">Die angeforderte Eigenschaftengruppe ist DBPROPSET_SQLSERVERPARAMETER.</span><span class="sxs-lookup"><span data-stu-id="df0c8-119">The property set requested is DBPROPSET_SQLSERVERPARAMETER.</span></span>|  
|<span data-ttu-id="df0c8-120">ISSCommandWithParameters::GetParameterInfo</span><span class="sxs-lookup"><span data-stu-id="df0c8-120">ISSCommandWithParameters::GetParameterInfo</span></span>|<span data-ttu-id="df0c8-121">Ruft die Typen aller Parameter zu einem angegebenen Befehl ab.</span><span class="sxs-lookup"><span data-stu-id="df0c8-121">Gets the types of all the parameters to a specified command.</span></span><br /><br /> <span data-ttu-id="df0c8-122">Für Tabellenwertparameter verfügt das *wType*-Feld in der DBPARAMINFO-Struktur über den Typ DBTYPE_TABLE.</span><span class="sxs-lookup"><span data-stu-id="df0c8-122">For table-valued parameters, the *wType* field in DBPARAMINFO structure will have type DBTYPE_TABLE.</span></span> <span data-ttu-id="df0c8-123">Das *ulParamSize*-Feld wird auf ~0 festgelegt, um anzugeben, dass die Länge unbekannt ist.</span><span class="sxs-lookup"><span data-stu-id="df0c8-123">The *ulParamSize* field will be set to ~0 to indicate unknown length.</span></span>|  
|<span data-ttu-id="df0c8-124">ISSCommandWithParameters::GetParameterProperties</span><span class="sxs-lookup"><span data-stu-id="df0c8-124">ISSCommandWithParameters::GetParameterProperties</span></span>|<span data-ttu-id="df0c8-125">Ruft weitere Typinformationen für Parameter des DBTYPE_TABLE-Typs ab.</span><span class="sxs-lookup"><span data-stu-id="df0c8-125">Gets additional type information for parameters of the DBTYPE_TABLE type.</span></span><br /><br /> <span data-ttu-id="df0c8-126">Der Consumer gibt die Ordnungszahl des Parameterwerts im *iOrdinal*-Element der SSPARAMPROPS-Struktur an.</span><span class="sxs-lookup"><span data-stu-id="df0c8-126">The consumer specifies the ordinal of the parameter in the *iOrdinal* member of the SSPARAMPROPS structure.</span></span> <span data-ttu-id="df0c8-127">Der Consumer kann beliebige Eigenschaften der DBPROPSET_SQLSERVERPARAMETER-Eigenschaftengruppe anfordern, die unter ISSCommandWithParameters::SetParameterProperties aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="df0c8-127">The consumer can request any of the properties in the DBPROPSET_SQLSERVERPARAMETER property set that are listed under ISSCommandWithParameters::SetParameterProperties.</span></span><br /><br /> <span data-ttu-id="df0c8-128">Da der Consumer den Tabellenwertparameter-Typ nicht kennt, muss der Anbieter für SSPROP_PARAM_TYPE_TYPENAME, SSPROP_PARAM_TYPE_SCHEMANAME und SSPROP_PARAM_TYPE_CATALOGNAME die korrekten Werte festlegen.</span><span class="sxs-lookup"><span data-stu-id="df0c8-128">Because the consumer does not know the table-valued parameter type, the provider must set the SSPROP_PARAM_TYPE_TYPENAME, SSPROP_PARAM_TYPE_SCHEMANAME, and SSPROP_PARAM_TYPE_CATALOGNAME to their correct values.</span></span> <span data-ttu-id="df0c8-129">Die übrigen Eigenschaften, SSPROP_PARAM_TABLE_DEFAULT_COLUMNS und SSPROP_PARAM_TABLE_COLUMN_SORT_ORDER, behalten ihre Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="df0c8-129">The remaining properties, SSPROP_PARAM_TABLE_DEFAULT_COLUMNS and SSPROP_PARAM_TABLE_COLUMN_SORT_ORDER, will have their default values.</span></span> <span data-ttu-id="df0c8-130">Nachdem der Consumer den Tabellenwertparameter-Typnamen erkannt hat, erstellt er mithilfe von IOpenRowset::OpenRowset eine Instanz dieses Tabellenwertparameters. Dabei wird der Name des Tabellenwertparameter-Typs angegeben.</span><span class="sxs-lookup"><span data-stu-id="df0c8-130">After the consumer has discovered the table-valued parameter type name, it uses IOpenRowset::OpenRowset to create an instance of this table-valued parameter, specifying the name of table-valued parameter type.</span></span> <span data-ttu-id="df0c8-131">Weitere Informationen finden Sie unter [Tabellenwertparameter-Typermittlung](../../database-engine/dev-guide/table-valued-parameter-type-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="df0c8-131">For more information, see [Table-Valued Parameter Type Discovery](../../database-engine/dev-guide/table-valued-parameter-type-discovery.md).</span></span>|  
|<span data-ttu-id="df0c8-132">IRowsetInfo::GetProperties</span><span class="sxs-lookup"><span data-stu-id="df0c8-132">IRowsetInfo::GetProperties</span></span>|<span data-ttu-id="df0c8-133">Ruft Tabellenwertparameter-Rowseteigenschaften ab.</span><span class="sxs-lookup"><span data-stu-id="df0c8-133">Gets table-valued parameter rowset properties.</span></span> <span data-ttu-id="df0c8-134">Der Consumer kann diese Eigenschaften verwenden, um Bindungen optimal einzurichten.</span><span class="sxs-lookup"><span data-stu-id="df0c8-134">The consumer can use these properties to optimally set up bindings.</span></span>|  
|<span data-ttu-id="df0c8-135">IColumnsRowset::GetColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="df0c8-135">IColumnsRowset::GetColumnsRowset</span></span>|<span data-ttu-id="df0c8-136">Ruft Metadateninformationen zu einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Tabelle ab.</span><span class="sxs-lookup"><span data-stu-id="df0c8-136">Retrieves metadata information about a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="df0c8-137">Für Tabellenwertparameter stellt diese Schnittstelle ausführliche Metadateninformationen über jede Spalte bereit, darunter:</span><span class="sxs-lookup"><span data-stu-id="df0c8-137">For table-valued parameters, this same interface provides detailed metadata information about each column, such as the following:</span></span><br /><br /> <span data-ttu-id="df0c8-138">-DBCOLUMN_FLAGS gibt die NULL-Zulässigkeit durch das DBCOLUMNFLAGS_ISNULLABLE Bit an.</span><span class="sxs-lookup"><span data-stu-id="df0c8-138">-   DBCOLUMN_FLAGS indicates nullability through the DBCOLUMNFLAGS_ISNULLABLE bit.</span></span><br /><span data-ttu-id="df0c8-139">-DBCOLUMN_ISUNIQUE gibt an, ob die Spalte eine Identitäts Spalte ist.</span><span class="sxs-lookup"><span data-stu-id="df0c8-139">-   DBCOLUMN_ISUNIQUE indicates whether the column is an identity column.</span></span><br /><span data-ttu-id="df0c8-140">-DBCOLUMN_COMPUTEMODE gibt an, ob die Spalte berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="df0c8-140">-   DBCOLUMN_COMPUTEMODE indicates whether the column is computed.</span></span>|  
|<span data-ttu-id="df0c8-141">IAccessor::CreateAccessor</span><span class="sxs-lookup"><span data-stu-id="df0c8-141">IAccessor::CreateAccessor</span></span>|<span data-ttu-id="df0c8-142">Um ein Tabellenwertparameter-Rowsetobjekt an einen Befehlsparameter zu binden, erstellen Sie einen Accessor. Für das *wType*-Element wird dabei DBTYPE_TABLE festgelegt.</span><span class="sxs-lookup"><span data-stu-id="df0c8-142">To bind a table-valued parameter rowset object to a command parameter, you create an accessor with its *wType* member set to DBTYPE_TABLE.</span></span> <span data-ttu-id="df0c8-143">Die DBOBJECT-Struktur enthält IID_IRowset oder eine beliebige andere gültige Rowsetobjekt-Schnittstelle im *iid*-Element.</span><span class="sxs-lookup"><span data-stu-id="df0c8-143">The DBOBJECT structure will contain IID_IRowset or any other valid rowset object interface in the *iid* member.</span></span> <span data-ttu-id="df0c8-144">Die übrigen Felder werden ähnlich behandelt wie DBTYPE_IUNKNOWN.</span><span class="sxs-lookup"><span data-stu-id="df0c8-144">The rest of the fields are treated similarly to DBTYPE_IUNKNOWN.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="df0c8-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="df0c8-145">See Also</span></span>  
 <span data-ttu-id="df0c8-146">[OLE DB Typunterstützung für Tabellenwert Parameter](ole-db-table-valued-parameter-type-support.md) </span><span class="sxs-lookup"><span data-stu-id="df0c8-146">[OLE DB Table-Valued Parameter Type Support](ole-db-table-valued-parameter-type-support.md) </span></span>  
 <span data-ttu-id="df0c8-147">[Erstellung eines Tabellenwert Parameter-Rowsets](table-valued-parameter-rowset-creation.md) </span><span class="sxs-lookup"><span data-stu-id="df0c8-147">[Table-Valued Parameter Rowset Creation](table-valued-parameter-rowset-creation.md) </span></span>  
 [<span data-ttu-id="df0c8-148">Verwenden von Tabellenwertparametern &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="df0c8-148">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](table-valued-parameters-ole-db.md)  
  
  