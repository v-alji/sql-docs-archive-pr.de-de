---
title: Verbindung mit Server herstellen (Seite „Zusätzliche Verbindungsparameter“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttoserver.options.registeredservers.f1
ms.assetid: ba34b01a-6289-4eb8-8341-fa3d9ec87b3f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 5c6a23df6a6b9ea324d54fd270f5aa2269471ed8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622872"
---
# <a name="connect-to-server-additional-connection-parameters-page"></a><span data-ttu-id="a1c57-102">Verbindung mit Server herstellen (Seite 'Zusätzliche Verbindungsparameter')</span><span class="sxs-lookup"><span data-stu-id="a1c57-102">Connect to Server (Additional Connection Parameters Page)</span></span>
  <span data-ttu-id="a1c57-103">Im Dialogfeld **Verbinden mit** von [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] werden die gängigsten Verbindungszeichenfolgenwerte als Optionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a1c57-103">The **Connect to** dialog box of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] presents the most common connection string values as options.</span></span> <span data-ttu-id="a1c57-104">Mithilfe der Seite **Zusätzliche Verbindungsparameter** können Sie der Verbindungszeichenfolge weitere Verbindungsparameter hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a1c57-104">Use the **Additional Connection Parameters** page to add more connection parameters to the connection string.</span></span>  
  
-   <span data-ttu-id="a1c57-105">Zusätzliche Verbindungsparameter können beliebige ODBC-Verbindungsparameter sein.</span><span class="sxs-lookup"><span data-stu-id="a1c57-105">Additional connection parameters can be any ODBC connection parameter.</span></span>  
  
-   <span data-ttu-id="a1c57-106">Zusätzliche Verbindungsparameter sollten im Format **;Parameter1=Wert1;Parameter2=Wert2**hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="a1c57-106">Additional connection parameters should be added in the format **;parameter1=value1;parameter2=value2**.</span></span>  
  
-   <span data-ttu-id="a1c57-107">Parameter, die mithilfe der Seite **Zusätzliche Verbindungsparameter** hinzugefügt werden, werden den Parametern hinzugefügt, die mithilfe der Optionen des Dialogfelds **Verbinden mit** ausgewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="a1c57-107">Parameters added using the **Additional Connection Parameters** page are added to the parameters selected using the **Connect to** dialog box options.</span></span>  
  
-   <span data-ttu-id="a1c57-108">Durch die letzte Instanz eines Parameters werden alle vorherigen Instanzen des Parameters überschrieben.</span><span class="sxs-lookup"><span data-stu-id="a1c57-108">The last instance of each parameter provided overrides any previous instances of the parameter.</span></span> <span data-ttu-id="a1c57-109">Parameter, die mithilfe der Seite **Zusätzliche Verbindungsparameter** hinzugefügt werden, orientieren sich an den Parametern, die auf den Registerkarten **Anmeldung** und **Verbindungseigenschaften** bereitgestellt sind, und ersetzen diese.</span><span class="sxs-lookup"><span data-stu-id="a1c57-109">Parameters added using the **Additional Connection Parameters** page follow and replace the parameters provided in the **Login** or **Connection Properties** tabs.</span></span> <span data-ttu-id="a1c57-110">Wird auf der Registerkarte **Anmeldung** beispielsweise **SERVER1** als **Servername**bereitgestellt, und enthält die Seite **Zusätzliche Verbindungsparameter** die Option **;SERVER=SERVER2**, wird die Verbindung mit **SERVER2**hergestellt.</span><span class="sxs-lookup"><span data-stu-id="a1c57-110">For example, if the **Login** tab provides **SERVER1** as the **Server name**, and the **Additional Connection Parameters** page contains **;SERVER=SERVER2**, the connection will be made to **SERVER2**.</span></span>  
  
-   <span data-ttu-id="a1c57-111">Parameter, die mithilfe der Seite **Zusätzliche Verbindungsparameter** hinzugefügt wurden, werden immer als Nur-Text übergeben.</span><span class="sxs-lookup"><span data-stu-id="a1c57-111">Parameters added using the **Additional Connection Parameters** page are always passed as plain text.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="a1c57-112">Auf der Seite **Zusätzliche Verbindungsparameter** dürfen keine Anmeldeinformationen und Kennwörter eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="a1c57-112">Do not include login credentials and passwords in the **Additional Connection Parameters** page.</span></span> <span data-ttu-id="a1c57-113">Sie werden nicht verschlüsselt, wenn sie über das Netzwerk übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="a1c57-113">They will not be encrypted when they are passed across the network.</span></span> <span data-ttu-id="a1c57-114">Verwenden Sie stattdessen die Registerkarte **Anmeldung** .</span><span class="sxs-lookup"><span data-stu-id="a1c57-114">Use the **Login** tab instead.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="a1c57-115">Aufgabenliste</span><span class="sxs-lookup"><span data-stu-id="a1c57-115">Task List</span></span>  
  
### <a name="to-show-the-additional-connection-parameters-page"></a><span data-ttu-id="a1c57-116">So zeigen Sie die Seite 'Zusätzliche Verbindungsparameter' an</span><span class="sxs-lookup"><span data-stu-id="a1c57-116">To show the Additional Connection Parameters page</span></span>  
  
1.  <span data-ttu-id="a1c57-117">Zeigen Sie in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]im Menü **Abfrage** auf **Verbindung**, und klicken Sie dann auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="a1c57-117">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], on the **Query** menu, point to **Connection**, and then click **Connect**.</span></span>  
  
