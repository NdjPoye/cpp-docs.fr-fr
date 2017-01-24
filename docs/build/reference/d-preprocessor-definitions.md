---
title: "/D (D&#233;finitions de pr&#233;processeur) | Microsoft Docs"
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
  - "VC.Project.VCNMakeTool.PreprocessorDefinitions"
  - "VC.Project.VCCLCompilerTool.PreprocessorDefinitions"
  - "/d"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/D (option du compilateur C++)"
  - "constantes, définition"
  - "D (option du compilateur C++)"
  - "-D (option du compilateur C++)"
  - "macros, compiler"
  - "préprocesseur (symboles de définition)"
ms.assetid: b53fdda7-8da1-474f-8811-ba7cdcc66dba
caps.latest.revision: 22
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /D (D&#233;finitions de pr&#233;processeur)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit un symbole de prétraitement pour un fichier source.  
  
## Syntaxe  
  
```  
/Dname[= | # [{string | number}] ]  
```  
  
## Notes  
 Vous pouvez utiliser ce symbole avec `#if` ou `#ifdef` pour effectuer une compilation conditionnelle du code source.  La définition du symbole reste en vigueur jusqu'à ce qu'elle soit redéfinie ou annulée dans le code par la directive `#undef`.  
  
 **\/D** a le même effet que la directive `#define` au début d'un fichier de code source, sauf que **\/D** enlève les guillemets sur la ligne de commande et que `#define` les conserve.  
  
 Par défaut, la valeur associée à un symbole est 1.  Par exemple, **\/D**`name` équivaut à **\/D**`name`**\=1**.  Dans l'exemple situé à la fin de cet article, la définition de **TEST** indique d'afficher `1`.  
  
 Lors d'une compilation avec **\/D**`name`**\=**, aucune valeur n'est associée au symbole.  Bien que le symbole puisse toujours être utilisé pour effectuer une compilation de code conditionnelle, il ne retourne rien.  Dans l'exemple, si vous compilez à l'aide de **\/DTEST\=**, une erreur se produit.  Ce comportement ressemble à l'utilisation de `#define` avec ou sans valeur.  
  
 Cette commande définit le symbole DEBUG dans TEST.c:  
  
 **CL \/DDEBUG  TEST.C**  
  
 Cette commande supprime toutes les occurrences du mot clé `__far` dans TEST.c :  
  
 **CL \/D\_\_far\=  TEST.C**  
  
 Vous ne pouvez pas définir la variable d'environnement **CL** en tant que chaîne contenant le signe égal.  Pour utiliser **\/D** avec la variable d'environnement **CL**, vous devez spécifier le signe dièse à la place du signe égal :  
  
```  
SET CL=/DTEST#0  
```  
  
 Lorsque vous définissez un symbole de prétraitement à l'invite de commandes, tenez compte des règles d'analyse du compilateur et des règles d'analyse du shell.  Par exemple, pour définir le symbole de prétraitement pourcentage \(%\) dans votre programme, spécifiez deux caractères pourcentage \(%%\) à l'invite de commandes : si vous n'en spécifiez qu'un seul, une erreur d'analyse est émise.  
  
```  
CL /DTEST=%% TEST.C  
```  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriétés** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Dans le volet gauche, sélectionnez **Propriétés de configuration**, **C\/C\+\+**, **Préprocesseur**.  
  
3.  Dans le volet droit, dans la colonne de droite de la propriété **Définitions de préprocesseur**, ouvrez le menu déroulant et choisissez **Modifier**.  
  
4.  Dans la boîte de dialogue **Définitions de préprocesseur**, ajoutez \(une par ligne\), modifiez ou supprimez une ou plusieurs définitions.  Choisissez **OK** pour enregistrer vos modifications.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PreprocessorDefinitions%2A>.  
  
## Exemple  
  
```  
// cpp_D_compiler_option.cpp  
// compile with: /DTEST  
#include <stdio.h>  
  
int main( )  
{  
    #ifdef TEST  
        printf_s("TEST defined %d\n", TEST);  
    #else  
        printf_s("TEST not defined\n");  
    #endif  
}  
```  
  
  **TEST defined 1**   
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [\/U, \/u \(Annuler la définition de symboles\)](../../build/reference/u-u-undefine-symbols.md)   
 [\#undef, directive](../../preprocessor/hash-undef-directive-c-cpp.md)   
 [\#define, directive](../../preprocessor/hash-define-directive-c-cpp.md)