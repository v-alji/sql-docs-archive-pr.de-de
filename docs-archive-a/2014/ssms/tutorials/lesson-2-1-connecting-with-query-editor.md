---
title: Herstellen einer Verbindung mit dem Abfrage-Editor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 48725f54-a7b6-4b79-948e-965c1fe4eef1
author: stevestein
ms.author: sstein
ms.openlocfilehash: b50783450dfb9516c78a465806ee322d7a575377
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619507"
---
# <a name="connecting-with-query-editor"></a><span data-ttu-id="7146a-102">Herstellen einer Verbindung mit dem Abfrage-Editor</span><span class="sxs-lookup"><span data-stu-id="7146a-102">Connecting with Query Editor</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="7146a-103">können Sie auch dann Code schreiben oder bearbeiten, wenn Sie nicht mit dem Server verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="7146a-103">permits you to write or edit code while disconnected from the server.</span></span> <span data-ttu-id="7146a-104">Dies kann nützlich sein, wenn der Server nicht verfügbar ist oder wenn die Ressourcen auf dem Server oder im Netzwerk knapp sind.</span><span class="sxs-lookup"><span data-stu-id="7146a-104">This can be useful when the server is not available or when you want to conserve scarce server or network resources.</span></span> <span data-ttu-id="7146a-105">Sie können auch den Abfrage-Editor mit einer neuen Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verbinden, ohne ein neues Abfrage-Editorfenster zu öffnen und ohne den Code neu einzugeben.</span><span class="sxs-lookup"><span data-stu-id="7146a-105">You can also change the connection of Query Editor to a new instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without opening a new Query Editor window or retyping your code.</span></span>  
  
## <a name="coding-offline"></a><span data-ttu-id="7146a-106">Schreiben von Code offline</span><span class="sxs-lookup"><span data-stu-id="7146a-106">Coding Offline</span></span>  
  
#### <a name="to-write-code-offline-and-then-connect-to-different-servers"></a><span data-ttu-id="7146a-107">So schreiben Sie Code offline und stellen dann Verbindungen mit verschiedenen Servern her</span><span class="sxs-lookup"><span data-stu-id="7146a-107">To write code offline and then connect to different servers</span></span>  
  
1.  <span data-ttu-id="7146a-108">Klicken Sie auf der Symbolleiste von [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] auf **Datenbank-Engine-Abfrage** , um den Abfrage-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7146a-108">On the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] toolbar, click **Database Engine Query** to open the Query Editor.</span></span>  
  
2.  <span data-ttu-id="7146a-109">Klicken Sie im Dialogfeld **Verbindung mit Datenbank-Engine herstellen** auf **Abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="7146a-109">In the **Connect to Database Engine** dialog box, click **Cancel**.</span></span> <span data-ttu-id="7146a-110">Der Abfrage-Editor wird geöffnet, und in der Titelleiste des Abfrage-Editors wird angezeigt, dass Sie mit keiner Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="7146a-110">The Query Editor opens, and the title bar for the Query Editor indicates that you are not connected to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="7146a-111">Geben Sie im Codebereich folgende [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen ein:</span><span class="sxs-lookup"><span data-stu-id="7146a-111">In the code pane, type the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    SELECT * FROM Production.Product;  
    GO  
    ```  
  
     <span data-ttu-id="7146a-112">An diesem Punkt können Sie eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herstellen, indem Sie auf **Verbinden**, **Ausführen**, **Analysieren**oder **Geschätzten Ausführungsplan anzeigen**klicken. Alle diese Optionen sind im Menü **Abfrage** , auf der Symbolleiste des Abfrage-Editors oder in dem Kontextmenü verfügbar, das angezeigt wird, wenn Sie mit der rechten Maustaste in das Abfrage-Editorfenster klicken.</span><span class="sxs-lookup"><span data-stu-id="7146a-112">At this point you can connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by clicking **Connect**, **Execute**, **Parse**, or **Display Estimated Execution Plan**, all of which are available from either the **Query** menu, the Query Editor toolbar, or from the shortcut menu when you right-click in the Query Editor window.</span></span> <span data-ttu-id="7146a-113">Im Rahmen dieser Übung verwenden wir die Symbolleiste.</span><span class="sxs-lookup"><span data-stu-id="7146a-113">For this practice, we'll use the toolbar.</span></span>  
  
4.  <span data-ttu-id="7146a-114">Klicken Sie auf der Symbolleiste auf die Schaltfläche **Ausführen** , um das Dialogfeld **Verbindung mit Datenbank-Engine herstellen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7146a-114">On the toolbar, click the **Execute** button to open the **Connect to Database Engine** dialog box.</span></span>  
  
5.  <span data-ttu-id="7146a-115">Geben Sie im Textfeld **Servername** den Namen Ihres Servers ein, und klicken Sie dann auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="7146a-115">In the **Server name** text box, type your server name, and then click **Options**.</span></span>  
  
6.  <span data-ttu-id="7146a-116">Durchsuchen Sie auf der Registerkarte **Verbindungseigenschaften** in der Liste **Verbindung mit Datenbank herstellen** den Server, um [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] auszuwählen, und klicken Sie dann auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="7146a-116">On the **Connection Properties** tab, in the **Connect to database** list, browse the server to select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] and then click **Connect**.</span></span>  
  
7.  <span data-ttu-id="7146a-117">Wenn Sie für dieselbe Verbindung ein weiteres Abfrage-Editorfenster öffnen möchten, klicken Sie auf das Symbolleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="7146a-117">To open another Query Editor window with the same connection, on the toolbar click **New Query**.</span></span>  
  
8.  <span data-ttu-id="7146a-118">Klicken Sie mit der rechten Maustaste auf das Abfrage-Editor-Fenster, zeigen Sie auf **Verbindung**, und klicken Sie anschließend auf **Verbindung ändern**, um die Verbindungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7146a-118">To change connections, right-click in the Query Editor window, point to **Connection**, and then click **Change Connection**.</span></span>  
  
9. <span data-ttu-id="7146a-119">Wählen Sie im Dialogfeld **Verbindung mit SQL Server herstellen** eine andere Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (falls verfügbar), und klicken Sie dann auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="7146a-119">In the **Connect to SQL Server** dialog box, select another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if available, and then click **Connect**.</span></span>  
  
 <span data-ttu-id="7146a-120">Diese neue Funktion des Abfrage-Editors ermöglicht es Ihnen, denselben Code auf mehreren Servern auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7146a-120">This new feature of Query Editor enables you to easily run the same code on several servers.</span></span> <span data-ttu-id="7146a-121">Dies kann für Wartungsaktionen nützlich sein, an denen mehrere Server beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="7146a-121">This may be useful for maintenance actions involving similar servers.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="7146a-122">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="7146a-122">Next Task in Lesson</span></span>  
 [<span data-ttu-id="7146a-123">Hinzufügen von Einzügen</span><span class="sxs-lookup"><span data-stu-id="7146a-123">Adding Indentation</span></span>](lesson-2-2-adding-indentation.md)  
  
  
