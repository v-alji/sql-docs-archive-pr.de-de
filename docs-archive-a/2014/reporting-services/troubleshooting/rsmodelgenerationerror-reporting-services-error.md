---
title: 'rsModelGenerationError: Reporting Services-Fehler | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsModelGenerationError
ms.assetid: 3a0ad63f-87f9-4ca1-b0c2-c85fa991634a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 713de57f0f2957983966f8ef0345bb374c311781
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618457"
---
# <a name="rsmodelgenerationerror---reporting-services-error"></a><span data-ttu-id="81c6b-102">rsModelGenerationError – Reporting Services-Fehler</span><span class="sxs-lookup"><span data-stu-id="81c6b-102">rsModelGenerationError - Reporting Services Error</span></span>
    
## <a name="details"></a><span data-ttu-id="81c6b-103">Details</span><span class="sxs-lookup"><span data-stu-id="81c6b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="81c6b-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="81c6b-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="81c6b-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="81c6b-105">Event ID</span></span>|<span data-ttu-id="81c6b-106">rsRenderingError</span><span class="sxs-lookup"><span data-stu-id="81c6b-106">rsRenderingError</span></span>|  
|<span data-ttu-id="81c6b-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="81c6b-107">Event Source</span></span>|<span data-ttu-id="81c6b-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span><span class="sxs-lookup"><span data-stu-id="81c6b-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span></span>|  
|<span data-ttu-id="81c6b-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="81c6b-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="81c6b-110">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="81c6b-110">Message Text</span></span>|<span data-ttu-id="81c6b-111">Fehler beim Generieren des Modells.</span><span class="sxs-lookup"><span data-stu-id="81c6b-111">An error occurred while generating model.</span></span> <span data-ttu-id="81c6b-112">(rsModelGenerationError) (ReportingServicesLibrary) %1</span><span class="sxs-lookup"><span data-stu-id="81c6b-112">(rsModelGenerationError) (ReportingServicesLibrary) %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="81c6b-113">Erklärung</span><span class="sxs-lookup"><span data-stu-id="81c6b-113">Explanation</span></span>  
 <span data-ttu-id="81c6b-114">Das Berichtsmodell konnte nicht generiert werden.</span><span class="sxs-lookup"><span data-stu-id="81c6b-114">The report model could not be generated.</span></span> <span data-ttu-id="81c6b-115">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]2005 SP1 und früheren Versionen wird der Fehler meist angezeigt, wenn das System.Data.DataSet-Objekt eine Tabelle oder Beziehung innerhalb des Datenbankschemas nicht behandeln kann, beispielsweise wenn für dieselbe Spalte in einer Tabelle zwei Fremdschlüssel definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="81c6b-115">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]2005 SP1 and earlier versions, this error is most likely displayed when the System.Data.DataSet object cannot handle a table or relationship within the database schema, such as when, for example, two foreign keys are defined on the same column within a table.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="81c6b-116">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="81c6b-116">User Action</span></span>  
 <span data-ttu-id="81c6b-117">Überprüfen Sie die Berichtsserver-Protokolldateien, um die spezifische Ursache dieser Meldung zu bestimmen. Diese Dateien finden Sie unter \Microsoft SQL Server\\<SQL Server-Instanz\>\Reporting Services\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="81c6b-117">To determine the specific reason that caused this message to appear, review the report server log files, which are located at \Microsoft SQL Server\\<SQL Server Instance\>\Reporting Services\LogFiles.</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="81c6b-118">Nur intern</span><span class="sxs-lookup"><span data-stu-id="81c6b-118">Internal-Only</span></span>  
  
