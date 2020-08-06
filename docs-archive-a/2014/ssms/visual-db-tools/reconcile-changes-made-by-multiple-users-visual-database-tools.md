---
title: Abstimmen der Änderungen von mehreren Benutzern (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- table modifications [SQL Server], multiple users
- reconciling changes made by multiple users
- modifications made by multiple users
ms.assetid: fc7ed4f2-ad3d-47fc-a3ef-51e5bb069ef0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 337d505fce474a33301c18313fe6137f6bc0ec1b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697333"
---
# <a name="reconcile-changes-made-by-multiple-users-visual-database-tools"></a><span data-ttu-id="7f83e-102">Abstimmen der Änderungen von mehreren Benutzern (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="7f83e-102">Reconcile Changes Made by Multiple Users (Visual Database Tools)</span></span>
  <span data-ttu-id="7f83e-103">In einer Mehrbenutzerumgebung können mehrere Benutzer gleichzeitig Änderungen an ein und demselben Objekt vornehmen.</span><span class="sxs-lookup"><span data-stu-id="7f83e-103">In a multiuser environment, changes can be made on the same object by multiple users at once.</span></span> <span data-ttu-id="7f83e-104">Diese Situation kann auftreten, wenn Sie an der Struktur des Objekts im Tabellen-Designer oder im Datenbankdiagramm-Designer arbeiten, oder bei Ergebniswerten, die im Ergebnisbereich des Abfrage- und Sicht-Designers zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7f83e-104">This can happen when you're working on the structure of the object in the Table or Database Diagram designers or it can happen to values in the results returned in the Query and View designer's Results pane.</span></span> <span data-ttu-id="7f83e-105">Dies kann Konflikte verursachen, die aufgelöst werden sollten.</span><span class="sxs-lookup"><span data-stu-id="7f83e-105">This can cause conflicts that you'll want to resolve.</span></span>  
  
## <a name="conflicts-in-the-table-or-database-diagram-designers"></a><span data-ttu-id="7f83e-106">Konflikte im Tabellen-Designer oder im Datenbankdiagramm-Designer</span><span class="sxs-lookup"><span data-stu-id="7f83e-106">Conflicts in the Table or Database Diagram Designers</span></span>  
 <span data-ttu-id="7f83e-107">Beispielsweise kann ein Benutzer eine Tabelle löschen oder umbenennen, während Sie gerade an derselben Tabelle oder einer verknüpften Tabelle im Tabellen-Designer arbeiten.</span><span class="sxs-lookup"><span data-stu-id="7f83e-107">For example, another user might delete or rename a table while you are working with the same or a related table in Table Designer.</span></span> <span data-ttu-id="7f83e-108">Wenn Sie versuchen, die Tabelle zu speichern, werden Sie vom [Es wurden Änderungen in der Datenbank festgestellt (Dialogfeld) &#40;Visual Database Tools&#41;](visual-database-tools.md) darüber benachrichtigt, dass die Datenbank nach dem Öffnen der Tabelle aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7f83e-108">When you attempt to save your table, the [Database Changes Detected Dialog Box &#40;Visual Database Tools&#41;](visual-database-tools.md) notifies you that the database has been updated since you opened the table.</span></span>  
  
 <span data-ttu-id="7f83e-109">In diesem Dialogfeld finden Sie auch eine Liste der Datenbankobjekte, die durch das Speichern der Tabelle beeinflusst werden.</span><span class="sxs-lookup"><span data-stu-id="7f83e-109">This dialog box also displays a list of database objects that will be affected as a result of saving your table.</span></span> <span data-ttu-id="7f83e-110">Sie können hier eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="7f83e-110">At this point, you can take one of these actions:</span></span>  
  
-   <span data-ttu-id="7f83e-111">Wählen Sie **Ja** aus, um die Tabelle zu speichern und die Datenbank mit allen Änderungen in der Liste zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7f83e-111">Choose **Yes** to save your table and update the database with all the changes in the list.</span></span>  
  
     <span data-ttu-id="7f83e-112">Diese Aktion kann sich auch auf Tabellen auswirken, die dieselben Datenbankobjekte nutzen.</span><span class="sxs-lookup"><span data-stu-id="7f83e-112">This action could affect tables that share the same database objects.</span></span> <span data-ttu-id="7f83e-113">Angenommen, Sie ändern in der Tabelle `au`die Spalte`id` _ `titleauthors` , und ein anderer Benutzer arbeitet an der Tabelle `authors` , die über die Spalte `titleauthors` mit der Tabelle `au`\_`id` verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="7f83e-113">For example, suppose you edit the `au`_`id` column in the `titleauthors` table while another user is working on the `authors` table which is related to the `titleauthors` table by the `au`\_`id` column.</span></span> <span data-ttu-id="7f83e-114">Wenn Sie Ihre Tabelle speichern, wirkt sich dies auf die Tabelle des anderen Benutzers aus.</span><span class="sxs-lookup"><span data-stu-id="7f83e-114">Saving your table will affect the other user's table.</span></span> <span data-ttu-id="7f83e-115">Ein ähnlicher Fall liegt vor, wenn ein anderer Benutzer in der Tabelle `qty` eine CHECK-Einschränkung für die Spalte `sales` definiert hat.</span><span class="sxs-lookup"><span data-stu-id="7f83e-115">Similarly, suppose that another user defined a check constraint for the `qty` column in the `sales` table.</span></span> <span data-ttu-id="7f83e-116">Wenn Sie die Spalte `qty` löschen und die Tabelle `sales` speichern, wirkt sich dies auf die CHECK-Einschränkung des anderen Benutzers aus.</span><span class="sxs-lookup"><span data-stu-id="7f83e-116">If you delete the `qty` column and save the `sales` table, the other user's check constraint will be affected.</span></span>  
  
-   <span data-ttu-id="7f83e-117">Wählen Sie **Nein** aus, um den Speichervorgang abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="7f83e-117">Choose **No** to cancel the save action.</span></span>  
  
     <span data-ttu-id="7f83e-118">Sie können die Tabelle jetzt schließen, ohne sie zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7f83e-118">You can then close the table without saving it.</span></span> <span data-ttu-id="7f83e-119">Wenn Sie die Tabelle erneut öffnen, wird diese mit dem Inhalt der Datenbank angepasst.</span><span class="sxs-lookup"><span data-stu-id="7f83e-119">When you reopen the table it will match what is in the database.</span></span>  
  
-   <span data-ttu-id="7f83e-120">Wählen Sie **Textdatei speichern** aus, um eine Liste der Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7f83e-120">Choose **Save Text File** to save a list of the changes.</span></span>  
  
     <span data-ttu-id="7f83e-121">Sie können die im Dialogfeld **Es wurden Änderungen in der Datenbank festgestellt** aufgelisteten Datenbankänderungen in einer Textdatei speichern, sodass Sie die Gründe untersuchen können, die andere Benutzer für ihre Änderungen hatten.</span><span class="sxs-lookup"><span data-stu-id="7f83e-121">You can save the list of database changes shown in the **Database Changes Detected** dialog box to a text file so that you can investigate the cause of other users' changes.</span></span> <span data-ttu-id="7f83e-122">Wenn ein anderer Benutzer z. B. eine Tabelle geändert hat, die Sie zum Löschen ausgewählt haben, können Sie überprüfen, ob die Tabelle vor dem Aktualisieren der Datenbank gelöscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="7f83e-122">For example, if another user edited a table that you marked for deletion, you may want to research whether the table should be deleted before updating the database.</span></span>  
  
## <a name="conflicts-in-the-query-and-view-designer"></a><span data-ttu-id="7f83e-123">Konflikte im Abfrage- und Sicht-Designer</span><span class="sxs-lookup"><span data-stu-id="7f83e-123">Conflicts in the Query and View Designer</span></span>  
 <span data-ttu-id="7f83e-124">Wenn Sie eine Abfrage ausführen oder die Ergebnisse einer Ansicht zurückgeben lassen, werden die Daten im [Ergebnisbereich](results-pane-visual-database-tools.md)angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7f83e-124">If you run a query or return the results of a view, the data is shown in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="7f83e-125">Da mehrere Benutzer gleichzeitig an derselben Gruppe von Daten arbeiten können, kann es zu Konflikten kommen.</span><span class="sxs-lookup"><span data-stu-id="7f83e-125">Multiple users can work on the same set of data at the same time, which can cause conflicts.</span></span>  
  
 <span data-ttu-id="7f83e-126">Beispielsweise führen Sie und ein Kollege jeweils eine Abfrage aus, um die gesamten Daten in der Tabelle `titleauthors` anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7f83e-126">For example, lets say you and a colleague each run a query to show all the data in the `titleauthors` table.</span></span> <span data-ttu-id="7f83e-127">Ihr Kollege ändert den ersten Namen im ersten zurückgegebenen Datensatz von Barb in Barbara.</span><span class="sxs-lookup"><span data-stu-id="7f83e-127">Your colleague changes the first name in the first record returned from Barb to Barbara.</span></span> <span data-ttu-id="7f83e-128">Zu diesem Zeitpunkt enthält dieses Feld in der Datenbank Barbara, während in Ihrem Resultset immer noch Barb angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7f83e-128">At this point the database has Barbara in that field, while your result set still shows Barb.</span></span> <span data-ttu-id="7f83e-129">Sie geben jetzt Barbara ein und klicken auf eine Stelle außerhalb der Zeile.</span><span class="sxs-lookup"><span data-stu-id="7f83e-129">Now you type in Barbara and click off of the row.</span></span> <span data-ttu-id="7f83e-130">Daraufhin erhalten Sie eine Meldung, in der Sie zum Auflösen des Konflikts aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="7f83e-130">You will receive a message asking you how you want to resolve the conflict.</span></span>  
  
-   <span data-ttu-id="7f83e-131">Klicken Sie auf **Ja** , um die Datenbank mit den Änderungen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7f83e-131">Click **Yes** to update the database with your changes.</span></span>  
  
     <span data-ttu-id="7f83e-132">Dadurch werden die Änderungen Ihres Kollegen überschrieben.</span><span class="sxs-lookup"><span data-stu-id="7f83e-132">This will override your colleague's changes.</span></span>  
  
-   <span data-ttu-id="7f83e-133">Klicken Sie auf **Nein** , um das Resultset mit den aktuellen Daten aus der Datenbank zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7f83e-133">Click **No** to have your result set updated to what's currently in the database.</span></span>  
  
     <span data-ttu-id="7f83e-134">Dadurch werden Ihre Änderungen mit den Änderungen Ihres Kollegen überschrieben.</span><span class="sxs-lookup"><span data-stu-id="7f83e-134">This will override your changes with those of your colleague's.</span></span>  
  
-   <span data-ttu-id="7f83e-135">Klicken Sie auf **Abbrechen** , um die Bearbeitung fortzusetzen, ohne den Konflikt aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="7f83e-135">Click **Cancel** to continue to edit without resolving the conflict.</span></span>  
  
     <span data-ttu-id="7f83e-136">In diesem Fall können Sie Ihre Änderungen nicht in die Datenbank übernehmen.</span><span class="sxs-lookup"><span data-stu-id="7f83e-136">In this case you will not be able to commit your changes to the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f83e-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7f83e-137">See Also</span></span>  
 [<span data-ttu-id="7f83e-138">Es wurden Änderungen in der Datenbank festgestellt (Dialogfeld) &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="7f83e-138">Database Changes Detected Dialog Box &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
