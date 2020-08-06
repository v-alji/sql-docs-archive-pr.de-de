---
title: Ausführen des SQL Server-Import/Export-Assistenten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Import and Export Wizard
- starting SQL Server Import and Export Wizard
- Import and Export Wizard
- starting Import and Export Wizard
ms.assetid: 5fc4f6d1-1f6f-444e-9aeb-827f85e1c405
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 008c541b1f1a295057b0ee7cc384982627b9689a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619916"
---
# <a name="run-the-sql-server-import-and-export-wizard"></a><span data-ttu-id="fa788-102">Ausführen des SQL Server-Import/Export-Assistenten</span><span class="sxs-lookup"><span data-stu-id="fa788-102">Run the SQL Server Import and Export Wizard</span></span>
  <span data-ttu-id="fa788-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Import/Export-Assistent stellt die einfachste Methode zum Kopieren von Daten zwischen Datenquellen und zum Erstellen von Basispaketen bereit.</span><span class="sxs-lookup"><span data-stu-id="fa788-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard provides the simplest method of copying data between data sources and of constructing basic packages.</span></span> <span data-ttu-id="fa788-104">Weitere Informationen zum Assistenten finden Sie unter [SQL Server-Import/Export-Assistenten](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="fa788-104">For more information about the wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="fa788-105">Ein Video, das veranschaulicht, wie der SQL Server-Import/Export-Assistent zum Erstellen eines Pakets verwendet wird, das Daten aus einer SQL Server Datenbank in ein Microsoft Excel-Arbeitsblatt exportiert, finden Sie unter [Exportieren von SQL Server Daten nach Excel (SQL Server Video)](https://go.microsoft.com/fwlink/?LinkId=131024).</span><span class="sxs-lookup"><span data-stu-id="fa788-105">For a video that demonstrates how to use the SQL Server Import and Export Wizard to create a package that exports data from a SQL Server database to a Microsoft Excel spreadsheet, see [Exporting SQL Server Data to Excel (SQL Server Video)](https://go.microsoft.com/fwlink/?LinkId=131024).</span></span>  
  
### <a name="to-start-the-sql-server-import-and-export-wizard"></a><span data-ttu-id="fa788-106">So starten Sie den SQL Server-Import/Export-Assistenten</span><span class="sxs-lookup"><span data-stu-id="fa788-106">To start the SQL Server Import and Export Wizard</span></span>  
  
-   <span data-ttu-id="fa788-107">Zeigen Sie im Menü **Start** auf **Alle Programme**, zeigen Sie auf**Microsoft SQL Server** , und klicken Sie dann auf **Daten importieren und exportieren**.</span><span class="sxs-lookup"><span data-stu-id="fa788-107">On the **Start** menu, point to **All Programs**, point to**Microsoft SQL Server** , and then click **Import and Export Data**.</span></span>  
  
     <span data-ttu-id="fa788-108">Oder</span><span class="sxs-lookup"><span data-stu-id="fa788-108">-or-</span></span>  
  
     <span data-ttu-id="fa788-109">[!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]Klicken Sie in mit der rechten Maustaste auf den Ordner **SSIS-Pakete** , und klicken Sie dann auf **ssisimport und Export-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="fa788-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], right-click the **SSIS Packages** folder, and then click **SSISImport and Export Wizard**.</span></span>  
  
     <span data-ttu-id="fa788-110">Oder</span><span class="sxs-lookup"><span data-stu-id="fa788-110">-or-</span></span>  
  
     <span data-ttu-id="fa788-111">[!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]Klicken Sie in im Menü **Projekt** auf **ssisimport und Export-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="fa788-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], on the **Project** menu, click **SSISImport and Export Wizard**.</span></span>  
  
     <span data-ttu-id="fa788-112">Oder</span><span class="sxs-lookup"><span data-stu-id="fa788-112">-or-</span></span>  
  
     <span data-ttu-id="fa788-113">Stellen [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Sie in eine Verbindung mit dem [!INCLUDE[ssDE](../../includes/ssde-md.md)] Servertyp her, erweitern Sie Datenbanken, klicken Sie mit der rechten Maustaste auf eine Datenbank, **Export data**zeigen Sie auf **Tasks**, und klicken Sie dann auf **Daten importieren** bzw</span><span class="sxs-lookup"><span data-stu-id="fa788-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] server type, expand Databases, right-click a database, point to **Tasks**, and then click **Import Data** or **Export data**.</span></span>  
  
     <span data-ttu-id="fa788-114">Oder</span><span class="sxs-lookup"><span data-stu-id="fa788-114">-or-</span></span>  
  
     <span data-ttu-id="fa788-115">Führen Sie in einem Eingabeaufforderungsfenster DTSWizard.exe aus. Diese Datei ist im Verzeichnis C:\Programme\Microsoft SQL Server\100\DTS\Binn gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fa788-115">In a command prompt window, run DTSWizard.exe, located in C:\Program Files\Microsoft SQL Server\100\DTS\Binn.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fa788-116">Auf einem 64-Bit-Computer installiert [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] die 64-Bit-Version des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Import/Export-Assistenten (DTSWizard.exe).</span><span class="sxs-lookup"><span data-stu-id="fa788-116">On a 64-bit computer, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installs the 64-bit version of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard (DTSWizard.exe).</span></span> <span data-ttu-id="fa788-117">Jedoch verfügen einige Datenquellen, wie Access oder Excel, nur über einen 32-Bit-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="fa788-117">However, some data sources, such as Access or Excel, only have a 32-bit provider available.</span></span> <span data-ttu-id="fa788-118">Damit Sie diese Datenquellen verwenden können, müssen Sie möglicherweise die 32-Bit-Version des Assistenten installieren und ausführen.</span><span class="sxs-lookup"><span data-stu-id="fa788-118">To work with these data sources, you might have to install and run the 32-bit version of the wizard.</span></span> <span data-ttu-id="fa788-119">Wählen Sie zum Installieren der 32-Bit-Version des Assistenten während des Setups entweder Clienttools oder [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa788-119">To install the 32-bit version of the wizard, select either Client Tools or [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] during setup.</span></span>  
  
### <a name="to-import-or-export-data-by-using-the-sql-server-import-and-export-wizard"></a><span data-ttu-id="fa788-120">So importieren oder exportieren Sie Daten mit dem SQL Server-Import/Export-Assistenten</span><span class="sxs-lookup"><span data-stu-id="fa788-120">To import or export data by using the SQL Server Import and Export Wizard</span></span>  
  
1.  <span data-ttu-id="fa788-121">Starten Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Import/Export-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="fa788-121">Start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard.</span></span>  
  
2.  <span data-ttu-id="fa788-122">Wählen Sie auf den entsprechenden Assistentenseiten eine Datenquelle und ein Datenziel aus.</span><span class="sxs-lookup"><span data-stu-id="fa788-122">On the corresponding wizard pages, select a data source and a data destination.</span></span>  
  
     <span data-ttu-id="fa788-123">Zu den verfügbaren Datenquellen zählen [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Datenanbieter, OLE DB-Anbieter, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-Anbieter, [!INCLUDE[vstecado](../../includes/vstecado-md.md)]-Anbieter, Microsoft Office Excel, Microsoft Office Access und die Flatfilequelle.</span><span class="sxs-lookup"><span data-stu-id="fa788-123">The available data sources include [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data providers, OLE DB providers, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client providers, [!INCLUDE[vstecado](../../includes/vstecado-md.md)] providers, Microsoft Office Excel, Microsoft Office Access, and the Flat File source.</span></span> <span data-ttu-id="fa788-124">In Abhängigkeit von der Quelle legen Sie Optionen fest, wie z. B. den Authentifizierungsmodus, den Servernamen, den Datenbanknamen und das Dateiformat.</span><span class="sxs-lookup"><span data-stu-id="fa788-124">Depending on the source, you set options such as the authentication mode, server name, database name, and file format.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fa788-125">Der [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB-Anbieter für Oracle unterstützt die folgenden Oracle-Datentypen nicht: BLOB, CLOB, NCLOB, BFILE und UROWID.</span><span class="sxs-lookup"><span data-stu-id="fa788-125">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for Oracle does not support the Oracle BLOB, CLOB, NCLOB, BFILE, and UROWID data types.</span></span> <span data-ttu-id="fa788-126">Deshalb kann die OLE DB-Quelle keine Daten aus Tabellen herausziehen, die Spalten mit diesen Datentypen enthalten.</span><span class="sxs-lookup"><span data-stu-id="fa788-126">Therefore, the OLE DB source cannot extract data from tables that contain columns with these data types.</span></span>  
  
     <span data-ttu-id="fa788-127">Zu den verfügbaren Datenzielen zählen [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Datenanbieter, OLE DB-Anbieter, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, Excel, Access und das Flatfileziel.</span><span class="sxs-lookup"><span data-stu-id="fa788-127">The available data destinations include [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data providers, OLE DB providers, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, Excel, Access, and the Flat File destination.</span></span>  
  
3.  <span data-ttu-id="fa788-128">Legen Sie die Optionen für den Zieltyp fest, den Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="fa788-128">Set the options for the type of destination that you selected.</span></span>  
  
     <span data-ttu-id="fa788-129">Wenn es sich bei dem Ziel um eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datenbank handelt, können Sie Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="fa788-129">If the destination is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database you can specify the following:</span></span>  
  
    -   <span data-ttu-id="fa788-130">Geben Sie an, ob eine neue Datenbank erstellt werden soll, und legen Sie die Datenbankeigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="fa788-130">Indicate whether to create a new database and set the database properties.</span></span> <span data-ttu-id="fa788-131">Die folgenden Eigenschaften können nicht konfiguriert werden, und der Assistent verwendet die angegebenen Standardwerte:</span><span class="sxs-lookup"><span data-stu-id="fa788-131">The following properties cannot be configured and the wizard uses the specified default values:</span></span>  
  
        |<span data-ttu-id="fa788-132">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="fa788-132">Property</span></span>|<span data-ttu-id="fa788-133">Wert</span><span class="sxs-lookup"><span data-stu-id="fa788-133">Value</span></span>|  
        |--------------|-----------|  
        |<span data-ttu-id="fa788-134">Sortierung</span><span class="sxs-lookup"><span data-stu-id="fa788-134">Collation</span></span>|<span data-ttu-id="fa788-135">Latin1_General_CS_AS_KS_WS</span><span class="sxs-lookup"><span data-stu-id="fa788-135">Latin1_General_CS_AS_KS_WS</span></span>|  
        |<span data-ttu-id="fa788-136">Wiederherstellungsmodell</span><span class="sxs-lookup"><span data-stu-id="fa788-136">Recovery model</span></span>|<span data-ttu-id="fa788-137">Vollständig</span><span class="sxs-lookup"><span data-stu-id="fa788-137">Full</span></span>|  
        |<span data-ttu-id="fa788-138">Volltextindizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fa788-138">Use full-text indexing</span></span>|<span data-ttu-id="fa788-139">True</span><span class="sxs-lookup"><span data-stu-id="fa788-139">True</span></span>|  
  
    -   <span data-ttu-id="fa788-140">Wählen Sie aus, ob Daten aus Tabellen oder Sichten kopiert werden sollen oder ob Abfrageergebnisse kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fa788-140">Select whether to copy data from tables or views, or to copy query results.</span></span>  
  
         <span data-ttu-id="fa788-141">Wenn Sie die Quelldaten abfragen und die Ergebnisse kopieren möchten, können Sie eine Transact-SQL-Abfrage erstellen.</span><span class="sxs-lookup"><span data-stu-id="fa788-141">If you want to query the source data and copy the results, you can construct a Transact-SQL query.</span></span> <span data-ttu-id="fa788-142">Sie können die Transact-SQL-Abfrage manuell eingeben oder eine als Datei gespeicherte Abfrage verwenden.</span><span class="sxs-lookup"><span data-stu-id="fa788-142">You can enter the Transact-SQL query manually or use a query saved to a file.</span></span> <span data-ttu-id="fa788-143">Der Assistent enthält eine Suchfunktion, um nach der Datei zu suchen. Der Assistent öffnet die Datei automatisch und fügt deren Inhalt auf der Assistentenseite ein, wenn Sie die Datei auswählen.</span><span class="sxs-lookup"><span data-stu-id="fa788-143">The wizard includes a browse feature for locating the file, and the wizard automatically opens the file and pastes its content into the wizard page when you select the file.</span></span>  
  
         <span data-ttu-id="fa788-144">Wenn es sich bei der Quelle um einen [!INCLUDE[vstecado](../../includes/vstecado-md.md)]-Anbieter handelt, können Sie auch die Option zum Kopieren von Abfrageergebnissen verwenden, wobei Sie die DBCommand-Zeichenfolge als Abfrage bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="fa788-144">If the source is an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] provider you can also use the option to copy query results, providing the DBCommand string as the query.</span></span>  
  
         <span data-ttu-id="fa788-145">Wenn als Quelldaten eine Sicht vorhanden ist, konvertiert der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Import/Export-Assistent die Sicht im Ziel automatisch in eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="fa788-145">If the source data is a view, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard automatically converts the view to a table in the destination.</span></span>  
  
    -   <span data-ttu-id="fa788-146">Geben Sie an, ob die Zieltabelle gelöscht und anschließend neu erstellt wird und ob IDENTITY_INSERT aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="fa788-146">Indicate whether the destination table is dropped and then re-created, and whether to enable identity inserts.</span></span>  
  
    -   <span data-ttu-id="fa788-147">Geben Sie an, ob Zeilen in einer vorhandenen Zieltabelle gelöscht oder angefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fa788-147">Indicate whether to delete rows or append rows in an existing destination table.</span></span> <span data-ttu-id="fa788-148">Falls die Tabelle nicht vorhanden ist, wird sie automatisch vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Import/Export-Assistenten erstellt.</span><span class="sxs-lookup"><span data-stu-id="fa788-148">If the table does not exist, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard automatically creates it.</span></span>  
  
     <span data-ttu-id="fa788-149">Wenn es sich bei dem Ziel um ein Flatfileziel handelt, können Sie Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="fa788-149">If the destination is a Flat File destination you can specify the following:</span></span>  
  
    -   <span data-ttu-id="fa788-150">Geben Sie das Zeilentrennzeichen in der Zieldatei an.</span><span class="sxs-lookup"><span data-stu-id="fa788-150">Specify the row delimiter in the destination file.</span></span>  
  
    -   <span data-ttu-id="fa788-151">Geben Sie das Spaltentrennzeichen in der Zieldatei an.</span><span class="sxs-lookup"><span data-stu-id="fa788-151">Specify the column delimiter in the destination file.</span></span>  
  
4.  <span data-ttu-id="fa788-152">(Optional) Wählen Sie eine Tabelle aus, und ändern Sie die Zuordnungen zwischen Quell- und Zielspalten, oder ändern Sie die Metadaten von Zielspalten:</span><span class="sxs-lookup"><span data-stu-id="fa788-152">(Optional) Select one table and change the mappings between source and destination columns, or change the metadata of destination columns:</span></span>  
  
    -   <span data-ttu-id="fa788-153">Ordnen Sie Quellspalten verschiedenen Zielspalten zu.</span><span class="sxs-lookup"><span data-stu-id="fa788-153">Map source columns to different destination columns.</span></span>  
  
    -   <span data-ttu-id="fa788-154">Ändern Sie den Datentyp in der Zielspalte.</span><span class="sxs-lookup"><span data-stu-id="fa788-154">Change the data type in the destination column.</span></span>  
  
    -   <span data-ttu-id="fa788-155">Legen Sie die Länge von Spalten mit Zeichendatentypen fest.</span><span class="sxs-lookup"><span data-stu-id="fa788-155">Set the length of columns with character data types.</span></span>  
  
    -   <span data-ttu-id="fa788-156">Legen Sie die Genauigkeit und die Dezimalstellen von Spalten mit numerischen Datentypen fest.</span><span class="sxs-lookup"><span data-stu-id="fa788-156">Set the precision and scale of columns with numeric data types.</span></span>  
  
    -   <span data-ttu-id="fa788-157">Geben Sie an, ob für die Spalte NULL-Werte zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="fa788-157">Specify whether the column can contain null values.</span></span>  
  
5.  <span data-ttu-id="fa788-158">(Optional) Wählen Sie mehrere Tabellen aus, und aktualisieren Sie die Metadaten und Optionen, die auf jene Tabellen angewendet werden sollen:</span><span class="sxs-lookup"><span data-stu-id="fa788-158">(Optional) Select multiple tables, and update the metadata and options to apply to those tables:</span></span>  
  
    -   <span data-ttu-id="fa788-159">Wählen Sie ein vorhandenes Zielschema aus, oder geben Sie ein neues Schema an, dem Tabellen zugewiesen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fa788-159">Select an existing destination schema or provide a new schema to which to assign tables.</span></span>  
  
    -   <span data-ttu-id="fa788-160">Geben Sie an, ob IDENTITY_INSERT in Zieltabellen aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="fa788-160">Specify whether to enable identity inserts in destination tables.</span></span>  
  
    -   <span data-ttu-id="fa788-161">Geben Sie an, ob Zieltabellen gelöscht und neu erstellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fa788-161">Specify whether to drop and re-create destination tables.</span></span>  
  
    -   <span data-ttu-id="fa788-162">Geben Sie an, ob vorhandene Zieltabellen abgeschnitten werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fa788-162">Specify whether to truncate existing destination tables.</span></span>  
  
6.  <span data-ttu-id="fa788-163">Speichern Sie ein Paket, und führen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="fa788-163">Save and run a package.</span></span>  
  
     <span data-ttu-id="fa788-164">Falls der Assistent in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder an der Eingabeaufforderung gestartet wird, kann das Paket sofort ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fa788-164">If the wizard is started from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or the command prompt, the package can run immediately.</span></span> <span data-ttu-id="fa788-165">Optional können Sie das Paket in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **msdb** -Datenbank oder im Dateisystem speichern.</span><span class="sxs-lookup"><span data-stu-id="fa788-165">You can optionally save the package to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **msdb** database or to the file system.</span></span> <span data-ttu-id="fa788-166">Weitere Informationen zur **msdb** -Datenbank finden Sie unter [Paketverwaltung &#40;SSIS-Dienst&#41;](../service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="fa788-166">For more information about the **msdb** database, see [Package Management &#40;SSIS Service&#41;](../service/package-management-ssis-service.md).</span></span>  
  
     <span data-ttu-id="fa788-167">Beim Speichern des Pakets können Sie die Paketschutzebene festlegen und das Kennwort angeben, wenn für die Schutzebene ein Kennwort verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fa788-167">When you save the package you can set the package protection level, and if the protection level uses a password, provide the password.</span></span> <span data-ttu-id="fa788-168">Weitere Informationen zu Paket Schutz Ebenen finden Sie unter [Access Control für sensible Daten in-Paketen](../security/access-control-for-sensitive-data-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="fa788-168">For more information about package protection levels, see [Access Control for Sensitive Data in Packages](../security/access-control-for-sensitive-data-in-packages.md).</span></span>  
  
     <span data-ttu-id="fa788-169">Falls der Assistent in einem [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Projekt in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] gestartet wird, kann das Paket nicht im Assistenten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fa788-169">If the wizard is started from an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you cannot run the package from the wizard.</span></span> <span data-ttu-id="fa788-170">Stattdessen wird das Paket dem [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Projekt hinzugefügt, in dem Sie den Assistenten gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="fa788-170">Instead, the package is added to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project from which you started the wizard.</span></span> <span data-ttu-id="fa788-171">Sie können das Paket dann in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] ausführen.</span><span class="sxs-lookup"><span data-stu-id="fa788-171">You can then run the package in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fa788-172">In [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] ist die Option zum Speichern des vom Assistenten erstellten Pakets nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fa788-172">In [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], the option to save the package created by the wizard is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa788-173">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fa788-173">See Also</span></span>  
 <span data-ttu-id="fa788-174">[SQL Server-Import/Export-Assistent](import-and-export-data-with-the-sql-server-import-and-export-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="fa788-174">[SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md) </span></span>  
 [<span data-ttu-id="fa788-175">Erstellen von Paketen in SQL Server-Datentools</span><span class="sxs-lookup"><span data-stu-id="fa788-175">Create Packages in SQL Server Data Tools</span></span>](../create-packages-in-sql-server-data-tools.md)  
  
  
