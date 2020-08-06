---
title: Konfigurieren und Verwalten von Thesaurusdateien für die Volltextsuche | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- full-text indexes [SQL Server], thesaurus files
- thesaurus [full-text search], configuring
- thesaurus [full-text search]
ms.assetid: 3ef96a63-8a52-45be-9a1f-265bff400e54
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 67f0a5af7be4f41ce33692e5f28ad5adf676980c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726862"
---
# <a name="configure-and-manage-thesaurus-files-for-full-text-search"></a><span data-ttu-id="1b2f7-102">Konfigurieren und Verwalten von Thesaurusdateien für die Volltextsuche</span><span class="sxs-lookup"><span data-stu-id="1b2f7-102">Configure and Manage Thesaurus Files for Full-Text Search</span></span>
  <span data-ttu-id="1b2f7-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]kann bei Volltextabfragen ein Thesaurus verwendet werden, um nach Synonymen der vom Benutzer angegebenen Begriffe zu suchen.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], full-text queries can search for synonyms of user-specified terms through the use of a thesaurus.</span></span> <span data-ttu-id="1b2f7-104">Ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] *Thesaurus* definiert Synonyme für eine bestimmte Sprache.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-104">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] *thesaurus* defines a set of synonyms for a specific language.</span></span> <span data-ttu-id="1b2f7-105">Systemadministratoren können zwei Formen von Synonymen definieren: Erweiterungssätze und Ersetzungssätze.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-105">System administrators can define two forms of synonyms: expansion sets and replacement sets.</span></span> <span data-ttu-id="1b2f7-106">Indem Sie einen Thesaurus entwickeln, der genau auf Ihre Volltextdaten abgestimmt ist, können Sie den Bereich der Volltextabfragen für diese Daten effektiv erweitern.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-106">By developing a thesaurus tailored to your full-text data, you can effectively broaden the scope of full-text queries on that data.</span></span> <span data-ttu-id="1b2f7-107">Der Thesaurusvergleich erfolgt für alle [FREETEXT](/sql/t-sql/queries/freetext-transact-sql) - und [FREETEXTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) -Abfragen sowie für alle [CONTAINS](/sql/t-sql/queries/contains-transact-sql) - und [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) -Abfragen, in denen die FORMSOF THESAURUS-Klausel angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-107">Thesaurus matching occurs for all [FREETEXT](/sql/t-sql/queries/freetext-transact-sql) and [FREETEXTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) queries and for any [CONTAINS](/sql/t-sql/queries/contains-transact-sql) and [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) queries that specify the FORMSOF THESAURUS clause.</span></span>  
  
##  <a name="basic-tasks-for-setting-up-a-thesaurus-file"></a><a name="tasks"></a><span data-ttu-id="1b2f7-108">Grundlegende Aufgaben zum Einrichten einer Thesaurusdatei</span><span class="sxs-lookup"><span data-stu-id="1b2f7-108">Basic Tasks for Setting Up a Thesaurus File</span></span>  
 <span data-ttu-id="1b2f7-109">Bevor bei Volltextsuchabfragen auf der Serverinstanz nach Synonymen in einer bestimmten Sprache gesucht werden kann, müssen Sie Thesauruszuordnungen (Synonyme) für diese Sprache definieren.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-109">Before full-text search queries on your server instance can look for synonyms in a given language, you must define thesaurus mappings (synonyms) for that language.</span></span> <span data-ttu-id="1b2f7-110">Jeder Thesaurus muss manuell konfiguriert werden, um Folgendes zu definieren:</span><span class="sxs-lookup"><span data-stu-id="1b2f7-110">Each thesaurus must be manually configured to define the following:</span></span>  
  
