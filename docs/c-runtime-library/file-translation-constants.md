---
title: "Constantes de translation de fichier | Microsoft Docs"
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
  - "c.constants.file"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "constantes (C++), mode de translation de fichier"
  - "translation de fichier (C++)"
  - "translation de fichier (C++), constantes"
  - "constantes de translation"
  - "translation, constantes"
  - "translation, constantes de translation de fichier"
ms.assetid: 49b13bf3-442e-4d19-878b-bd1029fa666a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Constantes de translation de fichier
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
#include <stdio.h>  
```  
  
## Notes  
 Ces constantes spécifient le mode de traductions \(**"b"** ou **"t"**\).  Le mode est inclus dans la chaîne qui spécifie le type d'accès \(**"r"**, **"w"**, **"a"**, **"r\+"**, **"w\+"**, **"a\+"**\).  
  
 Les modes de traduction sont les suivants :  
  
 **t**  
 Ouvre en mode texte \(traduit\).  Dans ce mode, les combinaisons de retour et saut à la ligneCR\-LF\) sont traduites en sauts de ligne uniques \(LF\) en entrée et les caractères LF sont traduits en combinaisons CR\-LF en sortie.  En outre, CTRL\+Z est interprété comme caractère de fin de fichier sur l'entrée.  Dans les fichiers autorisés en lecture\/écriture, `fopen` vérifie la présence de Ctrl\+Z à la fin du fichier et le supprime, si possible.  Cette opération est effectuée car l'utilisation des fonctions `fseek` et  `ftell` pour se déplacer dans un fichier qui se termine par Ctrl\+Z peut provoquer un comportement incorrect de `fseek` près de la fin du fichier.  
  
> [!NOTE]
>  L'option de **t** ne fait pas partie de la norme ANSI pour `fopen` et `freopen`.  Il s'agit d'une extension Microsoft et ne doit pas être utilisé lorsque la portabilité ANSI est souhaitée.  
  
 **b**  
 Ouvre en mode binary.  Les traductions ci\-dessus sont supprimées.  
  
 Si  ou  **b**n'est pas donné dans *mode*, le mode de traduction est définit par a variable de mode par défaut [\_fmode](../c-runtime-library/fmode.md).  Pour plus d'informations sur l'utilisation des modes de texte et binaires, consultez [E\/S de fichier en mode texte et binaire](../c-runtime-library/text-and-binary-mode-file-i-o.md).  
  
## Voir aussi  
 [\_fdopen, \_wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fopen, \_wfopen](../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, \_wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)   
 [\_fsopen, \_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)