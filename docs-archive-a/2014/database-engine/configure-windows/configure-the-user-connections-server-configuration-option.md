---
title: Konfigurieren der Serverkonfigurationsoption „Benutzerverbindungen“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/02/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- simultaneous connections [SQL Server]
- user connections option [SQL Server]
- users [SQL Server], simultaneous connections
- maximum number of simultaneous user connections
- connections [SQL Server], simultaneous
ms.assetid: 53beee6e-59fe-4276-9abb-8f1cec2a3508
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 68fbb4a17de131c128b5b1bb7cfb35a33b9d0037
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608841"
---
# <a name="configure-the-user-connections-server-configuration-option"></a><span data-ttu-id="46081-102">Konfigurieren der Serverkonfigurationsoption Benutzerverbindungen</span><span class="sxs-lookup"><span data-stu-id="46081-102">Configure the user connections Server Configuration Option</span></span>
  <span data-ttu-id="46081-103">In diesem Thema wird beschrieben, wie die Serverkonfigurationsoption **Benutzerverbindungen** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="46081-103">This topic describes how to set the **user connections** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="46081-104">Die Option **Benutzerverbindungen** gibt die maximale Anzahl gleichzeitiger Benutzerverbindungen an, die für eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="46081-104">The **user connections** option specifies the maximum number of simultaneous user connections that are allowed on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="46081-105">Die tatsächliche Anzahl von zulässigen Benutzerverbindungen ist auch abhängig von der verwendeten Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sowie von den Einschränkungen der Anwendung bzw. Anwendungen und der Hardware.</span><span class="sxs-lookup"><span data-stu-id="46081-105">The actual number of user connections allowed also depends on the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you are using, and also the limits of your application or applications and hardware.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="46081-106">lässt maximal 32.767 Benutzerverbindungen zu.</span><span class="sxs-lookup"><span data-stu-id="46081-106">allows a maximum of 32,767 user connections.</span></span> <span data-ttu-id="46081-107">Da **Benutzerverbindungen** eine dynamische (selbstkonfigurierende) Option ist, passt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die maximale Anzahl der Benutzerverbindungen automatisch nach Bedarf bis zum zulässigen Höchstwert an.</span><span class="sxs-lookup"><span data-stu-id="46081-107">Because **user connections** is a dynamic (self-configuring) option, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] adjusts the maximum number of user connections automatically as needed, up to the maximum value allowable.</span></span> <span data-ttu-id="46081-108">Wenn beispielsweise nur 10 Benutzer angemeldet sind, werden 10 Benutzerverbindungsobjekte reserviert.</span><span class="sxs-lookup"><span data-stu-id="46081-108">For example, if only 10 users are logged in, 10 user connection objects are allocated.</span></span> <span data-ttu-id="46081-109">In den meisten Fällen ist es nicht erforderlich, dass Sie den Wert für diese Option ändern.</span><span class="sxs-lookup"><span data-stu-id="46081-109">In most cases, you do not have to change the value for this option.</span></span> <span data-ttu-id="46081-110">Der Standardwert ist null (0), womit die maximale Anzahl (32.767) Benutzerverbindungen zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="46081-110">The default is 0, which means that the maximum (32,767) user connections are allowed.</span></span>  
  
 <span data-ttu-id="46081-111">Um die maximale Anzahl von Benutzerverbindungen zu bestimmen, die im System zulässig sind, können Sie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) ausführen oder die Katalogsicht [sys.configuration](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) abfragen.</span><span class="sxs-lookup"><span data-stu-id="46081-111">To determine the maximum number of user connections that your system allows, you can execute [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) or query the [sys.configuration](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) catalog view.</span></span>  
  
 <span data-ttu-id="46081-112">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="46081-112">**In This Topic**</span></span>  
  
