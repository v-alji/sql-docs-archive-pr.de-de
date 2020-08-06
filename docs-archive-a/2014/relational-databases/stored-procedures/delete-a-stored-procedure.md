---
title: Löschen einer gespeicherten Prozedur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- removing stored procedures
- stored procedures [SQL Server], deleting
- deleting stored procedures
ms.assetid: 232dbf4d-392a-406f-af3a-579518cd8e46
author: stevestein
ms.author: sstein
ms.openlocfilehash: 418e68d4bb7c6ba6632767a554aea72e85726840
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621398"
---
# <a name="delete-a-stored-procedure"></a><span data-ttu-id="39d73-102">Löschen einer gespeicherten Prozedur</span><span class="sxs-lookup"><span data-stu-id="39d73-102">Delete a Stored Procedure</span></span>
    
##  <a name="this-topic-describes-how-to-delete-a-stored-procedure-in-sscurrent-by-using-ssmanstudiofull-or-tsql"></a><a name="Top"></a> <span data-ttu-id="39d73-103">Dieses Thema beschreibt, wie mit [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] eine gespeicherte Prozedur in [!INCLUDE[tsql](../../includes/tsql-md.md)]gelöscht werden kann.</span><span class="sxs-lookup"><span data-stu-id="39d73-103">This topic describes how to delete a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="39d73-104">**Vorbereitungen:**  [Beschränkungen](#Restrictions), [Sicherheit](#Security)</span><span class="sxs-lookup"><span data-stu-id="39d73-104">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="39d73-105">**So löschen Sie eine Prozedur mithilfe von:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="39d73-105">**To delete a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="39d73-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="39d73-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="39d73-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="39d73-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="39d73-108">Das Löschen einer Prozedur kann dazu führen, dass abhängige Objekte und Skripts fehlerhaft sind, wenn diese Objekte und Skripts nicht so aktualisiert werden, dass sie Löschung der Prozedur widerspiegeln.</span><span class="sxs-lookup"><span data-stu-id="39d73-108">Deleting a procedure can cause dependent objects and scripts to fail when the objects and scripts are not updated to reflect the removal of the procedure.</span></span> <span data-ttu-id="39d73-109">Wird jedoch eine neue Prozedur mit demselben Namen und denselben Parametern erstellt, um die gelöschte Prozedur zu ersetzen, können andere Objekte, die darauf verweisen, weiterhin erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="39d73-109">However, if a new procedure of the same name and the same parameters is created to replace the one that was deleted, other objects that reference it will still process successfully.</span></span> <span data-ttu-id="39d73-110">Weitere Informationen finden Sie unter [Anzeigen der Abhängigkeiten einer gespeicherten Prozedur](view-the-dependencies-of-a-stored-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="39d73-110">For more information, see [View the Dependencies of a Stored Procedure](view-the-dependencies-of-a-stored-procedure.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="39d73-111">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="39d73-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="39d73-112">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="39d73-112">Permissions</span></span>  
 <span data-ttu-id="39d73-113">Erfordert die ALTER-Berechtigung im Schema, zu der die Prozedur gehört, oder die CONTROL-Berechtigung für die Prozedur.</span><span class="sxs-lookup"><span data-stu-id="39d73-113">Requires ALTER permission on the schema to which the procedure belongs, or CONTROL permission on the procedure.</span></span>  
  
##  <a name="how-to-delete-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="39d73-114">Vorgehensweise: Löschen einer gespeicherten Prozedur</span><span class="sxs-lookup"><span data-stu-id="39d73-114">How to Delete a Stored Procedure</span></span>  
 <span data-ttu-id="39d73-115">Sie können eine der folgenden Anwendungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="39d73-115">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="39d73-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="39d73-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="39d73-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="39d73-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="39d73-118">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="39d73-118">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="39d73-119">**So löschen Sie eine Prozedur im Objekt-Explorer**</span><span class="sxs-lookup"><span data-stu-id="39d73-119">**To delete a procedure in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="39d73-120">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="39d73-120">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="39d73-121">Erweitern Sie **Datenbanken**, erweitern Sie die Datenbank, zu der die Prozedur gehört, und erweitern Sie dann **Programmierbarkeit**.</span><span class="sxs-lookup"><span data-stu-id="39d73-121">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="39d73-122">Erweitern Sie **Gespeicherte Prozeduren**, klicken Sie mit der rechten Maustaste auf die zu entfernende Prozedur, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="39d73-122">Expand **Stored Procedures**, right-click the procedure to remove, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="39d73-123">Klicken Sie auf **Abhängigkeiten anzeigen**, um die von der Prozedur abhängigen Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="39d73-123">To view objects that depend on the procedure, click **Show Dependencies**.</span></span>  
  
