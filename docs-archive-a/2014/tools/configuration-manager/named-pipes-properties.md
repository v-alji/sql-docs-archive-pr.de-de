---
title: Named Pipes-Eigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- pipes [SQL Server]
- listening [SQL Server], pipes
- pipes [SQL Server], listening on pipes
- Named Pipes [SQL Server], listening on pipes
ms.assetid: a5fd5b8e-f889-485b-89e3-d4010ec4c6ec
author: stevestein
ms.author: sstein
ms.openlocfilehash: 80790c1cb8830a0fd132721f375a70d2574421b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617336"
---
# <a name="named-pipes-properties"></a><span data-ttu-id="a5327-102">Named Pipes-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a5327-102">Named Pipes Properties</span></span>
  <span data-ttu-id="a5327-103">Verwenden Sie die Seite **Protokoll** im Dialogfeld **Named Pipes-Eigenschaften**, um die Named Pipe anzuzeigen oder zu ändern, an der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] lauscht, wenn Sie das Named Pipes-Protokoll verwenden.</span><span class="sxs-lookup"><span data-stu-id="a5327-103">Use the **Protocol**page on the **Named Pipes Properties** dialog box to view or change the named pipe that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens to, when using the Named Pipes protocol.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a5327-104">muss neu gestartet werden, um das Protokoll zu aktivieren oder zu deaktivieren oder die Named Pipe zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a5327-104">must be restarted to enable or disable the protocol, or change the named pipe.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a5327-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="a5327-105">Options</span></span>  
 <span data-ttu-id="a5327-106">**Aktiviert**</span><span class="sxs-lookup"><span data-stu-id="a5327-106">**Enabled**</span></span>  
 <span data-ttu-id="a5327-107">Mögliche Werte sind **Yes** und **No**.</span><span class="sxs-lookup"><span data-stu-id="a5327-107">Possible values are **Yes** and **No**.</span></span>  
  
 <span data-ttu-id="a5327-108">**Pipename**</span><span class="sxs-lookup"><span data-stu-id="a5327-108">**Pipe Name**</span></span>  
 <span data-ttu-id="a5327-109">Gibt die Named Pipe an, an der von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gelauscht wird.</span><span class="sxs-lookup"><span data-stu-id="a5327-109">Specifies the named pipe on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens.</span></span> <span data-ttu-id="a5327-110">Standardmäßig lauscht [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] folgende: `\\.\pipe\sql\query` nach der Standardinstanz und `\\.\pipe\MSSQL$<instancename>\sql\query` nach einer benannten Instanz.</span><span class="sxs-lookup"><span data-stu-id="a5327-110">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens on: `\\.\pipe\sql\query` for the default instance and `\\.\pipe\MSSQL$<instancename>\sql\query` for a named instance.</span></span> <span data-ttu-id="a5327-111">Dieses Feld ist auf 2047 Zeichen begrenzt.</span><span class="sxs-lookup"><span data-stu-id="a5327-111">This field is limited to 2047 characters.</span></span>  
  
## <a name="creating-an-alternate-named-pipe"></a><span data-ttu-id="a5327-112">Erstellen einer alternativen Named Pipe</span><span class="sxs-lookup"><span data-stu-id="a5327-112">Creating an Alternate Named Pipe</span></span>  
 <span data-ttu-id="a5327-113">Zum Ändern der Named Pipe geben Sie im Feld **Pipename** einen neuen Pipenamen ein. Beenden Sie anschließend [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], und führen Sie einen Neustart aus.</span><span class="sxs-lookup"><span data-stu-id="a5327-113">To change the named pipe, type the new pipe name in the **Pipe Name** box and then stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a5327-114">Da **sql\query** bekannt ist als Named Pipe, die von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verwendet wird, kann eine Änderung der Pipe das Risiko eines Angriffs durch böswillige Programme reduzieren.</span><span class="sxs-lookup"><span data-stu-id="a5327-114">Since **sql\query** is well known as the named pipe used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], changing the pipe can help reduce the risk of attack by malicious programs.</span></span>  
  
### <a name="example"></a><span data-ttu-id="a5327-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a5327-115">Example</span></span>  
 <span data-ttu-id="a5327-116">Geben Sie **\\\\.\pipe\unit\app** ein, um an der Pipe **unit\app** zu lauschen.</span><span class="sxs-lookup"><span data-stu-id="a5327-116">Type **\\\\.\pipe\unit\app** to listen on the **unit\app** pipe.</span></span>  
  
 <span data-ttu-id="a5327-117">Geben Sie **\\\\.\pipe\acct** ein, um an der Pipe **acct** zu lauschen.</span><span class="sxs-lookup"><span data-stu-id="a5327-117">Type **\\\\.\pipe\acct** to listen on the **acct** pipe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5327-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a5327-118">See Also</span></span>  
 <span data-ttu-id="a5327-119">[Aktivieren oder Deaktivieren eines Servernetzwerkprotokolls](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="a5327-119">[Enable or Disable a Server Network Protocol](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md) </span></span>  
 <span data-ttu-id="a5327-120">[Auswählen eines Netzwerkprotokolls](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="a5327-120">[Choosing a Network Protocol](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span></span>  
 [<span data-ttu-id="a5327-121">Erstellen einer gültigen Verbindungszeichenfolge mithilfe von Named Pipes</span><span class="sxs-lookup"><span data-stu-id="a5327-121">Creating a Valid Connection String Using Named Pipes</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md)  
  
  