-   <span data-ttu-id="1b2f7-111">Einstellung für diakritische Zeichen</span><span class="sxs-lookup"><span data-stu-id="1b2f7-111">Diacritics setting</span></span>  
  
     <span data-ttu-id="1b2f7-112">Bei einem bestimmten Thesaurus sind alle Suchmuster entweder sensibel oder nicht für diakritische Zeichen wie z. b. Tilde ( **~** ), akute Akzente (**??**) oder Umlaut (**??**). (das heißt, Unterscheidung nach *Akzent* oder *Akzent*).</span><span class="sxs-lookup"><span data-stu-id="1b2f7-112">For a given thesaurus, all search patterns are either sensitive or insensitive to diacritical marks such as a tilde (**~**), acute accent mark (**??**), or umlaut (**??**) (that is, *accent sensitive* or *accent insensitive*).</span></span> <span data-ttu-id="1b2f7-113">Nehmen Sie beispielsweise an, dass Sie das Muster "CAF?" angeben.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-113">For example, suppose you specify the pattern "caf??"</span></span> <span data-ttu-id="1b2f7-114">das in einer Volltextabfrage durch andere Muster ersetzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-114">to be replaced by other patterns in a full-text query.</span></span> <span data-ttu-id="1b2f7-115">Wenn der Thesaurus keine Unterscheidung nach Akzent hat, ersetzt die Volltextsuche die Muster "CAF?".</span><span class="sxs-lookup"><span data-stu-id="1b2f7-115">If the thesaurus is accent-insensitive, full-text search replaces the patterns "caf??"</span></span> <span data-ttu-id="1b2f7-116">und „cafe“.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-116">and "cafe".</span></span> <span data-ttu-id="1b2f7-117">Wenn der Thesaurus nach Akzent unterscheidet, ersetzt die Volltextsuche nur das Muster "CAF?".</span><span class="sxs-lookup"><span data-stu-id="1b2f7-117">If the thesaurus is accent-sensitive, full-text search replaces only the pattern "caf??".</span></span> <span data-ttu-id="1b2f7-118">Standardmäßig wird bei einem Thesaurus nicht nach Akzent unterschieden.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-118">By default, a thesaurus is accent-insensitive.</span></span>  
  
-   <span data-ttu-id="1b2f7-119">Erweiterungssatz</span><span class="sxs-lookup"><span data-stu-id="1b2f7-119">Expansion set</span></span>  
  
     <span data-ttu-id="1b2f7-120">Ein Erweiterungssatz enthält eine Gruppe von Synonymen wie "writer", "author" und "journalist", die bei einer Volltextabfrage ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-120">An expansion set contains a group of synonyms such as "writer", "author", and "journalist" that are substituted for one another by a full-text query.</span></span> <span data-ttu-id="1b2f7-121">Abfragen, die eine Übereinstimmung für ein beliebiges Synonym in einem Erweiterungssatz enthalten, werden erweitert, um jedes andere Synonym im Erweiterungssatz einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-121">Queries that contain a match for any synonym in an expansion set are expanded to include every other synonym in the expansion set.</span></span>  
  
     <span data-ttu-id="1b2f7-122">Weitere Informationen finden Sie unter "XML-Struktur eines Erweiterungssatzes" weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-122">For more information, see "XML Structure of an Expansion Set," later in this topic.</span></span>  
  
-   <span data-ttu-id="1b2f7-123">Ersetzungssatz</span><span class="sxs-lookup"><span data-stu-id="1b2f7-123">Replacement set</span></span>  
  
     <span data-ttu-id="1b2f7-124">Ein Ersetzungssatz enthält ein durch einen Substitutionssatz zu ersetzendes Textmuster.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-124">A replacement set contains a text pattern to be replaced by a substitution set.</span></span> <span data-ttu-id="1b2f7-125">Ein Beispiel dafür finden Sie im Abschnitt "XML-Struktur eines Ersetzungssatzes" weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-125">For an example, see the section "XML Structure of a Replacement Set" later in this topic.</span></span>  
  
  
##  <a name="initial-content-of-the-thesaurus-files"></a><a name="initial_thesaurus_files"></a><span data-ttu-id="1b2f7-126">Ursprünglicher Inhalt der Thesaurusdateien</span><span class="sxs-lookup"><span data-stu-id="1b2f7-126">Initial Content of the Thesaurus Files</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1b2f7-127">stellt einen Satz von XML-Thesaurusdateien bereit, und zwar eine für jede unterstützte Sprache.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-127">provides a set of XML thesaurus files, one for each supported language.</span></span> <span data-ttu-id="1b2f7-128">Diese Dateien sind im Wesentlichen leer.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-128">These files are essentially empty.</span></span> <span data-ttu-id="1b2f7-129">Sie enthalten nur die XML-Hauptstruktur, die alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Thesaurusdateien aufweisen, sowie einen auskommentierten Beispielthesaurus.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-129">They contain only the top-level XML structure that is common to all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] thesauruses and a commented-out sample thesaurus.</span></span>  
  
 <span data-ttu-id="1b2f7-130">Alle im Lieferumfang von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] enthaltenen Thesaurusdateien enthalten folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="1b2f7-130">The thesaurus files that are released with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] all contain the following XML code:</span></span>  
  
