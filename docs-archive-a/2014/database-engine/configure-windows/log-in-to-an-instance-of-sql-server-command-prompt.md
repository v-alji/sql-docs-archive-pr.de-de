---
title: Anmelden an einer Instanz von SQL Server (Befehlszeile) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- logins [SQL Server], named instance of SQL Server
- log ins [SQL Server]
- logins [SQL Server], default instance of SQL Server
- command prompt [SQL Server], logins
- logging in [SQL Server]
ms.assetid: f67c11e3-c519-40c9-82c1-07efa9d9985e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 32028a30786117f2cafa76150867a0e726b07cda
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608840"
---
# <a name="log-in-to-an-instance-of-sql-server-command-prompt"></a><span data-ttu-id="0b34a-102">Anmelden an einer Instanz von SQL Server (Befehlszeile)</span><span class="sxs-lookup"><span data-stu-id="0b34a-102">Log In to an Instance of SQL Server (Command Prompt)</span></span>
  <span data-ttu-id="0b34a-103">In diesem Thema wird beschrieben, wie Sie die Konnektivität mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]mithilfe des Hilfsprogramms **sqlcmd** testen.</span><span class="sxs-lookup"><span data-stu-id="0b34a-103">This topic describes how to test connectivity to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], use the **sqlcmd** utility.</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-log-in-to-the-default-instance-of-sql-server"></a><span data-ttu-id="0b34a-104">So melden Sie sich an der Standardinstanz von SQL Server an</span><span class="sxs-lookup"><span data-stu-id="0b34a-104">To log in to the default instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="0b34a-105">Geben Sie an einer Eingabeaufforderung den folgenden Befehl ein, um eine Verbindung mithilfe der Windows-Authentifizierung herzustellen:</span><span class="sxs-lookup"><span data-stu-id="0b34a-105">From a command prompt, enter the following command to connect by using Windows Authentication:</span></span>  
  
    ```  
    sqlcmd [ /E ] [ /S servername ]  
  
    ```  
  
#### <a name="to-log-in-to-a-named-instance-of-sql-server"></a><span data-ttu-id="0b34a-106">So melden Sie sich an einer benannten Instanz von SQL Server an</span><span class="sxs-lookup"><span data-stu-id="0b34a-106">To log in to a named instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="0b34a-107">Geben Sie an einer Eingabeaufforderung den folgenden Befehl ein, um eine Verbindung mithilfe der Windows-Authentifizierung herzustellen:</span><span class="sxs-lookup"><span data-stu-id="0b34a-107">From a command prompt, enter the following command to connect by using Windows Authentication:</span></span>  
  
    ```  
    sqlcmd [ /E ] /S servername\instancename  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0b34a-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0b34a-108">See Also</span></span>  
 <span data-ttu-id="0b34a-109">[sqlcmd (Hilfsprogramm)](../../tools/sqlcmd-utility.md) </span><span class="sxs-lookup"><span data-stu-id="0b34a-109">[sqlcmd Utility](../../tools/sqlcmd-utility.md) </span></span>  
 [<span data-ttu-id="0b34a-110">osql (Hilfsprogramm)</span><span class="sxs-lookup"><span data-stu-id="0b34a-110">osql Utility</span></span>](../../tools/osql-utility.md)  
  
  
