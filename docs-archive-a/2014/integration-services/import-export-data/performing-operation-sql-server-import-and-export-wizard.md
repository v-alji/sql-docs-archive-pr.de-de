---
title: Vorgang wird ausgeführt (SQL Server-Import/Export-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.performingoperation.f1
ms.assetid: 83259509-71d6-4a64-a7f2-4e9603b30bd4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b6cdac605da2288149909a3fb6e9f245e10eebf8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619934"
---
# <a name="performing-operation-sql-server-import-and-export-wizard"></a><span data-ttu-id="a4954-102">Vorgang wird ausgeführt (SQL Server-Import/Export-Assistent)</span><span class="sxs-lookup"><span data-stu-id="a4954-102">Performing Operation (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="a4954-103">Auf der Seite **Vorgang wird ausgeführt** können Sie den Fortschritt und die Ergebnisse des Import- bzw. Exportvorgangs anzeigen und den Vorgang ggf. unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="a4954-103">Use the **Performing Operation** page to view the progress and the results of the import/export operation, and to interrupt the operation if necessary.</span></span>  
  
 <span data-ttu-id="a4954-104">Weitere Informationen zu diesem Assistenten finden Sie unter [SQL Server-Import/Export-Assistenten](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="a4954-104">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="a4954-105">Weitere Informationen zu den Optionen für das Starten des Assistenten sowie zu den Berechtigungen, die zum erfolgreichen Ausführen des Assistenten erforderlich sind, finden Sie unter [Ausführen des SQL Server-Import/Export-Assistenten](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="a4954-105">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="a4954-106">Mit dem SQL Server-Import/Export-Assistenten werden Daten aus einer Quelle in ein Ziel kopiert.</span><span class="sxs-lookup"><span data-stu-id="a4954-106">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="a4954-107">Mit dem Assistenten können auch eine Zieldatenbank und Zieltabellen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a4954-107">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="a4954-108">Wenn Sie jedoch mehrere Datenbanken, Tabellen oder andere Datenbankobjekte kopieren müssen, verwenden Sie stattdessen den Assistenten zum Kopieren von Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="a4954-108">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="a4954-109">Weitere Informationen finden Sie unter [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="a4954-109">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a4954-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="a4954-110">Options</span></span>  
 <span data-ttu-id="a4954-111">**Aktion**</span><span class="sxs-lookup"><span data-stu-id="a4954-111">**Action**</span></span>  
 <span data-ttu-id="a4954-112">Zeigt alle Aktionen an, die Teil des Vorgangs sind.</span><span class="sxs-lookup"><span data-stu-id="a4954-112">Displays each action that is part of the operation.</span></span>  
  
 <span data-ttu-id="a4954-113">**Status**</span><span class="sxs-lookup"><span data-stu-id="a4954-113">**Status**</span></span>  
 <span data-ttu-id="a4954-114">Zeigt an, ob die einzelnen Aktionen erfolgreich ausgeführt wurden oder fehlerhaft sind.</span><span class="sxs-lookup"><span data-stu-id="a4954-114">Displays the success or failure of each action.</span></span>  
  
 <span data-ttu-id="a4954-115">**Meldung**</span><span class="sxs-lookup"><span data-stu-id="a4954-115">**Message**</span></span>  
 <span data-ttu-id="a4954-116">Zeigt ggf. durch die Aktion generierte Informations- oder Fehlermeldungen an.</span><span class="sxs-lookup"><span data-stu-id="a4954-116">Displays informational and error messages that the action might generate.</span></span>  
  
 <span data-ttu-id="a4954-117">**Filter**</span><span class="sxs-lookup"><span data-stu-id="a4954-117">**Filter**</span></span>  
 <span data-ttu-id="a4954-118">Wählen Sie aus, ob nur Fehler, Warnungen oder erfolgreiche Aktionen angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a4954-118">Choose whether you want to display only errors, warnings, or successful actions.</span></span> <span data-ttu-id="a4954-119">Wenn Sie **Alle Aktionen anzeigen**auswählen, können Sie die Einstellung auf die Standardanzeige zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="a4954-119">You can revert to the default display by choosing **Show All Actions**.</span></span>  
  
 <span data-ttu-id="a4954-120">**Beenden**</span><span class="sxs-lookup"><span data-stu-id="a4954-120">**Stop**</span></span>  
 <span data-ttu-id="a4954-121">Mit der Schaltfläche **Beenden** können Sie den Vorgang ggf. unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="a4954-121">Interrupt the operation, if necessary, by using the **Stop** button.</span></span>  
  
 <span data-ttu-id="a4954-122">**Report**</span><span class="sxs-lookup"><span data-stu-id="a4954-122">**Report**</span></span>  
 <span data-ttu-id="a4954-123">Mit dieser Option können Sie einen Bericht mit den Ergebnissen anzeigen, den Bericht in einer Datei speichern, den Bericht in die Zwischenablage kopieren oder den Bericht per E-Mail versenden.</span><span class="sxs-lookup"><span data-stu-id="a4954-123">View a report of the results, save the report to a file, copy the report to the clipboard, or send the report by e-mail.</span></span>  
  
  
