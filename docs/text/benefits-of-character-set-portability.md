---
title: "Avantages du caractère d’un jeu portabilité | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- character sets [C++], benefits
- portability [C++], character sets
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 554137352c0a8f7275a051e4026020fce25edbb8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="benefits-of-character-set-portability"></a>Avantages de la portabilité d'un jeu de caractères
Vous pouvez bénéficier de l’aide des fonctionnalités de portabilité runtime MFC et C même si vous n’envisagez pas internationaliser votre application pour :  
  
-   Le codage portable rend votre code base flexible. Vous pouvez ultérieurement le déplacer facilement en Unicode ou MBCS.  
  
-   L’utilisation de Unicode rend vos applications pour Windows 2000 est plus efficace. Étant donné que Windows 2000 utilise Unicode, les chaînes non-Unicode passés à et depuis le système d’exploitation doivent être traduites, ce qui entraîne une surcharge.  
  
-   L’utilisation de MBCS permet de prendre en charge les marchés internationaux sur des plateformes Win32 autre que Windows 2000, telles que Windows 95 ou Windows 98.  
  
## <a name="see-also"></a>Voir aussi  
 [Unicode et MBCS](../text/unicode-and-mbcs.md)   
 [Prise en charge pour Unicode](../text/support-for-unicode.md)