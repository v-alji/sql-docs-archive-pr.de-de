---
title: 'Lektion 1: Erstellen des Projekts und Basispakets | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 84d0b877-603f-4f8e-bb6b-671558ade5c2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1a9ddc36ef242cc4e4b146e90dfa9de470e68d83
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618121"
---
# <a name="lesson-1-creating-the-project-and-basic-package"></a><span data-ttu-id="05fe4-102">Lektion 1: Erstellen des Projekts und Basispakets</span><span class="sxs-lookup"><span data-stu-id="05fe4-102">Lesson 1: Creating the Project and Basic Package</span></span>
  <span data-ttu-id="05fe4-103">In dieser Lektion erstellen Sie ein einfaches ETL-Paket, durch das Daten aus einer einzelnen Flatfilequelle extrahiert, Daten mithilfe zweier Transformationskomponenten für die Suche transformiert und diese Daten in die **FactCurrency** -Faktentabelle in **AdventureWorksDW2012**geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="05fe4-103">In this lesson, you will create a simple ETL package that extracts data from a single flat file source, transforms the data using two lookup transformation components, and writes that data to the **FactCurrency** fact table in **AdventureWorksDW2012**.</span></span> <span data-ttu-id="05fe4-104">Als Teil dieser Lektion lernen Sie das Erstellen neuer Pakete, das Hinzufügen und Konfigurieren von Datenquellen- und Datenzielverbindungen sowie das Arbeiten mit neuen Ablaufsteuerungs- und Datenflusskomponenten.</span><span class="sxs-lookup"><span data-stu-id="05fe4-104">As part of this lesson, you will learn how to create new packages, add and configure data source and destination connections, and work with new control flow and data flow components.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="05fe4-105">Dieses Lernprogramm erfordert die **AdventureWorksDW2012** -Beispieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="05fe4-105">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="05fe4-106">Weitere Informationen zum Installieren und Bereitstellen von **AdventureWorksDW2012**finden Sie unter [Microsoft SQL Server Product Samples: Reporting Services](https://archive.codeplex.com/?p=msftrsprodsamples).</span><span class="sxs-lookup"><span data-stu-id="05fe4-106">For more information on installing and deploying **AdventureWorksDW2012**, see [Microsoft SQL Server Product Samples: Reporting Services](https://archive.codeplex.com/?p=msftrsprodsamples).</span></span>  
  
## <a name="understanding-the-package-requirements"></a><span data-ttu-id="05fe4-107">Grundlegendes zu Paketanforderungen</span><span class="sxs-lookup"><span data-stu-id="05fe4-107">Understanding the Package Requirements</span></span>  
 <span data-ttu-id="05fe4-108">Dieses Lernprogramm erfordert Microsoft SQL Server Data Tools.</span><span class="sxs-lookup"><span data-stu-id="05fe4-108">This tutorial requires Microsoft SQL Server Data Tools.</span></span>  
  
 <span data-ttu-id="05fe4-109">Weitere Informationen zum Installieren von SQL Server Data Tools finden Sie unter [Herunterladen von SQL Server Data Tools](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt?view=sql-server-2017).</span><span class="sxs-lookup"><span data-stu-id="05fe4-109">For more information on installing the SQL Server Data Tools see [SQL Server Data Tools Download](https://docs.microsoft.com/sql/ssdt/download-sql-server-data-tools-ssdt?view=sql-server-2017).</span></span>  
  
 <span data-ttu-id="05fe4-110">Vor dem Erstellen eines Pakets benötigen Sie ein durchgehendes Verständnis der Formatierung in Quelldaten und dem Ziel.</span><span class="sxs-lookup"><span data-stu-id="05fe4-110">Before creating a package, you need a good understanding of the formatting used in both the source data and the destination.</span></span> <span data-ttu-id="05fe4-111">Nachdem Sie sich mit beiden dieser Datenformate vertraut gemacht haben, können Sie die Transformationen definieren, die zum Zuordnen der Quelldaten zum Ziel erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="05fe4-111">Once you understand both of these data formats, you will be ready to define the transformations necessary to map the source data to the destination.</span></span>  
  
### <a name="looking-at-the-source"></a><span data-ttu-id="05fe4-112">Untersuchen der Quelle</span><span class="sxs-lookup"><span data-stu-id="05fe4-112">Looking at the Source</span></span>  
 <span data-ttu-id="05fe4-113">Für dieses Lernprogramm bestehen die Quelldaten aus einer Reihe von historischen Währungsdaten in der Flatfile SampleCurrencyData.txt.</span><span class="sxs-lookup"><span data-stu-id="05fe4-113">For this tutorial, the source data is a set of historical currency data contained in the flat file, SampleCurrencyData.txt.</span></span> <span data-ttu-id="05fe4-114">Die Quelldaten bestehen aus den vier folgenden Spalten: der Durchschnittsrate der Währung, einem Währungsschlüssel, einem Datenschlüssel und der Tagesendrate.</span><span class="sxs-lookup"><span data-stu-id="05fe4-114">The source data has the following four columns: the average rate of the currency, a currency key, a date key, and the end-of-day rate.</span></span>  
  
 <span data-ttu-id="05fe4-115">Im Folgenden sehen Sie ein Beispiel der in der Datei SampleCurrencyData.txt enthaltenen Quelldaten:</span><span class="sxs-lookup"><span data-stu-id="05fe4-115">Here is an example of the source data contained in the SampleCurrencyData.txt file:</span></span>  
  
 `1.00070049USD9/3/05 0:001.001201442`  
  
 `1.00020004USD9/4/05 0:001`  
  
 `1.00020004USD9/5/05 0:001.001201442`  
  
 `1.00020004USD9/6/05 0:001`  
  
 `1.00020004USD9/7/05 0:001.00070049`  
  
 `1.00070049USD9/8/05 0:000.99980004`  
  
 `1.00070049USD9/9/05 0:001.001502253`  
  
 `1.00070049USD9/10/05 0:000.99990001`  
  
 `1.00020004USD9/11/05 0:001.001101211`  
  
 `1.00020004USD9/12/05 0:000.99970009`  
  
 <span data-ttu-id="05fe4-116">Für das Arbeiten mit Flatfile-Quelldaten ist das Verständnis darüber wichtig, wie vom Flatfile-Verbindungs-Manager die Flatfiledaten interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="05fe4-116">When working with flat file source data, it is important to understand how the Flat File connection manager interprets the flat file data.</span></span> <span data-ttu-id="05fe4-117">Wenn die Flatfilequelle aus Unicode besteht, definiert der Flatfile-Verbindungs-Manager alle Spalten als [DT_WSTR] mit einer Standardspaltenbreite von 50.</span><span class="sxs-lookup"><span data-stu-id="05fe4-117">If the flat file source is Unicode, the Flat File connection manager defines all columns as [DT_WSTR] with a default column width of 50.</span></span> <span data-ttu-id="05fe4-118">Wenn die Flatfilequelle ANSI-codiert ist, werden die Spalten als [DT_STR] mit einer Spaltenbreite von 50 definiert.</span><span class="sxs-lookup"><span data-stu-id="05fe4-118">If the flat file source is ANSI-encoded, the columns are defined as [DT_STR] with a column width of 50.</span></span> <span data-ttu-id="05fe4-119">Wahrscheinlich müssen Sie diese Standards ändern, um die Zeichenfolgen-Spaltentypen Ihren Daten anzupassen.</span><span class="sxs-lookup"><span data-stu-id="05fe4-119">You will probably have to change these defaults to make the string column types more appropriate for your data.</span></span> <span data-ttu-id="05fe4-120">Dafür müssen Sie den Datentyp des Zieles untersuchen, wohin die Daten geschrieben werden, und dann den entsprechenden Typ innerhalb des Flatfile-Verbindungs-Managers auswählen.</span><span class="sxs-lookup"><span data-stu-id="05fe4-120">To do this, you will need to look at the data type of the destination where the data will be written to and then choose the correct type within the Flat File connection manager.</span></span>  
  
### <a name="looking-at-the-destination"></a><span data-ttu-id="05fe4-121">Untersuchen des Zieles</span><span class="sxs-lookup"><span data-stu-id="05fe4-121">Looking at the Destination</span></span>  
 <span data-ttu-id="05fe4-122">Das endgültige Ziel für die Quelldaten ist die **FactCurrency** -Faktentabelle in **AdventureWorksDW**.</span><span class="sxs-lookup"><span data-stu-id="05fe4-122">The ultimate destination for the source data is the **FactCurrency** fact table in **AdventureWorksDW**.</span></span> <span data-ttu-id="05fe4-123">Die **FactCurrency** -Faktentabelle weist vier Spalten auf und hat Beziehungen zu zwei Dimensionstabellen, wie in der folgenden Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="05fe4-123">The **FactCurrency** fact table has four columns, and has relationships to two dimension tables, as shown in the following table.</span></span>  
  
|<span data-ttu-id="05fe4-124">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="05fe4-124">Column Name</span></span>|<span data-ttu-id="05fe4-125">Datentyp</span><span class="sxs-lookup"><span data-stu-id="05fe4-125">Data Type</span></span>|<span data-ttu-id="05fe4-126">Nachschlagetabelle</span><span class="sxs-lookup"><span data-stu-id="05fe4-126">Lookup Table</span></span>|<span data-ttu-id="05fe4-127">Suchspalte</span><span class="sxs-lookup"><span data-stu-id="05fe4-127">Lookup Column</span></span>|  
|-----------------|---------------|------------------|-------------------|  
|<span data-ttu-id="05fe4-128">AverageRate</span><span class="sxs-lookup"><span data-stu-id="05fe4-128">AverageRate</span></span>|<span data-ttu-id="05fe4-129">float</span><span class="sxs-lookup"><span data-stu-id="05fe4-129">float</span></span>|<span data-ttu-id="05fe4-130">Keine</span><span class="sxs-lookup"><span data-stu-id="05fe4-130">None</span></span>|<span data-ttu-id="05fe4-131">Keine</span><span class="sxs-lookup"><span data-stu-id="05fe4-131">None</span></span>|  
|<span data-ttu-id="05fe4-132">CurrencyKey</span><span class="sxs-lookup"><span data-stu-id="05fe4-132">CurrencyKey</span></span>|<span data-ttu-id="05fe4-133">int (FK)</span><span class="sxs-lookup"><span data-stu-id="05fe4-133">int (FK)</span></span>|<span data-ttu-id="05fe4-134">DimCurrency</span><span class="sxs-lookup"><span data-stu-id="05fe4-134">DimCurrency</span></span>|<span data-ttu-id="05fe4-135">CurrencyKey (PK)</span><span class="sxs-lookup"><span data-stu-id="05fe4-135">CurrencyKey (PK)</span></span>|  
|<span data-ttu-id="05fe4-136">DateKey</span><span class="sxs-lookup"><span data-stu-id="05fe4-136">DateKey</span></span>|<span data-ttu-id="05fe4-137">int (FK)</span><span class="sxs-lookup"><span data-stu-id="05fe4-137">Int (FK)</span></span>|<span data-ttu-id="05fe4-138">DimDate</span><span class="sxs-lookup"><span data-stu-id="05fe4-138">DimDate</span></span>|<span data-ttu-id="05fe4-139">DateKey (PK)</span><span class="sxs-lookup"><span data-stu-id="05fe4-139">DateKey (PK)</span></span>|  
|<span data-ttu-id="05fe4-140">EndOfDayRate</span><span class="sxs-lookup"><span data-stu-id="05fe4-140">EndOfDayRate</span></span>|<span data-ttu-id="05fe4-141">float</span><span class="sxs-lookup"><span data-stu-id="05fe4-141">float</span></span>|<span data-ttu-id="05fe4-142">Keine</span><span class="sxs-lookup"><span data-stu-id="05fe4-142">None</span></span>|<span data-ttu-id="05fe4-143">Keine</span><span class="sxs-lookup"><span data-stu-id="05fe4-143">None</span></span>|  
  
### <a name="mapping-source-data-to-be-compatible-with-the-destination"></a><span data-ttu-id="05fe4-144">Zuordnen der Quelldaten zum Ziel aus Kompatibilitätsgründen</span><span class="sxs-lookup"><span data-stu-id="05fe4-144">Mapping Source Data to be Compatible with the Destination</span></span>  
 <span data-ttu-id="05fe4-145">Die Analyse der Quell- und Zieldatenformate ergibt, dass Suchvorgänge für die Werte **CurrencyKey** und **DateKey** notwendig sein werden.</span><span class="sxs-lookup"><span data-stu-id="05fe4-145">Analysis of the source and destination data formats indicates that lookups will be necessary for the **CurrencyKey** and **DateKey** values.</span></span> <span data-ttu-id="05fe4-146">Die Transformationen, von denen diese Suchvorgänge ausgeführt werden, rufen die Werte **CurrencyKey** und **DateKey** ab, indem die alternativen Schlüssel aus den Dimensionstabellen **DimCurrency** und **DimDate** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="05fe4-146">The transformations that will perform these lookups will obtain the **CurrencyKey** and **DateKey** values by using the alternate keys from **DimCurrency** and **DimDate** dimension tables.</span></span>  
  
|<span data-ttu-id="05fe4-147">Flatfilespalte</span><span class="sxs-lookup"><span data-stu-id="05fe4-147">Flat File Column</span></span>|<span data-ttu-id="05fe4-148">Tabellenname</span><span class="sxs-lookup"><span data-stu-id="05fe4-148">Table Name</span></span>|<span data-ttu-id="05fe4-149">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="05fe4-149">Column Name</span></span>|<span data-ttu-id="05fe4-150">Datentyp</span><span class="sxs-lookup"><span data-stu-id="05fe4-150">Data Type</span></span>|  
|----------------------|----------------|-----------------|---------------|  
|<span data-ttu-id="05fe4-151">0</span><span class="sxs-lookup"><span data-stu-id="05fe4-151">0</span></span>|<span data-ttu-id="05fe4-152">FactCurrency</span><span class="sxs-lookup"><span data-stu-id="05fe4-152">FactCurrency</span></span>|<span data-ttu-id="05fe4-153">AverageRate</span><span class="sxs-lookup"><span data-stu-id="05fe4-153">AverageRate</span></span>|<span data-ttu-id="05fe4-154">float</span><span class="sxs-lookup"><span data-stu-id="05fe4-154">float</span></span>|  
|<span data-ttu-id="05fe4-155">1</span><span class="sxs-lookup"><span data-stu-id="05fe4-155">1</span></span>|<span data-ttu-id="05fe4-156">DimCurrency</span><span class="sxs-lookup"><span data-stu-id="05fe4-156">DimCurrency</span></span>|<span data-ttu-id="05fe4-157">CurrencyAlternateKey</span><span class="sxs-lookup"><span data-stu-id="05fe4-157">CurrencyAlternateKey</span></span>|<span data-ttu-id="05fe4-158">nchar (3)</span><span class="sxs-lookup"><span data-stu-id="05fe4-158">nchar (3)</span></span>|  
|<span data-ttu-id="05fe4-159">2</span><span class="sxs-lookup"><span data-stu-id="05fe4-159">2</span></span>|<span data-ttu-id="05fe4-160">DimDate</span><span class="sxs-lookup"><span data-stu-id="05fe4-160">DimDate</span></span>|<span data-ttu-id="05fe4-161">FullDateAlternateKey</span><span class="sxs-lookup"><span data-stu-id="05fe4-161">FullDateAlternateKey</span></span>|<span data-ttu-id="05fe4-162">date</span><span class="sxs-lookup"><span data-stu-id="05fe4-162">date</span></span>|  
|<span data-ttu-id="05fe4-163">3</span><span class="sxs-lookup"><span data-stu-id="05fe4-163">3</span></span>|<span data-ttu-id="05fe4-164">FactCurrency</span><span class="sxs-lookup"><span data-stu-id="05fe4-164">FactCurrency</span></span>|<span data-ttu-id="05fe4-165">EndOfDayRate</span><span class="sxs-lookup"><span data-stu-id="05fe4-165">EndOfDayRate</span></span>|<span data-ttu-id="05fe4-166">float</span><span class="sxs-lookup"><span data-stu-id="05fe4-166">float</span></span>|  
  
## <a name="lesson-tasks"></a><span data-ttu-id="05fe4-167">Lektionsaufgaben</span><span class="sxs-lookup"><span data-stu-id="05fe4-167">Lesson Tasks</span></span>  
 <span data-ttu-id="05fe4-168">Diese Lektion enthält die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="05fe4-168">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="05fe4-169">Schritt 1: Erstellen eines neuen Integration Services-Projekts</span><span class="sxs-lookup"><span data-stu-id="05fe4-169">Step 1: Creating a New Integration Services Project</span></span>](lesson-1-1-creating-a-new-integration-services-project.md)  
  
-   [<span data-ttu-id="05fe4-170">Schritt 2: Hinzufügen und Konfigurieren eines Verbindungs-Managers für Flatfiles</span><span class="sxs-lookup"><span data-stu-id="05fe4-170">Step 2: Adding and Configuring a Flat File Connection Manager</span></span>](lesson-1-2-adding-and-configuring-a-flat-file-connection-manager.md)  
  
-   [<span data-ttu-id="05fe4-171">Schritt 3: Hinzufügen und Konfigurieren eines OLE DB-Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="05fe4-171">Step 3: Adding and Configuring an OLE DB Connection Manager</span></span>](lesson-1-3-adding-and-configuring-an-ole-db-connection-manager.md)  
  
-   [<span data-ttu-id="05fe4-172">Schritt 4: Hinzufügen eines Datenflusstasks zum Paket</span><span class="sxs-lookup"><span data-stu-id="05fe4-172">Step 4: Adding a Data Flow Task to the Package</span></span>](lesson-1-4-adding-a-data-flow-task-to-the-package.md)  
  
-   [<span data-ttu-id="05fe4-173">Schritt 5: Hinzufügen und Konfigurieren der Flatfilequelle</span><span class="sxs-lookup"><span data-stu-id="05fe4-173">Step 5: Adding and Configuring the Flat File Source</span></span>](lesson-1-5-adding-and-configuring-the-flat-file-source.md)  
  
-   [<span data-ttu-id="05fe4-174">Schritt 6: Hinzufügen und Konfigurieren der Transformationen zum Suchen</span><span class="sxs-lookup"><span data-stu-id="05fe4-174">Step 6: Adding and Configuring the Lookup Transformations</span></span>](lesson-1-6-adding-and-configuring-the-lookup-transformations.md)  
  
-   [<span data-ttu-id="05fe4-175">Schritt 7: Hinzufügen und Konfigurieren des OLE DB-Ziels</span><span class="sxs-lookup"><span data-stu-id="05fe4-175">Step 7: Adding and Configuring the OLE DB Destination</span></span>](lesson-1-7-adding-and-configuring-the-ole-db-destination.md)  
  
-   [<span data-ttu-id="05fe4-176">Schritt 8: Vereinfachen des Layouts des Pakets aus Lektion 1</span><span class="sxs-lookup"><span data-stu-id="05fe4-176">Step 8: Making the Lesson 1 Package Easier to Understand</span></span>](lesson-1-8-making-the-lesson-1-package-easier-to-understand.md)  
  
-   [<span data-ttu-id="05fe4-177">Schritt 9: Testen des Tutorialpakets aus Lektion 1</span><span class="sxs-lookup"><span data-stu-id="05fe4-177">Step 9: Testing the Lesson 1 Tutorial Package</span></span>](lesson-1-9-testing-the-lesson-1-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="05fe4-178">Lektion beginnen</span><span class="sxs-lookup"><span data-stu-id="05fe4-178">Start the Lesson</span></span>  
 [<span data-ttu-id="05fe4-179">Schritt 1: Erstellen eines neuen Integration Services-Projekts</span><span class="sxs-lookup"><span data-stu-id="05fe4-179">Step 1: Creating a New Integration Services Project</span></span>](lesson-1-1-creating-a-new-integration-services-project.md)  
  
  
