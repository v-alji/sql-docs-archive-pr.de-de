---
title: Starten der dta-Eingabeaufforderung und Optimieren einer Arbeitsauslastung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], tutorials
ms.assetid: f34a5acf-1f3b-4484-a770-6470cb925ab0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4b2b1755a2ce8299556ab7d0ae14c89d3b2c8554
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695006"
---
# <a name="starting-the-dta-command-prompt-utility-and-tuning-a-workload"></a><span data-ttu-id="3bdec-102">Starten des Befehlzeilenprogramms dta und Optimieren einer Arbeitsauslastung</span><span class="sxs-lookup"><span data-stu-id="3bdec-102">Starting the dta Command Prompt Utility and Tuning a Workload</span></span>
  <span data-ttu-id="3bdec-103"> In dieser Aufgabe erfahren Sie, wie Sie das Hilfsprogramm **dta** starten, die dazugehörige Hilfe anzeigen und es anschließend zur Optimierung einer Arbeitsauslastung über die Eingabeaufforderung verwenden.</span><span class="sxs-lookup"><span data-stu-id="3bdec-103">This task guides you through starting the **dta** utility, viewing its Help, and then using it to tune a workload from the command prompt.</span></span> <span data-ttu-id="3bdec-104">Dabei wird die Arbeitsauslastung MyScript. SQL verwendet, die Sie für die Vorgehensweise beim [Optimieren einer Arbeitsauslastung](lesson-1-1-tuning-a-workload.md)Datenbankoptimierungsratgeber grafischen Benutzeroberfläche (GUI) erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="3bdec-104">It uses the workload, MyScript.sql, which you created for the Database Engine Tuning Advisor graphical user interface (GUI) practice [Tuning a Workload](lesson-1-1-tuning-a-workload.md).</span></span>  
  
 <span data-ttu-id="3bdec-105">Im Lernprogramm wird die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Beispieldatenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="3bdec-105">The tutorial uses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="3bdec-106">Aus Sicherheitsgründen werden die Beispieldatenbanken nicht standardmäßig installiert.</span><span class="sxs-lookup"><span data-stu-id="3bdec-106">For security reasons, the sample databases are not installed by default.</span></span> <span data-ttu-id="3bdec-107">Informationen zur Installation der Beispieldatenbanken finden Sie unter [Installieren der SQL Server-Beispiele und -Beispieldatenbanken](http://sqlserversamples.codeplex.com).</span><span class="sxs-lookup"><span data-stu-id="3bdec-107">To install the sample databases, see [Installing SQL Server Samples and Sample Databases](http://sqlserversamples.codeplex.com).</span></span>  
  
 <span data-ttu-id="3bdec-108">Im Folgenden werden folgende Schritte erläutert: Öffnen einer Eingabeaufforderung, Starten des Befehlszeilen-Hilfsprogramms **dta** , Anzeigen der Syntaxhilfe und Optimieren der einfachen Arbeitsauslastung MyScript.sql, die Sie in [Optimieren einer Arbeitsauslastung](lesson-1-1-tuning-a-workload.md)angelegt haben.</span><span class="sxs-lookup"><span data-stu-id="3bdec-108">The following tasks guide you through opening a command prompt, starting the **dta** command prompt utility, viewing its syntax Help, and tuning a simple workload, MyScript.sql, which you created in [Tuning a Workload](lesson-1-1-tuning-a-workload.md).</span></span>  
  
### <a name="to-start-the-dta-command-prompt-utility-and-view-help"></a><span data-ttu-id="3bdec-109">So starten Sie das Befehlszeilen-Hilfsprogramms dta und zeigen die Hilfe an</span><span class="sxs-lookup"><span data-stu-id="3bdec-109">To start the dta command prompt utility and view Help</span></span>  
  
1.  <span data-ttu-id="3bdec-110">Zeigen Sie im **Startmenü** auf **Alle Programme**, zeigen Sie auf **Zubehör**, und klicken Sie anschließend auf **Eingabeaufforderung**.</span><span class="sxs-lookup"><span data-stu-id="3bdec-110">On the **Start** menu, point to **All Programs**, point to **Accessories**, and then click **Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="3bdec-111">Geben Sie an der Eingabeaufforderung die folgende ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="3bdec-111">At the command prompt, type the following, and press ENTER:</span></span>  
  
    ```  
    dta -? | more  
    ```  
  
     <span data-ttu-id="3bdec-112">Der folgende Teil des Befehls ist optional: `| more` .</span><span class="sxs-lookup"><span data-stu-id="3bdec-112">The `| more` part of this command is optional.</span></span> <span data-ttu-id="3bdec-113">Sie können mit seiner Hilfe jedoch die Syntaxhilfe des Hilfsprogramms besser durchblättern.</span><span class="sxs-lookup"><span data-stu-id="3bdec-113">However, using it enables you to page through the syntax help for the utility.</span></span> <span data-ttu-id="3bdec-114">Drücken Sie die EINGABETASTE, um im Hilfetext jeweils eine weitere Zeile anzuzeigen, oder drücken Sie die LEERTASTE, um auf die nächste Seite zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="3bdec-114">Press ENTER to advance the help text by the line, or press the SPACEBAR to advance it by the page.</span></span>  
  
### <a name="to-tune-a-simple-workload-by-using-the-dta-command-prompt-utility"></a><span data-ttu-id="3bdec-115">So optimieren Sie eine einfache Arbeitsauslastung mithilfe des Befehlszeilen-Hilfsprogramms dta</span><span class="sxs-lookup"><span data-stu-id="3bdec-115">To tune a simple workload by using the dta command prompt utility</span></span>  
  
1.  <span data-ttu-id="3bdec-116">Navigieren Sie an der Eingabeaufforderung zu dem Verzeichnis, in dem Sie die Datei MyScript.sql gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="3bdec-116">At the command prompt, navigate to the directory where you have stored the MyScript.sql file.</span></span>  
  
2.  <span data-ttu-id="3bdec-117">Geben Sie an der Eingabeaufforderung Folgendes ein. Drücken Sie danach die EINGABETASTE, um den Befehl auszuführen und die Optimierungssitzung zu starten (beachten Sie, dass das Hilfsprogramm beim Analysieren von Befehlen die Groß- und Kleinschreibung berücksichtigt):</span><span class="sxs-lookup"><span data-stu-id="3bdec-117">At the command prompt, type the following, and press ENTER to run the command and start the tuning session (note that the utility is case-sensitive when it parses commands):</span></span>  
  
    ```  
    dta -S YourServerName\YourSQLServerInstanceName -E -D AdventureWorks2012 -if MyScript.sql -s MySession2 -of MySession2OutputScript.sql -ox MySession2Output.xml -fa IDX_IV -fp NONE -fk NONE  
    ```  
  
     <span data-ttu-id="3bdec-118">Dabei gibt `-S` den Namen Ihres Servers und die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz an, in der die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank installiert ist.</span><span class="sxs-lookup"><span data-stu-id="3bdec-118">where `-S` specifies the name of your server and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance where the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database is installed.</span></span> <span data-ttu-id="3bdec-119">Die Einstellung `-E` gibt an, dass Sie eine vertrauenswürdige Verbindungsart mit der Instanz verwenden möchten. Dies ist der geeignete Verbindungstyp, wenn Sie eine Verbindung mit einem Windows-Domänenkonto herstellen.</span><span class="sxs-lookup"><span data-stu-id="3bdec-119">The setting `-E` specifies that you want to use a trusted connection to the instance, which is appropriate if you are connecting with a Windows domain account.</span></span> <span data-ttu-id="3bdec-120">Die Einstellung `-D` gibt die Datenbank an, die Sie optimieren möchten, `-if` gibt die Arbeitsauslastungsdatei an, `-s` gibt den Sitzungsnamen an, `-of` gibt die Datei an, in die das Tool das Skript mit den [!INCLUDE[tsql](../../includes/tsql-md.md)] -Empfehlungen schreiben soll, und `-ox` gibt die Datei an, in die das Tool die Empfehlungen im XML-Format schreiben soll.</span><span class="sxs-lookup"><span data-stu-id="3bdec-120">The setting `-D` specifies the database that you want to tune, `-if` specifies the workload file, `-s` specifies the session name, `-of` specifies the file to which you want the tool to write the [!INCLUDE[tsql](../../includes/tsql-md.md)] recommendations script, and `-ox` specifies the file to which you want the tool to write the recommendations in XML format.</span></span> <span data-ttu-id="3bdec-121">Die letzten drei Schalter legen folgende Optimierungsoptionen fest: `-fa IDX_IV` gibt an, dass der Datenbankoptimierungsratgeber nur das Hinzufügen von Indizes (gruppiert und nicht gruppiert) und von indizierten Sichten berücksichtigen soll; `-fp NONE` gibt an, dass bei der Analyse keine Partitionsstrategie berücksichtigt werden soll; und `-fk NONE` gibt an, dass in der Datenbank vorhandene physische Entwurfsstrukturen nicht beibehalten werden müssen, wenn der Datenbankoptimierungsratgeber seine Empfehlungen abgibt.</span><span class="sxs-lookup"><span data-stu-id="3bdec-121">The last three switches specify tuning options as follows: `-fa IDX_IV` specifies that Database Engine Tuning Advisor should only consider adding indexes (both clustered and nonclustered) and indexed views; `-fp NONE` specifies that no partition strategy should be considered during analysis; and `-fk NONE` specifies that no existing physical design structures in the database must be kept when Database Engine Tuning Advisor makes its recommendations.</span></span>  
  
3.  <span data-ttu-id="3bdec-122">Wenn der Datenbankoptimierungsratgeber mit dem Optimieren der Arbeitsauslastung fertig ist, zeigt er eine Meldung an, die besagt, dass die Optimierungssitzung erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="3bdec-122">After Database Engine Tuning Advisor finishes tuning the workload, it displays a message indicating that your tuning session completed successfully.</span></span> <span data-ttu-id="3bdec-123">Sie können die Optimierungsergebnisse anzeigen. Verwenden Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] zum Öffnen der Dateien MySession2OutputScript.sql und MySession2Output.xml.</span><span class="sxs-lookup"><span data-stu-id="3bdec-123">You can view the tuning results, by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to open the files MySession2OutputScript.sql and MySession2Output.xml.</span></span> <span data-ttu-id="3bdec-124">Alternativ dazu können Sie auch die Optimierungssitzung MySession2 in der grafischen Benutzeroberfläche des Datenbankoptimierungsratgebers öffnen und die Empfehlungen und Berichte so anzeigen, wie in den Abschnitten [Anzeigen von Empfehlungen für die Optimierung](lesson-1-2-viewing-tuning-recommendations.md) und [Anzeigen von Optimierungsberichten](lesson-1-3-viewing-tuning-reports.md)erläutert.</span><span class="sxs-lookup"><span data-stu-id="3bdec-124">Alternatively, you can also open the MySession2 tuning session in the Database Engine Tuning Advisor GUI and view its recommendations and reports in the same way that you did in [Viewing Tuning Recommendations](lesson-1-2-viewing-tuning-recommendations.md) and [Viewing Tuning Reports](lesson-1-3-viewing-tuning-reports.md).</span></span>  
  
