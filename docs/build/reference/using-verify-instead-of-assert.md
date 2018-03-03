---
title: "Utilisation de VERIFY au lieu d’ASSERT | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- assert
dev_langs:
- C++
helpviewer_keywords:
- ASSERT statements
- debugging [MFC], ASSERT statements
- VERIFY macro
- assertions, troubleshooting ASSERT statements
- debugging assertions
- assertions, debugging
ms.assetid: 4c46397b-3fb1-49c1-a09b-41a72fae3797
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4ffe046a281bbbbefc251b48df55ecd275515e60
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="using-verify-instead-of-assert"></a>Utilisation de VERIFY au lieu d'ASSERT
Supposons que lorsque vous exécutez la version debug de votre application MFC, il n’existe aucun problème. Toutefois, la version de la même application se bloque, retourne des résultats incorrects et/ou présente certains autres comportement anormal.  
  
 Ce problème peut apparaître lorsque vous placez le code importante dans une instruction ASSERT pour vérifier qu’elle s’exécute correctement. Étant donné que les instructions ASSERT sont commentées dans une version Release d’un programme MFC, le code ne s’exécute pas dans une version Release.  
  
 Si vous utilisez ASSERT pour confirmer qu’un appel de fonction a réussi, envisagez d’utiliser [Vérifiez](../../mfc/reference/diagnostic-services.md#verify) à la place. La macro VERIFY évalue ses propres arguments dans les versions debug et les versions release de l’application.  
  
 Une autre technique consiste à affecter la valeur de retour de la fonction dans une variable temporaire, puis tester la variable dans une instruction ASSERT de préférence.  
  
 Examinez le fragment de code suivant :  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
ASSERT(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
 Ce code s’exécute parfaitement dans une version debug d’une application MFC. Si l’appel à `calloc( )` échoue, un message de diagnostic qui inclut le fichier et numéro de ligne apparaît. Toutefois, dans une version commerciale d’une application MFC :  
  
-   l’appel à `calloc( )` ne se produit jamais, en laissant `buf` non initialisée, ou  
  
-   `strcpy_s( )`copies «`Hello, World`» dans une zone aléatoire de la mémoire, bloquant probablement l’application ou à l’origine du système peut cesser de répondre ou  
  
-   `free()`tente de libérer la mémoire qui n’a jamais été allouée.  
  
 Pour utiliser ASSERT correctement, l’exemple de code doit être modifié à ce qui suit :  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
buf = (char *) calloc(sizeOfBuffer, sizeof(char) );  
ASSERT( buf != NULL );  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
 Ou bien, vous pouvez utiliser plutôt VERIFY :  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
VERIFY(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Résolution de problèmes liés à la version Release](../../build/reference/fixing-release-build-problems.md)