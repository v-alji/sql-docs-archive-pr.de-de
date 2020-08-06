---
title: Festlegen des Einzelbenutzermodus für eine Datenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- single-user mode [SQL Server], database option
ms.assetid: fb5254eb-b635-4b39-8361-136fd36f2b1f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 16281b5fa7d4f6698bb6c498915bfa84779b3e14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695694"
---
# <a name="set-a-database-to-single-user-mode"></a><span data-ttu-id="0423a-102">Festlegen des Einzelbenutzermodus für eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="0423a-102">Set a Database to Single-user Mode</span></span>
  <span data-ttu-id="0423a-103">In diesem Thema wird beschrieben, wie für eine benutzerdefinierte Datenbank in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]der Einzelbenutzermodus festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="0423a-103">This topic describes how to set a user-defined database to single-user mode in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="0423a-104">Der Einzelbenutzermodus gibt an, dass jeweils nur ein Benutzer auf die Datenbank zugreifen kann. Er wird im Allgemeinen für Wartungsaktionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="0423a-104">Single-user mode specifies that only one user at a time can access the database and is generally used for maintenance actions.</span></span>  
  
 <span data-ttu-id="0423a-105">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="0423a-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0423a-106">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="0423a-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0423a-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="0423a-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="0423a-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="0423a-108">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="0423a-109">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="0423a-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0423a-110">**So legen Sie den Einzelbenutzermodus für eine Datenbank fest mit:**</span><span class="sxs-lookup"><span data-stu-id="0423a-110">**To set a database to single-user mode, using:**</span></span>  
  
     [<span data-ttu-id="0423a-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0423a-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0423a-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0423a-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0423a-113">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="0423a-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="0423a-114">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="0423a-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="0423a-115">Wenn zu dem Zeitpunkt, an dem Sie den Einzelbenutzermodus für die Datenbank festlegen, andere Benutzer mit der Datenbank verbunden sind, werden ihre Verbindungen mit der Datenbank ohne Warnung geschlossen.</span><span class="sxs-lookup"><span data-stu-id="0423a-115">If other users are connected to the database at the time that you set the database to single-user mode, their connections to the database will be closed without warning.</span></span>  
  
-   <span data-ttu-id="0423a-116">Die Datenbank verbleibt im Einzelbenutzermodus, selbst wenn sich der Benutzer, der die Option festgelegt hat, abmeldet.</span><span class="sxs-lookup"><span data-stu-id="0423a-116">The database remains in single-user mode even if the user that set the option logs off.</span></span> <span data-ttu-id="0423a-117">Dadurch kann ein anderer Benutzer (aber nur einer) eine Verbindung mit der Datenbank herstellen.</span><span class="sxs-lookup"><span data-stu-id="0423a-117">At that point, a different user, but only one, can connect to the database.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="0423a-118">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="0423a-118">Prerequisites</span></span>  
  
-   <span data-ttu-id="0423a-119">Bevor Sie die Datenbank auf SINGLE_USER festlegen, müssen Sie überprüfen, ob die AUTO_UPDATE_STATISTICS_ASYNC-Option auf OFF festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="0423a-119">Before you set the database to SINGLE_USER, verify that the AUTO_UPDATE_STATISTICS_ASYNC option is set to OFF.</span></span> <span data-ttu-id="0423a-120">Wenn diese Option auf ON festgelegt ist, stellt der Hintergrundthread, der zum Aktualisieren von Statistiken verwendet wird, eine Verbindung mit der Datenbank her, und Sie können im Einzelbenutzermodus nicht auf die Datenbank zugreifen.</span><span class="sxs-lookup"><span data-stu-id="0423a-120">When this option is set to ON, the background thread that is used to update statistics takes a connection against the database, and you will be unable to access the database in single-user mode.</span></span> <span data-ttu-id="0423a-121">Weitere Informationen zu dieser Einstellung finden Sie unter [ALTER DATABASE SET-Optionen &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="0423a-121">For more information, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0423a-122">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="0423a-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0423a-123">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="0423a-123">Permissions</span></span>  
 <span data-ttu-id="0423a-124">Erfordert die ALTER-Berechtigung für die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="0423a-124">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0423a-125">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0423a-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-a-database-to-single-user-mode"></a><span data-ttu-id="0423a-126">So legen Sie den Einzelbenutzermodus für eine Datenbank fest</span><span class="sxs-lookup"><span data-stu-id="0423a-126">To set a database to single-user mode</span></span>  
  
1.  <span data-ttu-id="0423a-127">Stellen Sie im **Objekt-Explorer**eine Verbindung zu einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="0423a-127">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="0423a-128">Klicken Sie mit der rechten Maustaste auf die zu ändernde Datenbank, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="0423a-128">Right-click the database to change, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="0423a-129">Klicken Sie im Dialogfeld **Datenbankeigenschaften** auf die Seite **Optionen** .</span><span class="sxs-lookup"><span data-stu-id="0423a-129">In the **Database Properties** dialog box, click the **Options** page.</span></span>  
  
4.  <span data-ttu-id="0423a-130">Wählen Sie unter der Option **Zugriff beschränken** den Eintrag **Single**aus.</span><span class="sxs-lookup"><span data-stu-id="0423a-130">From the **Restrict Access** option, select **Single**.</span></span>  
  
5.  <span data-ttu-id="0423a-131">Wenn andere Benutzer mit der Datenbank verbunden sind, wird die Meldung **Geöffnete Verbindungen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0423a-131">If other users are connected to the database, an **Open Connections** message will appear.</span></span> <span data-ttu-id="0423a-132">Klicken Sie zum Ändern der Eigenschaft und Schließen aller anderen Verbindungen auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="0423a-132">To change the property and close all other connections, click **Yes**.</span></span>  
  
 <span data-ttu-id="0423a-133">Mit dieser Prozedur können Sie für die Datenbank auch einen Mehrbenutzer- oder beschränkten Zugriff festlegen.</span><span class="sxs-lookup"><span data-stu-id="0423a-133">You can also set the database to Multiple or Restricted access by using this procedure.</span></span> <span data-ttu-id="0423a-134">Weitere Informationen zu den Optionen von „Zugriff beschränken“ finden Sie unter [Datenbankeigenschaften &#40;Seite Optionen&#41;](database-properties-options-page.md).</span><span class="sxs-lookup"><span data-stu-id="0423a-134">For more information about the Restrict Access options, see [Database Properties &#40;Options Page&#41;](database-properties-options-page.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0423a-135">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0423a-135">Using Transact-SQL</span></span>  
  
#### <a name="to-set-a-database-to-single-user-mode"></a><span data-ttu-id="0423a-136">So legen Sie den Einzelbenutzermodus für eine Datenbank fest</span><span class="sxs-lookup"><span data-stu-id="0423a-136">To set a database to single-user mode</span></span>  
  
1.  <span data-ttu-id="0423a-137">Stellen Sie eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="0423a-137">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0423a-138">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="0423a-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0423a-139">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="0423a-139">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="0423a-140">In diesem Beispiel wird die Datenbank auf den `SINGLE_USER` -Modus festgelegt, um exklusiven Zugriff zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0423a-140">This example sets the database to `SINGLE_USER` mode to obtain exclusive access.</span></span> <span data-ttu-id="0423a-141">Anschließend wird in dem Beispiel der Status der [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] -Datenbank auf `READ_ONLY` festgelegt und der Zugriff auf die Datenbank an alle Benutzer zurückgegeben. Die Beendigungsoption `WITH ROLLBACK IMMEDIATE` wird in der ersten `ALTER DATABASE` -Anweisung angegeben.</span><span class="sxs-lookup"><span data-stu-id="0423a-141">The example then sets the state of the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database to `READ_ONLY` and returns access to the database to all users.The termination option `WITH ROLLBACK IMMEDIATE` is specified in the first `ALTER DATABASE` statement.</span></span> <span data-ttu-id="0423a-142">Dies führt dazu, dass für alle unvollständigen Transaktionen ein Rollback ausgeführt wird und alle anderen Verbindungen zur [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] -Datenbank sofort getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="0423a-142">This will cause all incomplete transactions to be rolled back and any other connections to the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database to be immediately disconnected.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase8](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase8)]  
  
## <a name="see-also"></a><span data-ttu-id="0423a-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0423a-143">See Also</span></span>  
 [<span data-ttu-id="0423a-144">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0423a-144">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