```  
<XML ID="Microsoft Search Thesaurus">  
  
<!--  Commented out  
  
    <thesaurus xmlns="x-schema:tsSchema.xml">  
<diacritics_sensitive>0</diacritics_sensitive>  
        <expansion>  
            <sub>Internet Explorer</sub>  
            <sub>IE</sub>  
            <sub>IE5</sub>  
        </expansion>  
        <replacement>  
            <pat>NT5</pat>  
            <pat>W2K</pat>  
            <sub>Windows 2012</sub>  
        </replacement>  
        <expansion>  
            <sub>run</sub>  
            <sub>jog</sub>  
        </expansion>  
    </thesaurus>  
-->  
</XML>  
```  
  
  
##  <a name="location-of-the-thesaurus-files"></a><a name="location"></a><span data-ttu-id="1b2f7-131">Speicherort der Thesaurusdateien</span><span class="sxs-lookup"><span data-stu-id="1b2f7-131">Location of the Thesaurus Files</span></span>  
 <span data-ttu-id="1b2f7-132">Der Standardspeicherort der Thesaurusdateien lautet folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="1b2f7-132">The default location of the thesaurus files is:</span></span>  
  
 <span data-ttu-id="1b2f7-133">*<SQL_Server_data_files_path>* \mssql12. mssqlserver\mssql\ftdata</span><span class="sxs-lookup"><span data-stu-id="1b2f7-133">*<SQL_Server_data_files_path>* \MSSQL12.MSSQLSERVER\MSSQL\FTDATA</span></span>\  
  
 <span data-ttu-id="1b2f7-134">Dieser Standardspeicherort enthält die folgenden Dateien:</span><span class="sxs-lookup"><span data-stu-id="1b2f7-134">This default location contains the following files:</span></span>  
  
-   <span data-ttu-id="1b2f7-135">Sprachspezifische Thesaurusdateien</span><span class="sxs-lookup"><span data-stu-id="1b2f7-135">Language-specific thesaurus files</span></span>  
  
     <span data-ttu-id="1b2f7-136">Beim Setup werden am oben genannten Speicherort leere Thesaurusdateien installiert.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-136">During setup, empty thesaurus files are installed in the above location.</span></span> <span data-ttu-id="1b2f7-137">Für jede unterstützte Sprache wird eine separate Datei bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-137">A separate file is provided for each supported language.</span></span> <span data-ttu-id="1b2f7-138">Ein Systemadministrator kann diese Dateien anpassen.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-138">A system administrator can customize these files.</span></span>  
  
     <span data-ttu-id="1b2f7-139">Die Standarddateinamen der Thesaurusdateien haben das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="1b2f7-139">The default file names of the thesaurus files use following format:</span></span>  
  
     <span data-ttu-id="1b2f7-140">' ts ' + \<three-letter language-abbreviation> + '. xml '</span><span class="sxs-lookup"><span data-stu-id="1b2f7-140">'ts' + \<three-letter language-abbreviation> + '.xml'</span></span>  
  
     <span data-ttu-id="1b2f7-141">Der Name der Thesaurusdatei für eine bestimmte Sprache ist in der Registrierung im folgenden Wert angegeben: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<Instanzname>\MSSearch\\<Sprachcode>.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-141">The name of the thesaurus file for a given language is specified in the registry in the following value HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<instance-name>\MSSearch\\<language-abbrev>.</span></span>  
  
-   <span data-ttu-id="1b2f7-142">Die globale Thesaurusdatei</span><span class="sxs-lookup"><span data-stu-id="1b2f7-142">The global thesaurus file</span></span>  
  
     <span data-ttu-id="1b2f7-143">Eine leere globale Thesaurusdatei mit dem Namen „tsGlobal.xml“.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-143">An empty global thesaurus file, tsGlobal.xml.</span></span>  
  
 <span data-ttu-id="1b2f7-144">Sie können den Speicherort und den Namen einer Thesaurusdatei ändern, indem Sie den zugehörigen Registrierungsschlüssel ändern.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-144">You can change the location and names of a thesaurus file by changing its registry key.</span></span> <span data-ttu-id="1b2f7-145">Der Speicherort der Thesaurusdatei für jede einzelne Sprache ist im folgenden Wert in der Registrierung angegeben:</span><span class="sxs-lookup"><span data-stu-id="1b2f7-145">For each language, the location of the thesaurus file is specified in the following value in the registry:</span></span>  
  
 <span data-ttu-id="1b2f7-146">HKLM/Software/Microsoft/Microsoft SQL Server/ \<instance name> /MSSearch/Language/ \<language-abbreviation> /TsaurusFile</span><span class="sxs-lookup"><span data-stu-id="1b2f7-146">HKLM/SOFTWARE/Microsoft/Microsoft SQL Server/\<instance name>/MSSearch/Language/\<language-abbreviation>/TsaurusFile</span></span>  
  
 <span data-ttu-id="1b2f7-147">Die globale Thesaurusdatei entspricht der neutralen Sprache mit LCID 0.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-147">The global thesaurus file corresponds to the Neutral language with LCID 0.</span></span> <span data-ttu-id="1b2f7-148">Dieser Wert kann nur von Administratoren geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-148">This value can be changed by administrators only.</span></span>  
  
  
