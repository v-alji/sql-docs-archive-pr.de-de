---
title: Konfigurieren von in-Memory-oder directquery-Zugriff für eine tabellarische Modelldatenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a5d439a9-5be1-4145-90e8-90777d80e98b
author: minewiskan
ms.author: owend
ms.openlocfilehash: a607bc6c11f35736487932bdf10d239afc8b5355
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696201"
---
# <a name="configure-in-memory-or-directquery-access-for-a-tabular-model-database"></a><span data-ttu-id="28315-102">Konfigurieren von speicherinternem oder DirectQuery-Zugriff für eine tabellarische Modelldatenbank</span><span class="sxs-lookup"><span data-stu-id="28315-102">Configure In-Memory or DirectQuery Access for a Tabular Model Database</span></span>
  <span data-ttu-id="28315-103">In diesem Thema wird beschrieben, wie die Verbindungseigenschaften eines bereits bereitgestellten tabellarischen Modells geändert werden, um die Verwendung des Modells im DirectQuery-Modus zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="28315-103">This topic describes how to change the connection properties of a tabular model that has already been deployed, to enable use of the model in Direct Query mode.</span></span>  
  
 <span data-ttu-id="28315-104">Weitere Informationen zu diesen Eigenschaften und zur Konfiguration für die gängigsten Szenarien finden Sie unter [directquery-Bereitstellungs Szenarien &#40;tabellarischen SSAS-&#41;](../directquery-deployment-scenarios-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="28315-104">For more information about these properties, and configuration for the most common scenarios, see [DirectQuery Deployment Scenarios &#40;SSAS Tabular&#41;](../directquery-deployment-scenarios-ssas-tabular.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28315-105">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="28315-105">Requirements</span></span>  
 <span data-ttu-id="28315-106">Es sind mehrere Schritte nötig, um den DirectQuery-Modus auf ein tabellarisches Modell anwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="28315-106">Enabling the use of Direct Query mode on a tabular model is a multistep process.</span></span> <span data-ttu-id="28315-107">Die Voraussetzungen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="28315-107">You must:</span></span>  
  
1.  <span data-ttu-id="28315-108">Stellen Sie sicher, dass das Modell keine Funktionen hat, die möglicherweise Überprüfungsfehler im DirectQuery-Modus verursachen.</span><span class="sxs-lookup"><span data-stu-id="28315-108">Ensure that the model does not have features which might cause validation errors in Direct Query mode.</span></span>  
  
2.  <span data-ttu-id="28315-109">Ändern Sie den Speichermodus für das Modell, um DirectQuery zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="28315-109">Change the storage mode on the model to support Direct Query.</span></span>  
  
3.  <span data-ttu-id="28315-110">Stellen Sie das Modell in einem Modus bereit, in dem Abfragen in entweder einem hybriden oder reinen DirectQuery-Modus unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="28315-110">Deploy the model in a mode that supports queries in either a hybrid or pure Direct Query mode.</span></span>  
  
4.  <span data-ttu-id="28315-111">Bearbeiten Sie die Verbindungszeichenfolge in der bereitgestellten Datenbank, um den DirectQuery-Modus zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="28315-111">Edit the connection string on the deployed database to support Direct Query mode.</span></span>  
  
 <span data-ttu-id="28315-112">In diesem Thema wird davon ausgegangen, dass Sie das Modell erstellt und überprüft haben und den DirectQuery-Zugriff nur noch von einem Client (beispielsweise [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)]) aktivieren müssen.</span><span class="sxs-lookup"><span data-stu-id="28315-112">This topic assumes that you have created and validated your model, and only need to enable Direct Query access from a client such as [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="28315-113">Verfahren</span><span class="sxs-lookup"><span data-stu-id="28315-113">Procedure</span></span>  
  
#### <a name="change-the-connection-string-properties-of-the-model"></a><span data-ttu-id="28315-114">Ändern der Verbindungszeichenfolgen-Eigenschaften eines Modells</span><span class="sxs-lookup"><span data-stu-id="28315-114">Change the Connection String Properties of the Model</span></span>  
  
1.  <span data-ttu-id="28315-115">Öffnen Sie in SQL Server Management Studio die Instanz, für die Sie das Modell bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="28315-115">In SQL Server Management Studio, open the instance to which you deployed the model.</span></span>  
  
2.  <span data-ttu-id="28315-116">Klicken Sie in Objekt-Explorer mit der rechten Maustaste auf den Namen der Model-Datenbank, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="28315-116">In Object Explorer, right-click the name of the model database, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="28315-117">Suchen Sie die Eigenschaft **directquerymode**.</span><span class="sxs-lookup"><span data-stu-id="28315-117">Locate the property, **DirectQueryMode**.</span></span> <span data-ttu-id="28315-118">Diese Eigenschaft muss auf einen dieser Werte festgelegt werden, um die Verwendung der relationalen Datenquelle zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="28315-118">To enable use of the relational data source, this property must be set to one of these values:</span></span>  
  
    -   <span data-ttu-id="28315-119">**DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="28315-119">**DirectQuery**</span></span>  
  
    -   <span data-ttu-id="28315-120">**InMemoryWithDirectQuery**</span><span class="sxs-lookup"><span data-stu-id="28315-120">**InMemoryWithDirectQuery**</span></span>  
  
    -   <span data-ttu-id="28315-121">**DirectQueryWithInMemory**</span><span class="sxs-lookup"><span data-stu-id="28315-121">**DirectQueryWithInMemory**</span></span>  
  
  
