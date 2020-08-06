---
title: Operatoren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- operators (users) [Database Engine]
- fail-safe operator [SQL Server]
- aliases [SQL Server], operators
- SQL Server Agent alerts, operators
- contact information [SQL Server Agent]
- net send [SQL Server]
- e-mail [SQL Server], SQL Server Agent operators
- pager notifications [SQL Server Agent]
- mail [SQL Server], SQL Server Agent operators
- operators (users) [Database Engine], defining
- jobs [SQL Server Agent], operators
- alerts [SQL Server], operators
ms.assetid: 38e8488f-2669-4cea-b9c3-5f394a663678
author: stevestein
ms.author: sstein
ms.openlocfilehash: d141a2db9a69603701200bc50dcac57ef402968a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720791"
---
# <a name="operators"></a><span data-ttu-id="b7817-102">Operatoren</span><span class="sxs-lookup"><span data-stu-id="b7817-102">Operators</span></span>
  <span data-ttu-id="b7817-103">Operatoren sind Aliasnamen für Personen oder Gruppen, die elektronische Benachrichtigungen erhalten können, sobald ein Auftrag abgeschlossen oder eine Warnung ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="b7817-103">Operators are aliases for people or groups that can receive electronic notification when jobs have completed or alerts have been raised.</span></span> <span data-ttu-id="b7817-104">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst unterstützt die Benachrichtigung der Administratoren durch Operatoren.</span><span class="sxs-lookup"><span data-stu-id="b7817-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service supports the notification of administrators through operators.</span></span> <span data-ttu-id="b7817-105">Durch Operatoren werden Benachrichtigungs- und Überwachungsfunktionen des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b7817-105">Operators enable notification and monitoring capabilities of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
## <a name="operator-attributes-and-concepts"></a><span data-ttu-id="b7817-106">Operatorattribute und -konzepte</span><span class="sxs-lookup"><span data-stu-id="b7817-106">Operator Attributes and Concepts</span></span>  
 <span data-ttu-id="b7817-107">Für Operatoren gelten die folgenden Hauptattribute:</span><span class="sxs-lookup"><span data-stu-id="b7817-107">The primary attributes of an operator are:</span></span>  
  
-   <span data-ttu-id="b7817-108">Operatorname</span><span class="sxs-lookup"><span data-stu-id="b7817-108">Operator name</span></span>  
  
-   <span data-ttu-id="b7817-109">Kontaktinformationen</span><span class="sxs-lookup"><span data-stu-id="b7817-109">Contact information</span></span>  
  
### <a name="naming-an-operator"></a><span data-ttu-id="b7817-110">Benennen eines Operators</span><span class="sxs-lookup"><span data-stu-id="b7817-110">Naming an Operator</span></span>  
 <span data-ttu-id="b7817-111">Jeder Operator muss einen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b7817-111">Every operator must have a name.</span></span> <span data-ttu-id="b7817-112">Operatornamen müssen innerhalb der jeweiligen Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eindeutig sein und dürfen nicht länger als **128** Zeichen lang sein.</span><span class="sxs-lookup"><span data-stu-id="b7817-112">Operator names must be unique within the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance and can be no longer than **128** characters.</span></span>  
  
### <a name="contact-information"></a><span data-ttu-id="b7817-113">Kontaktinformationen</span><span class="sxs-lookup"><span data-stu-id="b7817-113">Contact Information</span></span>  
 <span data-ttu-id="b7817-114">Die Kontaktinformationen eines Operators definieren, wie der Operator benachrichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="b7817-114">An operator's contact information defines how the operator is notified.</span></span> <span data-ttu-id="b7817-115">Operatoren können per E-Mail, per Pager oder über den Befehl **net send** benachrichtigt werden:</span><span class="sxs-lookup"><span data-stu-id="b7817-115">Operators can be notified by e-mail, pager, or through the **net send** command:</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b7817-116">Die Pager- und **net send** -Optionen werden in zukünftigen Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht mehr im [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7817-116">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b7817-117">Nutzen Sie diese Funktionen bei Neuentwicklungen nicht mehr, und planen Sie die Änderung von Anwendungen, die diese Funktionen zurzeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="b7817-117">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="b7817-118">**E-Mail-Benachrichtigung**</span><span class="sxs-lookup"><span data-stu-id="b7817-118">**E-mail notification**</span></span>  
  
     <span data-ttu-id="b7817-119">Der Operator wird per E-Mail benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="b7817-119">E-mail notification sends an e-mail message to the operator.</span></span> <span data-ttu-id="b7817-120">Für die E-Mail-Benachrichtigung geben Sie die E-Mail-Adresse des Operators an.</span><span class="sxs-lookup"><span data-stu-id="b7817-120">For e-mail notification, you provide the e-mail address for the operator.</span></span>  
  
