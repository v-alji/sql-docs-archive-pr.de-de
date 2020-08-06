---
title: Angeben von Standardwerten für Spalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], defaults
- default values
ms.assetid: 64514aed-b846-407b-992e-cf813f9a1a91
author: stevestein
ms.author: sstein
ms.openlocfilehash: 650347c29e1175c5a1fe646fc079478520dc8c6d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620756"
---
# <a name="specify-default-values-for-columns"></a><span data-ttu-id="c05bc-102">Angeben von Standardwerten für Spalten</span><span class="sxs-lookup"><span data-stu-id="c05bc-102">Specify Default Values for Columns</span></span>
  <span data-ttu-id="c05bc-103">Sie können einen Standardwert angeben, der mit [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] in die Spalte in [!INCLUDE[tsql](../../includes/tsql-md.md)]eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c05bc-103">You can specify a default value that will be entered in the column in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c05bc-104">Wenn kein Standardwert zugewiesen ist und Benutzer die Spalte leer lassen, wird wie folgt verfahren:</span><span class="sxs-lookup"><span data-stu-id="c05bc-104">If you do not assign a default value and the user leaves the column blank, then:</span></span>  
  
-   <span data-ttu-id="c05bc-105">Wenn NULL-Werte zugelassen sind, wird NULL in die Spalte eingefügt.</span><span class="sxs-lookup"><span data-stu-id="c05bc-105">If you set the option to allow null values, NULL will be inserted into the column.</span></span>  
  
-   <span data-ttu-id="c05bc-106">Wenn NULL-Werte nicht zugelassen sind, bleibt die Spalte leer. Die Zeile kann jedoch erst dann gespeichert werden, wenn ein Wert in die Spalte eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c05bc-106">If you do not set the option to allow null values, the column will remain blank, but the user will not be able to save the row until they supply a value for the column.</span></span>  
  
 <span data-ttu-id="c05bc-107">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="c05bc-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c05bc-108">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="c05bc-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c05bc-109">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="c05bc-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c05bc-110">Security</span><span class="sxs-lookup"><span data-stu-id="c05bc-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c05bc-111">**So geben Sie einen benutzerdefinierten Standardwert an mit:**</span><span class="sxs-lookup"><span data-stu-id="c05bc-111">**To specify a default value, using:**</span></span>  
  
     [<span data-ttu-id="c05bc-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c05bc-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c05bc-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c05bc-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c05bc-114">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="c05bc-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c05bc-115">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="c05bc-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c05bc-116">Wenn die Eingabe im Feld **Standardwert** einen gebundenen Standardwert ersetzt (der ohne Klammern angezeigt wird), werden Sie aufgefordert, die Bindung des Standardwerts aufzuheben und ihn durch den neuen Standardwert zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="c05bc-116">If your entry in the **Default Value** field replaces a bound default (which is shown without parentheses), you will be prompted to unbind the default and replace it with your new default.</span></span>  
  
-   <span data-ttu-id="c05bc-117">Werte für Zeichenfolgen müssen in einfache Anführungszeichen (') gesetzt werden. Verwenden Sie keine doppelten Anführungszeichen ("), da diese für in Anführungszeichen gesetzte Bezeichner reserviert sind.</span><span class="sxs-lookup"><span data-stu-id="c05bc-117">To enter a text string, enclose the value in single quotation marks ('); do not use double quotation marks (") because they are reserved for quoted identifiers.</span></span>  
  
-   <span data-ttu-id="c05bc-118">Um einen numerischen Standardwert einzugeben, geben Sie die Zahl ohne Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="c05bc-118">To enter a numeric default, enter the number without quotation marks around it.</span></span>  
  
-   <span data-ttu-id="c05bc-119">Wenn Sie ein Objekt bzw. eine Funktion eingeben, geben Sie den Namen des Objekts bzw. der Funktion ein, ohne ihn in Anführungszeichen einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="c05bc-119">To enter an object/function, enter the name of the object/function without quotation marks around it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c05bc-120">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c05bc-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c05bc-121">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="c05bc-121">Permissions</span></span>  
 <span data-ttu-id="c05bc-122">Erfordert die ALTER-Berechtigung für die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c05bc-122">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c05bc-123">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c05bc-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-a-default-value-for-a-column"></a><span data-ttu-id="c05bc-124">So geben Sie einen Standardwert für eine Spalte an</span><span class="sxs-lookup"><span data-stu-id="c05bc-124">To specify a default value for a column</span></span>  
  
1.  <span data-ttu-id="c05bc-125">Klicken Sie im **Objekt-Explorer**mit der rechten Maustaste auf die Tabelle mit den Spalten, für die Sie Dezimalstellen ändern möchten, und klicken Sie auf **Entwerfen**.</span><span class="sxs-lookup"><span data-stu-id="c05bc-125">In **Object Explorer**, right-click the table with columns for which you want to change the scale and click **Design**.</span></span>  
  
2.  <span data-ttu-id="c05bc-126">Wählen Sie die Spalte aus, für die Sie einen Standardwert angeben möchten.</span><span class="sxs-lookup"><span data-stu-id="c05bc-126">Select the column for which you want to specify a default value.</span></span>  
  
3.  <span data-ttu-id="c05bc-127">Geben Sie den neuen Standardwert auf der Registerkarte **Spalteneigenschaften** in der Eigenschaft **Standardwert oder -bindung** ein.</span><span class="sxs-lookup"><span data-stu-id="c05bc-127">In the **Column Properties** tab, enter the new default value in the **Default Value or Binding** property.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c05bc-128">Um einen numerischen Standardwert einzugeben, geben Sie die Zahl ein.</span><span class="sxs-lookup"><span data-stu-id="c05bc-128">To enter a numeric default value, enter the number.</span></span> <span data-ttu-id="c05bc-129">Geben Sie bei einem Objekt oder einer Funktion den entsprechenden Namen ein.</span><span class="sxs-lookup"><span data-stu-id="c05bc-129">For an object or function enter its name.</span></span> <span data-ttu-id="c05bc-130">Geben Sie für einen alphanumerischen Standardwert den Wert in einfachen Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="c05bc-130">For an alphanumeric default enter the value inside single quotes.</span></span>  
  
4.  <span data-ttu-id="c05bc-131">Klicken Sie im Menü **Datei** auf _Tabellenname_**speichern**.</span><span class="sxs-lookup"><span data-stu-id="c05bc-131">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c05bc-132">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c05bc-132">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-a-default-value-for-a-column"></a><span data-ttu-id="c05bc-133">So geben Sie einen Standardwert für eine Spalte an</span><span class="sxs-lookup"><span data-stu-id="c05bc-133">To specify a default value for a column</span></span>  
  
1.  <span data-ttu-id="c05bc-134">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="c05bc-134">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c05bc-135">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="c05bc-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c05bc-136">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c05bc-136">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    CREATE TABLE dbo.doc_exz ( column_a INT, column_b INT) ;  
    GO  
    INSERT INTO dbo.doc_exz (column_a)VALUES ( 7 ) ;  
    GO  
    ALTER TABLE dbo.doc_exz  
    ADD CONSTRAINT col_b_def  
    DEFAULT 50 FOR column_b ;  
    GO  
  
    ```  
  
 <span data-ttu-id="c05bc-137">Weitere Informationen finden Sie unter [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c05bc-137">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
