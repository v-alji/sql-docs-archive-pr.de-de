---
title: Data-at-Execution-und Text-, ntext-oder image-Spalten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- text columns [ODBC]
- SQL Server Native Client ODBC driver, image columns
- SQL Server Native Client ODBC driver, text columns
- data types [ODBC], image
- data types [ODBC], text
- columns [ODBC]
- ODBC data types, image columns
- ODBC data types, text columns
- data-at-execution
- ODBC data-at-execution
- image columns [ODBC]
ms.assetid: 67ffb1a6-f38d-4712-ba64-96bdd41ec2b2
author: rothja
ms.author: jroth
ms.openlocfilehash: 404fade34862fe4705ec440eef7f466a9073250b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725641"
---
# <a name="data-at-execution-and-text-ntext-or-image-columns"></a><span data-ttu-id="56f89-102">Data-at-Execution und Text-, ntext- oder Imagespalten</span><span class="sxs-lookup"><span data-stu-id="56f89-102">Data-at-Execution and Text, ntext, or Image Columns</span></span>
  <span data-ttu-id="56f89-103">ODBC verfügt über eine Funktion namens Data-at-Execution (Daten bei Ausführung), die es Anwendungen ermöglicht, sehr große Datenmengen in gebundenen Spalten oder Parametern zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="56f89-103">ODBC data-at-execution is a feature that enables applications to work with extremely large amounts of data on bound columns or parameters.</span></span> <span data-ttu-id="56f89-104">Beim Abrufen sehr großer **Text**-, **ntext**-oder **Image** -Spalten kann eine Anwendung möglicherweise nicht einfach einen riesigen Puffer zuordnen, die Spalte an den Puffer binden und die Zeile abrufen.</span><span class="sxs-lookup"><span data-stu-id="56f89-104">When retrieving very large **text**, **ntext**, or **image** columns, an application may not be able to simply allocate a huge buffer, bind the column into the buffer, and fetch the row.</span></span> <span data-ttu-id="56f89-105">Beim Aktualisieren sehr großer **Text**-, **ntext**-oder **Image** -Spalten kann die Anwendung möglicherweise nicht einfach einen riesigen Puffer zuordnen, Sie an eine Parameter Markierung in einer SQL-Anweisung binden und dann die Anweisung ausführen.</span><span class="sxs-lookup"><span data-stu-id="56f89-105">When updating very large **text**, **ntext**, or **image** columns, the application might not be able to simply allocate a huge buffer, bind it to a parameter marker in an SQL statement, and then execute the statement.</span></span> <span data-ttu-id="56f89-106">In diesen Fällen muss die Anwendung [SQLGetData](../native-client-odbc-api/sqlgetdata.md) oder [SQLPutData](../native-client-odbc-api/sqlputdata.md) mit ihren Data-at-Execution-Optionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="56f89-106">In these cases, the application must use [SQLGetData](../native-client-odbc-api/sqlgetdata.md) or [SQLPutData](../native-client-odbc-api/sqlputdata.md) with its data-at-execution options.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56f89-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56f89-107">See Also</span></span>  
 [<span data-ttu-id="56f89-108">Verwalten von Text und Imagespalten</span><span class="sxs-lookup"><span data-stu-id="56f89-108">Managing Text and Image Columns</span></span>](managing-text-and-image-columns.md)  
  
  
