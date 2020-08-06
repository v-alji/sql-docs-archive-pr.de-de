---
title: SQL Server-Agent Dienst kann SQL Server Authentifizierung nicht verwenden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- authentication [SQL Server Agent]
- SQL Server Authentication [SQL Server Agent]
ms.assetid: c39f3ec3-fc2c-4c12-940f-60d8d3d17660
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 32188b1c47168aefbca914fa15f71850df716153
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619554"
---
# <a name="sql-server-agent-service-cannot-use-sql-server-authentication"></a><span data-ttu-id="67c58-102">Die SQL Server-Authentifizierung kann vom SQL Server-Agent-Dienst nicht verwendet werden</span><span class="sxs-lookup"><span data-stu-id="67c58-102">SQL Server Agent Service cannot use SQL Server Authentication</span></span>
  <span data-ttu-id="67c58-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent unterstützt nur die Windows-Authentifizierung, wenn der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent-Dienst eine Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herstellt.</span><span class="sxs-lookup"><span data-stu-id="67c58-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent only supports Windows Authentication when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service connects to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="component"></a><span data-ttu-id="67c58-104">Komponente</span><span class="sxs-lookup"><span data-stu-id="67c58-104">Component</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="67c58-105">-Agent</span><span class="sxs-lookup"><span data-stu-id="67c58-105">Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="67c58-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="67c58-106">Description</span></span>  
 <span data-ttu-id="67c58-107">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] kann sich der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent-Dienst nur mit der Windows-Authentifizierung bei der Datenbank anmelden.</span><span class="sxs-lookup"><span data-stu-id="67c58-107">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service can only log on to the database using Windows Authentication.</span></span> <span data-ttu-id="67c58-108">Dies bedeutet, dass das- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent-Dienst Konto ein Benutzer sein muss [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="67c58-108">This means that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account must be a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user.</span></span>  
  
 <span data-ttu-id="67c58-109">Weitere Informationen finden Sie in den Themen "Sicherheit bei der automatischen Verwaltung" und "Implementieren der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent-Sicherheit" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="67c58-109">For more information, see the topics "Security for Automatic Administration" and "Implementing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Security" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67c58-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="67c58-110">See Also</span></span>  
 [<span data-ttu-id="67c58-111">Probleme beim Aktualisieren des SQL Server-Agents</span><span class="sxs-lookup"><span data-stu-id="67c58-111">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
