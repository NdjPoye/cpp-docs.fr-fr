---
title: -DYNAMICBASE | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /dynamicbase
dev_langs:
- C++
helpviewer_keywords:
- -DYNAMICBASE editbin option
- DYNAMICBASE editbin option
- /DYNAMICBASE editbin option
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d7a4cf7aa35d7ad6b41fc6d61f3f27662ae2c8d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="dynamicbase"></a>/DYNAMICBASE
Spécifie si une image exécutable peut être rebasée de façon aléatoire au moment du chargement en utilisant la randomisation du format d’espace d’adresse (ASLR).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
/DYNAMICBASE[:NO]  
```  
  
## <a name="remarks"></a>Notes  
 Par défaut, l’éditeur de liens définit les **/DYNAMICBASE** option.  
  
 Cette option modifie l’en-tête d’une image exécutable pour indiquer si le chargeur peut rebaser aléatoirement l’image au moment du chargement.  
  
 La fonctionnalité ASLR est prise en charge sur Windows Vista, Windows Server 2008, Windows 7, Windows 8 et Windows Server 2012.  
  
## <a name="see-also"></a>Voir aussi  
 [Options EDITBIN](../../build/reference/editbin-options.md)   
 [Mesures de sécurité des éditeurs de logiciels Windows](http://msdn.microsoft.com/library/bb430720.aspx)