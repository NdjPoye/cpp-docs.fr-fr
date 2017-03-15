---
title: "/BASE (Adresse de base) | Microsoft Docs"
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
  - "/base"
  - "VC.Project.VCLinkerTool.BaseAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/BASE (option de l'éditeur de liens)"
  - "@ (symbole d'adresse de base)"
  - "arobase (symbole d'adresse de base)"
  - "adresses de base (C++)"
  - "BASE (option de l'éditeur de liens)"
  - "-BASE (option de l'éditeur de liens)"
  - "DLL (C++), lier"
  - "variables d'environnement (C++), LIB"
  - "fichiers exécutables (C++), adresse de base"
  - "emplacement et taille de DLL"
  - "LIB (variable d'environnement)"
  - "programmes (C++), adresse de base"
  - "programmes (C++), éviter le réadressage"
  - "point-virgule (C++), spécificateur"
ms.assetid: 00b9f6fe-0bd2-4772-a69c-7365eb199069
caps.latest.revision: 15
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /BASE (Adresse de base)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/BASE:{address[,size] | @filename,key}  
```  
  
 L'option \/BASE définit une adresse de base pour le programme, en substituant l'emplacement par défaut d'un fichier .exe \(à 0x400000\) ou d'une DLL \(à 0x10000000\).  Le système d'exploitation tente d'abord de charger un programme à l'adresse de base spécifiée ou à l'adresse de base par défaut.  Faute de place, le système réaffecte le programme.  Pour éviter le réadressage, utilisez l'option [\/FIXED](../../build/reference/fixed-fixed-base-address.md).  
  
 L'éditeur de liens génère une erreur si *address* n'est pas un multiple de 64 Ko.  Vous pouvez éventuellement spécifier la taille du programme afin que l'éditeur de liens vous avertisse si le programme possède une taille supérieure à celle qui est spécifiée.  
  
 Sur la ligne de commande, un autre moyen de spécifier l'adresse de base consiste à utiliser *filename* précédé du signe \(@\) et d'un argument `key` dans le fichier.  L'argument *filename* est un fichier texte contenant les emplacements et les tailles de toutes les DLL que votre programme va utiliser.  L'éditeur de liens recherche le *filename* dans le chemin d'accès spécifié ou, si celui\-ci n'est pas mentionné, dans les répertoires spécifiés dans la variable d'environnement LIB.  Chaque ligne de *filename* représente une DLL. Sa syntaxe est la suivante :  
  
```  
  
key address [size] ;comment  
```  
  
 L'argument `key` est une chaîne de caractères alphanumériques et ne respecte pas la casse.  Il s'agit en général du nom d'une DLL, mais ce n'est pas une obligation.  L'argument `key` est suivi d'un argument *address* de base en langage C, en notation hexadécimale ou décimale et possède une taille maximale \(argument `size`\) facultative.  Ces trois arguments sont séparés par des espaces ou des tabulations.  L'éditeur de liens émet un avertissement si l'argument `size` spécifié est inférieur à l'espace d'adressage virtuel requis par le programme.  Un commentaire \(`comment`\) est spécifié par un point virgule \(;\) ; il se trouve sur la même ligne ou sur une ligne différente.  L'éditeur de liens ignore tout le texte compris entre le point\-virgule et la fin de la ligne.  Cet exemple affiche une partie d'un tel fichier :  
  
```  
main   0x00010000    0x08000000    ; for PROJECT.exe  
one    0x28000000    0x00100000    ; for DLLONE.DLL  
two    0x28100000    0x00300000    ; for DLLTWO.DLL  
```  
  
 Si le fichier contenant ces lignes s'appelle DLLS.txt, l'exemple de commande suivant s'applique à ces informations :  
  
```  
link dlltwo.obj /dll /base:@dlls.txt,two  
```  
  
## Notes  
 Vous pouvez réduire l'échange et améliorer les performances de votre programme en assignant des adresses de base de sorte que les DLL ne se chevauchent pas dans l'espace d'adressage.  
  
 Un autre moyen de définir l'adresse de base consiste à utiliser l'argument *BASE* dans une instruction [NAME](../../build/reference/name-c-cpp.md) ou [LIBRARY](../../build/reference/library.md).  Les options \/BASE et [\/DLL](../../build/reference/dll-build-a-dll.md) réunies sont équivalentes à l'instruction **LIBRARY**.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Avancé**.  
  
4.  Modifiez la propriété **Adresse de base**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.BaseAddress%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)