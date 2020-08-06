---
title: Identitätswechsel und Anmelde Informationen für Verbindungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- impersonation [CLR integration]
- security [CLR integration]
- database objects [CLR integration], connections
- connections [CLR integration]
- authentication [CLR integration]
- user impersonation [CLR integration]
- credentials [CLR integration]
- database objects [CLR integration], security
ms.assetid: 293dce7d-1db2-4657-992f-8c583d6e9ebb
author: rothja
ms.author: jroth
ms.openlocfilehash: cdbc52e07f4502adda7301ce7f635c050ed9c3c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619162"
---
# <a name="impersonation-and-credentials-for-connections"></a><span data-ttu-id="9e576-102">Identitätswechsel und Anmeldeinformationen für Verbindungen</span><span class="sxs-lookup"><span data-stu-id="9e576-102">Impersonation and Credentials for Connections</span></span>
  <span data-ttu-id="9e576-103">In der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] CLR (Common Language Runtime)-Integration ist die Verwendung der Windows-Authentifizierung zwar komplex, jedoch sicherer als die SQL Server-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9e576-103">In the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] common language runtime (CLR) integration, using Windows Authentication is complex, but is more secure than using SQL Server Authentication.</span></span> <span data-ttu-id="9e576-104">Beachten Sie bei Verwendung der Windows-Authentifizierung folgende Punkte:</span><span class="sxs-lookup"><span data-stu-id="9e576-104">When using Windows Authentication, keep in mind the following considerations.</span></span>  
  
 <span data-ttu-id="9e576-105">Standardmäßig ist für einen SQL Server-Prozess, der eine ausgehende Verbindung mit Windows herstellt, der Sicherheitskontext des Windows-Dienstkontos für SQL Server erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9e576-105">By default, a SQL Server process that connects out to Windows acquires the security context of the SQL Server Windows service account.</span></span> <span data-ttu-id="9e576-106">Es ist jedoch möglich, einer Proxyidentität eine CLR-Funktion zuzuordnen, sodass ausgehende Verbindungen einen anderen Sicherheitskontext haben als die Verbindungen des Windows-Dienstkontos.</span><span class="sxs-lookup"><span data-stu-id="9e576-106">But it is possible to map a CLR function to a proxy identity, so that its outbound connections have a different security context than that of the Windows service account.</span></span>  
  
 <span data-ttu-id="9e576-107">In einigen Fällen bietet es sich an, die Identität des Aufrufers durch Verwenden der `SqlContext.WindowsIdentity`-Eigenschaft statt Ausführen des Dienstkontos anzunehmen.</span><span class="sxs-lookup"><span data-stu-id="9e576-107">In some cases, you may want to impersonate the caller by using the `SqlContext.WindowsIdentity` property instead of running as the service account.</span></span> <span data-ttu-id="9e576-108">Die `WindowsIdentity`-Instanz repräsentiert die Identität des Clients, der den Aufrufcode aufgerufen hat, und ist nur verfügbar, wenn der Client die Windows-Authentifizierung verwendet hat.</span><span class="sxs-lookup"><span data-stu-id="9e576-108">The `WindowsIdentity` instance represents the identity of the client that invoked the calling code, and is only available when the client used Windows Authentication.</span></span> <span data-ttu-id="9e576-109">Nachdem Sie die `WindowsIdentity`-Instanz erhalten haben, können Sie `Impersonate` aufrufen, um das Sicherheitstoken des Threads zu ändern, und anschließend ADO.NET-Verbindungen im Auftrag des Clients öffnen.</span><span class="sxs-lookup"><span data-stu-id="9e576-109">After you have obtained the `WindowsIdentity` instance, you can call `Impersonate` to change the security token of the thread, and then open ADO.NET connections on behalf of the client.</span></span>  
  
 <span data-ttu-id="9e576-110">Nachdem Sie SqlContext. Windows Identity. Imitation aufgerufen haben, können Sie nicht mehr auf lokale Daten zugreifen, und Sie können nicht auf die Systemdaten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9e576-110">After you call SQLContext.WindowsIdentity.Impersonate, you cannot access local data and you cannot access system data.</span></span> <span data-ttu-id="9e576-111">Um erneut auf Daten zuzugreifen, müssen Sie WindowsImpersonationContext. Undo aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9e576-111">To access data again, you have to call WindowsImpersonationContext.Undo.</span></span>  
  
 <span data-ttu-id="9e576-112">Im folgenden Beispiel wird veranschaulicht, wie die Identität des Aufrufers mit der `SqlContext.WindowsIdentity`-Eigenschaft angenommen wird.</span><span class="sxs-lookup"><span data-stu-id="9e576-112">The following example shows how to impersonate the caller by using the `SqlContext.WindowsIdentity` property.</span></span>  
  
 <span data-ttu-id="9e576-113">Visual C#</span><span class="sxs-lookup"><span data-stu-id="9e576-113">Visual C#</span></span>  
  
