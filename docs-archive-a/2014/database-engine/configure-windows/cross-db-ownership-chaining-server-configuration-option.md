---
title: Datenbankübergreifende Besitzverkettung (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- cross-database ownership chaining
- cross db ownership chaining option
- chaining ownership
ms.assetid: 7b2d49f2-b91c-4aee-a52b-6cc49bed03af
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cfb768065cc0aa2aaa7aed0f996b18e46f1da7ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618902"
---
# <a name="cross-db-ownership-chaining-server-configuration-option"></a><span data-ttu-id="acbae-102">Datenbankübergreifende Besitzverkettung (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="acbae-102">cross db ownership chaining Server Configuration Option</span></span>
  <span data-ttu-id="acbae-103">Mit der Option **cross db ownership chaining** lässt sich die datenbankübergreifende Besitzverkettung für eine Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="acbae-103">Use the **cross db ownership chaining** option to configure cross-database ownership chaining for an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="acbae-104">Mithilfe dieser Serveroption können Sie die datenbankübergreifende Besitzverkettung für alle Datenbanken auf Datenbankebene steuern oder die datenbankübergreifende Besitzverkettung für alle Datenbanken ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="acbae-104">This server option allows you to control cross-database ownership chaining at the database level or to allow cross-database ownership chaining for all databases:</span></span>  
  
-   <span data-ttu-id="acbae-105">Wenn **Datenbankübergreifende Besitzverkettung** für die Instanz deaktiviert ist (0), ist die datenbankübergreifende Besitzverkettung für alle Datenbanken deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="acbae-105">When **cross db ownership chaining** is off (0) for the instance, cross-database ownership chaining is disabled for all databases.</span></span>  
  
-   <span data-ttu-id="acbae-106">Wenn **Datenbankübergreifende Besitzverkettung** für die Instanz aktiviert ist (1), ist die datenbankübergreifende Besitzverkettung für alle Datenbanken aktiviert.</span><span class="sxs-lookup"><span data-stu-id="acbae-106">When **cross db ownership chaining** is on (1) for the instance, cross-database ownership chaining is on for all databases.</span></span>  
  
-   <span data-ttu-id="acbae-107">Sie können die datenbankübergreifende Besitzverkettung für einzelne Datenbanken mithilfe der SET-Klausel der ALTER DATABASE-Anweisung festlegen.</span><span class="sxs-lookup"><span data-stu-id="acbae-107">You can set cross-database ownership chaining for individual databases using the SET clause of the ALTER DATABASE statement.</span></span> <span data-ttu-id="acbae-108">Wenn Sie eine neue Datenbank erstellen, können Sie die datenbankübergreifende Besitzverkettungsoption für die neue Datenbank mithilfe der CREATE DATABASE-Anweisung festlegen.</span><span class="sxs-lookup"><span data-stu-id="acbae-108">If you are creating a new database, you can set the cross-database ownership chaining option for the new database using the CREATE DATABASE statement.</span></span>  
  
     <span data-ttu-id="acbae-109">Es ist nicht empfehlenswert, die Option **Datenbankübergreifende Besitzverkettung** auf 1 festzulegen, es sei denn, alle von der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz gehosteten Datenbanken müssen an der datenbankübergreifenden Besitzverkettung teilnehmen. Darüber hinaus sollten Ihnen die Sicherheitsauswirkungen dieser Einstellung bewusst sein.</span><span class="sxs-lookup"><span data-stu-id="acbae-109">Setting **cross db ownership chaining** to 1 is not recommended unless all of the databases hosted by the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must participate in cross-database ownership chaining and you are aware of the security implications of this setting.</span></span>  
  
## <a name="controlling-cross-database-ownership-chaining"></a><span data-ttu-id="acbae-110">Steuern der datenbankübergreifenden Besitzverkettung</span><span class="sxs-lookup"><span data-stu-id="acbae-110">Controlling Cross-Database Ownership Chaining</span></span>  
 <span data-ttu-id="acbae-111">Vor dem Aktivieren bzw. Deaktivieren der datenbankübergreifenden Besitzverkettung sollten Sie Folgendes berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="acbae-111">Before turning cross-database ownership chaining on or off, consider the following:</span></span>  
  
-   <span data-ttu-id="acbae-112">Sie müssen Mitglied der **sysadmin** -Rolle sein, um die datenbankübergreifende Besitzverkettung aktivieren oder deaktivieren zu können.</span><span class="sxs-lookup"><span data-stu-id="acbae-112">You must be a member of the **sysadmin** fixed server role to turn cross-database ownership chaining on or off.</span></span>  
  
-   <span data-ttu-id="acbae-113">Vor dem Deaktivieren der datenbankübergreifenden Besitzverkettung auf einem Produktionsserver sollten Sie jede Anwendung testen, einschließlich Anwendungen von Drittanbietern. Auf diese Weise können Sie sicherstellen, dass die Änderungen die Funktionalität der Anwendungen nicht beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="acbae-113">Before turning off cross-database ownership chaining on a production server, fully test all applications, including third-party applications, to ensure that the changes do not affect application functionality.</span></span>  
  
-   <span data-ttu-id="acbae-114">Sie können die Option **Datenbankübergreifende Besitzverkettung** ändern, wenn der Server ausgeführt wird und Sie RECONFIGURE mit **sp_configure**angeben.</span><span class="sxs-lookup"><span data-stu-id="acbae-114">You can change the **cross db ownership chaining** option while the server is running if you specify RECONFIGURE with **sp_configure**.</span></span>  
  
-   <span data-ttu-id="acbae-115">Verfügen Sie über Datenbanken, die eine datenbankübergreifende Besitzverkettung erfordern, ist es empfehlenswert, die Option **Datenbankübergreifende Besitzverkettung** für die Instanz mithilfe von **sp_configure**zu deaktivieren, und dann die datenbankübergreifende Besitzverkettung für einzelne Datenbanken, die sie erfordern, mithilfe der ALTER DATABASE-Anweisung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="acbae-115">If you have databases that require cross-database ownership chaining, the recommended practice is to turn off the **cross db ownership chaining** option for the instance using **sp_configure**; then turn on cross-database ownership chaining for individual databases that require it using the ALTER DATABASE statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acbae-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="acbae-116">See Also</span></span>  
 <span data-ttu-id="acbae-117">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="acbae-117">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="acbae-118">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="acbae-118">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="acbae-119">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="acbae-119">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="acbae-120">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="acbae-120">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="acbae-121">RECONFIGURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="acbae-121">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  