##  <a name="how-queries-use-thesaurus-files"></a><a name="how_queries_use_tf"></a><span data-ttu-id="1b2f7-149">Verwenden von Thesaurusdateien in Abfragen</span><span class="sxs-lookup"><span data-stu-id="1b2f7-149">How Queries Use Thesaurus Files</span></span>  
 <span data-ttu-id="1b2f7-150">Für jede Thesaurusabfrage wird zuerst ein sprachspezifischer Thesaurus und dann der globale Thesaurus verwendet.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-150">A thesaurus query uses both a language-specific thesaurus and the global thesaurus.</span></span> <span data-ttu-id="1b2f7-151">Zuerst wird die sprachspezifische Datei gesucht und (falls erforderlich) zur Verarbeitung geladen.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-151">First, the query looks up the language-specific file and loads it for processing (unless it is already loaded).</span></span> <span data-ttu-id="1b2f7-152">Die Abfrage wird um die durch die Erweiterungssatz- und Ersetzungssatz-Regeln in der Thesaurusdatei angegebenen Synonyme erweitert.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-152">The query is expanded to include the language-specific synonyms specified by the expansion set and replacement set rules in the thesaurus file.</span></span> <span data-ttu-id="1b2f7-153">Anschließend werden diese Schritte für den globalen Thesaurus wiederholt.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-153">These steps are then repeated for the global thesaurus.</span></span> <span data-ttu-id="1b2f7-154">Wenn für einen Begriff in der sprachspezifischen Thesaurusdatei bereits eine Übereinstimmung gefunden wurde, werden die globalen Synonyme des Begriffs ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-154">However, if a term is already part of a match in the language specific thesaurus file, the term is ineligible for matching in the global thesaurus.</span></span>  
  
  
##  <a name="understanding-the-structure-of-a-thesaurus-file"></a><a name="structure"></a><span data-ttu-id="1b2f7-155">Grundlegendes zur Struktur einer Thesaurusdatei</span><span class="sxs-lookup"><span data-stu-id="1b2f7-155">Understanding the Structure of a Thesaurus File</span></span>  
 <span data-ttu-id="1b2f7-156">Jede Thesaurusdatei definiert einen XML-Container, dessen ID `Microsoft Search Thesaurus` lautet, sowie einen Kommentar, `<!--` … `-->`, der einen Beispielthesaurus enthält.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-156">Each thesaurus file defines an XML container whose ID is `Microsoft Search Thesaurus`, and a comment, `<!--` ... `-->`, that contains a sample thesaurus.</span></span> <span data-ttu-id="1b2f7-157">Der Thesaurus wird in einem- \<thesaurus> Element definiert, das Beispiele für die untergeordneten Elemente enthält, die die Einstellung für diakritische Zeichen, Erweiterungs Sätze und Ersetzungs Sätze wie folgt definieren:</span><span class="sxs-lookup"><span data-stu-id="1b2f7-157">The thesaurus is defined in a \<thesaurus> element that contains samples of the child elements that define the diacritics setting, expansion sets, and replacement sets, as follows:</span></span>  
  
-   <span data-ttu-id="1b2f7-158">XML-Struktur der Einstellung für diakritische Zeichen</span><span class="sxs-lookup"><span data-stu-id="1b2f7-158">XML Structure of the Diacritical Setting</span></span>  
  
     <span data-ttu-id="1b2f7-159">Die Einstellung eines Thesaurus für diakritische Zeichen wird in einem einzelnen <diacritics_sensitive>-Element angegeben.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-159">The diacritics setting of a thesaurus is specified in a single <diacritics_sensitive> element.</span></span> <span data-ttu-id="1b2f7-160">Dieses Element enthält einen ganzzahligen Wert, der die Unterscheidung nach Akzent folgendermaßen steuert:</span><span class="sxs-lookup"><span data-stu-id="1b2f7-160">This element contains an integer value that controls accent sensitivity, as follows:</span></span>  
  
    |<span data-ttu-id="1b2f7-161">Einstellung für diakritische Zeichen</span><span class="sxs-lookup"><span data-stu-id="1b2f7-161">Diacritics Setting</span></span>|<span data-ttu-id="1b2f7-162">Wert</span><span class="sxs-lookup"><span data-stu-id="1b2f7-162">Value</span></span>|<span data-ttu-id="1b2f7-163">XML</span><span class="sxs-lookup"><span data-stu-id="1b2f7-163">XML</span></span>|  
    |------------------------|-----------|---------|  
    |<span data-ttu-id="1b2f7-164">keine Unterscheidung nach Akzent</span><span class="sxs-lookup"><span data-stu-id="1b2f7-164">Accent insensitive</span></span>|<span data-ttu-id="1b2f7-165">0</span><span class="sxs-lookup"><span data-stu-id="1b2f7-165">0</span></span>|`<diacritics_sensitive>0</diacritics_sensitive>`|  
    |<span data-ttu-id="1b2f7-166">Unterscheidung nach Akzent</span><span class="sxs-lookup"><span data-stu-id="1b2f7-166">Accent sensitive</span></span>|<span data-ttu-id="1b2f7-167">1</span><span class="sxs-lookup"><span data-stu-id="1b2f7-167">1</span></span>|`<diacritics_sensitive>1</diacritics_sensitive>`|  
  
    > [!NOTE]  
    >  <span data-ttu-id="1b2f7-168">Diese Einstellung kann nur ein einziges Mal in der Datei vorgenommen werden und gilt für alle Suchmuster in der Datei.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-168">This setting can only be applied one time in the file, and it applies to all search patterns in the file.</span></span> <span data-ttu-id="1b2f7-169">Diese Einstellung kann nicht für einzelne Muster angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-169">This setting cannot be specified for individual patterns.</span></span>  
  
