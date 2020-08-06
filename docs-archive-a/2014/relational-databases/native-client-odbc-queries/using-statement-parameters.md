---
title: Verwenden von Anweisungs Parametern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, parameters
- parameters [SQL Server Native Client], ODBC
- ODBC, parameters
- statements [ODBC], parameters
- parameter markers [ODBC]
- SQL Server Native Client ODBC driver, statements
- ODBC applications, statements
ms.assetid: 2427d886-ec6c-49d7-b0b6-0d998b64cdb9
author: rothja
ms.author: jroth
ms.openlocfilehash: 7b7e207416e60af94efd59555980a0edff68a38b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608599"
---
# <a name="using-statement-parameters"></a><span data-ttu-id="b90d0-102">Verwenden von Anweisungsparametern</span><span class="sxs-lookup"><span data-stu-id="b90d0-102">Using Statement Parameters</span></span>
  <span data-ttu-id="b90d0-103">Ein Parameter ist eine Variable in einer SQL-Anweisung, die eine ODBC-Anwendung für folgende Vorgänge aktivieren kann:</span><span class="sxs-lookup"><span data-stu-id="b90d0-103">A parameter is a variable in an SQL statement that can enable an ODBC application to:</span></span>  
  
-   <span data-ttu-id="b90d0-104">Werte für Spalten in einer Tabelle effizient bereitstellen</span><span class="sxs-lookup"><span data-stu-id="b90d0-104">Efficiently provide values for columns in a table.</span></span>  
  
-   <span data-ttu-id="b90d0-105">Benutzerinteraktion beim Aufstellen von Abfragekriterien verbessern</span><span class="sxs-lookup"><span data-stu-id="b90d0-105">Enhance user interaction in constructing query criteria.</span></span>  
  
-   <span data-ttu-id="b90d0-106">Verwalten von **Text**-, **ntext**-und **Image** -Daten und [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -spezifischen C-Datentypen.</span><span class="sxs-lookup"><span data-stu-id="b90d0-106">Manage **text**, **ntext**, and **image** data and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific C data types.</span></span>  
  
 <span data-ttu-id="b90d0-107">Beispielsweise enthält eine **Teile** Tabelle Spalten mit dem Namen " **partid**", " **Description**" und " **Price**".</span><span class="sxs-lookup"><span data-stu-id="b90d0-107">For example, a **Parts** table has columns named **PartID**, **Description**, and **Price**.</span></span> <span data-ttu-id="b90d0-108">Um ein Teil ohne Parameter hinzuzufügen, ist eine SQL-Anweisung erforderlich. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b90d0-108">To add a part without parameters requires constructing an SQL statement such as:</span></span>  
  
```  
INSERT INTO Parts (PartID, Description, Price) VALUES (2100, 'Drive shaft', 50.00)  
```  
  
 <span data-ttu-id="b90d0-109">Diese Anweisung ist zwar zum Einfügen einer Zeile in eine bekannte Menge von Werten akzeptabel, sie ist jedoch umständlich, wenn die Anwendung mehrere Zeilen einfügen muss.</span><span class="sxs-lookup"><span data-stu-id="b90d0-109">Although this statement is acceptable for inserting one row with a known set of values, it is awkward when an application is required to insert several rows.</span></span> <span data-ttu-id="b90d0-110">ODBC löst dieses Problem, indem eine Anwendung jeden Datenwert in einer SQL-Anweisung durch eine Parametermarkierung ersetzen kann.</span><span class="sxs-lookup"><span data-stu-id="b90d0-110">ODBC addresses this by letting an application to replace any data value in an SQL statement by a parameter maker.</span></span> <span data-ttu-id="b90d0-111">Diese wird durch ein Fragezeichen (?) angegeben.</span><span class="sxs-lookup"><span data-stu-id="b90d0-111">This is denoted by a question mark (?).</span></span> <span data-ttu-id="b90d0-112">Im folgenden Beispiel werden drei Datenwerte durch Parametermarkierungen ersetzt:</span><span class="sxs-lookup"><span data-stu-id="b90d0-112">In the following example, three data values are replaced with parameter markers:</span></span>  
  
```  
INSERT INTO Parts (PartID, Description, Price) VALUES (?, ?, ?)  
```  
  
 <span data-ttu-id="b90d0-113">Die Parametermarkierungen werden dann an Anwendungsvariablen gebunden.</span><span class="sxs-lookup"><span data-stu-id="b90d0-113">The parameter markers are then bound to application variables.</span></span> <span data-ttu-id="b90d0-114">Um eine neue Zeile einzufügen, muss die Anwendung nur die Werte der Variablen festlegen und die Anweisung ausführen.</span><span class="sxs-lookup"><span data-stu-id="b90d0-114">To insert a new row, the application has only to set the values of the variables and execute the statement.</span></span> <span data-ttu-id="b90d0-115">Der Treiber ruft dann die aktuellen Werte der Variablen ab und sendet sie an die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="b90d0-115">The driver then retrieves the current values of the variables and sends them to the data source.</span></span> <span data-ttu-id="b90d0-116">Wenn die Anweisung mehrfach ausgeführt wird, kann die Anwendung den Prozess durch Vorbereiten der Anweisung noch effizienter gestalten.</span><span class="sxs-lookup"><span data-stu-id="b90d0-116">If the statement is executed multiple times, the application can make the process even more efficient by preparing the statement.</span></span>  
  
 <span data-ttu-id="b90d0-117">Auf jede Parametermarkierung wird durch die entsprechende Ordnungszahl, die den Parametern von links nach rechts zugewiesen wurde, verwiesen.</span><span class="sxs-lookup"><span data-stu-id="b90d0-117">Each parameter marker is referenced by its ordinal number assigned to the parameters from left to right.</span></span> <span data-ttu-id="b90d0-118">Die äußere linke Parametermarkierung in einer SQL-Anweisung besitzt den Ordnungswert 1, die nächste Markierung den Wert 2 usw.</span><span class="sxs-lookup"><span data-stu-id="b90d0-118">The leftmost parameter marker in an SQL statement has an ordinal value of 1; the next one is ordinal 2, and so on.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b90d0-119">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b90d0-119">In This Section</span></span>  
  
-   [<span data-ttu-id="b90d0-120">Binden von Parametern</span><span class="sxs-lookup"><span data-stu-id="b90d0-120">Binding Parameters</span></span>](using-statement-parameters-binding-parameters.md)  
  
## <a name="see-also"></a><span data-ttu-id="b90d0-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b90d0-121">See Also</span></span>  
 [<span data-ttu-id="b90d0-122">Ausführen von Abfragen &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="b90d0-122">Executing Queries &#40;ODBC&#41;</span></span>](executing-queries-odbc.md)  
  
  
