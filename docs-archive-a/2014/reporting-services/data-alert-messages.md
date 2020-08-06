---
title: Datenwarnmeldungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6819720c-d848-4b90-9b51-89501b4f4645
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d50c3dd24c0057f695a9318c5eef7ad9e7540a45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619649"
---
# <a name="data-alert-messages"></a><span data-ttu-id="70775-102">Datenwarnmeldungen</span><span class="sxs-lookup"><span data-stu-id="70775-102">Data Alert Messages</span></span>
  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="70775-103">-Datenwarnungen übermitteln zwei Typen von Datenwarnmeldungen per E-Mail: Meldungen mit Datenwarnungsergebnissen und Meldungen mit Fehlerbeschreibungen.</span><span class="sxs-lookup"><span data-stu-id="70775-103">data alerts deliver two types of data alert messages by email: Messages with data alert results and messages with error descriptions.</span></span> <span data-ttu-id="70775-104">Durch Meldungen mit Ergebnissen werden alle Empfänger über Änderungen der Berichtsdaten informiert, die von allgemeinem Interesse und wichtig für Geschäftsentscheidungen sind.</span><span class="sxs-lookup"><span data-stu-id="70775-104">Messages with results keep all recipients informed about changes in report data that is of common interest and important to business decisions.</span></span> <span data-ttu-id="70775-105">Tritt aus einem unbestimmten Grund ein Fehler auf, und sind die Ergebnisse nicht verfügbar, wird stattdessen die Fehlermeldung gesendet.</span><span class="sxs-lookup"><span data-stu-id="70775-105">If for some reason an error occurs and the results are not available, the error message is sent instead.</span></span>

 <span data-ttu-id="70775-106">Der Eigentümer der Datenwarnungsdefinition kann auch Informationen zur Datenwarnungsinstanz im Datenwarnungs-Manager anzeigen.</span><span class="sxs-lookup"><span data-stu-id="70775-106">The owner of the data alert definition also can view information about the data alert instance in Data Alert Manager.</span></span> <span data-ttu-id="70775-107">Weitere Informationen finden Sie unter [Data Alert Manager for SharePoint Users](../../2014/reporting-services/data-alert-manager-for-sharepoint-users.md).</span><span class="sxs-lookup"><span data-stu-id="70775-107">For more information, see [Data Alert Manager for SharePoint Users](../../2014/reporting-services/data-alert-manager-for-sharepoint-users.md).</span></span>

##  <a name="data-alert-messages"></a><a name="DataAlertMessages"></a><span data-ttu-id="70775-108">Daten Warnmeldungen</span><span class="sxs-lookup"><span data-stu-id="70775-108">Data Alert Messages</span></span>
 <span data-ttu-id="70775-109">Die folgenden Bilder zeigen eine Datenwarnmeldung mit Ergebnissen und eine Warnmeldung mit einer Fehlerbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="70775-109">The following pictures show a data alert message with results and an alert message with an error description.</span></span>

 <span data-ttu-id="70775-110">**Ergebnismeldung**</span><span class="sxs-lookup"><span data-stu-id="70775-110">**Results message**</span></span>

 <span data-ttu-id="70775-111">![E-Mail mit Datenwarnung mit Ergebnissen](media/rs-alertmessageresults.gif "E-Mail mit Datenwarnung mit Ergebnissen")</span><span class="sxs-lookup"><span data-stu-id="70775-111">![Data alert e-mail message with results](media/rs-alertmessageresults.gif "Data alert e-mail message with results")</span></span>

 <span data-ttu-id="70775-112">**Fehlermeldung**</span><span class="sxs-lookup"><span data-stu-id="70775-112">**Error message**</span></span>

 <span data-ttu-id="70775-113">![Datenwarnmeldung mit Fehlermeldung](media/rs-alertmessageerrror.gif "Datenwarnmeldung mit Fehlermeldung")</span><span class="sxs-lookup"><span data-stu-id="70775-113">![Data alert message with error message](media/rs-alertmessageerrror.gif "Data alert message with error message")</span></span>

 <span data-ttu-id="70775-114">Die Meldungen beinhalten die gleichen Informationstypen.</span><span class="sxs-lookup"><span data-stu-id="70775-114">The messages include the same types of information.</span></span>

1.  <span data-ttu-id="70775-115">**Im Auftrag von** enthält den Namen des Erstellers der Datenwarnungsdefinition.</span><span class="sxs-lookup"><span data-stu-id="70775-115">**On behalf of** contains the name of the person who created the data alert definition.</span></span>

2.  <span data-ttu-id="70775-116">Haben Sie in der Warnungsdefinition eine Beschreibung angegeben, wird diese unterhalb von **Im Auftrag von**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="70775-116">If you provided a description in the alert definition, it displays below **On behalf of**.</span></span>

3.  <span data-ttu-id="70775-117">**Warnungsergebnisse** zeigen die Zeilen im Berichtsdatenfeed, der die in der Warnungsdefinition angegebenen Regeln erfüllt, in einem Tabellenformat oder eine Fehlermeldung an.</span><span class="sxs-lookup"><span data-stu-id="70775-117">**Alert Results** display the rows in the report data feed that satisfy the rules specified in the alert definition in a tabular format or display an error description.</span></span> <span data-ttu-id="70775-118">Die Anzahl der angezeigten Zeilen ist unbeschränkt.</span><span class="sxs-lookup"><span data-stu-id="70775-118">There is no limit on the number of rows that displays.</span></span>

