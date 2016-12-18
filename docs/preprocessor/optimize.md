---
title: "optimize | Microsoft Docs"
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
  - "vc-pragma.optimize"
  - "optimize_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "optimize (pragma)"
  - "pragmas, optimize"
ms.assetid: cb13c1cc-186a-45bc-bee7-95a8de7381cc
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# optimize
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie les optimisations à effectuer sur une base fonction par fonction.  
  
## Syntaxe  
  
```  
  
#pragma optimize( "[optimization-list]", {on | off} )  
```  
  
## Notes  
 Le pragma **optimize** doit apparaître à l'extérieur d'une fonction et prend effet à la première fonction définie après sa détection.  Les arguments **on** et **off** activent ou désactivent les options spécifiées dans l'élément *optimization\-list*.  
  
 L'élément *optimization\-list*peut être égal à zéro ou à plusieurs des paramètres indiqués dans le tableau suivant.  
  
### Paramètres du pragma optimize  
  
|Paramètre\(s\)|Type d'optimisation|  
|--------------------|-------------------------|  
|**g**|Active les optimisations globales.|  
|**s** ou **t**|Spécifie des séquences courtes ou rapides de code machine.|  
|**y**|Génère des pointeurs de frame sur la pile du programme.|  
  
 Ce sont les mêmes lettres que celles utilisées avec les options du compilateur [\/O](../build/reference/o-options-optimize-code.md).  Par exemple, le pragma suivant équivaut à l'option du compilateur **\/Os** :  
  
```  
#pragma optimize( "ts", on )  
```  
  
 L'utilisation du pragma **optimize** avec la chaîne vide \(**""**\) est une forme particulière de la directive :  
  
 Lorsque vous utilisez le paramètre **off**, il désactive les optimisations, répertoriées dans le tableau précédent de cette rubrique.  
  
 Lorsque vous utilisez le paramètre **on**, il réinitialise les optimisations à celles spécifiées avec l'option du compilateur [\/O](../build/reference/o-options-optimize-code.md).  
  
```  
#pragma optimize( "", off )  
.  
.  
.  
#pragma optimize( "", on )   
```  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)