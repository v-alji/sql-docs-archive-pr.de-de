---
title: CLR-fähig (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- assemblies [CLR integration], verifying can run
- clr enabled option
ms.assetid: 0722d382-8fd3-4fac-b4a8-cd2b7a7e0293
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b83cd0e00bdd32c8b44667209544c8e81b1e90c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608852"
---
# <a name="clr-enabled-server-configuration-option"></a><span data-ttu-id="2defc-102">CLR-fähig (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="2defc-102">clr enabled Server Configuration Option</span></span>
  <span data-ttu-id="2defc-103">Mithilfe der Option CLR-fähig können Sie angeben, ob Benutzerassemblys von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ausgeführt werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="2defc-103">Use the clr enabled option to specify whether user assemblies can be run by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2defc-104">Von der Option "CLR-fähig" werden folgende Werte bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="2defc-104">The clr enabled option provides the following values.</span></span>  
  
|<span data-ttu-id="2defc-105">Wert</span><span class="sxs-lookup"><span data-stu-id="2defc-105">Value</span></span>|<span data-ttu-id="2defc-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2defc-106">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2defc-107">0</span><span class="sxs-lookup"><span data-stu-id="2defc-107">0</span></span>|<span data-ttu-id="2defc-108">Das Ausführen von Assemblys für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ist unzulässig.</span><span class="sxs-lookup"><span data-stu-id="2defc-108">Assembly execution not allowed on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|<span data-ttu-id="2defc-109">1</span><span class="sxs-lookup"><span data-stu-id="2defc-109">1</span></span>|<span data-ttu-id="2defc-110">Das Ausführen von Assemblys für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="2defc-110">Assembly execution allowed on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
  
 <span data-ttu-id="2defc-111">WOW64-Server müssen neu gestartet werden, bevor die Änderungen an dieser Einstellung wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="2defc-111">WOW64 servers must be restarted before the changes to this setting will take effect.</span></span> <span data-ttu-id="2defc-112">Ein Neustart ist für andere Servertypen nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2defc-112">Restart is not required for other server types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2defc-113">Wenn RECONFIGURE ausgeführt und der Ausführungswert der Option "CLR-fähig" von 1 in 0 geändert wird, werden alle Anwendungsdomänen mit Benutzerassemblys sofort entladen.</span><span class="sxs-lookup"><span data-stu-id="2defc-113">When RECONFIGURE is run and the run value of the clr enabled option is changed from 1 to 0, all application domains containing user assemblies are immediately unloaded.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2defc-114">CLR (Common Language Runtime) wird beim Lightweightpooling nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2defc-114">Common language runtime (CLR) execution is not supported under lightweight pooling.</span></span> <span data-ttu-id="2defc-115">Deaktivieren Sie eine der beiden Optionen "CLR-fähig" oder "Lightweightpooling".</span><span class="sxs-lookup"><span data-stu-id="2defc-115">Disable one of two options: "clr enabled" or "lightweight pooling.</span></span> <span data-ttu-id="2defc-116">Zu den Funktionen, die auf CLR basieren und nicht ordnungsgemäß im Fibermodus arbeiten, gehören der `hierarchy`-Datentyp, die Replikation und die richtlinienbasierte Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="2defc-116">Features that rely upon CLR and that do not work properly in fiber mode include the `hierarchy` data type, replication, and Policy-Based Management.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2defc-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2defc-117">Example</span></span>  
 <span data-ttu-id="2defc-118">Im folgenden Beispiel wird zunächst die aktuelle Einstellung der Option CLR-fähig angezeigt und die Option dann aktiviert, indem der Optionswert auf 1 festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="2defc-118">The following example first displays the current setting of the clr enabled option and then enables the option by setting the option value to 1.</span></span> <span data-ttu-id="2defc-119">Wenn Sie die Option deaktivieren möchten, legen Sie den Wert auf 0 fest.</span><span class="sxs-lookup"><span data-stu-id="2defc-119">To disable the option, set the value to 0.</span></span>  
  
```  
EXEC sp_configure 'clr enabled';  
EXEC sp_configure 'clr enabled' , '1';  
RECONFIGURE;  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="2defc-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2defc-120">See Also</span></span>  
 <span data-ttu-id="2defc-121">[Lightweightpooling (Serverkonfigurationsoption)](lightweight-pooling-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="2defc-121">[lightweight pooling Server Configuration Option](lightweight-pooling-server-configuration-option.md) </span></span>  
 <span data-ttu-id="2defc-122">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2defc-122">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="2defc-123">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2defc-123">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="2defc-124">Lightweightpooling (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="2defc-124">lightweight pooling Server Configuration Option</span></span>](lightweight-pooling-server-configuration-option.md)  
  
  
