---
title: "hdrstop | Microsoft Docs"
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
  - "hdrstop_CPP"
  - "vc-pragma.hdrstop"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "hdrstop (pragma)"
  - "pragmas, hdrstop"
ms.assetid: 5ea8370a-10d1-4538-ade6-4c841185da0e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# hdrstop
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous permet de mieux contrôler les noms des fichiers de précompilation et l'emplacement auquel l'état de compilation est enregistré.  
  
## Syntaxe  
  
```  
  
#pragma hdrstop [( "filename" )]    
```  
  
## Notes  
 *filename* correspond au nom du fichier d'en\-tête précompilé à utiliser ou créer \(selon que [\/Yu](../build/reference/yu-use-precompiled-header-file.md) ou [\/Yc](../build/reference/yc-create-precompiled-header-file.md) est spécifié\).  Si *filename* ne contient pas de spécification de chemin d'accès, il est supposé que le fichier d'en\-tête précompilé est dans le même répertoire que le fichier source.  
  
 Si un fichier C ou C\+\+ contient un pragma **hdrstop** lorsqu'il est compilé avec \/Yc, le compilateur enregistre l'état de la compilation jusqu'à l'emplacement du pragma.  L'état compilé de tout code qui suit le pragma n'est pas enregistré.  
  
 Utilisez *filename* pour nommer le fichier d'en\-tête précompilé dans lequel l'état compilé est enregistré.  Il est facultatif d'insérer un espace entre **hdrstop** et *filename*.  Le nom de fichier spécifié dans le pragma **hdrstop** est une chaîne et est soumis par conséquent aux contraintes de toute chaîne C ou C\+\+.  En particulier, vous devez le placer entre guillemets et utiliser le caractère d'échappement \(barre oblique inverse\) pour spécifier des noms de répertoires.  Par exemple :  
  
```  
#pragma hdrstop( "c:\\projects\\include\\myinc.pch" )  
```  
  
 Le nom du fichier d'en\-tête précompilé est déterminé selon les règles suivantes par ordre de priorité :  
  
1.  L'argument de l'option du compilateur \/Fp  
  
2.  L'argument *filename* de \#**pragma hdrstop**  
  
3.  Le nom de base du fichier source avec une extension .PCH  
  
 Pour les options \/Yc et \/Yu, si ni les options de compilation, ni le pragma **hdrstop** indique un nom de fichier, le nom de base du fichier source est utilisé comme nom de base du fichier d'en\-tête précompilé.  
  
 Vous pouvez également utiliser les commandes de prétraitement pour remplacer une macro comme suit :  
  
```  
#define INCLUDE_PATH "c:\\progra~`1\\devstsu~1\\vc\\include\\"  
#define PCH_FNAME "PROG.PCH"  
.  
.  
.  
#pragma hdrstop( INCLUDE_PATH PCH_FNAME )  
```  
  
 Les règles suivantes régissent l'emplacement où le pragma **hdrstop** peut être placé :  
  
-   Il doit apparaître hors de toute déclaration ou définition de données ou de fonction.  
  
-   Il doit être spécifié dans le fichier source, pas dans un fichier d'en\-tête.  
  
## Exemple  
  
```  
#include <windows.h>                 // Include several files  
#include "myhdr.h"  
  
__inline Disp( char *szToDisplay )   // Define an inline function  
{  
    ...                              // Some code to display string  
}  
#pragma hdrstop  
```  
  
 Dans cet exemple, le pragma **hdrstop** apparaît après l'inclusion de deux fichiers et la définition d'une fonction inline.  Au départ, cela peut sembler être un positionnement étrange pour le pragma.  Toutefois, pensez que l'utilisation des options de précompilation manuelles, \/Yc et \/Yu, avec le pragma **hdrstop** vous permet de précompiler des fichiers source entiers, même du code incorporé.  Le compilateur Microsoft ne se limite pas à précompiler uniquement les déclarations de données.  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)