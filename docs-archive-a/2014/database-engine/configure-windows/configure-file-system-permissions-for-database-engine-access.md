---
title: Konfigurieren von Dateisystemberechtigungen für den Datenbank-Engine-Zugriff | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- file system permissions
- service account [SQL Server], file system permissions
- permissions [SQL Server], file system
ms.assetid: 78bba43c-4edb-4216-84ac-d6246ae5546d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1d9abbd095f2d5be7415ed28a17fb710ff8ab504
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622893"
---
# <a name="configure-file-system-permissions-for-database-engine-access"></a><span data-ttu-id="415dc-102">Konfigurieren von Dateisystemberechtigungen für den Datenbank-Engine-Zugriff</span><span class="sxs-lookup"><span data-stu-id="415dc-102">Configure File System Permissions for Database Engine Access</span></span>
  <span data-ttu-id="415dc-103">In diesem Thema wird beschrieben, wie [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]Dateisystemzugriff auf den Ort gewährt wird, an dem die Datenbankdateien gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="415dc-103">This topic describes how to grant the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], file system access to the location where database files are stored.</span></span> <span data-ttu-id="415dc-104">Der [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Dienst muss vom Windows-Dateisystem die Berechtigung für den Zugriff auf den Dateiordner erhalten, in dem die Datenbankdateien gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="415dc-104">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] service must have permission of the Windows file system to access the file folder where database files are stored.</span></span> <span data-ttu-id="415dc-105">Die Berechtigung für den Zugriff auf den Standardspeicherort wird bei der Ausführung von Setup konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="415dc-105">Permission to the default location is configured during setup.</span></span> <span data-ttu-id="415dc-106">Wenn Sie Datenbankdateien an einem anderen Ort ablegen, müssen Sie u. U. die folgenden Schritte ausführen, um dem [!INCLUDE[ssDE](../../includes/ssde-md.md)] die Vollzugriffsberechtigung auf diesen Ort zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="415dc-106">If you place your database files in a different location, you might need to follow these steps to grant the [!INCLUDE[ssDE](../../includes/ssde-md.md)] the full control permission to that location.</span></span>  
  
 <span data-ttu-id="415dc-107">Ab [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] werden der Pro-Dienst-SID Berechtigungen für alle enthaltenen Dienste zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="415dc-107">Beginning with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] permissions are assigned to the per-service SID for each of its services.</span></span> <span data-ttu-id="415dc-108">Dieses System unterstützt die Dienstisolierung und den gründlichen Schutz.</span><span class="sxs-lookup"><span data-stu-id="415dc-108">This system helps provide service isolation and defense in depth.</span></span> <span data-ttu-id="415dc-109">Die Pro-Dienst-SID ergibt sich aus dem Dienstnamen und ist für jeden Dienst eindeutig.</span><span class="sxs-lookup"><span data-stu-id="415dc-109">The per-service SID is derived from the service name and is unique to each service.</span></span> <span data-ttu-id="415dc-110">Im Thema [Konfigurieren von Windows-Dienstkonten und -Berechtigungen](configure-windows-service-accounts-and-permissions.md) werden die Pro-Dienst-SID beschrieben und Namen im Abschnitt **Windows-Berechtigungen und Rechte**bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="415dc-110">The topic [Configure Windows Service Accounts and Permissions](configure-windows-service-accounts-and-permissions.md) describes the per-service SID and provides the names in the section **Windows Privileges and Rights**.</span></span> <span data-ttu-id="415dc-111">Der Pro-Dienst-SID muss die Zugriffsberechtigung für den Dateispeicherort zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="415dc-111">It is the per-service SID that must be assigned the access permission on the file location.</span></span>  
  
## <a name="to-grant-file-system-permission-to-the-per-service-sid"></a><span data-ttu-id="415dc-112">So gewähren Sie der Pro-Dienst-SID eine Dateisystemberechtigung</span><span class="sxs-lookup"><span data-stu-id="415dc-112">To Grant File System Permission to the Per-service SID</span></span>  
  
1.  <span data-ttu-id="415dc-113">Navigieren Sie im Windows-Explorer zu dem Speicherort im Dateisystem, an dem die Datenbankdateien gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="415dc-113">Using Windows Explorer, navigate to the file system location where the database files are stored.</span></span> <span data-ttu-id="415dc-114">Klicken Sie mit der rechten Maustaste auf den Dateisystemordner, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="415dc-114">Right-click the file system folder, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="415dc-115">Klicken Sie auf der Registerkarte **Sicherheit** auf **Bearbeiten**und dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="415dc-115">On the **Security** tab, click **Edit**, and then **Add**.</span></span>  
  
