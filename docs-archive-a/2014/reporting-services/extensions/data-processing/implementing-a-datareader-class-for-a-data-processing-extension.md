---
title: Implementieren einer DataReader-Klasse für Datenverarbeitungserweiterungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], data readers
- data readers [Reporting Services]
- DataReader class
- read-only data
ms.assetid: 23e286e7-6074-4fbe-be29-203420d6c3d0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7c9e55741c72d624b7149435ced90550135d8b4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725273"
---
# <a name="implementing-a-datareader-class-for-a-data-processing-extension"></a><span data-ttu-id="6c9dc-102">Implementieren einer DataReader-Klasse für Datenverarbeitungserweiterungen</span><span class="sxs-lookup"><span data-stu-id="6c9dc-102">Implementing a DataReader Class for a Data Processing Extension</span></span>
  <span data-ttu-id="6c9dc-103">Mithilfe des **DataReader**-Objekts kann ein Client einen schreibgeschützten Vorwärtsdatenstrom von einer Datenquelle empfangen.</span><span class="sxs-lookup"><span data-stu-id="6c9dc-103">The **DataReader** object enables a client to retrieve a read-only, forward-only stream of data from a data source.</span></span> <span data-ttu-id="6c9dc-104">Ergebnisse werden bei der Ausführung der Abfrage zurückgegeben und im Netzwerkpuffer auf dem Client gespeichert, bis Sie sie unter Verwendung der **Read**-Methode der **DataReader**-Klasse anfordern.</span><span class="sxs-lookup"><span data-stu-id="6c9dc-104">Results are returned as the query executes and are stored in the network buffer on the client until you request them using the **Read** method of the **DataReader** class.</span></span> <span data-ttu-id="6c9dc-105">Implementieren Sie <xref:Microsoft.ReportingServices.DataProcessing.IDataReader> und optional <xref:Microsoft.ReportingServices.DataProcessing.IDataReaderExtension>, um eine **DataReader**-Klasse zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6c9dc-105">To create a **DataReader** class, implement <xref:Microsoft.ReportingServices.DataProcessing.IDataReader> and optionally implement <xref:Microsoft.ReportingServices.DataProcessing.IDataReaderExtension>.</span></span> <span data-ttu-id="6c9dc-106">Die Verwendung eines **DataReader**-Objekts erhöht die Anwendungsleistung, da die Daten sofort bei Verfügbarkeit abgerufen werden, statt auf die gesamten Ergebnisse der Abfrage zu warten, und da (standardmäßig) immer nur eine Zeile im Speicher gespeichert wird. So wird der Systemverwaltungsaufwand reduziert.</span><span class="sxs-lookup"><span data-stu-id="6c9dc-106">Using a **DataReader** object increases application performance both by retrieving data as soon as it is available, rather than waiting for the entire results of the query to be returned, and (by default) storing only one row at a time in memory, reducing system overhead.</span></span>  
  
 <span data-ttu-id="6c9dc-107">Nachdem Sie eine Instanz der **Command**-Klasse erstellt haben, legen Sie ein **DataReader**-Objekt an, indem Sie **Command.ExecuteReader** aufrufen, um Zeilen von der Datenquelle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="6c9dc-107">After creating an instance of your **Command** class, you create a **DataReader** object by calling **Command.ExecuteReader** to retrieve rows from the data source.</span></span> <span data-ttu-id="6c9dc-108">Die **DataReader**-Implementierung muss über zwei grundlegende Funktionen verfügen: Vorwärtszugriff auf die Resultsets, die durch die Ausführung eines Befehls abgerufen wurden, und Zugriff auf die Spaltentypen, Namen und Werte innerhalb jeder Zeile.</span><span class="sxs-lookup"><span data-stu-id="6c9dc-108">The **DataReader** implementation must provide two basic capabilities: forward-only access over the result sets obtained by executing a command and access to the column types, names, and values within each row.</span></span> <span data-ttu-id="6c9dc-109">Clients verwenden die **Read**-Methode des **DataReader**-Objekts, um eine Zeile aus den Ergebnissen der Abfrage abzurufen.</span><span class="sxs-lookup"><span data-stu-id="6c9dc-109">Clients use the **Read** method of the **DataReader** object to obtain a row from the results of the query.</span></span>  
  
 <span data-ttu-id="6c9dc-110">Im Berichts-Designer werden mithilfe des **DataReader**-Objekts eine Liste der Felder sowie Schemainformationen zur Ergebnisreihe abgerufen.</span><span class="sxs-lookup"><span data-stu-id="6c9dc-110">In Report Designer, your **DataReader** object is used to retrieve a list of fields as well as schema information about the result set.</span></span> <span data-ttu-id="6c9dc-111">Hierzu müssen die Methoden **GetName**, **GetValue**, **GetFieldType,** und **GetOrdinal** der <xref:Microsoft.ReportingServices.DataProcessing.IDataReader>-Schnittstelle implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="6c9dc-111">This is accomplished by implementing the **GetName**, **GetValue**, **GetFieldType,** and **GetOrdinal** methods of the <xref:Microsoft.ReportingServices.DataProcessing.IDataReader> interface.</span></span>  
  
 <span data-ttu-id="6c9dc-112">Mit der <xref:Microsoft.ReportingServices.DataProcessing.IDataReaderExtension>-Schnittstelle können Sie bestimmte Aggregationsinformationen über das Resultset angeben.</span><span class="sxs-lookup"><span data-stu-id="6c9dc-112">The <xref:Microsoft.ReportingServices.DataProcessing.IDataReaderExtension> interface allows you to supply specific aggregation information about your result set.</span></span> <span data-ttu-id="6c9dc-113">Eine Beispiel-**DataReader**-Klassenimplementierung finden Sie unter [SQL Server Reporting Services Product Samples (SQL Server Reporting Services-Produktbeispiele)](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="6c9dc-113">For a sample **DataReader** class implementation, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c9dc-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6c9dc-114">See Also</span></span>  
 <span data-ttu-id="6c9dc-115">[Erweiterungen für Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="6c9dc-115">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="6c9dc-116">[Implementieren von Datenverarbeitungserweiterungen](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="6c9dc-116">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="6c9dc-117">Reporting Services Extension Library (Reporting Services-Erweiterungsbibliothek)</span><span class="sxs-lookup"><span data-stu-id="6c9dc-117">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
