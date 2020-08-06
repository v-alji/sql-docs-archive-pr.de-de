---
title: Ziel auswählen (SQL Server-Import/Export-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.chooseadestination.f1
ms.assetid: 1898be15-3e69-42d3-8ecb-3733c9f6c8e3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e4bf9b717ef9de20d84d32c18eb3caa4c54cad87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619945"
---
# <a name="choose-a-destination-sql-server-import-and-export-wizard"></a><span data-ttu-id="5c485-102">Ziel auswählen (SQL Server-Import/Export-Assistent)</span><span class="sxs-lookup"><span data-stu-id="5c485-102">Choose a Destination (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="5c485-103">Verwenden Sie die Seite **Ziel auswählen** , um das Ziel der Daten anzugeben, die Sie kopieren möchten.</span><span class="sxs-lookup"><span data-stu-id="5c485-103">Use the **Choose a Destination** page to specify the destination of the data that you want to copy.</span></span>  
  
 <span data-ttu-id="5c485-104">Weitere Informationen zu diesem Assistenten finden Sie unter [SQL Server-Import/Export-Assistenten](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="5c485-104">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="5c485-105">Weitere Informationen zu den Optionen für das Starten des Assistenten sowie zu den Berechtigungen, die zum erfolgreichen Ausführen des Assistenten erforderlich sind, finden Sie unter [Ausführen des SQL Server-Import/Export-Assistenten](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="5c485-105">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="5c485-106">Mit dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Import/Export-Assistenten werden Daten aus einer Quelle in ein Ziel kopiert.</span><span class="sxs-lookup"><span data-stu-id="5c485-106">The purpose of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="5c485-107">Mit dem Assistenten können auch eine Zieldatenbank und Zieltabellen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="5c485-107">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="5c485-108">Wenn Sie jedoch mehrere Datenbanken, Tabellen oder andere Datenbankobjekte kopieren müssen, verwenden Sie stattdessen den Assistenten zum Kopieren von Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="5c485-108">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="5c485-109">Weitere Informationen finden Sie unter [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="5c485-109">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="5c485-110">Statische Optionen</span><span class="sxs-lookup"><span data-stu-id="5c485-110">Static Options</span></span>  
 <span data-ttu-id="5c485-111">**Ziel**</span><span class="sxs-lookup"><span data-stu-id="5c485-111">**Destination**</span></span>  
 <span data-ttu-id="5c485-112">Wählen Sie den Datenanbieter aus, dessen Datenspeicherformat mit dem des Zieles übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="5c485-112">Choose the data provider that matches the data storage format of the destination.</span></span> <span data-ttu-id="5c485-113">Möglicherweise sind für die Datenquelle mehrere Anbieter verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5c485-113">There may be more than one provider available for your data source.</span></span> <span data-ttu-id="5c485-114">Mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] können Sie z [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . b. Native Client, den .NET Framework Datenanbieter für SQL Server oder den Microsoft OLE DB-Anbieter für SQL Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="5c485-114">For example, with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you can use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, the .NET Framework Data Provider for SQL Server, or the Microsoft OLE DB Provider for SQL Server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5c485-115">Wählen Sie zum Speichern von Daten in einem ODBC-Ziel den .NET Framework-Datenanbieter für ODBC aus.</span><span class="sxs-lookup"><span data-stu-id="5c485-115">To save data to an ODBC destination, select the .NET Framework Data Provider for ODBC.</span></span>  
  
 <span data-ttu-id="5c485-116">Die **Datenquellen** Eigenschaft verfügt über eine Variable Anzahl von Optionen, die sich abhängig von den auf dem Computer installierten Anbietern ändern.</span><span class="sxs-lookup"><span data-stu-id="5c485-116">The **Data Source** property has a variable number of options, which change depending on the providers installed on the computer.</span></span> <span data-ttu-id="5c485-117">In den folgenden Tabellen sind die Optionen für einige häufig verwendete Ziele aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="5c485-117">The following tables list the options for some commonly used destinations.</span></span> <span data-ttu-id="5c485-118">Die Angaben zu anderen Anbietern finden Sie in den entsprechenden Dokumentationen zu den Anbietern.</span><span class="sxs-lookup"><span data-stu-id="5c485-118">For other providers, see the provider-specific documentation.</span></span>  
  
## <a name="dynamic-options"></a><span data-ttu-id="5c485-119">Dynamische Optionen</span><span class="sxs-lookup"><span data-stu-id="5c485-119">Dynamic Options</span></span>  
 <span data-ttu-id="5c485-120">In den folgenden Abschnitten sind die verfügbaren Optionen für mehrere Datenquellen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="5c485-120">The following sections show the options available for several data sources.</span></span> <span data-ttu-id="5c485-121">Nicht alle Ziele, die in der Dropdownliste der Ziele verfügbar sind, werden hier aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="5c485-121">Not all the destinations that are available in the Destination drop-down are listed here.</span></span>  
  
### <a name="destination--sql-server-native-client-or-microsoft-ole-db-provider-for-sql-server"></a><span data-ttu-id="5c485-122">Ziel = SQL Server Native Client oder Microsoft OLE DB-Anbieter für SQL Server</span><span class="sxs-lookup"><span data-stu-id="5c485-122">Destination = SQL Server Native Client or Microsoft OLE DB Provider for SQL Server</span></span>  
 <span data-ttu-id="5c485-123">**Servername**</span><span class="sxs-lookup"><span data-stu-id="5c485-123">**Server name**</span></span>  
 <span data-ttu-id="5c485-124">Geben Sie den Namen des Servers ein, der die Daten empfangen soll, oder wählen Sie einen Server aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="5c485-124">Type the name of the server to receive the data, or choose a server from the list.</span></span>  
  
 <span data-ttu-id="5c485-125">**Windows-Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="5c485-125">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="5c485-126">Gibt an, ob das Paket die Microsoft Windows-Authentifizierung verwenden soll, um sich bei der Datenbank anzumelden.</span><span class="sxs-lookup"><span data-stu-id="5c485-126">Specify whether the package should use Microsoft Windows Authentication to log in to the database.</span></span> <span data-ttu-id="5c485-127">Im Sinne einer größeren Sicherheit wird die Windows-Authentifizierung empfohlen.</span><span class="sxs-lookup"><span data-stu-id="5c485-127">Windows Authentication is recommended for better security.</span></span>  
  
 <span data-ttu-id="5c485-128">**SQL Server-Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="5c485-128">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="5c485-129">Gibt an, ob das Paket die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Authentifizierung verwenden soll, um sich bei der Datenbank anzumelden.</span><span class="sxs-lookup"><span data-stu-id="5c485-129">Specify whether the package should use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication to log in to the database.</span></span> <span data-ttu-id="5c485-130">Wenn Sie die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Authentifizierung verwenden, müssen Sie einen Benutzernamen und ein Kennwort angeben.</span><span class="sxs-lookup"><span data-stu-id="5c485-130">If you use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, you must provide a user name and password.</span></span>  
  
 <span data-ttu-id="5c485-131">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="5c485-131">**User name**</span></span>  
 <span data-ttu-id="5c485-132">Geben Sie einen Benutzernamen für die Datenbankverbindung an, wenn Sie die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="5c485-132">Specify a user name for the database connection when you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="5c485-133">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="5c485-133">**Password**</span></span>  
 <span data-ttu-id="5c485-134">Geben Sie das Kennwort für die Datenbankverbindung ein, wenn Sie die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="5c485-134">Provide the password for the database connection when you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="5c485-135">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="5c485-135">**Database**</span></span>  
 <span data-ttu-id="5c485-136">Wählen Sie aus der Liste der Datenbanken auf der angegebenen Instanz von aus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , oder erstellen Sie eine neue Datenbank, indem Sie auf **neu**klicken.</span><span class="sxs-lookup"><span data-stu-id="5c485-136">Select from the list of databases on the specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or create a new database by clicking **New**.</span></span>  
  
 <span data-ttu-id="5c485-137">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="5c485-137">**Refresh**</span></span>  
 <span data-ttu-id="5c485-138">Klicken Sie auf **Aktualisieren**, um die Liste der verfügbaren Datenbanken zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="5c485-138">Restore the list of available databases by clicking **Refresh**.</span></span>  
  
 <span data-ttu-id="5c485-139">**Neu**</span><span class="sxs-lookup"><span data-stu-id="5c485-139">**New**</span></span>  
 <span data-ttu-id="5c485-140">Erstellen Sie eine neue Zieldatenbank mithilfe des Dialog Felds **Datenbank erstellen** .</span><span class="sxs-lookup"><span data-stu-id="5c485-140">Create a new destination database by using the **Create Database** dialog box.</span></span>  
  
### <a name="destination--flat-file-destination"></a><span data-ttu-id="5c485-141">Ziel = Flatfileziel</span><span class="sxs-lookup"><span data-stu-id="5c485-141">Destination = Flat File Destination</span></span>  
 <span data-ttu-id="5c485-142">**Dateiname**</span><span class="sxs-lookup"><span data-stu-id="5c485-142">**File name**</span></span>  
 <span data-ttu-id="5c485-143">Geben Sie den Pfad und den Dateinamen für die Datei an, in der die Daten gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5c485-143">Specify the path and file name for the file in which to store the data.</span></span> <span data-ttu-id="5c485-144">Klicken Sie alternativ auf **Durchsuchen**, um nach einer Datei zu suchen.</span><span class="sxs-lookup"><span data-stu-id="5c485-144">Or, click **Browse** to locate a file.</span></span>  
  
 <span data-ttu-id="5c485-145">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="5c485-145">**Browse**</span></span>  
 <span data-ttu-id="5c485-146">Suchen Sie nach einer Datei mithilfe des Dialogfelds **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="5c485-146">Locate a file by using the **Open** dialog box.</span></span>  
  
 <span data-ttu-id="5c485-147">**Gebietsschema**</span><span class="sxs-lookup"><span data-stu-id="5c485-147">**Locale**</span></span>  
 <span data-ttu-id="5c485-148">Geben Sie die Gebietsschema-ID (LCID) an, die die Sortierreihenfolge für Zeichen und das Datums- und Zeitformat definiert.</span><span class="sxs-lookup"><span data-stu-id="5c485-148">Specify the locale ID (LCID) that defines character sort orders and date and time formatting.</span></span>  
  
 <span data-ttu-id="5c485-149">**Unicode**</span><span class="sxs-lookup"><span data-stu-id="5c485-149">**Unicode**</span></span>  
 <span data-ttu-id="5c485-150">Gibt an, ob Unicode verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c485-150">Indicate whether to use Unicode.</span></span> <span data-ttu-id="5c485-151">Wenn Sie Unicode verwenden, brauchen Sie keine Codepage anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5c485-151">If you use Unicode, you do not have to specify a code page.</span></span>  
  
 <span data-ttu-id="5c485-152">**Codepage**</span><span class="sxs-lookup"><span data-stu-id="5c485-152">**Code page**</span></span>  
 <span data-ttu-id="5c485-153">Geben Sie die Codepage für die Sprache an, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="5c485-153">Specify the code page for the language you want to use.</span></span>  
  
 <span data-ttu-id="5c485-154">**Format**</span><span class="sxs-lookup"><span data-stu-id="5c485-154">**Format**</span></span>  
 <span data-ttu-id="5c485-155">Gibt an, ob die Datei Formatierung mit Trennzeichen, fester Breite oder rechtem Flatterrand verwendet.</span><span class="sxs-lookup"><span data-stu-id="5c485-155">Indicate whether to use delimited, fixed width, or ragged right formatting.</span></span>  
  
|<span data-ttu-id="5c485-156">Wert</span><span class="sxs-lookup"><span data-stu-id="5c485-156">Value</span></span>|<span data-ttu-id="5c485-157">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5c485-157">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5c485-158">Durch Trennzeichen getrennt</span><span class="sxs-lookup"><span data-stu-id="5c485-158">Delimited</span></span>|<span data-ttu-id="5c485-159">Spalten werden durch ein Trennzeichen getrennt, das auf der Seite **Spalten** angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5c485-159">Columns are separated by a delimiter, specified on the **Columns** page.</span></span>|  
|<span data-ttu-id="5c485-160">Feste Breite</span><span class="sxs-lookup"><span data-stu-id="5c485-160">Fixed width</span></span>|<span data-ttu-id="5c485-161">Spalten haben eine feste Breite.</span><span class="sxs-lookup"><span data-stu-id="5c485-161">Columns have a fixed width.</span></span>|  
|<span data-ttu-id="5c485-162">Rechter Flatterrand</span><span class="sxs-lookup"><span data-stu-id="5c485-162">Ragged right</span></span>|<span data-ttu-id="5c485-163">Bei Dateien mit rechtem Flatterrand weisen alle Spalten mit Ausnahme der letzten eine feste Breite auf. Die letzte Spalte wird durch das Zeilentrennzeichen begrenzt.</span><span class="sxs-lookup"><span data-stu-id="5c485-163">Ragged right files are files in which every column has a fixed width, except for the last column, which is delimited by the row delimiter.</span></span>|  
  
 <span data-ttu-id="5c485-164">**Textqualifizierer**</span><span class="sxs-lookup"><span data-stu-id="5c485-164">**Text qualifier**</span></span>  
 <span data-ttu-id="5c485-165">Geben Sie die zu verwendenden Textqualifizierer ein.</span><span class="sxs-lookup"><span data-stu-id="5c485-165">Type the text qualifier to use.</span></span> <span data-ttu-id="5c485-166">Sie können z. B. angeben, dass jede Textspalte in Anführungszeichen eingeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c485-166">For example, you can specify that each text column be surrounded with quotation marks.</span></span>  
  
 <span data-ttu-id="5c485-167">**Spaltennamen in der ersten Datenzeile**</span><span class="sxs-lookup"><span data-stu-id="5c485-167">**Column names in first data row**</span></span>  
 <span data-ttu-id="5c485-168">Gibt an, ob die Spaltennamen in der ersten Datenzeile angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5c485-168">Indicate whether you want to display column names in the first data row.</span></span>  
  
### <a name="destination--microsoft-excel"></a><span data-ttu-id="5c485-169">Ziel = Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="5c485-169">Destination = Microsoft Excel</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5c485-170">Wählen Sie **Microsoft Excel** nur aus, wenn Sie eine Verbindung mit einer Datenquelle herstellen möchten, für die Excel 2003 oder früher verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5c485-170">Select **Microsoft Excel** only if you want to connect to a data source that uses Excel 2003 or earlier.</span></span> <span data-ttu-id="5c485-171">Zum Herstellen einer Verbindung mit einer Datenquelle, die Excel 2007 verwendet, wählen Sie **Microsoft Office 12,0 Access Datenbank-Engine OLE DB Provider**aus, klicken Sie auf **Eigenschaften**, und geben Sie dann im Dialogfeld Daten Verknüpfungs **Eigenschaften** auf der Registerkarte **alle** für **Erweiterte Eigenschaften**ein `Excel 12.0` .</span><span class="sxs-lookup"><span data-stu-id="5c485-171">To connect to a data source that uses Excel 2007, select **Microsoft Office 12.0 Access Database Engine OLE DB Provider**, click **Properties**, and then on the **All** tab of the **Data Link Properties** dialog box, for **Extended Properties**, enter `Excel 12.0`.</span></span>  
  
 <span data-ttu-id="5c485-172">**Excel-Dateipfad**</span><span class="sxs-lookup"><span data-stu-id="5c485-172">**Excel file path**</span></span>  
 <span data-ttu-id="5c485-173">Geben Sie den Pfad und den Dateinamen für die Arbeitsmappe an, in der die Daten gespeichert werden sollen (z \\ . b. C:\MyData.xls\Sales\Database\Northwind.xls).</span><span class="sxs-lookup"><span data-stu-id="5c485-173">Specify the path and file name for the workbook in which to store the data (for example, C:\MyData.xls, \\\Sales\Database\Northwind.xls).</span></span> <span data-ttu-id="5c485-174">Oder klicken Sie auf **Durchsuchen** , um eine Arbeitsmappe zu suchen.</span><span class="sxs-lookup"><span data-stu-id="5c485-174">Or, click **Browse** to locate a workbook.</span></span>  
  
 <span data-ttu-id="5c485-175">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="5c485-175">**Browse**</span></span>  
 <span data-ttu-id="5c485-176">Suchen Sie mithilfe des Dialog Felds **Öffnen** eine Excel-Arbeitsmappe.</span><span class="sxs-lookup"><span data-stu-id="5c485-176">Locate an Excel workbook by using the **Open** dialog box.</span></span>  
  
 <span data-ttu-id="5c485-177">**Excel-Version**</span><span class="sxs-lookup"><span data-stu-id="5c485-177">**Excel version**</span></span>  
 <span data-ttu-id="5c485-178">Wählen Sie die Version von Excel aus, die von der Zielarbeitsmappe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5c485-178">Select the version of Excel that is used by the destination workbook.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5c485-179">Wenn Sie Daten in ein [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)]-Ziel exportieren, verwendet der Assistent die Excel-Zielkomponente von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c485-179">When you export data to a [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)] destination, the wizard uses the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Excel Destination component.</span></span> <span data-ttu-id="5c485-180">Weitere Informationen zu Überlegungen zur Verwendung und zu bekannten Problemen finden Sie unter [Excel Destination](../data-flow/excel-destination.md).</span><span class="sxs-lookup"><span data-stu-id="5c485-180">For information on some usage considerations and known issues, see [Excel Destination](../data-flow/excel-destination.md).</span></span>  
  
### <a name="destination--microsoft-access"></a><span data-ttu-id="5c485-181">Ziel = Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="5c485-181">Destination = Microsoft Access</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5c485-182">Wählen Sie **Microsoft Access** nur aus, wenn Sie eine Verbindung mit einer Datenbank herstellen möchten, die Access 2003 oder früher verwendet.</span><span class="sxs-lookup"><span data-stu-id="5c485-182">Select **Microsoft Access** only if you want to connect to a database that uses Access 2003 or earlier.</span></span> <span data-ttu-id="5c485-183">Zum Herstellen einer Verbindung mit einer Datenbank, die Access 2007 verwendet, wählen Sie **Microsoft Office 12,0 Access Datenbank-Engine OLE DB Provider**aus.</span><span class="sxs-lookup"><span data-stu-id="5c485-183">To connect to a database that uses Access 2007, select **Microsoft Office 12.0 Access Database Engine OLE DB Provider**.</span></span>  
  
 <span data-ttu-id="5c485-184">**Dateiname**</span><span class="sxs-lookup"><span data-stu-id="5c485-184">**File name**</span></span>  
 <span data-ttu-id="5c485-185">Geben Sie den Pfad und den Dateinamen für die Datenbankdatei an, in der die Daten gespeichert werden sollen (z. b. c:\mydata.mdb, \\ \sales\database\northwind.mdb).</span><span class="sxs-lookup"><span data-stu-id="5c485-185">Specify the path and file name for the database file in which to store the data (for example, C:\MyData.mdb, \\\Sales\Database\Northwind.mdb).</span></span> <span data-ttu-id="5c485-186">Oder klicken Sie auf **Durchsuchen** , um eine Datenbankdatei zu suchen.</span><span class="sxs-lookup"><span data-stu-id="5c485-186">Or, click **Browse** to locate a database file.</span></span>  
  
 <span data-ttu-id="5c485-187">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="5c485-187">**Browse**</span></span>  
 <span data-ttu-id="5c485-188">Navigieren Sie im Dialogfeld **Öffnen** zu der Datenbankdatei.</span><span class="sxs-lookup"><span data-stu-id="5c485-188">Browse to the database file by using the **Open** dialog box.</span></span>  
  
 <span data-ttu-id="5c485-189">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="5c485-189">**User name**</span></span>  
 <span data-ttu-id="5c485-190">Geben Sie einen gültigen Benutzernamen für die Datenbankverbindung an, wenn der Datenbank eine Informationsdatei für die Arbeitsgruppe zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="5c485-190">Specify a valid user name for the database connection when a workgroup information file is associated with the database.</span></span>  
  
 <span data-ttu-id="5c485-191">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="5c485-191">**Password**</span></span>  
 <span data-ttu-id="5c485-192">Geben Sie das Kennwort des Benutzers für die Datenbankverbindung an, wenn der Datenbank eine Informationsdatei für die Arbeitsgruppe zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="5c485-192">Provide the user's password for the database connection when a workgroup information file is associated with the database.</span></span> <span data-ttu-id="5c485-193">Wenn die Datenbank jedoch mit einem einzigen Kennwort für alle Benutzer geschützt ist, müssen Sie diesen Wert im Dialogfeld **Daten** Verknüpfungs Eigenschaften angeben, auf das über die Schaltfläche **erweitert** zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="5c485-193">However, if the database is protected with a single password for all users, you must provide this value in the **Data Link Properties** dialog box, which is accessed from the **Advanced** button.</span></span>  
  
 <span data-ttu-id="5c485-194">**Erweitert**</span><span class="sxs-lookup"><span data-stu-id="5c485-194">**Advanced**</span></span>  
 <span data-ttu-id="5c485-195">Mithilfe des Dialogfelds **Datenlinkeigenschaften** geben Sie erweiterte Optionen an, z.B. das Datenbankkennwort oder eine nicht standardmäßige Informationsdatei für Arbeitsgruppen.</span><span class="sxs-lookup"><span data-stu-id="5c485-195">Specify advanced options, such as the database password or a non-default workgroup information file, by using the **Data Link Properties** dialog box.</span></span> <span data-ttu-id="5c485-196">Weitere Informationen zu OLE DB Anbieter Eigenschaften finden Sie im Abschnitt Datenzugriff der [MSDN Library](https://go.microsoft.com/fwlink/?linkid=62553).</span><span class="sxs-lookup"><span data-stu-id="5c485-196">For more information about OLE DB provider properties, search in the Data Access section of the [MSDN Library](https://go.microsoft.com/fwlink/?linkid=62553).</span></span>  
  
  
