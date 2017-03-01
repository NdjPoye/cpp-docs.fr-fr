---
title: "Écrire vos propres manipulateurs sans arguments | Microsoft Docs"
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
- manipulators
ms.assetid: 2dc62d09-45b7-454d-bd9d-55f3c72c206d
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 276bba3dd5ce5debd926ebbc4ccfaf52c6b92097
ms.lasthandoff: 02/24/2017

---
# <a name="writing-your-own-manipulators-without-arguments"></a>Écrire vos propres manipulateurs sans arguments
Écrire des manipulateurs qui n’utilisent pas d’arguments ne requiert ni dérivation de classe, ni utilisation de macros complexes. Supposons que votre imprimante nécessite la paire \<ÉCHAP>[ pour entrer en mode gras. Vous pouvez insérer cette paire directement dans le flux :  
  
```  
cout <<"regular " <<'\033' <<'[' <<"boldface" <<endl;  
```  
  
 Ou vous pouvez définir le manipulateur `bold`, qui insère les caractères :  
  
```  
ostream& bold(ostream& os) {  
    return os <<'\033' <<'[';  
}  
cout <<"regular " <<bold <<"boldface" <<endl;  
```  
  
 La fonction `bold` définie globalement accepte un argument de référence `ostream` et retourne la référence `ostream`. Ce n’est pas une fonction membre ou amie, car elle n’a besoin d’accéder à aucun élément de classe privée. La fonction `bold` se connecte au flux car l’opérateur `<<` du flux est surchargé pour accepter ce type de fonction, utilisant une déclaration qui ressemble quelque peu à ceci :  
  
```  
_Myt& operator<<(ios_base& (__cdecl *_Pfn)(ios_base&))  
{     // call ios_base manipulator  
 (*_Pfn)(*(ios_base *)this);

    return (*this);

}  
```  
  
 Vous pouvez utiliser cette fonctionnalité pour étendre d’autres opérateurs surchargés. Dans ce cas, il est accessoire que `bold` insère des caractères dans le flux. La fonction est appelée lorsqu’elle est insérée dans le flux, mais pas nécessairement lorsque les caractères adjacents sont imprimés. Par conséquent, l’impression peut être retardée en raison de la mise en mémoire tampon du flux.  
  
## <a name="see-also"></a>Voir aussi  
 [Flux de sortie](../standard-library/output-streams.md)


