---
title: Nettoyage des ressources | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- termination handlers [C++], cleaning up resources
- exception handling [C++], cleaning up resources
- C++ exception handling, termination handlers
- resources [C++], cleaning up
- exception handling [C++], cleanup code
- try-catch keyword [C++], termination handlers
ms.assetid: 65753efe-6a27-4750-b90c-50635775c1b6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fd84fdd041a3b3715c4fbfa9b4c1d78fdf2ba464
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cleaning-up-resources"></a>Nettoyage des ressources
Pendant l'exécution du gestionnaire de terminaisons, il est possible que vous ne sachiez pas quelles ressources ont été réellement allouées avant l'appel du gestionnaire de terminaisons. Il est possible que le bloc d'instructions `__try` ait été interrompu avant l'allocation de toutes les ressources, afin que toutes les ressources ne soient pas ouvertes.  
  
 Ainsi, par sécurité, vous devez vérifier les ressources qui sont réellement ouvertes avant de procéder au nettoyage de la gestion du bloc de fin. Voici une procédure recommandée :  
  
1.  Initialiser les handles sur NULL.  
  
2.  Dans le bloc d'instructions `__try`, allouer les ressources. Les handles sont définis sur des valeurs positives lorsque la ressource est allouée.  
  
3.  Dans le bloc d'instructions `__finally`, libérez chaque ressource dont la variable de handle ou de type indicateur est différente de zéro ou non Null.  
  
## <a name="example"></a>Exemple  
 Par exemple, le code suivant utilise un gestionnaire de terminaisons pour fermer trois fichiers et un bloc de mémoire alloués dans le bloc d'instructions `__try`. Avant de nettoyer une ressource, le code vérifie si elle a été allouée.  
  
```  
// exceptions_Cleaning_up_Resources.cpp  
#include <stdlib.h>  
#include <malloc.h>  
#include <stdio.h>  
#include <windows.h>  
  
void fileOps() {  
   FILE  *fp1 = NULL,  
         *fp2 = NULL,  
         *fp3 = NULL;  
   LPVOID lpvoid = NULL;  
   errno_t err;  
  
   __try {  
      lpvoid = malloc( BUFSIZ );  
  
      err = fopen_s(&fp1, "ADDRESS.DAT", "w+" );  
      err = fopen_s(&fp2, "NAMES.DAT", "w+" );  
      err = fopen_s(&fp3, "CARS.DAT", "w+" );  
   }  
   __finally {  
      if ( fp1 )  
         fclose( fp1 );  
      if ( fp2 )  
         fclose( fp2 );  
      if ( fp3 )  
         fclose( fp3 );  
      if ( lpvoid )  
         free( lpvoid );  
   }  
}  
  
int main() {  
   fileOps();  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [L’écriture d’un gestionnaire de terminaisons](../cpp/writing-a-termination-handler.md)   
 [Gestion structurée des exceptions (C/C++)](../cpp/structured-exception-handling-c-cpp.md)