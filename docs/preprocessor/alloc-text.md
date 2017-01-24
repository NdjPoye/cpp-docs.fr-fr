---
title: "alloc_text | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.alloc_text"
  - "alloc_text_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "alloc_text (pragma)"
  - "pragmas, alloc_text"
ms.assetid: 1fd7be18-e4f7-4f70-b079-6326f72b871a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# alloc_text
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Nomme la section de code où les définitions de fonctions spécifiées doivent résider.  Le pragma doit intervenir entre un déclarateur de fonction et la définition de fonction pour les fonctions nommées.  
  
## Syntaxe  
  
```  
  
#pragma alloc_text( "  
textsection  
", function1, ... )  
```  
  
## Notes  
 Le pragma **alloc\_text** ne gère pas les fonctions membres C\+\+ ni les fonctions surchargées.  Il s'applique uniquement aux fonctions déclarées avec une liaison C, c'est\-à\-dire aux fonctions déclarées avec la spécification de liaison **extern "C"**.  Si vous tentez d'utiliser ce pragma sur une fonction avec une liaison C\+\+, une erreur de compilateur est générée.  
  
 Comme l'adressage de fonction à l'aide de `__based` n'est pas pris en charge, la spécification d'emplacements de section nécessite l'utilisation du pragma **alloc\_text**.  Le nom spécifié par *textsection* doit être placé entre guillemets doubles.  
  
 Le pragma **alloc\_text** doit figurer après les déclarations de toutes les fonctions éventuellement spécifiées et avant les définitions de ces fonctions.  
  
 Les fonctions référencées dans un pragma **alloc\_text** doivent être définies dans le même module que le pragma.  Si ce n'est pas le cas et qu'une fonction non définie est compilée ultérieurement dans une section de texte différente, l'erreur peut être interceptée ou non.  En règle générale, le programme fonctionnera correctement, mais la fonction ne sera pas allouée dans les sections prévues.  
  
 Les autres limitations relatives au pragma **alloc\_text** sont les suivantes :  
  
-   Il ne peut pas être utilisé au sein d'une fonction.  
  
-   Il doit être utilisé après que la fonction a été déclarée, mais avant que la fonction soit définie.  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)