2.  <span data-ttu-id="a1c57-118">Klicken Sie im Dialogfeld **Verbinden mit** auf **Optionen**, und klicken Sie dann auf die Registerkarte **Zusätzliche Verbindungsparameter** .</span><span class="sxs-lookup"><span data-stu-id="a1c57-118">In the **Connect to** dialog box, click **Options**, and then click the **Additional Connection Parameters** tab.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="a1c57-119">Beispiele</span><span class="sxs-lookup"><span data-stu-id="a1c57-119">Examples</span></span>  
  
### <a name="example-a-connecting-to-the-database-engine"></a><span data-ttu-id="a1c57-120">Beispiel A: Herstellen einer Verbindung mit der Datenbank-Engine</span><span class="sxs-lookup"><span data-stu-id="a1c57-120">Example A: Connecting to the Database Engine</span></span>  
 <span data-ttu-id="a1c57-121">Um eine Verbindung mit der [!INCLUDE[ssSampleDBnormal](../includes/sssampledbnormal-md.md)] -Datenbank auf einem Server mit dem Namen ACCOUNTING herzustellen, geben Sie auf der Seite **Zusätzliche Verbindungsparameter** Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a1c57-121">To connect to the [!INCLUDE[ssSampleDBnormal](../includes/sssampledbnormal-md.md)] database on a server named ACCOUNTING, enter the following in the **Additional connection parameters** page:</span></span>  
  
```  
;SERVER=ACCOUNTING;DATABASE=AdventureWorks2012  
```  
  
### <a name="example-b-connecting-to-analysis-services"></a><span data-ttu-id="a1c57-122">Beispiel B: Herstellen einer Verbindung mit Analysis Services</span><span class="sxs-lookup"><span data-stu-id="a1c57-122">Example B: Connecting to Analysis Services</span></span>  
 <span data-ttu-id="a1c57-123">Um eine Verbindung mit den Analysis-Servern herzustellen und zu bewirken, dass alle Partitionen, die Benachrichtigungen überwachen, in Echtzeit abgefragt werden (wobei das Caching umgangen wird), und den Timeoutwert für das Rückschreiben auf 5 festzulegen, geben Sie auf der Seite **Zusätzliche Verbindungsparameter** Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a1c57-123">To connect to the Analysis Servers and cause all the partitions listening for notifications to be queried as real time (bypassing caching), and to set the writeback time out value to 5, enter the following in the **Additional connection parameters** page:</span></span>  
  
```  
;Real Time Olap=TRUE;Writeback Timeout=5  
```  
  
  
