---
title: Azure-Blob-Quelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpblobsrc.f1
- sql11.dts.designer.afpblobsrc.f1
ms.assetid: 80645c5c-88c8-4fb0-8607-de1bb7bffcbb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a14c7022437c8a23f898a0f29c211bd9ae82aa0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621625"
---
# <a name="azure-blob-source"></a><span data-ttu-id="fcbb2-102">Azure-Blob-Quelle</span><span class="sxs-lookup"><span data-stu-id="fcbb2-102">Azure Blob Source</span></span>
 <span data-ttu-id="fcbb2-103">Die **Azure-Blobquelle** ermöglicht es einem SSIS-Paket, Daten aus einem Azure-Blob zu lesen.</span><span class="sxs-lookup"><span data-stu-id="fcbb2-103">The **Azure Blob Source** component enables an SSIS package to read data from an Azure blob.</span></span> <span data-ttu-id="fcbb2-104">Die unterstützten Dateiformate sind CSV und AVRO.</span><span class="sxs-lookup"><span data-stu-id="fcbb2-104">The supported file formats are: CSV and AVRO.</span></span> <span data-ttu-id="fcbb2-105">Um den Editor für die Azure-Blobquelle aufzurufen, ziehen Sie die **Azure-Blobquelle** auf den Datenfluss-Designer, und doppelklicken Sie darauf, um den Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="fcbb2-105">To see the editor for the Azure Blob Source, drag and drop **Azure Blob Source** on the data flow designer and double-click it to open the editor).</span></span>  
  
1.  <span data-ttu-id="fcbb2-106">Geben Sie für den **Azure Storage-Verbindungs-Manager** einen vorhandenen Azure Storage-Verbindungs-Manager an, oder erstellen Sie einen neuen, der auf ein Azure-Speicherkonto verweist.</span><span class="sxs-lookup"><span data-stu-id="fcbb2-106">For the **Azure storage connection manager** field, specify an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account.</span></span>  
  
2.  <span data-ttu-id="fcbb2-107">Geben Sie im Feld **Blobcontainername** den Namen des Blobcontainers an, der die Quelldateien enthält.</span><span class="sxs-lookup"><span data-stu-id="fcbb2-107">For the **Blob container name** field, specify the name of the blob container that contains source files.</span></span>  
  
3.  <span data-ttu-id="fcbb2-108">Geben Sie im Feld **Blobname** den Pfad für das Blob an.</span><span class="sxs-lookup"><span data-stu-id="fcbb2-108">For the **Blob name** field, specify the path for the blob.</span></span>  
  
4.  <span data-ttu-id="fcbb2-109">Geben Sie im Feld **Blobdateiformat** das gewünschte Blobformat an.</span><span class="sxs-lookup"><span data-stu-id="fcbb2-109">For the **Blob file format** field, specify the blob format you want to use.</span></span>  
  
5.  <span data-ttu-id="fcbb2-110">Wenn es sich um das CSV-Dateiformat handelt, geben Sie den Wert für das **Spaltentrennzeichen** ein.</span><span class="sxs-lookup"><span data-stu-id="fcbb2-110">If the file format is CSV, you must specify the **Column delimiter character** value.</span></span> <span data-ttu-id="fcbb2-111">Aktivieren Sie außerdem **Spaltennamen in der ersten Datenzeile** , wenn die erste Zeile in der Datei Spaltennamen enthält.</span><span class="sxs-lookup"><span data-stu-id="fcbb2-111">Also select **Column names in the first data row** if the first row in the file contains column names.</span></span>  
  
6.  <span data-ttu-id="fcbb2-112">Nachdem Sie die Verbindungsinformationen angegeben haben, wechseln Sie zur Seite **Spalten** , um Quellspalten zu den Zielspalten für den SSIS-Datenfluss zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="fcbb2-112">After specifying the connection information, switch to the **Columns** page to map source columns to destination columns for the SSIS data flow.</span></span>  
  
  
