---
title: Erteilen von Berechtigungen für Integration Services-Dienst | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 0c2caa68-7834-4ea0-bd77-4f3a7c86d634
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0e7ab0c2f482e5a0b1bfeaa06f38ec5a886420a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609335"
---
# <a name="grant-permissions-to-integration-services-service"></a><span data-ttu-id="33755-102">Gewähren von Berechtigungen an Integration Services-Dienst</span><span class="sxs-lookup"><span data-stu-id="33755-102">Grant Permissions to Integration Services Service</span></span>
  <span data-ttu-id="33755-103">In vorherigen Versionen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]hatten alle Benutzer in der Gruppe Benutzer standardmäßig Zugriff auf den Dienst [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , wenn Sie [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] installiert haben.</span><span class="sxs-lookup"><span data-stu-id="33755-103">In previous versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], by default when you installed [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] all users in the Users group had access to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="33755-104">Wenn Sie die aktuelle Version von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]installieren, haben Benutzer keinen Zugriff auf den Dienst [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="33755-104">When you install the current release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], users do not have access to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="33755-105">Der Dienst ist standardmäßig sicher.</span><span class="sxs-lookup"><span data-stu-id="33755-105">The service is secure by default.</span></span> <span data-ttu-id="33755-106">Nach der Installation von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] muss der Administrator Zugriff auf den Dienst gewähren.</span><span class="sxs-lookup"><span data-stu-id="33755-106">After [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is installed, the administrator must grant access to the service.</span></span>  
  
### <a name="to-grant-access-to-the-integration-services-service"></a><span data-ttu-id="33755-107">So gewähren Sie Zugriff auf den Integration Services-Dienst</span><span class="sxs-lookup"><span data-stu-id="33755-107">To grant access to the Integration Services service</span></span>  
  
1.  <span data-ttu-id="33755-108">Führen Sie "Dcomcnfg.exe" aus.</span><span class="sxs-lookup"><span data-stu-id="33755-108">Run Dcomcnfg.exe.</span></span> <span data-ttu-id="33755-109">"Dcomcnfg.exe" verfügt über eine Benutzeroberfläche, über die Sie bestimmte Einstellungen in der Registrierung ändern können.</span><span class="sxs-lookup"><span data-stu-id="33755-109">Dcomcnfg.exe provides a user interface for modifying certain settings in the registry.</span></span>  
  
2.  <span data-ttu-id="33755-110">Erweitern Sie im Dialogfeld **Komponentendienste** den Knoten „Komponentendienste“ > „Computer“ > „Arbeitsplatz“ > „DCOM-Konfiguration“.</span><span class="sxs-lookup"><span data-stu-id="33755-110">In the **Component Services** dialog, expand the Component Services > Computers > My Computer > DCOM Config node.</span></span>  
  
3.  <span data-ttu-id="33755-111">Klicken Sie mit der rechten Maustaste auf **Microsoft SQL Server Integration Services 12,0**, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="33755-111">Right-click **Microsoft SQL Server Integration Services 12.0**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="33755-112">Klicken Sie auf der Registerkarte **Sicherheit** im Abschnitt **Start- und Aktivierungsberechtigungen** auf **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="33755-112">On the **Security** tab, click **Edit** in the **Launch and Activation Permissions** area.</span></span>  
  
5.  <span data-ttu-id="33755-113">Fügen Sie Benutzer hinzu, weisen Sie ihnen entsprechende Berechtigungen zu, und klicken Sie dann auf OK.</span><span class="sxs-lookup"><span data-stu-id="33755-113">Add users and assign appropriate permissions, and then click Ok.</span></span>  
  
6.  <span data-ttu-id="33755-114">Wiederholen Sie die Schritte 4 - 5 für Zugriffsberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="33755-114">Repeat steps 4 - 5 for Access Permissions.</span></span>  
  
7.  <span data-ttu-id="33755-115">Starten Sie SQL Server Management Studio neu.</span><span class="sxs-lookup"><span data-stu-id="33755-115">Restart SQL Server Management Studio.</span></span>  
  
8.  <span data-ttu-id="33755-116">Starten Sie den [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienst neu.</span><span class="sxs-lookup"><span data-stu-id="33755-116">Restart the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Service.</span></span>  
  
  
