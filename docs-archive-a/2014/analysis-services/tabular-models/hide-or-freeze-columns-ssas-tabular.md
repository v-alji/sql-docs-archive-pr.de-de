---
title: Ausblenden oder Fixieren von Spalten (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.hideunhidecolumnsdb.f1
ms.assetid: 5407aee5-6a07-4559-a2ba-2ca00a242f02
author: minewiskan
ms.author: owend
ms.openlocfilehash: 71398eecbc342b4e3f9c2445fef3023132266dac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696194"
---
# <a name="hide-or-freeze-columns-ssas-tabular"></a><span data-ttu-id="a87bc-102">Ausblenden oder Einfrieren von Spalten (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="a87bc-102">Hide or Freeze Columns (SSAS Tabular)</span></span>
  <span data-ttu-id="a87bc-103">Wenn es im Modell-Designer Spalten gibt, die Sie nicht in einer Tabelle anzeigen möchten, können Sie diese zeitweise ausblenden.</span><span class="sxs-lookup"><span data-stu-id="a87bc-103">In the model designer, if there are columns that you don't want to display in a table, you can temporarily hide them.</span></span> <span data-ttu-id="a87bc-104">Durch das Ausblenden einer Spalte erhalten Sie mehr Platz auf dem Bildschirm, um neue Spalten hinzuzufügen oder nur mit relevanten Datenspalten zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="a87bc-104">Hiding a column gives you more room on the screen to add new columns or to work with only relevant columns of data.</span></span> <span data-ttu-id="a87bc-105">Sie können Spalten über das Menüband **Spalte** im Modell-Designer und über das Kontextmenü der einzelnen Spaltenüberschriften aus- und einblenden.</span><span class="sxs-lookup"><span data-stu-id="a87bc-105">You can hide and unhide columns from the **Column** menu in the model designer, and from the right-click menu available from each column header.</span></span> <span data-ttu-id="a87bc-106">Um einen Bereich eines Modells sichtbar zu halten, während Sie einen Bildlauf zu einem anderen Bereich des Modells ausführen, können Sie bestimmte Spalten in einem Bereich sperren, indem Sie sie fixieren.</span><span class="sxs-lookup"><span data-stu-id="a87bc-106">To keep an area of a model visible while you scroll to another area of the model, you can lock specific columns in one area by freezing them.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a87bc-107">Die Möglichkeit, Spalten auszublenden, dient nicht der Datensicherheit, sondern nur zur Vereinfachung und Kürzung der Spaltenliste im Modell-Designer oder in Berichten.</span><span class="sxs-lookup"><span data-stu-id="a87bc-107">The ability to hide columns is not intended to be used for data security, only to simplify and shorten the list of columns visible in the model designer or reports.</span></span> <span data-ttu-id="a87bc-108">Um Daten zu sichern, können Sie Sicherheitsrollen definieren.</span><span class="sxs-lookup"><span data-stu-id="a87bc-108">To secure data, you can define security roles.</span></span> <span data-ttu-id="a87bc-109">Durch Rollen können die anzeigbaren Metadaten und Daten auf die in der Rolle definierten Objekte eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="a87bc-109">Roles can limit viewable metadata and data to only those objects defined in the role.</span></span> <span data-ttu-id="a87bc-110">Weitere Informationen finden Sie unter [Rollen &#40;SSAS – tabellarisch&#41;](roles-ssas-tabular.md)erstellte tabellarische Modellprojekte.</span><span class="sxs-lookup"><span data-stu-id="a87bc-110">For more information, see [Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="a87bc-111">Wenn Sie mit ausgeblendeten Spalten arbeiten, haben Sie die Möglichkeit, eine Spalte auszublenden, während Sie im Modell-Designer oder in Berichten arbeiten.</span><span class="sxs-lookup"><span data-stu-id="a87bc-111">When you hide a column, you have the option to hide the column while you are working in the model designer or in reports.</span></span> <span data-ttu-id="a87bc-112">Wenn Sie alle Spalten ausblenden, wird die gesamte Tabelle im Modell-Designer leer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a87bc-112">If you hide all columns, the entire table appears blank in the model designer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a87bc-113">Wenn Sie viele Spalten ausblenden müssen, können Sie eine Perspektive erstellen, statt Spalten aus- und einzublenden.</span><span class="sxs-lookup"><span data-stu-id="a87bc-113">If you have many columns to hide, you can create a perspective instead of hiding and unhiding columns.</span></span> <span data-ttu-id="a87bc-114">Eine Perspektive ist eine benutzerdefinierte Sicht der Daten, die das Arbeiten mit Teilmengen verknüpfter Daten erleichtert.</span><span class="sxs-lookup"><span data-stu-id="a87bc-114">A perspective is a custom view of the data that makes it easier to work with subset of related data.</span></span> <span data-ttu-id="a87bc-115">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Perspektiven &#40;SSAS – tabellarisch&#41;](perspectives-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="a87bc-115">For more information, see [Create and Manage Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md)</span></span>  
  
### <a name="to-hide-an-individual-column"></a><span data-ttu-id="a87bc-116">So blenden Sie eine einzelne Spalte aus</span><span class="sxs-lookup"><span data-stu-id="a87bc-116">To hide an individual column</span></span>  
  
1.  <span data-ttu-id="a87bc-117">Wählen Sie im Modell-Designer die Tabelle aus, die die auszublendende Spalte enthält.</span><span class="sxs-lookup"><span data-stu-id="a87bc-117">In the model designer, select the table that contains the column that you want to hide.</span></span>  
  
2.  <span data-ttu-id="a87bc-118">Klicken Sie mit der rechten Maustaste auf die Spalte, und klicken Sie dann auf **Spalten ausblenden**und auf **Aus Designer und aus Berichten**, **Aus Berichten**oder **Aus Designer**.</span><span class="sxs-lookup"><span data-stu-id="a87bc-118">Right-click the column, then click **Hide Columns**, and then click **From Designer and Reports**, **From Reports**, or **From Designer**.</span></span>  
  
### <a name="to-hide-multiple-columns"></a><span data-ttu-id="a87bc-119">So blenden Sie mehrere Spalten aus</span><span class="sxs-lookup"><span data-stu-id="a87bc-119">To hide multiple columns</span></span>  
  
1.  <span data-ttu-id="a87bc-120">Wählen Sie im Modell-Designer die Tabelle aus, die die auszublendenden Spalten enthält.</span><span class="sxs-lookup"><span data-stu-id="a87bc-120">In the model designer, select the table that contains the columns that you want to hide.</span></span>  
  
2.  <span data-ttu-id="a87bc-121">Klicken Sie auf das Menü **Spalten** , und klicken Sie dann auf **Aus- und einblenden**.</span><span class="sxs-lookup"><span data-stu-id="a87bc-121">Click on the **Columns** menu, and then click **Hide and Unhide**.</span></span>  
  
3.  <span data-ttu-id="a87bc-122">Suchen Sie im Dialogfeld **Spalten aus- und einblenden** diejenigen Spalten, die Sie ausblenden möchten, und deaktivieren Sie dann **In Designer** bzw. **In Berichten**.</span><span class="sxs-lookup"><span data-stu-id="a87bc-122">In the **Hide and Unhide Columns** dialog box, locate each column that you want to hide, and then deselect one or both of **In Designer** and **In Reports**.</span></span>  
  
4.  <span data-ttu-id="a87bc-123">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a87bc-123">Click **OK**.</span></span>  
  
### <a name="to-freeze-columns"></a><span data-ttu-id="a87bc-124">So fixieren Sie Spalten</span><span class="sxs-lookup"><span data-stu-id="a87bc-124">To freeze columns</span></span>  
  
1.  <span data-ttu-id="a87bc-125">Wählen Sie im Modell-Designer die Tabelle aus, die die zu fixierenden Spalten enthält.</span><span class="sxs-lookup"><span data-stu-id="a87bc-125">In the model designer, select the table that contains the columns that you want to freeze.</span></span>  
  
2.  <span data-ttu-id="a87bc-126">Wählen Sie eine oder mehrere Spalten zum Fixieren aus.</span><span class="sxs-lookup"><span data-stu-id="a87bc-126">Select one or more columns to freeze.</span></span>  
  
3.  <span data-ttu-id="a87bc-127">Klicken Sie auf das Menü **Spalten** , und klicken Sie dann auf **Fixieren**.</span><span class="sxs-lookup"><span data-stu-id="a87bc-127">Click on the **Columns** menu, and then click **Freeze**..</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a87bc-128">Wenn Spalten fixiert sind, werden Sie im Designer in der Tabelle nach links (bzw. nach vorne) verschoben.</span><span class="sxs-lookup"><span data-stu-id="a87bc-128">When a column(s) is frozen, it is moved to left (or front) of the table in the designer.</span></span> <span data-ttu-id="a87bc-129">Wenn Sie die Fixierung der Spalte aufheben, wird diese nicht an ihre ursprüngliche Position zurückverschoben.</span><span class="sxs-lookup"><span data-stu-id="a87bc-129">Unfreezing the column does not move it back to its original location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a87bc-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a87bc-130">See Also</span></span>  
 <span data-ttu-id="a87bc-131">[Tabellen und Spalten &#40;tabellarischen SSAS-&#41;](tables-and-columns-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="a87bc-131">[Tables and Columns &#40;SSAS Tabular&#41;](tables-and-columns-ssas-tabular.md) </span></span>  
 <span data-ttu-id="a87bc-132">[Perspektiven &#40;tabellarischen SSAS-&#41;](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="a87bc-132">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="a87bc-133">Rollen &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="a87bc-133">Roles &#40;SSAS Tabular&#41;</span></span>](roles-ssas-tabular.md)  
  
  
