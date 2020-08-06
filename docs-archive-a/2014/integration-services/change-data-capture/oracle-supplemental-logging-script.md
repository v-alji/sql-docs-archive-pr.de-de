---
title: Ergänzendes Oracle-Protokollierungsskript | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5e6ee618-b89b-46c7-92ad-4fc5ef7b777a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0aa55e71c17574eba9e25e098a3881b0eb4c9e11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695941"
---
# <a name="oracle-supplemental-logging-script"></a><span data-ttu-id="22adb-102">Ergänzendes Oracle-Protokollierungsskript</span><span class="sxs-lookup"><span data-stu-id="22adb-102">Oracle Supplemental Logging Script</span></span>
  <span data-ttu-id="22adb-103">In diesem Dialogfeld wird das ergänzende Oracle-Protokollierungsskript angezeigt.</span><span class="sxs-lookup"><span data-stu-id="22adb-103">This dialog box shows the script the Oracle supplemental logging script.</span></span>  
  
 <span data-ttu-id="22adb-104">Wenn Sie eine CDC-Instanz für die Verwendung vorbereiten, erstellt der CDC Designer ein Oracle SQL-Skript, mit dem die ergänzende Protokollierung für die aufzuzeichnenden Tabellen eingerichtet wird.</span><span class="sxs-lookup"><span data-stu-id="22adb-104">When you prepare a CDC Instance for use, the CDC Designer creates an Oracle SQL script that sets up supplemental logging for the tables to be captured.</span></span> <span data-ttu-id="22adb-105">Das ergänzende Protokollierungsskript weist Oracle an, dass beim Aktualisieren einer bestimmten Tabelle die Änderungsdatensätze, die in das Transaktionsprotokoll geschrieben werden, die Daten aller wichtigen Spalten enthalten sollen, nicht nur die Spalten, die sich geändert haben.</span><span class="sxs-lookup"><span data-stu-id="22adb-105">The supplemental logging script tells Oracle that when a specific table is updated, the change records it writes to the transaction log should contain the data of all columns of interest, not just the columns that changed.</span></span>  
  
 <span data-ttu-id="22adb-106">Je nach den Oracle DBA-Richtlinien in Ihrer Organisation kann es erforderlich sein, dass beim Ausführen des ergänzenden Protokollierungsskripts eine Überprüfung und Genehmigung durch einen Oracle-Datenbankadministrator erfolgt.</span><span class="sxs-lookup"><span data-stu-id="22adb-106">Depending on the Oracle DBA policies in your organization, running the supplemental logging script may require a review and approval by an Oracle DBA.</span></span>  
  
## <a name="options"></a><span data-ttu-id="22adb-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="22adb-107">Options</span></span>  
 <span data-ttu-id="22adb-108">Sie können die folgenden Optionen verwenden, um festzulegen, wie das Skript ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="22adb-108">The following are the available options for how to execute the script.</span></span>  
  
 <span data-ttu-id="22adb-109">**Skript ausführen**</span><span class="sxs-lookup"><span data-stu-id="22adb-109">**Run Script**</span></span>  
 <span data-ttu-id="22adb-110">Führt das ergänzende Protokollierungsskript für die Tabellen aus, die für die CDC-Instanz definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="22adb-110">Runs the supplemental logging script on the tables defined for the CDC instance.</span></span> <span data-ttu-id="22adb-111">Zum Ausführen dieses Skripts muss der Oracle-Benutzer über die ALTER TABLE-Berechtigung für alle zu erfassenden Tabellen und die SELECT-Berechtigung für die DBA_LOG_GROUPS-Sicht verfügen.</span><span class="sxs-lookup"><span data-stu-id="22adb-111">To run this script, the Oracle user must have ALTER TABLE permission for all the tables to be captured and SELECT permission on the DBA_LOG_GROUPS view.</span></span> <span data-ttu-id="22adb-112">Außerdem muss der Oracle-Benutzer die Anmeldeinformationen für eine Oracle-Datenbankverwendung mit den erforderlichen Berechtigungen besitzen.</span><span class="sxs-lookup"><span data-stu-id="22adb-112">In addition, the Oracle user must have the credentials for an Oracle database use with the required permissions.</span></span> <span data-ttu-id="22adb-113">Sie können auf die Aufforderung des Programms zur Eingabe der Oracle-Anmeldeinformationen warten, und dann die Ausführung des Skripts folgen lassen.</span><span class="sxs-lookup"><span data-stu-id="22adb-113">You can let the program prompt you for the Oracle credentials and then have it run the script.</span></span>  
  
 <span data-ttu-id="22adb-114">**Speichern unter**</span><span class="sxs-lookup"><span data-stu-id="22adb-114">**Save As**</span></span>  
 <span data-ttu-id="22adb-115">Speichert das Skript als Textdatei.</span><span class="sxs-lookup"><span data-stu-id="22adb-115">Saves the script to a text file.</span></span> <span data-ttu-id="22adb-116">Diese Option wird verwendet, wenn ein Oracle-Datenbankadministrator das ergänzende Protokollierungsskript untersuchen und ausführen muss und wenn das Programm das Speichern des Skripts in einer Textdatei zulässt, die Sie später per E-Mail an den Oracle-Datenbankadministrator senden oder auf andere Art für die spätere Ausführung bereitstellen können (mithilfe des SQL\*Plus Oracle-Hilfsprogramms oder eines anderen Tools zum Ausführen von Skripts für eine Oracle-Datenbank).</span><span class="sxs-lookup"><span data-stu-id="22adb-116">This is used if an Oracle database administrator (DBA) needs to examine and execute the supplemental logging script, the program lets you save the script to a text file that you can later send to the Oracle DBA by email or by other means to be execute later (by using the SQL\*Plus Oracle utility or other tool for running scripts on an Oracle database).</span></span>  
  
 <span data-ttu-id="22adb-117">**Copy**</span><span class="sxs-lookup"><span data-stu-id="22adb-117">**Copy**</span></span>  
 <span data-ttu-id="22adb-118">Kopiert das Skript in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="22adb-118">Copies the script to the clipboard.</span></span> <span data-ttu-id="22adb-119">Nach Abschluss des Vorgangs können Sie das Skript an jedem erforderlichen Speicherort einfügen, falls ein Oracle-Datenbankadministrator das ergänzende Protokollierungsskript untersuchen und ausführen muss.</span><span class="sxs-lookup"><span data-stu-id="22adb-119">When ready you can paste the script in any location you need in case an Oracle database administrator (DBA) needs to examine and execute the supplemental logging script.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22adb-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="22adb-120">See Also</span></span>  
 <span data-ttu-id="22adb-121">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span><span class="sxs-lookup"><span data-stu-id="22adb-121">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span></span>  
 [<span data-ttu-id="22adb-122">Verwalten einer CDC-Instanz</span><span class="sxs-lookup"><span data-stu-id="22adb-122">Manage a CDC Instance</span></span>](manage-a-cdc-instance.md)  
  
  
