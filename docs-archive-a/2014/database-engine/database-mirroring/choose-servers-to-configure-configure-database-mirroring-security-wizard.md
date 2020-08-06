---
title: Zu konfigurierende Server auswählen (Assistent zum Konfigurieren der Sicherheit für die Datenbankspiegelung) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.choosesrvrs.f1
ms.assetid: 59e23ff3-d7ee-4e32-9629-0b54d3a258f7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 18e36f5c8ec020b3859dc847d1bbfc019817bcd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615581"
---
# <a name="choose-servers-to-configure-configure-database-mirroring-security-wizard"></a><span data-ttu-id="dc687-102">Zu konfigurierende Server auswählen (Assistent zum Konfigurieren der Sicherheit für die Datenbankspiegelung)</span><span class="sxs-lookup"><span data-stu-id="dc687-102">Choose Servers to Configure (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="dc687-103">Mithilfe dieser Seite können Sie angeben, welche Serverinstanzen nachfolgend konfiguriert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dc687-103">Use this page to specify which server instances you want to configure now.</span></span> <span data-ttu-id="dc687-104">Sie müssen mindestens eine Serverinstanz auswählen, bevor Sie den Assistenten fortsetzen können.</span><span class="sxs-lookup"><span data-stu-id="dc687-104">You must select at least one server instance before continuing the wizard.</span></span>  
  
 <span data-ttu-id="dc687-105">Wenn Sie ein Kontrollkästchen für eine Serverinstanz deaktivieren, nimmt der Assistent keine Änderung an dieser Instanz vor.</span><span class="sxs-lookup"><span data-stu-id="dc687-105">If you clear the check box for a server instance, the wizard will not make any changes to it.</span></span> <span data-ttu-id="dc687-106">Sie werden jedoch vom Assistenten aufgefordert, Informationen zur Instanz einzugeben und diese Informationen als Teil der Konfiguration der übrigen Serverinstanzen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="dc687-106">The wizard, however, will ask you to enter information about that instance and save this information as part of the configuration of the other server instances.</span></span> <span data-ttu-id="dc687-107">Wenn Sie beispielsweise das Kontrollkästchen für die Zeugenserverinstanz deaktivieren, werden Sie vom Assistenten aufgefordert, das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienstkonto des Zeugen einzugeben, da eine Anmeldung für dieses Konto als Teil der Sicherheitskonfiguration erstellt werden muss, die in den Prinzipal- und Spiegelserverinstanzen gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="dc687-107">For example, if you clear the check box for the witness server instance, the wizard will ask you to enter the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account of the witness because a login for that account must be created as part of the security configuration saved at the principal and mirror server instances.</span></span>  
  
 <span data-ttu-id="dc687-108">**So konfigurieren Sie die Datenbankspiegelung mithilfe von SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="dc687-108">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="dc687-109">Einrichten einer Datenbank-Spiegelungssitzung mithilfe der Windows-Authentifizierung &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="dc687-109">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="dc687-110">Starten des Assistenten zum Konfigurieren der Sicherheit für die Datenbankspiegelung &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="dc687-110">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="dc687-111">Tastatur</span><span class="sxs-lookup"><span data-stu-id="dc687-111">Options</span></span>  
 <span data-ttu-id="dc687-112">**Prinzipalserverinstanz**</span><span class="sxs-lookup"><span data-stu-id="dc687-112">**Principal server instance**</span></span>  
 <span data-ttu-id="dc687-113">Wählen Sie diese Option aus, um die Sicherheit für den Prinzipalserver zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="dc687-113">Select to configure security for the principal server.</span></span>  
  
 <span data-ttu-id="dc687-114">**Spiegelserverinstanz**</span><span class="sxs-lookup"><span data-stu-id="dc687-114">**Mirror server instance**</span></span>  
 <span data-ttu-id="dc687-115">Wählen Sie diese Option aus, um die Sicherheit für den Spiegelserver zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="dc687-115">Select to configure security for the mirror server.</span></span>  
  
 <span data-ttu-id="dc687-116">**Zeugenserverinstanz**</span><span class="sxs-lookup"><span data-stu-id="dc687-116">**Witness server instance**</span></span>  
 <span data-ttu-id="dc687-117">Wählen Sie diese Option aus, um die Sicherheit für den Zeugenserver zu konfigurieren (falls vorhanden).</span><span class="sxs-lookup"><span data-stu-id="dc687-117">Select to configure security for the witness server (if present).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc687-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dc687-118">See Also</span></span>  
 <span data-ttu-id="dc687-119">[Datenbankeigenschaften &#40;Seite Wird gespiegelt&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="dc687-119">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 [<span data-ttu-id="dc687-120">Datenbankspiegelung &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dc687-120">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
