---
title: Arbeiten mit dem WMI-Anbieter für die Konfigurations Verwaltung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- permissions [WMI]
- connection strings [WMI]
- security [WMI]
- WMI Provider for Configuration Management, connection strings
- WMI Provider for Configuration Management, security
- late binding [WMI]
- WMI Provider for Configuration Management, late binding
- binding [WMI]
ms.assetid: 34daa922-7074-41d0-9077-042bb18c222a
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 80f311fb0abae2337f6ea4a5d5d85aaa0d320b94
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617839"
---
# <a name="working-with-the-wmi-provider-for-configuration-management"></a><span data-ttu-id="f97e6-102">Arbeiten mit dem WMI-Anbieter für die Konfigurationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="f97e6-102">Working with the WMI Provider for Configuration Management</span></span>
  <span data-ttu-id="f97e6-103">Beachten Sie vor dem Programmieren mit dem WMI-Anbieter für die Computerverwaltung die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="f97e6-103">Consider the following before programming with the WMI Provider for Computer Management:</span></span>  
  
## <a name="binding"></a><span data-ttu-id="f97e6-104">Bindung</span><span class="sxs-lookup"><span data-stu-id="f97e6-104">Binding</span></span>  
 <span data-ttu-id="f97e6-105">Der WMI-Anbieter für die Konfigurationsverwaltung ist ein COM-Objektmodell und unterstützt frühes und spätes Binden.</span><span class="sxs-lookup"><span data-stu-id="f97e6-105">The WMI Provider for Configuration Management is a COM object model and it supports early and late binding.</span></span> <span data-ttu-id="f97e6-106">Mit spätem Binden können Sie Skriptsprachen wie VBScript verwenden, um die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienste, Netzwerkeinstellungen und Aliasnamen programmgesteuert zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="f97e6-106">With late binding you can use script languages, such as VBScript, to manipulate the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, network settings, and aliases programmatically.</span></span>  
  
 <span data-ttu-id="f97e6-107">Weitere Informationen zum Programmieren von WMI-Anbieter Implementierungen mithilfe von Skriptsprachen finden Sie auf der [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN- [Website](https://go.microsoft.com/fwlink/?linkid=15426).</span><span class="sxs-lookup"><span data-stu-id="f97e6-107">For further information about programming WMI Provider implementations using scripting languages, see the [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN [Web site](https://go.microsoft.com/fwlink/?linkid=15426).</span></span>  
  
## <a name="specifying-a-connection-string"></a><span data-ttu-id="f97e6-108">Angeben einer Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f97e6-108">Specifying a Connection String</span></span>  
 <span data-ttu-id="f97e6-109">Anwendungen leiten den WMI-Anbieter für die Konfigurationsverwaltung an eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] weiter, indem sie eine Verbindung zu einem vom Anbieter definierten WMI-Namespace herstellen.</span><span class="sxs-lookup"><span data-stu-id="f97e6-109">Applications direct the WMI Provider for Configuration Management to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by connecting to a WMI namespace defined by the provider.</span></span> <span data-ttu-id="f97e6-110">Der Windows-WMI-Dienst ordnet der Anbieter-DLL diesen Namespace zu und lädt sie in den Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="f97e6-110">The Windows WMI service maps this namespace to the provider DLL and loads it into memory.</span></span> <span data-ttu-id="f97e6-111">Alle Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] werden mit einem einzigen WMI-Namespace dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f97e6-111">All instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are represented with a single WMI namespace.</span></span> <span data-ttu-id="f97e6-112">Der Namespace lautet standardmäßig</span><span class="sxs-lookup"><span data-stu-id="f97e6-112">The namespace defaults to</span></span>  
  
```  
\\.\root\Microsoft\SqlServer\ComputerManagement12\instance_name  
```  
  
 <span data-ttu-id="f97e6-113">wobei `instance_name` in einer Standardinstallation von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] standardmäßig auf `MSSQLSERVER` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="f97e6-113">where `instance_name` defaults to `MSSQLSERVER` in a default installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f97e6-114">**Hinweis:** Wenn Sie über die Windows-Firewall eine Verbindung herstellen, müssen Sie sicherstellen, dass Ihre Computer ordnungsgemäß konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="f97e6-114">**Note:** If you are connecting through Windows Firewall you will need to make sure your computers are configured appropriately.</span></span> <span data-ttu-id="f97e6-115">Weitere Informationen finden Sie im Artikel "Herstellen einer Verbindung über die Windows-Firewall" in der Windows-Verwaltungsinstrumentation Dokumentation auf der [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN- [Website](https://go.microsoft.com/fwlink/?linkid=15426).</span><span class="sxs-lookup"><span data-stu-id="f97e6-115">See the "Connecting Through Windows Firewall" article in the Windows Management Instrumentation documentation on [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN [Web site](https://go.microsoft.com/fwlink/?linkid=15426).</span></span>  
  
## <a name="permissions-and-server-authentication"></a><span data-ttu-id="f97e6-116">Berechtigungen und Serverauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="f97e6-116">Permissions and Server Authentication</span></span>  
 <span data-ttu-id="f97e6-117">Für den Zugriff auf den WMI-Anbieter für die Konfigurationsverwaltung muss das WMI-Verwaltungsskript des Clients im Kontext eines Administrators auf dem Zielcomputer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f97e6-117">To access the WMI Provider for Configuration Management, the client WMI management script must be running in the context of an administrator on the target computer.</span></span> <span data-ttu-id="f97e6-118">Sie müssen ein Mitglied der lokalen Windows-Administratorengruppe auf dem Computer sein, den Sie verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="f97e6-118">You need to be a member of the local Windows administrators group on the computer you want to manage.</span></span>  
  
 <span data-ttu-id="f97e6-119">Der Administrator kann Gruppenrichtlinien festlegen, um den Benutzerzugriff auf WMI-Anbieter zu kontrollieren.</span><span class="sxs-lookup"><span data-stu-id="f97e6-119">The administrator can set group policies to control user access to WMI providers.</span></span> <span data-ttu-id="f97e6-120">Weitere Informationen zum Festlegen von Gruppenrichtlinien finden Sie im Abschnitt zu Gruppenrichtlinien und MMC in der Hilfe zum [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Konfigurations-Manager.</span><span class="sxs-lookup"><span data-stu-id="f97e6-120">For more information about setting group policies see "Group Policy and MMC" in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager Help.</span></span>  
  
 <span data-ttu-id="f97e6-121">Das WMI-Verwaltungsskript kann zum Aktualisieren des Kontos verwendet werden, unter dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienste ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f97e6-121">The WMI management script can be used to update the account under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services run.</span></span>  
  
 <span data-ttu-id="f97e6-122">Sicherheitszertifikate werden vom WMI-Anbieter für die Konfigurationsverwaltung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f97e6-122">Security certificates are supported by the WMI Provider for Configuration Management.</span></span> <span data-ttu-id="f97e6-123">Weitere Informationen zu Zertifikaten finden Sie in der [Verschlüsselungs Hierarchie](../security/encryption/encryption-hierarchy.md).</span><span class="sxs-lookup"><span data-stu-id="f97e6-123">For more information about certificates, see [Encryption Hierarchy](../security/encryption/encryption-hierarchy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f97e6-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f97e6-124">See Also</span></span>  
 [<span data-ttu-id="f97e6-125">SQL Server-Konfigurations-Manager</span><span class="sxs-lookup"><span data-stu-id="f97e6-125">SQL Server Configuration Manager</span></span>](../sql-server-configuration-manager.md)  
  
  
