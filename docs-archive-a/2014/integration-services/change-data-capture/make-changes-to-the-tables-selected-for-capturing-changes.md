---
title: Vornehmen von Änderungen an den zum Aufzeichnen von Änderungen ausgewählten Tabellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- makChanToTab
ms.assetid: a309f82a-c6ef-464d-a6ef-df555bfb609a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 258eb8e761ac697bebd630cc0e627941b4ffc7d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615513"
---
# <a name="make-changes-to-the-tables-selected-for-capturing-changes"></a><span data-ttu-id="edf41-102">Vornehmen von Änderungen an den zum Aufzeichnen von Änderungen ausgewählten Tabellen</span><span class="sxs-lookup"><span data-stu-id="edf41-102">Make Changes to the Tables Selected for Capturing Changes</span></span>
  <span data-ttu-id="edf41-103">In diesem Dialogfeld können Sie bestimmte Spalten aus der ausgewählten Tabelle auswählen, um dafür Änderungen aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="edf41-103">In this dialog box, you can select specific columns from the selected table to capture changes from.</span></span> <span data-ttu-id="edf41-104">Sie können auch die Informationen unter **Security Role** und **Capture Instance** bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="edf41-104">You can also edit the **Security Role** and **Capture Instance** information.</span></span>  
  
 <span data-ttu-id="edf41-105">In den Tabellen, die Sie in diesem Dialogfeld für die Aufzeichnung von Änderungen ausgewählt haben, können Sie die folgenden Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="edf41-105">You can make the following changes to the tables you selected for capturing changes in this dialog box.</span></span>  
  
 <span data-ttu-id="edf41-106">**Ändern Sie, welche Spalten in die CDC-Instanz eingeschlossen sind:**</span><span class="sxs-lookup"><span data-stu-id="edf41-106">**Make changes to which columns are included in the CDC instance:**</span></span>  
  
 <span data-ttu-id="edf41-107">Führen Sie einen oder beide der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="edf41-107">Do one or both of the following:</span></span>  
  
-   <span data-ttu-id="edf41-108">Aktivieren Sie das Kontrollkästchen neben einer beliebigen zusätzlichen Spalte, die Sie einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="edf41-108">Select the check box next to any additional column you want to include.</span></span>  
  
-   <span data-ttu-id="edf41-109">Deaktivieren Sie das Kontrollkästchen neben den Spalten, die nicht mehr enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="edf41-109">Clear the check box next to any column that you no longer want to include.</span></span>  
  
 <span data-ttu-id="edf41-110">**Ändern Sie den Datentyp für eine bestimmte Spalte**:</span><span class="sxs-lookup"><span data-stu-id="edf41-110">**Change the data type for a specific column**:</span></span>  
  
 <span data-ttu-id="edf41-111">Sie können einen anderen Datentyp für eine bestimmte Spalte auswählen.</span><span class="sxs-lookup"><span data-stu-id="edf41-111">You can select a different data type for a specific column.</span></span> <span data-ttu-id="edf41-112">Der Datentyp kann jedoch nur in einen Datentyp geändert werden, der mit dem ursprünglichen Datentyp kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="edf41-112">You can only change the data type to a data type that is compatible with the original data type.</span></span>  
  
 <span data-ttu-id="edf41-113">Klicken Sie zum Ändern des Datentyps in die Spalte **Datentyp** , und wählen Sie einen anderen Datentyp aus.</span><span class="sxs-lookup"><span data-stu-id="edf41-113">To change the data type, click in the **Data Type** column and select a different data type.</span></span> <span data-ttu-id="edf41-114">Es sind nur Datentypen verfügbar, die mit dem ursprünglichen Datentyp kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="edf41-114">Only data types that are compatible with the original data type are available.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="edf41-115">Wenn keine zusätzlichen Datentypen ausgewählt werden können, ist die Dropdownliste nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="edf41-115">If no additional data types can be selected, the drop-down list is not available.</span></span>  
  
 <span data-ttu-id="edf41-116">**Ändern der Sicherheitsrolle**</span><span class="sxs-lookup"><span data-stu-id="edf41-116">**Change the Security Role**</span></span>  
  
 <span data-ttu-id="edf41-117">Geben Sie im Feld **Security Role** einen neuen Namen ein, oder bearbeiten Sie den Namen der Sicherheitsgatingrolle.</span><span class="sxs-lookup"><span data-stu-id="edf41-117">Type a new name or edit the name of the security gating role in the **Security Role** field.</span></span>  
  
 <span data-ttu-id="edf41-118">**Ändern oder Hinzufügen einer Aufzeichnungsinstanz**</span><span class="sxs-lookup"><span data-stu-id="edf41-118">**Change or add a capture instance**</span></span>  
  
 <span data-ttu-id="edf41-119">Geben Sie im Feld **Capture Instance** einen Namen für die Aufzeichnungsinstanz ein.</span><span class="sxs-lookup"><span data-stu-id="edf41-119">In the **Capture Instance** field enter a name for the capture instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edf41-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="edf41-120">See Also</span></span>  
 <span data-ttu-id="edf41-121">[Erstellen der Instanz für die SQL Server-Änderungsdatenbank](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="edf41-121">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="edf41-122">Auswählen von Oracle-Tabellen und -Spalten</span><span class="sxs-lookup"><span data-stu-id="edf41-122">Select Oracle Tables and Columns</span></span>](select-oracle-tables-and-columns.md)  
  
  