3.  <span data-ttu-id="415dc-116">Klicken Sie im Dialogfeld zum **Auswählen von Benutzern, Computer, Dienstkonto oder Gruppen** oben in der Speicherortliste auf **Speicherorte**, wählen Sie den Computernamen aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="415dc-116">In the **Select Users, Computer, Service Account, or Groups** dialog box, click **Locations**, at the top of the location list, select your computer name, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="415dc-117">Geben Sie im Feld **Geben Sie die zu ausgewäfenden Objektnamen** ein den Namen der pro-Dienst-SID ein, die im Thema **Konfigurieren von Windows-Dienst Konten und-Berechtigungen**aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="415dc-117">In the **Enter the object names to select** box, type the name of the per-service SID listed in the Books Online topic **Configure Windows Service Accounts and Permissions**.</span></span> <span data-ttu-id="415dc-118">(Verwenden Sie für die [!INCLUDE[ssDE](../../includes/ssde-md.md)] pro-Dienst-SID **NT service\mssqlserver** für eine Standard Instanz oder **NT service\mssql $ instanceName** für eine benannte Instanz.)</span><span class="sxs-lookup"><span data-stu-id="415dc-118">(For the [!INCLUDE[ssDE](../../includes/ssde-md.md)] per service SID, use **NT SERVICE\MSSQLSERVER** for a default instance, or **NT SERVICE\MSSQL$InstanceName** for a named instance.)</span></span>  
  
5.  <span data-ttu-id="415dc-119">Klicken Sie auf **Namen überprüfen** , um den Eintrag zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="415dc-119">Click **Check Names** to validate the entry.</span></span> <span data-ttu-id="415dc-120">Bei der Überprüfung wird häufig der Fehler zurückgegeben, dass der Name nicht gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="415dc-120">The validation often fails, and might advise you that the name was not found.</span></span> <span data-ttu-id="415dc-121">Wenn Sie auf **OK**klicken, wird das Dialogfeld **Mehrere Namen gefunden** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="415dc-121">When you click **OK**, a **Multiple Names Found** dialog box appears.</span></span>  
  
6.  <span data-ttu-id="415dc-122">Wählen Sie nun die pro-Dienst-SID aus, entweder **MSSQLSERVER** oder **NT service\mssql $ instanceName**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="415dc-122">Now select the per-service SID, either **MSSQLSERVER** or **NT SERVICE\MSSQL$InstanceName**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="415dc-123">Klicken Sie erneut auf **OK** , um zum Dialogfeld **Berechtigungen** zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="415dc-123">Click **OK** again to return to the **Permissions** dialog box.</span></span>  
  
8.  <span data-ttu-id="415dc-124">Wählen Sie im Feld **Gruppen-oder Benutzer** Namen die pro-Dienst-SID aus, und aktivieren Sie dann im Feld **Berechtigungen für** \<name> das Kontrollkästchen **zulassen** für **voll**Zugriff.</span><span class="sxs-lookup"><span data-stu-id="415dc-124">In the **Group or user** names box, select the per-service SID, and then in the **Permissions for** \<name> box, select the **Allow** check box for **Full control**.</span></span>  
  
9. <span data-ttu-id="415dc-125">Klicken Sie auf **Anwenden**und dann zweimal auf **OK** , um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="415dc-125">Click **Apply**, and then click **OK** twice to exit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="415dc-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="415dc-126">See Also</span></span>  
 <span data-ttu-id="415dc-127">[Verwalten der Datenbank-Engine-Dienste](manage-the-database-engine-services.md) </span><span class="sxs-lookup"><span data-stu-id="415dc-127">[Manage the Database Engine Services](manage-the-database-engine-services.md) </span></span>  
 <span data-ttu-id="415dc-128">[Verschieben von Systemdatenbanken](../../relational-databases/databases/system-databases.md) </span><span class="sxs-lookup"><span data-stu-id="415dc-128">[Move System Databases](../../relational-databases/databases/system-databases.md) </span></span>  
 [<span data-ttu-id="415dc-129">Verschieben von Benutzerdatenbanken</span><span class="sxs-lookup"><span data-stu-id="415dc-129">Move User Databases</span></span>](../../relational-databases/databases/move-user-databases.md)  
  
  
