---
title: Azure-Blob-Ziel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpblobdest.f1
- sql11.dts.designer.afpblobdest.f1
ms.assetid: 820a1e7a-7182-4c7b-ab56-5b4097a7e042
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fb406d38b17748e8284acee4b2849a9fd99e53ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722933"
---
# <a name="azure-blob-destination"></a><span data-ttu-id="cd81a-102">Azure-BLOB-Ziel</span><span class="sxs-lookup"><span data-stu-id="cd81a-102">Azure Blob Destination</span></span>
  <span data-ttu-id="cd81a-103">Die Komponente **Azure-Blobziel** ermöglicht einem SSIS-Paket das Schreiben von Daten in ein Azure-Blob.</span><span class="sxs-lookup"><span data-stu-id="cd81a-103">The **Azure Blob Destination** component enables an SSIS package to write data to an Azure blob.</span></span> <span data-ttu-id="cd81a-104">Die unterstützten Dateiformate sind CSV und AVRO.</span><span class="sxs-lookup"><span data-stu-id="cd81a-104">The supported file formats are: CSV and AVRO.</span></span> <span data-ttu-id="cd81a-105">Ziehen Sie das **Azure-BLOB-Ziel** in den Datenfluss-Designer, und doppelklicken Sie darauf, um den Editor anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cd81a-105">Ddrag-drop **Azure Blob Destination** to the data flow designer and double-click it to see the editor).</span></span>  
  
1.  <span data-ttu-id="cd81a-106">Geben Sie für den **Azure Storage-Verbindungs-Manager** einen vorhandenen Azure Storage-Verbindungs-Manager an, oder erstellen Sie einen neuen, der auf ein Azure-Speicherkonto verweist.</span><span class="sxs-lookup"><span data-stu-id="cd81a-106">For the **Azure storage connection manager** field, specify an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account.</span></span>  
  
2.  <span data-ttu-id="cd81a-107">Geben Sie im Feld **Blobcontainername** den Namen des Blobcontainers an, der die Quelldateien enthält.</span><span class="sxs-lookup"><span data-stu-id="cd81a-107">For the **Blob container name** field, specify the name of the blob container that contains source files.</span></span>  
  
3.  <span data-ttu-id="cd81a-108">Geben Sie im Feld **Blobname** den Pfad für das Blob an.</span><span class="sxs-lookup"><span data-stu-id="cd81a-108">For the **Blob name** field, specify the path for the blob.</span></span>  
  
4.  <span data-ttu-id="cd81a-109">Geben Sie im Feld **Blobdateiformat** das gewünschte Blobformat an.</span><span class="sxs-lookup"><span data-stu-id="cd81a-109">For the **Blob file format** field, specify the blob format you want to use.</span></span>  
  
5.  <span data-ttu-id="cd81a-110">Wenn es sich um das CSV-Dateiformat handelt, geben Sie den Wert für das **Spaltentrennzeichen** ein.</span><span class="sxs-lookup"><span data-stu-id="cd81a-110">If the file format is CSV, you must specify the **Column delimiter character** value.</span></span> <span data-ttu-id="cd81a-111">Wählen Sie außerdem **Spaltennamen in der ersten Daten Zeile aus** , wenn die erste Zeile in der Datei Spaltennamen enthält.</span><span class="sxs-lookup"><span data-stu-id="cd81a-111">Also  select **Column names in the first data row** if the first row in the file contains column names.</span></span>  
  
6.  <span data-ttu-id="cd81a-112">Nachdem Sie die Verbindungsinformationen angegeben haben, wechseln Sie zur Seite **Spalten** , um Quellspalten zu den Zielspalten für den SSIS-Datenfluss zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="cd81a-112">After specifying the connection information, switch to the **Columns** page to map source columns to destination columns for the SSIS data flow.</span></span>  
  
  