-   <span data-ttu-id="1b2f7-170">XML-Struktur eines Erweiterungssatzes</span><span class="sxs-lookup"><span data-stu-id="1b2f7-170">XML Structure of an Expansion Set</span></span>  
  
     <span data-ttu-id="1b2f7-171">Jeder Erweiterungssatz ist in ein \<expansion>-Element eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-171">Each expansion set is enclosed within an \<expansion> element.</span></span> <span data-ttu-id="1b2f7-172">Innerhalb dieses Elements geben Sie eine oder mehrere Substitutionen in einem \<sub>-Element an.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-172">Within this element, you specify one or more substitutions in a \<sub> element.</span></span> <span data-ttu-id="1b2f7-173">Im Erweiterungssatz können Sie eine Gruppe von Substitutionen angeben, die Synonyme zueinander sind.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-173">In the expansion set, you can specify a group of substitutions that are synonyms of each other.</span></span>  
  
     <span data-ttu-id="1b2f7-174">Sie können beispielsweise den expansion-Abschnitt bearbeiten, um die Substitutionen "writer", "author" und "journalist" als Synonyme zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-174">For example, you can edit the expansion section to treat the substitutions "writer", "author", and "journalist" as synonyms.</span></span> <span data-ttu-id="1b2f7-175">Volltextsuchabfragen, die Übereinstimmungen in einer Substitution enthalten, werden erweitert, um alle weiteren im Erweiterungssatz angegebenen Substitutionen einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-175">full-text search queries that contain matches in one substitution are expanded to include all other substitutions specified in the expansion set.</span></span> <span data-ttu-id="1b2f7-176">Wenn Sie daher im vorherigen Beispiel eine FORMS OF THESAURUS- oder eine FREETEXT-Abfrage nach dem Wort "author" ausführen, gibt die Volltextsuche auch Suchergebnisse zurück, die die Wörter "writer" und "journalist" enthalten.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-176">Therefore, in the preceding example, when you issue a FORMS OF THESAURUS or a FREETEXT query for the word "author", full-text search also returns search results containing the words "writer" and "journalist".</span></span>  
  
     <span data-ttu-id="1b2f7-177">Der Erweiterungssatzabschnitt für das oben genannte Beispiel würde wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="1b2f7-177">This is what the expansion set section would look like for the above example:</span></span>  
  
    ```  
    <expansion>  
            <sub>writer</sub>  
            <sub>author</sub>  
            <sub>journalist</sub>  
    </expansion>  
    ```  
  
