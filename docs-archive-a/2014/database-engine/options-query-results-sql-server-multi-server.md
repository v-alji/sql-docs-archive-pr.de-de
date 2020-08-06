---
title: Optionen (Abfrageergebnisse-SQL Server-Multiserver) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqleditors.multiserverresultssettings
- VS.ToolsOptionsPages.QueryResults.SqlServer.SQLMultiServerResults
ms.assetid: d6768bd8-9cb5-4606-a726-a33a1df9e1bb
author: rothja
ms.author: jroth
ms.openlocfilehash: 8273ad5edc65dd7351533209e9fa670c49f75f7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721726"
---
# <a name="options-query-results-sql-server-multi-server"></a><span data-ttu-id="4d517-102">Optionen (Abfrageergebnisse > SQL Server > Multiserver)</span><span class="sxs-lookup"><span data-stu-id="4d517-102">Options (Query Results-SQL Server-Multi-Server)</span></span>
  <span data-ttu-id="4d517-103">Wenn Sie mehrere Server gleichzeitig abfragen, können Sie mit dieser Seite die Optionen für die Anzeige von Resultsets angeben.</span><span class="sxs-lookup"><span data-stu-id="4d517-103">When you are querying multiple servers at the same time, use this page to specify the options for displaying result sets.</span></span> <span data-ttu-id="4d517-104">Die Option Ergebnisse zusammenführen kombiniert die Resultsets von allen Servern zu einem einzigen Resultset.</span><span class="sxs-lookup"><span data-stu-id="4d517-104">Merge results combines the result sets from all servers into a single result set.</span></span> <span data-ttu-id="4d517-105">Wenn Sie Ergebnisse zusammenführen, bestimmt der erste Server, der antwortet, das Schema für das Resultset.</span><span class="sxs-lookup"><span data-stu-id="4d517-105">When merging results, the first server to respond sets the schema for the result set.</span></span> <span data-ttu-id="4d517-106">Um die Resultsets zusammenzuführen, muss die Abfrage dieselbe Anzahl von Spalten mit denselben Spaltennamen für jeden Server zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="4d517-106">To merge the result sets, the query must return the same number of columns with the same column names from each server.</span></span> <span data-ttu-id="4d517-107">Wenn Sie Ergebnisse zusammenführen, wird eine Meldung für jeden Server angezeigt, der dem durch den ersten antwortenden Server festgelegten Schema nicht entspricht (Spaltenanzahl und Spaltennamen).</span><span class="sxs-lookup"><span data-stu-id="4d517-107">When merging results, a message is displayed for each server that does not match the schema (column count and column names) that is returned by the first server to return results.</span></span>  
  
 <span data-ttu-id="4d517-108">Wenn Sie die Ergebnisse nicht zusammenführen, wird das Resultset von jedem Server in einem eigenen Raster mit einem eigenen Schema angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4d517-108">When you do not merge results, the result set from each server will be displayed in its own grid with its own schema.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="4d517-109">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="4d517-109">UI element list</span></span>  
 <span data-ttu-id="4d517-110">**Ergebnisse zusammenführen**</span><span class="sxs-lookup"><span data-stu-id="4d517-110">**Merge results**</span></span>  
 <span data-ttu-id="4d517-111">Aktivieren Sie dieses Kontrollkästchen, um die Resultsets von mehreren Servern im selben Raster zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="4d517-111">Select this check box to combine the result sets from several servers into the same grid.</span></span>  
  
 <span data-ttu-id="4d517-112">**Servername zu den Ergebnissen hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="4d517-112">**Add server name to the results**</span></span>  
 <span data-ttu-id="4d517-113">Aktivieren Sie dieses Kontrollkästchen, um eine zusätzliche Spalte einzuschließen, die den Namen des Servers bereitstellt, der jede Zeile erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="4d517-113">Select this check box to include an additional column that provides the name of the server that produced each row.</span></span>  
  
 <span data-ttu-id="4d517-114">**Anmeldename zu den Ergebnissen hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="4d517-114">**Add login name to the results**</span></span>  
 <span data-ttu-id="4d517-115">Aktivieren Sie dieses Kontrollkästchen, um eine zusätzliche Spalte einzuschließen, die den Benutzernamen enthält, der verwendet wurde, um die Verbindung zu dem Server herzustellen, der jede Zeile bereitgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="4d517-115">Select this check box to include an additional column that provides the login that was used to connect to the server that provided each row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d517-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4d517-116">See Also</span></span>  
 <span data-ttu-id="4d517-117">[Erstellen eines zentralen Verwaltungs Servers und einer Server Gruppe &#40;SQL Server Management Studio&#41;](../ssms/register-servers/create-a-central-management-server-and-server-group.md) </span><span class="sxs-lookup"><span data-stu-id="4d517-117">[Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;](../ssms/register-servers/create-a-central-management-server-and-server-group.md) </span></span>  
 [<span data-ttu-id="4d517-118">Gleichzeitiges Ausführen von Anweisungen für mehrere Server &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="4d517-118">Execute Statements Against Multiple Servers Simultaneously &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/execute-statements-against-multiple-servers-simultaneously.md)  
  
  
