---
title: Einfügen von Transact-SQL-Ausschnitten
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- IntelliSense [SQL Server], snippets
- Transact-SQL snippets, code
- snippets [Transact-SQL], how to insert
ms.assetid: d66c96f4-2e84-4d79-9bfd-3635fdd98425
author: rothja
ms.author: jroth
ms.openlocfilehash: 26a7a224e700c726ee3d4437321843d45ddb6e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622016"
---
# <a name="insert-transact-sql-snippets"></a><span data-ttu-id="b2911-102">Einfügen von Transact-SQL-Ausschnitten</span><span class="sxs-lookup"><span data-stu-id="b2911-102">Insert Transact-SQL Snippets</span></span>
  <span data-ttu-id="b2911-103">Ein [!INCLUDE[tsql](../../includes/tsql-md.md)] -Codeausschnitt ist eine Vorlage, die Sie als Ausgangspunkt beim Schreiben von neuen [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen im [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b2911-103">A [!INCLUDE[tsql](../../includes/tsql-md.md)] code snippet is a template you can use as a starting point when writing new [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span>  
  
## <a name="inserting-snippets"></a><span data-ttu-id="b2911-104">Einfügen von Ausschnitten</span><span class="sxs-lookup"><span data-stu-id="b2911-104">Inserting Snippets</span></span>  
 <span data-ttu-id="b2911-105">Sie können das Menü **Ausschnitt einfügen** verwenden, um eine kategorisierte Liste von Ausschnitten zu öffnen, die Sie auswählen können.</span><span class="sxs-lookup"><span data-stu-id="b2911-105">You can use the **Insert Snippet** menu to open a categorized list of snippets to choose from.</span></span>  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="b2911-106">-Ausschnitte enthalten Ersetzungspunkte. Dabei handelt es sich um Text, der die für diesen Punkt relevante Syntax vorschlägt.</span><span class="sxs-lookup"><span data-stu-id="b2911-106">snippets contain replacement points: text that suggests the syntax relevant to that point.</span></span> <span data-ttu-id="b2911-107">Beispielsweise enthält der CREATE TABLE-Ausschnitt Ersetzungspunkte für Elemente wie den Tabellennamen, die Spaltennamen und die Spaltendatentypen.</span><span class="sxs-lookup"><span data-stu-id="b2911-107">For example, the CREATE TABLE snippet has replacement points for elements such as the table name, column names, and column data types.</span></span> <span data-ttu-id="b2911-108">Wenn Sie den Ausschnitt eingefügt haben, müssen Sie den Ersetzungstext so ändern, dass eine gültige [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung entsteht.</span><span class="sxs-lookup"><span data-stu-id="b2911-108">After inserting the snippet, you must change the replacement text to form a valid [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="b2911-109">Weitere Informationen finden Sie unter [Abschließen von Transact-SQL-Ausschnitten](complete-transact-sql-snippets.md).</span><span class="sxs-lookup"><span data-stu-id="b2911-109">For more information, see [Complete Transact-SQL Snippets](complete-transact-sql-snippets.md).</span></span>  
  
#### <a name="inserting-a-snippet-by-using-the-insert-snippet-menu"></a><span data-ttu-id="b2911-110">Einfügen eines Ausschnitts mit dem Menü "Ausschnitt einfügen"</span><span class="sxs-lookup"><span data-stu-id="b2911-110">Inserting a Snippet by Using the Insert Snippet Menu</span></span>  
  
1.  <span data-ttu-id="b2911-111">Setzen Sie im [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor-Fenster den Cursor an die Position, an der Sie den [!INCLUDE[tsql](../../includes/tsql-md.md)] -Ausschnitt einfügen möchten.</span><span class="sxs-lookup"><span data-stu-id="b2911-111">In the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window, put the cursor where you want to insert the [!INCLUDE[tsql](../../includes/tsql-md.md)] snippet.</span></span>  
  
2.  <span data-ttu-id="b2911-112">Rufen Sie die QuickInfo für die Ausschnittauswahl mit einer von drei Methoden auf:</span><span class="sxs-lookup"><span data-stu-id="b2911-112">Launch the snippet picker tooltip in one of three ways:</span></span>  
  
    -   <span data-ttu-id="b2911-113">Drücken Sie STRG+K, STRG+X.</span><span class="sxs-lookup"><span data-stu-id="b2911-113">Press CTRL+K, CTRL+X.</span></span>  
  
    -   <span data-ttu-id="b2911-114">Zeigen Sie im Menü **Bearbeiten** auf **IntelliSense**, und klicken Sie dann auf **Ausschnitt einfügen**.</span><span class="sxs-lookup"><span data-stu-id="b2911-114">On the **Edit** menu, point to **IntelliSense**, then click **Insert Snippet**.</span></span>  
  
    -   <span data-ttu-id="b2911-115">Klicken Sie mit der rechten Maustaste, und wählen Sie dann im Kontextmenü den Befehl **Ausschnitt einfügen** aus.</span><span class="sxs-lookup"><span data-stu-id="b2911-115">Right-click the mouse and then select the **Insert Snippet** command from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="b2911-116">Doppelklicken Sie auf den Ausschnitt, oder wählen Sie in der Ausschnittauswahl den Ausschnitt aus, und drücken Sie dann TAB oder die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="b2911-116">Double-click the snippet, or select the snippet from the snippet picker and then press TAB or ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2911-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b2911-117">See Also</span></span>  
 [<span data-ttu-id="b2911-118">Einfügen von Transact-SQL-Umschließungsausschnitten</span><span class="sxs-lookup"><span data-stu-id="b2911-118">Insert Surround-with Transact-SQL snippets</span></span>](insert-surround-with-transact-sql-snippets.md)  
  
  
