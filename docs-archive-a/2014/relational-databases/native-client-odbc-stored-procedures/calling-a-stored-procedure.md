---
title: Aufrufen einer gespeicherten Prozedur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- calling stored procedures
- ODBC, stored procedures
- stored procedures [ODBC], calling
- SQL Server Native Client ODBC driver, stored procedures
- ODBC CALL escape sequence
- escape sequences [SQL Server]
- CALL statement
ms.assetid: d13737f4-f641-45bf-b56c-523e2ffc080f
author: rothja
ms.author: jroth
ms.openlocfilehash: c6fa704e45e4e85b479ae8a40a3e567bea1ec5e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725638"
---
# <a name="calling-a-stored-procedure"></a><span data-ttu-id="25342-102">Aufrufen von gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="25342-102">Calling a Stored Procedure</span></span>
  <span data-ttu-id="25342-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber unterstützt sowohl die ODBC-Rückruf-Escapesequenz als auch die [!INCLUDE[tsql](../../includes/tsql-md.md)] [Execute](/sql/t-sql/language-elements/execute-transact-sql) -Anweisung zum Ausführen gespeicherter Prozeduren. die ODBC-Rückruf Sequenz ist die bevorzugte Methode</span><span class="sxs-lookup"><span data-stu-id="25342-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports both the ODBC CALL escape sequence and the [!INCLUDE[tsql](../../includes/tsql-md.md)][EXECUTE](/sql/t-sql/language-elements/execute-transact-sql) statement for executing stored procedures; the ODBC CALL escape sequence is the preferred method.</span></span> <span data-ttu-id="25342-104">Mithilfe der ODBC-Syntax kann eine Anwendung die Rückgabecodes von gespeicherten Prozeduren abrufen. Zudem wurde der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC-Treiber für die Verwendung eines ursprünglich zum Senden von Remoteprozeduraufrufen (RPC) zwischen Computern, die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausführen, entwickelten Protokolls optimiert.</span><span class="sxs-lookup"><span data-stu-id="25342-104">Using ODBC syntax enables an application to retrieve the return codes of stored procedures and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver is also optimized to use a protocol originally developed for sending remote procedure (RPC) calls between computers running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="25342-105">Dieses RPC-Protokoll erhöht die Leistung, indem es einen Großteil der Parameterverarbeitung und Anweisungsauswertung auf dem Server überflüssig macht.</span><span class="sxs-lookup"><span data-stu-id="25342-105">This RPC protocol increases performance by eliminating much of the parameter processing and statement parsing done on the server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="25342-106">Beim Aufrufen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gespeicherter Prozeduren mit benannten Parametern mit ODBC (Weitere Informationen finden Sie unter [Binden von Parametern anhand des Namens (benannte Parameter)](https://go.microsoft.com/fwlink/?LinkID=209721)) müssen die Parameternamen mit dem \@ Zeichen "" beginnen.</span><span class="sxs-lookup"><span data-stu-id="25342-106">When calling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures using named parameters with ODBC (for more information, see [Binding Parameters by Name (Named Parameters)](https://go.microsoft.com/fwlink/?LinkID=209721)), the parameter names must start with the '\@' character.</span></span> <span data-ttu-id="25342-107">Dies ist eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-spezifische Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="25342-107">This is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] specific restriction.</span></span> <span data-ttu-id="25342-108">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODCB-Treiber erzwingt diese Einschränkung strenger als die MDAC (Microsoft Data Access Components).</span><span class="sxs-lookup"><span data-stu-id="25342-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver enforces this restriction more strictly than the Microsoft Data Access Components (MDAC).</span></span>  
  
 <span data-ttu-id="25342-109">Die ODBC CALL-Escapesequenz für das Aufrufen einer Prozedur lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="25342-109">The ODBC CALL escape sequence for calling a procedure is:</span></span>  
  
 <span data-ttu-id="25342-110">{[**? =**]**aufrufen**_procedure_name_[([*Parameter*] [**,**[*Parameter*]]...)]}</span><span class="sxs-lookup"><span data-stu-id="25342-110">{[**?=**]**call**_procedure_name_[([*parameter*][**,**[*parameter*]]...)]}</span></span>  
  
 <span data-ttu-id="25342-111">wobei *procedure_name* den Namen einer Prozedur angibt und *Parameter* einen Prozedur Parameter angibt.</span><span class="sxs-lookup"><span data-stu-id="25342-111">where *procedure_name* specifies the name of a procedure and *parameter* specifies a procedure parameter.</span></span> <span data-ttu-id="25342-112">Benannte Parameter werden nur in Anweisungen mit ODBC CALL-Escapesequenz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="25342-112">Named parameters are only supported in statements using the ODBC CALL escape sequence.</span></span>  
  
 <span data-ttu-id="25342-113">Eine Prozedur kann 0 (null) oder mehr Parameter haben.</span><span class="sxs-lookup"><span data-stu-id="25342-113">A procedure can have zero or more parameters.</span></span> <span data-ttu-id="25342-114">Sie kann außerdem einen Wert zurückgeben (wie durch die optionale Parametermarkierung ?= am Anfang der Markierung angegeben).</span><span class="sxs-lookup"><span data-stu-id="25342-114">It can also return a value (as indicated by the optional parameter marker ?= at the start of the syntax).</span></span> <span data-ttu-id="25342-115">Wenn es sich bei einem Parameter um einen Eingabe- oder einen Eingabe-/Ausgabeparameter handelt, kann ein Literalwert oder eine Parametermarkierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="25342-115">If a parameter is an input or an input/output parameter, it can be a literal or a parameter marker.</span></span> <span data-ttu-id="25342-116">Wenn es sich bei dem Parameter um einen Ausgabeparameter handelt, muss eine Parametermarkierung verwendet werden, da die Ausgabe unbekannt ist.</span><span class="sxs-lookup"><span data-stu-id="25342-116">If the parameter is an output parameter, it must be a parameter marker because the output is unknown.</span></span> <span data-ttu-id="25342-117">Parameter Markierungen müssen mit [SQLBindParameter](../../relational-databases/native-client-odbc-api/sqlbindparameter.md) gebunden werden, bevor die Prozedur aufrufen-Anweisung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="25342-117">Parameter markers must be bound with [SQLBindParameter](../../relational-databases/native-client-odbc-api/sqlbindparameter.md) before the procedure call statement is executed.</span></span>  
  
 <span data-ttu-id="25342-118">Eingabe- und Eingabe-/Ausgabeparameter müssen in Prozeduraufrufen nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="25342-118">Input and input/output parameters can be omitted from procedure calls.</span></span> <span data-ttu-id="25342-119">Wenn eine Prozedur mit Klammern aber ohne Parameter aufgerufen wird, weist der Treiber die Datenquelle an, für den ersten Parameter den Standardwert zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="25342-119">If a procedure is called with parentheses but without any parameters, the driver instructs the data source to use the default value for the first parameter.</span></span> <span data-ttu-id="25342-120">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="25342-120">For example:</span></span>  
  
 <span data-ttu-id="25342-121">{**call** _procedure_name_**()**} abrufen</span><span class="sxs-lookup"><span data-stu-id="25342-121">{**call** _procedure_name_**( )**}</span></span>  
  
 <span data-ttu-id="25342-122">Wenn die Prozedur keine Parameter aufweist, kann bei der Prozedur ein Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="25342-122">If the procedure does not have any parameters, the procedure can fail.</span></span> <span data-ttu-id="25342-123">Wenn eine Prozedur ohne Klammern aufgerufen wird, sendet der Treiber keine Parameterwerte.</span><span class="sxs-lookup"><span data-stu-id="25342-123">If a procedure is called without parentheses, the driver does not send any parameter values.</span></span> <span data-ttu-id="25342-124">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="25342-124">For example:</span></span>  
  
 <span data-ttu-id="25342-125">{**call** _procedure_name_} abrufen</span><span class="sxs-lookup"><span data-stu-id="25342-125">{**call** _procedure_name_}</span></span>  
  
 <span data-ttu-id="25342-126">Literalwerte können in Prozeduraufrufen für Eingabe- und Eingabe-/Ausgabeparameter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="25342-126">Literals can be specified for input and input/output parameters in procedure calls.</span></span> <span data-ttu-id="25342-127">Die Prozedur InsertOrder weist beispielsweise fünf Parameter auf.</span><span class="sxs-lookup"><span data-stu-id="25342-127">For example, the procedure InsertOrder has five input parameters.</span></span> <span data-ttu-id="25342-128">Beim folgenden Aufruf von InsertOrder ist der erste Parameter nicht angegeben, für den zweiten Parameter ist ein Literalwert angegeben und für den dritten, vierten und fünften Parameter wird eine Parametermarkierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="25342-128">The following call to InsertOrder omits the first parameter, provides a literal for the second parameter, and uses a parameter marker for the third, fourth, and fifth parameters.</span></span> <span data-ttu-id="25342-129">(Parameter werden sequenziell nummeriert und beginnen mit dem Wert 1.)</span><span class="sxs-lookup"><span data-stu-id="25342-129">(Parameters are numbered sequentially, beginning with a value of 1.)</span></span>  
  
```  
{call InsertOrder(, 10, ?, ?, ?)}  
```  
  
 <span data-ttu-id="25342-130">Wenn ein Parameter nicht angegeben wird, muss das Komma dennoch gesetzt werden, damit dieser Parameter von anderen Parametern abgegrenzt wird.</span><span class="sxs-lookup"><span data-stu-id="25342-130">Note that if a parameter is omitted, the comma delimiting it from other parameters must still appear.</span></span> <span data-ttu-id="25342-131">Wenn ein Eingabe- oder ein Eingabe-/Ausgabeparameter ausgelassen wird, verwendet die Prozedur den Standardwert des Parameters.</span><span class="sxs-lookup"><span data-stu-id="25342-131">If an input or input/output parameter is omitted, the procedure uses the default value of the parameter.</span></span> <span data-ttu-id="25342-132">Eine weitere Möglichkeit, den Standardwert eines Eingabe- oder eines Eingabe-/Ausgabeparameters anzugeben, besteht darin, den Wert des an den Parameter gebundenen Längen-/Indikatorpuffers auf SQL_DEFAULT_PARAM festzulegen oder das DEFAULT-Schlüsselwort zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="25342-132">Other ways to specify the default value of an input or input/output parameter are to set the value of the length/indicator buffer bound to the parameter to SQL_DEFAULT_PARAM, or to use the DEFAULT keyword.</span></span>  
  
 <span data-ttu-id="25342-133">Wenn ein Eingabe-/Ausgabeparameter ausgelassen oder ein Literalwert für den Parameter angegeben wird, verwirft der Treiber den Ausgabewert.</span><span class="sxs-lookup"><span data-stu-id="25342-133">If an input/output parameter is omitted, or if a literal is supplied for the parameter, the driver discards the output value.</span></span> <span data-ttu-id="25342-134">Entsprechend verwirft der Treiber den Rückgabewert, wenn die Parametermarkierung für den Rückgabewert einer Prozedur ausgelassen wird.</span><span class="sxs-lookup"><span data-stu-id="25342-134">Similarly, if the parameter marker for the return value of a procedure is omitted, the driver discards the return value.</span></span> <span data-ttu-id="25342-135">Wenn eine Anwendung den Parameter des Rückgabewerts für eine Prozedur angibt, die keinen Wert zurückgibt, legt der Treiber den Wert des an den Parameter gebundenen Längen-/Indikatorpuffers auf SQL_NULL_DATA fest.</span><span class="sxs-lookup"><span data-stu-id="25342-135">Finally, if an application specifies a return value parameter for a procedure that does not return a value, the driver sets the value of the length/indicator buffer bound to the parameter to SQL_NULL_DATA.</span></span>  
  
## <a name="delimiters-in-call-statements"></a><span data-ttu-id="25342-136">Trennzeichen in CALL-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="25342-136">Delimiters in CALL Statements</span></span>  
 <span data-ttu-id="25342-137">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC-Treiber unterstützt außerdem standardmäßig eine für die ODBC { CALL }-Escapesequenz spezifische Kompatibilitätsoption.</span><span class="sxs-lookup"><span data-stu-id="25342-137">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver by default also supports a compatibility option specific to the ODBC { CALL } escape sequence.</span></span> <span data-ttu-id="25342-138">Der Treiber akzeptiert nur CALL-Anweisungen mit einem Satz doppelter Anführungszeichen zum Trennen des gesamten Namens der gespeicherten Prozedur:</span><span class="sxs-lookup"><span data-stu-id="25342-138">The driver accepts CALL statements with only a single set of double quotation marks delimiting the entire stored procedure name:</span></span>  
  
```  
{ CALL "master.dbo.sp_who" }  
```  
  
 <span data-ttu-id="25342-139">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC-Treiber akzeptiert darüber hinaus auch standardmäßig CALL-Anweisungen, die den ISO-Regeln gehorchen und bei denen jeder Bezeichner in doppelten Anführungszeichen steht:</span><span class="sxs-lookup"><span data-stu-id="25342-139">By default the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver also accepts CALL statements that follow the ISO rules and enclose each identifier in double quotation marks:</span></span>  
  
```  
{ CALL "master"."dbo"."sp_who" }  
```  
  
 <span data-ttu-id="25342-140">Beim Ausführen der Standardeinstellungen unterstützt der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC-Treiber bei Bezeichnern mit Zeichen, die durch den ISO-Standard nicht als gültige Zeichen in Bezeichnern angegeben sind, jedoch keine Form von Bezeichnern mit Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="25342-140">When running with the default settings, however, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not support using either form of quoted identifier with identifiers that contain characters not specified as legal in identifiers by the ISO standard.</span></span> <span data-ttu-id="25342-141">Beispielsweise kann der Treiber nicht auf eine gespeicherte Prozedur mit dem Namen **"My. proc"** zugreifen, indem eine-Anweisung mit Bezeichnern in Anführungszeichen verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="25342-141">For example, the driver cannot access a stored procedure named **"My.Proc"** using a CALL statement with quoted identifiers:</span></span>  
  
```  
{ CALL "MyDB"."MyOwner"."My.Proc" }  
```  
  
 <span data-ttu-id="25342-142">Diese Anweisung wird vom Treiber wie folgt interpretiert:</span><span class="sxs-lookup"><span data-stu-id="25342-142">This statement is interpreted by the driver as:</span></span>  
  
```  
{ CALL MyDB.MyOwner.My.Proc }  
```  
  
 <span data-ttu-id="25342-143">Der Server löst einen Fehler aus, dass kein Verbindungs Server mit dem Namen **mydb** vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="25342-143">The server raises an error that a linked server named **MyDB** does not exist.</span></span>  
  
 <span data-ttu-id="25342-144">Das Problem tritt nicht auf, wenn Bezeichner in Klammern verwendet werden. Dann wird diese Anweisung richtig interpretiert:</span><span class="sxs-lookup"><span data-stu-id="25342-144">The issue does not exist when using bracketed identifiers, this statement is interpreted correctly:</span></span>  
  
```  
{ CALL [MyDB].[MyOwner].[My.Table] }  
```  
  
## <a name="see-also"></a><span data-ttu-id="25342-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="25342-145">See Also</span></span>  
 [<span data-ttu-id="25342-146">Ausführen gespeicherter Prozeduren</span><span class="sxs-lookup"><span data-stu-id="25342-146">Running Stored Procedures</span></span>](../../relational-databases/native-client-odbc-stored-procedures/running-stored-procedures.md)  
  
  
