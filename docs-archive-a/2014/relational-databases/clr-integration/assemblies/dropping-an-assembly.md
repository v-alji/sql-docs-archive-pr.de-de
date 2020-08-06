---
title: Löschen einer Assembly | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- removing assemblies
- DROP ASSEMBLY statement
- assemblies [CLR integration], removing
- dropping assemblies
ms.assetid: 03481034-dc91-4488-ab24-ba44243e2690
author: rothja
ms.author: jroth
ms.openlocfilehash: 45d02cbb57459a4c1c11330446021c32dc897353
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720032"
---
# <a name="dropping-an-assembly"></a><span data-ttu-id="57172-102">Löschen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="57172-102">Dropping an Assembly</span></span>
  <span data-ttu-id="57172-103">Assemblys, die mithilfe der CREATE ASSEMBLY-Anweisung in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] registriert wurden, können gelöscht oder verworfen werden, wenn die von ihnen bereitgestellte Funktionalität nicht mehr benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="57172-103">Assemblies that have been registered in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] using the CREATE ASSEMBLY statement can be deleted, or dropped, when the functionality they provide is no longer needed.</span></span> <span data-ttu-id="57172-104">Durch das Löschen einer Assembly werden die Assembly sowie alle zugehörigen Dateien, wie Debugdateien, aus der Datenbank entfernt.</span><span class="sxs-lookup"><span data-stu-id="57172-104">Dropping an assembly removes the assembly and all of its associated files, such as debug files, from the database.</span></span> <span data-ttu-id="57172-105">Zum Löschen einer Assembly verwenden Sie die DROP ASSEMBLY-Anweisung mit der folgenden Syntax:</span><span class="sxs-lookup"><span data-stu-id="57172-105">To drop an assembly, use the DROP ASSEMBLY statement with the following syntax:</span></span>  
  
```  
DROP ASSEMBLY MyDotNETAssembly  
```  
  
 <span data-ttu-id="57172-106">Die DROP ASSEMBLY-Anweisung stört nicht die aktuelle Ausführung von Code, der auf die Assembly verweist, aber nach der Ausführung der DROP ASSEMBLY-Anweisung schlagen alle Versuche fehl, den Assemblycode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="57172-106">DROP ASSEMBLY does not interfere with any code referencing the assembly that is currently running, but after DROP ASSEMBLY executes, any attempts to invoke the assembly code fail.</span></span>  
  
 <span data-ttu-id="57172-107">DROP ASSEMBLY gibt einen Fehler zurück, wenn eine andere Assembly in der Datenbank auf die Assembly verweist oder diese von CLR-basierten Funktionen (Common Language Runtime), -Prozeduren, -Triggern, benutzerdefinierten Typen (User Defined Types, UDTs) oder Aggregaten in der aktuellen Datenbank verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="57172-107">DROP ASSEMBLY returns an error if the assembly is referenced by another assembly that exists in the database, or if it is used by common language runtime (CLR) functions, procedures, triggers, user-defined types (UDTs), or user-defined aggregates (UDAs) in the current database.</span></span> <span data-ttu-id="57172-108">Löschen Sie zuerst die in der Assembly enthaltenen verwalteten Datenbankobjekte mit entsprechenden DROP AGGREGATE-, DROP FUNCTION-, DROP PROCEDURE-, DROP TRIGGER- und DROP TYPE-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="57172-108">First use the DROP AGGREGATE, DROP FUNCTION, DROP PROCEDURE, DROP TRIGGER, and DROP TYPE statements to delete any managed database objects contained in the assembly.</span></span>  
  
## <a name="removing-a-udt-from-the-database"></a><span data-ttu-id="57172-109">Entfernen eines UDTs aus der Datenbank</span><span class="sxs-lookup"><span data-stu-id="57172-109">Removing a UDT from the Database</span></span>  
 <span data-ttu-id="57172-110">Mit der DROP TYPE-Anweisung wird ein UDT aus der aktuellen Datenbank entfernt.</span><span class="sxs-lookup"><span data-stu-id="57172-110">The DROP TYPE statement removes a UDT from the current database.</span></span> <span data-ttu-id="57172-111">Sobald der UDT entfernt wurde, können Sie die Assembly mit der DROP ASSEMBLY-Anweisung aus der Datenbank löschen.</span><span class="sxs-lookup"><span data-stu-id="57172-111">Once a UDT is dropped, you can use the DROP ASSEMBLY statement to drop the assembly from the database.</span></span>  
  
 <span data-ttu-id="57172-112">Die DROP TYPE-Anweisung schlägt fehl, wenn Objekte vom UDT abhängen, wie in den folgenden Situationen:</span><span class="sxs-lookup"><span data-stu-id="57172-112">The DROP TYPE statement fails if objects depend on the UDT, as in the following situations:</span></span>  
  
