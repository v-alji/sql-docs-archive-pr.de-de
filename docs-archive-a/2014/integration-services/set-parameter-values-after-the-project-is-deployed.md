---
title: Festlegen von Parameter Werten nach der Bereitstellung des Projekts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: c9dcca4d-f1a0-45ec-b078-f4d372589baf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 39572594e429b61de0641c6e6929e84105138f1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726073"
---
# <a name="set-parameter-values-after-the-project-is-deployed"></a><span data-ttu-id="f2340-102">Festlegen von Parameterwerten nach der Bereitstellung des Projekts</span><span class="sxs-lookup"><span data-stu-id="f2340-102">Set Parameter Values After the Project Is Deployed</span></span>
  <span data-ttu-id="f2340-103">Mit dem Bereitstellungs-Assistenten können Sie Serverstandardparameterwerte festlegen, wenn Sie das Projekt im Katalog bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f2340-103">The Deployment Wizard allows you to set server default parameter values when you deploy your project to the catalog.</span></span> <span data-ttu-id="f2340-104">Nachdem das Projekt dem Katalog hinzugefügt worden ist, Sie können Serverstandardwerte mithilfe von SQL Server Management Studio (SSMS)-Objekt-Explorer oder Transact-SQL festlegen.</span><span class="sxs-lookup"><span data-stu-id="f2340-104">After your project is in the catalog, you can use SQL Server Management Studio (SSMS) Object Explorer or Transact-SQL to set server default values.</span></span>  
  
### <a name="to-set-server-defaults-with-ssms-object-explorer"></a><span data-ttu-id="f2340-105">So legen Sie Serverstandardwerte mit SSMS-Objekt-Explorer fest</span><span class="sxs-lookup"><span data-stu-id="f2340-105">To set server defaults with SSMS Object Explorer:</span></span>  
  
1.  <span data-ttu-id="f2340-106">Wählen Sie das Projekt unter dem Knoten **Integration Services** aus, und klicken Sie mit der rechten Maustaste darauf.</span><span class="sxs-lookup"><span data-stu-id="f2340-106">Select and right-click the project under the **Integration Services** node.</span></span>  
  
2.  <span data-ttu-id="f2340-107">Klicken Sie auf **Eigenschaften** , um das Dialogfeld **Projekteigenschaften** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f2340-107">Click **Properties** to open the **Project Properties** dialog window.</span></span>  
  
3.  <span data-ttu-id="f2340-108">Öffnen Sie die Parameterseite, indem Sie unter **Seite auswählen** auf **Parameter**klicken.</span><span class="sxs-lookup"><span data-stu-id="f2340-108">Open the parameters page by clicking **Parameters** under **Select a page**.</span></span>  
  
4.  <span data-ttu-id="f2340-109">Wählen Sie in der Liste **Parameter** den gewünschten Parameter aus.</span><span class="sxs-lookup"><span data-stu-id="f2340-109">Select the desired parameter in the **Parameters** list.</span></span> <span data-ttu-id="f2340-110">Hinweis: Anhand der Spalte **Container** können Projektparameter leichter von Paketparametern unterschieden werden.</span><span class="sxs-lookup"><span data-stu-id="f2340-110">Note: The **Container** column helps distinguish project parameters from package parameters.</span></span>  
  
5.  <span data-ttu-id="f2340-111">Geben Sie in der Spalte **Wert** den gewünschten Serverstandardparameterwert an.</span><span class="sxs-lookup"><span data-stu-id="f2340-111">In the **Value** column, specify the desired server default parameter value.</span></span>  
  
 <span data-ttu-id="f2340-112">Verwenden Sie zum Festlegen von Serverstandardwerten mit Transact-SQL die gespeicherte Prozedur [catalog.set_object_parameter_value &#40;SSISDB-Datenbank&#41;](/sql/integration-services/system-stored-procedures/catalog-set-object-parameter-value-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="f2340-112">To set server defaults with Transact-SQL, use the [catalog.set_object_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-object-parameter-value-ssisdb-database) stored procedure.</span></span> <span data-ttu-id="f2340-113">Verwenden Sie zum Anzeigen der aktuellen Serverstandards die Abfrage [catalog.object_parameters &#40;SSISDB-Datenbank&#41;](/sql/integration-services/system-views/catalog-object-parameters-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="f2340-113">To view current server defaults, query the [catalog.object_parameters &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-object-parameters-ssisdb-database) view.</span></span> <span data-ttu-id="f2340-114">Verwenden Sie zum Löschen von Serverstandardwerten die gespeicherte Prozedur [catalog.clear_object_parameter_value &#40;SSISDB-Datenbank&#41;](/sql/integration-services/system-stored-procedures/catalog-clear-object-parameter-value-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="f2340-114">To clear a server default value, use the [catalog.clear_object_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-clear-object-parameter-value-ssisdb-database) stored procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2340-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f2340-115">See Also</span></span>  
 [<span data-ttu-id="f2340-116">Integration Services &#40;SSIS-&#41; Parameter</span><span class="sxs-lookup"><span data-stu-id="f2340-116">Integration Services &#40;SSIS&#41; Parameters</span></span>](integration-services-ssis-package-and-project-parameters.md)  
  
  
