---
title: SqlServerAlias-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_name:
- SqlServerAlias Class
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SqlServerAlias class
ms.assetid: 475662b9-6985-45bf-b1e9-b0f26ef50443
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 46994409cc6a5119c9144eb7a3a4b9a8a9a22c44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622469"
---
# <a name="sqlserveralias-class"></a><span data-ttu-id="42199-102">SqlServerAlias-Klasse</span><span class="sxs-lookup"><span data-stu-id="42199-102">SqlServerAlias Class</span></span>
  <span data-ttu-id="42199-103">Die [SqlServerAlias Class](sqlserveralias-class.md) -Klasse stellt einen Serververbindungsalias dar.</span><span class="sxs-lookup"><span data-stu-id="42199-103">The [SqlServerAlias Class](sqlserveralias-class.md) class represents a server connection alias.</span></span>  
  
 <span data-ttu-id="42199-104">Ein Serververbindungsalias ist erforderlich, wenn beide der folgenden Situationen eintreten:</span><span class="sxs-lookup"><span data-stu-id="42199-104">A server connection alias is required when both the following occur:</span></span>  
  
-   <span data-ttu-id="42199-105">Der Client stellt [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] über einen Netzwerk Transport, der nicht der standardmäßige Netzwerk Transport ist, eine Verbindung mit einer Instanz von her.</span><span class="sxs-lookup"><span data-stu-id="42199-105">The client is connecting to an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] over a network transport that is not the default network transport.</span></span>  
  
-   <span data-ttu-id="42199-106">Die Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , mit der der Client verbunden ist, überwacht einen anderen Named Pipe.</span><span class="sxs-lookup"><span data-stu-id="42199-106">The instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to which the client is connected listens on an alternate named pipe.</span></span>  
  
 <span data-ttu-id="42199-107">**Hinweis:** Die [SqlServerAlias-Klasse](sqlserveralias-class.md) erbt die- `Put` Methode von der Provider-Klasse.</span><span class="sxs-lookup"><span data-stu-id="42199-107">**Note:** The [SqlServerAlias Class](sqlserveralias-class.md) inherits the `Put` method from the Provider class.</span></span> <span data-ttu-id="42199-108">Es werden jedoch keine Ergebnisse ausgegeben , wie von der `Provider::Put`-Methode angegeben.</span><span class="sxs-lookup"><span data-stu-id="42199-108">However, it does not return any results as indicated by the `Provider::Put` method.</span></span> <span data-ttu-id="42199-109">Weitere Informationen finden Sie in der WMI-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="42199-109">For more information, see the WMI documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42199-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="42199-110">See Also</span></span>  
 [<span data-ttu-id="42199-111">Konfigurieren von Clientprotokollen</span><span class="sxs-lookup"><span data-stu-id="42199-111">Configure Client Protocols</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
