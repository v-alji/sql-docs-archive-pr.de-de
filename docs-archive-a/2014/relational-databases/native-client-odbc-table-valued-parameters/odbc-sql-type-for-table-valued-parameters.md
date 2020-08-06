---
title: ODBC-SQL-Typ für Tabellenwert Parameter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL_SS_TABLE
ms.assetid: 6725bfb9-5f10-4115-be09-fd9c9f5779ea
author: rothja
ms.author: jroth
ms.openlocfilehash: c8ed46bf117c9158ae5b60c10ebd89e3d348f77c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620856"
---
# <a name="odbc-sql-type-for-table-valued-parameters"></a><span data-ttu-id="5ecfa-102">ODBC-SQL-Typ für Tabellenwertparameter</span><span class="sxs-lookup"><span data-stu-id="5ecfa-102">ODBC SQL Type for Table-Valued Parameters</span></span>
  <span data-ttu-id="5ecfa-103">Unterstützung für Tabellenwertparameter wird von einem neuen ODBC-SQL-Typ, SQL_SS_TABLE, bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5ecfa-103">Support for table-valued parameters is provided by a new ODBC SQL type, SQL_SS_TABLE.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ecfa-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5ecfa-104">Remarks</span></span>  
 <span data-ttu-id="5ecfa-105">SQL_SS_TABLE kann nicht in einen anderen ODBC- oder [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datentyp konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="5ecfa-105">SQL_SS_TABLE cannot be converted to any other ODBC or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type.</span></span>  
  
 <span data-ttu-id="5ecfa-106">Wenn SQL_SS_TABLE im *ValueType* -Parameter von SQLBindParameter als C-Datentyp verwendet wird, oder wenn versucht wird, SQL_DESC_TYPE in einem Anwendungsparameter Deskriptor (APD)-Datensatz auf SQL_SS_TABLE festzulegen, wird SQL_ERROR zurückgegeben, und es wird ein Diagnosedaten Satz mit SQLSTATE = HY003, "Ungültiger Anwendungs Puffertyp", generiert.</span><span class="sxs-lookup"><span data-stu-id="5ecfa-106">If SQL_SS_TABLE is used as a C data type in the *ValueType* parameter of SQLBindParameter, or an attempt is made to set SQL_DESC_TYPE in an application parameter descriptor (APD) record to SQL_SS_TABLE, SQL_ERROR is returned and a diagnostic record is generated with SQLSTATE=HY003, "Invalid application buffer type".</span></span>  
  
 <span data-ttu-id="5ecfa-107">Wenn SQL_DESC_TYPE in einem IPD-Datensatz auf SQL_SS_TABLE festgelegt wird, und der entsprechende Anwendungsparameterdeskriptor-Datensatz nicht SQL_C_DEFAULT ist, wird SQL_ERROR zurückgegeben, und ein Diagnosedatensatz mit der Meldung SQLSTATE=HY003, "Ungültiger Anwendungspuffertyp" wird generiert.</span><span class="sxs-lookup"><span data-stu-id="5ecfa-107">If SQL_DESC_TYPE is set to SQL_SS_TABLE in an IPD record and the corresponding application parameter descriptor record is not SQL_C_DEFAULT, SQL_ERROR is returned and a diagnostic record is generated with SQLSTATE=HY003, "Invalid application buffer type".</span></span> <span data-ttu-id="5ecfa-108">Dies kann mit dem *ParameterType* von SQLSetDescField, SQLSetDescRec oder SQLBindParameter auftreten.</span><span class="sxs-lookup"><span data-stu-id="5ecfa-108">This can occur with the *ParameterType* of a SQLSetDescField, SQLSetDescRec or SQLBindParameter.</span></span>  
  
 <span data-ttu-id="5ecfa-109">Wenn der *TargetType* -Parameter beim Aufrufen von SQLGetData SQL_SS_TABLE ist, wird SQL_ERROR zurückgegeben, und es wird ein Diagnosedaten Satz mit SQLSTATE = HY003, "Ungültiger Anwendungs Puffertyp", generiert.</span><span class="sxs-lookup"><span data-stu-id="5ecfa-109">If the *TargetType* parameter is SQL_SS_TABLE when calling SQLGetData, SQL_ERROR is returned and a diagnostic record is generated with SQLSTATE=HY003, "Invalid application buffer type".</span></span>  
  
 <span data-ttu-id="5ecfa-110">Eine Tabellenwertparameter-Spalte kann nicht als SQL_SS_TABLE-Datentyp gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="5ecfa-110">A table-valued parameter column cannot be bound as type SQL_SS_TABLE.</span></span> <span data-ttu-id="5ecfa-111">Wenn `SQLBindParameter` aufgerufen wird, wobei *ParameterType* auf SQL_SS_TABLE festgelegt ist, wird SQL_ERROR zurückgegeben, und es wird ein Diagnosedaten Satz mit SQLSTATE = HY004, "Ungültiger SQL-Datentyp", generiert.</span><span class="sxs-lookup"><span data-stu-id="5ecfa-111">If `SQLBindParameter` is called with *ParameterType* set to SQL_SS_TABLE, SQL_ERROR is returned and a diagnostic record is generated with SQLSTATE=HY004, "Invalid SQL data type".</span></span> <span data-ttu-id="5ecfa-112">Dies kann auch mit SQLSetDescField und SQLSetDescRec auftreten.</span><span class="sxs-lookup"><span data-stu-id="5ecfa-112">This can also occur with SQLSetDescField and SQLSetDescRec.</span></span>  
  
 <span data-ttu-id="5ecfa-113">Tabellenwertparameter-Spaltenwerte verfügen über dieselben Datenkonvertierungsoptionen wie Parameter und Ergebnisspalten.</span><span class="sxs-lookup"><span data-stu-id="5ecfa-113">Table-valued parameter column values have the same data conversion options as parameters and result columns.</span></span>  
  
 <span data-ttu-id="5ecfa-114">Bei einem Tabellenwertparameter kann es sich nur um einen Eingabeparameter in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] oder höher handeln.</span><span class="sxs-lookup"><span data-stu-id="5ecfa-114">A table-valued parameter can only be an input parameter in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later.</span></span> <span data-ttu-id="5ecfa-115">Wenn versucht wird, SQL_DESC_PARAMETER_TYPE auf einen anderen Wert als SQL_PARAM_INPUT über SQLBindParameter oder SQLSetDescField festzulegen, wird SQL_ERROR zurückgegeben, und der Anweisung wird mit SQLSTATE = HY105 und der Meldung "Ungültiger Parametertyp" ein Diagnosedaten Satz hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5ecfa-115">If an attempt is made to set SQL_DESC_PARAMETER_TYPE to a value other than SQL_PARAM_INPUT via SQLBindParameter or SQLSetDescField, SQL_ERROR is returned and a diagnostic record is added to the statement with SQLSTATE=HY105 and the message "Invalid parameter type".</span></span>  
  
 <span data-ttu-id="5ecfa-116">Tabellenwertparameter-Spalten können SQL_DEFAULT_PARAM nicht in *StrLen_or_IndPtr*verwenden, da Standardwerte pro Zeile nicht mit Tabellenwertparametern unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="5ecfa-116">Table-valued parameter columns cannot use SQL_DEFAULT_PARAM in *StrLen_or_IndPtr*, because per-row default values are not supported with table-valued parameters.</span></span> <span data-ttu-id="5ecfa-117">Stattdessen kann eine Anwendung das Spaltenattribut SQL_CA_SS_COL_HAS_DEFAULT_VALUE auf 1 festlegen.</span><span class="sxs-lookup"><span data-stu-id="5ecfa-117">Instead, an application can set the column attribute SQL_CA_SS_COL_HAS_DEFAULT_VALUE to 1.</span></span> <span data-ttu-id="5ecfa-118">Dies bedeutet, dass die Spalte Standardwerte für alle Zeilen aufweist.</span><span class="sxs-lookup"><span data-stu-id="5ecfa-118">This means that the column will have default values for all rows.</span></span> <span data-ttu-id="5ecfa-119">Wenn *StrLen_or_IndPtr* auf SQL_DEFAULT_PARAM festgelegt ist, wird von SQLExecute oder SQLExecDirect SQL_ERROR zurückgegeben, und der Anweisung mit SQLSTATE = HY090 und der Meldung "ungültige Zeichen folgen-oder Pufferlänge" wird ein Diagnosedaten Satz hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5ecfa-119">If *StrLen_or_IndPtr* is set to SQL_DEFAULT_PARAM, SQLExecute or SQLExecDirect will return SQL_ERROR, and a diagnostic record will be added to the statement with SQLSTATE=HY090 and the message "Invalid string or buffer length".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ecfa-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ecfa-120">See Also</span></span>  
 [<span data-ttu-id="5ecfa-121">Tabellenwert Parameter &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="5ecfa-121">Table-Valued Parameters &#40;ODBC&#41;</span></span>](table-valued-parameters-odbc.md)  
  
  
