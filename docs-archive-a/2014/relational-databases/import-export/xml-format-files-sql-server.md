---
title: XML-Formatdateien (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- format files [SQL Server], XML format files
- bulk importing [SQL Server], format files
- XML format files [SQL Server]
ms.assetid: 69024aad-eeea-4187-8fea-b49bc2359849
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7cc1e8de30fa582898ef8516b9767dec14c4fa81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620876"
---
# <a name="xml-format-files-sql-server"></a><span data-ttu-id="c4c3e-102">XML-Formatdateien (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c4c3e-102">XML Format Files (SQL Server)</span></span>
  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="c4c3e-103">stellt ein XML-Schema bereit, das die Syntax für das Schreiben von *XML-Formatdateien* definiert, die zum Übertragen von Daten in eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Tabelle per Massenimport verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-103">provides an XML schema that defines syntax for writing *XML format files* to use for bulk importing data into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="c4c3e-104">XML-Formatdateien müssen sich an dieses Schema halten, das in XSDL (XML Schema Definition Language) definiert ist.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-104">XML format files must adhere to this schema, which is defined in the XML Schema Definition Language (XSDL).</span></span> <span data-ttu-id="c4c3e-105">XML-Formatdateien werden nur unterstützt, wenn die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Tools zusammen mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client installiert werden.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-105">XML format files are only supported when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tools are installed together with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 <span data-ttu-id="c4c3e-106">Eine XML-Formatdatei kann mit dem Befehl **bcp**, einer BULK INSERT-Anweisung oder einer INSERT ... SELECT \* FROM OPENROWSET(BULK...)-Anweisung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-106">You can use an XML format file with a **bcp** command, BULK INSERT statement, or INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement.</span></span> <span data-ttu-id="c4c3e-107">Mithilfe des **bcp** -Befehls können Sie automatisch eine XML-Formatdatei für eine Tabelle generieren. Weitere Informationen finden Sie unter [bcp Utility](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="c4c3e-107">The **bcp** command allows you to automatically generate an XML format file for a table; for more information, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c4c3e-108">Zwei Typen von Formatdateien werden zum Massenexportieren und -importieren unterstützt: *Nicht-XML-Formatdateien* und *XML-Formatdateien*.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-108">Two types of format files are supported for bulk exporting and importing: *non-XML format files* and *XML format files*.</span></span> <span data-ttu-id="c4c3e-109">XML-Formatdateien bieten eine flexible und leistungsfähige Alternative zu Nicht-XML-Formatdateien.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-109">XML format files provide a flexible and powerful alternative to non-XML format files.</span></span> <span data-ttu-id="c4c3e-110">Informationen zu Nicht-XML-Formatdateien finden Sie unter [Nicht-XML-Formatdateien &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c4c3e-110">For information about non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  

  
##  <a name="benefits-of-xml-format-files"></a><a name="BenefitsOfXmlFFs"></a> <span data-ttu-id="c4c3e-111">Vorteile von XML-Formatdateien</span><span class="sxs-lookup"><span data-stu-id="c4c3e-111">Benefits of XML Format Files</span></span>  
  
-   <span data-ttu-id="c4c3e-112">XML-Formatdateien sind selbstbeschreibend, wodurch das Lesen, Erstellen und Erweitern erleichtert wird.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-112">XML format files are self-describing, making them easy to read, create, and extend.</span></span> <span data-ttu-id="c4c3e-113">Sie können vom Benutzer gelesen werden, sodass dieser nachvollziehen kann, wie Daten bei Massenvorgängen interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-113">They are human readable, making it easy to understand how data is interpreted during bulk operations.</span></span>  
  
-   <span data-ttu-id="c4c3e-114">XML-Formatdateien enthalten die Datentypen von Zielspalten.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-114">XML format files contain the data types of target columns.</span></span>  <span data-ttu-id="c4c3e-115">Die XML-Codierung enthält eine klare Beschreibung der Datentypen und Datenelemente der Datendatei sowie der Zuordnung zwischen den Datenelementen und den Tabellenspalten.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-115">The XML encoding clearly describes the data types and data elements of the data file and also the mapping between data elements and table columns.</span></span>  
  
     <span data-ttu-id="c4c3e-116">Dies ermöglicht die Trennung zwischen der Darstellungsweise von Daten in den Datendateien und der Zuordnung des betreffenden Datentyps für jedes Feld in der Datei.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-116">This enables separation between how data is represented in the data file and what data type is associated with each field in the file.</span></span> <span data-ttu-id="c4c3e-117">Wenn z. B. eine Datendatei eine Zeichendarstellung der Daten enthält, geht der entsprechende SQL-Spaltentyp verloren.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-117">For example, if a data file contains a character representation of the data, the corresponding SQL column type is lost.</span></span>  
  
-   <span data-ttu-id="c4c3e-118">Eine XML-Formatdatei ermöglicht das Laden eines Felds aus einer Datendatei, das einen einzigen LOB-Datentyp (Large Object) enthält.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-118">An XML format file allows for loading of a field that contains a single large object (LOB) data type from a data file.</span></span>  
  
-   <span data-ttu-id="c4c3e-119">Eine XML-Formatdatei kann erweitert werden und bleibt dennoch mit früheren Versionen kompatibel.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-119">An XML format file can be enhanced yet remain compatible with its earlier versions.</span></span> <span data-ttu-id="c4c3e-120">Darüber hinaus erleichtert die Übersichtlichkeit der XML-Codierung die Erstellung mehrerer Formatdateien für eine bestimmte Datendatei.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-120">Furthermore, the clarity of XML encoding facilitates the creation of multiple format files for a given data file.</span></span> <span data-ttu-id="c4c3e-121">Dies ist von Nutzen, wenn Sie alle oder einige Datenfelder den Spalten in verschiedenen Tabellen oder Sichten zuordnen müssen.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-121">This is useful if you have to map all or some of the data fields to columns in different tables or views.</span></span>  
  
-   <span data-ttu-id="c4c3e-122">Die XML-Syntax einer Formatdatei ist unabhängig von der Richtung des Vorgangs, die Syntax ist also für Massenexport und Massenimport identisch.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-122">The XML syntax is independent of the direction of the operation; that is, the syntax is the same for bulk export and bulk import.</span></span>  
  
-   <span data-ttu-id="c4c3e-123">Sie können XML-Formatdateien verwenden, um Massenimporte von Daten in Tabellen bzw. nicht partitionierte Sichten oder Massenexporte von Daten auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-123">You can use XML format files to bulk import data into tables or non-partitioned views and to bulk export data.</span></span>  
  
-   <span data-ttu-id="c4c3e-124">Bei einer OPENROWSET (BULK...)-Funktion ist die Angabe einer Zieltabelle optional.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-124">For the OPENROWSET(BULK...) function specifying a target table is optional.</span></span> <span data-ttu-id="c4c3e-125">Das liegt daran, dass die Funktion die XML-Formatdatei zum Lesen von Daten aus einer Datendatei benötigt.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-125">This is because the function relies on the XML format file to read data from a data file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c4c3e-126">Beim **bcp** -Befehl und der BULK INSERT-Anweisung ist eine Zieltabelle erforderlich, die mithilfe der Zieltabellenspalten die Typkonvertierung durchführt.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-126">A target table is necessary with the **bcp** command and the BULK INSERT statement, which uses the target table columns to do the type conversion.</span></span>  
  
##  <a name="structure-of-xml-format-files"></a><a name="StructureOfXmlFFs"></a> <span data-ttu-id="c4c3e-127">Struktur von XML-Formatdateien</span><span class="sxs-lookup"><span data-stu-id="c4c3e-127">Structure of XML Format Files</span></span>  
 <span data-ttu-id="c4c3e-128">XML-Formatdateien definieren, ebenso wie Nicht-XML-Formatdateien, das Format und die Struktur der Datenfelder in einer Datendatei und ordnen diese Datenfelder den Spalten in einer einzigen Zieltabelle zu.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-128">Like a non-XML format file, an XML format file defines the format and structure of the data fields in a data file and maps those data fields to columns in a single target table.</span></span>  
  
 <span data-ttu-id="c4c3e-129">Eine XML-Formatdatei besteht aus zwei Hauptkomponenten: \<RECORD> und \<ROW>:</span><span class="sxs-lookup"><span data-stu-id="c4c3e-129">An XML format file possesses two main components, \<RECORD> and \<ROW>:</span></span>  
  
-   <span data-ttu-id="c4c3e-130">\<RECORD> beschreibt die Daten so, wie sie in der Datendatei gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-130">\<RECORD> describes the data as it is stored in the data file.</span></span>  
  
     <span data-ttu-id="c4c3e-131">Jedes \<RECORD>-Element enthält ein oder mehrere \<FIELD>-Elemente.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-131">Each \<RECORD> element contains a set of one or more \<FIELD> elements.</span></span> <span data-ttu-id="c4c3e-132">Diese Elemente entsprechen den Feldern in der Datendatei.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-132">These elements correspond to fields in the data file.</span></span> <span data-ttu-id="c4c3e-133">Die Basissyntax lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c4c3e-133">The basic syntax is as follows:</span></span>  
  
     \<RECORD>  
  
     <span data-ttu-id="c4c3e-134">\<FIELD .../> [ ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="c4c3e-134">\<FIELD .../> [ ...*n* ]</span></span>  
  
     \</RECORD>  
  
     <span data-ttu-id="c4c3e-135">Jedes \<FIELD>-Element beschreibt den Inhalt eines bestimmten Datenfelds.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-135">Each \<FIELD> element describes the contents of a specific data field.</span></span> <span data-ttu-id="c4c3e-136">Ein Feld kann jeweils nur einer Spalte in der Tabelle zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-136">A field can only be mapped to one column in the table.</span></span> <span data-ttu-id="c4c3e-137">Nicht alle Felder müssen Spalten zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-137">Not all fields need to be mapped to columns.</span></span>  
  
     <span data-ttu-id="c4c3e-138">Ein Feld in einer Datendatei kann eine feste bzw. variable Länge aufweisen oder durch Zeichen abgeschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-138">A field in a data file can be either of fixed/variable length or character terminated.</span></span> <span data-ttu-id="c4c3e-139">Ein *Feldwert* kann als ein Zeichen (mit Einzelbytedarstellung), als ein Doppelbytezeichen (mit Unicode-Doppelbytedarstellung), als ein systemeigenes Datenbankformat oder als ein Dateiname dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-139">A *field value* can be represented as: a character (using single-byte representation), a wide character (using Unicode two-byte representation), native database format, or a file name.</span></span> <span data-ttu-id="c4c3e-140">Wird ein Feldwert als Dateiname dargestellt, verweist der Dateiname auf die Datei, die den Wert einer BLOB-Spalte in der Zieltabelle enthält.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-140">If a field value is represented as a file name, the file name points to the file that contains the value of a BLOB column in the target table.</span></span>  
  
-   <span data-ttu-id="c4c3e-141">\<ROW> beschreibt, wie aus einer Datendatei Datenzeilen konstruiert werden sollen, wenn die Daten aus der Datei in eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Tabelle importiert werden.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-141">\<ROW> describes how to construct data rows from a data file when the data from the file is imported into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
     <span data-ttu-id="c4c3e-142">Ein \<ROW>-Element enthält eine Gruppe von \<COLUMN>-Elementen.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-142">A \<ROW> element contains a set of \<COLUMN> elements.</span></span> <span data-ttu-id="c4c3e-143">Diese Elemente entsprechen den Tabellenspalten.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-143">These elements correspond to table columns.</span></span> <span data-ttu-id="c4c3e-144">Die Basissyntax lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c4c3e-144">The basic syntax is as follows:</span></span>  
  
     \<ROW>  
  
     <span data-ttu-id="c4c3e-145">\<COLUMN .../> [ ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="c4c3e-145">\<COLUMN .../> [ ...*n* ]</span></span>  
  
     \</ROW>  
  
     <span data-ttu-id="c4c3e-146">Jedes \<COLUMN>-Element kann nur einem Feld in der Datendatei zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-146">Each \<COLUMN> element can be mapped to only one field in the data file.</span></span> <span data-ttu-id="c4c3e-147">Die Reihenfolge der \<COLUMN>-Elemente im \<ROW>-Element definiert die Reihenfolge, in der sie vom Massenvorgang zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-147">The order of the \<COLUMN> elements in the \<ROW> element defines the order in which they are returned by the bulk operation.</span></span> <span data-ttu-id="c4c3e-148">Die XML-Formatdatei weist jedem \<COLUMN>-Element einen lokalen Namen zu, der keine Beziehung zu der Spalte in der Zieltabelle des Massenimportvorgangs aufweist.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-148">The XML format file assigns each \<COLUMN> element a local name that has no relationship to the column in the target table of a bulk import operation.</span></span>  
  
##  <a name="schema-syntax-for-xml-format-files"></a><a name="SchemaSyntax"></a> <span data-ttu-id="c4c3e-149">Schemasyntax für XML-Formatdateien</span><span class="sxs-lookup"><span data-stu-id="c4c3e-149">Schema Syntax for XML Format Files</span></span>  
 <span data-ttu-id="c4c3e-150">Dieser Abschnitt enthält eine Zusammenfassung der Elemente und Attribute des XML-Schemas für XML-Formatdateien.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-150">This section contains a summary of the elements and attributes of the XML schema for XML format files.</span></span> <span data-ttu-id="c4c3e-151">Die Syntax einer Formatdatei ist unabhängig von der Richtung des Vorgangs, die Syntax ist also für Massenexport und Massenimport identisch.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-151">The syntax of a format file is independent of the direction of the operation; that is, the syntax is the same for bulk export and bulk import.</span></span> <span data-ttu-id="c4c3e-152">Darüber hinaus wird in diesem Abschnitt gezeigt, wie Sie \<ROW>- und \<COLUMN>-Elemente beim Massenimport verwenden und wie Sie den xsi:type-Wert eines Elements in ein Dataset einfügen.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-152">This section also considers how bulk import uses the \<ROW> and \<COLUMN> elements and how to put the xsi:type value of an element into a data set.</span></span>  
  
 <span data-ttu-id="c4c3e-153">Unter [Beispiele für XML-Formatdateien](#SampleXmlFFs)weiter unten in diesem Thema können Sie die Syntax mit tatsächlichen XML-Formatdateien vergleichen.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-153">To see how the syntax corresponds to actual XML format files, see [Sample XML Format Files](#SampleXmlFFs), later in this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c4c3e-154">Sie können eine Formatdatei so ändern, dass Sie einen Massenimport von einer Datendatei durchführen können, in der die Anzahl und/oder Reihenfolge der Felder von der Anzahl und/oder Reihenfolge der Tabellenspalten abweicht.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-154">You can modify a format file to let you bulk import from a data file in which the number and/or order of the fields differ from the number and/or order of table columns.</span></span> <span data-ttu-id="c4c3e-155">Weitere Informationen finden Sie unter [Formatdateien zum Importieren oder Exportieren von Daten &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md)erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-155">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
  
  
###  <a name="basic-syntax-of-the-xml-schema"></a><a name="BasicSyntax"></a> <span data-ttu-id="c4c3e-156">Basissyntax des XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="c4c3e-156">Basic Syntax of the XML Schema</span></span>  
 <span data-ttu-id="c4c3e-157">Diese Syntaxanweisungen zeigen nur die Elemente (\<BCPFORMAT>, \<RECORD>, \<FIELD>, \<ROW> und \<COLUMN>) und deren grundlegende Attribute.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-157">This syntax statements show only the elements (\<BCPFORMAT>, \<RECORD>, \<FIELD>, \<ROW>, and \<COLUMN>) and their basic attributes.</span></span>  
  
 \<BCPFORMAT ...>  
  
 \<RECORD>  
  
 <span data-ttu-id="c4c3e-158">\<FIELD ID = "*fieldID*" xsi:type = "*fieldType*" [...]</span><span class="sxs-lookup"><span data-stu-id="c4c3e-158">\<FIELD ID = "*fieldID*" xsi:type = "*fieldType*" [...]</span></span>  
  
 />  
  
 \</RECORD>  
  
 \<ROW>  
  
 <span data-ttu-id="c4c3e-159">\<COLUMN SOURCE = "*fieldID*" NAME = "*columnName*" xsi:type = "*columnType*" [...]</span><span class="sxs-lookup"><span data-stu-id="c4c3e-159">\<COLUMN SOURCE = "*fieldID*" NAME = "*columnName*" xsi:type = "*columnType*" [...]</span></span>  
  
 />  
  
 \</ROW>  
  
 \</BCPFORMAT>  
  
> [!NOTE]  
>  <span data-ttu-id="c4c3e-160">Weitere Attribute, die mit dem Wert von xsi:type in einem \<FIELD>- oder \<COLUMN>-Element verknüpft sind, werden weiter unten in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-160">Additional attributes that are associated with the value of the xsi:type in a \<FIELD> or \<COLUMN> element are described later in this topic.</span></span>  
  

  
####  <a name="schema-elements"></a><a name="SchemaElements"></a> <span data-ttu-id="c4c3e-161">Schema-Elemente</span><span class="sxs-lookup"><span data-stu-id="c4c3e-161">Schema Elements</span></span>  
 <span data-ttu-id="c4c3e-162">In diesem Abschnitt werden die Funktionen aller Elemente dargestellt, die das XML-Schema für XML-Formatdateien definiert.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-162">This section summarizes the purpose of each element that the XML schema defines for XML format files.</span></span> <span data-ttu-id="c4c3e-163">Die Attribute werden in separaten Abschnitten weiter unten in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-163">The attributes are described in separate sections later in this topic.</span></span>  
  
 \<BCPFORMAT>  
 <span data-ttu-id="c4c3e-164">Ist das Element der Formatdatei, das die Datensatzstruktur einer bestimmten Datendatei und ihre Übereinstimmung mit den Spalten einer Tabellenzeile in einer Tabelle definiert.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-164">Is the format-file element that defines the record structure of a given data file and its correspondence to the columns of a table row in the table.</span></span>  
  
 \<RECORD .../>  
 <span data-ttu-id="c4c3e-165">Hiermit wird ein komplexes Element definiert, das ein oder mehrere \<FIELD>-Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-165">Defines a complex element containing one or more \<FIELD> elements.</span></span> <span data-ttu-id="c4c3e-166">Die Reihenfolge, in der die Felder in der Formatdatei deklariert werden, entspricht der Reihenfolge, in der diese Felder in der Datendatei angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-166">The order in which the fields are declared in the format file is the order in which those fields appear in the data file.</span></span>  
  
 \<FIELD .../>  
 <span data-ttu-id="c4c3e-167">Definiert ein Feld in der Datendatei, das Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-167">Defines a field in data file, which contains data.</span></span>  
  
 <span data-ttu-id="c4c3e-168">Die Attribute dieses Elements werden unter [Attribute des \<FIELD>-Elements](#AttrOfFieldElement) weiter unten in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-168">The attributes of this element are discussed in [Attributes of the \<FIELD> Element](#AttrOfFieldElement), later in this topic.</span></span>  
  
 \<ROW .../>  
 <span data-ttu-id="c4c3e-169">Hiermit wird ein komplexes Element definiert, das ein oder mehrere \<COLUMN>-Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-169">Defines a complex element containing one or more \<COLUMN> elements.</span></span> <span data-ttu-id="c4c3e-170">Die Reihenfolge der \<COLUMN>-Elemente hängt nicht von der Reihenfolge der \<FIELD>-Elemente in einer RECORD-Definition ab.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-170">The order of the \<COLUMN> elements is independent of the order of \<FIELD> elements in a RECORD definition.</span></span> <span data-ttu-id="c4c3e-171">Stattdessen bestimmt die Reihenfolge der \<COLUMN>-Elemente in einer Formatdatei die Reihenfolge der Spalten im zurückgegebenen Rowset.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-171">Rather, the order of the \<COLUMN> elements in a format file determines the column order of the resultant rowset.</span></span> <span data-ttu-id="c4c3e-172">Die Datenfelder werden in der Reihenfolge geladen, in der die entsprechenden \<COLUMN>-Elemente im \<COLUMN>-Element deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-172">Data fields are loaded in the order in which the corresponding \<COLUMN> elements are declared in the \<COLUMN> element.</span></span>  
  
 <span data-ttu-id="c4c3e-173">Weitere Informationen finden Sie unter [Verwendung des \<ROW>-Elements beim Massenimport](#HowUsesROW) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-173">For more information, see [How Bulk Import Uses the \<ROW> Element](#HowUsesROW), later in this topic.</span></span>  
  
 \<COLUMN>  
 <span data-ttu-id="c4c3e-174">Hiermit wird eine Spalte als Element (\<COLUMN>) definiert.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-174">Defines a column as an element (\<COLUMN>).</span></span> <span data-ttu-id="c4c3e-175">Jedes \<COLUMN>-Element entspricht einem \<FIELD>-Element (dessen ID im SOURCE-Attribut des \<COLUMN>-Elements angegeben ist).</span><span class="sxs-lookup"><span data-stu-id="c4c3e-175">Each \<COLUMN> element corresponds to a \<FIELD> element (whose ID is specified in the SOURCE attribute of the \<COLUMN> element).</span></span>  
  
 <span data-ttu-id="c4c3e-176">Die Attribute dieses Elements werden unter [Attribute des \<COLUMN>-Elements](#AttrOfColumnElement) weiter unten in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-176">The attributes of this element are discussed in [Attributes of the \<COLUMN> Element](#AttrOfColumnElement), later in this topic.</span></span> <span data-ttu-id="c4c3e-177">Weitere Informationen finden Sie außerdem unter [Verwendung des \<COLUMN>-Elements beim Massenimport](#HowUsesColumn) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-177">Also see, [How Bulk Import Uses the \<COLUMN> Element](#HowUsesColumn), later in this topic.</span></span>  
  
 \</BCPFORMAT>  
 <span data-ttu-id="c4c3e-178">Ist erforderlich, um die Formatdatei zu beenden.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-178">Required to end the format file.</span></span>  
  
####  <a name="attributes-of-the-field-element"></a><a name="AttrOfFieldElement"></a> <span data-ttu-id="c4c3e-179">Attribute des \<FIELD>-Elements</span><span class="sxs-lookup"><span data-stu-id="c4c3e-179">Attributes of the \<FIELD> Element</span></span>  
 <span data-ttu-id="c4c3e-180">In diesem Abschnitt werden die Attribute des \<FIELD>-Elements beschrieben, die in der folgenden Schemasyntax zusammengefasst sind:</span><span class="sxs-lookup"><span data-stu-id="c4c3e-180">This section describes the attributes of the \<FIELD> element, which are summarized in the following schema syntax:</span></span>  
  
 <span data-ttu-id="c4c3e-181"><FIELD</span><span class="sxs-lookup"><span data-stu-id="c4c3e-181"><FIELD</span></span>  
  
 <span data-ttu-id="c4c3e-182">ID **= " *`fieldID`* "**</span><span class="sxs-lookup"><span data-stu-id="c4c3e-182">ID **="*`fieldID`*"**</span></span>  
  
 <span data-ttu-id="c4c3e-183">xsi **:** Type **= " *`fieldType`* "**</span><span class="sxs-lookup"><span data-stu-id="c4c3e-183">xsi **:** type **="*`fieldType`*"**</span></span>  
  
 <span data-ttu-id="c4c3e-184">[ LENGTH **="*`n`*"** ]</span><span class="sxs-lookup"><span data-stu-id="c4c3e-184">[ LENGTH **="*`n`*"** ]</span></span>  
  
 <span data-ttu-id="c4c3e-185">[PREFIX_LENGTH **= " *`p`* "** ]</span><span class="sxs-lookup"><span data-stu-id="c4c3e-185">[ PREFIX_LENGTH **="*`p`*"** ]</span></span>  
  
 <span data-ttu-id="c4c3e-186">[max_length **= " *`m`* "** ]</span><span class="sxs-lookup"><span data-stu-id="c4c3e-186">[ MAX_LENGTH **="*`m`*"** ]</span></span>  
  
 <span data-ttu-id="c4c3e-187">[Sortierung **= " *`collationName`* "** ]</span><span class="sxs-lookup"><span data-stu-id="c4c3e-187">[ COLLATION **="*`collationName`*"** ]</span></span>  
  
 <span data-ttu-id="c4c3e-188">[Terminator **= " *`terminator`* "** ]</span><span class="sxs-lookup"><span data-stu-id="c4c3e-188">[ TERMINATOR **="*`terminator`*"** ]</span></span>  
  
 />  
  
 <span data-ttu-id="c4c3e-189">Alle \<FIELD>-Elemente sind unabhängig voneinander.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-189">Each \<FIELD> element is independent of the others.</span></span> <span data-ttu-id="c4c3e-190">Ein Feld wird anhand der folgenden Attribute beschrieben:</span><span class="sxs-lookup"><span data-stu-id="c4c3e-190">A field is described in terms of the following attributes:</span></span>  
  
|<span data-ttu-id="c4c3e-191">FIELD-Attribut</span><span class="sxs-lookup"><span data-stu-id="c4c3e-191">FIELD Attribute</span></span>|<span data-ttu-id="c4c3e-192">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c4c3e-192">Description</span></span>|<span data-ttu-id="c4c3e-193">Optional /</span><span class="sxs-lookup"><span data-stu-id="c4c3e-193">Optional /</span></span><br /><br /> <span data-ttu-id="c4c3e-194">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c4c3e-194">Required</span></span>|  
|---------------------|-----------------|------------------------------|  
|<span data-ttu-id="c4c3e-195">ID **= " *`fieldID`* "**</span><span class="sxs-lookup"><span data-stu-id="c4c3e-195">ID **="*`fieldID`*"**</span></span>|<span data-ttu-id="c4c3e-196">Gibt den logischen Namen des Felds in der Datendatei an.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-196">Specifies the logical name of the field in the data file.</span></span> <span data-ttu-id="c4c3e-197">Die ID eines Felds ist der Schlüssel, mit dem auf das Feld verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-197">The ID of a field is the key used to refer to the field.</span></span><br /><br /> <span data-ttu-id="c4c3e-198"><Feld-ID **= " *`fieldID`* "**/> wird <Spalten Quelle **= " *`fieldID`* "** zugeordnet./></span><span class="sxs-lookup"><span data-stu-id="c4c3e-198"><FIELD ID **="*`fieldID`*"**/> maps to <COLUMN SOURCE **="*`fieldID`*"**/></span></span>|<span data-ttu-id="c4c3e-199">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c4c3e-199">Required</span></span>|  
|<span data-ttu-id="c4c3e-200">xsi: Type **= " *`fieldType`* "**</span><span class="sxs-lookup"><span data-stu-id="c4c3e-200">xsi:type **="*`fieldType`*"**</span></span>|<span data-ttu-id="c4c3e-201">Dies ist ein (als Attribut verwendetes) XML-Konstrukt, das den Typ der Instanz des Elements identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-201">This is an XML construct (used like an attribute) that identifies the type of the instance of the element.</span></span> <span data-ttu-id="c4c3e-202">Der Wert von *fieldType* bestimmt, welche der optionalen Attribute (unten) in einer bestimmten Instanz erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-202">The value of *fieldType* determines which of the optional attributes (below) you need in a given instance.</span></span>|<span data-ttu-id="c4c3e-203">Erforderlich (abhängig vom Datentyp)</span><span class="sxs-lookup"><span data-stu-id="c4c3e-203">Required (depending on the data type)</span></span>|  
|<span data-ttu-id="c4c3e-204">Length **= " *`n`* "**</span><span class="sxs-lookup"><span data-stu-id="c4c3e-204">LENGTH **="*`n`*"**</span></span>|<span data-ttu-id="c4c3e-205">Dieses Attribut definiert die Länge für eine Instanz mit einem Datentyp fester Länge.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-205">This attribute defines the length for an instance of a fixed-length data type.</span></span><br /><br /> <span data-ttu-id="c4c3e-206">Der Wert von *n* muss eine positive ganze Zahl sein.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-206">The value of *n* must be a positive integer.</span></span>|<span data-ttu-id="c4c3e-207">Optional, sofern nicht für den xsi:type-Wert erforderlich</span><span class="sxs-lookup"><span data-stu-id="c4c3e-207">Optional unless required by the xsi:type value</span></span>|  
|<span data-ttu-id="c4c3e-208">PREFIX_LENGTH **= " *`p`* "**</span><span class="sxs-lookup"><span data-stu-id="c4c3e-208">PREFIX_LENGTH **="*`p`*"**</span></span>|<span data-ttu-id="c4c3e-209">Dieses Attribut definiert die Präfixlänge für eine binäre Datendarstellung.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-209">This attribute defines the prefix length for a binary data representation.</span></span> <span data-ttu-id="c4c3e-210">Bei dem PREFIX_LENGTH-Wert, *p*, muss es sich um eine der folgenden Zahlen handeln: 1, 2, 4 oder 8.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-210">The PREFIX_LENGTH value, *p*, must be one of the following: 1, 2, 4, or 8.</span></span>|<span data-ttu-id="c4c3e-211">Optional, sofern nicht für den xsi:type-Wert erforderlich</span><span class="sxs-lookup"><span data-stu-id="c4c3e-211">Optional unless required by the xsi:type value</span></span>|  
|<span data-ttu-id="c4c3e-212">max_length **= " *`m`* "**</span><span class="sxs-lookup"><span data-stu-id="c4c3e-212">MAX_LENGTH **="*`m`*"**</span></span>|<span data-ttu-id="c4c3e-213">Dieses Attribut gibt die maximale Anzahl an Byte an, die in einem bestimmten Feld gespeichert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-213">This attribute is the maximum number of bytes that can be stored in a given field.</span></span> <span data-ttu-id="c4c3e-214">Ohne eine Zieltabelle ist die maximale Spaltenlänge nicht bekannt.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-214">Without a target table, the column max-length is not known.</span></span> <span data-ttu-id="c4c3e-215">Das MAX_LENGTH-Attribut beschränkt die maximale Länge einer Ausgabezeichenspalte sowie den Speicherplatz, der dem Spaltenwert zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-215">The MAX_LENGTH attribute restricts the maximum length of an output character column, limiting the storage allocated for the column value.</span></span> <span data-ttu-id="c4c3e-216">Dies ist vor allem bei Verwendung der BULK-Option der OPENROWSET-Funktion in einer SELECT FROM-Klausel nützlich.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-216">This is especially convenient when using the OPENROWSET function's BULK option in a SELECT FROM clause.</span></span><br /><br /> <span data-ttu-id="c4c3e-217">Der Wert von *m* muss eine positive ganze Zahl sein.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-217">The value of *m* must be a positive integer.</span></span> <span data-ttu-id="c4c3e-218">Standardmäßig beträgt die maximale Länge 8000 Zeichen für eine **char** -Spalte und 4000 Zeichen für eine **nchar** -Spalte.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-218">By default, the maximum length is 8000 characters for a **char** column and 4000 characters for an **nchar** column.</span></span>|<span data-ttu-id="c4c3e-219">Optional</span><span class="sxs-lookup"><span data-stu-id="c4c3e-219">Optional</span></span>|  
|<span data-ttu-id="c4c3e-220">Collations **= " *`collationName`* "**</span><span class="sxs-lookup"><span data-stu-id="c4c3e-220">COLLATION **="*`collationName`*"**</span></span>|<span data-ttu-id="c4c3e-221">COLLATION ist nur für Zeichenfelder zulässig.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-221">COLLATION is only allowed for character fields.</span></span> <span data-ttu-id="c4c3e-222">Eine Liste der SQL-Sortierungsnamen finden Sie unter [SQL Server-Sortierungsname &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c4c3e-222">For a list of the SQL collation names, see [SQL Server Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql).</span></span>|<span data-ttu-id="c4c3e-223">Optional</span><span class="sxs-lookup"><span data-stu-id="c4c3e-223">Optional</span></span>|  
|<span data-ttu-id="c4c3e-224">Terminator **= " *`terminator`* "**</span><span class="sxs-lookup"><span data-stu-id="c4c3e-224">TERMINATOR **= "*`terminator`*"**</span></span>|<span data-ttu-id="c4c3e-225">Dieses Attribut gibt das Abschlusszeichen eines Datenfelds an.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-225">This attribute specifies the terminator of a data field.</span></span> <span data-ttu-id="c4c3e-226">Als Abschlusszeichen kann jedes beliebige Zeichen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-226">The terminator can be any character.</span></span> <span data-ttu-id="c4c3e-227">Es muss sich jedoch um ein eindeutiges Zeichen handeln, das nicht Teil der Daten ist.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-227">The terminator must be a unique character that is not part of the data.</span></span><br /><br /> <span data-ttu-id="c4c3e-228">Standardmäßig wird das Tabstoppzeichen (dargestellt als \t) als Abschlusszeichen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-228">By default, the field terminator is the tab character (represented as \t).</span></span> <span data-ttu-id="c4c3e-229">Um eine Absatzmarke darzustellen, verwenden Sie \r\n.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-229">To represent a paragraph mark, use \r\n.</span></span>|<span data-ttu-id="c4c3e-230">Wird nur mit einem xsi:type von Zeichendaten verwendet, die dieses Attribut erfordern.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-230">Used only with an xsi:type of character data, which requires this attribute</span></span>|  
  
#####  <a name="xsitype-values-of-the-field-element"></a><a name="XsiTypeValuesOfFIELD"></a> <span data-ttu-id="c4c3e-231">xsi:type-Werte des \<FIELD>-Elements</span><span class="sxs-lookup"><span data-stu-id="c4c3e-231">Xsi:type values of the \<FIELD> Element</span></span>  
 <span data-ttu-id="c4c3e-232">Der xsi:type-Wert ist ein (als Attribut verwendetes) XML-Konstrukt, das den Datentyp für eine Instanz eines Elements identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-232">The xsi:type value is an XML construct (used like an attribute) that identifies the data type of an instance of an element.</span></span> <span data-ttu-id="c4c3e-233">Weitere Informationen finden Sie unter "Einfügen des xsi:type-Werts in ein Dataset" weiter unten in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-233">For information on using the "Putting the xsi:type Value into a Data Set," later in this section.</span></span>  
  
 <span data-ttu-id="c4c3e-234">Bei den xsi:type-Werten des \<FIELD>-Elements werden die folgenden Datentypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-234">The xsi:type value of the \<FIELD> element supports the following data types.</span></span>  
  
|<span data-ttu-id="c4c3e-235">xsi:type-Werte für \<FIELD></span><span class="sxs-lookup"><span data-stu-id="c4c3e-235">\<FIELD> xsi:type values</span></span>|<span data-ttu-id="c4c3e-236">Erforderliche(s) XML-Attribut(e)</span><span class="sxs-lookup"><span data-stu-id="c4c3e-236">Required XML Attribute(s)</span></span><br /><br /> <span data-ttu-id="c4c3e-237">für Datentyp</span><span class="sxs-lookup"><span data-stu-id="c4c3e-237">for Data Type</span></span>|<span data-ttu-id="c4c3e-238">Optionale(s) XML-Attribut(e)</span><span class="sxs-lookup"><span data-stu-id="c4c3e-238">Optional XML Attribute(s)</span></span><br /><br /> <span data-ttu-id="c4c3e-239">für Datentyp</span><span class="sxs-lookup"><span data-stu-id="c4c3e-239">for Data Type</span></span>|  
|-------------------------------|---------------------------------------------------|---------------------------------------------------|  
|<span data-ttu-id="c4c3e-240">**NativeFixed**</span><span class="sxs-lookup"><span data-stu-id="c4c3e-240">**NativeFixed**</span></span>|`LENGTH`|<span data-ttu-id="c4c3e-241">Keine.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-241">None.</span></span>|  
|<span data-ttu-id="c4c3e-242">**NativePrefix**</span><span class="sxs-lookup"><span data-stu-id="c4c3e-242">**NativePrefix**</span></span>|`PREFIX_LENGTH`|<span data-ttu-id="c4c3e-243">MAX_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c4c3e-243">MAX_LENGTH</span></span>|  
|<span data-ttu-id="c4c3e-244">**CharFixed**</span><span class="sxs-lookup"><span data-stu-id="c4c3e-244">**CharFixed**</span></span>|`LENGTH`|<span data-ttu-id="c4c3e-245">COLLATION</span><span class="sxs-lookup"><span data-stu-id="c4c3e-245">COLLATION</span></span>|  
|<span data-ttu-id="c4c3e-246">**NCharFixed**</span><span class="sxs-lookup"><span data-stu-id="c4c3e-246">**NCharFixed**</span></span>|`LENGTH`|<span data-ttu-id="c4c3e-247">COLLATION</span><span class="sxs-lookup"><span data-stu-id="c4c3e-247">COLLATION</span></span>|  
|<span data-ttu-id="c4c3e-248">**CharPrefix**</span><span class="sxs-lookup"><span data-stu-id="c4c3e-248">**CharPrefix**</span></span>|`PREFIX_LENGTH`|<span data-ttu-id="c4c3e-249">MAX_LENGTH, COLLATION</span><span class="sxs-lookup"><span data-stu-id="c4c3e-249">MAX_LENGTH, COLLATION</span></span>|  
|<span data-ttu-id="c4c3e-250">**NCharPrefix**</span><span class="sxs-lookup"><span data-stu-id="c4c3e-250">**NCharPrefix**</span></span>|`PREFIX_LENGTH`|<span data-ttu-id="c4c3e-251">MAX_LENGTH, COLLATION</span><span class="sxs-lookup"><span data-stu-id="c4c3e-251">MAX_LENGTH, COLLATION</span></span>|  
|<span data-ttu-id="c4c3e-252">**CharTerm**</span><span class="sxs-lookup"><span data-stu-id="c4c3e-252">**CharTerm**</span></span>|`TERMINATOR`|<span data-ttu-id="c4c3e-253">MAX_LENGTH, COLLATION</span><span class="sxs-lookup"><span data-stu-id="c4c3e-253">MAX_LENGTH, COLLATION</span></span>|  
|<span data-ttu-id="c4c3e-254">**NCharTerm**</span><span class="sxs-lookup"><span data-stu-id="c4c3e-254">**NCharTerm**</span></span>|`TERMINATOR`|<span data-ttu-id="c4c3e-255">MAX_LENGTH, COLLATION</span><span class="sxs-lookup"><span data-stu-id="c4c3e-255">MAX_LENGTH, COLLATION</span></span>|  
  
 <span data-ttu-id="c4c3e-256">Weitere Informationen zu [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datentypen finden Sie unter [Datentypen &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c4c3e-256">For more information about [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
####  <a name="attributes-of-the-column-element"></a><a name="AttrOfColumnElement"></a> <span data-ttu-id="c4c3e-257">Attribute des \<COLUMN>-Elements</span><span class="sxs-lookup"><span data-stu-id="c4c3e-257">Attributes of the \<COLUMN> Element</span></span>  
 <span data-ttu-id="c4c3e-258">In diesem Abschnitt werden die Attribute des \<COLUMN>-Elements beschrieben, die in der folgenden Schemasyntax zusammengefasst sind:</span><span class="sxs-lookup"><span data-stu-id="c4c3e-258">This section describes the attributes of the \<COLUMN> element, which are summarized in the following schema syntax:</span></span>  
  
 <span data-ttu-id="c4c3e-259">\<COLUMN</span><span class="sxs-lookup"><span data-stu-id="c4c3e-259">\<COLUMN</span></span>  
  
 <span data-ttu-id="c4c3e-260">SOURCE = "*fieldID*"</span><span class="sxs-lookup"><span data-stu-id="c4c3e-260">SOURCE = "*fieldID*"</span></span>  
  
 <span data-ttu-id="c4c3e-261">NAME = "*columnName*"</span><span class="sxs-lookup"><span data-stu-id="c4c3e-261">NAME = "*columnName*"</span></span>  
  
 <span data-ttu-id="c4c3e-262">xsi:type = "*columnType*"</span><span class="sxs-lookup"><span data-stu-id="c4c3e-262">xsi:type = "*columnType*"</span></span>  
  
 <span data-ttu-id="c4c3e-263">[ LENGTH = "*n*" ]</span><span class="sxs-lookup"><span data-stu-id="c4c3e-263">[ LENGTH = "*n*" ]</span></span>  
  
 <span data-ttu-id="c4c3e-264">[ PRECISION = "*n*" ]</span><span class="sxs-lookup"><span data-stu-id="c4c3e-264">[ PRECISION = "*n*" ]</span></span>  
  
 <span data-ttu-id="c4c3e-265">[ SCALE = "*value*" ]</span><span class="sxs-lookup"><span data-stu-id="c4c3e-265">[ SCALE = "*value*" ]</span></span>  
  
 <span data-ttu-id="c4c3e-266">[ NULLABLE = { "YES"</span><span class="sxs-lookup"><span data-stu-id="c4c3e-266">[ NULLABLE = { "YES"</span></span>  
  
 <span data-ttu-id="c4c3e-267">"NO" } ]</span><span class="sxs-lookup"><span data-stu-id="c4c3e-267">"NO" } ]</span></span>  
  
 />  
  
 <span data-ttu-id="c4c3e-268">Ein Feld wird mithilfe der folgenden Attribute einer Spalte in der Zieltabelle zugeordnet:</span><span class="sxs-lookup"><span data-stu-id="c4c3e-268">A field is mapped to a column in the target table using the following attributes:</span></span>  
  
|<span data-ttu-id="c4c3e-269">COLUMN-Attribut</span><span class="sxs-lookup"><span data-stu-id="c4c3e-269">COLUMN Attribute</span></span>|<span data-ttu-id="c4c3e-270">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c4c3e-270">Description</span></span>|<span data-ttu-id="c4c3e-271">Optional /</span><span class="sxs-lookup"><span data-stu-id="c4c3e-271">Optional /</span></span><br /><br /> <span data-ttu-id="c4c3e-272">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c4c3e-272">Required</span></span>|  
|----------------------|-----------------|------------------------------|  
|<span data-ttu-id="c4c3e-273">Quelle **= " *`fieldID`* "**</span><span class="sxs-lookup"><span data-stu-id="c4c3e-273">SOURCE **="*`fieldID`*"**</span></span>|<span data-ttu-id="c4c3e-274">Gibt die ID des Felds an, das der Spalte zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-274">Specifies the ID of the field being mapped to the column.</span></span><br /><br /> <span data-ttu-id="c4c3e-275"><Spalten Quelle **= " *`fieldID`* "**/> wird <Feld-ID **= " *`fieldID`* "** zugeordnet./></span><span class="sxs-lookup"><span data-stu-id="c4c3e-275"><COLUMN SOURCE **="*`fieldID`*"**/> maps to <FIELD ID **="*`fieldID`*"**/></span></span>|<span data-ttu-id="c4c3e-276">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c4c3e-276">Required</span></span>|  
|<span data-ttu-id="c4c3e-277">NAME = "*columnName*"</span><span class="sxs-lookup"><span data-stu-id="c4c3e-277">NAME = "*columnName*"</span></span>|<span data-ttu-id="c4c3e-278">Gibt den Namen der Spalte im Rowset an, die durch die Formatdatei dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-278">Specifies the name of the column in the row set represented by the format file.</span></span> <span data-ttu-id="c4c3e-279">Dieser Spaltenname wird verwendet, um die Spalte im Resultset zu identifizieren; er muss nicht dem in der Zieltabelle verwendeten Spaltennamen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-279">This column name is used to identify the column in the result set, and it need not correspond to the column name used in the target table.</span></span>|<span data-ttu-id="c4c3e-280">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c4c3e-280">Required</span></span>|  
|<span data-ttu-id="c4c3e-281">xsi **:** Type **= " *`ColumnType`* "**</span><span class="sxs-lookup"><span data-stu-id="c4c3e-281">xsi **:** type **="*`ColumnType`*"**</span></span>|<span data-ttu-id="c4c3e-282">Dies ist ein (als Attribut verwendetes) XML-Konstrukt, das den Datentyp der Instanz des Elements identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-282">This is an XML construct (used like an attribute) that identifies the data type of the instance of the element.</span></span> <span data-ttu-id="c4c3e-283">Der Wert von *ColumnType* bestimmt, welche der optionalen Attribute (unten) in einer bestimmten Instanz erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-283">The value of *ColumnType* determines which of the optional attributes (below) you need in a given instance.</span></span><br /><br /> <span data-ttu-id="c4c3e-284">Hinweis: die möglichen Werte von *ColumnType* und den zugehörigen Attributen werden in der nächsten Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-284">Note: The possible values of *ColumnType* and their associated attributes are listed in the next table.</span></span>|<span data-ttu-id="c4c3e-285">Optional</span><span class="sxs-lookup"><span data-stu-id="c4c3e-285">Optional</span></span>|  
|<span data-ttu-id="c4c3e-286">Length **= " *`n`* "**</span><span class="sxs-lookup"><span data-stu-id="c4c3e-286">LENGTH **="*`n`*"**</span></span>|<span data-ttu-id="c4c3e-287">Definiert die Länge für eine Instanz mit einem Datentyp fester Länge.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-287">Defines the length for an instance of a fixed-length data type.</span></span> <span data-ttu-id="c4c3e-288">LENGTH wird nur verwendet, wenn es sich bei xsi:type um einen Zeichenfolgen-Datentyp handelt.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-288">LENGTH is used only when the xsi:type is a string data type.</span></span><br /><br /> <span data-ttu-id="c4c3e-289">Der Wert von *n* muss eine positive ganze Zahl sein.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-289">The value of *n* must be a positive integer.</span></span>|<span data-ttu-id="c4c3e-290">Optional (nur verfügbar, wenn xsi:type ein Zeichenfolgen-Datentyp ist)</span><span class="sxs-lookup"><span data-stu-id="c4c3e-290">Optional (available only if the xsi:type is a string data type)</span></span>|  
|<span data-ttu-id="c4c3e-291">PRECISION **="*`n`*"**</span><span class="sxs-lookup"><span data-stu-id="c4c3e-291">PRECISION **="*`n`*"**</span></span>|<span data-ttu-id="c4c3e-292">Gibt die Anzahl der Stellen einer Zahl an.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-292">Indicates the number of digits in a number.</span></span> <span data-ttu-id="c4c3e-293">Beispielsweise hat die Zahl 123,45 eine Genauigkeit von 5.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-293">For example, the number 123.45 has a precision of 5.</span></span><br /><br /> <span data-ttu-id="c4c3e-294">Der Wert muss eine positive ganze Zahl sein.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-294">The value must be a positive integer.</span></span>|<span data-ttu-id="c4c3e-295">Optional (nur verfügbar, wenn xsi:type ein Datentyp mit variablen Zahlen ist)</span><span class="sxs-lookup"><span data-stu-id="c4c3e-295">Optional (available only if the xsi:type is a variable-number data type)</span></span>|  
|<span data-ttu-id="c4c3e-296">Skalieren **= " *`int`* "**</span><span class="sxs-lookup"><span data-stu-id="c4c3e-296">SCALE **="*`int`*"**</span></span>|<span data-ttu-id="c4c3e-297">Gibt die Anzahl der Stellen rechts vom Dezimaltrennzeichen einer Zahl an.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-297">Indicates the number of digits to the right of the decimal point in a number.</span></span> <span data-ttu-id="c4c3e-298">Beispielsweise verfügt die Zahl 123,45 über 2 Dezimalstellen.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-298">For example, the number 123.45 has a scale of 2.</span></span><br /><br /> <span data-ttu-id="c4c3e-299">Der Wert muss eine ganze Zahl sein.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-299">The value must be an integer.</span></span>|<span data-ttu-id="c4c3e-300">Optional (nur verfügbar, wenn xsi:type ein Datentyp mit variablen Zahlen ist)</span><span class="sxs-lookup"><span data-stu-id="c4c3e-300">Optional (available only if the xsi:type is a variable-number data type)</span></span>|  
|<span data-ttu-id="c4c3e-301">NULLABLE **=** { **"** YES **"**</span><span class="sxs-lookup"><span data-stu-id="c4c3e-301">NULLABLE **=** { **"** YES **"**</span></span><br /><br /> <span data-ttu-id="c4c3e-302">**"** NO **"** }</span><span class="sxs-lookup"><span data-stu-id="c4c3e-302">**"** NO **"** }</span></span>|<span data-ttu-id="c4c3e-303">Gibt an, ob eine Spalte NULL-Werte verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-303">Indicates whether a column can assume NULL values.</span></span> <span data-ttu-id="c4c3e-304">Dieses Attribut ist unabhängig von FIELDS.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-304">This attribute is completely independent of FIELDS.</span></span> <span data-ttu-id="c4c3e-305">Falls die Spalte jedoch nicht NULLABLE ist und für ein Feld NULL (d. h. kein Wert) angegeben wurde, tritt ein Laufzeitfehler auf.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-305">However, if a column is not NULLABLE and field specifies NULL (by not specifying any value), a run-time error results.</span></span><br /><br /> <span data-ttu-id="c4c3e-306">Das NULLABLE-Attribut wird nur verwendet, wenn Sie eine einfache SELECT FROM OPENROWSET (BULK...)-Anweisung ausführen.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-306">The NULLABLE attribute is used only if you do a plain SELECT FROM OPENROWSET(BULK...) statement.</span></span>|<span data-ttu-id="c4c3e-307">Optional (verfügbar für jeden beliebigen Datentyp)</span><span class="sxs-lookup"><span data-stu-id="c4c3e-307">Optional (available for any data type)</span></span>|  
  
#####  <a name="xsitype-values-of-the-column-element"></a><a name="XsiTypeValuesOfCOLUMN"></a> <span data-ttu-id="c4c3e-308">xsi:type-Werte des \<COLUMN>-Elements</span><span class="sxs-lookup"><span data-stu-id="c4c3e-308">Xsi:type values of the \<COLUMN> Element</span></span>  
 <span data-ttu-id="c4c3e-309">Der xsi:type-Wert ist ein (als Attribut verwendetes) XML-Konstrukt, das den Datentyp für eine Instanz eines Elements identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-309">The xsi:type value is an XML construct (used like an attribute) that identifies the data type of an instance of an element.</span></span> <span data-ttu-id="c4c3e-310">Weitere Informationen finden Sie unter "Einfügen des xsi:type-Werts in ein Dataset" weiter unten in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-310">For information on using the "Putting the xsi:type Value into a Data Set," later in this section.</span></span>  
  
 <span data-ttu-id="c4c3e-311">Das \<COLUMN>-Element unterstützt native SQL-Datentypen wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c4c3e-311">The \<COLUMN> element supports native SQL data types, as follows:</span></span>  
  
|<span data-ttu-id="c4c3e-312">Typkategorie</span><span class="sxs-lookup"><span data-stu-id="c4c3e-312">Type Category</span></span>|<span data-ttu-id="c4c3e-313">\<COLUMN>-Datentypen</span><span class="sxs-lookup"><span data-stu-id="c4c3e-313">\<COLUMN> Data Types</span></span>|<span data-ttu-id="c4c3e-314">Erforderliche(s) XML-Attribut(e)</span><span class="sxs-lookup"><span data-stu-id="c4c3e-314">Required XML Attribute(s)</span></span><br /><br /> <span data-ttu-id="c4c3e-315">für Datentyp</span><span class="sxs-lookup"><span data-stu-id="c4c3e-315">for Data Type</span></span>|<span data-ttu-id="c4c3e-316">Optionale(s) XML-Attribut(e)</span><span class="sxs-lookup"><span data-stu-id="c4c3e-316">Optional XML Attribute(s)</span></span><br /><br /> <span data-ttu-id="c4c3e-317">für Datentyp</span><span class="sxs-lookup"><span data-stu-id="c4c3e-317">for Data Type</span></span>|  
|-------------------|---------------------------|---------------------------------------------------|---------------------------------------------------|  
|<span data-ttu-id="c4c3e-318">Korrigiert</span><span class="sxs-lookup"><span data-stu-id="c4c3e-318">Fixed</span></span>|<span data-ttu-id="c4c3e-319">`SQLBIT`, `SQLTINYINT`, `SQLSMALLINT`, `SQLINT`, `SQLBIGINT`, `SQLFLT4`, `SQLFLT8`, `SQLDATETIME`, `SQLDATETIM4`, `SQLDATETIM8`, `SQLMONEY`, `SQLMONEY4`, `SQLVARIANT` und `SQLUNIQUEID`</span><span class="sxs-lookup"><span data-stu-id="c4c3e-319">`SQLBIT`, `SQLTINYINT`, `SQLSMALLINT`, `SQLINT`, `SQLBIGINT`, `SQLFLT4`, `SQLFLT8`, `SQLDATETIME`, `SQLDATETIM4`, `SQLDATETIM8`, `SQLMONEY`, `SQLMONEY4`, `SQLVARIANT`, and `SQLUNIQUEID`</span></span>|<span data-ttu-id="c4c3e-320">Keine.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-320">None.</span></span>|<span data-ttu-id="c4c3e-321">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c4c3e-321">NULLABLE</span></span>|  
|<span data-ttu-id="c4c3e-322">Variable Zahl</span><span class="sxs-lookup"><span data-stu-id="c4c3e-322">Variable Number</span></span>|<span data-ttu-id="c4c3e-323">`SQLDECIMAL` und `SQLNUMERIC`</span><span class="sxs-lookup"><span data-stu-id="c4c3e-323">`SQLDECIMAL` and `SQLNUMERIC`</span></span>|<span data-ttu-id="c4c3e-324">Keine.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-324">None.</span></span>|<span data-ttu-id="c4c3e-325">NULLABLE, PRECISION, SCALE</span><span class="sxs-lookup"><span data-stu-id="c4c3e-325">NULLABLE, PRECISION, SCALE</span></span>|  
|<span data-ttu-id="c4c3e-326">LOB</span><span class="sxs-lookup"><span data-stu-id="c4c3e-326">LOB</span></span>|<span data-ttu-id="c4c3e-327">`SQLIMAGE`, `CharLOB`, `SQLTEXT` und `SQLUDT`</span><span class="sxs-lookup"><span data-stu-id="c4c3e-327">`SQLIMAGE`, `CharLOB`, `SQLTEXT`, and `SQLUDT`</span></span>|<span data-ttu-id="c4c3e-328">Keine.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-328">None.</span></span>|<span data-ttu-id="c4c3e-329">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c4c3e-329">NULLABLE</span></span>|  
|<span data-ttu-id="c4c3e-330">Character LOB</span><span class="sxs-lookup"><span data-stu-id="c4c3e-330">Character LOB</span></span>|`SQLNTEXT`|<span data-ttu-id="c4c3e-331">Keine.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-331">None.</span></span>|<span data-ttu-id="c4c3e-332">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c4c3e-332">NULLABLE</span></span>|  
|<span data-ttu-id="c4c3e-333">Binäre Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c4c3e-333">Binary string</span></span>|<span data-ttu-id="c4c3e-334">`SQLBINARY` und `SQLVARYBIN`</span><span class="sxs-lookup"><span data-stu-id="c4c3e-334">`SQLBINARY` and `SQLVARYBIN`</span></span>|<span data-ttu-id="c4c3e-335">Keine.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-335">None.</span></span>|<span data-ttu-id="c4c3e-336">NULLABLE, LENGTH</span><span class="sxs-lookup"><span data-stu-id="c4c3e-336">NULLABLE, LENGTH</span></span>|  
|<span data-ttu-id="c4c3e-337">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c4c3e-337">Character string</span></span>|<span data-ttu-id="c4c3e-338">`SQLCHAR`, `SQLVARYCHAR`, `SQLNCHAR` und `SQLNVARCHAR`</span><span class="sxs-lookup"><span data-stu-id="c4c3e-338">`SQLCHAR`, `SQLVARYCHAR`, `SQLNCHAR`, and `SQLNVARCHAR`</span></span>|<span data-ttu-id="c4c3e-339">Keine.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-339">None.</span></span>|<span data-ttu-id="c4c3e-340">NULLABLE, LENGTH</span><span class="sxs-lookup"><span data-stu-id="c4c3e-340">NULLABLE, LENGTH</span></span>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c4c3e-341">Verwenden Sie in der Formatdatei einen der folgenden Datentypen für den Massenexport oder -import von SQLXML-Daten: SQLCHAR oder SQLVARYCHAR (die Daten werden in der Clientcodepage oder in der Codepage, die durch die Sortierung impliziert wird, gesendet), SQLNCHAR oder SQLNVARCHAR (die Daten werden als Unicode gesendet) oder SQLBINARY oder SQLVARYBIN (die Daten werden ohne Konvertierung gesendet).</span><span class="sxs-lookup"><span data-stu-id="c4c3e-341">To bulk export or import SQLXML data, use one of the following data types in your format file: SQLCHAR or SQLVARYCHAR (the data is sent in the client code page or in the code page implied by the collation), SQLNCHAR or SQLNVARCHAR (the data is sent as Unicode), or SQLBINARY or SQLVARYBIN (the data is sent without any conversion).</span></span>  
  
 <span data-ttu-id="c4c3e-342">Weitere Informationen zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datentypen finden Sie unter [Datentypen &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c4c3e-342">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
###  <a name="how-bulk-import-uses-the-row-element"></a><a name="HowUsesROW"></a> <span data-ttu-id="c4c3e-343">Verwendung des \<ROW>-Elements beim Massenimport</span><span class="sxs-lookup"><span data-stu-id="c4c3e-343">How Bulk Import Uses the \<ROW> Element</span></span>  
 <span data-ttu-id="c4c3e-344">Das \<ROW>-Element wird in bestimmten Kontexten ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-344">The \<ROW> element is ignored in some contexts.</span></span> <span data-ttu-id="c4c3e-345">Ob sich das \<ROW>-Element auf einen Massenimportvorgang auswirkt, hängt davon ab, wie der Vorgang durchgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="c4c3e-345">Whether the \<ROW> element affects a bulk-import operation depends on how the operation is performed:</span></span>  
  
-   <span data-ttu-id="c4c3e-346">Befehl **bcp**</span><span class="sxs-lookup"><span data-stu-id="c4c3e-346">the **bcp** command</span></span>  
  
     <span data-ttu-id="c4c3e-347">Wenn Daten in eine Zieltabelle geladen werden, ignoriert **bcp** die \<ROW>-Komponente.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-347">When data is loaded into a target table, **bcp** ignores the \<ROW> component.</span></span> <span data-ttu-id="c4c3e-348">Stattdessen lädt **bcp** die Daten auf der Grundlage der Spaltentypen der Zieltabelle.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-348">Instead, **bcp** loads the data based on the column types of the target table.</span></span>  
  
-   [!INCLUDE[tsql](../../../includes/tsql-md.md)] <span data-ttu-id="c4c3e-349">-Anweisungen (BULK INSERT und der OPENROWSET-Massenrowsetanbieter)</span><span class="sxs-lookup"><span data-stu-id="c4c3e-349">statements (BULK INSERT and OPENROWSET's Bulk rowset provider)</span></span>  
  
     <span data-ttu-id="c4c3e-350">Beim Massenimport von Daten in eine Tabelle verwenden [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Anweisungen die \<ROW>-Komponente, um das Eingaberowset zu generieren.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-350">When bulk importing data into a table, [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements use the \<ROW> component to generate the input rowset.</span></span> <span data-ttu-id="c4c3e-351">Darüber hinaus führen [!INCLUDE[tsql](../../../includes/tsql-md.md)]-Anweisungen auf Grundlage der unter \<ROW> angegebenen Spaltentypen und der entsprechenden Spalte in der Zieltabelle die erforderlichen Typkonvertierungen durch.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-351">Also, [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements perform appropriate type conversions based on the column types specified under \<ROW> and the corresponding column in the target table.</span></span> <span data-ttu-id="c4c3e-352">Besteht eine Nichtübereinstimmung zwischen den Spaltentypen, die in der Formatdatei und in der Zieltabelle angegeben sind, wird eine zusätzliche Typkonvertierung durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-352">If a mismatch exists between column types as specified in the format file and in the target table, an extra type conversion occurs.</span></span> <span data-ttu-id="c4c3e-353">Aufgrund dieser zusätzlichen Typkonvertierung kann es zu einer Diskrepanz (d. h. einem Genauigkeitsverlust) im Verhalten von BULK INSERT bzw. des OPENROWSET-Massenrowsetanbieters verglichen mit **bcp**kommen.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-353">This extra type conversion may lead to some discrepancy (that is, a loss of precision) in behavior in BULK INSERT or OPENROWSET's Bulk rowset provider as compared to **bcp**.</span></span>  
  
     <span data-ttu-id="c4c3e-354">Anhand der Informationen im \<ROW>-Element kann eine Zeile erstellt werden, ohne dass zusätzliche Informationen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-354">The information in the \<ROW> element allows a row to be constructed without requiring any additional information.</span></span> <span data-ttu-id="c4c3e-355">Aus diesem Grund können Sie ein Rowset mithilfe einer SELECT-Anweisung generieren (SELECT \* FROM OPENROWSET(BULK *datafile* FORMATFILE=*xmlformatfile*).</span><span class="sxs-lookup"><span data-stu-id="c4c3e-355">For this reason, you can generate a rowset using a SELECT statement (SELECT \* FROM OPENROWSET(BULK *datafile* FORMATFILE=*xmlformatfile*).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c4c3e-356">Die OPENROWSET BULK-Klausel erfordert eine Formatdatei (beachten Sie, dass eine Konvertierung vom Datentyp des Felds in den Datentyp der Spalte nur mit einer XML-Formatdatei möglich ist).</span><span class="sxs-lookup"><span data-stu-id="c4c3e-356">The OPENROWSET BULK clause requires a format file (note that converting from the data type of the field to the data type of a column is available only with an XML format file).</span></span>  
  
###  <a name="how-bulk-import-uses-the-column-element"></a><a name="HowUsesColumn"></a> <span data-ttu-id="c4c3e-357">Verwendung des \<COLUMN>-Elements beim Massenimport</span><span class="sxs-lookup"><span data-stu-id="c4c3e-357">How Bulk Import Uses the \<COLUMN> Element</span></span>  
 <span data-ttu-id="c4c3e-358">Die \<COLUMN>-Elemente in einer Formatdatei ordnen durch die folgenden Angaben den Tabellenspalten ein Datendateifeld zu, um einen Massenimport von Daten in eine Tabelle auszuführen:</span><span class="sxs-lookup"><span data-stu-id="c4c3e-358">For bulk importing data into a table, the \<COLUMN> elements in a format file map a data-file field to table columns by specifying:</span></span>  
  
-   <span data-ttu-id="c4c3e-359">Die Position jedes Felds innerhalb einer Zeile in der Datendatei.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-359">The position of each field within a row in the data file.</span></span>  
  
-   <span data-ttu-id="c4c3e-360">Der Spaltentyp, der verwendet wird, um den Felddatentyp in den gewünschten Spaltendatentyp zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-360">The column type, which is used to convert the field data type to the desired column data type.</span></span>  
  
 <span data-ttu-id="c4c3e-361">Falls einem Feld keine Spalte zugeordnet ist, wird das Feld nicht in die generierte(n) Zeile(n) kopiert.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-361">If no column is mapped to a field, the field is not copied into the generated row(s).</span></span> <span data-ttu-id="c4c3e-362">Dieses Verhalten ermöglicht, dass eine Datendatei Zeilen mit unterschiedlichen Spalten (in verschiedenen Tabellen) generieren kann.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-362">This behavior allows a data file to generate rows with different columns (in different tables).</span></span>  
  
 <span data-ttu-id="c4c3e-363">Entsprechend ordnet beim Massenexport von Daten aus einer Tabelle jedes \<COLUMN>-Element in der Formatdatei die Spalte aus der Eingabetabellenzeile dem entsprechenden Feld in der Ausgabedatendatei zu.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-363">Similarly, for bulk exporting data from a table, each \<COLUMN> in the format file maps the column from the input table row to its corresponding field in the output data file.</span></span>  
  
###  <a name="putting-the-xsitype-value-into-a-data-set"></a><a name="PutXsiTypeValueIntoDataSet"></a> <span data-ttu-id="c4c3e-364">Einfügen des xsi:type-Werts in ein Dataset</span><span class="sxs-lookup"><span data-stu-id="c4c3e-364">Putting the xsi:type Value into a Data Set</span></span>  
 <span data-ttu-id="c4c3e-365">Wird ein XML-Dokument durch die XSD-Sprache (XML Schema Definition) überprüft, wird der xsi:type-Wert nicht in das Dataset eingefügt.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-365">When an XML document is validated through the XML Schema Definition (XSD) language, the xsi:type value is not put into the data set.</span></span> <span data-ttu-id="c4c3e-366">Sie können die xsi:type-Informationen jedoch in das Dataset einfügen, indem Sie die XML-Formatdatei in ein XML-Dokument laden (z. B. `myDoc`), wie durch den folgenden Codeausschnitt veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="c4c3e-366">However, you can put the xsi:type information into the data set by loading the XML format file into an XML document (for example, `myDoc`), as illustrated in the following code snippet:</span></span>  
  
```  
...;  
myDoc.LoadXml(xmlFormat);  
XmlNodeList ColumnList = myDoc.GetElementsByTagName("COLUMN");  
for(int i=0;i<ColumnList.Count;i++)  
{  
   Console.Write("COLUMN: xsi:type=" +ColumnList[i].Attributes["type",  
      "http://www.w3.org/2001/XMLSchema-instance"].Value+"\n");  
}  
```  
  
##  <a name="sample-xml-format-files"></a><a name="SampleXmlFFs"></a> <span data-ttu-id="c4c3e-367">Beispiele für XML-Formatdateien</span><span class="sxs-lookup"><span data-stu-id="c4c3e-367">Sample XML Format Files</span></span>  
 <span data-ttu-id="c4c3e-368">Dieser Abschnitt enthält Informationen zum Verwenden von XML-Formatdateien in verschiedenen Situationen, u. a. ein [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] -Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-368">This section contains information on using XML format files in a variety of cases, including an [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] example.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c4c3e-369">In den Datendateien, die in den folgenden Beispielen gezeigt werden, steht `<tab>` für ein Tabstoppzeichen in einer Datendatei, und `<return>` steht für einen Wagenrücklauf.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-369">In the data files shown in the following examples, `<tab>` indicates a tab character in a data file, and `<return>` indicates a carriage return.</span></span>  
  

  
> [!NOTE]  
>  <span data-ttu-id="c4c3e-370">Informationen zum Erstellen einer Formatdatei finden Sie unter [Erstellen einer Formatdatei &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c4c3e-370">For information about how to create format files, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
###  <a name="a-ordering-character-data-fields-the-same-as-table-columns"></a><a name="OrderCharFieldsSameAsCols"></a> <span data-ttu-id="c4c3e-371">A.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-371">A.</span></span> <span data-ttu-id="c4c3e-372">Gleiches Anordnen von Zeichendatenfeldern und Tabellenspalten</span><span class="sxs-lookup"><span data-stu-id="c4c3e-372">Ordering character-data fields the same as table columns</span></span>  
 <span data-ttu-id="c4c3e-373">Das folgende Beispiel zeigt eine XML-Formatdatei, die eine Datendatei beschreibt, in der drei Felder mit Zeichendaten enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-373">The following example shows an XML format file that describes a data file containing three fields of character data.</span></span> <span data-ttu-id="c4c3e-374">Die Formatdatei ordnet die Datendatei einer Tabelle zu, die drei Spalten enthält.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-374">The format file maps the data file to a table that contains three columns.</span></span> <span data-ttu-id="c4c3e-375">Die Datenfelder entsprechen den Spalten der Tabelle eins zu eins.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-375">The data fields correspond one-to-one with the columns of the table.</span></span>  
  
 <span data-ttu-id="c4c3e-376">**Tabelle (Zeile):** Person (Age int, FirstName varchar(20), LastName varchar(30))</span><span class="sxs-lookup"><span data-stu-id="c4c3e-376">**Table (row):** Person (Age int, FirstName varchar(20), LastName varchar(30))</span></span>  
  
 <span data-ttu-id="c4c3e-377">**Datendatei (Datensatz):** Age\<tab>Firstname\<tab>Lastname\<return></span><span class="sxs-lookup"><span data-stu-id="c4c3e-377">**Data file (record):** Age\<tab>Firstname\<tab>Lastname\<return></span></span>  
  
 <span data-ttu-id="c4c3e-378">Die folgende XML-Formatdatei liest aus der Datendatei in die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-378">The following XML format file reads from the data file to the table.</span></span>  
  
 <span data-ttu-id="c4c3e-379">Im `<RECORD>` -Element stellt die Formatdatei die Datenwerte in allen drei Feldern als Zeichendaten dar.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-379">In the `<RECORD>` element, the format file represents the data values in all three fields as character data.</span></span> <span data-ttu-id="c4c3e-380">Für jedes Feld gibt das `TERMINATOR` -Attribut das Abschlusszeichen an, das dem Datenwert folgt.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-380">For each field, the `TERMINATOR` attribute indicates the terminator that follows the data value.</span></span>  
  
 <span data-ttu-id="c4c3e-381">Die Datenfelder entsprechen den Spalten der Tabelle eins zu eins.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-381">The data fields correspond one-to-one with the columns of the table.</span></span> <span data-ttu-id="c4c3e-382">Im `<ROW>` -Element ordnet die Formatdatei die `Age` -Spalte dem ersten Feld, die `FirstName` -Spalte dem zweiten Feld und die `LastName` -Spalte dem dritten Feld zu.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-382">In the `<ROW>` element, the format file maps the column `Age` to the first field, the column `FirstName` to the second field, and the column `LastName` to the third field.</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT   
xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <RECORD>  
    <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="12"/>   
    <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="20" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
    <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\r\n"   
      MAX_LENGTH="30"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  </RECORD>  
  <ROW>  
    <COLUMN SOURCE="1" NAME="age" xsi:type="SQLINT"/>  
    <COLUMN SOURCE="2" NAME="firstname" xsi:type="SQLVARYCHAR"/>  
    <COLUMN SOURCE="3" NAME="lastname" xsi:type="SQLVARYCHAR"/>  
  </ROW>  
</BCPFORMAT>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="c4c3e-383">Ein entsprechendes [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] Beispiel finden Sie unter [Erstellen einer Formatdatei &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c4c3e-383">For an equivalent [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] example, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
###  <a name="b-ordering-data-fields-and-table-columns-differently"></a><a name="OrderFieldsAndColsDifferently"></a> <span data-ttu-id="c4c3e-384">B.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-384">B.</span></span> <span data-ttu-id="c4c3e-385">Unterschiedliches Anordnen von Datenfeldern und Tabellenspalten</span><span class="sxs-lookup"><span data-stu-id="c4c3e-385">Ordering data fields and table columns differently</span></span>  
 <span data-ttu-id="c4c3e-386">Das folgende Beispiel zeigt eine XML-Formatdatei, die eine Datendatei beschreibt, in der drei Felder mit Zeichendaten enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-386">The following example shows an XML format file that describes a data file containing three fields of character data.</span></span> <span data-ttu-id="c4c3e-387">Die Formatdatei ordnet die Datendatei einer Tabelle zu, die drei Spalten enthält, die anders angeordnet sind als die Felder der Datendatei.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-387">The format file maps the data file to a table that contains three columns that are ordered differently from the fields of the data file.</span></span>  
  
 <span data-ttu-id="c4c3e-388">**Tabelle (Zeile):** Person (Age int, FirstName varchar(20), LastName varchar(30))</span><span class="sxs-lookup"><span data-stu-id="c4c3e-388">**Table (row):** Person (Age int, FirstName varchar(20), LastName varchar(30))</span></span>  
  
 <span data-ttu-id="c4c3e-389">**Datendatei (Datensatz):** Alter\<tab>LastName\<tab>FirstName\<return></span><span class="sxs-lookup"><span data-stu-id="c4c3e-389">**Data file** (record): Age\<tab>Lastname\<tab>Firstname\<return></span></span>  
  
 <span data-ttu-id="c4c3e-390">Im `<RECORD>` -Element stellt die Formatdatei die Datenwerte in allen drei Feldern als Zeichendaten dar.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-390">In the `<RECORD>` element, the format file represents the data values in all three fields as character data.</span></span>  
  
 <span data-ttu-id="c4c3e-391">Im `<ROW>` -Element ordnet die Formatdatei die `Age` -Spalte dem ersten Feld, die `FirstName` -Spalte dem dritten Feld und die `LastName` -Spalte dem zweiten Feld zu.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-391">In the `<ROW>` element, the format file maps the column `Age` to the first field, the column `FirstName` to the third field, and the column `LastName` to the second field.</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT   
xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <RECORD>  
    <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="12"/>  
    <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\t" MAX_LENGTH="20"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
    <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\r\n"   
      MAX_LENGTH="30" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  </RECORD>  
  <ROW>  
    <COLUMN SOURCE="1" NAME="age" xsi:type="SQLINT"/>  
    <COLUMN SOURCE="3" NAME="firstname" xsi:type="SQLVARYCHAR"/>  
    <COLUMN SOURCE="2" NAME="lastname" xsi:type="SQLVARYCHAR"/>  
  </ROW>  
</BCPFORMAT>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="c4c3e-392">Ein entsprechendes [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] Beispiel finden Sie unter [Verwenden einer Formatdatei zum Zuordnen von Tabellenspalten zu Datendateifeldern &#40;SQL Server&#41;](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c4c3e-392">For an equivalent [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] example, see [Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md).</span></span>  
  
### <a name="c-omitting-a-data-field"></a><span data-ttu-id="c4c3e-393">C.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-393">C.</span></span> <span data-ttu-id="c4c3e-394">Auslassen eines Datenfelds</span><span class="sxs-lookup"><span data-stu-id="c4c3e-394">Omitting a data field</span></span>  
 <span data-ttu-id="c4c3e-395">Das folgende Beispiel zeigt eine XML-Formatdatei, die eine Datendatei beschreibt, in der vier Felder mit Zeichendaten enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-395">The following example shows an XML format file that describes a data file containing four fields of character data.</span></span> <span data-ttu-id="c4c3e-396">Die Formatdatei ordnet die Datendatei einer Tabelle zu, die drei Spalten enthält.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-396">The format file maps the data file to a table that contains three columns.</span></span> <span data-ttu-id="c4c3e-397">Das zweite Datenfeld entspricht keiner Tabellenspalte.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-397">The second data field does not correspond to any table column.</span></span>  
  
 <span data-ttu-id="c4c3e-398">**Tabelle (Zeile):** Person (Age int, FirstName varchar(20), LastName varchar(30))</span><span class="sxs-lookup"><span data-stu-id="c4c3e-398">**Table (row):** Person (Age int, FirstName Varchar(20), LastName Varchar(30))</span></span>  
  
 <span data-ttu-id="c4c3e-399">**Datendatei (Datensatz):** Age\<tab>employeeID\<tab>Firstname\<tab>Lastname\<return></span><span class="sxs-lookup"><span data-stu-id="c4c3e-399">**Data file (record):** Age\<tab>employeeID\<tab>Firstname\<tab>Lastname\<return></span></span>  
  
 <span data-ttu-id="c4c3e-400">Im `<RECORD>` -Element stellt die Formatdatei die Datenwerte in allen vier Feldern als Zeichendaten dar.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-400">In the `<RECORD>` element, the format file represents the data values in all four fields as character data.</span></span> <span data-ttu-id="c4c3e-401">Für jedes Feld gibt das TERMINATOR-Attribut das Abschlusszeichen an, das dem Datenwert folgt.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-401">For each field, the TERMINATOR attribute indicates the terminator that follows the data value.</span></span>  
  
 <span data-ttu-id="c4c3e-402">Im `<ROW>` -Element ordnet die Formatdatei die `Age` -Spalte dem ersten Feld, die `FirstName` -Spalte dem dritten Feld und die `LastName` -Spalte dem vierten Feld zu.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-402">In the `<ROW>` element, the format file maps the column `Age` to the first field, the column `FirstName` to the third field, and the column `LastName` to the fourth field.</span></span>  
  
```  
<BCPFORMAT   
xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <RECORD>  
    <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="12"/>  
    <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="10"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
    <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="20"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
    <FIELD ID="4" xsi:type="CharTerm" TERMINATOR="\r\n"   
      MAX_LENGTH="30"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  </RECORD>  
  <ROW>  
    <COLUMN SOURCE="1" NAME="age" xsi:type="SQLINT"/>  
    <COLUMN SOURCE="3" NAME="firstname" xsi:type="SQLVARYCHAR"/>  
    <COLUMN SOURCE="4" NAME="lastname" xsi:type="SQLVARYCHAR"/>  
  </ROW>  
</BCPFORMAT>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="c4c3e-403">Ein entsprechendes [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] Beispiel finden Sie unter [Auslassen eines Datenfelds mithilfe einer Formatdatei &#40;SQL Server&#41;](use-a-format-file-to-skip-a-data-field-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c4c3e-403">For an equivalent [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] example, see [Use a Format File to Skip a Data Field &#40;SQL Server&#41;](use-a-format-file-to-skip-a-data-field-sql-server.md).</span></span>  
  
###  <a name="d-mapping-field-xsitype-to-column-xsitype"></a><a name="MapXSItype"></a> <span data-ttu-id="c4c3e-404">D.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-404">D.</span></span> <span data-ttu-id="c4c3e-405">Zuordnung xsi:type-Wert für \<FIELD> zu xsi:type-Wert für \<COLUMN></span><span class="sxs-lookup"><span data-stu-id="c4c3e-405">Mapping \<FIELD> xsi:type to \<COLUMN> xsi:type</span></span>  
 <span data-ttu-id="c4c3e-406">Das folgende Beispiel zeigt verschiedene Typen von Feldern und ihre Zuordnungen zu Spalten.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-406">The following example shows different types of fields and their mappings to columns.</span></span>  
  
```  
<?xml version = "1.0"?>  
<BCPFORMAT  
xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
   xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
   <RECORD>  
      <FIELD xsi:type="CharTerm" ID="C1" TERMINATOR="\t"   
            MAX_LENGTH="4"/>  
      <FIELD xsi:type="CharFixed" ID="C2" LENGTH="10"   
         COLLATION="SQL_LATIN1_GENERAL_CP1_CI_AS"/>  
      <FIELD xsi:type="CharPrefix" ID="C3" PREFIX_LENGTH="2"   
         MAX_LENGTH="32" COLLATION="SQL_LATIN1_GENERAL_CP1_CI_AS"/>  
      <FIELD xsi:type="NCharTerm" ID="C4" TERMINATOR="\t"   
         MAX_LENGTH="4"/>  
      <FIELD xsi:type="NCharFixed" ID="C5" LENGTH="10"   
         COLLATION="SQL_LATIN1_GENERAL_CP1_CI_AS"/>  
      <FIELD xsi:type="NCharPrefix" ID="C6" PREFIX_LENGTH="2"   
         MAX_LENGTH="32" COLLATION="SQL_LATIN1_GENERAL_CP1_CI_AS"/>  
      <FIELD xsi:type="NativeFixed" ID="C7" LENGTH="4"/>  
   </RECORD>  
   <ROW>  
      <COLUMN SOURCE="C1" NAME="Age" xsi:type="SQLTINYINT"/>  
      <COLUMN SOURCE="C2" NAME="FirstName" xsi:type="SQLVARYCHAR"   
      LENGTH="16" NULLABLE="NO"/>  
      <COLUMN SOURCE="C3" NAME="LastName" />  
      <COLUMN SOURCE="C4" NAME="Salary" xsi:type="SQLMONEY"/>  
      <COLUMN SOURCE="C5" NAME="Picture" xsi:type="SQLIMAGE"/>  
      <COLUMN SOURCE="C6" NAME="Bio" xsi:type="SQLTEXT"/>  
      <COLUMN SOURCE="C7" NAME="Interest"xsi:type="SQLDECIMAL"   
      PRECISION="5" SCALE="3"/>  
   </ROW>  
</BCPFORMAT>  
```  
  
###  <a name="e-mapping-xml-data-to-a-table"></a><a name="MapXMLDataToTbl"></a> <span data-ttu-id="c4c3e-407">E.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-407">E.</span></span> <span data-ttu-id="c4c3e-408">Zuordnen von XML-Daten zu einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="c4c3e-408">Mapping XML data to a table</span></span>  
 <span data-ttu-id="c4c3e-409">Im folgenden Beispiel wird eine leere zweispaltige Tabelle (`t_xml`) erstellt, in der die erste Spalte dem `int` -Datentyp und die zweite Spalte dem `xml` -Datentyp zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-409">The following example creates an empty two-column table (`t_xml`), in which the first column maps to the `int` data type and the second column maps to the `xml` data type.</span></span>  
  
```  
CREATE TABLE t_xml (c1 int, c2 xml)  
```  
  
 <span data-ttu-id="c4c3e-410">Die folgende XML-Formatdatei lädt eine Datendatei in die `t_xml`-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-410">The following XML format file would load a data file into table `t_xml`.</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
 <RECORD>  
  <FIELD ID="1" xsi:type="NativePrefix" PREFIX_LENGTH="1"/>  
  <FIELD ID="2" xsi:type="NCharPrefix" PREFIX_LENGTH="8"/>  
 </RECORD>  
 <ROW>  
  <COLUMN SOURCE="1" NAME="c1" xsi:type="SQLINT"/>  
  <COLUMN SOURCE="2" NAME="c2" xsi:type="SQLNCHAR"/>  
 </ROW>  
</BCPFORMAT>  
```  
  
###  <a name="f-importing-fixed-length-or-fixed-width-fields"></a><a name="ImportFixedFields"></a> <span data-ttu-id="c4c3e-411">F.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-411">F.</span></span> <span data-ttu-id="c4c3e-412">Importieren von Feldern mit fester Länge oder fester Breite</span><span class="sxs-lookup"><span data-stu-id="c4c3e-412">Importing fixed-length or fixed-width fields</span></span>  
 <span data-ttu-id="c4c3e-413">Im folgenden Beispiel werden Felder mit einer festen Länge bzw. Breite von jeweils `10` und `6` Zeichen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-413">The following example describes fixed fields of `10` or `6` characters each.</span></span> <span data-ttu-id="c4c3e-414">Die Formatdatei stellt diese Feldlängen bzw. -breiten als `LENGTH="10"` und `LENGTH="6"`dar.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-414">The format file represents these field lengths/widths as `LENGTH="10"` and `LENGTH="6"`, respectively.</span></span> <span data-ttu-id="c4c3e-415">Jede Zeile der Datendatei endet mit einer Kombination von Wagenrücklauf/Zeilenvorschub, {CR}{LF}, was in der Formatdatei als `TERMINATOR="\r\n"`dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-415">Every row of the data files ends with a carriage return-line feed combination, {CR}{LF}, which the format file represents as `TERMINATOR="\r\n"`.</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT  
       xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"  
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <RECORD>  
    <FIELD ID="1" xsi:type="CharFixed" LENGTH="10"/>  
    <FIELD ID="2" xsi:type="CharFixed" LENGTH="6"/>  
    <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\r\n"  
  </RECORD>  
  <ROW>  
    <COLUMN SOURCE="1" NAME="C1" xsi:type="SQLINT" />  
    <COLUMN SOURCE="2" NAME="C2" xsi:type="SQLINT" />  
  </ROW>  
</BCPFORMAT>  
```  
  
###  <a name="additional-examples"></a><a name="AdditionalExamples"></a> <span data-ttu-id="c4c3e-416">Zusätzliche Beispiele</span><span class="sxs-lookup"><span data-stu-id="c4c3e-416">Additional Examples</span></span>  
 <span data-ttu-id="c4c3e-417">Die folgenden Themen enthalten weitere Beispiele sowohl für Nicht-XML-Dateien als auch für XML-Formatdateien:</span><span class="sxs-lookup"><span data-stu-id="c4c3e-417">For additional examples of both non-XML format files and XML format files, see the following topics:</span></span>  
  
-   [<span data-ttu-id="c4c3e-418">Überspringen einer Tabellenspalte mithilfe einer Formatdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3e-418">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
-   [<span data-ttu-id="c4c3e-419">Auslassen eines Datenfelds mithilfe einer Formatdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3e-419">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="c4c3e-420">Verwenden einer Formatdatei zum Zuordnen von Tabellenspalten zu Datendateifeldern &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3e-420">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="c4c3e-421">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="c4c3e-421">Related Tasks</span></span>  
  
-   [<span data-ttu-id="c4c3e-422">Erstellen einer Formatdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3e-422">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="c4c3e-423">Massenimport von Daten mithilfe einer Formatdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3e-423">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="c4c3e-424">Überspringen einer Tabellenspalte mithilfe einer Formatdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3e-424">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
-   [<span data-ttu-id="c4c3e-425">Auslassen eines Datenfelds mithilfe einer Formatdatei &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3e-425">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="c4c3e-426">Verwenden einer Formatdatei zum Zuordnen von Tabellenspalten zu Datendateifeldern &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3e-426">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="c4c3e-427">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="c4c3e-427">Related Content</span></span>  
 <span data-ttu-id="c4c3e-428">Keine.</span><span class="sxs-lookup"><span data-stu-id="c4c3e-428">None.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4c3e-429">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c4c3e-429">See Also</span></span>  
 <span data-ttu-id="c4c3e-430">[Massenimport und -export von Daten &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c4c3e-430">[Bulk Import and Export of Data &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span></span>  
 <span data-ttu-id="c4c3e-431">[Datentypen &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c4c3e-431">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="c4c3e-432">[Nicht-XML-Formatdateien &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c4c3e-432">[Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span></span>  
 [<span data-ttu-id="c4c3e-433">Formatdateien zum Importieren oder Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c4c3e-433">Format Files for Importing or Exporting Data &#40;SQL Server&#41;</span></span>](format-files-for-importing-or-exporting-data-sql-server.md)  
  
  