-   <span data-ttu-id="46081-113">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="46081-113">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="46081-114">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="46081-114">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="46081-115">Security</span><span class="sxs-lookup"><span data-stu-id="46081-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="46081-116">**So konfigurieren Sie die Option Benutzerverbindungen mit:**</span><span class="sxs-lookup"><span data-stu-id="46081-116">**To configure the user connections option, using:**</span></span>  
  
     [<span data-ttu-id="46081-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="46081-117">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="46081-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="46081-118">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="46081-119">**Nachverfolgung:**  [Nach dem Konfigurieren der Option „Benutzerverbindungen“](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="46081-119">**Follow Up:**  [After you configure the user connections option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="46081-120">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="46081-120">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="46081-121">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="46081-121">Recommendations</span></span>  
  
-   <span data-ttu-id="46081-122">Diese Option ist eine erweiterte Option und sollte ausschließlich von einem erfahrenen Datenbankadministrator oder einem zertifizierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Techniker geändert werden.</span><span class="sxs-lookup"><span data-stu-id="46081-122">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="46081-123">Durch die Option **Benutzerverbindungen** kann eine Überlastung des Servers durch zu viele gleichzeitige Verbindungen vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="46081-123">Using the **user connections** option helps avoid overloading the server with too many concurrent connections.</span></span> <span data-ttu-id="46081-124">Sie können die Anzahl der Verbindungen anhand der System- und Benutzeranforderungen schätzen.</span><span class="sxs-lookup"><span data-stu-id="46081-124">You can estimate the number of connections based on system and user requirements.</span></span> <span data-ttu-id="46081-125">So ist es beispielsweise bei einem System mit vielen Benutzern nicht notwendig, dass jeder Benutzer über eine eindeutige Verbindung verfügt.</span><span class="sxs-lookup"><span data-stu-id="46081-125">For example, on a system with many users, each user would not usually require a unique connection.</span></span> <span data-ttu-id="46081-126">Verbindungen können von Benutzern gemeinsam genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="46081-126">Connections can be shared among users.</span></span> <span data-ttu-id="46081-127">Benutzer, die OLE DB-Anwendungen ausführen, benötigen eine Verbindung für jedes geöffnete Verbindungsobjekt. Benutzer, die ODBC-Anwendungen (Open Database Connectivity) ausführen, benötigen eine Verbindung für jedes aktive Verbindungshandle in der Anwendung. Benutzer, die DB-Library-Anwendungen ausführen, benötigen eine Verbindung für jeden gestarteten Prozess, der die **dbopen** -Funktion von DB-Library aufruft.</span><span class="sxs-lookup"><span data-stu-id="46081-127">Users running OLE DB applications need a connection for each open connection object, users running Open Database Connectivity (ODBC) applications need a connection for each active connection handle in the application, and users running DB-Library applications need one connection for each process started that calls the DB-Library **dbopen** function.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="46081-128">Wenn Sie diese Option verwenden müssen, sollten Sie den Wert nicht zu hoch festlegen, da jede Verbindung Aufwand benötigt, unabhängig davon, ob die Verbindung tatsächlich verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="46081-128">If you must use this option, do not set the value too high, because each connection has overhead regardless of whether the connection is being used.</span></span> <span data-ttu-id="46081-129">Wenn Sie die maximale Anzahl der Benutzerverbindungen überschreiten, erhalten Sie eine Fehlermeldung und können erst eine neue Verbindung herstellen, wenn eine andere Verbindung verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="46081-129">If you exceed the maximum number of user connections, you receive an error message and are not able to connect until another connection becomes available.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="46081-130">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="46081-130">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="46081-131">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="46081-131">Permissions</span></span>  
 <span data-ttu-id="46081-132">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="46081-132">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="46081-133">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="46081-133">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="46081-134">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="46081-134">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="46081-135">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="46081-135">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-user-connections-option"></a><span data-ttu-id="46081-136">So konfigurieren Sie die Option Benutzerverbindungen</span><span class="sxs-lookup"><span data-stu-id="46081-136">To configure the user connections option</span></span>  
  
1.  <span data-ttu-id="46081-137">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="46081-137">In Object Explorer, right-click a server and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="46081-138">Klicken Sie auf den Knoten **Verbindungen** .</span><span class="sxs-lookup"><span data-stu-id="46081-138">Click the **Connections** node.</span></span>  
  
3.  <span data-ttu-id="46081-139">Geben Sie unter **Verbindungen**im Feld **Maximum der gleichzeitigen Benutzerverbindungen** einen Wert zwischen 0 und 32.767 ein, oder wählen Sie einen Wert aus, um für die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]die maximale Anzahl gleichzeitig zulässiger Benutzerverbindungen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="46081-139">Under **Connections**, in the **Max number of concurrent connections** box, type or select a value from 0 through 32767 to set the maximum number of users that are allowed to connect simultaneously to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="46081-140">Starten Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] neu.</span><span class="sxs-lookup"><span data-stu-id="46081-140">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="46081-141">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="46081-141">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-user-connections-option"></a><span data-ttu-id="46081-142">So konfigurieren Sie die Option Benutzerverbindungen</span><span class="sxs-lookup"><span data-stu-id="46081-142">To configure the user connections option</span></span>  
  
1.  <span data-ttu-id="46081-143">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="46081-143">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="46081-144">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="46081-144">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="46081-145">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="46081-145">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="46081-146">In diesem Beispiel wird gezeigt, wie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) verwendet wird, um den Wert der Option `user connections` auf `325` Benutzer festzulegen.</span><span class="sxs-lookup"><span data-stu-id="46081-146">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the value of the `user connections` option to `325` users.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'user connections', 325 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="46081-147">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="46081-147">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-user-connections-option"></a><a name="FollowUp"></a><span data-ttu-id="46081-148">Nächster Schritt: Nach dem Konfigurieren der Option „Benutzerverbindungen“</span><span class="sxs-lookup"><span data-stu-id="46081-148">Follow Up: After you configure the user connections option</span></span>  
 <span data-ttu-id="46081-149">Der Server muss neu gestartet werden, bevor die Einstellung wirksam werden kann.</span><span class="sxs-lookup"><span data-stu-id="46081-149">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46081-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46081-150">See Also</span></span>  
 <span data-ttu-id="46081-151">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="46081-151">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="46081-152">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="46081-152">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="46081-153">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="46081-153">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
