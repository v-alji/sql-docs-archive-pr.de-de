---
title: Ausführen gespeicherter Prozeduren (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [OLE DB], executing
- OLE DB, stored procedures
- SQL Server Native Client OLE DB provider, stored procedures
ms.assetid: c77d9be9-2176-4438-8c7a-04b63ebece08
author: rothja
ms.author: jroth
ms.openlocfilehash: 2e6ce951f343002feea5aa793d0cc2092422b819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722694"
---
# <a name="running-stored-procedures-ole-db"></a><span data-ttu-id="f1b8b-102">Ausführen von gespeicherten Prozeduren (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="f1b8b-102">Running Stored Procedures (OLE DB)</span></span>
  <span data-ttu-id="f1b8b-103">Wenn beim Ausführen von Anweisungen eine gespeicherte Prozedur in der Datenquelle ausgeführt wird (anstelle der Ausführung oder der Vorbereitung einer Anweisung direkt in der Clientanwendung), kann dies folgende Vorteile haben:</span><span class="sxs-lookup"><span data-stu-id="f1b8b-103">When executing statements, calling a stored procedure on the data source (instead of executing or preparing a statement in the client application directly) can provide:</span></span>  
  
-   <span data-ttu-id="f1b8b-104">Bessere Leistung</span><span class="sxs-lookup"><span data-stu-id="f1b8b-104">Higher performance.</span></span>  
  
-   <span data-ttu-id="f1b8b-105">Geringere Netzwerkbelastung</span><span class="sxs-lookup"><span data-stu-id="f1b8b-105">Reduced network overhead.</span></span>  
  
-   <span data-ttu-id="f1b8b-106">Bessere Konsistenz</span><span class="sxs-lookup"><span data-stu-id="f1b8b-106">Better consistency.</span></span>  
  
-   <span data-ttu-id="f1b8b-107">Höhere Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="f1b8b-107">Better accuracy.</span></span>  
  
-   <span data-ttu-id="f1b8b-108">Zusätzliche Funktionalität</span><span class="sxs-lookup"><span data-stu-id="f1b8b-108">Added functionality.</span></span>  
  
 <span data-ttu-id="f1b8b-109">Der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter unterstützt drei der Mechanismen, die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] gespeicherte Prozeduren zum Zurückgeben von Daten verwenden:</span><span class="sxs-lookup"><span data-stu-id="f1b8b-109">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports three of the mechanisms that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] stored procedures use to return data:</span></span>  
  
-   <span data-ttu-id="f1b8b-110">Jede SELECT-Anweisung in der Prozedur generiert ein Resultset.</span><span class="sxs-lookup"><span data-stu-id="f1b8b-110">Every SELECT statement in the procedure generates a result set.</span></span>  
  
-   <span data-ttu-id="f1b8b-111">Die Prozedur kann Daten über Ausgabeparameter zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="f1b8b-111">The procedure can return data through output parameters.</span></span>  
  
-   <span data-ttu-id="f1b8b-112">Die Prozedur kann einen ganzzahligen Rückgabecode besitzen.</span><span class="sxs-lookup"><span data-stu-id="f1b8b-112">The procedure can have an integer return code.</span></span>  
  
 <span data-ttu-id="f1b8b-113">Die Anwendung muss diese Ausgaben von gespeicherten Prozeduren verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f1b8b-113">The application must be able to handle all of these outputs from stored procedures.</span></span>  
  
 <span data-ttu-id="f1b8b-114">Die Rückgabe von Ausgabeparametern und Rückgabewerten erfolgt bei verschiedenen OLE DB-Anbietern zu unterschiedlichen Zeitpunkten während der Ergebnisverarbeitung.</span><span class="sxs-lookup"><span data-stu-id="f1b8b-114">Different OLE DB providers return output parameters and return values at different times during result processing.</span></span> <span data-ttu-id="f1b8b-115">Im Fall des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-OLE DB Anbieters werden die Ausgabeparameter und Rückgabecodes erst bereitgestellt, wenn der Consumer die von der gespeicherten Prozedur zurückgegebenen Resultsets abgerufen oder abgebrochen hat.</span><span class="sxs-lookup"><span data-stu-id="f1b8b-115">In case of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the output parameters and return codes are not supplied until after the consumer has retrieved or canceled the result sets returned by the stored procedure.</span></span> <span data-ttu-id="f1b8b-116">Die Rückgabecodes und die Ausgabeparameter werden im letzten TDS-Paket vom Server zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f1b8b-116">The return codes and the output parameters are returned in the last TDS packet from the server.</span></span>  
  
 <span data-ttu-id="f1b8b-117">Anbieter verwenden die DBPROP_OUTPUTPARAMETERAVAILABILITY-Eigenschaft, um die Rückgabe von Ausgabeparametern und Rückgabewerten zu melden.</span><span class="sxs-lookup"><span data-stu-id="f1b8b-117">Providers use the DBPROP_OUTPUTPARAMETERAVAILABILITY property to report when it returns output parameters and return values.</span></span> <span data-ttu-id="f1b8b-118">Bei dieser Eigenschaft handelt es sich um den DBPROPSET_DATASOURCEINFO-Eigenschaftensatz.</span><span class="sxs-lookup"><span data-stu-id="f1b8b-118">This property is in the DBPROPSET_DATASOURCEINFO property set.</span></span>  
  
 <span data-ttu-id="f1b8b-119">Der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter legt die DBPROP_OUTPUTPARAMETERAVAILABILITY-Eigenschaft auf DBPROPVAL_OA_ATROWRELEASE fest, um anzugeben, dass Rückgabecodes und Ausgabeparameter erst zurückgegeben werden, wenn das Resultset verarbeitet oder freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f1b8b-119">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider sets the DBPROP_OUTPUTPARAMETERAVAILABILITY property to DBPROPVAL_OA_ATROWRELEASE to indicate that return codes and output parameters are not returned until the result set is processed or released.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1b8b-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f1b8b-120">See Also</span></span>  
 [<span data-ttu-id="f1b8b-121">Gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f1b8b-121">Stored Procedures</span></span>](stored-procedures.md)  
  
  
