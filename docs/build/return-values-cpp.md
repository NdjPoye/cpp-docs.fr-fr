---
title: "Valeurs de retour (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 53583524-b337-4228-a9c6-c9bf516babe8
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Valeurs de retour (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une valeur de retour scalaire qui peut être stockée sur 64 bits est retournée via RAX. Ceci inclut les types \_\_m64.  Les types non scalaires, y compris les types float, double et vector, comme [\_\_m128](../cpp/m128.md), [\_\_m128i](../cpp/m128i.md), [\_\_m128d](../cpp/m128d.md), sont retournés dans XMM0.  L'état des bits non utilisés dans la valeur retournée dans RAX ou XMM0 est non défini.  
  
 Les types définis par l'utilisateur peuvent être retournés par valeur depuis des fonctions globales et des fonctions de membres statiques.  Pour être retournés par valeur dans RAX, les types définis par l'utilisateur doivent avoir une longueur de 1, 2, 4, 8, 16, 32 ou 64 bits, et pas de constructeur, de destructeur ou d'opérateur d'affectation de copie, pas de membre de données non statique privé ou protégé, pas de membre de données non statique de type référence, pas de classe de base, pas de fonction virtuelle et pas de membre de données qui ne répondent pas également à ces spécifications requises.  \(Il s'agit essentiellement de la définition d'un type POD de C\+\+ 03.  Comme la définition a été modifiée dans la norme C\+\+ 11, nous déconseillons l'utilisation de `std::is_pod` pour ce test.\) Sinon, l'appelant prend la responsabilité d'allouer de la mémoire et de passer un pointeur pour la valeur de retour comme premier argument.  Les arguments suivants sont décalés d'un argument vers la droite.  Le même pointeur doit être retourné par l'appelé dans RAX.  
  
 Ces exemples montrent comment les paramètres et les valeurs de retour sont passés pour les fonctions avec les déclarations spécifiées :  
  
## Exemple de valeur de retour 1 : résultat sur 64 bits  
  **\_\_int64 func1\(int a, float b, int c, int d, int e\);**  
**\/\/ L'appelant passe a dans RCX, b dans XMM1, c dans R8, d dans R9. e est placé sur la pile.**  
**\/\/ L'appelé retourne un résultat \_\_int64 dans RAX.**   
## Exemple de valeur de retour 2 : résultat sur 128 bits  
  **\_\_m128 func2\(float a, double b, int c, \_\_m64 d\);**   
**\/\/ L'appelant passe a dans XMM0, b dans XMM1, c dans R8, d dans R9.**   
**\/\/ L'appelé renvoie un résultat \_\_m128 dans XMM0.**   
## Exemple de valeur de retour 3 : résultat de type défini par l'utilisateur par pointeur  
  **struct Struct1 {**  
 **int j, k, l;    \/\/ Struct1 dépasse 64 bits.  };**  
**Struct1 func3\(int a, double b, int c, float d\);**   
**\/\/ L'appelant alloue de la mémoire pour la structure Struct1 retournée et passe un pointeur dans RCX,**   
**\/\/ a dans RDX, b dans XMM2, c dans R9, d est placé sur la pile.**   
**\/\/ L'appelé retourne un pointeur vers le résultat Struct1 dans RAX.**    
## Exemple de valeur de retour 4 : résultat de type défini par l'utilisateur par valeur  
  **struct Struct2 {**  
 **int j, k;    \/\/ Struct2 tient dans 64 bits et répond aux spécifications requises pour un retour par valeur.  };**  
**Struct2 func4\(int a, double b, int c, float d\);**   
**\/\/ L'appelant passe a dans RCX, b dans XMM1, c dans R8 et d dans XMM3.**   
**\/\/ L'appelé retourne un résultat Struct2 par valeur dans RAX.**    
## Voir aussi  
 [Convention d'appel](../build/calling-convention.md)