---
title: ICommandWithParameters | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 66644c70-def7-46d8-8c47-b883292a0288
author: rothja
ms.author: jroth
ms.openlocfilehash: df3103181b3cad772e7d1c73068b8864bf591b73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621492"
---
# <a name="icommandwithparameters"></a><span data-ttu-id="d362c-102">ICommandWithParameters</span><span class="sxs-lookup"><span data-stu-id="d362c-102">ICommandWithParameters</span></span>
  <span data-ttu-id="d362c-103">Verbesserungen an der Datenbank-Engine ab [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] ermöglichen das Abrufen genauerer Beschreibungen der erwarteten Ergebnisse durch ICommandWithParameters::GetParameterInfo.</span><span class="sxs-lookup"><span data-stu-id="d362c-103">Improvements in the database engine beginning with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] allow ICommandWithParameters::GetParameterInfo to obtain more accurate descriptions of the expected results.</span></span> <span data-ttu-id="d362c-104">Diese genaueren Ergebnisse unterscheiden sich möglicherweise von den Werten, die von CommandWithParameters::GetParameterInfo in früheren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="d362c-104">These more accurate results may differ from the values returned by CommandWithParameters::GetParameterInfo in previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d362c-105">Weitere Informationen finden Sie unter [Metadatenermittlung](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="d362c-105">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
 <span data-ttu-id="d362c-106">Ab [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] muss beim Aufrufen von ICommandWithParameters::SetParameterInfo der an den Parameter *pwszName* übergebene Wert ein gültiger Bezeichner sein.</span><span class="sxs-lookup"><span data-stu-id="d362c-106">Also beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], when calling ICommandWithParameters::SetParameterInfo, the value passed to the *pwszName* parameter must be a valid identifier.</span></span> <span data-ttu-id="d362c-107">Weitere Informationen finden Sie unter [Datenbankbezeichner](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="d362c-107">For more information, see [Database Identifiers](../databases/database-identifiers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d362c-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d362c-108">See Also</span></span>  
 [<span data-ttu-id="d362c-109">Schnittstellen &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="d362c-109">Interfaces &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/interfaces-ole-db.md)  
  
  
