---
title: Tabellenwert Parameter-Metadaten für vorbereitete Anweisungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC), metadata for prepared statements
ms.assetid: fd2fc705-2e98-4011-9822-c7e6cca4a535
author: rothja
ms.author: jroth
ms.openlocfilehash: ad1394bd5e5bedc69a98308ba67a98434559c146
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725625"
---
# <a name="table-valued-parameter-metadata-for-prepared-statements"></a><span data-ttu-id="b999e-102">Tabellenwertparameter-Metadaten für vorbereitete Anweisungen</span><span class="sxs-lookup"><span data-stu-id="b999e-102">Table-Valued Parameter Metadata for Prepared Statements</span></span>
  <span data-ttu-id="b999e-103">Eine Anwendung kann über SQLNumParams und SQLDescribeParam Metadaten für einen vorbereiteten Prozedur Aufrufe abrufen.</span><span class="sxs-lookup"><span data-stu-id="b999e-103">An application can obtain metadata for a prepared procedure call through SQLNumParams and SQLDescribeParam.</span></span> <span data-ttu-id="b999e-104">Für Tabellenwert Parameter wird *DataTypePtr* auf SQL_SS_TABLE festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b999e-104">For table-valued parameters, *DataTypePtr* is set to SQL_SS_TABLE.</span></span> <span data-ttu-id="b999e-105">Zusätzliche Metadaten sind über SQLGetDescField für SQL_CA_SS_TYPE_NAME, SQL_CA_SS_CATALOG_NAME und SQL_CA_SS_SCHEMA_NAME verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b999e-105">Additional metadata is available through SQLGetDescField for SQL_CA_SS_TYPE_NAME, SQL_CA_SS_CATALOG_NAME, and SQL_CA_SS_SCHEMA_NAME.</span></span>  
  
 <span data-ttu-id="b999e-106">SQL_CA_SS_TYPE_NAME, SQL_CA_SS_CATALOG_NAME und SQL_CA_SS_SCHEMA_NAME können mit SQLColumns verwendet werden, um Spalten Metadaten für Tabellentypen, die Tabellenwert Parametern zugeordnet sind, abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b999e-106">SQL_CA_SS_TYPE_NAME, SQL_CA_SS_CATALOG_NAME, and SQL_CA_SS_SCHEMA_NAME can be used with SQLColumns to obtain column metadata for table types associated with table-valued parameters.</span></span> <span data-ttu-id="b999e-107">In diesem Fall muss SQL_SOPT_SS_NAME_SCOPE auf SQL_SS_NAME_SCOPE_TABLE_TYPE festgelegt werden, bevor SQLColumns aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b999e-107">In this case, SQL_SOPT_SS_NAME_SCOPE must be set to SQL_SS_NAME_SCOPE_TABLE_TYPE before SQLColumns is called.</span></span> <span data-ttu-id="b999e-108">SQL_SOPT_SS_NAME_SCOPE sollte wieder auf den Standardwert SQL_SS_NAME_SCOPE_TABLE gesetzt werden, wenn die Anwendung alle Tabellenwertparameter-Spaltenmetadaten abgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="b999e-108">SQL_SOPT_SS_NAME_SCOPE should then be set back to the default value, SQL_SS_NAME_SCOPE_TABLE, when the application has finished retrieving table-valued parameter column metadata.</span></span>  
  
 <span data-ttu-id="b999e-109">SQL_CA_SS_TYPE_NAME , SQL_CA_SS_CATALOG_NAME und SQL_CA_SS_SCHEMA_NAME können auch mit CLR-benutzerdefinierten Typparametern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b999e-109">SQL_CA_SS_TYPE_NAME , SQL_CA_SS_CATALOG_NAME, and SQL_CA_SS_SCHEMA_NAME can also be used with CLR user-defined type parameters.</span></span>  
  
 <span data-ttu-id="b999e-110">Sie können keine Tabellenwertparameter-Metadaten für vorbereitete Anweisungen abrufen, bei denen es sich nicht um gespeicherte Prozeduraufrufe handelt.</span><span class="sxs-lookup"><span data-stu-id="b999e-110">You cannot obtain table-valued parameter metadata for prepared statements that are not stored procedure calls.</span></span> <span data-ttu-id="b999e-111">Wenn Sie dies dennoch versuchen, gibt die Anwendung den Fehler SQL_ERROR mit SQLSTATE 42000 sowie die Meldung "Syntaxfehler oder Zugriffsverletzung" zurück.</span><span class="sxs-lookup"><span data-stu-id="b999e-111">If you try to do this, the application returns SQL_ERROR with SQLSTATE 42000 and the message "Syntax error or access violation".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b999e-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b999e-112">See Also</span></span>  
 [<span data-ttu-id="b999e-113">Tabellenwert Parameter &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="b999e-113">Table-Valued Parameters &#40;ODBC&#41;</span></span>](table-valued-parameters-odbc.md)  
  
  