## <a name="summary"></a><span data-ttu-id="3bdec-125">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="3bdec-125">Summary</span></span>  
 <span data-ttu-id="3bdec-126">Sie haben damit eine einfache Arbeitsauslastung von der Eingabeaufforderung aus mithilfe des Hilfsprogramms **dta** optimiert.</span><span class="sxs-lookup"><span data-stu-id="3bdec-126">You have completed tuning a simple workload from the command prompt by using the **dta** utility.</span></span> <span data-ttu-id="3bdec-127">Dieses Tool umfasst noch viele weitere Optimierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="3bdec-127">This tool provides many other tuning options.</span></span> <span data-ttu-id="3bdec-128">Weitere Informationen dazu finden Sie in der Hilfe des Tools (**dta -?**) und im Referenzthema [dta (Hilfsprogramm)](dta-utility.md) .</span><span class="sxs-lookup"><span data-stu-id="3bdec-128">Refer to the tool Help (**dta -?**) and the reference topic [dta Utility](dta-utility.md) for more information.</span></span>  
  
## <a name="after-you-finish-this-tutorial"></a><span data-ttu-id="3bdec-129">Weiterführende Informationen nach Abschluss dieses Lernprogramms</span><span class="sxs-lookup"><span data-stu-id="3bdec-129">After You Finish This Tutorial</span></span>  
 <span data-ttu-id="3bdec-130">Wenn Sie die Lektionen in diesem Lernprogramm durchgearbeitet haben, finden Sie unter folgenden Themen weitere Informationen zum Datenbankoptimierungsratgeber:</span><span class="sxs-lookup"><span data-stu-id="3bdec-130">After you finish the lessons in this tutorial, refer to the following topics for more information about Database Engine Tuning Advisor:</span></span>  
  
