---
title: Ändern einer Assembly | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- assemblies [CLR integration], modifying
- permissions [CLR integration]
- altering assemblies
- ALTER ASSEMBLY statement
ms.assetid: 9e765fbd-f339-473c-8537-22f478e79696
author: rothja
ms.author: jroth
ms.openlocfilehash: c22ca979675d3b7f263e3bc6de0c41c134a1abcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720047"
---
# <a name="altering-an-assembly"></a><span data-ttu-id="f0e78-102">Ändern einer Assembly</span><span class="sxs-lookup"><span data-stu-id="f0e78-102">Altering an Assembly</span></span>
  <span data-ttu-id="f0e78-103">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] registrierte Assemblys können von einer aktuelleren Version aus mithilfe der ALTER ASSEMBLY-Anweisung aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="f0e78-103">Assemblies that have been registered in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] can be updated from a more recent version using the ALTER ASSEMBLY statement.</span></span> <span data-ttu-id="f0e78-104">Zum Aktualisieren einer Assembly verwenden Sie die ALTER ASSEMBLY-Anweisung mit der folgenden Syntax:</span><span class="sxs-lookup"><span data-stu-id="f0e78-104">To update an assembly, use the ALTER ASSEMBLY statement with the following syntax:</span></span>  
  
```  
ALTER ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll'  
```  
  
 <span data-ttu-id="f0e78-105">Mit ALTER ASSEMBLY werden zurzeit ausgeführte Prozesse, die die Assembly verwenden, nicht unterbrochen. Die Prozesse werden mit der unveränderten Assembly weiterhin ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f0e78-105">ALTER ASSEMBLY does not disrupt currently running processes that are using the assembly; the processes continue executing with the unaltered assembly.</span></span> <span data-ttu-id="f0e78-106">Mit ALTER ASSEMBLY können die Signaturen gängiger CLR-Funktionen (Common Language Runtime), Aggregatfunktionen, gespeicherter Prozeduren und Trigger nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f0e78-106">ALTER ASSEMBLY cannot be used to change the signatures of common language runtime (CLR) functions, aggregate functions, stored procedures, and triggers.</span></span> <span data-ttu-id="f0e78-107">Neue öffentliche Methoden können der Assembly hinzugefügt werden. Private Methoden können beliebig bearbeitet werden, während öffentliche Methoden nur so lange bearbeitet werden können, wie die Signaturen oder Attribute unverändert bleiben.</span><span class="sxs-lookup"><span data-stu-id="f0e78-107">New public methods can be added to the assembly, private methods can be modified in any way, and public methods can be modified as long as signatures or attributes are not changed.</span></span> <span data-ttu-id="f0e78-108">Felder, die in einem systemeigenen serialisierten benutzerdefinierten Typ enthalten sind, einschließlich Datenelemente oder Basisklassen, können nicht mithilfe von ALTER ASSEMBLY geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f0e78-108">Fields that are contained within a native-serialized user-defined type, including data members or base classes, cannot be changed by using ALTER ASSEMBLY.</span></span> <span data-ttu-id="f0e78-109">Alle anderen Änderungen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f0e78-109">All other changes are unsupported.</span></span> <span data-ttu-id="f0e78-110">Weitere Informationen finden Sie unter [Alter Assembly &#40;Transact-SQL-&#41;](/sql/t-sql/statements/alter-assembly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f0e78-110">For more information, see [ALTER ASSEMBLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-assembly-transact-sql).</span></span>  
  
## <a name="changing-the-permission-set-of-an-assembly"></a><span data-ttu-id="f0e78-111">Ändern des Berechtigungssatzes einer Assembly</span><span class="sxs-lookup"><span data-stu-id="f0e78-111">Changing the Permission Set of an Assembly</span></span>  
 <span data-ttu-id="f0e78-112">Der Berechtigungssatz einer Assembly kann auch mit der ALTER ASSEMBLY-Anweisung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f0e78-112">The permission set of an assembly can also be changed using the ALTER ASSEMBLY statement.</span></span> <span data-ttu-id="f0e78-113">Die folgende Anweisung ändert den Berechtigungssatz der SQLCLRTest-Assembly in `EXTERNAL_ACCESS`.</span><span class="sxs-lookup"><span data-stu-id="f0e78-113">The following statement changes the permission set of the SQLCLRTest assembly to `EXTERNAL_ACCESS`.</span></span>  
  
```  
ALTER ASSEMBLY SQLCLRTest  
WITH PERMISSION_SET = EXTERNAL_ACCESS   
```  
  
 <span data-ttu-id="f0e78-114">Wenn der Berechtigungssatz einer Assembly von `SAFE` in `EXTERNAL_ACCESS` oder `UNSAFE` geändert wird, muss zunächst ein asymmetrischer Schlüssel mit entsprechender Anmeldung mit der `EXTERNAL ACCESS ASSEMBLY`- oder der `UNSAFE ASSEMBLY`-Berechtigung für die Assembly erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f0e78-114">If the permission set of an assembly is being changed from `SAFE` to `EXTERNAL_ACCESS` or `UNSAFE`, an asymmetric key and corresponding login with `EXTERNAL ACCESS ASSEMBLY` permission or `UNSAFE ASSEMBLY` permission for the assembly must first be created.</span></span> <span data-ttu-id="f0e78-115">Weitere Informationen finden Sie unter [Creating an Assembly](creating-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="f0e78-115">For more information, see [Creating an Assembly](creating-an-assembly.md).</span></span>  
  
## <a name="adding-the-source-code-of-an-assembly"></a><span data-ttu-id="f0e78-116">Hinzufügen des Quellcodes einer Assembly</span><span class="sxs-lookup"><span data-stu-id="f0e78-116">Adding the Source Code of an Assembly</span></span>  
 <span data-ttu-id="f0e78-117">Die ADD FILE-Klausel in der ALTER ASSEMBLY-Syntax ist nicht in CREATE ASSEMBLY vorhanden.</span><span class="sxs-lookup"><span data-stu-id="f0e78-117">The ADD FILE clause in the ALTER ASSEMBLY syntax is not present in CREATE ASSEMBLY.</span></span> <span data-ttu-id="f0e78-118">Sie können sie verwenden, um Quellcode oder beliebige andere Dateien hinzuzufügen, die einer Assembly zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f0e78-118">You can use it to add source code or any other files associated with an assembly.</span></span> <span data-ttu-id="f0e78-119">Die Dateien werden von ihren ursprünglichen Speicherorten kopiert und in Systemtabellen in der Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f0e78-119">The files are copied from their original locations and stored in system tables in the database.</span></span> <span data-ttu-id="f0e78-120">Dadurch wird sichergestellt, dass stets der Quellcode oder andere Dateien verfügbar sind, wenn Sie die aktuelle Version des UDT neu erstellen oder dokumentieren müssen.</span><span class="sxs-lookup"><span data-stu-id="f0e78-120">This ensures that you always have source code or other files on hand should you ever need to re-create or document the current version of the UDT.</span></span>  
  
 <span data-ttu-id="f0e78-121">Die folgende Anweisung fügt der Point.cs-Klasse Quellcode für den Point-UDT hinzu.</span><span class="sxs-lookup"><span data-stu-id="f0e78-121">The following statement adds the Point.cs class source code for the Point UDT.</span></span> <span data-ttu-id="f0e78-122">Dadurch wird der in der Datei Point.cs enthaltene Text kopiert und unter dem Namen "PointSource" in der Datenbank gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f0e78-122">This copies the text contained in the Point.cs file and stores it in the database under the name "PointSource".</span></span>  
  
 `ALTER ASSEMBLY Point`  
  
 `ADD FILE FROM 'C:\Projects\Point\Point.cs' AS PointSource`  
  
## <a name="see-also"></a><span data-ttu-id="f0e78-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0e78-123">See Also</span></span>  
 <span data-ttu-id="f0e78-124">[Verwalten von CLR Integration](managing-clr-integration-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="f0e78-124">[Managing CLR Integration Assemblies](managing-clr-integration-assemblies.md) </span></span>  
 <span data-ttu-id="f0e78-125">[Erstellen einer Assembly](creating-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="f0e78-125">[Creating an Assembly](creating-an-assembly.md) </span></span>  
 <span data-ttu-id="f0e78-126">[Löschen einer Assembly](dropping-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="f0e78-126">[Dropping an Assembly](dropping-an-assembly.md) </span></span>  
 [<span data-ttu-id="f0e78-127">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f0e78-127">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-assembly-transact-sql)  
  
  