5.  <span data-ttu-id="39d73-124">Bestätigen Sie, dass die richtige Prozedur ausgewählt wurde, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="39d73-124">Confirm the correct procedure is selected, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="39d73-125">Entfernen Sie in allen abhängigen Objekten und Skripts die Verweise auf die Prozedur.</span><span class="sxs-lookup"><span data-stu-id="39d73-125">Remove references to the procedure from any dependent objects and scripts.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="39d73-126">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="39d73-126">Using Transact-SQL</span></span>  
 <span data-ttu-id="39d73-127">**So löschen Sie eine Prozedur im Abfrage-Editor**</span><span class="sxs-lookup"><span data-stu-id="39d73-127">**To delete a procedure in Query Editor**</span></span>  
  
1.  <span data-ttu-id="39d73-128">Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="39d73-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="39d73-129">Erweitern Sie **Datenbanken**, erweitern Sie die Datenbank, in die die Prozedur gehört, oder wählen Sie in der Symbolleiste die Datenbank aus der Liste der verfügbaren Datenbanken aus.</span><span class="sxs-lookup"><span data-stu-id="39d73-129">Expand **Databases**, expand the database in which the procedure belongs, or, from the tool bar, select the database from the list of available databases.</span></span>  
  
3.  <span data-ttu-id="39d73-130">Klicken Sie im Menü Datei auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="39d73-130">On the File menu, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="39d73-131">Rufen Sie den Namen der gespeicherten Prozedur ab, der aus der aktuellen Datenbank entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="39d73-131">Obtain the name of stored procedure to remove in the current database.</span></span> <span data-ttu-id="39d73-132">Erweitern Sie im Objekt-Explorer **Programmierbarkeit** , und erweitern Sie dann **Gespeicherte Prozeduren**.</span><span class="sxs-lookup"><span data-stu-id="39d73-132">From Object Explorer, expand **Programmability** and then expand **Stored Procedures**.</span></span> <span data-ttu-id="39d73-133">Führen Sie stattdessen im Abfrage-Editor die folgende Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="39d73-133">Alternatively, in the query editor, run the following statement.</span></span>  
  
    ```sql  
    SELECT name AS procedure_name   
        ,SCHEMA_NAME(schema_id) AS schema_name  
        ,type_desc  
        ,create_date  
        ,modify_date  
    FROM sys.procedures;  
    ```  
  
5.  <span data-ttu-id="39d73-134">Kopieren und fügen Sie das folgende Beispiel in den Abfrage-Editor ein, und fügen Sie einen Namen der gespeicherten Prozedur ein, der aus der aktuellen Datenbank gelöscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="39d73-134">Copy and paste the following example into the query editor and insert a stored procedure name to delete from the current database.</span></span>  
  
    ```sql  
    DROP PROCEDURE <stored procedure name>;  
    GO  
    ```  
  
6.  <span data-ttu-id="39d73-135">Entfernen Sie in allen abhängigen Objekten und Skripts die Verweise auf die Prozedur.</span><span class="sxs-lookup"><span data-stu-id="39d73-135">Remove references to the procedure from any dependent objects and scripts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39d73-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="39d73-136">See Also</span></span>  
 <span data-ttu-id="39d73-137">[Erstellen einer gespeicherten Prozedur](create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="39d73-137">[Create a Stored Procedure](create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="39d73-138">[Ändern einer gespeicherten Prozedur](modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="39d73-138">[Modify a Stored Procedure](modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="39d73-139">[Umbenennen einer gespeicherten Prozedur](rename-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="39d73-139">[Rename a Stored Procedure](rename-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="39d73-140">[Anzeigen der Definition einer gespeicherten Prozedur](view-the-definition-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="39d73-140">[View the Definition of a Stored Procedure](view-the-definition-of-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="39d73-141">[Anzeigen der Abhängigkeiten einer gespeicherten Prozedur](view-the-dependencies-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="39d73-141">[View the Dependencies of a Stored Procedure](view-the-dependencies-of-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="39d73-142">DROP PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="39d73-142">DROP PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-procedure-transact-sql)  
  
  
