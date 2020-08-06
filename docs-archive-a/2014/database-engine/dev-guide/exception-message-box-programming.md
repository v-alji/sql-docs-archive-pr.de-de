---
title: Programmierung von Ausnahme Meldungs Feldern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- ExceptionMessageBox class, about ExceptionMessageBox class
- exception message box [SQL Server], about exception message box
- exception message box [SQL Server]
- interfaces [SQL Server]
- exceptions [SQL Server]
- messages [SQL Server], exception message box
ms.assetid: 0b1ba514-6959-4e69-bfd2-3cf3c1ac4b9c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b2425169f838199ce24b4331dd57c74b480adf62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726217"
---
# <a name="exception-message-box-programming"></a><span data-ttu-id="6efb4-102">Programmierung eines Ausnahmemeldungsfelds</span><span class="sxs-lookup"><span data-stu-id="6efb4-102">Exception Message Box Programming</span></span>
  <span data-ttu-id="6efb4-103">Das Ausnahme Meldungs Feld ist eine programmgesteuerte Schnittstelle, die mit grafischen Komponenten von installiert und verwendet wird [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6efb4-103">The exception message box is a programmatic interface that is installed with and used by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] graphical components.</span></span> <span data-ttu-id="6efb4-104">Das Ausnahmemeldungsfeld ist eine unterstützte verwaltete Assembly, die Sie in Ihren Anwendungen verwenden können, um die Steuerungsmöglichkeiten für Meldungen bedeutend zu erweitern, Benutzern die Möglichkeit zum Speichern von Fehlermeldungen zur späteren Bezugnahme zu geben und Hilfe zu Meldungen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="6efb4-104">The exception message box is a supported managed assembly that you can use in your applications to provide significantly more control over the messaging experience and to give your users the options to save error message content for later reference and to get help on messages.</span></span> <span data-ttu-id="6efb4-105">Weil das Ausnahmemeldungsfeld von allen Editionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mit Ausnahme von [!INCLUDE[ssEW](../../includes/ssew-md.md)] installiert wird, können Sie es ohne zusätzliche Konfiguration auf jedem Computer verwenden, auf dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Clientkomponenten installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6efb4-105">Because the exception message box is installed by all editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] except [!INCLUDE[ssEW](../../includes/ssew-md.md)], you can use it with no additional configuration on any computer on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client components have been installed.</span></span>  
  
 <span data-ttu-id="6efb4-106">Die <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox>-Klasse im <xref:Microsoft.SqlServer.MessageBox>-Namespace verfügt über die gesamte Funktionalität der <xref:System.Windows.Forms.MessageBox>-Klasse und mehr.</span><span class="sxs-lookup"><span data-stu-id="6efb4-106">The <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> class in the <xref:Microsoft.SqlServer.MessageBox> namespace has all the functionality of the <xref:System.Windows.Forms.MessageBox> class and more.</span></span> <span data-ttu-id="6efb4-107">Die <xref:System.Windows.Forms.MessageBox>-Klasse wurde für die Handhabung von Ausnahmen in verwaltetem Code konzipiert und ist somit ideal für alle Aufgaben, für die <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="6efb4-107">Ideal for any tasks for which <xref:System.Windows.Forms.MessageBox> may be used, <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> is designed to elegantly handle managed code exceptions.</span></span> <span data-ttu-id="6efb4-108">Durch das Ausnahmemeldungsfeld werden folgende Aktionen ermöglicht:</span><span class="sxs-lookup"><span data-stu-id="6efb4-108">The exception message box allows you to do the following:</span></span>  
  
-   <span data-ttu-id="6efb4-109">Bereitstellen von benutzerdefiniertem Schaltflächentext für bis zu fünf Schaltflächen.</span><span class="sxs-lookup"><span data-stu-id="6efb4-109">Provide customized button text for up to five buttons.</span></span> <span data-ttu-id="6efb4-110">Die Größe von Schaltflächen und Dialogfeldern wird automatisch an verschiedene Textlängen angepasst.</span><span class="sxs-lookup"><span data-stu-id="6efb4-110">Buttons and the dialog box resize automatically for different text lengths.</span></span>  
  
-   <span data-ttu-id="6efb4-111">Ermöglichen, dass Benutzer den Meldungstitel, den Meldungstext, Schaltflächentexte und Links mit Hilfethemen (sofern vorhanden) in die Zwischenablage kopieren oder diese Informationen in einer E-Mail-Nachricht senden</span><span class="sxs-lookup"><span data-stu-id="6efb4-111">Allow users to easily copy the message title, text, button text, and help links (if any) to the Clipboard or send this information in an e-mail message.</span></span>  
  
-   <span data-ttu-id="6efb4-112">Zeigen Sie alle zugrunde liegenden Ausnahmen und Fehler in einer hierarchischen Beziehungsstruktur an, wenn Benutzer auf **zusätzliche Informationen**klicken.</span><span class="sxs-lookup"><span data-stu-id="6efb4-112">Display all underlying exceptions and errors in a hierarchical relationship tree when users click **Additional Information**.</span></span>  
  
-   <span data-ttu-id="6efb4-113">Ermöglichen, dass die Benutzer entscheiden können, ob die Meldung angezeigt werden soll, wenn die gleiche Ausnahme erneut auftritt.</span><span class="sxs-lookup"><span data-stu-id="6efb4-113">Allow users to decide whether to display the message when the same exception occurs again.</span></span>  
  
-   <span data-ttu-id="6efb4-114">Zugriff auf ein Onlinehilfesystem über einen der Ausnahme zugeordneten Hilfelink</span><span class="sxs-lookup"><span data-stu-id="6efb4-114">Access an online help system by using a help link associated with the exception.</span></span>  
  
 <span data-ttu-id="6efb4-115">Weitere Informationen finden Sie unter [Programm Exception Message Box](../../../2014/database-engine/dev-guide/program-exception-message-box.md).</span><span class="sxs-lookup"><span data-stu-id="6efb4-115">For more information, see [Program Exception Message Box](../../../2014/database-engine/dev-guide/program-exception-message-box.md).</span></span>  
  
  
