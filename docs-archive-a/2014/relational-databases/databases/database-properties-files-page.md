---
title: Datenbankeigenschaften (Seite Dateien) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.files.f1
ms.assetid: 3c030e51-db82-4b43-b1e5-8547ddd3de87
author: stevestein
ms.author: sstein
ms.openlocfilehash: 955a17857ce0d847fb712473dddd581a072ab83d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695701"
---
# <a name="database-properties-files-page"></a><span data-ttu-id="aef15-102">Datenbankeigenschaften (Seite Dateien)</span><span class="sxs-lookup"><span data-stu-id="aef15-102">Database Properties (Files Page)</span></span>
  <span data-ttu-id="aef15-103">Auf dieser Seite können Sie eine neue Datenbank erstellen bzw. die Eigenschaften einer ausgewählten Datenbank anzeigen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="aef15-103">Use this page to create a new database, or view or modify properties for the selected database.</span></span> <span data-ttu-id="aef15-104">Dieses Thema bezieht sich auf die Option **Datenbankeigenschaften (Seite 'Dateien')** für vorhandene Datenbanken und auf die Option **Neue Datenbank (Seite 'Allgemein')** .</span><span class="sxs-lookup"><span data-stu-id="aef15-104">This topic applies to the **Database Properties (Files Page)** for existing databases, and to the **New Database (General Page)**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="aef15-105">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="aef15-105">UI element list</span></span>  
 <span data-ttu-id="aef15-106">**Datenbankname**</span><span class="sxs-lookup"><span data-stu-id="aef15-106">**Database name**</span></span>  
 <span data-ttu-id="aef15-107">Fügen Sie den Namen der Datenbank hinzu, oder zeigen Sie ihn an.</span><span class="sxs-lookup"><span data-stu-id="aef15-107">Add or display the name of the database.</span></span>  
  
 <span data-ttu-id="aef15-108">**Besitzer**</span><span class="sxs-lookup"><span data-stu-id="aef15-108">**Owner**</span></span>  
 <span data-ttu-id="aef15-109">Geben Sie den Besitzer der Datenbank durch Auswahl aus der Liste an.</span><span class="sxs-lookup"><span data-stu-id="aef15-109">Specify the owner of the database by selecting from the list.</span></span>  
  
 <span data-ttu-id="aef15-110">**Volltextindizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="aef15-110">**Use full-text indexing**</span></span>  
 <span data-ttu-id="aef15-111">Dieses Kontrollkästchen ist mit einem Häkchen versehen und abgeblendet, da die Volltextindizierung in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]immer aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="aef15-111">This check box is checked and disabled because full-text indexing is always enabled in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="aef15-112">Weitere Informationen finden Sie unter [Aktualisieren der Volltextsuche](../search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="aef15-112">For more information, see [Full-Text Search](../search/full-text-search.md).</span></span>  
  
 <span data-ttu-id="aef15-113">**Datenbankdateien**</span><span class="sxs-lookup"><span data-stu-id="aef15-113">**Database Files**</span></span>  
 <span data-ttu-id="aef15-114">Damit können Sie Datenbankdateien für die zugeordnete Datenbank hinzufügen, anzeigen, ändern oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="aef15-114">Add, view, modify, or remove database files for the associated database.</span></span> <span data-ttu-id="aef15-115">Datenbankdateien haben folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="aef15-115">Database files have the following properties:</span></span>  
  
 <span data-ttu-id="aef15-116">**Logischer Name**</span><span class="sxs-lookup"><span data-stu-id="aef15-116">**Logical Name**</span></span>  
 <span data-ttu-id="aef15-117">Geben Sie den Namen der Datei ein, oder ändern Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="aef15-117">Enter or modify the name of the file.</span></span>  
  
 <span data-ttu-id="aef15-118">**Dateityp**</span><span class="sxs-lookup"><span data-stu-id="aef15-118">**File Type**</span></span>  
 <span data-ttu-id="aef15-119">Wählen Sie den Dateityp aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="aef15-119">Select the file type from the list.</span></span> <span data-ttu-id="aef15-120">Der Dateityp kann **Daten**, **Protokoll**oder **Filestream-Daten**lauten.</span><span class="sxs-lookup"><span data-stu-id="aef15-120">The file type can be **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="aef15-121">Den Dateityp einer vorhandenen Datei können Sie nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="aef15-121">You cannot modify the file type of an existing file.</span></span>  
  
 <span data-ttu-id="aef15-122">Wählen Sie **Filestream-Daten** aus, wenn Sie einer speicheroptimierten Dateigruppe Dateien (Container) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="aef15-122">Select **Filestream Data** if you are adding files (containers) to a memory-optimized filegroup.</span></span>  
  
 <span data-ttu-id="aef15-123">Um Dateien (Container) einer Filestream-Datendateigruppe hinzuzufügen, muss FILESTREAM aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="aef15-123">To add files (containers) to a Filestream data filegroup, FILESTREAM must be enabled.</span></span> <span data-ttu-id="aef15-124">Sie können FILESTREAM aktivieren, indem Sie das Dialogfeld [Servereigenschaften (Seite „Erweitert“)](../../database-engine/configure-windows/server-properties-advanced-page.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="aef15-124">You can enable FILESTREAM by using the [Server Properties (Advanced Page)](../../database-engine/configure-windows/server-properties-advanced-page.md) dialog box.</span></span>  
  
 <span data-ttu-id="aef15-125">**Dateigruppe**</span><span class="sxs-lookup"><span data-stu-id="aef15-125">**Filegroup**</span></span>  
 <span data-ttu-id="aef15-126">Wählen Sie die Dateigruppe für die Datei aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="aef15-126">Select the filegroup for the file from the list.</span></span> <span data-ttu-id="aef15-127">Standardmäßig lautet die Dateigruppe PRIMARY.</span><span class="sxs-lookup"><span data-stu-id="aef15-127">By default, the filegroup is PRIMARY.</span></span> <span data-ttu-id="aef15-128">Sie können eine neue Dateigruppe erstellen, indem Sie auf **\<new filegroup>** klicken und Informationen zur Dateigruppe im Dialogfeld **Neue Dateigruppe** eingeben.</span><span class="sxs-lookup"><span data-stu-id="aef15-128">You can create a new filegroup by selecting **\<new filegroup>** and entering information about the filegroup in the **New Filegroup** dialog box.</span></span> <span data-ttu-id="aef15-129">Eine neue Dateigruppe kann auch auf der Seite **Dateigruppe** erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="aef15-129">A new filegroup can also be created on the **Filegroup** page.</span></span> <span data-ttu-id="aef15-130">Die Dateigruppe einer vorhandenen Datei können Sie nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="aef15-130">You cannot modify the filegroup of an existing file.</span></span>  
  
 <span data-ttu-id="aef15-131">Wenn Sie Dateien (Container) einer speicheroptimierten Dateigruppe hinzufügen, wird in das Feld **Dateigruppe** der Name der speicheroptimierten Dateigruppe der Datenbank eingefügt.</span><span class="sxs-lookup"><span data-stu-id="aef15-131">When adding files (containers) to a memory-optimized filegroup, the **Filegroup** field will be populated with the name of the database's memory-optimized filegroup.</span></span>  
  
 <span data-ttu-id="aef15-132">**Anfangsgröße**</span><span class="sxs-lookup"><span data-stu-id="aef15-132">**Initial Size**</span></span>  
 <span data-ttu-id="aef15-133">Geben Sie die Anfangsgröße für die Datei in Megabytes ein, oder ändern Sie sie.</span><span class="sxs-lookup"><span data-stu-id="aef15-133">Enter or modify the initial size for the file in megabytes.</span></span> <span data-ttu-id="aef15-134">Standardmäßig wird dieser Wert auf den Wert der **model** -Datenbank gesetzt.</span><span class="sxs-lookup"><span data-stu-id="aef15-134">By default, this is the value of the **model** database.</span></span>  
  
 <span data-ttu-id="aef15-135">Dieses Feld ist für FILESTREAM-Dateien nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="aef15-135">This field is not valid for FILESTREAM files.</span></span>  
  
 <span data-ttu-id="aef15-136">Bei Dateien in speicheroptimierten Dateigruppen kann dieses Feld nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="aef15-136">For files in memory-optimized filegroups, this field cannot be modified.</span></span>  
  
 <span data-ttu-id="aef15-137">**Automatische Vergrößerung**</span><span class="sxs-lookup"><span data-stu-id="aef15-137">**Autogrowth**</span></span>  
 <span data-ttu-id="aef15-138">Wählen Sie die Eigenschaften der automatischen Vergrößerung der Datei aus, oder zeigen Sie sie an.</span><span class="sxs-lookup"><span data-stu-id="aef15-138">Select or display the autogrowth properties for the file.</span></span> <span data-ttu-id="aef15-139">Diese Eigenschaften steuern, wie die Datei erweitert wird, wenn die maximale Dateigröße erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="aef15-139">These properties control how the file expands when its maximum file size is reached.</span></span> <span data-ttu-id="aef15-140">Um die Werte für die automatische Vergrößerung zu bearbeiten, klicken Sie für die gewünschte Datei auf die Bearbeitungsschaltfläche neben den Eigenschaften für die automatischen Vergrößerung, und ändern Sie die Werte im Dialogfeld **Automatische Vergrößerung ändern** .</span><span class="sxs-lookup"><span data-stu-id="aef15-140">To edit autogrowth values, click the edit button next to the autogrowth properties for the file that you want, and change the values in the **Change Autogrowth** dialog box.</span></span> <span data-ttu-id="aef15-141">Standardmäßig werden diese Werte auf die Werte der **model** -Datenbank gesetzt.</span><span class="sxs-lookup"><span data-stu-id="aef15-141">By default, these are the values of the **model** database.</span></span>  
  
 <span data-ttu-id="aef15-142">Dieses Feld ist für FILESTREAM-Dateien nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="aef15-142">This field is not valid for FILESTREAM files.</span></span>  
  
 <span data-ttu-id="aef15-143">Bei Dateien in speicheroptimierten Dateigruppen sollte dieses Feld **Unbegrenzt**lauten.</span><span class="sxs-lookup"><span data-stu-id="aef15-143">For files in memory-optimized filegroups, this field should be **Unlimited**.</span></span>  
  
 <span data-ttu-id="aef15-144">**Pfad**</span><span class="sxs-lookup"><span data-stu-id="aef15-144">**Path**</span></span>  
 <span data-ttu-id="aef15-145">Zeigt den Pfad der ausgewählten Datei an.</span><span class="sxs-lookup"><span data-stu-id="aef15-145">Displays the path of the selected file.</span></span> <span data-ttu-id="aef15-146">Um einen Pfad für eine neue Datei anzugeben, klicken Sie auf die Bearbeitungsschaltfläche neben dem Pfad für die Datei, und navigieren Sie dann zum Zielordner.</span><span class="sxs-lookup"><span data-stu-id="aef15-146">To specify a path for a new file, click the edit button next to the path for the file, and navigate to the destination folder.</span></span> <span data-ttu-id="aef15-147">Den Pfad einer vorhandenen Datei können Sie nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="aef15-147">You cannot modify the path of an existing file.</span></span>  
  
 <span data-ttu-id="aef15-148">Für FILESTREAM-Dateien ist der Pfad ein Ordner.</span><span class="sxs-lookup"><span data-stu-id="aef15-148">For FILESTREAM files, the path is a folder.</span></span> <span data-ttu-id="aef15-149">Das [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] erstellt die zugrunde liegenden Dateien in diesem Ordner.</span><span class="sxs-lookup"><span data-stu-id="aef15-149">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] will create the underlying files in this folder.</span></span>  
  
 <span data-ttu-id="aef15-150">**Dateiname**</span><span class="sxs-lookup"><span data-stu-id="aef15-150">**File Name**</span></span>  
 <span data-ttu-id="aef15-151">Zeigt den Namen der Datei an.</span><span class="sxs-lookup"><span data-stu-id="aef15-151">Displays the name of the file.</span></span>  
  
 <span data-ttu-id="aef15-152">Dieses Feld ist für FILESTREAM-Dateien, einschließlich Dateien in speicheroptimierten Dateigruppen, nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="aef15-152">This field is not valid for FILESTREAM files, including files in memory-optimized filegroups.</span></span>  
  
 <span data-ttu-id="aef15-153">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="aef15-153">**Add**</span></span>  
 <span data-ttu-id="aef15-154">Fügt der Datenbank eine neue Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="aef15-154">Add a new file to the database.</span></span>  
  
 <span data-ttu-id="aef15-155">**Remove**</span><span class="sxs-lookup"><span data-stu-id="aef15-155">**Remove**</span></span>  
 <span data-ttu-id="aef15-156">Löscht die ausgewählte Datei aus der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="aef15-156">Delete the selected file from the database.</span></span> <span data-ttu-id="aef15-157">Eine Datei kann nur entfernt werden, wenn sie leer ist.</span><span class="sxs-lookup"><span data-stu-id="aef15-157">A file cannot be removed unless it is empty.</span></span> <span data-ttu-id="aef15-158">Die primäre Datendatei und die Protokolldatei können nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="aef15-158">The primary data file and log file cannot be removed.</span></span>  
  
 <span data-ttu-id="aef15-159">Weitere Informationen zu Dateien finden Sie unter [Database Files and Filegroups](database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="aef15-159">For information about files, see [Database Files and Filegroups](database-files-and-filegroups.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aef15-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aef15-160">See Also</span></span>  
 <span data-ttu-id="aef15-161">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aef15-161">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="aef15-162">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="aef15-162">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
