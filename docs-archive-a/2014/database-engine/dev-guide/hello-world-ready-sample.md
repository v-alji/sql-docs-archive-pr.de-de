---
title: Hallo Welt Ready-Beispiel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
ms.assetid: 1cb94266-f702-4a57-a1ae-689a89c98757
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7cc3088af258962a4cec615214147d1f4f09c431
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726190"
---
# <a name="hello-world-ready-sample"></a><span data-ttu-id="76f49-102">Beispiel für "Hello World Ready"</span><span class="sxs-lookup"><span data-stu-id="76f49-102">Hello World Ready Sample</span></span>
  <span data-ttu-id="76f49-103">Das Hello World Ready-Beispiel veranschaulicht die grundlegenden Vorgänge, die beim Erstellen, Bereitstellen und Testen einer einfachen gespeicherten World-Ready-Prozedur auf der Basis einer CLR (Common Language Runtime)-Integration ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="76f49-103">The Hello World Ready sample demonstrates the basic operations that are involved in creating, deploying, and testing a simple world ready common language runtime (CLR) integration-based stored procedure.</span></span> <span data-ttu-id="76f49-104">Eine World-Ready-Komponente lässt sich problemlos in verschiedene Sprachen für unterschiedliche Märkte in aller Welt lokalisieren, ohne den Quellcode der Komponente zu ändern.</span><span class="sxs-lookup"><span data-stu-id="76f49-104">A world-ready component can be easily localized into different languages for different markets around the world without changing the component's source code.</span></span> <span data-ttu-id="76f49-105">Dieses Beispiel zeigt außerdem, wie Sie Daten über einen Ausgabeparameter und einen Datensatz, der dynamisch von der gespeicherten Prozedur erstellt und an den Client zurückgegeben wird, zurückgeben können. Das Beispiel ist fast identisch mit dem Hello World-Beispiel, die Anwendung ist jedoch einfacher und sicherer zu lokalisieren.</span><span class="sxs-lookup"><span data-stu-id="76f49-105">This sample also demonstrates how to return data through an output parameter and through a record, which is dynamically constructed by the stored procedure and returned to the client.This sample is almost identical to the Hello World Sample except that it is much easier and safer to localize this application.</span></span> <span data-ttu-id="76f49-106">Das Ändern von lokalisiertem Text erfordert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="76f49-106">To change localized text requires the following:</span></span>  
  
1.  <span data-ttu-id="76f49-107">Ändern einer XML-Datei (der.`resx`</span><span class="sxs-lookup"><span data-stu-id="76f49-107">Changing an XML file (the .`resx`</span></span> <span data-ttu-id="76f49-108">Datei) für die jeweilige Kultur im Ressourcenverzeichnis</span><span class="sxs-lookup"><span data-stu-id="76f49-108">file) for the particular culture in the resources directory</span></span>  
  
2.  <span data-ttu-id="76f49-109">Erstellen der Ressourcendatei der Kultur mithilfe von `resgen`</span><span class="sxs-lookup"><span data-stu-id="76f49-109">Building the culture's resources file by using `resgen`</span></span>  
  
3.  <span data-ttu-id="76f49-110">Erstellen der aktualisierten Satelliten-DLL für diese Kultur</span><span class="sxs-lookup"><span data-stu-id="76f49-110">Building the updated satellite DLL for that culture</span></span>  
  
