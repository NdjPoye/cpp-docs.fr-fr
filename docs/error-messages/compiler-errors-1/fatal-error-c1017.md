---
title: "Erreur irr&#233;cup&#233;rable C1017 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1017"
ms.assetid: 5542e604-599d-4e36-8f83-1d454c5753c9
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur irr&#233;cup&#233;rable C1017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

expression constante entière non valide  
  
 L'expression d'une directive `#if` n'existe pas ou ne correspond pas à une constante.  
  
 Les constantes définies par `#define` doivent avoir des valeurs qui correspondent à une constante entière si elles sont utilisées dans une directive `#if`, `#elif` ou `#else`.  
  
 L'exemple suivant génère l'erreur C1017 :  
  
```  
// C1017.cpp  
#define CONSTANT_NAME "YES"  
#if CONSTANT_NAME   // C1017  
#endif  
```  
  
 Résolution possible :  
  
```  
// C1017b.cpp  
// compile with: /c  
#define CONSTANT_NAME 1  
#if CONSTANT_NAME  
#endif  
```  
  
 `CONSTANT_NAME` correspondant à une chaîne et non pas à un entier, la directive `#if` génère l'erreur irrécupérable C1017.  
  
 Dans d'autres cas, le préprocesseur évalue une constante indéfinie à zéro.  Ceci peut entraîner des résultats inattendus, comme dans l'exemple suivant.  `YES` n'étant pas défini, il correspond à la valeur zéro.  L'expression `#if` `CONSTANT_NAME` a la valeur false et le code à utiliser sur `YES` est supprimé par le préprocesseur.  Étant donné que la valeur `NO` est également indéfinie \(zéro\), `#elif` `CONSTANT_NAME==NO` a la valeur true \(`0 == 0` ; il en résulte que le préprocesseur quitte le code dans la partie `#elif` de l'instruction, contrairement au comportement prévu.  
  
```  
// C1017c.cpp  
// compile with: /c  
#define CONSTANT_NAME YES  
#if CONSTANT_NAME  
   // Code to use on YES...  
#elif CONSTANT_NAME==NO  
   // Code to use on NO...  
#endif  
```  
  
 Pour voir exactement comment le compilateur gère les directives de préprocesseur, utilisez [\/P](../../build/reference/p-preprocess-to-a-file.md), [\/E](../../build/reference/e-preprocess-to-stdout.md) ou [\/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md).