4.  <span data-ttu-id="70775-119">**Gehe zu Bericht** ist ein Link zum Bericht, auf dem die Warnungsdefinition basiert.</span><span class="sxs-lookup"><span data-stu-id="70775-119">**Go to report** is a link to the report that the alert definition is built upon.</span></span> <span data-ttu-id="70775-120">Wenn der Link nicht gültig ist, da der Bericht verschoben oder gelöscht wurde, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="70775-120">If the link is not valid because the report was moved or deleted, an error message displays.</span></span>

5.  <span data-ttu-id="70775-121">**Regel(n)** listet die Regeln und Klauseln in der Warnungsdefinition auf.</span><span class="sxs-lookup"><span data-stu-id="70775-121">**Rule(s)** lists the rules and clauses in the alert definition.</span></span> <span data-ttu-id="70775-122">Anhand dieser Informationen lassen sich die Warnungsergebnisse leichter überprüfen und verstehen. Des Weiteren lassen sich die Regeln in der Datenwarnungsdefinition identifizieren, die Sie ggf. zum Eingrenzen oder Erweitern der Ergebnisse ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="70775-122">This information helps you verify and understand the alert results and identify rules in the data alert definition that you might want to change to narrow or broaden results.</span></span>

6.  <span data-ttu-id="70775-123">**Berichtsparameter** listet die Parameter und Parameterwerte auf, mit denen der Bericht ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="70775-123">**Report parameters** list the parameters and parameter values that were used when the report was run.</span></span> <span data-ttu-id="70775-124">Parameter und Parameterwerte vereinfachen den Einblick in die Warnungsergebnisse.</span><span class="sxs-lookup"><span data-stu-id="70775-124">Parameters and parameter values help you understand the alert results.</span></span>

7.  <span data-ttu-id="70775-125">**Kontextwerte** beinhalten die Namen und Werte von Berichtselementen, die sich außerhalb der Berichtsdatenbereiche befinden.</span><span class="sxs-lookup"><span data-stu-id="70775-125">**Contextual values** list the names and values of report items that are outside of the report data regions.</span></span> <span data-ttu-id="70775-126">Die Elemente sind in der Regel Textfelder.</span><span class="sxs-lookup"><span data-stu-id="70775-126">The items are typically text boxes.</span></span> <span data-ttu-id="70775-127">Es kann sich zum Beispiel um ein Textfeld mit einem konstanten Wert wie dem Betreff oder der Beschreibung eines Berichts handeln.</span><span class="sxs-lookup"><span data-stu-id="70775-127">For example, a text box with a constant value such as the subject or description of a report.</span></span>

 <span data-ttu-id="70775-128">Der einzige Unterschied zwischen den zwei Meldungstypen ist Element 5, **Warnungsergebnisse**.</span><span class="sxs-lookup"><span data-stu-id="70775-128">The only difference between the two message types is item 5, **Alert Results**.</span></span> <span data-ttu-id="70775-129">Tritt bei der Erstellung einer Datenwarnungsinstanz oder Datenwarnmeldung ein Fehler auf, zeigt **Warnungsergebnisse** eine Fehlermeldung mit der Beschreibung des Problems an.</span><span class="sxs-lookup"><span data-stu-id="70775-129">If an error occurs when a data alert instance or data alert message is created, **Alert Results** displays an error message that describes the problem.</span></span> <span data-ttu-id="70775-130">Die Fehlermeldung wird an alle Empfänger gesendet und informiert diese, dass die erwarteten Warnungsergebnisse, die die Empfänger u. U. auch für Geschäftsentscheidungen benötigen, nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="70775-130">The error message, sent to all recipients, let them know that the alert results that they are expecting and might rely on to make business decisions are not available.</span></span>

 

##  <a name="related-tasks"></a><a name="HowTo"></a> <span data-ttu-id="70775-131">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="70775-131">Related Tasks</span></span>
 <span data-ttu-id="70775-132">Dieser Abschnitt listet Prozeduren zum Erstellen und Bearbeiten der Datenwarnungsdefinitionen auf, die viele der in den Datenwarnmeldungen angezeigten Informationen bieten.</span><span class="sxs-lookup"><span data-stu-id="70775-132">This section lists procedures that show you how to create and edit the data alert definitions that provide much of the information that you see in data alert messages.</span></span>

-   [<span data-ttu-id="70775-133">Create a Data Alert in Data Alert Designer (Erstellen einer Datenwarnung im Datenwarnungs-Designer)</span><span class="sxs-lookup"><span data-stu-id="70775-133">Create a Data Alert in Data Alert Designer</span></span>](create-a-data-alert-in-data-alert-designer.md)

-   [<span data-ttu-id="70775-134">Edit a Data Alert in Alert Designer (Bearbeiten einer Datenwarnung im Warnungs-Designer)</span><span class="sxs-lookup"><span data-stu-id="70775-134">Edit a Data Alert in Alert Designer</span></span>](edit-a-data-alert-in-alert-designer.md)



## <a name="see-also"></a><span data-ttu-id="70775-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="70775-135">See Also</span></span>
 <span data-ttu-id="70775-136">[Datenwarnungs-Designer](../../2014/reporting-services/data-alert-designer.md) [Reporting Services Daten Warnungen](../ssms/agent/alerts.md)</span><span class="sxs-lookup"><span data-stu-id="70775-136">[Data Alert Designer](../../2014/reporting-services/data-alert-designer.md) [Reporting Services Data Alerts](../ssms/agent/alerts.md)</span></span>


