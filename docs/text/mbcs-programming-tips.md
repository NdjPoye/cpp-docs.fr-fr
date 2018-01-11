---
title: Conseils de programmation MBCS | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _mbcs
dev_langs: C++
helpviewer_keywords:
- programming [C++], MBCS
- character sets [C++], multibyte
- MBCS [C++], programming
- multibyte characters [C++]
ms.assetid: d8ad36b8-917f-474e-8adb-69462adecd17
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1dc9c5dfd0dafe96e2d37b789b64c8215aa454e3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="mbcs-programming-tips"></a>Conseils de programmation MBCS
Dans tout nouveau développement, vous devez utiliser l’encodage de caractères Unicode pour toutes les chaînes que les utilisateurs finaux peuvent voir éventuellement. MBCS est une technologie héritée qui a été remplacée par le format Unicode. Cette section fournit des conseils pour les développeurs qui doivent conserver les programmes existants qui utilisent MBCS et où il n’est pas pratique de convertir au format Unicode. Les conseils s’appliquent aux applications MFC et les applications écrites sans MFC. Les rubriques traitées ici sont les suivantes :  
  
-   [Conseils généraux sur la programmation MBCS](../text/general-mbcs-programming-advice.md)  
  
-   [Incrémentation et décrémentation de pointeurs](../text/incrementing-and-decrementing-pointers.md)  
  
-   [Indices d’octets](../text/byte-indices.md)  
  
-   [Dernier caractère d’une chaîne](../text/last-character-in-a-string.md)  
  
-   [Assignation de caractère](../text/character-assignment.md)  
  
-   [Comparaison de caractères](../text/character-comparison.md)  
  
-   [Dépassement de mémoire tampon](../text/buffer-overflow.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge des jeux de caractères multioctets (MBCS)](../text/support-for-multibyte-character-sets-mbcss.md)