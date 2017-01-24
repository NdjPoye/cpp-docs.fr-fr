---
title: "/SYMBOLS | Microsoft Docs"
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
  - "/symbols"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SYMBOLS (option Dumpbin)"
  - "symboles publics"
  - "tables de symboles"
  - "SYMBOLS (option Dumpbin)"
  - "-SYMBOLS (option Dumpbin)"
  - "symboles, afficher la table de symboles COFF"
  - "symboles, vider"
ms.assetid: 34bcae90-4561-4c77-a80c-065508dec39a
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /SYMBOLS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SYMBOLS  
```  
  
 Cette option affiche la table des symboles COFF.  Des tables de symboles existent dans tous les fichiers objets.  Une table de symboles COFF apparaît dans un fichier image uniquement si celui\-ci est lié avec \/DEBUG.  
  
 L'exemple suivant est une description de la sortie correspondant à \/SYMBOLS.  Vous trouverez des informations supplémentaires concernant la signification de la sortie \/SYMBOLS en consultant winnt.h \(IMAGE\_SYMBOL et IMAGE\_AUX\_SYMBOL\) ou la documentation COFF.  
  
 Prenons l'exemple de dump suivant :  
  
```  
Dump of file main.obj  
File Type: COFF OBJECT  
  
COFF    SYMBOL    TABLE  
000    00000000   DEBUG      notype      Filename      | .file  
      main.cpp  
002   000B1FDB   ABS      notype      Static      | @comp.id  
003   00000000   SECT1      notype      Static      | .drectve  
      Section length       26, #relocs   0, #linenums    0, checksum 722C964F  
005   00000000   SECT2      notype      Static      | .text  
      Section length      23, #relocs      1, #linenums    0, checksum 459FF65F, selection    1 (pick no duplicates)  
007   00000000   SECT2      notype ()   External      | _main  
008   00000000   UNDEF      notype ()   External      | ?MyDump@@YAXXZ (void __cdecl MyDump(void))  
  
String Table Size = 0x10 bytes  
  
Summary  
  
      26 .drectve  
      23 .text  
```  
  
## Notes  
 La description suivante, qui s'applique aux lignes commençant par un numéro de symbole, concerne les colonnes contenant des informations pertinentes pour les utilisateurs :  
  
-   Le premier nombre à trois chiffres est l'index\/le numéro du symbole.  
  
-   Si la troisième colonne contient SECT*x*, le symbole est défini dans cette section du fichier objet.  Mais si UNDEF apparaît, il n'est pas défini dans cet objet et doit être résolu ailleurs.  
  
-   La cinquième colonne \(Static, External\) indique si le symbole est visible uniquement dans cet objet ou s'il est public \(visible de l'extérieur\).  Un symbole statique \_sym n'est normalement pas lié à un symbole public \_sym ; il s'agirait de deux instances différentes de fonctions nommées \_sym.  
  
 La dernière colonne dans une ligne numérotée est le nom du symbole, à la fois décoré et non décoré.  
  
 Seule l'option [\/HEADERS](../../build/reference/headers.md) de DUMPBIN est disponible pour les fichiers générés à l'aide de l'option de compilation [\/GL](../../build/reference/gl-whole-program-optimization.md).  
  
## Voir aussi  
 [Options DUMPBIN](../../build/reference/dumpbin-options.md)