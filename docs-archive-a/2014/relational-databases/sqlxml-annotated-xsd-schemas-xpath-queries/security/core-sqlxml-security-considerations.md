---
title: Grundlegende SQLXML-Sicherheitsüberlegungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- security [SQLXML], about security
ms.assetid: 330cd2ff-d5d5-4c8e-8f93-0869c977be94
author: rothja
ms.author: jroth
ms.openlocfilehash: eceaa28ff4d1a7b998a51b07df3b1076cf524e81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630627"
---
# <a name="core-sqlxml-security-considerations"></a><span data-ttu-id="8b585-102">Wichtige Sicherheitsüberlegungen zu SQLXML</span><span class="sxs-lookup"><span data-stu-id="8b585-102">Core SQLXML Security Considerations</span></span>
  <span data-ttu-id="8b585-103">Im Folgenden werden Sicherheitsrichtlinien zur Verwendung von SQLXML für den Datenzugriff erläutert.</span><span class="sxs-lookup"><span data-stu-id="8b585-103">The following are security guidelines for using SQLXML for data access.</span></span>  
  
-   <span data-ttu-id="8b585-104">Der SQLXMLOLEDB-Anbieter stellt eine `StreamFlags`-Eigenschaft zur Verfügung, mit der Sie Flags festlegen können, die angeben, welche SQLXML-Funktion für jede spezifische Instanz aktiviert oder deaktiviert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="8b585-104">The SQLXMLOLEDB provider exposes a `StreamFlags` property which allows you to set flags indicating what SQLXML functionality should be enabled or disabled for each specific instance.</span></span> <span data-ttu-id="8b585-105">Anhand dieser Eigenschaft können Sie die Verwendung von SQLXML anpassen und sicherstellen, dass nur die gewünschten Komponenten aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="8b585-105">You can use this property to customize your use of SQLXML and to make sure that only the components you want are enabled.</span></span> <span data-ttu-id="8b585-106">Weitere Informationen finden Sie unter [SQLXMLOLEDB-Anbieter &#40;SQLXML 4,0&#41;](../../../database-engine/dev-guide/sqlxmloledb-provider-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="8b585-106">For more information, see [SQLXMLOLEDB Provider &#40;SQLXML 4.0&#41;](../../../database-engine/dev-guide/sqlxmloledb-provider-sqlxml-4-0.md).</span></span>  
  
-   <span data-ttu-id="8b585-107">Wenn SQLXML-Fehler auftreten und zurückgegeben werden, können sie Informationen über das Datenbankschema wie Tabellennamen, Spaltennamen und Typ umfassen.</span><span class="sxs-lookup"><span data-stu-id="8b585-107">When SQLXML errors occur and are returned, they can include information about the database schema such as table names, column names or type information.</span></span> <span data-ttu-id="8b585-108">Gehen Sie bei der Behandlung dieser Fehler vorsichtig vor, sodass Informationen über Ihre [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Installation von anderen Benutzern nicht einfach ermittelt werden können, wenn keine Absicht oder Notwendigkeit dazu besteht.</span><span class="sxs-lookup"><span data-stu-id="8b585-108">You should use care when handling these errors so that information about your [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation is not easily discoverable by users where it is not intended or needed.</span></span>  
  
-   <span data-ttu-id="8b585-109">Wird SQLXML entweder zum Abfragen oder zum Senden von Updates an [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] verwendet, werden keine Einschränkungen in Bezug auf die Datenmenge, die ausgetauscht werden kann, festgelegt, und die Datenmenge in einer SQLXML-Nutzlast wird vor dem Verarbeitungsversuch nicht überprüft.</span><span class="sxs-lookup"><span data-stu-id="8b585-109">When used to either query or send updates to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], SQLXML sets no limit on the amount of data that can be exchanged and does not do any checking on the size of data in a SQLXML payload before attempting to process it.</span></span> <span data-ttu-id="8b585-110">Wenn Sie Ihre Anwendung mit SQLXML entwickeln, liegt es in Ihrem Verantwortungsbereich sicherzustellen, dass genügend Systemspeicher zum Verarbeiten der Daten vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8b585-110">When you develop your application using SQLXML, it is your responsibility to ensure there is enough memory on the system to process the data.</span></span> <span data-ttu-id="8b585-111">Beim Abfragen von Daten vom Server sollten Sie beispielsweise überprüfen, ob genügend Speicherplatz auf dem Client vorhanden ist, um die abgefragten Daten zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="8b585-111">For example, when querying data from the server, you should verify there is enough room in memory on the client to receive it.</span></span> <span data-ttu-id="8b585-112">Ebenso müssen Sie beim Laden von Daten auf den Server sicherstellen, dass genügend Speicherplatz auf dem Server zur Verarbeitung der Daten und genügend Festplattenspeicher auf dem Server zum Speichern der Daten zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="8b585-112">Likewise, if you are loading data to the server, you need to verify there is enough available memory on the server to process it and enough available disk storage space on the server to store the data.</span></span>  
  
-   <span data-ttu-id="8b585-113">SQLXML generiert [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Abfragen dynamisch und aktualisiert Befehle und sendet sie zur Ausführung an[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b585-113">SQLXML dynamically generates [!INCLUDE[tsql](../../../includes/tsql-md.md)] queries and update commands and sends them to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] for execution.</span></span> <span data-ttu-id="8b585-114">Dies ist die einzige Methode, bei der SQLXML den Server abfragt und aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="8b585-114">This is the only way in which SQLXML queries and updates the server.</span></span> <span data-ttu-id="8b585-115">Ergebnisse werden entweder als Datenstrom (von XML) oder als Rowset empfangen.</span><span class="sxs-lookup"><span data-stu-id="8b585-115">Results will be received either as a stream (of XML) or as a rowset.</span></span>  
  
-   <span data-ttu-id="8b585-116">Beim Empfang von Abfrageergebnissen führt SQLXML basierend auf dem Inhalt der empfangenen Daten keine Aktionen aus.</span><span class="sxs-lookup"><span data-stu-id="8b585-116">When receiving query results, SQLXML takes no actions based on the content of the data that it receives.</span></span> <span data-ttu-id="8b585-117">Es erfolgt keine zusätzliche Verarbeitung auf Grundlage des Typs oder des Inhalts der Daten.</span><span class="sxs-lookup"><span data-stu-id="8b585-117">No additional processing is done based on the type or contents of the data.</span></span> <span data-ttu-id="8b585-118">Die Daten werden nie als Code behandelt, mit dem Aktionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8b585-118">The data is never treated as code with which to execute actions.</span></span>  
  
-   <span data-ttu-id="8b585-119">Beim Ausführen von XML-Vorlagen übersetzt SQLXML die XPath- und DBObject-Abfragen, die in der übermittelten Vorlage enthalten sind, in [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Befehle, die dann für [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8b585-119">When executing XML Templates, SQLXML translates the XPath and DBObject queries contained within the submitted template into [!INCLUDE[tsql](../../../includes/tsql-md.md)] commands that are then executed against [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8b585-120">Diese Befehle beeinflussen nur vorhandene Daten.</span><span class="sxs-lookup"><span data-stu-id="8b585-120">These commands only ever affect existing data.</span></span> <span data-ttu-id="8b585-121">Von SQLXML generierte Befehle ändern nie die Struktur der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="8b585-121">Commands generated by SQLXML will never alter the structure of the database.</span></span> <span data-ttu-id="8b585-122">Benutzer müssen explizite Befehle ausgeben, um die Datenbankstruktur zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8b585-122">Users must issue explicit commands to alter the database structure.</span></span> <span data-ttu-id="8b585-123">Dazu können sie sie beispielsweise in einen `sql:query`-Block einer Vorlage einschließen.</span><span class="sxs-lookup"><span data-stu-id="8b585-123">For example, by including them in a `sql:query` block of a template.</span></span>  
  
-   <span data-ttu-id="8b585-124">Beim Ausführen von DBObject-Abfragen und XPath-Anweisungen über Zuordnungsdateien lässt SQLXML die Daten in der Datenbank unverändert.</span><span class="sxs-lookup"><span data-stu-id="8b585-124">When executing DBObject queries and XPath statements over mapping files, SQLXML will not alter the data in the database in any way.</span></span>  
  
-   <span data-ttu-id="8b585-125">SQLXML kann Formatierungsänderungen für die angegebenen Daten basierend auf den Unterschieden zwischen dem XML- und dem [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Datenmodell vornehmen.</span><span class="sxs-lookup"><span data-stu-id="8b585-125">SQLXML may make formatting changes to the given data based on differences between the XML and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data models.</span></span> <span data-ttu-id="8b585-126">Zum Beispiel ist das Format für die Zeitangabe unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="8b585-126">For example, the format for specifying a time is different.</span></span> <span data-ttu-id="8b585-127">SQLXML versucht, diese Unterschiede aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="8b585-127">SQLXML will attempt to resolve these differences.</span></span> <span data-ttu-id="8b585-128">Als Folge können Genauigkeitsinformationen verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="8b585-128">As a result, some precision information may be lost.</span></span>  
  
-   <span data-ttu-id="8b585-129">SQLXML legt keine Beschränkungen für die Dauer der Verarbeitung der Daten fest.</span><span class="sxs-lookup"><span data-stu-id="8b585-129">SQLXML sets no limit on the amount of time it takes to process the data.</span></span> <span data-ttu-id="8b585-130">Die Verarbeitung wird fortgesetzt, bis ein Fehler auftritt oder die Verarbeitung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="8b585-130">Processing will continue until an error occurs or processing is complete.</span></span>  
  
-   <span data-ttu-id="8b585-131">SQLXML schreibt nicht ins Dateisystem.</span><span class="sxs-lookup"><span data-stu-id="8b585-131">SQLXML does not write to the file system.</span></span> <span data-ttu-id="8b585-132">Wenn Benutzer Daten, die sie aus der Datenbank abrufen, speichern möchten, müssen sie dazu ihren Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="8b585-132">If users wish to save the data they retrieve from the database, they must do this in their code.</span></span>  
  
-   <span data-ttu-id="8b585-133">SQLXML ermöglicht es Benutzern, eine beliebige SQL-Abfrage für die Datenbank auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8b585-133">SQLXML allows users to execute any SQL query they like against the database.</span></span> <span data-ttu-id="8b585-134">Diese Funktion sollte nie einer unsicheren oder unkontrollierten Quelle verfügbar gemacht werden, da es im Grunde eine Öffnung der SQL-Datenbank ohne Bereitstellung für die Benutzer bedeutet.</span><span class="sxs-lookup"><span data-stu-id="8b585-134">This functionality should never be exposed to an unsecure or uncontrolled source, as this is essentially opening up the SQL database without provision to any users.</span></span>  
  
-   <span data-ttu-id="8b585-135">Beim Ausführen von Updategrams übersetzt SQLXML die `updg:sync`-Blöcke in DELETE-, UPDATE- und INSERT-Befehle für die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Instanz.</span><span class="sxs-lookup"><span data-stu-id="8b585-135">When executing Updategrams, SQLXML translates the `updg:sync` blocks into DELETE, UPDATE, and INSERT commands against the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="8b585-136">Diese Befehle beeinflussen nur vorhandene Daten.</span><span class="sxs-lookup"><span data-stu-id="8b585-136">These commands only ever affect existing data.</span></span> <span data-ttu-id="8b585-137">Von SQLXML generierte Befehle ändern nie die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="8b585-137">Commands generated by SQLXML will never alter the database.</span></span> <span data-ttu-id="8b585-138">Benutzer müssen explizite Befehle ausgeben, um die Datenbankstruktur zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8b585-138">Users must issue explicit commands to alter the database structure.</span></span> <span data-ttu-id="8b585-139">Dazu können sie sie beispielsweise in einen `sql:query`-Block einer Vorlage einschließen.</span><span class="sxs-lookup"><span data-stu-id="8b585-139">For example, by including them in a `sql:query` block of a template.</span></span>  
  
-   <span data-ttu-id="8b585-140">Beim Ausführen von DiffGrams übersetzt SQLXML das DiffGram in DELETE-, UPDATE- und INSERT-Befehle für die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Instanz.</span><span class="sxs-lookup"><span data-stu-id="8b585-140">When executing DiffGrams, SQLXML translates the DiffGram into DELETE, UPDATE, and INSERT commands against the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="8b585-141">Diese Befehle beeinflussen nur vorhandene Daten.</span><span class="sxs-lookup"><span data-stu-id="8b585-141">These commands only ever affect existing data.</span></span> <span data-ttu-id="8b585-142">Von SQLXML generierte Befehle ändern nie die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="8b585-142">Commands generated by SQLXML will never alter the database.</span></span> <span data-ttu-id="8b585-143">Benutzer müssen explizite Befehle ausgeben, um die Datenbankstruktur zu ändern.</span><span class="sxs-lookup"><span data-stu-id="8b585-143">Users must issue explicit commands to alter the database structure.</span></span> <span data-ttu-id="8b585-144">Dazu können sie sie beispielsweise in einen `sql:query`-Block einer Vorlage einschließen.</span><span class="sxs-lookup"><span data-stu-id="8b585-144">For example, by including them in a `sql:query` block of a template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b585-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8b585-145">See Also</span></span>  
 [<span data-ttu-id="8b585-146">Sicherheitsüberlegungen zu SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="8b585-146">SQLXML 4.0 Security Considerations</span></span>](sqlxml-4-0-security-considerations.md)  
  
  