---
title: OLE-Automatisierungsprozeduren (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Ole Automation Procedures option
ms.assetid: e8982e05-4984-4406-9760-285e8c028ddf
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d34615ce1f808c1015c9c3d312a38a67dba291b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696042"
---
# <a name="ole-automation-procedures-server-configuration-option"></a><span data-ttu-id="f0a37-102">OLE-Automatisierungsprozeduren (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="f0a37-102">Ole Automation Procedures Server Configuration Option</span></span>
  <span data-ttu-id="f0a37-103">Verwenden Sie die `Ole Automation Procedures`-Option zum Angeben, ob OLE-Automatisierungsobjekte in [!INCLUDE[tsql](../../includes/tsql-md.md)]-Batches instantiiert werden können.</span><span class="sxs-lookup"><span data-stu-id="f0a37-103">Use the `Ole Automation Procedures` option to specify whether OLE Automation objects can be instantiated within [!INCLUDE[tsql](../../includes/tsql-md.md)] batches.</span></span> <span data-ttu-id="f0a37-104">Diese Option kann auch mithilfe der richtlinienbasierten Verwaltung oder der gespeicherten Prozedur **sp_configure** konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="f0a37-104">This option can also be configured using the Policy-Based Management or the **sp_configure** stored procedure.</span></span> <span data-ttu-id="f0a37-105">Weitere Informationen finden Sie unter [Oberflächenkonfiguration](../../relational-databases/security/surface-area-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="f0a37-105">For more information, see [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md).</span></span>  
  
 <span data-ttu-id="f0a37-106">Die `Ole Automation Procedures`-Option kann auf die folgenden Werte festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f0a37-106">The `Ole Automation Procedures` option can be set to the following values.</span></span>  
  
 <span data-ttu-id="f0a37-107">0</span><span class="sxs-lookup"><span data-stu-id="f0a37-107">0</span></span>  
 <span data-ttu-id="f0a37-108">OLE-Automatisierungsprozeduren sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f0a37-108">OLE Automation Procedures are disabled.</span></span> <span data-ttu-id="f0a37-109">Standardeinstellung für neue Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0a37-109">Default for new instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f0a37-110">1</span><span class="sxs-lookup"><span data-stu-id="f0a37-110">1</span></span>  
 <span data-ttu-id="f0a37-111">OLE-Automatisierungsprozeduren sind aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f0a37-111">OLE Automation Procedures are enabled.</span></span>  
  
 <span data-ttu-id="f0a37-112">Wenn OLE-Automatisierungsprozeduren aktiviert sind, startet ein Aufruf von **sp_OACreate** die freigegebene OLE-Ausführungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="f0a37-112">When OLE Automation Procedures are enabled, a call to **sp_OACreate** will start the OLE shared execution environment.</span></span>  
  
 <span data-ttu-id="f0a37-113">Der aktuelle Wert der `Ole Automation Procedures` Option kann mithilfe der gespeicherten System Prozedur **sp_configure** angezeigt und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f0a37-113">The current value of the `Ole Automation Procedures` option can be viewed and changed by using the **sp_configure** system stored procedure.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f0a37-114">Beispiele</span><span class="sxs-lookup"><span data-stu-id="f0a37-114">Examples</span></span>  
 <span data-ttu-id="f0a37-115">Das folgende Beispiel zeigt, wie die aktuelle Einstellung von OLE-Automatisierungsprozeduren angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f0a37-115">The following example shows how to view the current setting of OLE Automation procedures.</span></span>  
  
```  
EXEC sp_configure 'Ole Automation Procedures';  
GO  
```  
  
 <span data-ttu-id="f0a37-116">Das folgende Beispiel zeigt, wie OLE-Automatisierungsprozeduren aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f0a37-116">The following example shows how to enable OLE Automation procedures.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'Ole Automation Procedures', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0a37-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0a37-117">See Also</span></span>  
 <span data-ttu-id="f0a37-118">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0a37-118">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="f0a37-119">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0a37-119">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="f0a37-120">[Oberflächenkonfiguration](../../relational-databases/security/surface-area-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="f0a37-120">[Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md) </span></span>  
 [<span data-ttu-id="f0a37-121">Serverkonfigurationsoptionen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f0a37-121">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
