---
title: "__asm | Microsoft Docs"
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
  - "__asm"
  - "__asm_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__asm (mot clé) (C++)"
  - "__asm (mot clé) (C++), différences par rapport aux blocs asm"
ms.assetid: 77ff3bc9-a492-4b5e-85e1-fa4e414e79cd
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __asm
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Le mot clé `__asm` appelle l'assembleur inline et peut apparaître partout où une instruction C ou C\+\+ est conforme.  Il ne peut pas apparaître de lui\-même.  Il doit être suivi par une instruction assembleur, un groupe d'instructions entre accolades ou, au minimum, par une paire d'accolades vide.  Le terme « bloc `__asm` » fait ici référence à une instruction ou un groupe d'instructions, que ce dernier soit ou non entouré d'accolades.  
  
> [!NOTE]
>  La prise en charge du mot clé C\+\+ standard `asm` par Visual C\+\+ se limite au fait que le compilateur ne génère pas d'erreur pour le mot clé.  Toutefois, un bloc `asm` ne génère aucun code explicite.  Utilisez `__asm` à la place de `asm`.  
  
 Syntaxe :  
  
 \_\_asm *assembly\-instruction* \[ ; \]  
  
 \_\_asm { *assembly\-instruction\-list* } \[ ; \]  
  
## Grammaire  
 `__asm`  `assembly-instruction`  `;` option  
  
 `__asm {`  `assembly-instruction-list`  `};` option  
  
 *liste\-instruction\-assembly* :  
 `assembly-instruction` `;` option  
  
 `assembly-instruction` `;` `assembly-instruction-list` `;` option  
  
 Utilisé sans accolades, le mot clé `__asm` signifie que le reste de la ligne est une instruction en langage assembleur.  Utilisé avec les accolades, il signifie que chaque ligne entre accolades est une instruction en langage assembleur.  Pour assurer la compatibilité avec les versions antérieures, `_asm` est un synonyme de `__asm`.  
  
 Dans la mesure où le mot clé `__asm` est un séparateur d'instruction, vous pouvez placer des instructions assembleur sur la même ligne :  
  
 Avant Visual C\+\+ 2005, l'instruction  
  
```  
__asm int 3  
```  
  
 n'a pas provoqué la génération de code natif une fois compilée avec **\/clr**. Le compilateur a traduit l'instruction en une instruction de saut CLR.  
  
 `__asm int 3` entraîne maintenant la génération de code natif pour la fonction.  Pour qu'une fonction génère un point d'arrêt dans votre code et qu'elle soit compilée en langage MSIL, utilisez [\_\_debugbreak](../../intrinsics/debugbreak.md).  
  
## Exemple  
 Le fragment de code suivant est un simple bloc `__asm` entre accolades :  
  
```  
__asm {  
   mov al, 2  
   mov dx, 0xD007  
   out dx, al  
}  
```  
  
 Vous pouvez aussi placer `__asm` devant chaque instruction assembleur :  
  
```  
__asm mov al, 2  
__asm mov dx, 0xD007  
__asm out dx, al  
```  
  
 Le mot clé `__asm` étant un séparateur d'instruction, vous pouvez également insérer des instructions assembleur sur la même ligne :  
  
```  
__asm mov al, 2   __asm mov dx, 0xD007   __asm out dx, al  
```  
  
 Les trois exemples génèrent le même code, mais le premier style \(bloc `__asm` placé entre accolades\) présente quelques avantages.  Les accolades séparent clairement le code de l'assembly du code C ou C\+\+. De plus, elles évitent toute répétition inutile du mot clé `__asm`.  Les accolades peuvent également empêcher les ambiguïtés.  Pour placer une instruction C ou C\+\+ sur la même ligne qu'un bloc `__asm`, placez le bloc entre accolades.  Sans accolades, le compilateur ne peut pas savoir où le code assembleur s'arrête et où les instructions C ou C\+\+ démarrent.  Enfin, étant donné que le texte entre accolades a le même format que le texte MASM ordinaire, vous pouvez facilement couper et coller le texte depuis des fichiers sources MASM existants.  
  
 Contrairement aux accolades en C et C\+\+, celles encadrant un bloc `__asm` n'affectent pas la portée de la variable.  Vous pouvez également imbriquer les blocs `__asm` ; l'imbrication n'affecte pas la portée de la variable.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Mots clés C\+\+](../../cpp/keywords-cpp.md)   
 [Assembleur inline](../../assembler/inline/inline-assembler.md)