-   <span data-ttu-id="b7817-121">**Pagerbenachrichtigung**</span><span class="sxs-lookup"><span data-stu-id="b7817-121">**Pager notification**</span></span>  
  
     <span data-ttu-id="b7817-122">Die Pagingfunktionen werden mithilfe von E-Mail implementiert.</span><span class="sxs-lookup"><span data-stu-id="b7817-122">Paging is implemented by e-mail.</span></span> <span data-ttu-id="b7817-123">Für die Pagerbenachrichtigung geben Sie die E-Mail-Adresse an, unter der der Operator die Pagernachrichten empfängt.</span><span class="sxs-lookup"><span data-stu-id="b7817-123">For pager notification, you provide the e-mail address where the operator receives pager messages.</span></span> <span data-ttu-id="b7817-124">Zum Einrichten der Pagerbenachrichtigung müssen Sie Software auf dem Mailserver installieren, auf dem eingehende E-Mails verarbeitet und in eine Pagernachricht konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="b7817-124">To set up pager notification, you must install software on the mail server that processes inbound mail and converts it to a pager message.</span></span> <span data-ttu-id="b7817-125">Mit der Software können unterschiedliche Methoden genutzt werden:</span><span class="sxs-lookup"><span data-stu-id="b7817-125">The software can take one of several approaches, including:</span></span>  
  
    -   <span data-ttu-id="b7817-126">Weiterleiten der E-Mail an einen Remotemailserver am Standort des Pageranbieters.</span><span class="sxs-lookup"><span data-stu-id="b7817-126">Forwarding the mail to a remote mail server at the site of the pager provider.</span></span>  
  
         <span data-ttu-id="b7817-127">Der Pageranbieter muss diesen Dienst anbieten, obwohl die erforderliche Software gewöhnlich als Teil des lokalen Mailsystems zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="b7817-127">The pager provider must offer this service, although the software required is generally available as part of the local mail system.</span></span> <span data-ttu-id="b7817-128">Weitere Informationen finden Sie in der Pager-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="b7817-128">For more information, see your pager documentation.</span></span>  
  
    -   <span data-ttu-id="b7817-129">Weiterleiten der E-Mail über das Internet an einen Mailserver am Standort des Pageranbieters.</span><span class="sxs-lookup"><span data-stu-id="b7817-129">Routing the e-mail by way of the Internet to an e-mail server at the pager provider's site.</span></span>  
  
         <span data-ttu-id="b7817-130">Es handelt sich hierbei um eine Variation der ersten Methode.</span><span class="sxs-lookup"><span data-stu-id="b7817-130">This is a variation on the first approach.</span></span>  
  
    -   <span data-ttu-id="b7817-131">Verarbeiten der eingehenden E-Mail und Anwählen des Pagers mithilfe eines angeschlossenen Modems.</span><span class="sxs-lookup"><span data-stu-id="b7817-131">Processing the inbound e-mail and dialing the pager by using an attached modem.</span></span>  
  
         <span data-ttu-id="b7817-132">Diese Software wird vom Pagerdienstanbieter bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b7817-132">This software is proprietary to pager service providers.</span></span> <span data-ttu-id="b7817-133">Die Software agiert als Mailclient, der den Inhalt des Posteingangs in regelmäßigen Abständen verarbeitet, indem entweder alle oder Teile der E-Mail-Adressinformationen als Pagernummern interpretiert werden oder indem E-Mail-Namen einer Pagernummer in einer Übersetzungstabelle zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="b7817-133">The software acts as a e-mail client that periodically processes its inbox either by interpreting all or part of the e-mail address information as a pager number, or by matching the e-mail name to a pager number in a translation table.</span></span>  
  
         <span data-ttu-id="b7817-134">Wenn der gleiche Pageranbieter für alle Operatoren freigegeben wird, können Sie mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] spezielle E-Mail-Formatierungen angeben, die das Umwandlungssystem vom E-Mail-Format zum Pagerformat benötigt.</span><span class="sxs-lookup"><span data-stu-id="b7817-134">If all of the operators share a pager provider, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to specify any special e-mail formatting that is required by the pager-to-e-mail system.</span></span> <span data-ttu-id="b7817-135">Die spezielle Formatierung kann dabei aus einem Präfix oder einem Suffix bestehen und in die folgenden Zeilen der E-Mail eingefügt werden:</span><span class="sxs-lookup"><span data-stu-id="b7817-135">The special formatting can be a prefix or a suffix and can be included in the following lines of the e-mail:</span></span>  
  
         <span data-ttu-id="b7817-136">**:**</span><span class="sxs-lookup"><span data-stu-id="b7817-136">**Subject:**</span></span>  
  
         <span data-ttu-id="b7817-137">**Cc**:</span><span class="sxs-lookup"><span data-stu-id="b7817-137">**Cc**:</span></span>  
  
         <span data-ttu-id="b7817-138">**An**:</span><span class="sxs-lookup"><span data-stu-id="b7817-138">**To**:</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b7817-139">Bei Verwendung eines alphanumerischen Pagingsystems mit niedriger Kapazität können Sie den gesendeten Text kürzen, indem Sie den Fehlertext aus der Pagerbenachrichtigung ausschließen.</span><span class="sxs-lookup"><span data-stu-id="b7817-139">If you use a low-capacity alphanumeric paging system, you can shorten the text that is sent by excluding the error text from the pager notification.</span></span> <span data-ttu-id="b7817-140">Dies empfiehlt sich beispielsweise für Systeme, die auf 64 Zeichen pro Seite begrenzt sind.</span><span class="sxs-lookup"><span data-stu-id="b7817-140">An example of a low-capacity alphanumeric paging system is one that is limited to 64 characters per page.</span></span>  
  
