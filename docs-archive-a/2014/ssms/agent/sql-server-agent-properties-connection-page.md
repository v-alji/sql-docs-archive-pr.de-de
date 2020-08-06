---
title: SQL Server-Agent-Eigenschaften (Seite Verbindung)| Microsoft-Dokumente
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.connection.f1
ms.assetid: d6a677ff-60ad-47ba-a0cb-df4193b165e0
author: stevestein
ms.author: sstein
ms.openlocfilehash: ec9ae575f1ced510d95256d6827435e5b6ad89d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621308"
---
# <a name="sql-server-agent-properties-connection-page"></a><span data-ttu-id="38660-102">SQL Server-Agent-Eigenschaften (Seite Verbindung)</span><span class="sxs-lookup"><span data-stu-id="38660-102">SQL Server Agent Properties (Connection Page)</span></span>
  <span data-ttu-id="38660-103">Verwenden Sie diese Seite, um die Einstellungen für die Verbindung zwischen dem-Agent-Dienst und anzuzeigen und [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zu ändern [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38660-103">Use this page to view and modify the settings for the connection from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="38660-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="38660-104">Options</span></span>  
 <span data-ttu-id="38660-105">**Aliasname für den lokalen Hostserver**</span><span class="sxs-lookup"><span data-stu-id="38660-105">**Alias local host server**</span></span>  
 <span data-ttu-id="38660-106">Gibt den Aliasnamen an, der beim Verbinden zur lokalen Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="38660-106">Specifies the alias to use to connect to the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="38660-107">Wenn Sie die Standardoptionen der Verbindung für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent nicht verwenden können, definieren Sie einen Alias für die Instanz, und geben Sie den Aliasnamen hier an.</span><span class="sxs-lookup"><span data-stu-id="38660-107">If you cannot use the default connection options for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, define an alias for the instance and specify the alias here.</span></span>  
  
 <span data-ttu-id="38660-108">**Windows-Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="38660-108">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="38660-109">Legt die [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Authentifizierung als die Authentifizierungsmethode fest, die für die Verbindung mit der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="38660-109">Sets [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Authentication as the authentication method used to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="38660-110">-Agent wird als das Konto verbunden, als das der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="38660-110">Agent connects as the account that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service runs as.</span></span>  
  
 <span data-ttu-id="38660-111">**SQL Server-Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="38660-111">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="38660-112">Legt die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Authentifizierung als die Authentifizierungsmethode fest, die für die Verbindung mit der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="38660-112">Sets [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication as the authentication method used to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="38660-113">-Authentifizierung wird aus Gründen der Abwärtskompatibilität bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="38660-113">Authentication is provided for backward compatibility.</span></span> <span data-ttu-id="38660-114">Aus Sicherheitsgründen sollte möglichst die Windows-Authentifizierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="38660-114">For improved security, use Windows Authentication if possible.</span></span>  
  
 <span data-ttu-id="38660-115">**Anmeldung**</span><span class="sxs-lookup"><span data-stu-id="38660-115">**Login**</span></span>  
 <span data-ttu-id="38660-116">Gibt den Anmeldenamen an, der für die Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="38660-116">Specifies the login name to use to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="38660-117">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="38660-117">**Password**</span></span>  
 <span data-ttu-id="38660-118">Gibt das Kennwort an, das für die Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="38660-118">Specifies the password to use to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
  
