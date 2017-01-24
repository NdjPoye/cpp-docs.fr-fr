---
title: "Erreur du compilateur C2099 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2099"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2099"
ms.assetid: 30e151ee-d458-4901-b0c0-d45054a913f5
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2099
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l'initialiseur n'est pas une constante  
  
 Cette erreur est émise uniquement par le compilateur C et ne se produit que pour les variables non automatiques.  Le compilateur initialise des variables non automatiques au début du programme et les valeurs avec lesquelles elles sont initialisées doivent être des constantes.  
  
## Exemple  
 L’exemple suivant génère l’erreur C2099.  
  
```  
// C2099.c int j; int *p; j = *p;   // C2099 *p is not a constant  
```  
  
## Exemple  
 L’erreur C2099 peut également se produire si le compilateur ne parvient pas à effectuer un repli de constante sur une expression sous **\/fp:strict**, ce qui peut être dû au fait que les paramètres de l’environnement de précision en virgule flottante diffèrent entre le moment de la compilation et celui de l’exécution. Pour plus d’informations, consultez [\_controlfp\_s](../../c-runtime-library/reference/controlfp-s.md).  
  
 En cas d’échec du repli de constante, le compilateur appelle l’initialisation dynamique, ce qui n’est pas autorisé en C.  
  
 Pour résoudre cette erreur, compilez le module en tant que fichier .cpp ou simplifiez l’expression.  
  
 Pour plus d'informations, consultez [\/fp \(Spécifier le comportement de virgule flottante\)](../../build/reference/fp-specify-floating-point-behavior.md).  
  
 L’exemple suivant génère l’erreur C2099.  
  
```  
// C2099_2.c // compile with: /fp:strict /c float X = 2.0 - 1.0;   // C2099 float X2 = 1.0;   // OK  
```