---
title: OLE-Automatisierungsobjekte in Transact-SQL | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: conceptual
helpviewer_keywords:
- triggers [SQL Server], OLE Automation
- batches [SQL Server], OLE Automation
- OLE Automation [SQL Server]
- OLE Automation [SQL Server], about OLE Automation
ms.assetid: a887d956-4cd0-400a-aa96-00d7abd7c44b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1f36846565bb60fbf875e9babdabbb6d1667f5ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630624"
---
# <a name="ole-automation-objects-in-transact-sql"></a><span data-ttu-id="4d394-102">OLE-Automatisierungsobjekte in Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4d394-102">OLE Automation Objects in Transact-SQL</span></span>
  [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="4d394-103">enthält mehrere gespeicherte Systemprozeduren, die Verweise auf OLE-Automatisierungsobjekte in [!INCLUDE[tsql](../../includes/tsql-md.md)] -Batches, gespeicherten Prozeduren und Triggern ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="4d394-103">includes several system stored procedures that allow OLE Automation objects to be referenced in [!INCLUDE[tsql](../../includes/tsql-md.md)] batches, stored procedures, and triggers.</span></span> <span data-ttu-id="4d394-104">Diese gespeicherten Systemprozeduren werden als erweiterte gespeicherte Prozeduren ausgeführt, und die OLE-Automatisierungsobjekte, die über die gespeicherten Prozeduren ausgeführt werden, werden wie eine erweiterte gespeicherte Prozedur im Adressraum einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4d394-104">These system stored procedures run as extended stored procedures, and the OLE Automation objects that are executed through the stored procedures run in the address space of an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] in the same way that an extended stored procedure runs.</span></span>  
  
 <span data-ttu-id="4d394-105">Die gespeicherten OLE-Automatisierungsprozeduren ermöglichen es [!INCLUDE[tsql](../../includes/tsql-md.md)] -Batches, auf SQL-DMO-Objekte und benutzerdefinierte OLE-Automatisierungsobjekte zu verweisen, wie etwa Objekte, die die **IDispatch** -Schnittstelle verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="4d394-105">The OLE Automation stored procedures enable [!INCLUDE[tsql](../../includes/tsql-md.md)] batches to reference SQL-DMO objects and custom OLE Automation objects, such as objects that expose the **IDispatch** interface.</span></span> <span data-ttu-id="4d394-106">Ein benutzerdefinierter In-Process-OLE-Server, der mithilfe von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] erstellt wurde, muss mit einem (mit der Anweisung **On Error GoTo** angegebenen) Fehlerhandler für die Unterroutinen **Class_Initialize** und **Class_Terminate** ausgestattet sein.</span><span class="sxs-lookup"><span data-stu-id="4d394-106">A custom in-process OLE server that is created by using [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] must have an error handler (specified with the **On Error GoTo** statement) for the **Class_Initialize** and **Class_Terminate** subroutines.</span></span> <span data-ttu-id="4d394-107">Nicht behandelte Fehler in den Unterroutinen **Class_Initialize** und **Class_Terminate** können unvorhersehbare Fehler verursachen, wie z.B. eine Zugriffsverletzungen in einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d394-107">Unhandled errors in the **Class_Initialize** and **Class_Terminate** subroutines can cause unpredictable errors, such as an access violation in an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="4d394-108">Fehlerhandler werden auch für andere Unterroutinen empfohlen.</span><span class="sxs-lookup"><span data-stu-id="4d394-108">Error handlers for other subroutines are also recommended.</span></span>  
  
 <span data-ttu-id="4d394-109">Der erste Schritt beim Verwenden eines OLE-Automatisierungsobjekts in [!INCLUDE[tsql](../../includes/tsql-md.md)] ist das Aufrufen der gespeicherten Systemprozedur **sp_OACreate** , um eine Instanz des Objekts im Adressraum der Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)]zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4d394-109">The first step when using an OLE Automation object in [!INCLUDE[tsql](../../includes/tsql-md.md)] is to call the **sp_OACreate** system stored procedure to create an instance of the object in the address space of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="4d394-110">Verwenden Sie nach dem Erstellen einer Instanz des Objekts die folgenden gespeicherten Prozeduren, um mit den Eigenschaften, Methoden und Fehlerinformationen im Zusammenhang mit dem Objekt zu arbeiten:</span><span class="sxs-lookup"><span data-stu-id="4d394-110">After an instance of the object has been created, call the following stored procedures to work with the properties, methods, and error information related to the object:</span></span>  
  
-   <span data-ttu-id="4d394-111">**sp_OAGetProperty** ruft den Wert einer Eigenschaft ab.</span><span class="sxs-lookup"><span data-stu-id="4d394-111">**sp_OAGetProperty** obtains the value of a property.</span></span>  
  
