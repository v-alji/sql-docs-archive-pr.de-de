---
title: 'Aufgabe 1: Erstellen einer Wissensdatenbank und von Domänen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 7d74a60b-8933-4038-bcbb-4e9dcc4f70e9
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ce1b22e3d677e831a1d518dacc1267ad0e6be236
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699057"
---
# <a name="task-1-creating-a-knowledge-base-and-domains"></a><span data-ttu-id="e47ad-102">Aufgabe 1: Erstellen von Wissensdatenbanken und Domänen</span><span class="sxs-lookup"><span data-stu-id="e47ad-102">Task 1: Creating a Knowledge Base and Domains</span></span>
  <span data-ttu-id="e47ad-103">In dieser Aufgabe erstellen Sie die Wissensdatenbank **Suppliers** und erstellen Domänen, die zum Bereinigen von Daten und zum Abgleichen von Daten verwendet werden, um Duplikate zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="e47ad-103">In this task, you create the **Suppliers** knowledge base and create domains that is used for cleansing data and matching data to remove duplicates.</span></span>  
  
1.  <span data-ttu-id="e47ad-104">Starten Sie **Data Quality-Client**.</span><span class="sxs-lookup"><span data-stu-id="e47ad-104">Launch **Data Quality Client**.</span></span> <span data-ttu-id="e47ad-105">Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, klicken Sie auf **Microsoft SQL Server 2012**und dann auf **Data Quality Services**, und klicken Sie dann auf **Data Quality-Client**.</span><span class="sxs-lookup"><span data-stu-id="e47ad-105">Click **Start**, point to **All Programs**, click **Microsoft SQL Server 2012**, click **Data Quality Services**, and then click **Data Quality Client**.</span></span>  
  
2.  <span data-ttu-id="e47ad-106">Wählen Sie im Dialogfeld **Verbindung mit Server herstellen** die Daten Bank Server Instanz aus, auf der DQS installiert ist, und klicken Sie auf **verbinden**.</span><span class="sxs-lookup"><span data-stu-id="e47ad-106">In the **Connect to Server** dialog box, select the database server instance on which the DQS is installed, and click **Connect**.</span></span>  
  
     <span data-ttu-id="e47ad-107">![Dialog Feld "Verbindung mit Server herstellen"](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-01.jpg "Dialogfeld „Verbindung mit dem Server herstellen“")</span><span class="sxs-lookup"><span data-stu-id="e47ad-107">![Connect to Server Dialog Box](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-01.jpg "Connect to Server Dialog Box")</span></span>  
  
3.  <span data-ttu-id="e47ad-108">Klicken Sie auf der Startseite Data Quality-Client im Bereich **Wissensdatenbank-Verwaltung** auf **neue Wissensdatenbank**.</span><span class="sxs-lookup"><span data-stu-id="e47ad-108">In the Data Quality Client home page, in the **Knowledge Base Management** pane, click **New Knowledge Base**.</span></span>  
  
     <span data-ttu-id="e47ad-109">![Wissensdatenbank-Verwaltung – Neu (KB)](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-02.jpg "Wissensdatenbank-Verwaltung – Neu (KB)")</span><span class="sxs-lookup"><span data-stu-id="e47ad-109">![Knowledge Base Management - New KB](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-02.jpg "Knowledge Base Management - New KB")</span></span>  
  
4.  <span data-ttu-id="e47ad-110">Geben Sie **Suppliers** als **Name** der Wissensdatenbank ein.</span><span class="sxs-lookup"><span data-stu-id="e47ad-110">Enter **Suppliers** for **Name** of the knowledge base.</span></span>  
  
     <span data-ttu-id="e47ad-111">![Neue Wissensdatenbank – Domänenverwaltung](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-03.jpg "Neue Wissensdatenbank – Domänenverwaltung")</span><span class="sxs-lookup"><span data-stu-id="e47ad-111">![New Knowledge Base - Domain Management](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-03.jpg "New Knowledge Base - Domain Management")</span></span>  
  
5.  <span data-ttu-id="e47ad-112">Vergewissern Sie sich, dass das Feld **Wissensdatenbank aus Feld erstellen** auf **keine** festgelegt ist, da Sie die Wissensdatenbank **Suppliers** von Grund auf neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e47ad-112">Confirm that **Create Knowledge Base from** field is set to **None** since you are creating the **Suppliers** knowledge base from scratch.</span></span>  
  
6.  <span data-ttu-id="e47ad-113">Vergewissern Sie sich, dass für die **Aktivität** **Domänen Verwaltung** ausgewählt ist, und klicken Sie auf **weiter**</span><span class="sxs-lookup"><span data-stu-id="e47ad-113">Confirm that **Domain Management** is selected for the **Activity** and click **Next**.</span></span> <span data-ttu-id="e47ad-114">Mit der Domänenverwaltungsaktivität können Sie Domänen in der Wissensdatenbank erstellen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="e47ad-114">The Domain Management activity lets you create and manage domains in the knowledge base.</span></span>  
  
7.  <span data-ttu-id="e47ad-115">Klicken Sie im Fenster **Domänen Verwaltung** auf **Domänen** Symbolleisten-Schaltfläche erstellen, um eine Domäne zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e47ad-115">In the **Domain Management** window, click **Create a domain** toolbar button to create a domain.</span></span>  
  
     <span data-ttu-id="e47ad-116">![Domäne erstellen (Symbolleistenschaltfläche)](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-04.jpg "Domäne erstellen (Symbolleistenschaltfläche)")</span><span class="sxs-lookup"><span data-stu-id="e47ad-116">![Create Domain Toolbar Button](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-04.jpg "Create Domain Toolbar Button")</span></span>  
  
