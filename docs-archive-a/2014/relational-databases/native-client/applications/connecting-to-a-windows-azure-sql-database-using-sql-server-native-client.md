---
title: Herstellen einer Verbindung mit einer Azure SQL-Datenbank mithilfe von SQL Server Native Client | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 0dc20bb6-b142-4259-b87b-427d2ba798af
author: rothja
ms.author: jroth
ms.openlocfilehash: 177c655f97e32f2044460e87c6cd775cdf8fcde9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619075"
---
# <a name="connecting-to-an-azure-sql-database-using-sql-server-native-client"></a><span data-ttu-id="a0fe1-102">Herstellen einer Verbindung mit einer Azure SQL-Datenbank mithilfe von SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="a0fe1-102">Connecting to an Azure SQL Database Using SQL Server Native Client</span></span>
  <span data-ttu-id="a0fe1-103">Ein Beispiel für das Herstellen einer Verbindung mit einer [!INCLUDE[ssSDSfull](../../../includes/sssdsfull-md.md)] mithilfe von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client finden Sie unter [Entwicklung: Themen zur Vorgehensweise (Azure SQL-Datenbank)](https://msdn.microsoft.com/library/ee621787.aspx).</span><span class="sxs-lookup"><span data-stu-id="a0fe1-103">For a sample that shows how to connect to a [!INCLUDE[ssSDSfull](../../../includes/sssdsfull-md.md)] using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, see [Development: How-to Topics (Azure SQL Database)](https://msdn.microsoft.com/library/ee621787.aspx).</span></span>  
  
## <a name="known-issues-when-connecting-to-a-sql-database"></a><span data-ttu-id="a0fe1-104">Bekannte Probleme beim Herstellen einer Verbindung mit einer SQL-Datenbank</span><span class="sxs-lookup"><span data-stu-id="a0fe1-104">Known Issues When Connecting to a SQL Database</span></span>  
 <span data-ttu-id="a0fe1-105">Die folgenden bekannten Probleme können auftreten, wenn mithilfe von [!INCLUDE[ssSDS](../../../includes/sssds-md.md)] Native Client eine Verbindung mit einer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] hergestellt wird:</span><span class="sxs-lookup"><span data-stu-id="a0fe1-105">The following are known issues when connecting to a [!INCLUDE[ssSDS](../../../includes/sssds-md.md)] using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client:</span></span>  
  
-   <span data-ttu-id="a0fe1-106">Eine mithilfe von `SQLBrowseConnect` hergestellte Verbindung wird möglicherweise abgelehnt, wenn `SQLBrowseConnect` in mehreren Phasen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a0fe1-106">A connection made with `SQLBrowseConnect` may be rejected if `SQLBrowseConnect` is used in stages.</span></span>  <span data-ttu-id="a0fe1-107">Beispiel: Im ersten Aufruf wird der Treibername gesendet, im zweiten Aufruf werden Informationen zum Server und Anmeldeinformationen (Benutzer und Kennwort) gesendet, die Verbindung wird hergestellt, und im dritten Aufruf werden ein Datenbankname und eine Sprache gesendet.</span><span class="sxs-lookup"><span data-stu-id="a0fe1-107">For example, if the driver name is sent in the first call, server and credentials (user and password) sent in the second call, establishing the connection, and a database name and a language in the third call.</span></span>  <span data-ttu-id="a0fe1-108">Der dritte Aufruf bewirkt, dass [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client eine USE-Anweisung zum Wechseln von Datenbanken ausgibt.</span><span class="sxs-lookup"><span data-stu-id="a0fe1-108">The third call will cause [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client to issue a USE statement to change databases.</span></span> <span data-ttu-id="a0fe1-109">Die USE-Anweisung wird jedoch in [!INCLUDE[ssSDS](../../../includes/sssds-md.md)]nicht unterstützt und generiert den folgenden Fehler:</span><span class="sxs-lookup"><span data-stu-id="a0fe1-109">However, the USE statement is not supported in [!INCLUDE[ssSDS](../../../includes/sssds-md.md)], generating the following error:</span></span>  
  
    ```  
    [Microsoft][SQL Server Native Client 11.0][SQL Server]USE statement is not supported to switch between databases. Use a new connection to connect to a different Database.  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a0fe1-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a0fe1-110">See Also</span></span>  
 [<span data-ttu-id="a0fe1-111">Erstellen von Anwendungen mit SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="a0fe1-111">Building Applications with SQL Server Native Client</span></span>](building-applications-with-sql-server-native-client.md)  
  
  