-   <span data-ttu-id="1b2f7-178">XML-Struktur eines Ersetzungssatzes</span><span class="sxs-lookup"><span data-stu-id="1b2f7-178">XML Structure of a Replacement Set</span></span>  
  
     <span data-ttu-id="1b2f7-179">Jeder Ersetzungssatz ist in ein \<replacement>-Element eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-179">Each replacement set is enclosed within a \<replacement> element.</span></span> <span data-ttu-id="1b2f7-180">Innerhalb dieses Elements können Sie ein oder mehrere Muster in einem \<pat>-Element und keine oder beliebig viele Substitutionen in \<sub>-Elementen (einem pro Synonym) angeben.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-180">Within this element you can specify one or more patterns in a \<pat> element and zero or more substitutions in \<sub> elements, one per synonym.</span></span> <span data-ttu-id="1b2f7-181">Sie können ein durch einen Substitutionssatz zu ersetzendes Muster angeben.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-181">You can specify a pattern to be replaced by a substitution set.</span></span> <span data-ttu-id="1b2f7-182">Muster und Substitutionen können ein Wort oder eine Wortfolge enthalten.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-182">Patterns and substitutions can contain a word, or a sequence of words.</span></span> <span data-ttu-id="1b2f7-183">Wenn für ein Muster keine Substitution angegeben wird, ist die Wirkung dieselbe, als würde das Muster aus der Benutzerabfrage entfernt.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-183">If there is no substitution specified for a pattern, it has the effect of removing the pattern from the user query.</span></span>  
  
     <span data-ttu-id="1b2f7-184">Angenommen, Sie möchten, dass Abfragen nach "Win8" (das Muster) durch "Windows Server 2012" oder "Windows 8.0" (die Substitutionen) ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-184">For example, suppose you want queries for "Win8", the pattern, to be replaced by "Windows Server 2012" or "Windows 8.0", the substitutions.</span></span> <span data-ttu-id="1b2f7-185">Wenn Sie eine Volltextabfrage nach "Win8" ausführen, gibt die Volltextsuche nur Suchergebnisse zurück, die "Windows Server 2012" oder "Windows 8.0" enthalten.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-185">If you run a full-text query for "Win8", full-text search only returns search results containing "Windows Server 2012" or "Windows 8.0".</span></span> <span data-ttu-id="1b2f7-186">Sie gibt keine Ergebnisse zurück, die "Win8" enthalten.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-186">It does not return results containing "Win8".</span></span> <span data-ttu-id="1b2f7-187">Dies liegt daran, dass das Muster "Win8" durch die Muster "Windows Server 2012" und "Windows 8.0" "ersetzt" wurde.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-187">This is because the pattern "Win8" has been "replaced" by the patterns "Windows Server 2012" and "Windows 8.0".</span></span>  
  
     <span data-ttu-id="1b2f7-188">Der Ersetzungssatzabschnitt für das oben genannte Beispiel würde wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="1b2f7-188">This is what the replacement set section would look like for the above example:</span></span>  
  
    ```  
    <replacement>  
            <pat>Win8</pat>  
            <sub>Windows Server 2012</sub>  
            <sub>Windows 8.0</sub>  
    </replacement>  
    ```  
  
     <span data-ttu-id="1b2f7-189">Wenn zwei Ersetzungssätze mit ähnlichen Mustern für die Übereinstimmung verwendet werden, hat der längere der beiden Vorrang.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-189">If you have two replacement sets with similar patterns being matched, the longer of the two takes precedence.</span></span> <span data-ttu-id="1b2f7-190">Wenn Sie beispielsweise eine FORMS OF THESAURUS-Abfrage nach "Internet Explorer online community" ausführen und die folgenden Ersetzungssätze haben, hat der "Internet Explorer"-Ersetzungssatz Vorrang vor dem "Internet"-Ersetzungssatz.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-190">For example, if you run a FORMS OF THESAURUS query for "Internet Explorer online community" and you have the following replacement sets, the "Internet Explorer" replacement set takes precedence over the "Internet" replacement set.</span></span> <span data-ttu-id="1b2f7-191">Die Abfrage wird demzufolge als "IE online community" oder "IE 9 online community" verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-191">The query will therefore be processed as "IE online community" or "IE 9 online community".</span></span>  
  
    ```  
    <replacement>  
             <pat>Internet</pat>  
             <sub>intranet</sub>  
    </replacement>  
    ```  
  
     <span data-ttu-id="1b2f7-192">and</span><span class="sxs-lookup"><span data-stu-id="1b2f7-192">and</span></span>  
  
    ```  
    <replacement>  
             <pat>Internet Explorer</pat>  
             <sub>IE</sub>  
             <sub>IE 9</sub>  
    </replacement>  
    ```  
  
  
##  <a name="working-with-thesaurus-files"></a><a name="working_with_thesaurus_files"></a><span data-ttu-id="1b2f7-193">Arbeiten mit Thesaurusdateien</span><span class="sxs-lookup"><span data-stu-id="1b2f7-193">Working with Thesaurus Files</span></span>  
 <span data-ttu-id="1b2f7-194">**So bearbeiten Sie eine Thesaurusdatei**</span><span class="sxs-lookup"><span data-stu-id="1b2f7-194">**To edit a thesaurus file**</span></span>  
  
