---
title: Symmetrische Schlüssel für Benutzerdatenbanken | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 3333ab5b-2518-4753-a0a8-57df5e5af74f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ca0fb62ccb32ce244e1087281997dcd9929df89c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615999"
---
# <a name="symmetric-keys-on-user-databases"></a><span data-ttu-id="6dbda-102">Symmetrische Schlüssel für Benutzerdatenbanken</span><span class="sxs-lookup"><span data-stu-id="6dbda-102">Symmetric Keys on User Databases</span></span>
  <span data-ttu-id="6dbda-103">Diese Regel überprüft, ob Schlüssel mit einer Länge von weniger als 128 Bytes den RC2- oder RC4-Verschlüsselungsalgorithmus verwenden.</span><span class="sxs-lookup"><span data-stu-id="6dbda-103">This rule checks whether keys that have a length of less than 128 bytes do not use the RC2 or RC4 encryption algorithm.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="6dbda-104">Empfehlungen zu Best Practices</span><span class="sxs-lookup"><span data-stu-id="6dbda-104">Best Practices Recommendations</span></span>  
 <span data-ttu-id="6dbda-105">Verwenden Sie die AES-128-Bit-Verschlüsselung oder eine stärkere Verschlüsselung, um symmetrische Schlüssel für die Datenverschlüsselung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6dbda-105">Use AES 128 bit or larger to create symmetric keys for data encryption.</span></span> <span data-ttu-id="6dbda-106">Wenn AES nicht vom Betriebssystem unterstützt wird, verwenden Sie 3DES.</span><span class="sxs-lookup"><span data-stu-id="6dbda-106">If AES is not supported by your operating system, use 3DES.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="6dbda-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6dbda-107">For More Information</span></span>  
 [<span data-ttu-id="6dbda-108">Auswählen eines Verschlüsselungsalgorithmus</span><span class="sxs-lookup"><span data-stu-id="6dbda-108">Choose an Encryption Algorithm</span></span>](../security/encryption/choose-an-encryption-algorithm.md)  
  
## <a name="see-also"></a><span data-ttu-id="6dbda-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6dbda-109">See Also</span></span>  
 [<span data-ttu-id="6dbda-110">Überwachen und Erzwingen von Best Practices mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="6dbda-110">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