4.  <span data-ttu-id="76f49-111">Löschen und Hinzufügen dieser Assembly in SQL Server</span><span class="sxs-lookup"><span data-stu-id="76f49-111">Dropping and adding that assembly in SQL Server</span></span>  
  
 <span data-ttu-id="76f49-112">Der Quellcode und die Assembly für die eigentliche gespeicherte CLR-Prozedur bleiben unverändert.</span><span class="sxs-lookup"><span data-stu-id="76f49-112">The source code and assembly for the CLR stored procedure itself does not change.</span></span> <span data-ttu-id="76f49-113">Ein `build.cmd`-Skript wird bereitgestellt, das veranschaulicht, wie die Ressourcenassemblys kompiliert und verknüpft werden. Obwohl der Quellcode der Anwendung einen Ressourcen-Manager auf der Basis der aktuell ausgeführten Assembly erstellt, müssen Sie die kulturneutralen Ressourcen nicht in die DLL einbetten, die die gespeicherte Prozedur enthält.</span><span class="sxs-lookup"><span data-stu-id="76f49-113">A `build.cmd` script is provided which demonstrates how to compile and link the resource assemblies.Although the source code for the application creates a resource manager based the currently executing assembly, you do not have to embed the culture neutral resources in the DLL that contains the stored procedure.</span></span> <span data-ttu-id="76f49-114">Das `System.Resources.NeutralResourcesLanguage attribute` lässt die kulturneutralen Ressourcen in einer Satelliten-DLL zu.</span><span class="sxs-lookup"><span data-stu-id="76f49-114">The `System.Resources.NeutralResourcesLanguage attribute` permits the culture-neutral resources to exist in a satellite DLL.</span></span> <span data-ttu-id="76f49-115">Es empfiehlt sich, für diesen Zweck eine separate DLL zu verwenden, damit die primäre DLL, in der sich die gespeicherte CLR-Prozedur befindet, nicht geändert werden muss, wenn lokalisierter Text hinzugefügt oder geändert werden muss.</span><span class="sxs-lookup"><span data-stu-id="76f49-115">It is much better to use a separate DLL for this purpose so that when localized text needs to be added or changed, the primary DLL that contains the CLR stored procedure does not have to be changed.</span></span> <span data-ttu-id="76f49-116">Dies erweist sich vor allem für benutzerdefinierte CLR-Typen als hilfreich, die möglicherweise Spalten und andere Abhängigkeiten beinhalten, die es schwierig machen, den Typ zu löschen und erneut hinzuzufügen. Normalerweise müssen die Satelliten-DLL-Versionen mit der Version der Hauptassembly übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="76f49-116">This is especially useful for CLR user-defined types that might have columns and other dependencies which would make it difficult to drop and re-add the type.Ordinarily, the satellite DLL versions must be identical to the main assembly version.</span></span> <span data-ttu-id="76f49-117">Sie können jedoch das `SatelliteContractVersion`-Attribut dazu verwenden, das Aktualisieren der Hauptassembly zuzulassen, ohne gleichzeitig die Satellitenassemblys zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="76f49-117">However, you can use the `SatelliteContractVersion` attribute to allow the main assembly to be updated without updating the satellite assemblies too.</span></span> <span data-ttu-id="76f49-118">Weitere Informationen finden Sie in der `ResourceManager`-Klasse in der Microsoft .NET-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="76f49-118">For more information, see the `ResourceManager` class in the Microsoft .NET documentation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="76f49-119">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="76f49-119">Prerequisites</span></span>  
 <span data-ttu-id="76f49-120">Dieses Beispiel kann nur mit SQL Server 2005 und höheren Versionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="76f49-120">This sample works only with SQL Server 2005 and later versions.</span></span>  
  
 <span data-ttu-id="76f49-121">Zum Erstellen und Ausführen dieses Projekts muss die folgende Software installiert sein:</span><span class="sxs-lookup"><span data-stu-id="76f49-121">To create and run this project the following the following software must be installed:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="76f49-122">oder [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="76f49-122">or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span></span> <span data-ttu-id="76f49-123">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express erhalten Sie kostenlos auf der [Website](https://www.microsoft.com/sql-server/sql-server-editions-express) mit der Dokumentation und den Beispielen für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="76f49-123">You can obtain [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express free of charge from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express Documentation and Samples [Web site](https://www.microsoft.com/sql-server/sql-server-editions-express)</span></span>  
  
-   <span data-ttu-id="76f49-124">Die AdventureWorks-Datenbank, die auf der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Developer-[Website](https://go.microsoft.com/fwlink/?linkid=62796) zur Verfügung gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="76f49-124">The AdventureWorks database that is available at the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Developer [Web site](https://go.microsoft.com/fwlink/?linkid=62796)</span></span>  
  
-   <span data-ttu-id="76f49-125">.NET Framework SDK 2.0 oder höher oder Microsoft Visual Studio 2005 oder höher.</span><span class="sxs-lookup"><span data-stu-id="76f49-125">.NET Framework SDK 2.0 or later or Microsoft Visual Studio 2005 or later.</span></span> <span data-ttu-id="76f49-126">Das .NET Framework SDK ist kostenlos erhältlich.</span><span class="sxs-lookup"><span data-stu-id="76f49-126">You can obtain .NET Framework SDK free of charge.</span></span>  
  
-   <span data-ttu-id="76f49-127">Außerdem müssen die folgenden Bedingungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="76f49-127">In addition, the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="76f49-128">In der von Ihnen verwendeten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz muss die CLR-Integration aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="76f49-128">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using must have CLR integration enabled.</span></span>  
  
-   <span data-ttu-id="76f49-129">Führen Sie zum Aktivieren der CLR-Integration die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="76f49-129">In order to enable CLR integration, perform the following steps:</span></span>  
  
    #### <a name="enabling-clr-integration"></a><span data-ttu-id="76f49-130">Aktivieren der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="76f49-130">Enabling CLR Integration</span></span>  
  
    -   <span data-ttu-id="76f49-131">Führen Sie die folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)]-Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="76f49-131">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] commands:</span></span>  
  
     `sp_configure 'clr enabled', 1`  
  
     `GO`  
  
     `RECONFIGURE`  
  
     `GO`  
  
    > [!NOTE]  
    >  <span data-ttu-id="76f49-132">Um CLR zu aktivieren, benötigen Sie die `ALTER SETTINGS`-Serverberechtigung, die Mitglieder der festen Serverrollen `sysadmin` und `serveradmin` implizit erhalten.</span><span class="sxs-lookup"><span data-stu-id="76f49-132">To enable CLR, you must have `ALTER SETTINGS` server level permission, which is implicitly held by members of the `sysadmin` and `serveradmin` fixed server roles.</span></span>  
  