-   <span data-ttu-id="4d394-112">**sp_OASetProperty** legt den Wert einer Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="4d394-112">**sp_OASetProperty** sets the value of a property.</span></span>  
  
-   <span data-ttu-id="4d394-113">**sp_OAMethod** ruft eine Methode auf.</span><span class="sxs-lookup"><span data-stu-id="4d394-113">**sp_OAMethod** calls a method.</span></span>  
  
-   <span data-ttu-id="4d394-114">**sp_OAGetErrorInfo** ruft die letzten Fehlerinformationen ab.</span><span class="sxs-lookup"><span data-stu-id="4d394-114">**sp_OAGetErrorInfo** obtains the most recent error information.</span></span>  
  
 <span data-ttu-id="4d394-115">Wenn das Objekt nicht mehr benötigt wird, rufen Sie **sp_OADestroy** auf, um die Zuordnung der mit **sp_OACreate**erstellten Instanz des Objekts aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="4d394-115">When there is no more need for the object, call **sp_OADestroy** to deallocate the instance of the object created by using **sp_OACreate**.</span></span>  
  
 <span data-ttu-id="4d394-116">OLE-Automatisierungsobjekte geben Daten durch Eigenschaftswerte und Methoden zurück.</span><span class="sxs-lookup"><span data-stu-id="4d394-116">OLE Automation objects return data through property values and methods.</span></span> <span data-ttu-id="4d394-117">**sp_OAGetProperty** und **sp_OAMethod** geben diese Datenwerte als Resultset zurück.</span><span class="sxs-lookup"><span data-stu-id="4d394-117">**sp_OAGetProperty** and **sp_OAMethod** return these data values in the form of a result set.</span></span>  
  
 <span data-ttu-id="4d394-118">Der Gültigkeitsbereich eines OLE-Automatisierungsobjekts ist ein Batch.</span><span class="sxs-lookup"><span data-stu-id="4d394-118">The scope of an OLE Automation object is a batch.</span></span> <span data-ttu-id="4d394-119">Alle Verweise auf das Objekt müssen in einem einzelnen Batch, einer gespeicherten Prozedur oder einem Trigger enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="4d394-119">All references to the object must be contained in a single batch, stored procedure, or trigger.</span></span>  
  
 <span data-ttu-id="4d394-120">Beim Verweisen auf Objekte unterstützen die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -OLE-Automatisierungsobjekte das Traversieren des Objekts, auf das verwiesen wird, auf andere Objekte, die es enthält.</span><span class="sxs-lookup"><span data-stu-id="4d394-120">When it references objects, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] OLE Automation objects support traversing the referenced object to other objects that it contains.</span></span> <span data-ttu-id="4d394-121">Wenn beispielsweise das SQL-DMO-Objekt **SQLServer** verwendet wird, können Verweise auf Datenbanken und Tabellen erfolgen, die sich auf dem betreffenden Server befinden.</span><span class="sxs-lookup"><span data-stu-id="4d394-121">For example, when using the SQL-DMO **SQLServer** object, references can be made to databases and tables contained on that server.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="4d394-122">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="4d394-122">Related Content</span></span>  
 [<span data-ttu-id="4d394-123">Objekthierarchiesyntax &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-123">Object Hierarchy Syntax &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/object-hierarchy-syntax-transact-sql)  
  
 [<span data-ttu-id="4d394-124">Oberflächenkonfiguration</span><span class="sxs-lookup"><span data-stu-id="4d394-124">Surface Area Configuration</span></span>](../security/surface-area-configuration.md)  
  
 [<span data-ttu-id="4d394-125">OLE-Automatisierungsprozeduren (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="4d394-125">Ole Automation Procedures Server Configuration Option</span></span>](../../database-engine/configure-windows/ole-automation-procedures-server-configuration-option.md)  
  
 [<span data-ttu-id="4d394-126">sp_OACreate &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-126">sp_OACreate &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oacreate-transact-sql)  
  
 [<span data-ttu-id="4d394-127">sp_OAGetProperty &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-127">sp_OAGetProperty &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oagetproperty-transact-sql)  
  
 [<span data-ttu-id="4d394-128">sp_OASetProperty &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-128">sp_OASetProperty &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oasetproperty-transact-sql)  
  
 [<span data-ttu-id="4d394-129">sp_OAMethod &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-129">sp_OAMethod &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oamethod-transact-sql)  
  
 [<span data-ttu-id="4d394-130">sp_OAGetErrorInfo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-130">sp_OAGetErrorInfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oageterrorinfo-transact-sql)  
  
 [<span data-ttu-id="4d394-131">sp_OADestroy &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4d394-131">sp_OADestroy &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-oadestroy-transact-sql)  
  
  
