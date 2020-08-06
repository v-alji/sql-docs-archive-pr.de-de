---
title: Konfigurieren der Serverkonfigurationsoption „Umstellungsjahr für Angaben mit zwei Ziffern“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- two digit year cutoff option
- four-digit years [SQL Server]
ms.assetid: d94e81b6-f2e6-47ef-b497-ec3d827a1646
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c31c1d87c8b743132dd90d495f73ef711dc1f813
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616165"
---
# <a name="configure-the-two-digit-year-cutoff-server-configuration-option"></a><span data-ttu-id="c1f84-102">Konfigurieren der Serverkonfigurationsoption Umstellungsjahr für Angaben mit zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="c1f84-102">Configure the two digit year cutoff Server Configuration Option</span></span>
  <span data-ttu-id="c1f84-103">In diesem Thema wird beschrieben, wie die Serverkonfigurationsoption **Umstellungsjahr für Angaben mit zwei Ziffern** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="c1f84-103">This topic describes how to configure the **two digit year cutoff** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c1f84-104">Mithilfe der Option **Umstellungsjahr für Angaben mit zwei Ziffern** können Sie eine ganze Zahl zwischen 1753 und 9999 angeben, die das Umstellungsjahr für das Interpretieren zweistelliger Jahre als vierstellige Jahre darstellt.</span><span class="sxs-lookup"><span data-stu-id="c1f84-104">The **two digit year cutoff** option specifies an integer from 1753 to 9999 that represents the cutoff year for interpreting two-digit years as four-digit years.</span></span> <span data-ttu-id="c1f84-105">Der Standardzeitraum für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ist 1950 bis 2049, wobei 2049 das Umstellungsjahr ist.</span><span class="sxs-lookup"><span data-stu-id="c1f84-105">The default time span for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is 1950-2049, which represents a cutoff year of 2049.</span></span> <span data-ttu-id="c1f84-106">Dies bedeutet, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eine zweistellige Jahreszahl von 49 als 2049, eine zweistellige Jahreszahl von 50 als 1950 und eine zweistellige Jahreszahl von 99 als 1999 interpretiert.</span><span class="sxs-lookup"><span data-stu-id="c1f84-106">This means that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interprets a two-digit year of 49 as 2049, a two-digit year of 50 as 1950, and a two-digit year of 99 as 1999.</span></span> <span data-ttu-id="c1f84-107">Übernehmen Sie bei der Einstellung den Standardwert, um Abwärtskompatibilität zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="c1f84-107">To maintain backward compatibility, leave the setting at the default value.</span></span>  
  
 <span data-ttu-id="c1f84-108">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="c1f84-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c1f84-109">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="c1f84-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c1f84-110">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="c1f84-110">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="c1f84-111">Security</span><span class="sxs-lookup"><span data-stu-id="c1f84-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c1f84-112">**So konfigurieren Sie die Option Umstellungsjahr für Angaben mit zwei Ziffern mit:**</span><span class="sxs-lookup"><span data-stu-id="c1f84-112">**To configure the two digit year cutoff option, using:**</span></span>  
  
     [<span data-ttu-id="c1f84-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c1f84-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c1f84-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c1f84-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="c1f84-115">**Nachverfolgung:**  [Nach dem Konfigurieren der Option „Umstellungsjahr für Angaben mit zwei Ziffern“](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="c1f84-115">**Follow Up:**  [After you configure the two digit year cutoff option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c1f84-116">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="c1f84-116">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="c1f84-117">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="c1f84-117">Recommendations</span></span>  
  
-   <span data-ttu-id="c1f84-118">Diese Option ist eine erweiterte Option und sollte ausschließlich von einem erfahrenen Datenbankadministrator oder einem zertifizierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Techniker geändert werden.</span><span class="sxs-lookup"><span data-stu-id="c1f84-118">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="c1f84-119">OLE-Automatisierungsobjekte verwenden 2030 als Umstellungsjahr für Angaben mit zwei Ziffern.</span><span class="sxs-lookup"><span data-stu-id="c1f84-119">OLE Automation objects use 2030 as the two-digit cutoff year.</span></span> <span data-ttu-id="c1f84-120">Mithilfe der Option **Umstellungsjahr für Angaben mit zwei Ziffern** können Sie Konsistenz zwischen den Datenwerten von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und Clientanwendungen herstellen.</span><span class="sxs-lookup"><span data-stu-id="c1f84-120">You can use the **two digit year cutoff** option to provide consistency in date values between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and client applications.</span></span> <span data-ttu-id="c1f84-121">Wenn Sie die Mehrdeutigkeit von Daten vermeiden möchten, sollten Sie allerdings vierstellige Jahre verwenden.</span><span class="sxs-lookup"><span data-stu-id="c1f84-121">However, to avoid ambiguity with dates, use four-digit years in your data.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c1f84-122">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c1f84-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c1f84-123">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="c1f84-123">Permissions</span></span>  
 <span data-ttu-id="c1f84-124">Die Ausführungsberechtigungen für **sp_configure** ohne Parameter oder nur mit dem ersten Parameter werden standardmäßig allen Benutzern erteilt.</span><span class="sxs-lookup"><span data-stu-id="c1f84-124">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="c1f84-125">Zum Ausführen von **sp_configure** mit beiden Parametern zum Ändern einer Konfigurationsoption oder zum Ausführen der RECONFIGURE-Anweisung muss einem Benutzer die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="c1f84-125">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="c1f84-126">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="c1f84-126">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c1f84-127">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c1f84-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-two-digit-year-cutoff-option"></a><span data-ttu-id="c1f84-128">So konfigurieren Sie die Option Umstellungsjahr für Angaben mit zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="c1f84-128">To configure the two digit year cutoff option</span></span>  
  
1.  <span data-ttu-id="c1f84-129">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="c1f84-129">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="c1f84-130">Klicken Sie auf den **Sonstige Servereinstellungen** -Knoten.</span><span class="sxs-lookup"><span data-stu-id="c1f84-130">Click the **Misc server settings** node.</span></span>  
  
3.  <span data-ttu-id="c1f84-131">Geben Sie unter **Unterstützung zweistelliger Jahresangaben**im Feld **Bei Eingabe einer zweistelligen Jahresangabe** **soll diese interpretiert werden als Jahr zwischen** einen Wert ein, der das Endjahr des Zeitraums angibt, oder wählen Sie einen Wert aus.</span><span class="sxs-lookup"><span data-stu-id="c1f84-131">Under **Two digit year support**, in the **When a two digit year is entered**, **interpret it as a year between** box, type or select a value that is the ending year of the time span.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c1f84-132">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c1f84-132">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-two-digit-year-cutoff-option"></a><span data-ttu-id="c1f84-133">So konfigurieren Sie die Option Umstellungsjahr für Angaben mit zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="c1f84-133">To configure the two digit year cutoff option</span></span>  
  
1.  <span data-ttu-id="c1f84-134">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="c1f84-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c1f84-135">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="c1f84-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c1f84-136">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c1f84-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="c1f84-137">In diesem Beispiel wird gezeigt, wie [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) verwendet wird, um den Wert der Option `two digit year cutoff` auf `2030`festzulegen.</span><span class="sxs-lookup"><span data-stu-id="c1f84-137">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `two digit year cutoff` option to `2030`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'two digit year cutoff', 2030 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="c1f84-138">Weitere Informationen finden Sie unter [Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md)angezeigt oder konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="c1f84-138">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-two-digit-year-cutoff-option"></a><a name="FollowUp"></a><span data-ttu-id="c1f84-139">Nächster Schritt: Nach dem Konfigurieren der Option „Umstellungsjahr für Angaben mit zwei Ziffern“</span><span class="sxs-lookup"><span data-stu-id="c1f84-139">Follow Up: After you configure the two digit year cutoff option</span></span>  
 <span data-ttu-id="c1f84-140">Die Einstellung tritt ohne Neustarten des Servers sofort in Kraft.</span><span class="sxs-lookup"><span data-stu-id="c1f84-140">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1f84-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1f84-141">See Also</span></span>  
 <span data-ttu-id="c1f84-142">[Serverkonfigurationsoptionen &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c1f84-142">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="c1f84-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c1f84-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="c1f84-144">RECONFIGURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c1f84-144">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  