```  
WindowsIdentity clientId = null;  
WindowsImpersonationContext impersonatedUser = null;  
  
clientId = SqlContext.WindowsIdentity;  
  
// This outer try block is used to protect from   
// exception filter attacks which would prevent  
// the inner finally block from executing and   
// resetting the impersonation.  
try  
{  
   try  
   {  
      impersonatedUser = clientId.Impersonate();  
      if (impersonatedUser != null)  
         return GetFileDetails(directoryPath);  
         else return null;  
   }  
   finally  
   {  
      if (impersonatedUser != null)  
         impersonatedUser.Undo();  
   }  
}  
catch  
{  
   throw;  
}  
```  
  
> [!NOTE]  
>  <span data-ttu-id="9e576-114">Informationen zu Verhaltensänderungen beim Identitätswechsel finden Sie unter [Breaking Changes to Datenbank-Engine Features in SQL Server 2014](../../../database-engine/breaking-changes-to-database-engine-features-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="9e576-114">For information about behavior changes in impersonation, see [Breaking Changes to Database Engine Features in SQL Server 2014](../../../database-engine/breaking-changes-to-database-engine-features-in-sql-server-2016.md).</span></span>  
  
 <span data-ttu-id="9e576-115">Wenn Sie die [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows-Identitätsinstanz erhalten haben, können Sie diese Instanz standardmäßig nicht an einen anderen Computer weitergeben. Die Windows-Sicherheitsinfrastruktur schränkt diese Möglichkeit standardmäßig ein.</span><span class="sxs-lookup"><span data-stu-id="9e576-115">Furthermore, if you obtained the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows identity instance, by default you cannot propagate that instance to another computer; Windows security infrastructure restricts that by default.</span></span> <span data-ttu-id="9e576-116">Es gibt jedoch einen Mechanismus, der als "Delegierung" bezeichnet wird. Dieser ermöglicht die Weitergabe von Windows-Identitäten über mehrere vertrauenswürdige Computer hinweg.</span><span class="sxs-lookup"><span data-stu-id="9e576-116">There is, however, a mechanism called "delegation" that enables propagation of Windows identities across multiple trusted computers.</span></span> <span data-ttu-id="9e576-117">Weitere Informationen zur Delegierung finden Sie im TechNet-Artikel "[Kerberos-Protokoll Übergang und eingeschränkte Delegierung](https://go.microsoft.com/fwlink/?LinkId=50419)".</span><span class="sxs-lookup"><span data-stu-id="9e576-117">You can learn more about delegation in the TechNet article, "[Kerberos Protocol Transition and Constrained Delegation](https://go.microsoft.com/fwlink/?LinkId=50419)".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e576-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9e576-118">See Also</span></span>  
 [<span data-ttu-id="9e576-119">SqlContext-Objekt</span><span class="sxs-lookup"><span data-stu-id="9e576-119">SqlContext Object</span></span>](../../clr-integration-data-access-in-process-ado-net/sqlcontext-object.md)  
  
  
