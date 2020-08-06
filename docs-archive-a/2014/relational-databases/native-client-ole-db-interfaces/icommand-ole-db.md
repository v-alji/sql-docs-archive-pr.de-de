---
title: ICommand (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ICommand [SQL Server Native Client]
ms.assetid: 5e24b3a0-0658-44fc-b653-f4c52f9eb328
author: rothja
ms.author: jroth
ms.openlocfilehash: 03bdccc83a04078210f2283d0b330f237ed02979
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621494"
---
# <a name="icommand-ole-db"></a><span data-ttu-id="ae58e-102">ICommand (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="ae58e-102">ICommand (OLE DB)</span></span>
  <span data-ttu-id="ae58e-103">In diesem Thema wird das OLE DB-Verhalten beschrieben, das für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client spezifisch ist.</span><span class="sxs-lookup"><span data-stu-id="ae58e-103">This topic discusses OLE DB behavior that is specific to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
## <a name="icommandexecute"></a><span data-ttu-id="ae58e-104">ICommand::Execute</span><span class="sxs-lookup"><span data-stu-id="ae58e-104">ICommand::Execute</span></span>  
 <span data-ttu-id="ae58e-105">Das Einfügen von Daten, die größer als die Größe einer Spalte sind, führt in der Regel zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="ae58e-105">Inserting data that is greater than the size of a column typically results in an error.</span></span> <span data-ttu-id="ae58e-106">In bestimmten Situationen wird zwar S_OK zurückgegeben, der *dwStatus* wird jedoch auf DBSTATUS_S_TRUNCATED festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ae58e-106">However, there are situations where S_OK will be returned but the *dwStatus* will be set to DBSTATUS_S_TRUNCATED.</span></span> <span data-ttu-id="ae58e-107">Dieser Fall tritt im Allgemeinen ein, wenn Daten mit Parametern eingefügt werden, die Spalte jedoch zum Speichern der Daten nicht groß genug ist und `ICommandWithParameters::SetParameterInfo` nicht aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="ae58e-107">This generally occurs when inserting data with parameters, where the column is not large enough to hold the data, and `ICommandWithParameters::SetParameterInfo` has not been called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae58e-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ae58e-108">See Also</span></span>  
 [<span data-ttu-id="ae58e-109">Schnittstellen &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="ae58e-109">Interfaces &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/interfaces-ole-db.md)  
  
  
