---
title: Azure Data Lake Store Source | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPADLSSRC.F1
- SQL11.DTS.DESIGNER.AFPADLSSRC.F1
ms.assetid: 7d9e8457-62aa-4aea-98ee-7d1121dfae4f
author: yualan
ms.author: chugu
ms.openlocfilehash: e5bce25e303b055d734da6a00c73851f4eb0d7ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619292"
---
# <a name="azure-data-lake-store-source"></a><span data-ttu-id="466e6-102">Azure Data Lake Store Source</span><span class="sxs-lookup"><span data-stu-id="466e6-102">Azure Data Lake Store Source</span></span>
  <span data-ttu-id="466e6-103">Die Komponente **Azure Data Lake Store Source** ermöglicht einem SSIS-Paket das Lesen von Daten aus Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="466e6-103">The **Azure Data Lake Store Source** component enables an SSIS package to read data from an Azure Data Lake Store.</span></span> <span data-ttu-id="466e6-104">Die unterstützten Dateiformate sind: Text und Avro.</span><span class="sxs-lookup"><span data-stu-id="466e6-104">The supported file formats are: Text and Avro.</span></span>
  
## <a name="configure-the-azure-data-lake-store-source"></a><span data-ttu-id="466e6-105">Konfigurieren von Azure Data Lake Store Source</span><span class="sxs-lookup"><span data-stu-id="466e6-105">Configure the Azure Data Lake Store Source</span></span> 
  
1.  <span data-ttu-id="466e6-106">Um den Editor für Azure Data Lake Store Source aufzurufen, ziehen Sie die **Azure Data Lake Store Source** auf den Datenfluss-Designer, und doppelklicken Sie darauf, um den Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="466e6-106">To see the editor for the Azure Data Lake Store Source, drag and drop **Azure Data Lake Store Source** on the data flow designer and double-click it to open the editor).</span></span>  
  
2.  <span data-ttu-id="466e6-107">Geben Sie im Feld **Azure Data Lake Store connection manager** (Azure Data Lake Store-Verbindungs-Manager) einen vorhandenen Azure Data Lake Store-Verbindungs-Manager an, oder erstellen Sie einen neuen, der auf einen Azure Data Lake Store-Dienst verweist.</span><span class="sxs-lookup"><span data-stu-id="466e6-107">For the **Azure Data Lake Store connection manager** field, specify an existing Azure Data Lake Store Connection Manager or create a new one that refers to an Azure Data Lake Store service.</span></span>  
  
    1.  <span data-ttu-id="466e6-108">Geben Sie im Feld **Dateipfad** den Dateipfad der Quelldatei in Azure Data Lake Store an.</span><span class="sxs-lookup"><span data-stu-id="466e6-108">For the **File Path** field, specify the file path of the source file in Azure Data Lake Store.</span></span>   
  
    2.  <span data-ttu-id="466e6-109">Geben Sie im Feld **Dateiformat** das Dateiformat der Quelldatei an.</span><span class="sxs-lookup"><span data-stu-id="466e6-109">For the **File format** field, specify the file format of the source file.</span></span>  
  
        <span data-ttu-id="466e6-110">Wenn es sich um Textformat handelt, geben Sie den Wert für das **Spaltentrennzeichen** ein.</span><span class="sxs-lookup"><span data-stu-id="466e6-110">If the file format is Text, you must specify the **Column delimiter character** value.</span></span> <span data-ttu-id="466e6-111">Aktivieren Sie außerdem **Spaltennamen in der ersten Datenzeile** , wenn die erste Zeile in der Datei Spaltennamen enthält.</span><span class="sxs-lookup"><span data-stu-id="466e6-111">Also select **Column names in the first data row** if the first row in the file contains column names.</span></span>  
  
3.  <span data-ttu-id="466e6-112">Nachdem Sie die Verbindungsinformationen angegeben haben, wechseln Sie zur Seite **Spalten** , um Quellspalten zu den Zielspalten für den SSIS-Datenfluss zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="466e6-112">After specifying the connection information, switch to the **Columns** page to map source columns to destination columns for the SSIS data flow.</span></span>  
