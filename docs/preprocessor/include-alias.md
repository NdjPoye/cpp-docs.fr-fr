---
title: "include_alias | Microsoft Docs"
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
  - "vc-pragma.include_alias"
  - "include_alias_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "include_alias (pragma)"
  - "pragmas, include_alias"
ms.assetid: 3256d589-12b3-4af0-a586-199e96eabacc
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# include_alias
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique que *nom\_fichier\_court* doit être utilisé comme alias pour *nom\_fichier\_long*.  
  
## Syntaxe  
  
```  
  
      #pragma include_alias( "  
      long_filename  
      ", "  
      short_filename  
      " )  
#pragma include_alias( <long_filename>, <short_filename> )  
```  
  
## Notes  
 Certains systèmes de fichiers autorisent l'utilisation de noms de fichiers d'en\-tête plus longs que la limite 8.3 du système de fichiers FAT.  Le compilateur ne peut pas simplement tronquer les noms plus longs à 8.3, car les huit premiers caractères des noms de fichiers d'en\-tête plus longs peuvent ne pas être uniques.  Chaque fois que le compilateur rencontre la chaîne *long\_filename*, il la remplace par *short\_filename* et recherche le *short\_filename* du fichier d'en\-tête à la place.  Ce pragma doit figurer avant les directives `#include` correspondantes.  Par exemple :  
  
```  
// First eight characters of these two files not unique.  
#pragma include_alias( "AppleSystemHeaderQuickdraw.h", "quickdra.h" )  
#pragma include_alias( "AppleSystemHeaderFruit.h", "fruit.h" )  
  
#pragma include_alias( "GraphicsMenu.h", "gramenu.h" )  
  
#include "AppleSystemHeaderQuickdraw.h"  
#include "AppleSystemHeaderFruit.h"  
#include "GraphicsMenu.h"  
```  
  
 L'alias recherché doit correspondre exactement à la spécification, aussi bien pour ce qui est de la casse, de l'orthographe, que de l'utilisation des guillemets doubles et des crochets pointus.  Le pragma **include\_alias** effectue une correspondance de chaîne simple sur les noms de fichiers ; aucune autre validation de nom de fichier n'est effectuée.  Par exemple, avec les directives suivantes,  
  
```  
#pragma include_alias("mymath.h", "math.h")  
#include "./mymath.h"  
#include "sys/mymath.h"  
```  
  
 aucune attribution d'alias \(substitution\) n'est effectuée, puisque les chaînes de fichier d'en\-tête ne correspondent pas exactement.  En outre, les noms de fichiers d'en\-tête utilisés comme arguments pour les options \/Yu et \/Yc du compilateur, ou le pragma **hdrstop**, ne sont pas substitués.  Par exemple, si votre fichier source contient la directive suivante,  
  
```  
#include <AppleSystemHeaderStop.h>  
```  
  
 l'option correspondante du compilateur doit être  
  
```  
/YcAppleSystemHeaderStop.h  
```  
  
 Vous pouvez utiliser le pragma **include\_alias** pour mapper tout nom de fichier d'en\-tête à un autre.  Par exemple :  
  
```  
#pragma include_alias( "api.h", "c:\version1.0\api.h" )  
#pragma include_alias( <stdio.h>, <newstdio.h> )  
#include "api.h"  
#include <stdio.h>  
```  
  
 Ne combinez pas les noms de fichiers placés entre guillemets doubles avec des noms de fichiers placés entre crochets pointus.  Par exemple, avec les deux directives **\#pragma include\_alias** ci\-dessus, le compilateur n'exécute aucune substitution sur les directives `#include` suivantes :  
  
```  
#include <api.h>  
#include "stdio.h"  
```  
  
 En outre, la directive suivante génère une erreur :  
  
```  
#pragma include_alias(<header.h>, "header.h")  // Error  
```  
  
 Notez que le nom de fichier signalé dans les messages d'erreur, ou en tant que valeur de la macro **\_\_FILE\_\_** prédéfinie, est le nom du fichier une fois que la substitution a été effectuée.  Par exemple, après les directives suivantes,  
  
```  
#pragma include_alias( "VeryLongFileName.H", "myfile.h" )  
#include "VeryLongFileName.H"  
```  
  
 une erreur dans VERYLONGFILENAME.H produit le message d'erreur suivant :  
  
```  
myfile.h(15) : error C2059 : syntax error  
```  
  
 Notez également que la transitivité n'est pas prise en charge.  Avec les directives suivantes,  
  
```  
#pragma include_alias( "one.h", "two.h" )  
#pragma include_alias( "two.h", "three.h" )  
#include "one.h"  
```  
  
 le compilateur recherche le fichier TWO.H à la place de THREE.H.  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)