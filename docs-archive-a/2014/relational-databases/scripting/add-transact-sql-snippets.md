---
title: Hinzufügen von Transact-SQL-Ausschnitten
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 901c7995-8eb5-4d12-8bb0-de0a922b48f8
author: rothja
ms.author: jroth
ms.openlocfilehash: 5b5886f8f36ae3753fcb7c89dd3aeff9c69eeba5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616467"
---
# <a name="add-transact-sql-snippets"></a><span data-ttu-id="21c8e-102">Hinzufügen von Transact-SQL-Ausschnitten</span><span class="sxs-lookup"><span data-stu-id="21c8e-102">Add Transact-SQL Snippets</span></span>
  <span data-ttu-id="21c8e-103">Sie können dem Satz von vordefinierten Ausschnitten, die in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]enthalten sind, eigene Transact-SQL-Codeausschnitte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="21c8e-103">You can add your own Transact-SQL code snippets to the set of pre-defined snippets included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="creating-a-transact-sql-snippet-file"></a><span data-ttu-id="21c8e-104">Erstellen einer Transact-SQL-Ausschnittdatei</span><span class="sxs-lookup"><span data-stu-id="21c8e-104">Creating a Transact-SQL Snippet File</span></span>  
 <span data-ttu-id="21c8e-105">Der erste Teil des Erstellens eines [!INCLUDE[tsql](../../includes/tsql-md.md)] -Codeausschnitts besteht darin, eine XML-Datei mit dem Text des Codeausschnitts zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="21c8e-105">The first part of creating a [!INCLUDE[tsql](../../includes/tsql-md.md)] code snippet is to create an XML file with the text of your code snippet.</span></span> <span data-ttu-id="21c8e-106">Die Datei muss die Dateierweiterung SNIPPET aufweisen und die Anforderungen des [Codeausschnittschemas](https://go.microsoft.com/fwlink/?LinkId=207504)erfüllen.</span><span class="sxs-lookup"><span data-stu-id="21c8e-106">The file must have a .snippet file extension, and meet the requirements of the [Code Snippets Schema](https://go.microsoft.com/fwlink/?LinkId=207504).</span></span> <span data-ttu-id="21c8e-107">Legen Sie die Ausschnittsprache auf SQL fest.</span><span class="sxs-lookup"><span data-stu-id="21c8e-107">Set the snippet language to SQL.</span></span>  
  
 <span data-ttu-id="21c8e-108">Sie können die vordefinierten Ausschnitte, die im Lieferumfang von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] enthalten sind, als Beispiele verwenden.</span><span class="sxs-lookup"><span data-stu-id="21c8e-108">You can use the pre-defined snippets that ship with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as examples.</span></span> <span data-ttu-id="21c8e-109">Um die vordefinierten Ausschnitte zu suchen, öffnen Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], wählen Sie das Menü **Extras** aus, und klicken Sie auf **Codeausschnitt-Manager**.</span><span class="sxs-lookup"><span data-stu-id="21c8e-109">To find the pre-defined snippets, open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the **Tools** menu, and click **Code Snippet Manager**.</span></span> <span data-ttu-id="21c8e-110">Wählen Sie im Listenfeld **Sprache** die Option **SQL** aus; der Pfad zu den [!INCLUDE[tsql](../../includes/tsql-md.md)] -Ausschnitten wird im Feld **Speicherort** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="21c8e-110">Select **SQL** in the **Language** list box, the path to the [!INCLUDE[tsql](../../includes/tsql-md.md)] snippets is displayed in the **Location** box.</span></span>  
  
