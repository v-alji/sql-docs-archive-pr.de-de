---
title: Objekte löschen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.deleteobjects.f1
helpviewer_keywords:
- Delete Objects dialog box
ms.assetid: 49541441-179c-40d3-ba0c-01bcae545984
author: stevestein
ms.author: sstein
ms.openlocfilehash: e7b20d1eee3e48c5531b6b788e125b943f7606d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607520"
---
# <a name="delete-objects"></a><span data-ttu-id="7743d-102">Objekte löschen</span><span class="sxs-lookup"><span data-stu-id="7743d-102">Delete Objects</span></span>
  <span data-ttu-id="7743d-103">In diesem Dialogfeld können Sie eine Datenbank oder ein Datenbankobjekt löschen.</span><span class="sxs-lookup"><span data-stu-id="7743d-103">Use this dialog box to delete a database or database object.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="7743d-104">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="7743d-104">UI element list</span></span>  
 <span data-ttu-id="7743d-105">**Zu löschendes Objekt**</span><span class="sxs-lookup"><span data-stu-id="7743d-105">**Object to be deleted**</span></span>  
 <span data-ttu-id="7743d-106">Zeigt die Namen, Typen, Besitzer und den Status von zu löschenden Objekten sowie Fehlermeldungen während der Ausführung an.</span><span class="sxs-lookup"><span data-stu-id="7743d-106">Displays the names, types, owners, and status of the objects that are about to be deleted, as well as any messages about errors during execution.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7743d-107">Das Ausführen von **Löschen** für eine Datenbank entspricht der Verwendung von DROP DATABASE in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7743d-107">Running **Delete** on a database is equivalent to issuing DROP DATABASE in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="7743d-108">**Abhängigkeiten anzeigen**</span><span class="sxs-lookup"><span data-stu-id="7743d-108">**Show Dependencies**</span></span>  
 <span data-ttu-id="7743d-109">Klicken Sie hier, um sowohl die vom gerade ausgewählten Objekt abhängigen Objekte als auch die Objekte anzuzeigen, von denen das aktuelle Objekt abhängt (Aufwärts- und Abwärtsabhängigkeit).</span><span class="sxs-lookup"><span data-stu-id="7743d-109">Click to display both the objects that are dependent on the currently selected object and objects that the current object is dependent on (upward and downward dependency).</span></span> <span data-ttu-id="7743d-110">Die im Dialogfeld **Abhängigkeiten anzeigen** angezeigten Informationen sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="7743d-110">The information displayed in the **Show Dependencies** dialog box is read-only.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7743d-111">Die Schaltfläche **Abhängigkeiten anzeigen** wird nicht für alle Datenbankobjekttypen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7743d-111">The **Show Dependencies** button does not appear for all types of database objects.</span></span> <span data-ttu-id="7743d-112">Wenn Sie die Abhängigkeiten anzeigen möchten und die Schaltfläche **Abhängigkeiten anzeigen** nicht verfügbar ist, klicken Sie im Objekt-Explorer mit der rechten Maustaste auf das Objekt, und klicken Sie dann auf **Abhängigkeiten anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="7743d-112">To view dependencies when the **Show Dependencies** button is not available, right-click the object in Object Explorer, and then click **View Dependencies**.</span></span>  
  
 <span data-ttu-id="7743d-113">**Sicherungs- und Wiederherstellungsverlaufsinformationen für Datenbanken löschen**</span><span class="sxs-lookup"><span data-stu-id="7743d-113">**Delete backup and restore history information for databases**</span></span>  
 <span data-ttu-id="7743d-114">Wird nur angezeigt, wenn eine Datenbank gelöscht wird. Bei Aktivierung dieses Kontrollkästchens wird der Sicherungs- und Wiederherstellungsverlauf für die betroffene Datenbank aus der **msdb** -Datenbank gelöscht.</span><span class="sxs-lookup"><span data-stu-id="7743d-114">Only appears when a database is deleted, this check box causes the backup and restore history for the subject database to be deleted from the **msdb** database.</span></span>  
  
 <span data-ttu-id="7743d-115">**Bestehende Verbindungen schließen**</span><span class="sxs-lookup"><span data-stu-id="7743d-115">**Close existing connections**</span></span>  
 <span data-ttu-id="7743d-116">Wird nur angezeigt, wenn eine Datenbank gelöscht wird. Bei Aktivierung dieses Kontrollkästchens werden die Verbindungen zur betreffenden Datenbank beendet.</span><span class="sxs-lookup"><span data-stu-id="7743d-116">Only appears when a database is deleted, this check box terminates connections to the subject database.</span></span>  
  
  
