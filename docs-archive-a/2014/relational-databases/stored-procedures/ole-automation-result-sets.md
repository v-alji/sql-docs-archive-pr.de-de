---
title: OLE-Automatisierungsresultsets | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: conceptual
helpviewer_keywords:
- data types [SQL Server], OLE Automation
- two-dimensional arrays
- one-dimensional arrays
- result sets [SQL Server], OLE Automation
- OLE Automation [SQL Server], result sets
- arrays [SQL Server]
ms.assetid: b2f99e33-2303-427c-94b9-9d55f8e2a6ab
author: stevestein
ms.author: sstein
ms.openlocfilehash: f7c9bdc4d51d989db2d4d676b29e0824c0e5b59a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630623"
---
# <a name="ole-automation-result-sets"></a><span data-ttu-id="58cc0-102">OLE-Automatisierungsresultsets</span><span class="sxs-lookup"><span data-stu-id="58cc0-102">OLE Automation Result Sets</span></span>
  <span data-ttu-id="58cc0-103">Wenn eine OLE-Automatisierungseigenschaft oder -methode Daten in einem ein- oder zweidimensionalen Array zurückgibt, wird das Array als Resultset an den Client zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="58cc0-103">If an OLE Automation property or method returns data in an array with one or two dimensions, the array is returned to the client as a result set:</span></span>  
  
-   <span data-ttu-id="58cc0-104">Ein eindimensionales Array wird dem Client als einzeiliges Resultset zurückgegeben, das so viele Spalten wie Elemente im Array enthält.</span><span class="sxs-lookup"><span data-stu-id="58cc0-104">A one-dimensional array is returned to the client as a single-row result set with as many columns as there are elements in the array.</span></span> <span data-ttu-id="58cc0-105">Ein Array(10) wird z. B. als einzelne Zeile mit 10 Spalten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="58cc0-105">For example, an array(10) is returned as a single row of 10 columns.</span></span>  
  
-   <span data-ttu-id="58cc0-106">Ein zweidimensionales Array wird dem Client als Resultset zurückgegeben, dessen Anzahl an Spalten der Anzahl der Elemente in der ersten Dimension des Arrays entspricht und dessen Anzahl an Zeilen der Anzahl der Elemente in der zweiten Dimension des Arrays entspricht.</span><span class="sxs-lookup"><span data-stu-id="58cc0-106">A two-dimensional array is returned to the client as a result set with as many columns as there are elements in the first dimension of the array and with as many rows as there are elements in the second dimension of the array.</span></span> <span data-ttu-id="58cc0-107">Ein Array(2,3) wird z. B. als 2 Spalten in 3 Zeilen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="58cc0-107">For example, an array(2,3) is returned as 2 columns in 3 rows.</span></span>  
  
 <span data-ttu-id="58cc0-108">Wenn der Rückgabewert für eine Eigenschaft oder eine Methode ein Array ist, geben sp_OAGetProperty oder sp_OAMethod ein Resultset an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="58cc0-108">When a property return value or method return value is an array, sp_OAGetProperty or sp_OAMethod returns a result set to the client.</span></span> <span data-ttu-id="58cc0-109">(Ausgabeparameter für Methoden können nicht einem Array entsprechen.) Diese Prozeduren durchsuchen alle Datenwerte des Arrays, um die geeigneten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datentypen und -Datenlängen für jede Spalte des Resultsets zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="58cc0-109">(Method output parameters cannot be arrays.) These procedures scan all the data values in the array to determine the appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types and data lengths to use for each column in the result set.</span></span> <span data-ttu-id="58cc0-110">Für eine bestimmte Spalte verwenden diese Prozeduren den Datentyp und die -länge, die erforderlich sind, um alle Datenwerte in dieser Spalte darzustellen.</span><span class="sxs-lookup"><span data-stu-id="58cc0-110">For a particular column, these procedures use the data type and length required to represent all data values in that column.</span></span>  
  
 <span data-ttu-id="58cc0-111">Wenn alle Datenwerte einer Spalte denselben Datentyp aufweisen, wird dieser Datentyp für die gesamte Spalte verwendet.</span><span class="sxs-lookup"><span data-stu-id="58cc0-111">When all data values in a column share the same data type, that data type is used for the whole column.</span></span> <span data-ttu-id="58cc0-112">Wenn Datenwerte in einer Spalte aus unterschiedlichen Datentypen bestehen, wird der Datentyp für die gesamte Spalte entsprechend der folgenden Tabelle ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="58cc0-112">When data values in a column are different data types, the data type of the whole column is chosen based on the following table.</span></span> <span data-ttu-id="58cc0-113">Zum Verwenden der folgenden Tabelle wählen Sie einen Datentyp auf der Achse der linken Zeile und einen zweiten Datentyp auf der Achse der obersten Spalte aus.</span><span class="sxs-lookup"><span data-stu-id="58cc0-113">To use the following table, find one data type along the left row axis and a second data type along the top column axis.</span></span> <span data-ttu-id="58cc0-114">Der Schnittpunkt von Zeile und Spalte beschreibt den Datentyp der Resultset-Spalte.</span><span class="sxs-lookup"><span data-stu-id="58cc0-114">The intersection of the row and column describes the data type of the result set column.</span></span>  
  
||||||||  
|-|-|-|-|-|-|-|  
||`int`|`float`|`money`|`datetime`|`varchar`|`nvarchar`|  
|`int`|`int`|`float`|`money`|`varchar`|`varchar`|`nvarchar`|  
|`float`|`float`|`float`|`money`|`varchar`|`varchar`|`nvarchar`|  
|`money`|`money`|`money`|`money`|`varchar`|`varchar`|`nvarchar`|  
|`datetime`|`varchar`|`varchar`|`varchar`|`datetime`|`varchar`|`nvarchar`|  
|`varchar`|`varchar`|`varchar`|`varchar`|`varchar`|`varchar`|`nvarchar`|  
|`nvarchar`|`nvarchar`|`nvarchar`|`nvarchar`|`nvarchar`|`nvarchar`|`nvarchar`|  
  
## <a name="related-content"></a><span data-ttu-id="58cc0-115">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="58cc0-115">Related Content</span></span>  
 [<span data-ttu-id="58cc0-116">Gespeicherte OLE-Automatisierungsprozeduren &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="58cc0-116">OLE Automation Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/ole-automation-stored-procedures-transact-sql)  
  
 [<span data-ttu-id="58cc0-117">OLE-Automatisierungsprozeduren (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="58cc0-117">Ole Automation Procedures Server Configuration Option</span></span>](../../database-engine/configure-windows/ole-automation-procedures-server-configuration-option.md)  
  
  
