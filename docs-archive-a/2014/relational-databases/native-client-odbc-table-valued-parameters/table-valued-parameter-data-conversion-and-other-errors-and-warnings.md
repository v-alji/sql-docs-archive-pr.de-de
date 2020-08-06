---
title: Tabellenwert Parameter-Datenkonvertierung und andere Fehler und Warnungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC), data conversion
- table-valued parameters (ODBC), error messages
ms.assetid: edd45234-59dc-4338-94fc-330e820cc248
author: rothja
ms.author: jroth
ms.openlocfilehash: 45b9ba7f91b54548e096bbe47da6e01ba562f59d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608597"
---
# <a name="table-valued-parameter-data-conversion-and-other-errors-and-warnings"></a><span data-ttu-id="52022-102">Tabellenwertparameter-Datenkonvertierung und andere Fehler und Warnungen</span><span class="sxs-lookup"><span data-stu-id="52022-102">Table-Valued Parameter Data Conversion and Other Errors and Warnings</span></span>
  <span data-ttu-id="52022-103">Tabellenwertparameter-Spaltenwerte können genau wie andere Spalten- und Parameterwerte zwischen Client- und Serverdatentypen konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="52022-103">Table-valued parameter column values can be converted between client and server data types in the same way as other column and parameter values.</span></span> <span data-ttu-id="52022-104">Da Tabellenwertparameter jedoch mehrere Spalten und Zeilen enthalten können, ist es wichtig, den Wert identifizieren zu können, bei dem der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="52022-104">But because a table-valued parameter can contain multiple columns and multiple rows, it is important to be able to identify the actual value where the error occurred.</span></span>  
  
 <span data-ttu-id="52022-105">Wird eine Warnung oder ein Fehler in einer Tabellenwertparameter-Spalte erkannt, generiert [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client einen Diagnosedatensatz.</span><span class="sxs-lookup"><span data-stu-id="52022-105">When an error or warning is detected in a table-valued parameter column, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client will generate a diagnostic record.</span></span> <span data-ttu-id="52022-106">Die Fehlermeldung enthält die Parameternummer des Tabellenwertparameters sowie die Spaltenordnungszahl und Zeilennummer.</span><span class="sxs-lookup"><span data-stu-id="52022-106">The error message will contain the parameter number of the table-valued parameter, plus the column ordinal and row number.</span></span> <span data-ttu-id="52022-107">Zudem können die Diagnosefelder SQL_DIAG_SS_TABLE_COLUMN_NUMBER und SQL_DIAG_SS_TABLE_ROW_NUMBER innerhalb der Diagnosedatensätze von einer Anwendung verwendet werden, um zu bestimmen, welche Werte mit Fehlern und Warnungen verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="52022-107">An application can also use the diagnostic fields SQL_DIAG_SS_TABLE_COLUMN_NUMBER and SQL_DIAG_SS_TABLE_ROW_NUMBER within diagnostic records to determine which values are associated with errors and warnings.</span></span> <span data-ttu-id="52022-108">Diese Diagnosefelder sind in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] und höheren Versionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="52022-108">These diagnostic fields are available in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions.</span></span>  
  
 <span data-ttu-id="52022-109">In jeder anderen Hinsicht entsprechen die SQLSTATE- und Meldungskomponenten von Diagnosedatensätzen vorhandenem ODBC-Verhalten.</span><span class="sxs-lookup"><span data-stu-id="52022-109">The SQLSTATE and message components of diagnostic records will conform to existing ODBC behavior in all other respects.</span></span> <span data-ttu-id="52022-110">Das heißt, mit Ausnahme der Parameter-, Zeilen-und Spalten Identifizierungs Informationen haben Fehlermeldungen dieselben Werte für Tabellenwert Parameter wie für nicht-Tabellenwert Parameter.</span><span class="sxs-lookup"><span data-stu-id="52022-110">That is, except for the parameter, row, and column identification information, error messages have the same values for table-valued parameters as they would for non-table-valued parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52022-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="52022-111">See Also</span></span>  
 [<span data-ttu-id="52022-112">Tabellenwert Parameter &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="52022-112">Table-Valued Parameters &#40;ODBC&#41;</span></span>](table-valued-parameters-odbc.md)  
  
  
