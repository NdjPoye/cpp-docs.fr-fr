---
title: -HIGHENTROPYVA | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /HIGHENTROPYVA
dev_langs:
- C++
helpviewer_keywords:
- HIGHENTROPYVA editbin option
- -HIGHENTROPYVA editbin option
- /HIGHENTROPYVA editbin option
ms.assetid: ef4b7c63-440d-40ca-b39d-edefb3217505
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 122f524db9af10449ce809e5a8de78148d04d431
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
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