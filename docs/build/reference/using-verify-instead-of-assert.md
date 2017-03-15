---
title: "Utilisation de VERIFY au lieu d&#39;ASSERT | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "assert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "instructions ASSERT"
  - "assertions, débogage"
  - "assertions, dépanner les instructions ASSERT"
  - "déboguer (MFC), instructions ASSERT"
  - "déboguer les assertions"
  - "VERIFY (macro)"
ms.assetid: 4c46397b-3fb1-49c1-a09b-41a72fae3797
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Utilisation de VERIFY au lieu d&#39;ASSERT
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Supposons que vous ne rencontriez pas de problème lorsque vous exécutez la version debug de votre application MFC.  Cependant, la version release de la même application se bloque, retourne des résultats incorrects et\/ou se comporte anormalement.  
  
 Ce problème peut trouver son origine dans la quantité importante de code que vous placez dans une instruction ASSERT pour confirmer sa parfaite exécution.  Dans la mesure où les instructions ASSERT sont mises en commentaire dans la version release d'un programme MFC, le code ne s'exécute pas dans une version release.  
  
 Si vous utilisez ASSERT pour vérifier qu'un appel de fonction a réussi, pensez à utiliser [VERIFY](../Topic/VERIFY.md) à la place.  La macro VERIFY évalue ses propres arguments dans les deux versions debug et release de l'application.  
  
 Une autre technique préférable consiste à assigner la valeur de retour de la fonction à une variable temporaire, puis à tester la variable dans une instruction ASSERT.  
  
 Examinons le fragment de code suivant :  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
ASSERT(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
 Ce code s'exécute parfaitement dans la version debug d'une application MFC.  Si l'appel à `calloc( )` échoue, un message de diagnostic comprenant le fichier et le numéro de ligne apparaît.  Cependant, dans la version commerciale d'une application MFC :  
  
-   l'appel à `calloc( )` ne survient jamais, laissant `buf` non initialisée, ou  
  
-   `strcpy_s( )` copie "`Hello, World`" dans une partie aléatoire de mémoire, bloquant probablement l'application, entraînant l'arrêt du système ou  
  
-   `free()` tente de libérer un espace mémoire qui n'a jamais été alloué.  
  
 Pour utiliser ASSERT correctement, l'exemple de code doit être remplacé par celui\-ci :  
  
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
  
 Sinon, vous pouvez utiliser plutôt VERIFY :  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
VERIFY(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
## Voir aussi  
 [Résolution de problèmes liés à la version release](../../build/reference/fixing-release-build-problems.md)