-   <span data-ttu-id="3bdec-131">[Database Engine Tuning Advisor](../../relational-databases/performance/database-engine-tuning-advisor.md) enthält Beschreibungen zum Ausführen von Tasks mit diesem Tool.</span><span class="sxs-lookup"><span data-stu-id="3bdec-131">[Database Engine Tuning Advisor](../../relational-databases/performance/database-engine-tuning-advisor.md) for descriptions of how to perform tasks with this tool.</span></span>  
  
-   <span data-ttu-id="3bdec-132">[dta Utility](dta-utility.md) enthält Referenzmaterial zum Eingabeaufforderungs-Hilfsprogramm und der optionalen XML-Datei, mit der Sie die Ausführung des Hilfsprogramms steuern können.</span><span class="sxs-lookup"><span data-stu-id="3bdec-132">[dta Utility](dta-utility.md) for reference material on the command prompt utility and the optional XML file you can use to control the operation of the utility.</span></span>  
  
 <span data-ttu-id="3bdec-133">Gehen Sie auf die Seite [Tutorial: Datenbankoptimierungsratgeber](tutorial-database-engine-tuning-advisor.md), um zum Anfang des Tutorials zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="3bdec-133">To return to the start of the tutorial, see [Tutorial: Database Engine Tuning Advisor](tutorial-database-engine-tuning-advisor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bdec-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3bdec-134">See Also</span></span>  
 [<span data-ttu-id="3bdec-135">Lernprogramme zur Datenbank-Engine</span><span class="sxs-lookup"><span data-stu-id="3bdec-135">Database Engine Tutorials</span></span>](../../relational-databases/database-engine-tutorials.md)  
  
  