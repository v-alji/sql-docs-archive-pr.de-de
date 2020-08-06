---
title: Anmeldeinformationen (Datenbank-Engine) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- principals [SQL Server], credentials
- schemas [SQL Server], credentials
- permissions [SQL Server], credentials
- groups [SQL Server], credentials
- ALTER ANY CREDENTIAL permission
- security [SQL Server], credentials
- authentication [SQL Server], credentials
- users [SQL Server], credentials
- credentials [SQL Server], about credentials
- credentials [SQL Server]
ms.assetid: c8df6022-e0b4-46b8-9670-3f86938d3177
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: faa2b5be7cf6918b5d5232763a96ed4dbbc89e51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620777"
---
# <a name="credentials-database-engine"></a><span data-ttu-id="ba151-102">Anmeldeinformationen (Datenbank-Engine)</span><span class="sxs-lookup"><span data-stu-id="ba151-102">Credentials (Database Engine)</span></span>
  <span data-ttu-id="ba151-103">Anmeldeinformationen sind in einem Datensatz gespeichert, in dem die Authentifizierungsinformationen (Anmeldeinformationen) enthalten sind, die zum Herstellen einer Verbindung mit einer Ressource außerhalb von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ba151-103">A credential is a record that contains the authentication information (credentials) required to connect to a resource outside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ba151-104">Diese Informationen werden intern von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]verwendet.</span><span class="sxs-lookup"><span data-stu-id="ba151-104">This information is used internally by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ba151-105">Die meisten Anmeldeinformationen enthalten einen Windows-Benutzernamen und ein Kennwort.</span><span class="sxs-lookup"><span data-stu-id="ba151-105">Most credentials contain a Windows user name and password.</span></span>  
  
 <span data-ttu-id="ba151-106">Die in Anmeldeinformationen gespeicherten Informationen ermöglichen einem Benutzer, der eine Verbindung mit [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] über die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Authentifizierung hergestellt hat, auf Ressourcen außerhalb der Serverinstanz zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="ba151-106">The information stored in a credential enables a user who has connected to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by way of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication to access resources outside the server instance.</span></span> <span data-ttu-id="ba151-107">Wenn es sich bei der externen Ressource um Windows handelt, wird der Benutzer als der in den Anmeldeinformationen angegebene Windows-Benutzer authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="ba151-107">When the external resource is Windows, the user is authenticated as the Windows user specified in the credential.</span></span> <span data-ttu-id="ba151-108">Eine einzelne Anmeldung kann mehreren [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Anmeldungen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="ba151-108">A single credential can be mapped to multiple [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins.</span></span> <span data-ttu-id="ba151-109">Eine [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Anmeldung kann allerdings nur einer Anmeldung zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="ba151-109">However, a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login can be mapped to only one credential.</span></span>  
  
 <span data-ttu-id="ba151-110">Systemanmeldeinformationen werden automatisch erstellt und mit bestimmten Endpunkten verbunden.</span><span class="sxs-lookup"><span data-stu-id="ba151-110">System credentials are created automatically and are associated with specific endpoints.</span></span> <span data-ttu-id="ba151-111">Namen für Systemanmeldeinformationen beginnen mit zwei Nummernzeichen (##).</span><span class="sxs-lookup"><span data-stu-id="ba151-111">Names for system credentials start with two hash signs (##).</span></span>  
  
 <span data-ttu-id="ba151-112">Weitere Informationen zu Anmelde Informationen finden Sie in der Katalog Sicht [sys. Anmelde](/sql/relational-databases/system-catalog-views/sys-credentials-transact-sql) Informationen.</span><span class="sxs-lookup"><span data-stu-id="ba151-112">For more information about credentials, see the [sys.credentials](/sql/relational-databases/system-catalog-views/sys-credentials-transact-sql) catalog view.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="ba151-113">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="ba151-113">Related Content</span></span>  
 <span data-ttu-id="ba151-114">[Create](../authentication-access/create-a-credential.md) [Credential CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="ba151-114">[Create a Credential](../authentication-access/create-a-credential.md) [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql)</span></span>  
  
 [<span data-ttu-id="ba151-115">Sichern von SQL Server</span><span class="sxs-lookup"><span data-stu-id="ba151-115">Securing SQL Server</span></span>](../securing-sql-server.md)  
  
  
