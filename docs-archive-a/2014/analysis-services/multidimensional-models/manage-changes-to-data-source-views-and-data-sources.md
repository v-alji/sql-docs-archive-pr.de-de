---
title: Verwalten von Änderungen an Datenquellen Sichten und Datenquellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying data sources
- modifying data source views
- data source views [Analysis Services], schema updates
- data sources [Analysis Services], schema updates
ms.assetid: 928c9f63-365a-43fd-9bbd-78828cc7e54d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0f558ce6aaf9e57576d5773322352d33b81a3392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698642"
---
# <a name="manage-changes-to-data-source-views-and-data-sources"></a><span data-ttu-id="5ac66-102">Verwalten von Änderungen an Datenquellensichten und Datenquellen</span><span class="sxs-lookup"><span data-stu-id="5ac66-102">Manage Changes to Data Source Views and Data Sources</span></span>
  <span data-ttu-id="5ac66-103">Wird der Schemagenerierungs-Assistent erneut ausgeführt, verwendet er dieselbe Datenquelle und Datenquellensicht wie für die ursprüngliche Generierung.</span><span class="sxs-lookup"><span data-stu-id="5ac66-103">When the Schema Generation Wizard is rerun, it reuses the same data source and data source view that it used for the original generation.</span></span> <span data-ttu-id="5ac66-104">Wenn Sie eine Datenquelle oder Datenquellensicht hinzufügen, wird diese vom Assistenten nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="5ac66-104">If you add a data source or a data source view, the wizard does not use it.</span></span> <span data-ttu-id="5ac66-105">Wenn Sie die ursprüngliche Datenquelle oder Datenquellensicht nach der Anfangsgenerierung löschen, müssen Sie den Assistenten von Anfang an ausführen.</span><span class="sxs-lookup"><span data-stu-id="5ac66-105">If you delete the original data source or data source view after the initial generation, you must run the wizard from the beginning.</span></span> <span data-ttu-id="5ac66-106">Alle bisherigen Einstellungen im Assistenten werden ebenfalls gelöscht.</span><span class="sxs-lookup"><span data-stu-id="5ac66-106">All previous settings in the wizard are also deleted.</span></span> <span data-ttu-id="5ac66-107">Alle vorhandenen Objekte in einer zugrunde liegenden Datenbank, die mit einer gelöschten Datenquelle oder Datenquellensicht verbunden waren, werden bei dem nächsten Ausführen des Schemagenerierungs-Assistenten als vom Benutzer erstellte Objekte behandelt.</span><span class="sxs-lookup"><span data-stu-id="5ac66-107">Any existing objects in an underlying database that were bound to a deleted data source or data source view are treated as user-created objects the next time you run the Schema Generation Wizard.</span></span>  
  
 <span data-ttu-id="5ac66-108">Gibt die Datenquellensicht nicht den tatsächlichen Status der zugrunde liegenden Datenbank zum Zeitpunkt der Generierung wieder, ist es möglich, dass bei der Generierung des Schemas für die Themenbereichsdatenbank durch den Schemagenerierungs-Assistenten Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="5ac66-108">If the data source view does not reflect the actual state of the underlying database at the time of generation, the Schema Generation Wizard may encounter errors when it generates the schema for the subject area database.</span></span> <span data-ttu-id="5ac66-109">Wenn die Datenquellensicht beispielsweise angibt, dass der Datentyp einer Spalte **int**ist, der Datentyp der Spalte tatsächlich aber auf **string**festgelegt wurde, legt der Schemagenerierungs-Assistent den Datentyp für den Fremdschlüssel in Übereinstimmung mit der Datenquellensicht auf **INT** fest und erzeugt dann beim Erstellen der Beziehung einen Fehler, da der tatsächliche Datentyp **string**ist.</span><span class="sxs-lookup"><span data-stu-id="5ac66-109">For example, if the data source view specifies that the data type for a column is **int**, but data type for the column is actually **string**, the Schema Generation Wizard sets the data type for the foreign key to **INT** to match the data source view and then fails when it creates the relationship because the actual type is **string**.</span></span>  
  
 <span data-ttu-id="5ac66-110">Wenn Sie allerdings die Datenquellen-Verbindungszeichenfolge auf eine andere Datenbank aus der vorherigen Generierung ändern, wird kein Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="5ac66-110">On the other hand, if you change the data source connection string to a different database from the previous generation, no error is generated.</span></span> <span data-ttu-id="5ac66-111">Es wird die neue Datenbank verwendet und keine Änderung an der vorherigen Datenbank vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="5ac66-111">The new database is used, and no change is made to the previous database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ac66-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ac66-112">See Also</span></span>  
 [<span data-ttu-id="5ac66-113">Grundlegendes zur inkrementellen Generierung</span><span class="sxs-lookup"><span data-stu-id="5ac66-113">Understanding Incremental Generation</span></span>](understanding-incremental-generation.md)  
  
  
