---
title: Verwenden des Abfrage-und Sicht-Designers bei internationalen Daten (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- Visual Database Tools [SQL Server], international data
- queries [SQL Server], international data
- languages [SQL Server], Query and View Designer
- international considerations [SQL Server], Query and View Designer
- Criteria pane
- View Designer, international data
- Query Designer [SQL Server], international data
- localized information in Query and View Designer [SQL Server]
- global considerations [SQL Server], Query and View Designer
- SQL pane [Visual Database Tools]
- multiple language support [SQL Server], Query and View Designer
ms.assetid: 4b51c56f-f902-4e72-b919-e36127369b63
author: stevestein
ms.author: sstein
ms.openlocfilehash: 905e4c6909c792b019c11ef95662a7ec1a113bb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719291"
---
# <a name="use-the-query-and-view-designer-with-international-data-visual-database-tools"></a><span data-ttu-id="0bcbe-102">Verwenden des Abfrage- und Sicht-Designers bei internationalen Daten (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="0bcbe-102">Use the Query and View Designer with International Data (Visual Database Tools)</span></span>
  <span data-ttu-id="0bcbe-103">Sie können den [Abfrage- und Sicht-Designer](visual-database-tools.md) mit Daten in jeder Sprache und mit jeder Version des Betriebssystems Windows verwenden.</span><span class="sxs-lookup"><span data-stu-id="0bcbe-103">You can use the [Query and View Designer](visual-database-tools.md) with data in any language and in any version of the Windows operating system.</span></span> <span data-ttu-id="0bcbe-104">In den folgenden Richtlinien werden die Unterschiede erläutert und Informationen zur Datenverwaltung in internationalen Anwendungen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="0bcbe-104">The following guidelines outline the differences you will notice and provide information about managing data in international applications.</span></span>  
  
## <a name="localized-information-in-the-criteria-and-sql-panes"></a><span data-ttu-id="0bcbe-105">Lokalisierte Informationen im Kriterien- und im SQL-Bereich</span><span class="sxs-lookup"><span data-stu-id="0bcbe-105">Localized Information in the Criteria and SQL Panes</span></span>  
 <span data-ttu-id="0bcbe-106">Wenn Sie eine Abfrage im Kriterienbereich erstellen, können Sie die Informationen in dem Format eingeben, das den Ländereinstellungen von Windows auf dem Computer entspricht.</span><span class="sxs-lookup"><span data-stu-id="0bcbe-106">If you are using the Criteria pane to create your query, you can enter information in the format that corresponds to the Windows Regional Settings for you computer.</span></span> <span data-ttu-id="0bcbe-107">Wenn Sie z. B. nach Daten suchen, können Sie die Daten in den Spalten Kriterien in dem für Sie gewohnten Format eingeben, wobei jedoch folgende Ausnahmen zu beachten sind:</span><span class="sxs-lookup"><span data-stu-id="0bcbe-107">For example, if you are searching for data, you can enter the data in the Criteria columns using whatever format you are accustomed to using, with these exceptions:</span></span>  
  
-   <span data-ttu-id="0bcbe-108">Lange Datenformate werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0bcbe-108">Long data formats are not supported.</span></span>  
  
-   <span data-ttu-id="0bcbe-109">Währungssymbole sollten im Kriterienbereich nicht eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0bcbe-109">Currency symbols should not be entered in the Criteria pane.</span></span>  
  
-   <span data-ttu-id="0bcbe-110">Währungssymbole werden im Ergebnisbereich nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0bcbe-110">Currency symbols will not display in the Results pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0bcbe-111">Sie können im Ergebnisbereich zwar das Währungssymbol eingeben, das den Ländereinstellungen von Windows auf dem Computer entspricht, das Symbol wird jedoch entfernt und im Ergebnisbereich nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0bcbe-111">In the Results pane, you can actually enter the currency symbol that corresponds to the Windows Regional Settings for your computer, but the symbol will be removed and will not display in the Results pane.</span></span>  
  
-   <span data-ttu-id="0bcbe-112">Ein unäres Minus wird immer links angezeigt (z. B. -1), unabhängig von den in den Ländereinstellungen gewählten Optionen.</span><span class="sxs-lookup"><span data-stu-id="0bcbe-112">Unary minus always appears on the left side (for example, -1) regardless of the Regional Settings options.</span></span>  
  
 <span data-ttu-id="0bcbe-113">Dagegen müssen Daten und Schlüsselwörter im SQL-Bereich immer im ANSI-Format (U.S.) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0bcbe-113">In contrast, data and keywords in the SQL pane must always be in ANSI (U.S.) format.</span></span> <span data-ttu-id="0bcbe-114">Beispielsweise fügt der Abfrage- und Sicht-Designer beim Erstellen einer Abfrage alle SQL-Schlüsselwörter wie SELECT oder FROM im ANSI-Format ein.</span><span class="sxs-lookup"><span data-stu-id="0bcbe-114">For example, as the Query and View Designer builds a query, it inserts the ANSI form of all SQL keywords such as SELECT and FROM.</span></span> <span data-ttu-id="0bcbe-115">Achten Sie beim Hinzufügen von Elementen zu Anweisungen im SQL-Bereich darauf, für diese Elemente die ANSI-Standardform zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0bcbe-115">If you add elements to the statement in the SQL pane, be sure to use the ANSI standard form for the elements.</span></span>  
  
 <span data-ttu-id="0bcbe-116">Wenn Sie im Kriterienbereich Daten in einem gebietsspezifischen Format eingeben, wandelt der Abfrage- und Sicht-Designer diese Eingaben für den SQL-Bereich automatisch in das ANSI-Format um.</span><span class="sxs-lookup"><span data-stu-id="0bcbe-116">When you enter data using local-specific format in the Criteria pane, the Query and View Designer automatically translates it to ANSI format in the SQL pane.</span></span> <span data-ttu-id="0bcbe-117">Wenn die Ländereinstellungen des Computers z. B. auf die Option Deutsch (Standard) festgelegt sind, können Sie im Kriterienbereich ein Datum u. a. im Format "31.12.96" eingeben.</span><span class="sxs-lookup"><span data-stu-id="0bcbe-117">For example, if your Regional Settings are set to Standard German, you can enter data in the Criteria pane in a format such as "31.12.96."</span></span> <span data-ttu-id="0bcbe-118">Allerdings wird das Datum im SQL-Bereich im ANSI-Datums- und Zeitformat als `{ ts '1996-12-31 00:00:00' }.` angezeigt. Wenn Sie Daten direkt im SQL-Bereich eingeben, müssen Sie diese im ANSI-Format eingeben.</span><span class="sxs-lookup"><span data-stu-id="0bcbe-118">However, the date will appear in the SQL pane in ANSI datetime format as `{ ts '1996-12-31 00:00:00' }.` If you enter data directly in the SQL pane, you must enter it in ANSI format.</span></span>  
  
## <a name="sort-order"></a><span data-ttu-id="0bcbe-119">Sortierreihenfolge</span><span class="sxs-lookup"><span data-stu-id="0bcbe-119">Sort Order</span></span>  
 <span data-ttu-id="0bcbe-120">Die in Abfragen für Daten verwendete Sortierreihenfolge wird durch die verwendete Datenbank vorgegeben.</span><span class="sxs-lookup"><span data-stu-id="0bcbe-120">The sort order of data in your query is determined by the database.</span></span> <span data-ttu-id="0bcbe-121">Im Dialogfeld Ländereinstellungen von Windows ausgewählte Optionen haben keinen Einfluss auf die Sortierreihenfolge für Abfragen.</span><span class="sxs-lookup"><span data-stu-id="0bcbe-121">Options that you set in the Windows Regional Settings dialog box do not affect sort order for queries.</span></span> <span data-ttu-id="0bcbe-122">Sie haben jedoch die Möglichkeit, für einzelne Abfragen eine spezielle Reihenfolge für die Zeilenausgabe anzufordern.</span><span class="sxs-lookup"><span data-stu-id="0bcbe-122">Within any particular query, however, you can request that rows be returned in a particular order.</span></span>  
  
## <a name="using-double-byte-characters"></a><span data-ttu-id="0bcbe-123">Verwenden von Doppelbytezeichen</span><span class="sxs-lookup"><span data-stu-id="0bcbe-123">Using Double-Byte Characters</span></span>  
 <span data-ttu-id="0bcbe-124">Sie können DBCS-Zeichen für Literalwerte und für Namen von Datenbankobjekten, wie Tabellen- und Sichtnamen oder Aliase, eingeben.</span><span class="sxs-lookup"><span data-stu-id="0bcbe-124">You can enter DBCS characters for literals and for database object names such as table and view names or aliases.</span></span> <span data-ttu-id="0bcbe-125">Weiterhin sind DBCS-Zeichen in Parameternamen und Parametermarkierungszeichen zulässig.</span><span class="sxs-lookup"><span data-stu-id="0bcbe-125">You can also use DBCS characters for parameter names and parameter marker characters.</span></span> <span data-ttu-id="0bcbe-126">In SQL-Elementen, z. B. Funktionsnamen oder SQL-Schlüsselwörtern, dürfen DBCS-Zeichen jedoch nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0bcbe-126">However, you cannot use DBCS characters in SQL language elements such as function names or SQL keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bcbe-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0bcbe-127">See Also</span></span>  
 [<span data-ttu-id="0bcbe-128">Themen zur Vorgehensweise: Entwerfen von Abfragen und Sichten &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="0bcbe-128">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
