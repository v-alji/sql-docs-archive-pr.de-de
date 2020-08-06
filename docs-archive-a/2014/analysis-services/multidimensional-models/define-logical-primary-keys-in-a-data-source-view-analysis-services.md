---
title: Definieren logischer Primärschlüssel in einer Datenquellen Sicht (Analysis Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- removing logical primary keys
- logical primary keys [SQL Server]
- deleting logical primary keys
- data source views [Analysis Services], logical primary keys
ms.assetid: 172bc267-c637-4caa-bf55-0ba198d30b1e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25092e5d754381c572dcdbfc03e5ee0f29c1df24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618387"
---
# <a name="define-logical-primary-keys-in-a-data-source-view-analysis-services"></a><span data-ttu-id="b3717-102">Definieren logischer Primärschlüssel in einer Datenquellensicht (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="b3717-102">Define Logical Primary Keys in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="b3717-103">Der Datenquellensicht-Assistent und der Datenquellensicht-Designer definieren automatisch einen Primärschlüssel für eine Tabelle, die einer Datenquellensicht basierend auf der zugrunde liegenden Datenbanktabelle hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="b3717-103">The Data Source View Wizard and Data Source View Designer automatically define a primary key for a table that is added to a data source view based on underlying database table.</span></span>  
  
 <span data-ttu-id="b3717-104">Es kann jedoch zeitweise erforderlich sein, einen Primärschlüssel manuell in der Datenquellensicht zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b3717-104">Occasionally, you may need to manually define a primary key in the data source view.</span></span> <span data-ttu-id="b3717-105">Aus Leistungs- oder Entwurfsgründen haben Tabellen in einer Datenquelle z. B. möglicherweise keine explizit definierten Primärschlüsselspalten.</span><span class="sxs-lookup"><span data-stu-id="b3717-105">For example, for performance or design reasons, tables in a data source may not have explicitly defined primary key columns.</span></span> <span data-ttu-id="b3717-106">In benannten Abfragen und Sichten kann die Primärschlüsselspalte einer Tabelle ebenfalls fehlen.</span><span class="sxs-lookup"><span data-stu-id="b3717-106">Named queries and views may also omit the primary key column for a table.</span></span> <span data-ttu-id="b3717-107">Wenn für eine Tabelle, Sicht oder benannte Abfrage kein physischer Primärschlüssel definiert ist, können Sie im Datenquellensicht-Designer manuell einen logischen Primärschlüssel für die Tabelle, Sicht oder benannte Abfrage definieren.</span><span class="sxs-lookup"><span data-stu-id="b3717-107">If a table, view, or named query does not have a physical primary key defined, you can manually define a logical primary key on the table, view or named query in Data Source View Designer.</span></span>  
  
## <a name="set-a-logical-primary-key"></a><span data-ttu-id="b3717-108">Festlegen eines logischen Primärschlüssels</span><span class="sxs-lookup"><span data-stu-id="b3717-108">Set a Logical Primary Key</span></span>  
 <span data-ttu-id="b3717-109">Primärschlüssel werden in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] benötigt, um Datensätze in Tabellen eindeutig zu identifizieren, um Schlüsselspalten in Dimensionstabellen zu identifizieren und um Beziehungen zwischen Tabellen, Sichten und benannten Abfragen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b3717-109">Primary keys are required in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to uniquely identify records in a table, identify key columns in dimension tables and to support relationships between tables, views and named queries.</span></span> <span data-ttu-id="b3717-110">Diese Beziehungen werden verwendet, um Abfragen zum Abrufen von Daten und Metadaten aus zugrunde liegenden Datenquellen zu erstellen und um erweiterte Business Intelligence-Funktionen zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="b3717-110">These relationships are used to construct queries for retrieving data and metadata from underlying data sources, and to take advantage of advanced business intelligence features.</span></span>  
  
 <span data-ttu-id="b3717-111">Jede Spalte kann für den logischen Primärschlüssel verwendet werden, einschließlich einer benannten Berechnung.</span><span class="sxs-lookup"><span data-stu-id="b3717-111">Any column can be used for the logical primary key, including a named calculation.</span></span> <span data-ttu-id="b3717-112">Wenn Sie einen logischen Primärschlüssel erstellen, wird eine eindeutige Einschränkung in der Datenquellensicht erstellt und als Primärschlüsseleinschränkung markiert.</span><span class="sxs-lookup"><span data-stu-id="b3717-112">When you create a logical primary key, a unique constraint is created in the data source view and marked as a primary key constraint.</span></span> <span data-ttu-id="b3717-113">Jeder andere in der ausgewählten Tabelle festgelegte, vorhandene logische Primärschlüssel wird gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b3717-113">Any other existing logical primary key specified in the selected table is deleted.</span></span>  
  
1.  <span data-ttu-id="b3717-114">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das Projekt, oder stellen Sie eine Verbindung mit der Datenbank her, das bzw. die die Datenquellensicht enthält, in der Sie einen logischen Primärschlüssel festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="b3717-114">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you wish to set a logical primary key.</span></span>  
  
2.  <span data-ttu-id="b3717-115">Erweitern Sie im Projektmappen-Explorer den Ordner **Datenquellensichten** , und doppelklicken Sie anschließend auf die Datenquellensicht.</span><span class="sxs-lookup"><span data-stu-id="b3717-115">In Solution Explorer, expand the **Data Source Views** folder, then double-click the data source view.</span></span>  
  
     <span data-ttu-id="b3717-116">Wenn Sie eine Tabelle oder Sicht suchen möchten, können Sie die Option **Tabelle suchen** verwenden, indem Sie entweder auf das Menü **Datenquellen Sicht** klicken oder mit der rechten Maustaste auf einen geöffneten Bereich der **Tabellen** -oder **Diagramm** Bereiche klicken.</span><span class="sxs-lookup"><span data-stu-id="b3717-116">To locate a table or view, you can use the **Find Table** option by either clicking the **Data Source View**  menu or right-clicking in an open area of the **Tables** or **Diagram** panes.</span></span>  
  
3.  <span data-ttu-id="b3717-117">Klicken Sie im Bereich **Tabellen** oder **Diagramm** mit der rechten Maustaste auf die Spalte(n), mit denen Sie einen logischen Primärschlüssel definierten möchten, und klicken Sie anschließend auf **Logischen Primärschlüssel festlegen**.</span><span class="sxs-lookup"><span data-stu-id="b3717-117">In either the **Tables** or the **Diagram** pane, right-click the column or columns that you want to use to define a logical primary key, and then click **Set Logical Primary Key**.</span></span>  
  
     <span data-ttu-id="b3717-118">Die Option zum Festlegen eines logischen Primärschlüssels steht nur für Tabellen zur Verfügung, die keinen Primärschlüssel aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b3717-118">The option to set a logical primary key is available only for tables that do not have a primary key.</span></span>  
  
     <span data-ttu-id="b3717-119">Beachten Sie, dass die Primärschlüsselspalten nach dem Festlegen des Schlüssels mit einem Schlüsselsymbol gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="b3717-119">Notice that after you set the key, a key icon now identifies the primary key columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3717-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b3717-120">See Also</span></span>  
 <span data-ttu-id="b3717-121">[Datenquellen Sichten in mehrdimensionalen Modellen](data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="b3717-121">[Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="b3717-122">Definieren von benannten Berechnungen in einer Datenquellensicht &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b3717-122">Define Named Calculations in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-calculations-in-a-data-source-view-analysis-services.md)  
  
  
