---
title: ADO-Verbindungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], ADO
- connection managers [Integration Services], ADO
- ADO connection manager [Integration Services]
ms.assetid: 490418bc-5ef1-41b8-a9c8-de38aa96e0f6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fb4b667733f81eebbaf2b6a2ab9b205c09fe2c66
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621146"
---
# <a name="ado-connection-manager"></a><span data-ttu-id="50305-102">ADO-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="50305-102">ADO Connection Manager</span></span>
  <span data-ttu-id="50305-103">Durch einen ADO-Verbindungs-Manager kann ein Paket eine Verbindung mit ADO-Objekten (ActiveX Data Objects) herstellen, wie z. B. einem Recordset.</span><span class="sxs-lookup"><span data-stu-id="50305-103">An ADO connection manager enables a package to connect to ActiveX Data Objects (ADO) objects, such as a recordset.</span></span> <span data-ttu-id="50305-104">Dieser Verbindungs-Manager wird normalerweise für benutzerdefinierte Tasks verwendet, die in einer früheren Version einer Programmiersprache, wie z. B. Microsoft Visual Basic 6.0, erstellt wurden, oder für benutzerdefinierte Tasks, die Bestandteil einer vorhandenen Anwendung sind, die mithilfe von ADO eine Verbindung mit einer Datenquelle herstellt.</span><span class="sxs-lookup"><span data-stu-id="50305-104">This connection manager is typically used in custom tasks written in an earlier version of a language, such as Microsoft Visual Basic 6.0, or in custom tasks that are part of an existing application that uses ADO to connect to a data source.</span></span>  
  
 <span data-ttu-id="50305-105">Wenn Sie einem Paket einen ADO-Verbindungs-Manager hinzufügen, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] erstellt einen Verbindungs-Manager, der zur Laufzeit in eine ADO-Verbindung aufgelöst wird, die Eigenschaften des Verbindungs-Managers festlegt und der-Auflistung im Paket den Verbindungs-Manager hinzufügt `Connections` .</span><span class="sxs-lookup"><span data-stu-id="50305-105">When you add an ADO connection manager to a package, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an ADO connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="50305-106">Die `ConnectionManagerType`-Eigenschaft des Verbindungs-Managers ist auf `ADO` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="50305-106">The `ConnectionManagerType` property of the connection manager is set to `ADO`.</span></span>  
  
## <a name="troubleshooting-the-ado-connection-manager"></a><span data-ttu-id="50305-107">Problembehandlung des ADO-Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="50305-107">Troubleshooting the ADO Connection Manager</span></span>  
 <span data-ttu-id="50305-108">Daten bestimmter [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datumsdatentypen generieren beim Lesen durch einen ADO-Verbindungs-Manager die in der folgenden Tabelle dargestellten Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="50305-108">When being read by an ADO connection manager, certain [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date data types will generate the results shown in the following table.</span></span>  
  
|<span data-ttu-id="50305-109">SQL Server-Datentyp</span><span class="sxs-lookup"><span data-stu-id="50305-109">SQL Server Data type</span></span>|<span data-ttu-id="50305-110">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="50305-110">Result</span></span>|  
|--------------------------|------------|  
|<span data-ttu-id="50305-111">`time`, `datetimeoffset`</span><span class="sxs-lookup"><span data-stu-id="50305-111">`time`, `datetimeoffset`</span></span>|<span data-ttu-id="50305-112">Das Paket erzeugt einen Fehler, sofern das Paket keine parametrisierten SQL-Befehle verwendet.</span><span class="sxs-lookup"><span data-stu-id="50305-112">The package fails unless the package uses parameterized SQL commands.</span></span> <span data-ttu-id="50305-113">Um parametrisierte SQL-Befehle zu verwenden, verwenden Sie den Task SQL ausführen im Paket.</span><span class="sxs-lookup"><span data-stu-id="50305-113">To use parameterized SQL commands, use the Execute SQL Task in your package.</span></span> <span data-ttu-id="50305-114">Weitere Informationen finden Sie unter [SQL ausführen (Task)](../control-flow/execute-sql-task.md) und [Parameter und Rückgabecodes im Task „SQL ausführen“](../parameters-and-return-codes-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="50305-114">For more information, see [Execute SQL Task](../control-flow/execute-sql-task.md) and [Parameters and Return Codes in the Execute SQL Task](../parameters-and-return-codes-in-the-execute-sql-task.md).</span></span>|  
|`datetime2`|<span data-ttu-id="50305-115">Der ADO-Verbindungs-Manager schneidet den Millisekundenwert ab.</span><span class="sxs-lookup"><span data-stu-id="50305-115">The ADO connection manager truncates the millisecond value.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="50305-116">Weitere Informationen zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datentypen sowie deren Zuordnung zu [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Datentypen finden Sie unter [Datentypen &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) und [SQL Server Integration Services-Datentypen](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="50305-116">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types and how they map to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] data types, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) and [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="configuring-the-ado-connection-manager"></a><span data-ttu-id="50305-117">Konfigurieren des ADO-Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="50305-117">Configuring the ADO Connection Manager</span></span>  
 <span data-ttu-id="50305-118">Es gibt folgende Möglichkeiten, um einen ADO-Verbindungs-Manager zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="50305-118">You can configure an ADO connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="50305-119">Stellen Sie eine Verbindungszeichenfolge bereit, die die Anforderungen des ausgewählten Anbieters erfüllt.</span><span class="sxs-lookup"><span data-stu-id="50305-119">Provide a specific connection string configured to meet the requirements of the selected provider.</span></span>  
  
-   <span data-ttu-id="50305-120">Schließen Sie in Abhängigkeit vom Anbieter den Namen der Datenquelle ein, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="50305-120">Depending on the provider, include the name of the data source to connect to.</span></span>  
  
-   <span data-ttu-id="50305-121">Stellen Sie entsprechende Sicherheitsanmeldeinformationen für den ausgewählten Anbieter bereit.</span><span class="sxs-lookup"><span data-stu-id="50305-121">Provide security credentials as appropriate for the selected provider.</span></span>  
  
-   <span data-ttu-id="50305-122">Geben Sie an, ob die im Verbindungs-Manager erstellte Verbindung zur Laufzeit beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="50305-122">Indicate whether the connection that is created from the connection manager is retained at run time.</span></span>  
  
 <span data-ttu-id="50305-123">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="50305-123">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="50305-124">Klicken Sie auf das folgende Thema, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer festlegen können:</span><span class="sxs-lookup"><span data-stu-id="50305-124">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="50305-125">Konfigurieren des OLE DB-Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="50305-125">Configure OLE DB Connection Manager</span></span>](ole-db-connection-manager.md)  
  
 <span data-ttu-id="50305-126">Weitere Informationen zum programmgesteuerten Konfigurieren eines Verbindungs-Managers finden Sie unter <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> und [Programmgesteuertes Hinzufügen von Verbindungen](../building-packages-programmatically/adding-connections-programmatically.md)festgelegt.</span><span class="sxs-lookup"><span data-stu-id="50305-126">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50305-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="50305-127">See Also</span></span>  
 [<span data-ttu-id="50305-128">Integration Services-Verbindungen &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="50305-128">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
