---
title: "Vue d&#39;ensemble des fonctions | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "flux de contrôle, appels de fonction"
  - "fonctions (C++)"
ms.assetid: b6f4637f-02b9-49d8-8601-1f886bd2cfb9
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Vue d&#39;ensemble des fonctions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les fonctions doivent avoir une définition et une déclaration, même si une définition peut servir de déclaration si celle\-ci apparaît avant l'appel de la fonction.  La définition de fonction comprend le corps de la fonction, c'est\-à\-dire le code qui s'exécute lorsque la fonction est appelée.  
  
 Une déclaration de fonction génère le nom, le type de retour et les attributs d'une fonction qui est définie ailleurs dans le programme.  Une déclaration de fonction doit précéder l'appel à la fonction.  C'est pourquoi les fichiers d'en\-tête contenant les déclarations pour les fonctions runtime sont inclus dans votre code avant un appel à une fonction runtime.  Si la déclaration comporte des informations sur les types et le nombre de paramètres, il s'agit d'un prototype.  \(Pour plus d'informations, consultez [Prototypes de fonction](../c-language/function-prototypes.md).\)  
  
 Le compilateur utilise le prototype pour comparer les types d'argument dans les appels suivants à la fonction avec les paramètres de la fonction et convertir ces types d'argument en types de paramètre chaque fois que nécessaire.  
  
 Un appel de fonction transmet le contrôle d'exécution à la fonction appelée à partir de la fonction appelante.  Les arguments, le cas échéant, sont transmis par valeur à la fonction appelée.  L'exécution d'une instruction `return` dans la fonction appelée retourne le contrôle et éventuellement une valeur à la fonction appelante.  
  
## Voir aussi  
 [Fonctions](../c-language/functions-c.md)