---
title: "Avantages du caractère d’un jeu portabilité | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- character sets [C++], benefits
- portability [C++], character sets
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7ce02fa834c39f629990d4f3c9785de94bd02196
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/09/2018
---
# <a name="benefits-of-character-set-portability"></a>Avantages de la portabilité d'un jeu de caractères
Vous pouvez bénéficier de l’aide des fonctionnalités de portabilité runtime MFC et C même si vous n’envisagez pas internationaliser votre application pour :  
  
-   Le codage portable rend votre code base flexible. Vous pouvez ultérieurement le déplacer facilement en Unicode ou MBCS.  
  
-   L’utilisation de Unicode rend vos applications pour Windows est plus efficace. Étant donné que Windows utilise Unicode, les chaînes non-Unicode passés à et depuis le système d’exploitation doivent être traduites, ce qui entraîne une surcharge.  

  
## <a name="see-also"></a>Voir aussi  
 [Unicode et MBCS](../text/unicode-and-mbcs.md)   
 [Prise en charge pour Unicode](../text/support-for-unicode.md)