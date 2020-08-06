---
title: Azure Data Lake Store Destination | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPADLSDEST.F1
- SQL11.DTS.DESIGNER.AFPADLSDEST.F1
ms.assetid: d0e86032-2a6b-48b2-898f-e94328474fde
author: yualan
ms.author: chugu
ms.openlocfilehash: 14248d14b6a944250c33a19c8cf83ab0e0330587
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724049"
---
# <a name="azure-data-lake-store-destination"></a><span data-ttu-id="3bf50-102">Azure Data Lake Store Destination</span><span class="sxs-lookup"><span data-stu-id="3bf50-102">Azure Data Lake Store Destination</span></span>
  <span data-ttu-id="3bf50-103">Die Komponente **Azure Data Lake Store Destination** ermöglicht einem SSIS-Paket das Schreiben von Daten in Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="3bf50-103">The **Azure Data Lake Store Destination** component enables an SSIS package to write data to an Azure Data Lake Store.</span></span> <span data-ttu-id="3bf50-104">Die unterstützten Dateiformate sind: Text, Avro und ORC.</span><span class="sxs-lookup"><span data-stu-id="3bf50-104">The supported file formats are: Text, Avro and ORC.</span></span> 
  
## <a name="configure-the-azure-data-lake-store-destination"></a><span data-ttu-id="3bf50-105">Konfigurieren von Azure Data Lake Store Destination</span><span class="sxs-lookup"><span data-stu-id="3bf50-105">Configure the Azure Data Lake Store Destination</span></span> 

1. <span data-ttu-id="3bf50-106">Ziehen Sie **Azure Data Lake Store Destination** auf den Datenfluss-Designer, und doppelklicken Sie darauf, um den Code-Editor aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="3bf50-106">Drag-drop **Azure Data Lake Store Destination** to the data flow designer and double-click it to see the editor.</span></span>  

2.  <span data-ttu-id="3bf50-107">Geben Sie im Feld **Azure Data Lake Store connection manager** (Azure Data Lake Store-Verbindungs-Manager) einen vorhandenen Azure Data Lake Store-Verbindungs-Manager an, oder erstellen Sie einen neuen, der auf einen Azure Data Lake Store-Dienst verweist.</span><span class="sxs-lookup"><span data-stu-id="3bf50-107">For the **Azure Data Lake Store connection manager** field, specify an existing Azure Data Lake Store Connection Manager or create a new one that refers to an Azure Data Lake Store service.</span></span>  
  
    1.  <span data-ttu-id="3bf50-108">Geben Sie im Feld **Dateipfad** den Namen der Datei an, in die Daten geschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3bf50-108">For the **File Path** field, specify the file name you want to write data to.</span></span> <span data-ttu-id="3bf50-109">Wenn diese Datei bereits vorhanden ist, wird der Inhalt überschrieben.</span><span class="sxs-lookup"><span data-stu-id="3bf50-109">If this file already exist, its content will be overwritten.</span></span>  
  
    2.  <span data-ttu-id="3bf50-110">Geben Sie im Feld **Dateiformat** das gewünschte Dateiformat an.</span><span class="sxs-lookup"><span data-stu-id="3bf50-110">For the **File format** field, specify the file format you want to use.</span></span>  
  
        <span data-ttu-id="3bf50-111">Wenn es sich um Textformat handelt, geben Sie den Wert für das **Spaltentrennzeichen** ein.</span><span class="sxs-lookup"><span data-stu-id="3bf50-111">If the file format is Text, you must specify the **Column delimiter character** value.</span></span> <span data-ttu-id="3bf50-112">Wählen Sie außerdem **Spaltennamen in der ersten Daten Zeile aus** , wenn die erste Zeile in der Datei Spaltennamen enthält.</span><span class="sxs-lookup"><span data-stu-id="3bf50-112">Also  select **Column names in the first data row** if the first row in the file contains column names.</span></span>  

        <span data-ttu-id="3bf50-113">Wenn das Dateiformat ORC ist, müssen Sie JRE auf der entsprechenden Plattform installieren.</span><span class="sxs-lookup"><span data-stu-id="3bf50-113">If the file format is ORC, you need to install JRE of corresponding platform.</span></span> 
  
3.  <span data-ttu-id="3bf50-114">Nachdem Sie die Verbindungsinformationen angegeben haben, wechseln Sie zur Seite **Spalten** , um Quellspalten zu den Zielspalten für den SSIS-Datenfluss zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="3bf50-114">After specifying the connection information, switch to the **Columns** page to map source columns to destination columns for the SSIS data flow.</span></span>  
