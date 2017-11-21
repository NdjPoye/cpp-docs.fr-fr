---
title: "Collage de jeton (opérateur) (#) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: '##'
dev_langs: C++
helpviewer_keywords:
- preprocessor, operators
- '## preprocessor operator'
ms.assetid: 4f173503-990f-4bff-aef3-ec4d1f1458ef
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5573107688968026bf98eda4b18223e35b7b3ef2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="token-pasting-operator-"></a>Opérateurs de collage de jeton (##)
L’opérateur double-number-sign ou « collage de jeton » (**##**), qui est parfois appelé l’opérateur « fusion », est utilisé dans les macros object-like et de type fonction. Il permet aux jetons séparés d'être regroupés en un seul jeton et ne peut donc pas être le premier ou dernier jeton de la définition de macro.  
  
 Si un paramètre formel d'une définition de macro est précédé ou suivi d'un opérateur de collage de jeton, le paramètre formel est immédiatement remplacé par l'argument réel non étendu. L’expansion de macro n’est pas exécutée sur l’argument avant son remplacement.  
  
 Ensuite, chaque occurrence de l’opérateur de collage de jeton dans *chaîne de jeton* est supprimé, et les jetons précédant et suivant sont concaténés. Le jeton résultant doit être un jeton valide. Dans ce cas, le jeton est analysé en vue de son remplacement éventuel lorsqu'il représente un nom de macro. L'identificateur représente le nom sous lequel les jetons concaténés sont connus dans le programme avant leur remplacement. Chaque jeton représente un jeton défini ailleurs, soit dans le programme, soit sur la ligne de commande du compilateur. L'espace blanc précédent ou suivant l'opérateur est facultatif.  
  
 Cet exemple illustre l'utilisation de l'opérateur stringizing et de l'opérateur de collage de jeton lors de la spécification de la sortie du programme :  
  
```  
#define paster( n ) printf_s( "token" #n " = %d", token##n )  
int token9 = 9;  
```  
  
 Si une macro est appelée avec un argument numérique comme  
  
```  
paster( 9 );  
```  
  
 la macro génère  
  
```  
printf_s( "token" "9" " = %d", token9 );  
```  
  
 qui devient  
  
```  
printf_s( "token9 = %d", token9 );  
```  
  
## <a name="example"></a>Exemple  
  
```  
// preprocessor_token_pasting.cpp  
#include <stdio.h>  
#define paster( n ) printf_s( "token" #n " = %d", token##n )  
int token9 = 9;  
  
int main()  
{  
   paster(9);  
}  
```  
  
```Output  
token9 = 9  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Opérateurs de préprocesseur](../preprocessor/preprocessor-operators.md)