-   <span data-ttu-id="b7817-141">**net sendnotification**</span><span class="sxs-lookup"><span data-stu-id="b7817-141">**net sendnotification**</span></span>  
  
     <span data-ttu-id="b7817-142">Hiermit senden Sie dem Operator eine Nachricht über den Befehl **NET SEND** .</span><span class="sxs-lookup"><span data-stu-id="b7817-142">This sends a message to the operator by means of the **net send** command.</span></span> <span data-ttu-id="b7817-143">Bei **NET SEND**geben Sie den Empfänger (Computer oder Benutzer) einer Netzwerknachricht an.</span><span class="sxs-lookup"><span data-stu-id="b7817-143">For **net send**, specify the recipient (computer or user) of a network message.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b7817-144">Der Befehl **NET SEND** greift auf Microsoft Windows Messenger zurück.</span><span class="sxs-lookup"><span data-stu-id="b7817-144">The **net send** command uses Microsoft Windows Messenger.</span></span> <span data-ttu-id="b7817-145">Um Warnungen fehlerfrei senden zu können, muss dieser Service sowohl auf dem Computer ausgeführt werden, auf dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgeführt wird, als auch auf dem Computer, den der Operator verwendet.</span><span class="sxs-lookup"><span data-stu-id="b7817-145">To successfully send alerts, this service must be running on both the computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running and the computer that the operator uses.</span></span>  
  
