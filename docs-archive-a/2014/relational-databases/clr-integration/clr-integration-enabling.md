---
title: Aktivieren der CLR-Integration | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- clr enabled option
- common language runtime [SQL Server], enabling
ms.assetid: eb3e9c64-7486-42e7-baf6-c956fb311a2c
author: rothja
ms.author: jroth
ms.openlocfilehash: d7187906f1376deb81ca7ff4770af7b12b63c022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720011"
---
# <a name="enabling-clr-integration"></a><span data-ttu-id="4ee37-102">Aktivieren der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="4ee37-102">Enabling CLR Integration</span></span>
  <span data-ttu-id="4ee37-103">Die Funktion zur CLR-Integration (Common Language Runtime) ist standardmäßig deaktiviert und muss aktiviert werden, um Objekte, die mittels CLR-Integration implementiert werden, verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="4ee37-103">The common language runtime (CLR) integration feature is off by default, and must be enabled in order to use objects that are implemented using CLR integration.</span></span> <span data-ttu-id="4ee37-104">Um die CLR-Integration zu aktivieren, verwenden Sie die Option **CLR-fähig** der gespeicherten Prozedur **sp_configure** :</span><span class="sxs-lookup"><span data-stu-id="4ee37-104">To enable CLR integration, use the **clr enabled** option of the **sp_configure** stored procedure:</span></span>  
  
```  
  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'clr enabled', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="4ee37-105">Sie können die CLR-Integration deaktivieren, indem Sie die Option **CLR-fähig** auf 0 festlegen.</span><span class="sxs-lookup"><span data-stu-id="4ee37-105">You can disable CLR integration by setting the **clr enabled** option to 0.</span></span> <span data-ttu-id="4ee37-106">Wenn Sie die CLR-Integration deaktivieren, stoppt [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] die Ausführung aller CLR-Routinen und entlädt alle Anwendungsdomänen.</span><span class="sxs-lookup"><span data-stu-id="4ee37-106">When you disable CLR integration, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] stops executing all CLR routines and unloads all application domains.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ee37-107">Um die CLR-Integration zu aktivieren, müssen Sie über die ALTER SETTINGS-Berechtigung auf Serverebene verfügen, die von Mitgliedern der festen Server Rollen **sysadmin** und **serveradmin** implizit aufbewahrt wird.</span><span class="sxs-lookup"><span data-stu-id="4ee37-107">To enable CLR integration, you must have ALTER SETTINGS server level permission, which is implicitly held by members of the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ee37-108">Computer, die mit großen Mengen an Arbeitsspeicher und einer großen Anzahl von Prozessoren konfiguriert sind, können das SQL Server-Funktion zur CLR-Integration beim Serverstart möglicherweise nicht laden.</span><span class="sxs-lookup"><span data-stu-id="4ee37-108">Computers configured with large amounts of memory and a large number of processors may fail to load the CLR integration feature of SQL Server when starting the server.</span></span> <span data-ttu-id="4ee37-109">Um dieses Problem zu beheben, starten Sie den Server mithilfe der Startoption **-gmemory_to_reserve** [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Service, und geben Sie einen Wert für den Arbeitsspeicher an, der groß genug ist.</span><span class="sxs-lookup"><span data-stu-id="4ee37-109">To address this issue, start the server by using the **-gmemory_to_reserve**[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service startup option, and specify a memory value large enough.</span></span> <span data-ttu-id="4ee37-110">Weitere Informationen finden Sie unter [Startoptionen für den Datenbank-Engine-Dienst](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="4ee37-110">For more information, see [Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ee37-111">CLR (Common Language Runtime) wird beim Lightweightpooling nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4ee37-111">Common language runtime (CLR) execution is not supported under lightweight pooling.</span></span> <span data-ttu-id="4ee37-112">Vor dem Aktivieren der CLR-Integration müssen Sie Lightweightpooling deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4ee37-112">Before enabling CLR integration, you must disable lightweight pooling.</span></span> <span data-ttu-id="4ee37-113">Weitere Informationen finden Sie unter [Lightweightpooling (Serverkonfigurationsoption)](../../database-engine/configure-windows/lightweight-pooling-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="4ee37-113">For more information, see [lightweight pooling Server Configuration Option](../../database-engine/configure-windows/lightweight-pooling-server-configuration-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ee37-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4ee37-114">See Also</span></span>  
 <span data-ttu-id="4ee37-115">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ee37-115">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="4ee37-116">[CLR-fähig (Serverkonfigurationsoption)](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="4ee37-116">[clr enabled Server Configuration Option](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) </span></span>  
 <span data-ttu-id="4ee37-117">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ee37-117">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="4ee37-118">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4ee37-118">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span></span>  
 [<span data-ttu-id="4ee37-119">Rollen auf Serverebene</span><span class="sxs-lookup"><span data-stu-id="4ee37-119">Server-Level Roles</span></span>](../security/authentication-access/server-level-roles.md)  
  
  
