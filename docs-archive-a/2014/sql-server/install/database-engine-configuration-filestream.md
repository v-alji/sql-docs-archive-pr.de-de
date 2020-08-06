---
title: 'Datenbank-Engine Konfiguration: FILESTREAM | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], about FILESTREAM
ms.assetid: 641a10a1-ae52-4d26-8f1c-a032a4aeff02
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ab12b507246a3e13ac59be213813604d531d9a28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720896"
---
# <a name="database-engine-configuration---filestream"></a><span data-ttu-id="eaf6f-102">Konfiguration der Datenbank-Engine - Filestream</span><span class="sxs-lookup"><span data-stu-id="eaf6f-102">Database Engine Configuration - Filestream</span></span>
  <span data-ttu-id="eaf6f-103">Verwenden Sie diese Seite, um FILESTREAM für diese Installation von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="eaf6f-103">Use this page to enable FILESTREAM for this installation of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="eaf6f-104">FileStream integriert [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] in ein NTFS-Dateisystem, indem `varbinary(max)` Binary Large Object (BLOB)-Daten als Dateien im Dateisystem gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="eaf6f-104">FILESTREAM integrates the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with an NTFS file system by storing `varbinary(max)` binary large object (BLOB) data as files on the file system.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="eaf6f-105">-Anweisungen können FILESTREAM-Daten eingefügt, aktualisiert, abgefragt, gesucht und gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="eaf6f-105">statements can insert, update, query, search, and back up FILESTREAM data.</span></span> <span data-ttu-id="eaf6f-106">Die Win32-Dateisystemschnittstellen stellen Streamingzugriff auf die Daten bereit.</span><span class="sxs-lookup"><span data-stu-id="eaf6f-106">Win32 file system interfaces provide streaming access to the data.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="eaf6f-107">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="eaf6f-107">UI element list</span></span>  
 <span data-ttu-id="eaf6f-108">**FILESTREAM für Transact-SQL-Zugriff aktivieren**</span><span class="sxs-lookup"><span data-stu-id="eaf6f-108">**Enable FILESTREAM for Transact-SQL access**</span></span>  
 <span data-ttu-id="eaf6f-109">Wählen Sie diese Option aus, um FILESTREAM für den [!INCLUDE[tsql](../../includes/tsql-md.md)] -Zugriff zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="eaf6f-109">Select to enable FILESTREAM for [!INCLUDE[tsql](../../includes/tsql-md.md)] access.</span></span> <span data-ttu-id="eaf6f-110">Dieses Steuerelement muss aktiviert werden, bevor die anderen Steuerelementoptionen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="eaf6f-110">This control must be checked before the other control options will be available.</span></span>  
  
 <span data-ttu-id="eaf6f-111">**FILESTREAM für E/A-Streamingzugriff auf Datei aktivieren**</span><span class="sxs-lookup"><span data-stu-id="eaf6f-111">**Enable FILESTREAM for file I/O streaming access**</span></span>  
 <span data-ttu-id="eaf6f-112">Wählen Sie diese Option aus, um den Win32-Streamingzugriff für FILESTREAM zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="eaf6f-112">Select to enable Win32 streaming access for FILESTREAM.</span></span>  
  
 <span data-ttu-id="eaf6f-113">**Windows-Freigabename**</span><span class="sxs-lookup"><span data-stu-id="eaf6f-113">**Windows share name**</span></span>  
 <span data-ttu-id="eaf6f-114">Verwenden Sie dieses Steuerelement, um den Namen der Windows-Freigabe einzugeben, in der die FILESTREAM-Daten gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="eaf6f-114">Use this control to enter the name of the Windows share in which the FILESTREAM data will be stored.</span></span>  
  
 <span data-ttu-id="eaf6f-115">**Streamingzugriff von Remoteclients auf FILESTREAM-Daten zulassen**</span><span class="sxs-lookup"><span data-stu-id="eaf6f-115">**Allow remote clients to have streaming access to FILESTREAM data**</span></span>  
 <span data-ttu-id="eaf6f-116">Aktivieren Sie dieses Steuerelement, damit Remoteclients auf diese FILESTREAM-Daten auf diesem Server zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="eaf6f-116">Select this control to allow remote clients to access this FILESTREAM data on this server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaf6f-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eaf6f-117">See Also</span></span>  
 <span data-ttu-id="eaf6f-118">[Aktivieren und Konfigurieren von FILESTREAM](../../relational-databases/blob/enable-and-configure-filestream.md) </span><span class="sxs-lookup"><span data-stu-id="eaf6f-118">[Enable and Configure FILESTREAM](../../relational-databases/blob/enable-and-configure-filestream.md) </span></span>  
 [<span data-ttu-id="eaf6f-119">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="eaf6f-119">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