## <a name="alerting-and-fail-safe-operators"></a><span data-ttu-id="b7817-146">Warn- und Ausfallsicherheitsoperatoren</span><span class="sxs-lookup"><span data-stu-id="b7817-146">Alerting and Fail-Safe Operators</span></span>  
 <span data-ttu-id="b7817-147">Sie können die Operatoren auswählen, die als Reaktion auf eine Warnung benachrichtigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b7817-147">You can choose which operators are to be notified in response to an alert.</span></span> <span data-ttu-id="b7817-148">So können Sie beispielsweise die Zuständigkeiten bei der Operatorbenachrichtigung abwechselnd zuweisen, indem Sie Zeitpläne für Warnungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="b7817-148">For example, you can assign rotating responsibilities for operator notification by scheduling alerts.</span></span> <span data-ttu-id="b7817-149">Auf diese Weise wird z. B. Person A über Warnungen benachrichtigt, die am Montag, Mittwoch oder Freitag auftreten, und Person B ist für Warnungen am Dienstag, Donnerstag oder Samstag zuständig.</span><span class="sxs-lookup"><span data-stu-id="b7817-149">For example, Individual A is notified of alerts that occur on Monday, Wednesday, or Friday, and Individual B is notified of alerts that occur on Tuesday, Thursday, or Saturday.</span></span>  
  
 <span data-ttu-id="b7817-150">Der Ausfallsicherheitsoperator erhält eine Warnung, nachdem alle Pagerbenachrichtigungen an die angegebenen Operatoren fehlgeschlagen sind.</span><span class="sxs-lookup"><span data-stu-id="b7817-150">The fail-safe operator receives an alert notification after all pager notifications to the designated operators have failed.</span></span> <span data-ttu-id="b7817-151">Wenn Sie beispielsweise drei Operatoren für die Pagerbenachrichtigungen definiert haben und keiner dieser Operatoren per Pager benachrichtigt werden kann, wird der Ausfallsicherheitsoperator benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="b7817-151">For example, if you have defined three operators for pager notifications and none of the designated operators can be paged, the fail-safe operator is notified.</span></span>  
  
 <span data-ttu-id="b7817-152">Der Ausfallsicherheitsoperator wird in den folgenden Fällen benachrichtigt:</span><span class="sxs-lookup"><span data-stu-id="b7817-152">The fail-safe operator is notified when:</span></span>  
  
-   <span data-ttu-id="b7817-153">Die für die Warnung verantwortlichen Operatoren können per Pager nicht benachrichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="b7817-153">The operators responsible for the alert could not be paged.</span></span>  
  
     <span data-ttu-id="b7817-154">Die primären Operatoren sind nicht erreichbar, weil beispielsweise die Pageradresse fehlerhaft ist oder die betreffenden Operatoren möglicherweise gerade außer Dienst sind.</span><span class="sxs-lookup"><span data-stu-id="b7817-154">Reasons for failure to reach primary operators include incorrect pager addresses and off-duty operators.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b7817-155">Agent kann nicht auf Systemtabellen in der **msdb** -Datenbank zugreifen.</span><span class="sxs-lookup"><span data-stu-id="b7817-155">Agent cannot access system tables in the **msdb** database.</span></span>  
  
     <span data-ttu-id="b7817-156">In der **sysnotifications** -Systemtabelle werden die Aufgaben der Operatoren bei Warnungen angegeben.</span><span class="sxs-lookup"><span data-stu-id="b7817-156">The **sysnotifications** system table specifies operator responsibilities for alerts.</span></span>  
  
 <span data-ttu-id="b7817-157">Der Ausfallsicherheitsoperator ist eine Sicherheitsfunktion.</span><span class="sxs-lookup"><span data-stu-id="b7817-157">The fail-safe operator is a security feature.</span></span> <span data-ttu-id="b7817-158">Sie können den Operator, dem der Ausfallsicherheitsdienst zugewiesen wurde, nicht löschen, ohne zuvor die Ausfallsicherheitsaufgabe einem anderen Operator zuzuweisen oder die Ausfallsicherheitszuweisung zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b7817-158">You cannot delete the operator assigned to fail-safe duty without reassigning fail-safe duty to another operator, or deleting the fail-safe assignment altogether.</span></span>  
  