8.  <span data-ttu-id="e47ad-117">Geben Sie im Dialogfeld **Domäne erstellen** den Namen **Lieferanten-ID** für den **Domänen Namen**ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e47ad-117">In the **Create Domain** dialog box, type **Supplier ID** for the **Domain Name**, and click **OK**.</span></span>  
  
     <span data-ttu-id="e47ad-118">![Domäne erstellen (Dialogfeld)](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-05.jpg "Domäne erstellen (Dialogfeld)")</span><span class="sxs-lookup"><span data-stu-id="e47ad-118">![Create Domain Dialog Box](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-05.jpg "Create Domain Dialog Box")</span></span>  
  
9. <span data-ttu-id="e47ad-119">Wiederholen Sie den vorherigen Schritt, um folgenden Domänen mit allen Standardeinstellungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e47ad-119">Repeat previous step to create the following domains with all the default settings.</span></span> <span data-ttu-id="e47ad-120">Um das Tutorial einfach zu halten, legen Sie den **Datentyp** aller Domänen als **Zeichenfolge**fest.</span><span class="sxs-lookup"><span data-stu-id="e47ad-120">To keep the tutorial simple, you set the **Data Type** of all the domains as **String**.</span></span> <span data-ttu-id="e47ad-121">Die anderen zulässigen Datentypen sind: Ganze Zahl, Dezimalzahl und Datum.</span><span class="sxs-lookup"><span data-stu-id="e47ad-121">The other allowed data types are: Integer, Decimal, and Date.</span></span> <span data-ttu-id="e47ad-122">Wenn die Option **führende Werte verwenden** ausgewählt ist (Standard), werden alle Synonyme durch den führenden Wert der Synonym Gruppe in der Ausgabe ersetzt.</span><span class="sxs-lookup"><span data-stu-id="e47ad-122">When the **Use Leading Values** option is selected (default), all synonyms are replaced with the leading value of the synonym group in the output.</span></span> <span data-ttu-id="e47ad-123">Durch Festlegen der Option " **normalize String** " (Standard) werden alle Sonderzeichen in den Domänen Werten entfernt.</span><span class="sxs-lookup"><span data-stu-id="e47ad-123">Setting **Normalize String** option (default) removes any special characters in the domain values.</span></span> <span data-ttu-id="e47ad-124">Mit der Option **Format Output to** können Sie die Formatierung auswählen, die angewendet wird, wenn die Datenwerte in der Domäne ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e47ad-124">The **Format Output to** option lets you select the formatting that is applied when the data values in the domain are output.</span></span> <span data-ttu-id="e47ad-125">Wählen Sie Rechtschreibprüfung **aktivieren** (Standard) aus, um die Rechtschreibprüfung beim Auffüllen der Domäne für alle Zeichen folgen Werte auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e47ad-125">Select **Enable Speller** (default) to run Speller on all string values when populating the domain.</span></span> <span data-ttu-id="e47ad-126">Die **sprach** Einstellung gibt die Sprachversion der Rechtschreibprüfung an, **die Sie anwenden** möchten.</span><span class="sxs-lookup"><span data-stu-id="e47ad-126">The **Language** setting specifies which language version of the **Speller** you want to apply.</span></span> <span data-ttu-id="e47ad-127">Aktivieren Sie **Syntax Fehler Algorithmen deaktivieren** , um die Domäne aufzufüllen, ohne die Zeichen folgen Werte auf Syntax Fehler zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e47ad-127">Select **Disable Syntax Error Algorithms** to populate the domain without checking string values for syntax errors.</span></span> <span data-ttu-id="e47ad-128">Weitere Informationen finden Sie unter [Erstellen eines Domänen](https://msdn.microsoft.com/library/hh510401.aspx) Themas in der MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="e47ad-128">See [Create a Domain](https://msdn.microsoft.com/library/hh510401.aspx) topic in the MSDN library for more details.</span></span>  
  
    -   <span data-ttu-id="e47ad-129">Supplier Name</span><span class="sxs-lookup"><span data-stu-id="e47ad-129">Supplier Name</span></span>  
  
    -   <span data-ttu-id="e47ad-130">Kontakt-E-Mail</span><span class="sxs-lookup"><span data-stu-id="e47ad-130">Contact Email</span></span>  
  
    -   <span data-ttu-id="e47ad-131">Adresszeile</span><span class="sxs-lookup"><span data-stu-id="e47ad-131">Address Line</span></span>  
  
    -   <span data-ttu-id="e47ad-132">City</span><span class="sxs-lookup"><span data-stu-id="e47ad-132">City</span></span>  
  
    -   <span data-ttu-id="e47ad-133">State</span><span class="sxs-lookup"><span data-stu-id="e47ad-133">State</span></span>  
  
    -   <span data-ttu-id="e47ad-134">Land</span><span class="sxs-lookup"><span data-stu-id="e47ad-134">Country</span></span>  
  
    -   <span data-ttu-id="e47ad-135">Zip</span><span class="sxs-lookup"><span data-stu-id="e47ad-135">Zip</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="e47ad-136">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="e47ad-136">Next Step</span></span>  
 [<span data-ttu-id="e47ad-137">Aufgabe 2: Manuelles Hinzufügen von Domänenwerten</span><span class="sxs-lookup"><span data-stu-id="e47ad-137">Task 2: Adding Domain Values Manually</span></span>](../../2014/tutorials/task-2-adding-domain-values-manually.md)  
  
  
