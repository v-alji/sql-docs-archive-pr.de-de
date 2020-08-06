---
title: Überprüfen replizierter Tabellen auf Unterschiede (Replikationsprogrammierung) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- tablediff utility
- comparing replicated tables
ms.assetid: cd253a17-0c85-42b4-912c-690169ebe799
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0d804c7d4ac9cc54fa144b7054c6032663b76c0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725582"
---
# <a name="compare-replicated-tables-for-differences-replication-programming"></a><span data-ttu-id="9af1d-102">Überprüfen replizierter Tabellen auf Unterschiede (Replikationsprogrammierung)</span><span class="sxs-lookup"><span data-stu-id="9af1d-102">Compare Replicated Tables for Differences (Replication Programming)</span></span>
  <span data-ttu-id="9af1d-103">Mithilfe der Artikelüberprüfung wird ermittelt, ob veröffentlichte Daten für Tabellenartikel auf dem Verleger und dem Verteiler identisch sind. Unterschiede können auf Nichtkonvergenz hinweisen.</span><span class="sxs-lookup"><span data-stu-id="9af1d-103">Article validation is used to determine if published data for table articles at the Publisher and Subscriber are not identical, which can indicate non-convergence.</span></span> <span data-ttu-id="9af1d-104">Weitere Informationen finden Sie unter [Überprüfen von replizierten Daten](../validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="9af1d-104">For more information, see [Validate Replicated Data](../validate-data-at-the-subscriber.md).</span></span> <span data-ttu-id="9af1d-105">Die Überprüfung gibt jedoch lediglich Auskunft darüber, ob die Daten identisch sind oder nicht. Details zu Unterschieden zwischen der Quell- und der Zieltabelle werden nicht zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9af1d-105">However, validation only returns pass or fail information and does not provide any information about what is different between the source and destination tables.</span></span> <span data-ttu-id="9af1d-106">Das Befehlszeilenhilfsprogramm **tablediff** gibt ausführliche Informationen zu den Unterschieden zwischen zwei Tabellen zurück und kann sogar ein [!INCLUDE[tsql](../../../includes/tsql-md.md)] -Skript generieren, mit dem ein Abonnement mit den Daten auf dem Verleger in Übereinstimmung gebracht werden kann.</span><span class="sxs-lookup"><span data-stu-id="9af1d-106">The **tablediff** command prompt utility returns detailed difference information between two tables and can even generate a [!INCLUDE[tsql](../../../includes/tsql-md.md)] script to bring a subscription into convergence with data at the Publisher.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9af1d-107">Das Hilfsprogramm **tablediff** wird nur für [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Server unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9af1d-107">The **tablediff** utility is only supported for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] servers.</span></span>  
  
### <a name="to-compare-replicated-tables-for-differences-using-tablediff"></a><span data-ttu-id="9af1d-108">So überprüfen Sie replizierte Tabellen mithilfe von "tablediff" auf Unterschiede</span><span class="sxs-lookup"><span data-stu-id="9af1d-108">To compare replicated tables for differences using tablediff</span></span>  
  
1.  <span data-ttu-id="9af1d-109">Führen Sie an der Eingabeaufforderung auf einem beliebigen Server in einer Replikationstopologie [tablediff Utility](../../../tools/tablediff-utility.md)aus.</span><span class="sxs-lookup"><span data-stu-id="9af1d-109">From the command prompt at any server in a replication topology, run the [tablediff Utility](../../../tools/tablediff-utility.md).</span></span> <span data-ttu-id="9af1d-110">Geben Sie die folgenden Parameter an:</span><span class="sxs-lookup"><span data-stu-id="9af1d-110">Specify the following parameters:</span></span>  
  
    -   <span data-ttu-id="9af1d-111">**-sourceserver** - Name des Servers, auf dem die Daten korrekt sind (in der Regel der Verleger).</span><span class="sxs-lookup"><span data-stu-id="9af1d-111">**-sourceserver** - name of the server on which the data is known to be correct, usually the Publisher.</span></span>  
  
    -   <span data-ttu-id="9af1d-112">**-sourcedatabase** - Name der Datenbank, die die richtigen Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="9af1d-112">**-sourcedatabase** - name of the database containing the correct data.</span></span>  
  
    -   <span data-ttu-id="9af1d-113">**-sourcetable** - Name der Quelltabelle für den Artikel, der verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="9af1d-113">**-sourcetable** - name of the source table for the article being compared.</span></span>  
  
    -   <span data-ttu-id="9af1d-114">(Optional) **-sourceschema** - Schemabesitzer der Quelltabelle, wenn nicht das Standardschema verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9af1d-114">(Optional) **-sourceschema** - schema owner of the source table, if not the default schema.</span></span>  
  
    -   <span data-ttu-id="9af1d-115">(Optional) **-sourceuser** und **-sourcepassword** bei Verwendung der SQL Server-Authentifizierung zum Herstellen der Verbindung mit dem Verleger.</span><span class="sxs-lookup"><span data-stu-id="9af1d-115">(Optional) **-sourceuser** and **-sourcepassword** when using SQL Server Authentication to connect to the Publisher.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="9af1d-116">Verwenden Sie nach Möglichkeit die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9af1d-116">When possible, use Windows Authentication.</span></span> <span data-ttu-id="9af1d-117">Wenn Sie die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Authentifizierung verwenden müssen, sollten die Benutzer zur Laufzeit zur Eingabe der Sicherheitsanmeldeinformationen aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="9af1d-117">If you must use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="9af1d-118">Wenn Anmeldeinformationen in einer Skriptdatei gespeichert werden müssen, muss die Datei an einem sicheren Ort gespeichert werden, um unberechtigten Zugriff zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="9af1d-118">If you must store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
    -   <span data-ttu-id="9af1d-119">**-destinationserver** - Name des Servers, auf dem die Daten verglichen werden (in der Regel ein Abonnent).</span><span class="sxs-lookup"><span data-stu-id="9af1d-119">**-destinationserver** - name of the server on which the data is being compared, usually a Subscriber.</span></span>  
  
    -   <span data-ttu-id="9af1d-120">**-destinationdatabase** - Name der Datenbank, die verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="9af1d-120">**-destinationdatabase** - name of a the database being compared.</span></span>  
  
    -   <span data-ttu-id="9af1d-121">**-destinationtable** - Name der Tabelle, die verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="9af1d-121">**-destinationtable** - name of the table being compared.</span></span>  
  
    -   <span data-ttu-id="9af1d-122">(Optional) **-destinationschema** - Schemabesitzer der Zieltabelle, wenn nicht das Standardschema verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9af1d-122">(Optional) **-destinationschema** - schema owner of the destination table, if not the default schema.</span></span>  
  
    -   <span data-ttu-id="9af1d-123">(Optional) **-destinationuser** und **-destinationpassword** bei Verwendung der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Authentifizierung zum Herstellen der Verbindung mit dem Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="9af1d-123">(Optional) **-destinationuser** and **-destinationpassword** when using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication to connect to the Subscriber.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="9af1d-124">Verwenden Sie nach Möglichkeit die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9af1d-124">When possible, use Windows Authentication.</span></span> <span data-ttu-id="9af1d-125">Wenn Sie die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Authentifizierung verwenden müssen, sollten die Benutzer zur Laufzeit zur Eingabe der Sicherheitsanmeldeinformationen aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="9af1d-125">If you must use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="9af1d-126">Wenn Anmeldeinformationen in einer Skriptdatei gespeichert werden müssen, muss die Datei an einem sicheren Ort gespeichert werden, um unberechtigten Zugriff zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="9af1d-126">If you must store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
    -   <span data-ttu-id="9af1d-127">(Optional) Verwenden Sie **-c** , um einen Vergleich auf Spaltenebene auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9af1d-127">(Optional) Use **-c** to do a column-level comparison.</span></span>  
  
    -   <span data-ttu-id="9af1d-128">(Optional) Verwenden Sie **-q** , um einen schnellen Vergleich auszuführen, bei dem lediglich die Zeilenanzahl und das Schema berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="9af1d-128">(Optional) Use **-q** to do a fast, row count- and schema-only comparison.</span></span>  
  
    -   <span data-ttu-id="9af1d-129">(Optional) Geben Sie einen Dateinamen und einen Pfad für **-o** an, damit die Ergebnisse in eine Datei ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9af1d-129">(Optional) Specify a file name and path for **-o** to output the results to a file.</span></span>  
  
    -   <span data-ttu-id="9af1d-130">(Optional) Geben Sie eine Tabelle in der Abonnementdatenbank an, in die die Ergebnisse für **-et**eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="9af1d-130">(Optional) Specify a table in the subscription database into which to insert results for **-et**.</span></span> <span data-ttu-id="9af1d-131">Wenn die Tabelle bereits vorhanden ist, geben Sie **-dt** an, um die Tabelle zunächst zu löschen.</span><span class="sxs-lookup"><span data-stu-id="9af1d-131">If the table already exists, specify **-dt** to first drop the table.</span></span>  
  
    -   <span data-ttu-id="9af1d-132">(Optional) Verwenden Sie **-f** , um eine [!INCLUDE[tsql](../../../includes/tsql-md.md)] -Datei zu generieren und die Daten auf dem Abonnenten zu korrigieren, sodass sie mit den Daten auf dem Verleger übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="9af1d-132">(Optional) Use **-f** to generate a [!INCLUDE[tsql](../../../includes/tsql-md.md)] file to fix data at the Subscriber so that it matches data at the Publisher.</span></span> <span data-ttu-id="9af1d-133">Verwenden Sie **-df** , um die Anzahl von [!INCLUDE[tsql](../../../includes/tsql-md.md)] -Anweisungen in jeder Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9af1d-133">Use **-df** to specify the number of [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements in each file.</span></span>  
  
    -   <span data-ttu-id="9af1d-134">(Optional) Verwenden Sie **-rc** bzw. **-ri** , um anzugeben, wie oft ein Vorgang wiederholt wird, bzw. um das Wiederholungsintervall anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9af1d-134">(Optional) Use **-rc** and **-ri** to specify the number of times to retry an operation and the retry interval.</span></span>  
  
    -   <span data-ttu-id="9af1d-135">(Optional) Verwenden Sie **-strict** , um einen strikten Schemavergleich zwischen Quell- und Zieltabelle zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="9af1d-135">(Optional) Use **-strict** to enforce strict schema comparison between source and destination tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9af1d-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9af1d-136">See Also</span></span>  
 [<span data-ttu-id="9af1d-137">Überprüfen der Daten am Abonnenten</span><span class="sxs-lookup"><span data-stu-id="9af1d-137">Validate Data at the Subscriber</span></span>](../validate-data-at-the-subscriber.md)  
  
  
