---
title: "D&#233;finition des blocs __asm en tant que macros C | Microsoft Docs"
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
helpviewer_keywords: 
  - "__asm (mot clé) (C++), en tant que macros C"
  - "macros, __asm (blocs)"
  - "Visual C, macros"
ms.assetid: 677ba11c-21c8-4609-bba7-cd47312243b0
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# D&#233;finition des blocs __asm en tant que macros C
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 C les macros offrent un moyen pratique d'insérer le code de l'assembly dans votre code source, mais elles exigent prudent car une macro se développe en une même ligne logique.  Pour créer des macros sans problème, suivez ces règles :  
  
-   Encadrer les  `__asm`bloquer entre accolades.  
  
-   Placer les  `__asm`mot devant chaque instruction assembly.  
  
-   Utiliser les commentaires en style ancien C \(  `/* comment */`\) au lieu de commentaires de style d'assembly \(   `; comment`\) ou les commentaires à ligne unique C \(   `// comment`\).  
  
 Pour illustrer, l'exemple suivant définit une macro simple :  
  
```  
#define PORTIO __asm      \  
/* Port output */         \  
{                         \  
   __asm mov al, 2        \  
   __asm mov dx, 0xD007   \  
   __asm out dx, al       \  
}  
```  
  
 Au premier coup de œil, les trois dernières  `__asm`mots clés paraissent superflues.  Toutefois, ils sont nécessaires, car la macro se développe en une seule ligne :  
  
```  
__asm /* Port output */ { __asm mov al, 2  __asm mov dx, 0xD007 __asm out dx, al }  
```  
  
 Les troisième et quatrième  `__asm`mots clés sont nécessaires en tant que séparateurs instruction.  Les séparateurs seule instruction reconnu dans  `__asm`blocs sont le caractère de saut de ligne et de  `__asm`mot\-clé.  Dans la mesure où un bloc défini sous la forme d'une macro est une ligne logique, vous devez séparer chaque instruction avec  `__asm`.  
  
 Les accolades sont également essentielles.  Si vous les omettez, le compilateur peut être confondu en C ou C\+\+ des instructions sur la même ligne vers la droite de l'appel de la macro.  Sans l'accolade fermante, le compilateur ne peut pas déterminer où le code de l'assembly s'arrête et il voit les instructions C ou C\+\+ le  `__asm`bloc sous la forme d'instructions d'assemblage.  
  
 Les commentaires de style d'assembly qui commencent par un point\-virgule \(**;**\) continuent jusqu'à la fin de la ligne.  Cela provoque des problèmes dans les macros, car le compilateur ignore tous les éléments après le commentaire, à la fin de la ligne logique.  Est de même des commentaires sur une ligne C ou C\+\+ \(  `// comment`\).  Pour éviter les erreurs, utilisez les commentaires C en style ancien \(  `/* comment */`\) dans  `__asm`blocs définis en tant que macros.  
  
 Un  `__asm`bloc écrit comme une macro C peut prendre des arguments.  Contrairement à une macro de C ordinaire, cependant, un  `__asm`macro ne peut pas retourner une valeur.  Vous ne pouvez pas utiliser ces macros dans les expressions de C ou C\+\+.  
  
 Veillez à ne pas appeler des macros de ce type sans discrimination.  Par exemple, l'appel d'une macro de langage d'assemblage dans une fonction déclarée avec le  `__fastcall`convention peut provoquer des résultats inattendus.  \(Voir  [utilisation et conservation de registres dans un Assembly Inline](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md).\)  
  
 **FIN spécifique à Microsoft**  
  
## Voir aussi  
 [Assembleur inline](../../assembler/inline/inline-assembler.md)