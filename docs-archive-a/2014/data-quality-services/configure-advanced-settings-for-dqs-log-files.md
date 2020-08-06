---
title: Konfigurieren der erweiterten Einstellungen für DQS-Protokolldateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
helpviewer_keywords:
- log files,advanced settings
- dqs log files,advanced settings
ms.assetid: 1d565748-9759-425c-ae38-4d2032a86868
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ad41b0cac95f9bfe5565ccbac16b0fda3e28ddf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696097"
---
# <a name="configure-advanced-settings-for-dqs-log-files"></a><span data-ttu-id="bbd4d-102">Konfigurieren der erweiterten Einstellungen für DQS-Protokolldateien</span><span class="sxs-lookup"><span data-stu-id="bbd4d-102">Configure Advanced Settings for DQS Log Files</span></span>
  <span data-ttu-id="bbd4d-103">In diesem Thema wird beschrieben, wie erweiterte Einstellungen für [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] - und [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Protokolldateien konfiguriert werden, z. B. das Festlegen der maximalen Rolldateigröße für Protokolldateien, das Festlegen des Zeitstempelschemas von Ereignissen usw.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-103">This topic describes how to configure advanced settings for [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] and [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log files, such as set the rolling file size limit of the log files, set the time stamp pattern of the events, and so on.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bbd4d-104">Diese Aktivitäten können nicht mit [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]ausgeführt werden und sind nur für erfahrene Benutzer vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-104">These activities cannot be performed using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], and is intended for advanced users only.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bbd4d-105">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="bbd4d-105">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bbd4d-106">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="bbd4d-106">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bbd4d-107">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="bbd4d-107">Permissions</span></span>  
  
-   <span data-ttu-id="bbd4d-108">Das Windows-Benutzerkonto muss ein Mitglied der festen Serverrolle "sysadmin" in der SQL Server-Instanz sein, damit Konfigurationseinstellungen in der A_CONFIGURATION-Tabelle in der DQS_MAIN-Datenbank geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-108">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance to modify configuration settings in the A_CONFIGURATION table in the DQS_MAIN database.</span></span>  
  
-   <span data-ttu-id="bbd4d-109">Sie müssen als Mitglied der Gruppe "Administratoren" auf dem Computer angemeldet sein, auf dem Sie die Datei "DQLog.Client.xml" ändern, um die [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Protokollierungseinstellungen konfigurieren zu können.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-109">You must be logged on as a member of the Administrators group on the computer where you are modifying the DQLog.Client.xml file to configure the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] logging settings.</span></span>  
  
##  <a name="configure-data-quality-server-log-settings"></a><a name="DQSServer"></a> <span data-ttu-id="bbd4d-110">Konfigurieren von Data Quality Server-Protokolleinstellungen</span><span class="sxs-lookup"><span data-stu-id="bbd4d-110">Configure Data Quality Server Log Settings</span></span>  
 <span data-ttu-id="bbd4d-111">Die [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] -Protokolleinstellungen sind in einem XML-Format in der Spalte **VALUE** der Zeile **ServerLogging** in der A_CONFIGURATION-Tabelle in der DQS_MAIN-Datenbank vorhanden.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-111">The [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log settings are present in an XML format in the **VALUE** column of the **ServerLogging** row in the A_CONFIGURATION table in the DQS_MAIN database.</span></span> <span data-ttu-id="bbd4d-112">Sie können die folgende SQL-Abfrage ausführen, um die Konfigurationsinformationen anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="bbd4d-112">You can run the following SQL query to view the configuration information:</span></span>  
  
```sql  
select * from DQS_MAIN.dbo.A_CONFIGURATION where NAME='ServerLogging'; 
```  
  
 <span data-ttu-id="bbd4d-113">Sie müssen die entsprechenden Informationen in der Spalte **VALUE** der Zeile **ServerLogging** aktualisieren, um die Konfigurationseinstellungen für die [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] -Protokollierung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-113">You must update the appropriate information in the **VALUE** column of the **ServerLogging** row to change the configuration settings for [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] logging.</span></span> <span data-ttu-id="bbd4d-114">In diesem Beispiel aktualisieren wir die [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] -Protokolleinstellungen, um die maximale Rolldateigröße auf 25.000 KB festzulegen (der Standard beträgt 20.000 KB).</span><span class="sxs-lookup"><span data-stu-id="bbd4d-114">In this example, we will update the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log settings to set the rolling file size limit to 25000 KB (the default is 20000 KB).</span></span>  
  
1.  <span data-ttu-id="bbd4d-115">Starten Sie Microsoft SQL Server Management Studio, und stellen Sie eine Verbindung mit der entsprechenden SQL Server-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-115">Start Microsoft SQL Server Management Studio, and connect to the appropriate SQL Server instance.</span></span>  
  
2.  <span data-ttu-id="bbd4d-116">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf den Server, und klicken Sie dann auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-116">In Object Explorer, right-click the server, and then click **New Query**.</span></span>  
  
3.  <span data-ttu-id="bbd4d-117">Geben Sie im Fenster Abfrage-Editor die folgenden SQL-Anweisungen ein:</span><span class="sxs-lookup"><span data-stu-id="bbd4d-117">In the Query Editor window, copy the following SQL statements:</span></span>  
  
    ```sql  
    -- Begin the transaction.  
    BEGIN TRAN  
    GO  
    -- set the XML value field for the row with name=ServerLogging  
    update DQS_MAIN.dbo.A_CONFIGURATION   
    set VALUE='<configuration>  
      <configSections>  
        <section name="loggingConfiguration" type="Microsoft.Practices.EnterpriseLibrary.Logging.Configuration.LoggingSettings, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" />  
      </configSections>  
      <loggingConfiguration name="Logging Application Block" tracingEnabled="true" defaultCategory="" logWarningsWhenNoCategoriesMatch="true">  
        <listeners>  
          <add fileName="###REPLACE_THIS_WITH_SQL_SERVER_INSTANCE_LOG_FOLDER_NAME###DQServerLog.###REPLACE_THIS_WITH_SQL_CATALOG_NAME###.log" footer="" formatter="Custom Text Formatter" header="" rollFileExistsBehavior="Increment" rollInterval="None" rollSizeKB="25000" timeStampPattern="yyyy-MM-dd" listenerDataType="Microsoft.Practices.EnterpriseLibrary.Logging.Configuration.RollingFlatFileTraceListenerData, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" traceOutputOptions="None" filter="All" type="Microsoft.Practices.EnterpriseLibrary.Logging.TraceListeners.RollingFlatFileTraceListener, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" name="Rolling Flat File Trace Listener" />  
        </listeners>  
        <formatters>  
          <add template="{timestamp(local)}|[{threadName}]|{dictionary({value}|)}{message}" type="Microsoft.Practices.EnterpriseLibrary.Logging.Formatters.TextFormatter, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" name="Custom Text Formatter" />  
        </formatters>  
        <logFilters>  
          <add enabled="true" type="Microsoft.Practices.EnterpriseLibrary.Logging.Filters.LogEnabledFilter, Microsoft.Practices.EnterpriseLibrary.Logging, Version=4.1.0.0, Culture=neutral, PublicKeyToken=e44a2bc38ed2c13c" name="LogEnabled Filter" />  
        </logFilters>  
        <categorySources />  
        <specialSources>  
          <allEvents switchValue="All" name="All Events" />  
          <notProcessed switchValue="All" name="Unprocessed Category" />  
          <errors switchValue="All" name="Logging Errors & Warnings">  
            <listeners>  
              <add name="Rolling Flat File Trace Listener" />  
            </listeners>  
          </errors>  
        </specialSources>  
      </loggingConfiguration>  
    </configuration>'  
    WHERE NAME='ServerLogging'  
    GO  
    -- check the result  
    select * from DQS_MAIN.dbo.A_CONFIGURATION where NAME='ServerLogging'  
  
    -- Commit the transaction.  
    COMMIT TRAN  
  
    ```  
  
4.  <span data-ttu-id="bbd4d-118">Drücken Sie F5, um die Anweisungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-118">Press F5 to execute the statements.</span></span> <span data-ttu-id="bbd4d-119">Überprüfen Sie im **Ergebnis** Bereich, ob die Anweisungen erfolgreich ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-119">Check the **Results** pane to verify that the statements have executed successfully.</span></span>  
  
5.  <span data-ttu-id="bbd4d-120">Um Änderungen an der Konfiguration der [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] -Protokollierung zu übernehmen, müssen Sie die folgenden Transact-SQL-Anweisungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-120">To apply changes done to the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] logging configuration, you must run the following Transact-SQL statements.</span></span> <span data-ttu-id="bbd4d-121">Öffnen Sie ein neues Abfrage-Editor-Fenster, und fügen Sie die folgenden Transact-SQL-Anweisungen ein:</span><span class="sxs-lookup"><span data-stu-id="bbd4d-121">Open a new Query Editor window, and paste the following Transact-SQL statements:</span></span>  
  
    ```sql  
    USE [DQS_MAIN]  
    GO  
    DECLARE @return_value int  
    EXEC @return_value = [internal_core].[RefreshLogSettings]  
    SELECT 'Return Value' = @return_value  
    GO  
    ```  
  
6.  <span data-ttu-id="bbd4d-122">Drücken Sie F5, um die Anweisungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-122">Press F5 to execute the statements.</span></span> <span data-ttu-id="bbd4d-123">Überprüfen Sie im **Ergebnis** Bereich, ob die Anweisungen erfolgreich ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-123">Check the **Results** pane to verify that the statements have executed successfully.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bbd4d-124">Die Konfiguration der [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)]-Protokolleinstellungen wird dynamisch generiert und in der DQS_MAIN.Log-Datei gespeichert, die in der Regel unter "C:\Programme\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log" vorhanden ist, wenn Sie die Standardinstanz von SQL Server installiert haben.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-124">The [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] logging settings configuration is dynamically generated and stored in the DQS_MAIN.Log file, which is typically available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Log if you installed the default instance of SQL Server.</span></span> <span data-ttu-id="bbd4d-125">In dieser Datei direkt ausgeführte Änderungen sind jedoch nicht dauerhaft und werden von den Konfigurationseinstellungen in der A_CONFIGURATION-Tabelle in der DQS_MAIN-Datenbank überschrieben.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-125">However, changes done directly in this file do not hold, and are overwritten by the configuration settings in the A_CONFIGURATION table in the DQS_MAIN database.</span></span>  
  
##  <a name="configure-data-quality-client-log-settings"></a><a name="DQSClient"></a><span data-ttu-id="bbd4d-126">Konfigurieren Data Quality-Client Protokoll Einstellungen</span><span class="sxs-lookup"><span data-stu-id="bbd4d-126">Configure Data Quality Client Log Settings</span></span>  
 <span data-ttu-id="bbd4d-127">Die [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] Konfigurationsdatei für die Protokoll Einstellungen (DQLog.Client.xml) ist in der Regel unter c:\Programme\Microsoft SQL server\120\tools\binn\dq\config. Der Inhalt der XML-Datei ähnelt der XML-Datei, die Sie zuvor für die [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] Protokoll Konfigurationseinstellungen geändert haben.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-127">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log setting configuration file, DQLog.Client.xml, is typically available at C:\Program Files\Microsoft SQL Server\120\Tools\Binn\DQ\config. The contents of the XML file is similar to the XML file that you modified earlier for the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] log configuration settings.</span></span> <span data-ttu-id="bbd4d-128">So konfigurieren Sie die [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Protokolleinstellungen:</span><span class="sxs-lookup"><span data-stu-id="bbd4d-128">To configure the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] log settings:</span></span>  
  
1.  <span data-ttu-id="bbd4d-129">Führen Sie ein beliebiges XML-Bearbeitungstool oder den Editor als Administrator aus.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-129">Run any XML editing tool or notepad as an administrator.</span></span>  
  
2.  <span data-ttu-id="bbd4d-130">Öffnen Sie die Datei "DQLog.Client.xml" im Tool oder Editor.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-130">Open the DQLog.Client.xml file in the tool or notepad.</span></span>  
  
3.  <span data-ttu-id="bbd4d-131">Nehmen Sie die erforderlichen Änderungen vor, und speichern Sie die Datei, um die geänderten Protokollierungseinstellungen zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="bbd4d-131">Make the required changes, and save the file to apply the new logging changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbd4d-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bbd4d-132">See Also</span></span>  
 [<span data-ttu-id="bbd4d-133">Konfigurieren von Schweregraden für DQS-Protokolldateien</span><span class="sxs-lookup"><span data-stu-id="bbd4d-133">Configure Severity Levels for DQS Log Files</span></span>](../../2014/data-quality-services/configure-severity-levels-for-dqs-log-files.md)  
  
  
