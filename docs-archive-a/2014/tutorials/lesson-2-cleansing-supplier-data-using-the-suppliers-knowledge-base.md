---
title: 'Lektion 2: Bereinigung von Lieferantendaten mithilfe der Wissensdatenbank "Suppliers" | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 215c14de-fc3f-46de-a022-bf69b9ea2a96
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ebc0231cd0f28fcad23656cf22abd8d68eca7dc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608164"
---
# <a name="lesson-2-cleansing-supplier-data-using-the-suppliers-knowledge-base"></a><span data-ttu-id="fd7be-102">Lektion 2: Bereinigung von Lieferantendaten mithilfe der Wissensdatenbank „Suppliers“</span><span class="sxs-lookup"><span data-stu-id="fd7be-102">Lesson 2: Cleansing Supplier Data using the Suppliers Knowledge Base</span></span>
  <span data-ttu-id="fd7be-103">In dieser Lektion bereinigen Sie die Lieferantendaten in einer Excel-Datei, indem Sie die Wissensdatenbank **Suppliers** verwenden, die Sie in der ersten Lektion erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="fd7be-103">In this lesson, you cleanse the supplier data in an Excel file by using the **Suppliers** knowledge base you have created in the first lesson.</span></span> <span data-ttu-id="fd7be-104">Die Datenbereinigung in DQS umfasst einen **computergestützten Prozess** , der analysiert, wie Daten den Kenntnissen in einer Wissensdatenbank entsprechen, sowie einen **interaktiven Prozess** , mit dem Sie die Ergebnisse des computergestützten Prozesses überprüfen und ändern können.</span><span class="sxs-lookup"><span data-stu-id="fd7be-104">Data cleansing in DQS includes a **computer-assisted process** that analyzes how data conforms to the knowledge in a knowledge base, and an **interactive process** that enables you to review and modify results from the computer-assisted process.</span></span> <span data-ttu-id="fd7be-105">Die Datenbereinigungsfunktion identifiziert falsche Daten in der Datenquelle und korrigiert diese anschließend oder schlägt Korrekturen für die falschen Daten vor.</span><span class="sxs-lookup"><span data-stu-id="fd7be-105">The data cleansing feature identifies incorrect data in your data source and then corrects or suggests corrections for the incorrect data.</span></span> <span data-ttu-id="fd7be-106">Darüber hinaus standardisiert und erweitert sie Kundendaten unter Verwendung von Domänenwerten, führenden Werten für Synonyme, Domänenregeln, begriffsbasierten Beziehungen und Verweisdaten.</span><span class="sxs-lookup"><span data-stu-id="fd7be-106">It also standardizes and enriches customer data by using domain values, leading values for synonyms, domain rules, term-based relations, and reference data.</span></span> <span data-ttu-id="fd7be-107">Sie können die vom computergestützten Prozess vorgeschlagenen Änderungen interaktiv genehmigen oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="fd7be-107">You can interactively approve or reject changes proposed by the computer-assisted process.</span></span> <span data-ttu-id="fd7be-108">Weitere Informationen finden Sie unter [Datenbereinigung](https://msdn.microsoft.com/library/gg524800.aspx) .</span><span class="sxs-lookup"><span data-stu-id="fd7be-108">See [Data Cleansing](https://msdn.microsoft.com/library/gg524800.aspx) for more details.</span></span>  
  
 <span data-ttu-id="fd7be-109">Der computergestützte Prozess verwendet die folgenden Schwellenwerte, die Sie mithilfe der Konfigurationsoption auf der DQS-Client-Hauptseite konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="fd7be-109">The computer-assisted process uses the following threshold values that you can configure using the Configuration option on the DQS Client main page.</span></span>  
  
-   <span data-ttu-id="fd7be-110">**Minimale Bewertung für Vorschläge:** Das minimale Ergebnis oder der Vertrauensgrad, der von DQS zum vorschlagen der Ersetzung für einen Wert verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fd7be-110">**Min score for suggestions:** The minimum score or confidence level that is used by DQS for suggesting replacement for a value.</span></span>  
  
-   <span data-ttu-id="fd7be-111">**Minimale Bewertung für automatische Korrekturen:** Das minimale Ergebnis oder der Vertrauensgrad, der von DQS zum automatischen Korrigieren eines Werts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fd7be-111">**Min score for auto corrections:** The minimum score or confidence level that is used by DQS for automatically correcting a value.</span></span>  
  
 <span data-ttu-id="fd7be-112">Ausführliche Informationen zum Konfigurieren dieser Einstellungen finden Sie unter [Konfigurieren der Schwellenwerte für Bereinigung und](https://msdn.microsoft.com/library/hh510415.aspx) Abgleich.</span><span class="sxs-lookup"><span data-stu-id="fd7be-112">See [Configure Threshold Values for Cleansing and Matching](https://msdn.microsoft.com/library/hh510415.aspx) for details on how to configure these settings.</span></span>  
  
 <span data-ttu-id="fd7be-113">In dieser Lektion führen Sie die folgenden Aufgaben für die Wissensdatenbank "Suppliers" aus, um die Eingabedaten zu bereinigen.</span><span class="sxs-lookup"><span data-stu-id="fd7be-113">In this lesson, you perform the following tasks to cleanse the input data by using the Suppliers knowledge base.</span></span>  
  
1.  <span data-ttu-id="fd7be-114">Erstellen Sie ein Data Quality-Projekt für die Bereinigung, wählen Sie die Wissensdatenbank "Suppliers" als Wissensdatenbank für die Analyse und Bereinigung der Quelldaten in einer Excel-Datei aus, und wählen Sie die Bereinigungsaktivität aus.</span><span class="sxs-lookup"><span data-stu-id="fd7be-114">Create a Data Quality Project for Cleansing, select the Suppliers knowledge base as the knowledge base to use to analyze and cleanse the source data in an Excel file, and select the Cleansing activity.</span></span>  
  
2.  <span data-ttu-id="fd7be-115">Ordnen Sie die Excel-Spalten, die Sie bereinigen möchten, entsprechenden DQS-Domänen/Verbunddomänen in der Wissensdatenbank zu.</span><span class="sxs-lookup"><span data-stu-id="fd7be-115">Map the Excel columns that you want to cleanse to appropriate DQS domains/composite domains in the knowledge base.</span></span>  
  
3.  <span data-ttu-id="fd7be-116">Führen Sie die computergestützte Bereinigungsaktivität aus.</span><span class="sxs-lookup"><span data-stu-id="fd7be-116">Run the computer-assisted cleansing activity.</span></span> <span data-ttu-id="fd7be-117">Der computergestützte Prozess zeigt Informationen zur Datenqualität im Data Quality-Client an, mit dem Sie die Daten interaktiv bereinigen können.</span><span class="sxs-lookup"><span data-stu-id="fd7be-117">The computer-assisted process displays data quality information in the Data Quality Client that you can use to cleanse the data interactively.</span></span>  
  
4.  <span data-ttu-id="fd7be-118">Zeigen Sie die Ergebnisse der Bereinigungsaktivität an, und verwalten Sie sie.</span><span class="sxs-lookup"><span data-stu-id="fd7be-118">View and manage the results of the cleansing activity.</span></span> <span data-ttu-id="fd7be-119">Sie können die Werte überprüfen, die vom computergestützten Prozess als richtig, falsch aber korrigiert, falsch mit einem Änderungsvorschlag oder ungültig bewertet werden.</span><span class="sxs-lookup"><span data-stu-id="fd7be-119">You can review the values that the computer-assisted process finds to be correct, incorrect but corrected, incorrect with a suggested change, or invalid.</span></span> <span data-ttu-id="fd7be-120">Sie können die Änderungen interaktiv genehmigen oder ablehnen und dabei den Vorschlag des computergestützten Prozesses im Feld "Korrigieren in" korrigieren oder überschreiben.</span><span class="sxs-lookup"><span data-stu-id="fd7be-120">You can interactively approve or reject changes, correcting or overriding the suggestion from the computer-assisted process by using the Correct To field.</span></span>  
  
5.  <span data-ttu-id="fd7be-121">Exportieren Sie die Ergebnisse des Bereinigungsprozesses in eine Excel-Datei.</span><span class="sxs-lookup"><span data-stu-id="fd7be-121">Export the results from the cleansing process to an Excel file.</span></span>  
  
6.  <span data-ttu-id="fd7be-122">Importieren Sie die Werte aus dem Bereinigungs Projekt in Domänen, um das Wissen in der Wissensdatenbank durch neue Regeln, Werte, Korrekturen usw. zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="fd7be-122">Import the values from the cleansing project into domains to augment the knowledge in the knowledge base with new rules, values, corrections etc...</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="fd7be-123">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="fd7be-123">Next Step</span></span>  
 [<span data-ttu-id="fd7be-124">Aufgabe 1: Erstellen eines Data Quality-Projekts</span><span class="sxs-lookup"><span data-stu-id="fd7be-124">Task 1: Creating a Data Quality Project</span></span>](../../2014/tutorials/task-1-creating-a-data-quality-project.md)  
  
  
