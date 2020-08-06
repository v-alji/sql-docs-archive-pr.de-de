---
title: Benutzerdefinierte Funktionen sind in system_function_schema nicht zulässig | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- system functions [SQL Server]
- user-defined functions [SQL Server], system
ms.assetid: 3cb54053-ef65-4558-ae96-8686b6b22f4f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7242f9fda74288a2b7354ac0550ff4966e05c555
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726441"
---
# <a name="user-defined-functions-are-not-allowed-in-system_function_schema"></a><span data-ttu-id="9fdeb-102">Benutzerdefinierte Funktionen sind in 'system_function_schema' unzulässig</span><span class="sxs-lookup"><span data-stu-id="9fdeb-102">User-defined functions are not allowed in system_function_schema</span></span>
  <span data-ttu-id="9fdeb-103">Der Upgrade Advisor hat benutzerdefinierte Funktionen erkannt, die sich im Besitz der nicht dokumentierten Benutzer **system_function_schema**befinden.</span><span class="sxs-lookup"><span data-stu-id="9fdeb-103">The Upgrade Advisor detected user-defined functions that are owned by the undocumented user **system_function_schema**.</span></span> <span data-ttu-id="9fdeb-104">Sie können eine benutzerdefinierte Systemfunktion erstellen, indem Sie diesen Benutzer angeben.</span><span class="sxs-lookup"><span data-stu-id="9fdeb-104">You cannot create a user-defined system function by specifying this user.</span></span> <span data-ttu-id="9fdeb-105">Der **system_function_schema** Benutzername ist nicht vorhanden, und die mit diesem Namen (UID = 4) verknüpfte Benutzer-ID ist für das **sys** -Schema reserviert und nur auf die interne Verwendung beschränkt.</span><span class="sxs-lookup"><span data-stu-id="9fdeb-105">The **system_function_schema** user name does not exist, and the user ID that is associated with this name (UID = 4) is reserved for the **sys** schema and is restricted to internal use only.</span></span>  
  
## <a name="component"></a><span data-ttu-id="9fdeb-106">Komponente</span><span class="sxs-lookup"><span data-stu-id="9fdeb-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="9fdeb-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9fdeb-107">Description</span></span>  
 <span data-ttu-id="9fdeb-108">Die Speicherung und der Zugriff auf Systemobjekte ändern sich wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9fdeb-108">System object storage and access has changed in the following ways:</span></span>  
  
-   <span data-ttu-id="9fdeb-109">System Objekte werden in der schreibgeschützten **Ressourcen** Datenbank gespeichert, und direkte Systemobjekt Updates sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="9fdeb-109">System objects are stored in the read-only **Resource** database, and direct system object updates are not permitted.</span></span>  
  
     <span data-ttu-id="9fdeb-110">System Objekte werden logisch im **sys** -Schema jeder Datenbank angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9fdeb-110">System objects logically appear in the **sys** schema of every database.</span></span> <span data-ttu-id="9fdeb-111">Dadurch wird die Fähigkeit beibehalten, Systemfunktionen von einer beliebigen Datenbank durch Angeben eines einteiligen Funktionsnamens aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="9fdeb-111">This maintains the ability to invoke system functions from any database by specifying a one-part function name.</span></span> <span data-ttu-id="9fdeb-112">Zum Beispiel kann die Anweisung, `SELECT * FROM fn_helpcollations()` von jeder Datenbank ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9fdeb-112">For example, the statement `SELECT * FROM fn_helpcollations()` can be run from any database.</span></span>  
  
-   <span data-ttu-id="9fdeb-113">Der nicht dokumentierte Benutzer **system_function_schema** wurde entfernt.</span><span class="sxs-lookup"><span data-stu-id="9fdeb-113">The undocumented user **system_function_schema** has been removed.</span></span>  
  
-   <span data-ttu-id="9fdeb-114">Die mit **system_function_schema** (UID = 4) verknüpfte Benutzer-ID ist für das **sys** -Schema reserviert und nur auf die interne Verwendung beschränkt.</span><span class="sxs-lookup"><span data-stu-id="9fdeb-114">The user ID associated with **system_function_schema** (UID = 4) is reserved for the **sys** schema and is restricted to internal use only.</span></span>  
  
 <span data-ttu-id="9fdeb-115">Diese Änderungen haben folgende Auswirkungen auf benutzerdefinierte Systemfunktionen:</span><span class="sxs-lookup"><span data-stu-id="9fdeb-115">These changes have the following effect on user-defined system functions:</span></span>  
  
-   <span data-ttu-id="9fdeb-116">DDL-Anweisungen (Data Definition Language), die auf **system_function_schema** verweisen, können nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9fdeb-116">Data Definition Language (DDL) statements that reference **system_function_schema** will fail.</span></span> <span data-ttu-id="9fdeb-117">Beispielsweise ist die Anweisung `CREATE FUNCTION system` _ `function` \_ `schema.fn` \_ `MySystemFunction` ... wird nicht erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9fdeb-117">For example, the statement `CREATE FUNCTION system`_`function`\_`schema.fn`\_`MySystemFunction` ... will not succeed.</span></span>  
  
