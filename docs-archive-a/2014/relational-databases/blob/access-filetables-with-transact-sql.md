---
title: Zugreifen auf FileTables mit Transact-SQL | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], accessing files with T-SQL
ms.assetid: 3c4a5ffb-c521-4696-99cb-2b03cffc9c02
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2c47751ef34747e1b3742accf5040846ecde074f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721501"
---
# <a name="access-filetables-with-transact-sql"></a><span data-ttu-id="78289-102">Zugreifen auf FileTables mit Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="78289-102">Access FileTables with Transact-SQL</span></span>
  <span data-ttu-id="78289-103">Beschreibt, wie die Befehle der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Datenbearbeitungssprache (Data Manipulation Language, DML) mit FileTables funktionieren.</span><span class="sxs-lookup"><span data-stu-id="78289-103">Describes how [!INCLUDE[tsql](../../includes/tsql-md.md)] data manipulation language (DML) commands work with FileTables.</span></span>  
  
##  <a name="insert-operations-on-filetables"></a><a name="BasicsInsert"></a> <span data-ttu-id="78289-104">INSERT-Vorgänge in FileTables</span><span class="sxs-lookup"><span data-stu-id="78289-104">INSERT Operations on FileTables</span></span>  
 <span data-ttu-id="78289-105">Die folgenden Überlegungen gelten für **INSERT** -Vorgänge in FileTables:</span><span class="sxs-lookup"><span data-stu-id="78289-105">The following considerations apply to **INSERT** Operations on FileTables:</span></span>  
  
-   <span data-ttu-id="78289-106">Alle Dateiattributspalten besitzen NOT NULL-Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="78289-106">All the file attribute columns have NOT NULL constraints.</span></span> <span data-ttu-id="78289-107">Wenn Werte nicht explizit festgelegt werden, werden entsprechende Standardwerte angegeben.</span><span class="sxs-lookup"><span data-stu-id="78289-107">If values are not explicitly set, then appropriate default values are supplied.</span></span>  
  
-   <span data-ttu-id="78289-108">Systemdefinierte Einschränkungen werden erzwungen, wenn die INSERT-Anweisung **name**, **path_locator**, **parent_path_locator**oder Dateiattribute festlegt.</span><span class="sxs-lookup"><span data-stu-id="78289-108">System-defined constraints are enforced if the INSERT statement sets the **name**, **path_locator**, **parent_path_locator**, or file attributes.</span></span>  
  
-   <span data-ttu-id="78289-109">Die Anwendung kann **path_locator** für eine Datei oder ein Verzeichnis abrufen, indem in der Funktion [GetPathLocator &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getpathlocator-transact-sql) der Dateisystempfad angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="78289-109">The application can obtain the **path_locator** for a file or directory by providing the file system path to the [GetPathLocator &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getpathlocator-transact-sql) function.</span></span>  
  
##  <a name="update-operations-on-filetables"></a><a name="BasicsUpdate"></a> <span data-ttu-id="78289-110">UPDATE-Vorgänge in FileTables</span><span class="sxs-lookup"><span data-stu-id="78289-110">UPDATE Operations on FileTables</span></span>  
 <span data-ttu-id="78289-111">Die folgenden Überlegungen gelten für **UPDATE** -Vorgänge in FileTables:</span><span class="sxs-lookup"><span data-stu-id="78289-111">The following considerations apply to **UPDATE** operations on FileTables:</span></span>  
  
-   <span data-ttu-id="78289-112">Aktualisierungen an benutzerdefinierten Daten sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="78289-112">Updates to any user-defined data are allowed.</span></span>  
  
-   <span data-ttu-id="78289-113">Systemdefinierte Einschränkungen werden erzwungen, wenn die INSERT-Anweisung **name**, **path_locator**, **parent_path_locator**oder Dateiattribute festlegt.</span><span class="sxs-lookup"><span data-stu-id="78289-113">System-defined constraints are enforced if the INSERT statement sets the **name**, **path_locator**, **parent_path_locator**, or file attributes.</span></span>  
  
-   <span data-ttu-id="78289-114">Aktualisierungen können an den FILESTREAM-Daten in der Spalte **file_stream** ohne Auswirkungen auf die anderen Spalten, einschließlich Timestamps, vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="78289-114">Updates can be made to the FILESTREAM data in the **file_stream** column without affecting any of the other columns, including the timestamps.</span></span>  
  
##  <a name="delete-operations-on-filetables"></a><a name="BasicsDelete"></a> <span data-ttu-id="78289-115">DELETE-Vorgänge in FileTables</span><span class="sxs-lookup"><span data-stu-id="78289-115">DELETE Operations on FileTables</span></span>  
 <span data-ttu-id="78289-116">Die folgenden Überlegungen gelten für **DELETE** -Vorgänge in FileTables:</span><span class="sxs-lookup"><span data-stu-id="78289-116">The following considerations apply to **DELETE** operations on FileTables:</span></span>  
  
-   <span data-ttu-id="78289-117">Durch Löschen einer Zeile wird auch die entsprechende Datei oder das entsprechende Verzeichnis aus dem Dateisystem entfernt.</span><span class="sxs-lookup"><span data-stu-id="78289-117">Deleting a row also removes the corresponding file or directory from the file system.</span></span>  
  
-   <span data-ttu-id="78289-118">Das Löschen einer Zeile schlägt fehl, wenn die Zeile einem Verzeichnis entspricht, das andere Dateien oder Verzeichnisse enthält.</span><span class="sxs-lookup"><span data-stu-id="78289-118">Deleting a row fails if the row corresponds to a directory that contains other files or directories.</span></span>  
  
