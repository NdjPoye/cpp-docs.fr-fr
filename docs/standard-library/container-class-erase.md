---
title: Conteneur Class::erase | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- erase method
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: aeb81554bdc50db44e9e8d4ee66369149eceb875
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="container-classerase"></a>Conteneur Class::erase
> [!NOTE]
>  Cette rubrique fait partie de la documentation Visual C++ comme exemple non fonctionnel de conteneurs utilisés dans la bibliothèque C++ Standard. Pour plus d’informations, consultez [Conteneurs disponibles dans la bibliothèque C++ Standard](../standard-library/stl-containers.md).  
  
 Efface un élément.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
 
    iterator erase(
    iterator _Where);

iterator erase(
    iterator first,  
    iterator last);
```  
  
## <a name="remarks"></a>Remarques  
 La première fonction membre supprime l’élément de la séquence contrôlée vers lequel pointé *_Where*. La deuxième fonction membre supprime l’élément de la séquence contrôlée dans la plage [`first`, `last`). Les deux fonctions retournent un itérateur qui désigne le premier élément restant après tous les éléments supprimés, ou [end](../standard-library/container-class-end.md) si aucun élément de ce genre n’existe.  
  
 Les fonctions membres lèvent une exception uniquement si une opération de copie lève une exception.  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple de classe de conteneur](../standard-library/sample-container-class.md)

