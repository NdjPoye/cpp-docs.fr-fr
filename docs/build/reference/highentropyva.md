---
title: -HIGHENTROPYVA | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /HIGHENTROPYVA
dev_langs:
- C++
helpviewer_keywords:
- HIGHENTROPYVA editbin option
- -HIGHENTROPYVA editbin option
- /HIGHENTROPYVA editbin option
ms.assetid: ef4b7c63-440d-40ca-b39d-edefb3217505
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 36ca3ea93f494587663d863b1dc4646750d38e82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="highentropyva"></a>/HIGHENTROPYVA
Spécifie si l’image exécutable prend en charge la randomisation du format d’espace d’adresse (ASLR) 64 bits de forte entropie.  
  
```  
  
/HIGHENTROPYVA[:NO]  
```  
  
## <a name="remarks"></a>Notes  
 Cette option modifie l'en-tête d'un fichier .dll ou .exe pour indiquer si la fonctionnalité ASLR est prise en charge avec des adresses 64 bits. Quand cette option est définie au niveau d’un fichier exécutable et de tous les modules dont il dépend, un système d’exploitation qui prend en charge l’ASLR 64 bits peut rebaser les segments de l’image exécutable au moment du chargement en utilisant des adresses aléatoires tirées d’un espace d’adressage virtuel de 64 bits. Devant ce grand espace d'adressage, il est plus difficile pour une personne malveillante de deviner l'emplacement d'une région de mémoire particulière.  
  
 Par défaut, l’éditeur de liens définit cette option pour les images exécutables 64 bits. Pour définir cette option, le [/DYNAMICBASE](../../build/reference/dynamicbase.md) option doit également être définie.  
  
## <a name="see-also"></a>Voir aussi  
 [Options EDITBIN](../../build/reference/editbin-options.md)   
 [/DYNAMICBASE](../../build/reference/dynamicbase.md)   
 [Mesures de sécurité des éditeurs de logiciels Windows](http://msdn.microsoft.com/library/bb430720.aspx)