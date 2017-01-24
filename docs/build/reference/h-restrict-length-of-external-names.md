---
title: "/H (Limiter la longueur des noms externes) | Microsoft Docs"
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
  - "/h"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/H (option du compilateur C++)"
  - "noms externes"
  - "H (option du compilateur C++)"
  - "-H (option du compilateur C++)"
  - "noms publics (longueur des)"
ms.assetid: de701dd3-ed04-4c88-8195-960d2520ec2e
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /H (Limiter la longueur des noms externes)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Limite la longueur des noms externes.  
  
## Syntaxe  
  
```  
/Hnumber  
```  
  
## Arguments  
 `number`  
 Spécifie la longueur maximale des noms externes autorisés dans un programme.  
  
## Notes  
 Par défaut, la longueur des noms \(publics\) externes est limitée à 2 047 caractères.  Cette restriction est valable pour les programmes C et C\+\+.  L'utilisation de **\/H** peut seulement diminuer la longueur maximale autorisée pour les identificateurs, et non l'augmenter.  L'espace entre **\/H** et `number` est facultatif.  
  
 Si un programme contient des noms externes dont la longueur dépasse `number`, les caractères en trop sont ignorés.  Si vous compilez un programme sans l'option **\/H** et qu'un identificateur contient plus de 2 047 caractères, le compilateur génère l'erreur [Erreur irrécupérable C1064](../../error-messages/compiler-errors-1/fatal-error-c1064.md).  
  
 La limite imposée à la longueur englobe tout trait de soulignement \(\_\) ou signe arobase \(@\) à gauche créé par le compilateur.  Ces caractères font partie de l'identificateur et occupent un emplacement particulier.  
  
-   Le compilateur ajoute un trait de soulignement \(\_\) à gauche aux noms modifiés par les conventions d'appel `__cdecl` \(par défaut\) et `__stdcall`, et un signe arobase \(@\) à gauche aux noms modifiés par la convention d'appel `__fastcall`.  
  
-   Le compilateur ajoute des informations relatives à la taille des arguments aux noms modifiés par les conventions d'appel `__fastcall` et `__stdcall`, et ajoute les informations concernant les types aux noms C\+\+.  
  
 **\/H** peut être utile dans les cas suivants :  
  
-   quand vous créez des programmes portables ou à plusieurs langages ;  
  
-   quand vous utilisez des outils qui imposent des limites à la longueur des identificateurs externes ;  
  
-   quand vous voulez restreindre la quantité d'espace que les symboles utilisent dans une version Debug.  
  
 L'exemple suivant montre comment l'utilisation de **\/H** peut en fait introduire des erreurs si les longueurs des identificateurs sont excessivement limitées :  
  
```  
// compiler_option_H.cpp  
// compile with: /H5  
// processor: x86  
// LNK2005 expected  
void func1(void);  
void func2(void);  
  
int main() { func1(); }  
  
void func1(void) {}  
void func2(void) {}  
```  
  
 Vous devez également faire preuve de prudence quand vous utilisez l'option **\/H** en raison des identificateurs prédéfinis du compilateur.  Si leur longueur maximale est trop petite, certains identificateurs prédéfinis ne seront pas résolus, tout comme certains appels de fonction de la bibliothèque.  Par exemple, si la fonction `printf` est utilisée et si l'option **\/H5** est spécifiée au moment de la compilation, le symbole **\_prin** sera créé afin de référencer `printf`, et ceci ne se retrouvera pas dans la bibliothèque.  
  
 L'utilisation de **\/H** est incompatible avec [\/GL \(Optimisation de l'ensemble du programme\)](../../build/reference/gl-whole-program-optimization.md).  
  
 **\/H** est déconseillé ; les limites de longueur maximale ont été augmentées et **\/H** n'est plus nécessaire.  Pour plus d'informations, consultez [Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/fr-fr/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Spécifiez l'option du compilateur dans la zone **Options supplémentaires**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)