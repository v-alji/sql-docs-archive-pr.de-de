---
title: Sichere Entwicklung (Reporting Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- development security [Reporting Services]
- security [Reporting Services], development
- security [Reporting Services], strategies
ms.assetid: 12161a6c-b93b-4312-9d27-0c922561eb9b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7ba284b9013c5da6b03cce06ec72deccb045cfad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630525"
---
# <a name="secure-development-reporting-services"></a><span data-ttu-id="3c555-102">Sichere Entwicklung (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="3c555-102">Secure Development (Reporting Services)</span></span>
  <span data-ttu-id="3c555-103">Das [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] bietet ein stabiles Sicherheitssystem, das Code in stark eingeschränkten, vom Administrator definierten Sicherheitskontexten ausführt.</span><span class="sxs-lookup"><span data-stu-id="3c555-103">The [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] provides a robust security system that can run code in tightly constrained, administrator-defined security contexts.</span></span> [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="3c555-104">verwendet das Sicherheitssystem von [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], das als Codezugriffssicherheit (oder beweisbasierte Sicherheit) bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="3c555-104">uses the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] security system, known as code access security (or evidence-based security).</span></span> <span data-ttu-id="3c555-105">Wenn Codezugriffssicherheit vorliegt, ist der Benutzer vertrauenswürdig genug, um auf eine Ressource zuzugreifen; ist aber der Code, den der Benutzer ausführt, nicht vertrauenswürdig, wird der Zugriff auf diese Ressource verweigert.</span><span class="sxs-lookup"><span data-stu-id="3c555-105">Under code access security, a user may be trusted to access a resource, but if the code the user executes is not trusted, access to the resource will be denied.</span></span>  
  
 <span data-ttu-id="3c555-106">Da die Sicherheit auf dem Code (und nicht auf bestimmten Benutzern) basiert, ist es möglich, Sicherheit für benutzerdefinierte Assemblys oder Daten, Übermittlungs-, Rendering- und Sicherheitserweiterungen, die Sie für [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] entwickeln, auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="3c555-106">Security based on code, as opposed to specific users, permits security to be expressed for custom assemblies or data, delivery, rendering, and security extensions that you develop for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="3c555-107">Ihr Erweiterungscode kann von beliebig vielen [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Benutzern ausgeführt werden, die alle zum Zeitpunkt der Entwicklung unbekannt sind.</span><span class="sxs-lookup"><span data-stu-id="3c555-107">Your extension code may be executed by any number of [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] users, all of whom are unknown at development time.</span></span> <span data-ttu-id="3c555-108">Die benutzerdefinierten Assemblys oder die Erweiterungen, die Sie entwickeln, erfordern bestimmte Sicherheitsrichtlinien in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c555-108">The custom assemblies or extensions that you develop require specific security policies in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="3c555-109">Diese Sicherheitsrichtlinien werden in [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] als Typen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="3c555-109">These security policies are represented as types in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="3c555-110">Weitere Informationen über die Codezugriffssicherheit finden Sie unter "Codezugriffssicherheit" in der Dokumentation von [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c555-110">For a more information about code access security, see "Code Access Security" in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] documentation.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3c555-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="3c555-111">In This Section</span></span>  
 [<span data-ttu-id="3c555-112">Code Access Security in Reporting Services (Codezugriffssicherheit in Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="3c555-112">Code Access Security in Reporting Services</span></span>](code-access-security-in-reporting-services.md)  
 <span data-ttu-id="3c555-113">Gibt eine Einführung in Codezugriffssicherheit und Richtlinienkonfigurationen für benutzerdefinierte Assemblys und Erweiterungen in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c555-113">Introduces code access security and policy configuration for custom assemblies and extensions in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="3c555-114">Understanding Security Policies (Grundlegendes zu Sicherheitsrichtlinien)</span><span class="sxs-lookup"><span data-stu-id="3c555-114">Understanding Security Policies</span></span>](understanding-security-policies.md)  
 <span data-ttu-id="3c555-115">Beschreibt die verschiedenen Assemblytypen in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] und die Auswirkungen der Codezugriffssicherheit auf die Codeberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="3c555-115">Describes the various assembly types in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] and how code access security affects code permissions.</span></span>  
  
 [<span data-ttu-id="3c555-116">Using Reporting Services Security Policy Files (Verwenden von Reporting Services-Sicherheitsrichtliniendateien)</span><span class="sxs-lookup"><span data-stu-id="3c555-116">Using Reporting Services Security Policy Files</span></span>](using-reporting-services-security-policy-files.md)  
 <span data-ttu-id="3c555-117">Beschreibt die verschiedenen [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Komponenten und die entsprechenden Richtlinienkonfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="3c555-117">Describes the different [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] components and the corresponding policy configuration files.</span></span>  
  
  