##  <a name="constraints-that-are-enforced-for-dml-operations-on-filetables"></a><a name="BasicsConstraints"></a> <span data-ttu-id="78289-119">Einschränkungen, die für DML-Vorgänge in FileTables erzwungen werden</span><span class="sxs-lookup"><span data-stu-id="78289-119">Constraints That Are Enforced for DML Operations on FileTables</span></span>  
 <span data-ttu-id="78289-120">Systemdefinierte Einschränkungen stellen sicher, dass DML-Aktionen nicht die Integrität der Dateinamespacehierarchie beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="78289-120">System-defined constraints ensure that DML actions do not compromise the integrity of the file namespace hierarchy.</span></span> <span data-ttu-id="78289-121">Zu den Einschränkungen, die erzwungen werden, gehören Folgende:</span><span class="sxs-lookup"><span data-stu-id="78289-121">The constraints that are enforced include the following:</span></span>  
  
-   <span data-ttu-id="78289-122">Wenn Sie **name** der Datei oder des Verzeichnisses festgelegt oder geändert haben:</span><span class="sxs-lookup"><span data-stu-id="78289-122">When you set or change the **name** of the file or directory:</span></span>  
  
    -   <span data-ttu-id="78289-123">Die Windows-Benennungskonventionen für Dateien und Verzeichnisse werden erzwungen.</span><span class="sxs-lookup"><span data-stu-id="78289-123">Windows file and directory naming conventions are enforced.</span></span>  
  
    -   <span data-ttu-id="78289-124">Die Eindeutigkeit des Namens im übergeordneten Verzeichnis wird erzwungen.</span><span class="sxs-lookup"><span data-stu-id="78289-124">The uniqueness of the name in the parent directory is enforced.</span></span>  
  
-   <span data-ttu-id="78289-125">Wenn Sie den Speicherort einer Datei oder eines Verzeichnisses durch Festlegen oder Ändern von **path_locator** oder **parent_path_locator**festgelegt oder geändert haben:</span><span class="sxs-lookup"><span data-stu-id="78289-125">When you set or change the location of a file or directory by setting or changing the **path_locator** or **parent_path_locator**:</span></span>  
  
    -   <span data-ttu-id="78289-126">Eindeutigkeit wird erzwungen.</span><span class="sxs-lookup"><span data-stu-id="78289-126">Uniqueness is enforced.</span></span>  
  
    -   <span data-ttu-id="78289-127">Die Konsistenz der hierarchischen Struktur von Verzeichnissen und Dateien wird erzwungen, einschließlich der Konsistenz der Werte **path_locator** und **parent_path_locator** .</span><span class="sxs-lookup"><span data-stu-id="78289-127">The consistency of the hierarchical tree of directories and files is enforced, including the consistency of **path_locator** and **parent_path_locator** values.</span></span>  
  
-   <span data-ttu-id="78289-128">Der Wert für **is_directory** kann nicht auf TRUE festgelegt werden, wenn die **file_stream** -Spalte nicht NULL ist.</span><span class="sxs-lookup"><span data-stu-id="78289-128">The value of **is_directory** cannot be set to true when the **file_stream** column is not null.</span></span> <span data-ttu-id="78289-129">Daten in der **file_stream** -Spalte geben an, dass die Zeile eine Datei und nicht ein Verzeichnis darstellt.</span><span class="sxs-lookup"><span data-stu-id="78289-129">Data in the **file_stream** column indicates that the row represents a file and not a directory.</span></span>  
  
-   <span data-ttu-id="78289-130">Spalten mit Dateiattributen können nicht NULL sein.</span><span class="sxs-lookup"><span data-stu-id="78289-130">File attribute columns cannot be null.</span></span> <span data-ttu-id="78289-131">NOT NULL-Einschränkungen werden mit Standardwerten erzwungen.</span><span class="sxs-lookup"><span data-stu-id="78289-131">NOT NULL constraints are enforced with default values.</span></span>  
  
-   <span data-ttu-id="78289-132">Der Wert **last_access_time** kann nicht vor **last_write_time** und **creation_time**liegen.</span><span class="sxs-lookup"><span data-stu-id="78289-132">The value of **last_access_time** cannot be earlier than **last_write_time** and **creation_time**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78289-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="78289-133">See Also</span></span>  
 <span data-ttu-id="78289-134">[Laden von Dateien in FileTables](load-files-into-filetables.md) </span><span class="sxs-lookup"><span data-stu-id="78289-134">[Load Files into FileTables](load-files-into-filetables.md) </span></span>  
 <span data-ttu-id="78289-135">[Work with Directories and Paths in FileTables](work-with-directories-and-paths-in-filetables.md) </span><span class="sxs-lookup"><span data-stu-id="78289-135">[Work with Directories and Paths in FileTables](work-with-directories-and-paths-in-filetables.md) </span></span>  
 <span data-ttu-id="78289-136">[Zugreifen auf FileTables mit Datei-E/A-APIs](access-filetables-with-file-input-output-apis.md) </span><span class="sxs-lookup"><span data-stu-id="78289-136">[Access FileTables with File Input-Output APIs](access-filetables-with-file-input-output-apis.md) </span></span>  
 [<span data-ttu-id="78289-137">FileTable-DDL, Funktionen, gespeicherte Prozeduren und Sichten</span><span class="sxs-lookup"><span data-stu-id="78289-137">FileTable DDL, Functions, Stored Procedures, and Views</span></span>](../views/views.md)  
  
  
