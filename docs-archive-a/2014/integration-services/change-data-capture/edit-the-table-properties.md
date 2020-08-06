---
title: Bearbeiten der Tabelleneigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- editTabProps
ms.assetid: 95ea72ba-8e40-4177-a963-0fb4d10c56e3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1ba0809b99474704ec0e93e417a04d776bb26d9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615518"
---
# <a name="edit-the-table-properties"></a><span data-ttu-id="7ad6f-102">Bearbeiten der Tabelleneigenschaften</span><span class="sxs-lookup"><span data-stu-id="7ad6f-102">Edit the Table Properties</span></span>
  <span data-ttu-id="7ad6f-103">Verwenden Sie dieses Dialogfeld, um die spezifischen Spalten der ausgewählten Tabelle zu bearbeiten, in der Änderungen aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="7ad6f-103">Use this dialog box to edit the specific columns from the selected table where changes are being captured.</span></span> <span data-ttu-id="7ad6f-104">Sie können auch die Informationen unter **Security Role** und **Capture Instance** bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="7ad6f-104">You can also edit the **Security Role** and **Capture Instance** information.</span></span>  
  
### <a name="to-edit-the-columns-to-include-in-the-cdc-instance"></a><span data-ttu-id="7ad6f-105">So bearbeiten Sie die Spalten, die in die CDC-Instanz eingeschlossen werden sollen</span><span class="sxs-lookup"><span data-stu-id="7ad6f-105">To edit the columns to include in the CDC instance</span></span>  
  
1.  <span data-ttu-id="7ad6f-106">Führen Sie einen oder beide der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="7ad6f-106">Do one or both of the following:</span></span>  
  
    -   <span data-ttu-id="7ad6f-107">Aktivieren Sie das Kontrollkästchen neben einer beliebigen zusätzlichen Spalte, die Sie einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="7ad6f-107">Select the check box next to any additional column you want to include.</span></span>  
  
    -   <span data-ttu-id="7ad6f-108">Deaktivieren Sie das Kontrollkästchen neben den Spalten, die nicht mehr enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="7ad6f-108">Clear the check box next to any column that you no longer want to include.</span></span>  
  
### <a name="to-edit-the-security-role"></a><span data-ttu-id="7ad6f-109">So bearbeiten Sie die Sicherheitsrolle</span><span class="sxs-lookup"><span data-stu-id="7ad6f-109">To edit the Security Role</span></span>  
  
1.  <span data-ttu-id="7ad6f-110">Geben Sie im Feld **Security Role** einen neuen Namen ein, oder bearbeiten Sie den Namen.</span><span class="sxs-lookup"><span data-stu-id="7ad6f-110">Type a new name or edit the name of the security role in the **Security Role** field.</span></span>  
  
### <a name="to-create-a-new-capture-instance"></a><span data-ttu-id="7ad6f-111">So erstellen Sie eine neue Aufzeichnungsinstanz</span><span class="sxs-lookup"><span data-stu-id="7ad6f-111">To create a new capture instance</span></span>  
  
1.  <span data-ttu-id="7ad6f-112">Geben Sie im Abschnitt **Security Role** im Feld **Name** einen Namen für die Aufzeichnungsinstanz ein.</span><span class="sxs-lookup"><span data-stu-id="7ad6f-112">In the **Security Role** section, **Name** field enter a name for the capture instance.</span></span> <span data-ttu-id="7ad6f-113">Standardmäßig entspricht der Name im Feld dem Namen der aktuellen Aufzeichnungsinstanz mit dem Zusatz **_NEW** (z.B. **alte_instanz_NEW**).</span><span class="sxs-lookup"><span data-stu-id="7ad6f-113">By default, the name entered in the field is the name of the current capture instance with **_NEW** added to the end of the name (for example, **old_instance_NEW**).</span></span>  
  
2.  <span data-ttu-id="7ad6f-114">Speichern Sie die Aufzeichnungsinstanz wie folgt:</span><span class="sxs-lookup"><span data-stu-id="7ad6f-114">Save the capture instance as one of the following:</span></span>  
  
    -   <span data-ttu-id="7ad6f-115">**New Capture Instance**: In diesem Fall wird eine neue Aufzeichnungsinstanz gespeichert und die alte Aufzeichnungsinstanz nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="7ad6f-115">**New Capture Instance**: In this case a new capture instance is saved and the old capture instance is not deleted.</span></span>  
  
         <span data-ttu-id="7ad6f-116">**Hinweis**: Sie können pro Tabelle nicht mehr als zwei Aufzeichnungsinstanzen verwenden.</span><span class="sxs-lookup"><span data-stu-id="7ad6f-116">**Note**: You can have no more than two capture instances per table.</span></span> <span data-ttu-id="7ad6f-117">Falls bereits zwei Aufzeichnungsinstanzen vorhanden sind, ist diese Option nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7ad6f-117">If there are already two capture instances, this option is not available.</span></span>  
  
    -   <span data-ttu-id="7ad6f-118">**Replace Existing**: In diesem Fall wird die aktuelle Aufzeichnungsinstanz gelöscht und durch die erstellte Aufzeichnungsinstanz ersetzt.</span><span class="sxs-lookup"><span data-stu-id="7ad6f-118">**Replace Existing**: In this case the current capture instance is deleted and replaced by the capture instance you created.</span></span> <span data-ttu-id="7ad6f-119">Wenn für die Tabelle zwei Aufzeichnungsinstanzen definiert sind, müssen Sie eine Instanz auswählen, die ersetzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7ad6f-119">If there are two capture instances defined for this table, you must select one to replace.</span></span>  
  
 <span data-ttu-id="7ad6f-120">**Hinweis**: Sie können eine Aufzeichnungsinstanz aus der Liste der Tabellen auf der Registerkarte **Tabelle** entfernen.</span><span class="sxs-lookup"><span data-stu-id="7ad6f-120">**Note**: You can remove a capture instance from the list of tables in the **Table** tab.</span></span>  
  
 <span data-ttu-id="7ad6f-121">Klicken Sie auf **OK** , nachdem Sie die Informationen in diesem Dialogfeld eingegeben haben, um die Änderungen zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="7ad6f-121">After you finish entering the information in this dialog box, click **OK** to accept the changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ad6f-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7ad6f-122">See Also</span></span>  
 <span data-ttu-id="7ad6f-123">[Bearbeiten der CDC-Instanzeigenschaften](how-to-edit-the-cdc-instance-properties.md) </span><span class="sxs-lookup"><span data-stu-id="7ad6f-123">[How to Edit the CDC Instance Properties](how-to-edit-the-cdc-instance-properties.md) </span></span>  
 [<span data-ttu-id="7ad6f-124">Vornehmen von Änderungen an den zum Aufzeichnen von Änderungen ausgewählten Tabellen</span><span class="sxs-lookup"><span data-stu-id="7ad6f-124">Make Changes to the Tables Selected for Capturing Changes</span></span>](make-changes-to-the-tables-selected-for-capturing-changes.md)  
  
  
