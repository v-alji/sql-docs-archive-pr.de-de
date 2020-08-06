---
title: Sichere Kennwörter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- logins [SQL Server], passwords
- passwords [SQL Server], strong
- symbols [SQL Server]
- security [SQL Server], passwords
- passwords [SQL Server], symbols
- characters [SQL Server], password policies
- strong passwords [SQL Server]
ms.assetid: 338548f4-c4d8-47ca-b597-5c9c0f2fa205
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 5e878e0de5ee1f496dcc981182d42f5898838c64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697665"
---
# <a name="strong-passwords"></a><span data-ttu-id="e1a57-102">Sichere Kennwörter</span><span class="sxs-lookup"><span data-stu-id="e1a57-102">Strong Passwords</span></span>
  <span data-ttu-id="e1a57-103">Kennwörter sind möglicherweise das schwächste Glied bei der Bereitstellung von Serversicherheit.</span><span class="sxs-lookup"><span data-stu-id="e1a57-103">Passwords can be the weakest link in a server security deployment.</span></span> <span data-ttu-id="e1a57-104">Bei der Auswahl eines Kennworts ist immer größte Vorsicht geboten.</span><span class="sxs-lookup"><span data-stu-id="e1a57-104">You should always take great care when you select a password.</span></span> <span data-ttu-id="e1a57-105">Ein sicheres Kennwort weist die folgenden Merkmale auf:</span><span class="sxs-lookup"><span data-stu-id="e1a57-105">A strong password has the following characteristics:</span></span>  
  
-   <span data-ttu-id="e1a57-106">Es ist wenigstens 8 Zeichen lang.</span><span class="sxs-lookup"><span data-stu-id="e1a57-106">Is at least 8 characters long.</span></span>  
  
-   <span data-ttu-id="e1a57-107">Es besteht aus einer Kombination aus Buchstaben, Ziffern und Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="e1a57-107">Combines letters, numbers, and symbol characters within the password.</span></span>  
  
-   <span data-ttu-id="e1a57-108">Es wird in keinem Wörterbuch aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="e1a57-108">Is not found in a dictionary.</span></span>  
  
-   <span data-ttu-id="e1a57-109">Es handelt sich nicht um einen Befehlsnamen.</span><span class="sxs-lookup"><span data-stu-id="e1a57-109">Is not the name of a command.</span></span>  
  
-   <span data-ttu-id="e1a57-110">Es handelt sich nicht um den Namen einer Person.</span><span class="sxs-lookup"><span data-stu-id="e1a57-110">Is not the name of a person.</span></span>  
  
-   <span data-ttu-id="e1a57-111">Es handelt sich nicht um den Namen eines Benutzers.</span><span class="sxs-lookup"><span data-stu-id="e1a57-111">Is not the name of a user.</span></span>  
  
-   <span data-ttu-id="e1a57-112">Es handelt sich nicht um einen Computernamen.</span><span class="sxs-lookup"><span data-stu-id="e1a57-112">Is not the name of a computer.</span></span>  
  
-   <span data-ttu-id="e1a57-113">Es wird regelmäßig geändert.</span><span class="sxs-lookup"><span data-stu-id="e1a57-113">Is changed regularly.</span></span>  
  
-   <span data-ttu-id="e1a57-114">Es unterscheidet sich deutlich von früheren Kennwörtern.</span><span class="sxs-lookup"><span data-stu-id="e1a57-114">Is significantly different from previous passwords.</span></span>  
  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="e1a57-115">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Kennwörter können bis zu 128 Zeichen (einschließlich Buchstaben, Sonderzeichen und Ziffern) enthalten.</span><span class="sxs-lookup"><span data-stu-id="e1a57-115">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] passwords can contain up to 128 characters, including letters, symbols, and digits.</span></span> <span data-ttu-id="e1a57-116">Bestimmte Symbole müssen jedoch von doppelten Anführungszeichen (") oder eckigen Klammern ([ ]) eingeschlossen werden, da Benutzernamen, Benutzer, Rollen und Kennwörter häufig in [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e1a57-116">Because logins, user names, roles, and passwords are frequently used in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, certain symbols must be enclosed by double quotation marks (") or square brackets ([ ]).</span></span> <span data-ttu-id="e1a57-117">Verwenden Sie diese Trennzeichen in [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen, wenn die Anmeldenamen, Benutzer, Rollen und Kennwörter von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] folgende Merkmale aufweisen:</span><span class="sxs-lookup"><span data-stu-id="e1a57-117">Use these delimiters in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login, user, role, or password has the following characteristics:</span></span>  
  
-   <span data-ttu-id="e1a57-118">Das Element enthält oder beginnt mit einem Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="e1a57-118">Contains or starts with a space character.</span></span>  
  
-   <span data-ttu-id="e1a57-119">Das Element beginnt mit dem Zeichen $ oder \@.</span><span class="sxs-lookup"><span data-stu-id="e1a57-119">Starts with the $ or \@ character.</span></span>  
  
 <span data-ttu-id="e1a57-120">Bei Verwendung in einer OLE DB- oder ODBC-Verbindungszeichenfolge dürfen die folgenden Zeichen nicht in einem Anmeldenamen oder Kennwort enthalten sein: [] {}() , ; ?</span><span class="sxs-lookup"><span data-stu-id="e1a57-120">If used in an OLE DB or ODBC connection string, a login or password must not contain the following characters: [] {}() , ; ?</span></span> <span data-ttu-id="e1a57-121">\* !</span><span class="sxs-lookup"><span data-stu-id="e1a57-121">\* !</span></span> <span data-ttu-id="e1a57-122">\@.</span><span class="sxs-lookup"><span data-stu-id="e1a57-122">\@.</span></span> <span data-ttu-id="e1a57-123">Mithilfe dieser Zeichen wird entweder eine Verbindung initialisiert oder Verbindungswerte werden getrennt.</span><span class="sxs-lookup"><span data-stu-id="e1a57-123">These characters are used to either initialize a connection or separate connection values.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="e1a57-124">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="e1a57-124">Related Content</span></span>  
 [<span data-ttu-id="e1a57-125">Kennwortrichtlinie</span><span class="sxs-lookup"><span data-stu-id="e1a57-125">Password Policy</span></span>](password-policy.md)  
  
  