-   <span data-ttu-id="76f49-133">Die AdventureWorks-Datenbank muss in der von Ihnen verwendeten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz installiert sein.</span><span class="sxs-lookup"><span data-stu-id="76f49-133">The AdventureWorks database must be installed on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using.</span></span>  
  
-   <span data-ttu-id="76f49-134">Wenn Sie keine Administratorrechte für die von Ihnen verwendete [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz besitzen, müssen Sie sich von einem Administrator die **CreateAssembly**-Berechtigung erteilen lassen, damit Sie die Installation ausführen können.</span><span class="sxs-lookup"><span data-stu-id="76f49-134">If you are not an administrator for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using, you must have an administrator grant you **CreateAssembly**  permission to complete the installation.</span></span>  
  
## <a name="building-the-sample"></a><span data-ttu-id="76f49-135">Erstellen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="76f49-135">Building the Sample</span></span>  
  
#### <a name="create-and-run-the-sample-by-using-the-following-instructions"></a><span data-ttu-id="76f49-136">Verwenden Sie die folgenden Anweisungen, um das Beispiel zu erstellen und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="76f49-136">Create and run the sample by using the following instructions:</span></span>  
  
1.  <span data-ttu-id="76f49-137">Wechseln Sie zu einer Visual Studio- oder .NET Framework-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="76f49-137">Open a Visual Studio or .NET Framework command prompt.</span></span>  
  
2.  <span data-ttu-id="76f49-138">Erstellen Sie ggf. ein Verzeichnis für das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="76f49-138">If necessary, create a directory for your sample.</span></span> <span data-ttu-id="76f49-139">Für dieses Beispiel wird C:\MySample verwendet.</span><span class="sxs-lookup"><span data-stu-id="76f49-139">For this example, we will use C:\MySample.</span></span>  
  
3.  <span data-ttu-id="76f49-140">Erstellen Sie in c:\MySample die Datei `HelloWorld.vb` (für das Visual Basic-Beispiel) oder `HelloWorld.cs` (für das C#-Beispiel), und kopieren Sie den entsprechenden Visual Basic- oder C#-Beispielcode (unten) in die Datei.</span><span class="sxs-lookup"><span data-stu-id="76f49-140">In c:\MySample, create `HelloWorld.vb` (for the Visual Basic sample) or `HelloWorld.cs` (for the C# sample) and copy the appropriate Visual Basic or C# sample code (below) into the file.</span></span>  
  
4.  <span data-ttu-id="76f49-141">Erstellen Sie in c:\mysample die Datei, `messages.resx` und kopieren Sie den Beispielcode in die Datei.</span><span class="sxs-lookup"><span data-stu-id="76f49-141">In c:\MySample, create the file `messages.resx` and copy the sample code into the file.</span></span>  
  
5.  <span data-ttu-id="76f49-142">Erstellen Sie in c:\mysample die Datei, `messages.de.resx` indem Sie die Datei `messages.resx` nach dem `messages.de.resx` Ändern der Zeile speichern.</span><span class="sxs-lookup"><span data-stu-id="76f49-142">In c:\MySample, create the file `messages.de.resx` by saving the file `messages.resx` as `messages.de.resx` after changing the line</span></span>  
  
    -   `<value xml:space="preserve">Hello, World!</value>`  
  
    -   <span data-ttu-id="76f49-143">wie folgt geändert haben:</span><span class="sxs-lookup"><span data-stu-id="76f49-143">To read</span></span>  
  
    -   `<value xml:space="preserve">Hallo Welt!</value>`  
  
6.  <span data-ttu-id="76f49-144">Erstellen Sie in c:\mysample die Datei, `messages.es.resx` indem Sie die Datei `messages.resx` nach dem `messages.es.resx` Ändern der Zeile speichern.</span><span class="sxs-lookup"><span data-stu-id="76f49-144">In c:\MySample, create the file `messages.es.resx` by saving the file `messages.resx` as `messages.es.resx` after changing the line</span></span>  
  
    -   `<value xml:space="preserve">Hello, World!</value>`  
  
    -   <span data-ttu-id="76f49-145">wie folgt geändert haben:</span><span class="sxs-lookup"><span data-stu-id="76f49-145">To read</span></span>  
  
    -   `<value xml:space="preserve">Hola a todos</value>`  
  
7.  <span data-ttu-id="76f49-146">Erstellen Sie in c:\mysample die Datei, `messages.fr.resx` indem Sie die Datei `messages.resx` nach dem `messages.fr.resx` Ändern der Zeile speichern.</span><span class="sxs-lookup"><span data-stu-id="76f49-146">In c:\MySample, create the file `messages.fr.resx` by saving the file `messages.resx` as `messages.fr.resx` after changing the line</span></span>  
  
    -   `<value xml:space="preserve">Hello, World!</value>`  
  
    -   <span data-ttu-id="76f49-147">wie folgt geändert haben:</span><span class="sxs-lookup"><span data-stu-id="76f49-147">To read</span></span>  
  
    -   `<value xml:space="preserve">BonjourÂ !</value>`  
  
8.  <span data-ttu-id="76f49-148">Erstellen Sie in c:\mysample die Datei, `messages.fr-FR.resx` indem Sie die Datei `messages.resx` nach dem `messages.fr-FR.resx` Ändern der Zeile speichern.</span><span class="sxs-lookup"><span data-stu-id="76f49-148">In c:\MySample, create the file `messages.fr-FR.resx` by saving the file `messages.resx` as `messages.fr-FR.resx` after changing the line</span></span>  
  
    -   `<value xml:space="preserve">Hello, World!</value>`  
  
    -   <span data-ttu-id="76f49-149">wie folgt geändert haben:</span><span class="sxs-lookup"><span data-stu-id="76f49-149">To read</span></span>  
  
    -   `<value xml:space="preserve">Bonjour de France!</value>`  
  
9. <span data-ttu-id="76f49-150">Erstellen Sie in c:\mysample die Datei, `messages.it.resx` indem Sie die Datei `messages.resx` nach dem `messages.it.resx` Ändern der Zeile speichern.</span><span class="sxs-lookup"><span data-stu-id="76f49-150">In c:\MySample, create the file `messages.it.resx` by saving the file `messages.resx` as `messages.it.resx` after changing the line</span></span>  
  
    -   `<value xml:space="preserve">Hello, World!</value>`  
  
    -   <span data-ttu-id="76f49-151">wie folgt geändert haben:</span><span class="sxs-lookup"><span data-stu-id="76f49-151">To read</span></span>  
  
    -   `<value xml:space="preserve">Buongiorno</value>`  
  
10. <span data-ttu-id="76f49-152">Erstellen Sie in c:\mysample die Datei, `messages.ja.resx` indem Sie die Datei `messages.resx` nach dem `messages.ja.resx` Ändern der Zeile speichern.</span><span class="sxs-lookup"><span data-stu-id="76f49-152">In c:\MySample, create the file `messages.ja.resx` by saving the file `messages.resx` as `messages.ja.resx` after changing the line</span></span>  
  
    -   `<value xml:space="preserve">Hello, World!</value>`  
  
    -   <span data-ttu-id="76f49-153">wie folgt geändert haben:</span><span class="sxs-lookup"><span data-stu-id="76f49-153">To read</span></span>  
  
    -   <span data-ttu-id="76f49-154">`<value xml:space="preserve">` `ã"ã‚"ã«ã¡ã¯</value>`</span><span class="sxs-lookup"><span data-stu-id="76f49-154">`<value xml:space="preserve">` `ã"ã‚"ã«ã¡ã¯</value>`</span></span>  
  
11. <span data-ttu-id="76f49-155">Erstellen Sie in c:\MySample die Datei `build.com`, und kopieren Sie den Beispielcode in die Datei.</span><span class="sxs-lookup"><span data-stu-id="76f49-155">In c:\MySample, create the file `build.com` and copy the sample code into the file</span></span>  
  
12. <span data-ttu-id="76f49-156">Erstellen Sie die Satellitenassemblys, indem Sie den Dateibuild an der Eingabeaufforderung ausführen.</span><span class="sxs-lookup"><span data-stu-id="76f49-156">Build the satellite assembles by executing the file build at the command prompt.</span></span>  
  
13. <span data-ttu-id="76f49-157">Kompilieren Sie den Beispielcode aus der Eingabeaufforderung, indem Sie eine der folgenden Anweisungen ausführen:</span><span class="sxs-lookup"><span data-stu-id="76f49-157">Compile the sample code from the command line prompt by executing the one of the following:</span></span>  
  
    -   `Vbc /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Xml.dll /out:HelloWorldReady.dll /target:library HelloWorld.vb`  
  
    -   `Csc /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.XML.dll /out:HelloWorldReady.dll /target:library Hello.csCopy the tsql installation code into a file and save it as Install.sql in the sample directory.`  
  
14. <span data-ttu-id="76f49-158">Wenn das Beispiel in einem anderen Verzeichnis als `C:\MySample\` installiert ist, bearbeiten Sie die Datei `Install.sql`wie gezeigt, damit sie auf diesen Speicherort verweist.</span><span class="sxs-lookup"><span data-stu-id="76f49-158">If the sample is installed in a directory other then `C:\MySample\`, edit the file `Install.sql` as indicated to point to that location.</span></span>  
  
15. <span data-ttu-id="76f49-159">Stellen Sie die Assembly und die gespeicherte Prozedur bereit, indem Sie die folgende Anweisung ausführen:</span><span class="sxs-lookup"><span data-stu-id="76f49-159">Deploy the assembly and stored procedure by executing</span></span>  
  
    -   `sqlcmd -E -I -i install.sql`  
  
16. <span data-ttu-id="76f49-160">Kopieren [!INCLUDE[tsql](../../includes/tsql-md.md)] Sie das Test Befehls Skript in eine Datei, und speichern Sie Sie als `test.sql` im Beispiel Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="76f49-160">Copy [!INCLUDE[tsql](../../includes/tsql-md.md)] test command script into a file and save it as `test.sql` in the sample directory.</span></span>  
  
17. <span data-ttu-id="76f49-161">Führen Sie das Testskript mit dem folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="76f49-161">Execute the test script with the following command</span></span>  
  
    -   `sqlcmd -E -I -i test.sql`  
  
18. <span data-ttu-id="76f49-162">Kopieren Sie das [!INCLUDE[tsql](../../includes/tsql-md.md)]-Bereinigungsskript in eine Datei, und speichern Sie diese als `cleanup.sql` im Beispielverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="76f49-162">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] cleanup script into a file and save it as `cleanup.sql` in the sample directory.</span></span>  
  
19. <span data-ttu-id="76f49-163">Führen Sie das Skript mit dem folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="76f49-163">Execute the script with the  following command</span></span>  
  
    -   `sqlcmd -E -I -i cleanup.sql`  
  
## <a name="sample-code"></a><span data-ttu-id="76f49-164">Beispielcode</span><span class="sxs-lookup"><span data-stu-id="76f49-164">Sample Code</span></span>  
 <span data-ttu-id="76f49-165">Die Codelistings für dieses Beispiel lauten wie folgt.</span><span class="sxs-lookup"><span data-stu-id="76f49-165">The following are the code listings for this sample.</span></span>  
  
 <span data-ttu-id="76f49-166">C#</span><span class="sxs-lookup"><span data-stu-id="76f49-166">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.Sql;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
using System.Globalization;  
using System.Threading;  
using System.Resources;  
using System.Reflection;  
using System.Runtime.CompilerServices;  
  
[assembly: System.Resources.NeutralResourcesLanguage("", System.Resources.UltimateResourceFallbackLocation.Satellite)]  
[assembly: System.Security.Permissions.SecurityPermissionAttribute(System.Security.Permissions.SecurityAction.RequestMinimum)]  
[assembly: System.Runtime.ConstrainedExecution.ReliabilityContract(System.Runtime.ConstrainedExecution.Consistency.MayCorruptInstance, System.Runtime.ConstrainedExecution.Cer.None)]  
  
    public sealed partial class StoredProcedures  
    {  
        private StoredProcedures()  
        {  
        }  
  
        [System.Diagnostics.CodeAnalysis.SuppressMessage("Microsoft.Design", "CA1021:AvoidOutParameters"), Microsoft.SqlServer.Server.SqlProcedure]  
        public static void HelloWorldReady(string culture, out string greeting)  
        {  
ResourceManager rm   
= new ResourceManager("Messages",   
Assembly.GetExecutingAssembly());  
  
string message = rm.GetString("HelloWorld", CultureInfo.GetCultureInfo(culture));  
  
            Microsoft.SqlServer.Server.SqlMetaData columnInfo  
                = new Microsoft.SqlServer.Server.SqlMetaData("Column1", SqlDbType.NVarChar, 24);  
            SqlDataRecord greetingRecord  
                = new SqlDataRecord(new Microsoft.SqlServer.Server.SqlMetaData[] { columnInfo });  
            greetingRecord.SetString(0, message);  
            SqlContext.Pipe.Send(greetingRecord);  
            greeting = message;  
        }  
    }  
  
```  
  
 <span data-ttu-id="76f49-167">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="76f49-167">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Globalization  
Imports System.Resources  
Imports System.Reflection  
Imports System.Runtime.InteropServices  
<Assembly: AssemblyVersion("1.0.*")>   
<Assembly: System.Runtime.InteropServices.ComVisible(False)>   
<Assembly: System.CLSCompliant(True)>   
<Assembly: System.Resources.NeutralResourcesLanguage("", System.Resources.UltimateResourceFallbackLocation.Satellite)>   
<Assembly: System.Security.Permissions.SecurityPermissionAttribute(System.Security.Permissions.SecurityAction.RequestMinimum)>   
<Assembly: System.Runtime.ConstrainedExecution.ReliabilityContract(System.Runtime.ConstrainedExecution.Consistency.WillNotCorruptState, Runtime.ConstrainedExecution.Cer.None)>   
  
Partial Public NotInheritable Class StoredProcedures  
    Private Sub New()  
    End Sub  
    <Microsoft.SqlServer.Server.SqlProcedure()> _  
    Public Shared Sub HelloWorldReady(ByVal culture As String, ByRef greeting As String)  
        Dim rm As New ResourceManager("Messages", Assembly.GetExecutingAssembly())  
        Dim message As String = rm.GetString("HelloWorld", CultureInfo.GetCultureInfo(culture))  
        Dim columnInfo As New Microsoft.SqlServer.Server.SqlMetaData("Column1", _  
            SqlDbType.NVarChar, 24)  
        Dim greetingRecord As New SqlDataRecord(New  _  
            Microsoft.SqlServer.Server.SqlMetaData() {columnInfo})  
        greetingRecord.SetString(0, message)  
        SqlContext.Pipe.Send(greetingRecord)  
        greeting = message  
    End Sub  
End Class  
  
```  
  
 <span data-ttu-id="76f49-168">Dies ist die Datei `build.com`, mit der die Satellitenassemblys erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="76f49-168">This is `build.com`, which builds the satellite assemblies.</span></span>  
  
```  
resgen Messages.resx  
resgen Messages.de.resx  
resgen Messages.es.resx  
resgen Messages.fr.resx  
resgen Messages.fr-Fr.resx  
resgen Messages.it.resx  
resgen Messages.ja.resx  
if not exist de/ mkdir de  
if not exist es/ mkdir es  
if not exist fr/ mkdir fr  
if not exist fr-FR/ mkdir fr-FR  
if not exist it/ mkdir it  
if not exist ja/ mkdir ja  
al /t:lib /culture:de /embed:Messages.de.resources /out:de\HelloWorldReady.resources.dll  
al /t:lib /culture:es /embed:Messages.es.resources /out:es\HelloWorldReady.resources.dll  
al /t:lib /culture:fr /embed:Messages.fr.resources /out:fr\HelloWorldReady.resources.dll  
al /t:lib /culture:fr-FR /embed:Messages.fr-FR.resources /out:fr-FR\HelloWorldReady.resources.dll  
al /t:lib /culture:it /embed:Messages.it.resources /out:it\HelloWorldReady.resources.dll  
al /t:lib /culture:ja /embed:Messages.ja.resources /out:ja\HelloWorldReady.resources.dll  
al /t:lib /culture:"" /embed:Messages.resources /out:HelloWorldReady.resources.dll  
```  
  
 <span data-ttu-id="76f49-169">Dies ist das [!INCLUDE[tsql](../../includes/tsql-md.md)]-Installationsskript (`Install.sql`), mit dem die Assemblys bereitgestellt werden und die gespeicherte Prozedur in der Datenbank erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="76f49-169">This is the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation script (`Install.sql`), which deploys the assemblies and creates the stored procedure within the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
-- Drop existing sproc and assembly if any.  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorldReady')  
DROP PROCEDURE usp_HelloWorldReady;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady')  
DROP ASSEMBLY HelloWorldReady;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.neutral')  
DROP ASSEMBLY [HelloWorldReady.resources.neutral]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.de')  
DROP ASSEMBLY [HelloWorldReady.resources.de]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.es')  
DROP ASSEMBLY [HelloWorldReady.resources.es]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.fr')  
DROP ASSEMBLY [HelloWorldReady.resources.fr]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.fr-FR')  
DROP ASSEMBLY [HelloWorldReady.resources.fr-FR]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.it')  
DROP ASSEMBLY [HelloWorldReady.resources.it]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.ja')  
DROP ASSEMBLY [HelloWorldReady.resources.ja]  
GO  
  
DECLARE @SamplesPath nvarchar(1024)  
-- You may need to modify the value of this variable if you have installed the sample someplace other than the default location.  
Set @SamplesPath = N'C:\MySample\'  
  
-- Add the assembly and CLR integration based stored procedure  
  
CREATE ASSEMBLY HelloWorldReady  
FROM @SamplesPath + 'HelloWorldReady.dll'  
WITH permission_set = Safe;  
  
CREATE ASSEMBLY [HelloWorldReady.resources.neutral]  
FROM @SamplesPath + 'HelloWorldReady.resources.dll'  
WITH permission_set = Safe;   
  
CREATE ASSEMBLY [HelloWorldReady.resources.de]  
FROM @SamplesPath + '\de\HelloWorldReady.resources.dll'  
WITH permission_set = Safe;  
  
CREATE ASSEMBLY [HelloWorldReady.resources.es]  
FROM @SamplesPath + '\es\HelloWorldReady.resources.dll'  
WITH permission_set = Safe;  
  
CREATE ASSEMBLY [HelloWorldReady.resources.fr]  
FROM @SamplesPath + '\fr\HelloWorldReady.resources.dll'  
WITH permission_set = Safe;  
  
CREATE ASSEMBLY [HelloWorldReady.resources.fr-FR]  
FROM @SamplesPath + '\fr-FR\HelloWorldReady.resources.dll'  
WITH permission_set = Safe;  
  
CREATE ASSEMBLY [HelloWorldReady.resources.it]  
FROM @SamplesPath + '\it\HelloWorldReady.resources.dll'  
WITH permission_set = Safe;  
  
CREATE ASSEMBLY [HelloWorldReady.resources.ja]  
FROM @SamplesPath + '\ja\HelloWorldReady.resources.dll'  
WITH permission_set = Safe;  
GO  
  
CREATE PROCEDURE usp_HelloWorldReady  
(  
@Culture NVarchar(12),  
@Greeting NVarchar(24) OUTPUT  
)  
AS EXTERNAL NAME HelloWorldReady.StoredProcedures.HelloWorldReady;  
GO  
  
USE master;  
GO  
```  
  
 <span data-ttu-id="76f49-170">Dies ist die Datei `test.sql`, mit der das Beispiel durch Ausführen der Funktionen für jedes Gebietsschema getestet wird.</span><span class="sxs-lookup"><span data-stu-id="76f49-170">This is `test.sql`, which tests the sample by executing the functions on each locale.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
DECLARE @GreetingDe nvarchar(24);  
DECLARE @GreetingDe_CH nvarchar(24);  
DECLARE @GreetingEn nvarchar(24);  
DECLARE @GreetingEs nvarchar(24);  
DECLARE @GreetingFr nvarchar(24);  
DECLARE @GreetingFr_FR nvarchar(24);  
DECLARE @GreetingIt nvarchar(24);  
DECLARE @GreetingJa nvarchar(24);  
  
--German as spoken anywhere in the world (the neutral German culture)  
EXEC usp_HelloWorldReady 'de', @GreetingDe OUTPUT;  
--German as spoken in Switzerland.  Because we don't have a specific assembly  
--for this case, the .NET Framework will automatically fall back to the neutral German culture DLL.  
EXEC usp_HelloWorldReady 'de-CH', @GreetingDe_CH OUTPUT;  
EXEC usp_HelloWorldReady 'en', @GreetingEn OUTPUT;  
EXEC usp_HelloWorldReady 'es', @GreetingEs OUTPUT;  
--French as spoken anywhere in the world (the neutral French culture)  
EXEC usp_HelloWorldReady 'fr', @GreetingFr OUTPUT  
--French as spoken in France.  Since we do have a specific assembly for this case, a specific   
--greeting is provided from that DLL.  The neutral French culture DLL is not used in this case.  
EXEC usp_HelloWorldReady 'fr-FR', @GreetingFr_FR OUTPUT  
EXEC usp_HelloWorldReady 'it', @GreetingIt OUTPUT;  
EXEC usp_HelloWorldReady 'ja', @GreetingJa OUTPUT;  
  
SELECT @GreetingDe AS OUTPUT_PARAMETER_DE;  
SELECT @GreetingDe_CH AS OUTPUT_PARAMETER_De_CH;  
SELECT @GreetingEn AS OUTPUT_PARAMETER_EN;  
SELECT @GreetingEs AS OUTPUT_PARAMETER_ES;  
SELECT @GreetingFr AS OUTPUT_PARAMETER_FR;  
SELECT @GreetingFr_FR AS OUTPUT_PARAMETER_Fr_FR;  
SELECT @GreetingIt AS OUTPUT_PARAMETER_IT;  
SELECT @GreetingJa AS OUTPUT_PARAMETER_JA;  
  
GO  
```  
  
 <span data-ttu-id="76f49-171">Im folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)]-Code werden die Assemblys und die gespeicherte Prozedur aus der Datenbank entfernt.</span><span class="sxs-lookup"><span data-stu-id="76f49-171">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] removes the assemblies and stored procedure from the database.</span></span>  
  
```  
USE AdventureWorks;  
GO  
  
-- Drop existing sproc and assembly if any.  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorldReady')  
DROP PROCEDURE usp_HelloWorldReady;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady')  
DROP ASSEMBLY HelloWorldReady;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.neutral')  
DROP ASSEMBLY [HelloWorldReady.resources.neutral]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.de')  
DROP ASSEMBLY [HelloWorldReady.resources.de]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.es')  
DROP ASSEMBLY [HelloWorldReady.resources.es]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.fr')  
DROP ASSEMBLY [HelloWorldReady.resources.fr]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.fr-FR')  
DROP ASSEMBLY [HelloWorldReady.resources.fr-FR]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.it')  
DROP ASSEMBLY [HelloWorldReady.resources.it]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.ja')  
DROP ASSEMBLY [HelloWorldReady.resources.ja]  
GO  
  
USE master;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="76f49-172">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76f49-172">See Also</span></span>  
 [<span data-ttu-id="76f49-173">Verwendungsszenarios und Beispiele für Common Language Runtime-Integration &#40;CLR&#41;</span><span class="sxs-lookup"><span data-stu-id="76f49-173">Usage Scenarios and Examples for Common Language Runtime &#40;CLR&#41; Integration</span></span>](../../../2014/database-engine/dev-guide/usage-scenarios-and-examples-for-common-language-runtime-clr-integration.md)  
  
  