## <a name="registering-the-code-snippet"></a><span data-ttu-id="21c8e-111">Registrieren des Codeausschnitts</span><span class="sxs-lookup"><span data-stu-id="21c8e-111">Registering the Code Snippet</span></span>  
 <span data-ttu-id="21c8e-112">Verwenden Sie nach dem Erstellen der Ausschnittdatei den Codeausschnitt-Manager, um den Ausschnitt bei [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="21c8e-112">After creating the snippet file, use the Code Snippets Manager to register the snippet with [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="21c8e-113">Sie können entweder einen Ordner hinzufügen, der mehrere Ausschnitte enthält, oder einzelne Ausschnitte in den Ordner **Eigene Codeausschnitte** importieren.</span><span class="sxs-lookup"><span data-stu-id="21c8e-113">You can either add a folder containing multiple snippets, or import individual snippets to the **My Code Snippets** folder.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="21c8e-114">Prozeduren</span><span class="sxs-lookup"><span data-stu-id="21c8e-114">Procedures</span></span>  
  
#### <a name="adding-a-snippet-folder"></a><span data-ttu-id="21c8e-115">Hinzufügen eines Ausschnittordners</span><span class="sxs-lookup"><span data-stu-id="21c8e-115">Adding a Snippet Folder</span></span>  
  
1.  <span data-ttu-id="21c8e-116">Öffnen Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21c8e-116">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="21c8e-117">Wählen Sie das Menü **Extras** aus, und klicken Sie auf **Codeausschnitt-Manager**.</span><span class="sxs-lookup"><span data-stu-id="21c8e-117">Select the **Tools** menu, and click **Code Snippets Manager**.</span></span>  
  
3.  <span data-ttu-id="21c8e-118">Klicken Sie auf die Schaltfläche **Hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="21c8e-118">Click the **Add** button.</span></span>  
  
4.  <span data-ttu-id="21c8e-119">Navigieren Sie zum Ordner, der die Codeausschnitte enthält, und klicken Sie auf die Schaltfläche **Ordner auswählen** .</span><span class="sxs-lookup"><span data-stu-id="21c8e-119">Navigate to the folder containing your code snippets, and click the **Select Folder** button.</span></span>  
  
#### <a name="importing-a-snippet"></a><span data-ttu-id="21c8e-120">Importieren eines Ausschnitts</span><span class="sxs-lookup"><span data-stu-id="21c8e-120">Importing a Snippet</span></span>  
  
1.  <span data-ttu-id="21c8e-121">Öffnen Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21c8e-121">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="21c8e-122">Wählen Sie das Menü **Extras** aus, und klicken Sie auf **Codeausschnitt-Manager**.</span><span class="sxs-lookup"><span data-stu-id="21c8e-122">Select the **Tools** menu, and click **Code Snippets Manager**.</span></span>  
  
3.  <span data-ttu-id="21c8e-123">Klicken Sie auf die Schaltfläche **Import** (Importieren).</span><span class="sxs-lookup"><span data-stu-id="21c8e-123">Click the **Import** button.</span></span>  
  
4.  <span data-ttu-id="21c8e-124">Navigieren Sie zum Ordner, der den Ausschnitt enthält, klicken Sie auf die SNIPPET-Datei, und klicken Sie auf die Schaltfläche **Öffnen** .</span><span class="sxs-lookup"><span data-stu-id="21c8e-124">Navigate to the folder containing your snippet, click on the .snippet file, and click the **Open** button.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="21c8e-125">Beispiele</span><span class="sxs-lookup"><span data-stu-id="21c8e-125">Examples</span></span>  
 <span data-ttu-id="21c8e-126">Im folgenden Beispiel wird ein `TRY-CATCH`-Umschließungsausschnitt erstellt und in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] importiert.</span><span class="sxs-lookup"><span data-stu-id="21c8e-126">The following example creates a `TRY-CATCH` surround-with snippet and imports it to [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
1.  <span data-ttu-id="21c8e-127">Fügen Sie den folgenden Code in Editor ein, speichern Sie die Datei dann unter dem Namen "TryCatch.snippet".</span><span class="sxs-lookup"><span data-stu-id="21c8e-127">Paste the following code into notepad, then save as a file named TryCatch.snippet.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <CodeSnippets  xmlns="https://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">  
    <_locDefinition xmlns="urn:locstudio">  
        <_locDefault _loc="locNone" />  
        <_locTag _loc="locData">Title</_locTag>  
        <_locTag _loc="locData">Description</_locTag>  
        <_locTag _loc="locData">Author</_locTag>  
        <_locTag _loc="locData">ToolTip</_locTag>  
       <_locTag _loc="locData">Default</_locTag>  
    </_locDefinition>  
    <CodeSnippet Format="1.0.0">  
    <Header>  
    <Title>TryCatch</Title>  
                            <Shortcut></Shortcut>  
    <Description>Example Snippet for Try-Catch.</Description>  
    <Author>SQL Server Books Online Example</Author>  
    <SnippetTypes>  
                                    <SnippetType>SurroundsWith</SnippetType>  
    </SnippetTypes>  
    </Header>  
    <Snippet>  
    <Declarations>  
                                    <Literal>  
                                    <ID>CatchCode</ID>  
                                    <ToolTip>Code to handle the caught error</ToolTip>  
                                    <Default>CatchCode</Default>  
                                    </Literal>  
    </Declarations>  
    <Code Language="SQL"><![CDATA[  
    BEGIN TRY  
  
    $selected$ $end$  
  
    END TRY  
    BEGIN CATCH  
  
    $CatchCode$  
  
    END CATCH;  
    ]]>  
    </Code>  
    </Snippet>  
    </CodeSnippet>  
    </CodeSnippets>  
    ```  
  
2.  <span data-ttu-id="21c8e-128">Öffnen Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21c8e-128">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
3.  <span data-ttu-id="21c8e-129">Wählen Sie das Menü **Extras** aus, und klicken Sie auf **Codeausschnitt-Manager**.</span><span class="sxs-lookup"><span data-stu-id="21c8e-129">Select the **Tools** menu, and click **Code Snippets Manager**.</span></span>  
  
4.  <span data-ttu-id="21c8e-130">Klicken Sie auf die Schaltfläche **Import** (Importieren).</span><span class="sxs-lookup"><span data-stu-id="21c8e-130">Click the **Import** button.</span></span>  
  
5.  <span data-ttu-id="21c8e-131">Navigieren Sie zum Ordner, der die Datei "TryCatch.snippet" enthält, klicken Sie auf die Datei "TryCatch.snippet", und klicken Sie auf die Schaltfläche **Öffnen** .</span><span class="sxs-lookup"><span data-stu-id="21c8e-131">Navigate to the folder containing TryCatch.snippet, click on the TryCatch.snippet file, and click the **Open** button.</span></span> <span data-ttu-id="21c8e-132">Im Ordner **Eigene Codeausschnitte** sollte kein TryCatch-Ausschnitt vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="21c8e-132">You should not have a TryCatch snippet in your **My Code Snippets** folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21c8e-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="21c8e-133">See Also</span></span>  
 [<span data-ttu-id="21c8e-134">Einfügen von Transact-SQL-Umschließungsausschnitten</span><span class="sxs-lookup"><span data-stu-id="21c8e-134">Insert Surround-with Transact-SQL snippets</span></span>](insert-surround-with-transact-sql-snippets.md)  
  
  
