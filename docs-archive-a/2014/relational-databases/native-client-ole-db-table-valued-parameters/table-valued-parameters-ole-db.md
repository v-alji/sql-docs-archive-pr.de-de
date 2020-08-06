---
title: Tabellenwertparameter (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, table-valued parameters
- table-valued parameters (OLE DB)
ms.assetid: 4298b73d-615b-4d28-9843-03b4d5fc489e
author: rothja
ms.author: jroth
ms.openlocfilehash: 41d125bcb254125d7f7562ca1873e8af03dab929
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722730"
---
# <a name="table-valued-parameters-ole-db"></a><span data-ttu-id="acd90-102">Tabellenwertparameter (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="acd90-102">Table-Valued Parameters (OLE DB)</span></span>
  <span data-ttu-id="acd90-103">In diesem Abschnitt wird die Unterstützung für Tabellenwertparameter in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter beschrieben.</span><span class="sxs-lookup"><span data-stu-id="acd90-103">This section describes support for table-valued parameters in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider.</span></span> <span data-ttu-id="acd90-104">Weitere Übersichts Informationen finden Sie unter [Tabellenwert Parameter &#40;SQL Server Native Client&#41;](../native-client/features/table-valued-parameters-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="acd90-104">For additional overview information, see [Table-Valued Parameters &#40;SQL Server Native Client&#41;](../native-client/features/table-valued-parameters-sql-server-native-client.md).</span></span> <span data-ttu-id="acd90-105">Ein Beispiel finden Sie unter [Verwenden von Tabellenwertparametern (OLE DB)](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="acd90-105">For a sample, see [Use Table-Valued Parameters &#40;OLE DB&#41;](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acd90-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="acd90-106">Remarks</span></span>  
 <span data-ttu-id="acd90-107">Derzeit können Sie mehrzeilige Daten an den Server als Parameter an eine Prozedur mit Parametersätzen senden (der DBPARAMS-Parameter in `ICommand::Execute`).</span><span class="sxs-lookup"><span data-stu-id="acd90-107">Currently, you can send multirow data to the server as parameters to a procedure with parameter sets (the DBPARAMS parameter in `ICommand::Execute`).</span></span> <span data-ttu-id="acd90-108">Bei Parametersätzen muss jedes Element des Satzes in einer separaten Remoteprozeduranforderung (Remote Procedure Call, RPC) an den Server gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="acd90-108">With parameter sets, every element of the set has to be sent in a separate remote procedure call (RPC) request to the server.</span></span> <span data-ttu-id="acd90-109">Tabellenwertparameter stellen eine ähnliche Funktionalität bereit, bieten jedoch eine bessere Integration mit dem Server.</span><span class="sxs-lookup"><span data-stu-id="acd90-109">Table-valued parameters provide similar functionality, but there is better integration with the server.</span></span> <span data-ttu-id="acd90-110">Dadurch werden die Anzahl von RPC-Anforderungen reduziert und setbasierte Vorgänge auf dem Server aktiviert.</span><span class="sxs-lookup"><span data-stu-id="acd90-110">This reduces the number of RPC requests and enables set-based operations on the server.</span></span>  
  
 <span data-ttu-id="acd90-111">Tabellenwertparameter werden in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter als OLE DB `Rowset`-Objekte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="acd90-111">Table-value parameters are supported in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider as OLE DB `Rowset` objects.</span></span> <span data-ttu-id="acd90-112">Jedes `Rowset`-Objekt kann vom Consumer (d. h. von der Clientanwendung, die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter verwendet) als Platzhalter für Tabellenwertparameter bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="acd90-112">Any `Rowset` object could be provided by the consumer (that is, the client application using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider) as a placeholder for table-valued parameter parameters.</span></span> <span data-ttu-id="acd90-113">Tabellenwertparameter werden wie andere [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Parametertypen behandelt.</span><span class="sxs-lookup"><span data-stu-id="acd90-113">Table-valued parameters are treated like other [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] parameter types.</span></span> <span data-ttu-id="acd90-114">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter stellt Erstellungs-, Ermittlungs-, Spezifizierungs-, Bindungs- und Schemaschnittstellen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="acd90-114">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider provides creation, discovery, specification, binding and schema interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="acd90-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="acd90-115">In This Section</span></span>  
  
-   [<span data-ttu-id="acd90-116">Tabellenwertparameter-Rowseterstellung</span><span class="sxs-lookup"><span data-stu-id="acd90-116">Table-Valued Parameter Rowset Creation</span></span>](table-valued-parameter-rowset-creation.md)  
  
-   [<span data-ttu-id="acd90-117">Tabellenwertparameter-Typermittlung</span><span class="sxs-lookup"><span data-stu-id="acd90-117">Table-Valued Parameter Type Discovery</span></span>](../../database-engine/dev-guide/table-valued-parameter-type-discovery.md)  
  
-   [<span data-ttu-id="acd90-118">Ausführen von Befehlen, die Tabellenwertparameter enthalten</span><span class="sxs-lookup"><span data-stu-id="acd90-118">Executing Commands Containing Table-Valued Parameters</span></span>](executing-commands-containing-table-valued-parameters.md)  
  
-   [<span data-ttu-id="acd90-119">Einfügen von Daten in Tabellenwertparameter</span><span class="sxs-lookup"><span data-stu-id="acd90-119">Inserting Data into Table-Valued Parameters</span></span>](inserting-data-into-table-valued-parameters.md)  
  
-   [<span data-ttu-id="acd90-120">Schemarowsets für OLE DB-Tabellenwertparameter geändert</span><span class="sxs-lookup"><span data-stu-id="acd90-120">Schema Rowsets Changed for OLE DB Table-Valued Parameters</span></span>](schema-rowsets-changed-for-ole-db-table-valued-parameters.md)  
  
-   [<span data-ttu-id="acd90-121">OLE DB-Typunterstützung für Tabellenwertparameter</span><span class="sxs-lookup"><span data-stu-id="acd90-121">OLE DB Table-Valued Parameter Type Support</span></span>](ole-db-table-valued-parameter-type-support.md)  
  
-   [<span data-ttu-id="acd90-122">OLE DB-Unterstützung für Tabellenwertparameter-Typen &#40;Methoden&#41;</span><span class="sxs-lookup"><span data-stu-id="acd90-122">OLE DB Table-Valued Parameter Type Support &#40;Methods&#41;</span></span>](ole-db-table-valued-parameter-type-support-methods.md)  
  
-   [<span data-ttu-id="acd90-123">OLE DB-Unterstützung für Tabellenwertparameter-Typen &#40;Eigenschaften&#41;</span><span class="sxs-lookup"><span data-stu-id="acd90-123">OLE DB Table-Valued Parameter Type Support &#40;Properties&#41;</span></span>](ole-db-table-valued-parameter-type-support-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="acd90-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="acd90-124">See Also</span></span>  
 <span data-ttu-id="acd90-125">[SQL Server Native Client &#40;OLE DB&#41;](../native-client/ole-db/sql-server-native-client-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="acd90-125">[SQL Server Native Client &#40;OLE DB&#41;](../native-client/ole-db/sql-server-native-client-ole-db.md) </span></span>  
 [<span data-ttu-id="acd90-126">Verwenden von Tabellenwertparametern &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="acd90-126">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
