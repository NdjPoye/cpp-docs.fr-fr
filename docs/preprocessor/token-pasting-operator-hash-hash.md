---
title: "Op&#233;rateurs de collage de jeton (##) | Microsoft Docs"
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
  - "##"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "## (opérateur de préprocesseur)"
  - "préprocesseur, opérateurs"
ms.assetid: 4f173503-990f-4bff-aef3-ec4d1f1458ef
caps.latest.revision: 10
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Op&#233;rateurs de collage de jeton (##)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'opérateur double\-number\-sign ou opérateur de collage de jeton \(**\#\#**\), qui est parfois appelé opérateur de fusion, est utilisé dans les macros object\-like et function\-like.  Il permet aux jetons séparés d'être regroupés en un seul jeton et ne peut donc pas être le premier ou dernier jeton de la définition de macro.  
  
 Si un paramètre formel d'une définition de macro est précédé ou suivi d'un opérateur de collage de jeton, le paramètre formel est immédiatement remplacé par l'argument réel non étendu.  L'expansion de macro n'est pas exécutée sur l'argument avant son remplacement.  
  
 Ensuite, chaque occurrence de l'opérateur de collage de jeton dans *token\-string* est supprimée et les jetons le précédant ou le suivant sont concaténés.  Le jeton résultant doit être un jeton valide.  Dans ce cas, le jeton est analysé en vue de son remplacement éventuel lorsqu'il représente un nom de macro.  L'identificateur représente le nom sous lequel les jetons concaténés sont connus dans le programme avant leur remplacement.  Chaque jeton représente un jeton défini ailleurs, soit dans le programme, soit sur la ligne de commande du compilateur.  L'espace blanc précédent ou suivant l'opérateur est facultatif.  
  
 Cet exemple illustre l'utilisation de l'opérateur stringizing et de l'opérateur de collage de jeton lors de la spécification de la sortie du programme :  
  
```  
#define paster( n ) printf_s( "token" #n " = %d", token##n )  
int token9 = 9;  
```  
  
 Si une macro est appelée avec un argument numérique comme  
  
```  
paster( 9 );  
```  
  
 la macro génère  
  
```  
printf_s( "token" "9" " = %d", token9 );  
```  
  
 qui devient  
  
```  
printf_s( "token9 = %d", token9 );  
```  
  
## Exemple  
  
```  
// preprocessor_token_pasting.cpp  
#include <stdio.h>  
#define paster( n ) printf_s( "token" #n " = %d", token##n )  
int token9 = 9;  
  
int main()  
{  
   paster(9);  
}  
```  
  
  **token9 \= 9**   
## Voir aussi  
 [Opérateurs de préprocesseur](../preprocessor/preprocessor-operators.md)