-   [<span data-ttu-id="1b2f7-195">Bearbeiten einer Thesaurusdatei</span><span class="sxs-lookup"><span data-stu-id="1b2f7-195">Editing a Thesaurus File</span></span>](#editing)  
  
 <span data-ttu-id="1b2f7-196">**So laden Sie eine aktualisierte Thesaurusdatei**</span><span class="sxs-lookup"><span data-stu-id="1b2f7-196">**To load an updated thesaurus file**</span></span>  
  
-   [<span data-ttu-id="1b2f7-197">sp_fulltext_load_thesaurus_file &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1b2f7-197">sp_fulltext_load_thesaurus_file &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-fulltext-load-thesaurus-file-transact-sql)  
  
 <span data-ttu-id="1b2f7-198">**So zeigen Sie das Tokenisierungsergebnis einer Kombination aus Wörtertrennung, Thesaurus und Stoplisten an**</span><span class="sxs-lookup"><span data-stu-id="1b2f7-198">**To view the tokenization result of a word breaker, thesaurus, and stoplist combination**</span></span>  
  
-   [<span data-ttu-id="1b2f7-199">sys. dm_fts_parser &#40;Transact-SQL-&#41;</span><span class="sxs-lookup"><span data-stu-id="1b2f7-199">sys.dm_fts_parser &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-parser-transact-sql)  
  
  
##  <a name="editing-a-thesaurus-file"></a><a name="editing"></a><span data-ttu-id="1b2f7-200">Bearbeiten einer Thesaurusdatei</span><span class="sxs-lookup"><span data-stu-id="1b2f7-200">Editing a Thesaurus File</span></span>  
 <span data-ttu-id="1b2f7-201">Der Thesaurus für eine bestimmte Sprache kann durch Bearbeiten der zugehörigen Thesaurusdatei (einer XML-Datei) konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-201">The thesaurus for a given language can be configured by editing its thesaurus file (an XML file).</span></span> <span data-ttu-id="1b2f7-202">Beim Setup werden leere Thesaurusdateien installiert, die nur den \<xml> Container und ein auskommentiertes Beispiel \<thesaurus> Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-202">During setup, empty thesaurus files that contain only the \<xml> container and a commented-out sample \<thesaurus> element are installed.</span></span> <span data-ttu-id="1b2f7-203">Damit voll Text Such Abfragen, bei denen nach Synonymen gesucht wird, ordnungsgemäß funktionieren, müssen Sie ein tatsächliches \<thesaurus> Element erstellen, das eine Gruppe von Synonymen definiert.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-203">In order for full-text search queries that look for synonyms to work properly, you must create an actual \<thesaurus> element that defines a set of synonyms.</span></span> <span data-ttu-id="1b2f7-204">Sie können zwei Formen von Synonymen definieren, nämlich Erweiterungssätze und Ersetzungssätze.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-204">You can define two forms of synonyms, expansion sets and replacement sets.</span></span>  
  
 <span data-ttu-id="1b2f7-205">**Einschränkungen für Thesaurusdateien**</span><span class="sxs-lookup"><span data-stu-id="1b2f7-205">**Restrictions for thesaurus files**</span></span>  
  
 <span data-ttu-id="1b2f7-206">Beim Bearbeiten einer Thesaurusdatei gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="1b2f7-206">The following restrictions apply to editing a thesaurus file:</span></span>  
  
-   <span data-ttu-id="1b2f7-207">Nur Systemadministratoren können Thesaurusdateien aktualisieren, ändern und löschen.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-207">Only system administrators can update, modify, or delete thesaurus files.</span></span>  
  
-   <span data-ttu-id="1b2f7-208">Wenn Sie Thesaurusdateien mithilfe von Text-Editor-Tools bearbeiten, müssen die Dateien im Unicode-Format gespeichert und Bytereihenfolgemarken (Byte Order Marks, BOMs) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-208">When editing thesaurus files using text editor tools, the files must be saved in Unicode format, and Byte Order Marks must be specified.</span></span>  
  
-   <span data-ttu-id="1b2f7-209">Thesauruseinträge dürfen nicht leer sein oder eine Wörtertrennung zu einer leeren Zeichenfolge aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-209">Thesaurus entries cannot be empty or word break to an empty string.</span></span>  
  
-   <span data-ttu-id="1b2f7-210">Ausdrücke in der Thesaurusdatei dürfen aus höchstens 512 Zeichen bestehen.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-210">Phrases in the thesaurus file must be no longer than 512 characters.</span></span>  
  
-   <span data-ttu-id="1b2f7-211">Ein Thesaurus darf in den \<sub>-Einträgen von Erweiterungssätzen und in den \<pat>-Elementen von Ersetzungssätzen keine doppelten Einträge enthalten.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-211">A thesaurus must not contain any duplicate entries among the \<sub> entries of expansion sets and the \<pat> elements of replacement sets.</span></span>  
  
 <span data-ttu-id="1b2f7-212">**Empfehlungen für Thesaurusdateien**</span><span class="sxs-lookup"><span data-stu-id="1b2f7-212">**Recommendations for thesaurus files**</span></span>  
  
 <span data-ttu-id="1b2f7-213">Einträge in der Thesaurusdatei sollten keine Sonderzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-213">We recommend that entries in the thesaurus file contain no special characters.</span></span> <span data-ttu-id="1b2f7-214">Dies wird deshalb empfohlen, weil die Wörtertrennung auf Sonderzeichen sehr fein reagiert.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-214">This is because word breakers have subtle behaviors with respect to special characters.</span></span> <span data-ttu-id="1b2f7-215">Wenn ein Thesauruseintrag Sonderzeichen enthält, kann die Verwendung der Wörtertrennung in Kombination mit diesem Eintrag schwer erkennbare Auswirkungen auf das Verhalten einer Volltextabfrage haben.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-215">If a thesaurus entry contains any special characters, word breakers used in combination with that entry can have subtle behavioral implications for a full-text query.</span></span>  
  
 <span data-ttu-id="1b2f7-216">Es wird empfohlen, in \<sub>-Einträgen keine Stoppwörter zu verwenden, da Stoppwörter im Volltextindex ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-216">We recommend that \<sub> entries contain no stopwords since stopwords are omitted from the full-text index.</span></span> <span data-ttu-id="1b2f7-217">Abfragen werden erweitert, um die \<sub>-Einträge in einer Thesaurusdatei einzubeziehen, und wenn ein \<sub>-Eintrag Stoppwörter enthält, nimmt die Abfrage unnötigerweise an Größe zu.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-217">Queries are expanded to include the \<sub> entries from a thesaurus file, and if a \<sub> entry contains stopwords, query size increases unnecessarily.</span></span>  
  
#### <a name="to-edit-a-thesaurus-file"></a><span data-ttu-id="1b2f7-218">So bearbeiten Sie eine Thesaurusdatei</span><span class="sxs-lookup"><span data-stu-id="1b2f7-218">To edit a thesaurus file</span></span>  
  
1.  <span data-ttu-id="1b2f7-219">Öffnen Sie die Thesaurusdatei in Editor.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-219">Open the thesaurus file in Notepad.</span></span>  
  
2.  <span data-ttu-id="1b2f7-220">Wenn Sie die Thesaurusdatei zum ersten Mal bearbeiten, entfernen Sie die folgenden Kommentarzeilen am Anfang bzw. Ende der Datei:</span><span class="sxs-lookup"><span data-stu-id="1b2f7-220">If you are editing the thesaurus file for the first time, remove the following comment lines at the beginning and end of the file, respectively:</span></span>  
  
    ```  
    <!--Commented out  
    -->  
    ```  
  
3.  <span data-ttu-id="1b2f7-221">Fügen Sie einen Ersetzungs- oder Erweiterungssatz hinzu, ändern oder löschen Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-221">Add, modify, or delete a replacement set, or expansion set.</span></span>  
  
4.  <span data-ttu-id="1b2f7-222">Speichern Sie die Datei, und schließen Sie Editor.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-222">Save the file and close Notepad.</span></span>  
  
5.  <span data-ttu-id="1b2f7-223">Verwenden Sie [sp_fulltext_load_thesaurus_file](/sql/relational-databases/system-stored-procedures/sp-fulltext-load-thesaurus-file-transact-sql) , um den Inhalt der Thesaurusdatei in tempdb zu laden, und geben Sie den Gebietsschemabezeichner (LCID) an, der der Sprache der Thesaurusdatei entspricht.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-223">Use [sp_fulltext_load_thesaurus_file](/sql/relational-databases/system-stored-procedures/sp-fulltext-load-thesaurus-file-transact-sql) to load the content of the thesaurus file into tempdb, specifying the local identifier (LCID) that corresponds to the language of the thesaurus file.</span></span> <span data-ttu-id="1b2f7-224">So lautet z. B. für die englische Thesaurusdatei "tsenu.xml" der LCID 1033.</span><span class="sxs-lookup"><span data-stu-id="1b2f7-224">For example, for the English thesaurus file, tsenu.xml, the corresponding LCID is 1033.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    EXEC sys.sp_fulltext_load_thesaurus_file 1033;  
    GO  
    ```  
  
  
## <a name="see-also"></a><span data-ttu-id="1b2f7-225">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1b2f7-225">See Also</span></span>  
 <span data-ttu-id="1b2f7-226">[CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1b2f7-226">[CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql) </span></span>  
 <span data-ttu-id="1b2f7-227">[CONTAINSTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/containstable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1b2f7-227">[CONTAINSTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/containstable-transact-sql) </span></span>  
 <span data-ttu-id="1b2f7-228">[FREETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/freetext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1b2f7-228">[FREETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/freetext-transact-sql) </span></span>  
 <span data-ttu-id="1b2f7-229">[FREETEXTTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/freetexttable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1b2f7-229">[FREETEXTTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/freetexttable-transact-sql) </span></span>  
 [<span data-ttu-id="1b2f7-230">Volltextsuche</span><span class="sxs-lookup"><span data-stu-id="1b2f7-230">Full-Text Search</span></span>](full-text-search.md)  
  
  