## <a name="notifying-an-operator"></a><span data-ttu-id="b7817-159">Benachrichtigen eines Operators</span><span class="sxs-lookup"><span data-stu-id="b7817-159">Notifying an Operator</span></span>  
 <span data-ttu-id="b7817-160">Sie müssen mindestens eines der folgenden Elemente einrichten, um einen Operator benachrichtigen zu können:</span><span class="sxs-lookup"><span data-stu-id="b7817-160">You must set up one or more of the following in order to notify an operator:</span></span>  
  
-   <span data-ttu-id="b7817-161">Um E-Mails mit den Funktionen von Datenbank-E-Mail senden zu können, benötigen Sie den Zugriff auf einen E-Mail-Server, der SMTP unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b7817-161">To send e-mail with Database Mail functionality, you must have access to an e-mail server that supports SMTP.</span></span>  
  
-   <span data-ttu-id="b7817-162">Für Pagerbenachrichtigungen benötigen Sie Software für Pager-zu-E-Mail von Drittanbietern und/oder die entsprechende Hardware.</span><span class="sxs-lookup"><span data-stu-id="b7817-162">For paging, you must have third-party pager-to-e-mail software and/or hardware.</span></span>  
  
-   <span data-ttu-id="b7817-163">Für den Befehl **NET SEND**muss der Bediener am angegebenen Computer angemeldet sein, und der angegebene Computer muss Nachrichten von Windows Messenger zulassen.</span><span class="sxs-lookup"><span data-stu-id="b7817-163">To use **net send**, the operator must be logged on to the specified computer, and the specified computer must allow messages from Windows Messenger.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="b7817-164">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="b7817-164">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b7817-165">**Aufgaben**</span><span class="sxs-lookup"><span data-stu-id="b7817-165">**Tasks**</span></span>|<span data-ttu-id="b7817-166">**Thema**</span><span class="sxs-lookup"><span data-stu-id="b7817-166">**Topic**</span></span>|  
|<span data-ttu-id="b7817-167">Tasks beim Erstellen eines Operators</span><span class="sxs-lookup"><span data-stu-id="b7817-167">Tasks related to creating an operator</span></span>|[<span data-ttu-id="b7817-168">Erstellen eines Operators</span><span class="sxs-lookup"><span data-stu-id="b7817-168">Create an Operator</span></span>](create-an-operator.md)<br /><br /> [<span data-ttu-id="b7817-169">Designate a Fail-Safe Operator</span><span class="sxs-lookup"><span data-stu-id="b7817-169">Designate a Fail-Safe Operator</span></span>](designate-a-fail-safe-operator.md)|  
|<span data-ttu-id="b7817-170">Tasks beim Zuordnen von Warnungen</span><span class="sxs-lookup"><span data-stu-id="b7817-170">Tasks related to assigning alerts</span></span>|[<span data-ttu-id="b7817-171">Zuweisen von Warnungen zu einem Operator</span><span class="sxs-lookup"><span data-stu-id="b7817-171">Assign Alerts to an Operator</span></span>](assign-alerts-to-an-operator.md)<br /><br /> [<span data-ttu-id="b7817-172">Definieren der Antwort auf eine Warnung &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="b7817-172">Define the Response to an Alert &#40;SQL Server Management Studio&#41;</span></span>](define-the-response-to-an-alert-sql-server-management-studio.md)<br /><br /> [<span data-ttu-id="b7817-173">sp_add_notification &#40;Transact-SQL-&#41;</span><span class="sxs-lookup"><span data-stu-id="b7817-173">sp_add_notification &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql)<br /><br /> [<span data-ttu-id="b7817-174">Zuweisen von Warnungen zu einem Operator</span><span class="sxs-lookup"><span data-stu-id="b7817-174">Assign Alerts to an Operator</span></span>](assign-alerts-to-an-operator.md)|  
  
## <a name="see-also"></a><span data-ttu-id="b7817-175">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b7817-175">See Also</span></span>  
 [<span data-ttu-id="b7817-176">Datenbank-E-Mail</span><span class="sxs-lookup"><span data-stu-id="b7817-176">Database Mail</span></span>](../../relational-databases/database-mail/database-mail.md)  
  
  