-   <span data-ttu-id="9fdeb-118">Nachdem Sie auf aktualisiert [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] haben, sind vorhandene Objekte, die sich im Besitz von **system_function_schema** befinden, nur im **sys** -Schema der **Master** -Datenbank enthalten.</span><span class="sxs-lookup"><span data-stu-id="9fdeb-118">After you upgrade to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], existing objects that are owned by **system_function_schema** are contained only in the **sys** schema of the **master** database.</span></span> <span data-ttu-id="9fdeb-119">Da Systemobjekte nicht geändert werden können, können diese Funktionen nie geändert oder aus der **Master** -Datenbank gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="9fdeb-119">Because system objects cannot be modified, these functions can never be changed or dropped from the **master** database.</span></span> <span data-ttu-id="9fdeb-120">Darüber hinaus können diese Funktionen nicht von anderen Datenbanken durch Angabe eines einteiligen Funktionsnamens aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9fdeb-120">Additionally, these functions cannot be invoked from other databases by specifying only a one-part function name.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="9fdeb-121">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="9fdeb-121">Corrective Action</span></span>  
 <span data-ttu-id="9fdeb-122">Vor dem Upgrade führen Sie die folgenden Tasks aus:</span><span class="sxs-lookup"><span data-stu-id="9fdeb-122">Before you upgrade , complete the following tasks:</span></span>  
  
1.  <span data-ttu-id="9fdeb-123">Ändern Sie den Besitz vorhandener benutzerdefinierter Funktionen in **dbo** mithilfe der gespeicherten System Prozedur **sp_changeobjectowner** .</span><span class="sxs-lookup"><span data-stu-id="9fdeb-123">Change the ownership of existing user-defined functions to **dbo** by using the **sp_changeobjectowner** system stored procedure.</span></span>  
  
2.  <span data-ttu-id="9fdeb-124">Sie sollten die Funktion umbenennen, damit sie nicht das Präfix 'fn_' verwendet.</span><span class="sxs-lookup"><span data-stu-id="9fdeb-124">Consider renaming the function so that is does not use the prefix 'fn_'.</span></span> <span data-ttu-id="9fdeb-125">Dadurch werden potenzielle Namenskonflikte mit aktuellen oder zukünftigen Systemfunktionen vermieden.</span><span class="sxs-lookup"><span data-stu-id="9fdeb-125">This will avoid potential name conflicts with current or future system functions.</span></span>  
  
3.  <span data-ttu-id="9fdeb-126">Fügen Sie eine Kopie der geänderten Funktionen in jeder Datenbank hinzu, die sie verwendet.</span><span class="sxs-lookup"><span data-stu-id="9fdeb-126">Add a copy of the modified functions in every database that uses them.</span></span>  
  
4.  <span data-ttu-id="9fdeb-127">Ersetzen Sie Verweise auf **system_function_schema** durch **dbo** in allen Skripts, die DDL-Anweisungen für benutzerdefinierte Funktionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="9fdeb-127">Replace references to **system_function_schema** with **dbo** in all scripts that contain user-defined function DDL statements.</span></span>  
  
5.  <span data-ttu-id="9fdeb-128">Ändern Sie Skripts, die diese Funktionen aufrufen, um entweder den zweiteiligen Namen dbo zu verwenden **.** _function_name_oder der dreiteilige Name _database_name_**.** dbo. *function_name*.</span><span class="sxs-lookup"><span data-stu-id="9fdeb-128">Modify scripts that invoke these functions to use either the two-part name dbo **.**_function_name_, or the three-part name _database_name_**.** dbo.*function_name*.</span></span>  
  
 <span data-ttu-id="9fdeb-129">Weitere Informationen finden Sie in den folgenden Themen in der SQL Server-Onlinedokumentation:</span><span class="sxs-lookup"><span data-stu-id="9fdeb-129">For more information, see the following topics in SQL Server Books Online:</span></span>  
  
-   <span data-ttu-id="9fdeb-130">"sp_changeobjectowner"</span><span class="sxs-lookup"><span data-stu-id="9fdeb-130">"sp_changeobjectowner"</span></span>  
  
-   <span data-ttu-id="9fdeb-131">"Trennung von Benutzer und Schema"</span><span class="sxs-lookup"><span data-stu-id="9fdeb-131">"User-schema Separation"</span></span>  
  
-   <span data-ttu-id="9fdeb-132">"Ressourcendatenbank"</span><span class="sxs-lookup"><span data-stu-id="9fdeb-132">"Resource Database"</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fdeb-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9fdeb-133">See Also</span></span>  
 <span data-ttu-id="9fdeb-134">[SQL Server 2014 Upgrade Advisor &#91;neuen&#93;](sql-server-2014-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="9fdeb-134">[SQL Server 2014 Upgrade Advisor &#91;new&#93;](sql-server-2014-upgrade-advisor.md) </span></span>  
 <span data-ttu-id="9fdeb-135">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="9fdeb-135">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 <span data-ttu-id="9fdeb-136">[Entfernen von Anweisungen, mit denen Systemobjekte geändert werden](../../../2014/sql-server/install/remove-statements-that-modify-system-objects.md) </span><span class="sxs-lookup"><span data-stu-id="9fdeb-136">[Remove statements that modify system objects](../../../2014/sql-server/install/remove-statements-that-modify-system-objects.md) </span></span>  
 [<span data-ttu-id="9fdeb-137">Entfernen Sie Anweisungen, mit denen Systemobjekte gelöscht werden</span><span class="sxs-lookup"><span data-stu-id="9fdeb-137">Remove statements that drop system objects</span></span>](../../../2014/sql-server/install/remove-statements-that-drop-system-objects.md)  
  
  
