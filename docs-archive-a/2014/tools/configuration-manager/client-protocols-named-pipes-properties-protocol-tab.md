---
title: 'Clientprotokolle: Named Pipes-Eigenschaften (Registerkarte „Protokoll“) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- pipes [SQL Server], connecting to
- Named Pipes [SQL Server], default pipe
- client protocols [SQL Server]
ms.assetid: 30fbae62-2f2e-4d36-9c6e-3444fff68781
author: stevestein
ms.author: sstein
ms.openlocfilehash: 169b6d98212c724b8d6c43615ae2fa7eba9cfc7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696358"
---
# <a name="client-protocols---named-pipes-properties-protocol-tab"></a><span data-ttu-id="b583c-102">Clientprotokolle - Named Pipes-Eigenschaften (Registerkarte Protokoll)</span><span class="sxs-lookup"><span data-stu-id="b583c-102">Client Protocols - Named Pipes Properties (Protocol Tab)</span></span>
  <span data-ttu-id="b583c-103">Verwenden Sie in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Configuration Manager im Dialogfeld **Named Pipes Properties** (Named Pipes-Eigenschaften) die Registerkarte **Protokoll**, um die Beschreibung der Standardpipe anzuzeigen oder zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="b583c-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager use the **Protocol** tab on the **Named Pipes Properties** dialog box to view or modify the description of default pipe.</span></span> <span data-ttu-id="b583c-104">Um eine Verbindung mit einer anderen Pipe herzustellen, geben Sie die Pipe im Dialogfeld **Standardpipe** ein.</span><span class="sxs-lookup"><span data-stu-id="b583c-104">To connect to a different pipe, type the pipe in the **Default Pipe** box.</span></span> <span data-ttu-id="b583c-105">Weitere Informationen zu Verbindungszeichenfolgen finden Sie unter [Creating a Valid Connection String Using Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md).</span><span class="sxs-lookup"><span data-stu-id="b583c-105">For more information about connection strings, see [Creating a Valid Connection String Using Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b583c-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="b583c-106">Options</span></span>  
 <span data-ttu-id="b583c-107">**Standardpipe**</span><span class="sxs-lookup"><span data-stu-id="b583c-107">**Default Pipe**</span></span>  
 <span data-ttu-id="b583c-108">Gibt die Standardpipe an, die von der Named Pipes-Netzwerkbibliothek zum Herstellen einer Verbindung mit der Zielinstanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b583c-108">Specifies the default pipe the Named Pipes Net-library will use to attempt to connect to the target instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b583c-109">Standardmäßig überwacht [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] : `\\.\pipe\sql\query`</span><span class="sxs-lookup"><span data-stu-id="b583c-109">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens on: `\\.\pipe\sql\query`</span></span>  
  
 <span data-ttu-id="b583c-110">Geben Sie `sql\query`</span><span class="sxs-lookup"><span data-stu-id="b583c-110">To connect to the default pipe, enter `sql\query`</span></span>  
  
 <span data-ttu-id="b583c-111">**Aktiviert**</span><span class="sxs-lookup"><span data-stu-id="b583c-111">**Enabled**</span></span>  
 <span data-ttu-id="b583c-112">Mögliche Werte sind **Yes** und **No**.</span><span class="sxs-lookup"><span data-stu-id="b583c-112">Possible values are **Yes** and **No**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b583c-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b583c-113">See Also</span></span>  
 [<span data-ttu-id="b583c-114">Auswählen eines Netzwerkprotokolls</span><span class="sxs-lookup"><span data-stu-id="b583c-114">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
