---
title: Ändern von Tabellen-, Spalten-oder Zeilen Filter Zuordnungen (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2124c526-5772-4f84-a019-9dd3e906e8dd
author: minewiskan
ms.author: owend
ms.openlocfilehash: d8a597fb51804ea12caace63f3308b07bffc5899
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616705"
---
# <a name="change-table-column-or-row-filter-mappings-ssas-tabular"></a><span data-ttu-id="bf399-102">Ändern von Tabellen-, Spalten- oder Zeilenfilterzuordnungen (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="bf399-102">Change table, column, or row filter mappings (SSAS Tabular)</span></span>
  <span data-ttu-id="bf399-103">In diesem Thema wird beschrieben, wie Tabellen-, Spalten- oder Zeilenfilterzuordnungen im Dialogfeld **Tabelleneigenschaften bearbeiten** in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]geändert werden.</span><span class="sxs-lookup"><span data-stu-id="bf399-103">This topic describes how to change table, column, or row filter mappings by using the **Edit Table Properties** dialog box in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
 <span data-ttu-id="bf399-104">Die Optionen im Dialogfeld **Tabelleneigenschaften bearbeiten** variieren, je nachdem, ob Daten ursprünglich durch Auswahl von Tabellen aus einer Liste oder mithilfe einer SQL-Abfrage importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="bf399-104">Options in the **Edit Table Properties** dialog box are different depending on whether you originally imported data by selecting tables from a list or by using a SQL query.</span></span> <span data-ttu-id="bf399-105">Wenn die Daten ursprünglich durch Auswahl aus einer Liste importiert wurden, wird das Dialogfeld **Tabelleneigenschaften bearbeiten** im Tabellenvorschaumodus angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bf399-105">If you originally imported the data by selecting from a list, the **Edit Table Properties** dialog box displays the Table Preview mode.</span></span> <span data-ttu-id="bf399-106">In diesem Modus wird nur eine Teilmenge angezeigt, die auf die ersten 50 Zeilen der Quelltabelle beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="bf399-106">This mode displays only a subset limited to the first fifty rows of the source table.</span></span> <span data-ttu-id="bf399-107">Wenn die Daten ursprünglich durch Verwendung einer SQL-Anweisung importiert wurden, wird im Dialogfeld **Tabelleneigenschaften bearbeiten** nur eine SQL-Anweisung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bf399-107">If you originally imported the data by using a SQL statement, the **Edit Table Properties** dialog box only displays a SQL statement.</span></span> <span data-ttu-id="bf399-108">Mithilfe einer SQL-Abfrageanweisung können Sie eine Teilmenge der Zeilen abrufen, indem Sie entweder einen Filter entwerfen oder die SQL-Anweisung manuell bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="bf399-108">Using a SQL query statement, you can retrieve a subset of rows, either by designing a filter, or by manually editing the SQL statement.</span></span>  
  
 <span data-ttu-id="bf399-109">Wenn Sie die Quelle in eine Tabelle ändern, die andere Spalten als die aktuelle Tabelle enthält, wird eine entsprechende Warnmeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bf399-109">If you change the source to a table that has different columns than the current table, a message is displayed warning that the columns are different.</span></span> <span data-ttu-id="bf399-110">Sie müssen dann die Spalten auswählen, die Sie in die aktuelle Tabelle einfügen möchten, und auf **Speichern**klicken.</span><span class="sxs-lookup"><span data-stu-id="bf399-110">You must then select the columns that you want to put in the current table and click **Save**.</span></span> <span data-ttu-id="bf399-111">Sie können die gesamte Tabelle ersetzen, indem Sie das Kontrollkästchen links von der Tabelle aktivieren.</span><span class="sxs-lookup"><span data-stu-id="bf399-111">You can replace the entire table by selecting the check box at the left of the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bf399-112">Wenn die Tabelle über mehrere Partitionen verfügt, können Sie die Zeilenfilterzuordnungen nicht im Dialogfeld Tabelleneigenschaften bearbeiten ändern.</span><span class="sxs-lookup"><span data-stu-id="bf399-112">If your table has more than one partition, you cannot use the Edit Table Properties dialog box to change row filter mappings.</span></span> <span data-ttu-id="bf399-113">Verwenden Sie zum Ändern der Zeilenfilterzuordnungen für Tabellen mit mehreren Partitionen den Partitions-Manager.</span><span class="sxs-lookup"><span data-stu-id="bf399-113">To change row filter mappings for tables with multiple partitions, use Partition Manager.</span></span> <span data-ttu-id="bf399-114">Weitere Informationen finden Sie unter [Partitionen &#40;SSAS – tabellarisch&#41;](partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="bf399-114">For more information, see [Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md).</span></span>  
  
#### <a name="to-change-table-column-or-row-filter-mappings"></a><span data-ttu-id="bf399-115">So ändern Sie Tabellen-, Spalten- oder Zeilenfilterzuordnungen</span><span class="sxs-lookup"><span data-stu-id="bf399-115">To change table, column, or row filter mappings</span></span>  
  
1.  <span data-ttu-id="bf399-116">Klicken Sie im Modell-Designer auf die Tabelle und dann auf das Menü **Tabelle** und auf **Tabelleneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="bf399-116">In the model designer, click the table, then click on the **Table** menu, and then click **Table Properties**.</span></span>  
  
2.  <span data-ttu-id="bf399-117">Suchen Sie im Dialogfeld **Tabelleneigenschaften bearbeiten** nach der Spalte, die die Filterkriterien enthält, und klicken Sie dann rechts von der Spaltenüberschrift auf den Pfeil nach unten.</span><span class="sxs-lookup"><span data-stu-id="bf399-117">In the **Edit Table Properties** dialog box, locate the column that contains the criteria you want to filter on, and then click the down arrow at the right of the column heading.</span></span>  
  
3.  <span data-ttu-id="bf399-118">Führen Sie im Menü **AutoFilter** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="bf399-118">In the **AutoFilter** menu, do one of the following:</span></span>  
  
    -   <span data-ttu-id="bf399-119">Wählen Sie in der Liste der Spaltenwerte mindestens einen Wert aus, nach dem gefiltert werden soll, bzw. heben Sie die Auswahl auf, und klicken Sie auf OK.</span><span class="sxs-lookup"><span data-stu-id="bf399-119">In the list of column values, select or clear one or more values to filter by, and then click OK.</span></span>  
  
         <span data-ttu-id="bf399-120">Wenn die Anzahl der Werte sehr groß ist, kann es sein, dass einzelne Elemente nicht in der Liste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bf399-120">If the number of values is extremely large, individual items might not be shown in the list.</span></span> <span data-ttu-id="bf399-121">Stattdessen wird eine Meldung angezeigt, dass zu viele Elemente zum Anzeigen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="bf399-121">Instead, you will see the message, "Too many items to show."</span></span>  
  
    -   <span data-ttu-id="bf399-122">Klicken Sie je nach Typ der Spalte auf **Zahlenfilter** oder **Textfilter** , und klicken Sie anschließend auf einen der Vergleichsoperatorbefehle (wie „Ist gleich“), oder klicken Sie auf „Benutzerdefinierter Filter“.</span><span class="sxs-lookup"><span data-stu-id="bf399-122">Click **Number Filters** or **Text Filters** (depending on the type of column), and then clicke of the comparison operator commands (such as Equals), or click Custom Filter.</span></span> <span data-ttu-id="bf399-123">Erstellen Sie im Dialogfeld **Benutzerdefinierter Filter** den Filter, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bf399-123">In the **Custom Filter** dialog box, create the filter, and then click **OK**.</span></span>  
  
         <span data-ttu-id="bf399-124">Falls Sie erneut beginnen möchten, klicken Sie auf **Zeilenfilter löschen**.</span><span class="sxs-lookup"><span data-stu-id="bf399-124">If you make a mistake and need to start over, click **Clear Row Filters**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf399-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bf399-125">See Also</span></span>  
 [<span data-ttu-id="bf399-126">Tabelleneigenschaften bearbeiten &#40; Dialogfeld, SSAS&#41;</span><span class="sxs-lookup"><span data-stu-id="bf399-126">Edit Table Properties Dialog Box &#40;SSAS&#41;</span></span>](../edit-table-properties-dialog-box-ssas.md)  
  
  