-   <span data-ttu-id="57172-113">Tabellen in der Datenbank, die mit dem UDT definierte Spalten enthalten.</span><span class="sxs-lookup"><span data-stu-id="57172-113">Tables in the database that contain columns defined using the UDT.</span></span>  
  
-   <span data-ttu-id="57172-114">Funktionen, gespeicherte Prozeduren oder Trigger, die Variablen und Parameter des UDT verwenden und in der Datenbank mit der WITH SCHEMABINDING-Klausel erzeugt wurden.</span><span class="sxs-lookup"><span data-stu-id="57172-114">Functions, stored procedures, or triggers that use variables or parameters of the UDT, created in the database with the WITH SCHEMABINDING clause.</span></span>  
  
### <a name="finding-udt-dependencies"></a><span data-ttu-id="57172-115">Ermitteln von UDT-Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="57172-115">Finding UDT Dependencies</span></span>  
 <span data-ttu-id="57172-116">Sie müssen zuerst alle abhängigen Objekte löschen und dann die DROP TYPE-Anweisung ausführen.</span><span class="sxs-lookup"><span data-stu-id="57172-116">You must first drop all dependent objects, and then execute the DROP TYPE statement.</span></span> <span data-ttu-id="57172-117">Die folgende [!INCLUDE[tsql](../../../includes/tsql-md.md)] Abfrage verwendet alle Spalten und Parameter, die einen UDT in der **AdventureWorks** -Datenbank verwenden.</span><span class="sxs-lookup"><span data-stu-id="57172-117">The following [!INCLUDE[tsql](../../../includes/tsql-md.md)] query locates all of the columns and parameters that use a UDT in the **AdventureWorks** database.</span></span>  
  
```  
USE Adventureworks;  
SELECT o.name AS major_name, o.type_desc AS major_type_desc  
     , c.name AS minor_name, c.type_desc AS minor_type_desc  
     , at.assembly_class  
  FROM (  
        SELECT object_id, name, user_type_id, 'SQL_COLUMN' AS type_desc  
          FROM sys.columns  
     UNION ALL  
        SELECT object_id, name, user_type_id, 'SQL_PROCEDURE_PARAMETER'  
          FROM sys.parameters  
     ) AS c  
  JOIN sys.objects AS o  
    ON o.object_id = c.object_id  
  JOIN sys.assembly_types AS at  
    ON at.user_type_id = c.user_type_id;   
```  
  
## <a name="see-also"></a><span data-ttu-id="57172-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="57172-118">See Also</span></span>  
 <span data-ttu-id="57172-119">[Verwalten von CLR Integration](managing-clr-integration-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="57172-119">[Managing CLR Integration Assemblies](managing-clr-integration-assemblies.md) </span></span>  
 <span data-ttu-id="57172-120">[Ändern einer Assembly](altering-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="57172-120">[Altering an Assembly](altering-an-assembly.md) </span></span>  
 <span data-ttu-id="57172-121">[Erstellen einer Assembly](creating-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="57172-121">[Creating an Assembly](creating-an-assembly.md) </span></span>  
 <span data-ttu-id="57172-122">[Drop Aggregate &#40;Transact-SQL-&#41;](/sql/t-sql/statements/drop-aggregate-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="57172-122">[DROP AGGREGATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-aggregate-transact-sql) </span></span>  
 <span data-ttu-id="57172-123">[DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="57172-123">[DROP FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-function-transact-sql) </span></span>  
 <span data-ttu-id="57172-124">[DROP PROCEDURE &#40;Transact-SQL-&#41;](/sql/t-sql/statements/drop-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="57172-124">[DROP PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-procedure-transact-sql) </span></span>  
 <span data-ttu-id="57172-125">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="57172-125">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span></span>  
 [<span data-ttu-id="57172-126">DROP TYPE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="57172-126">DROP TYPE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-type-transact-sql)  
  
  
