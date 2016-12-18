---
title: "/vd (D&#233;sactiver les d&#233;placements de construction) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/vd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/vd0 (option du compilateur C++)"
  - "/vd1 (option du compilateur C++)"
  - "/vdn (désactiver les déplacements de construction) (option du compilateur)"
  - "déplacements de construction"
  - "désactiver les déplacements de construction (option du compilateur)"
  - "déplacements (option du compilateur)"
  - "vd0 (option du compilateur C++)"
  - "-vd0 (option du compilateur C++)"
  - "vd1 (option du compilateur C++)"
  - "-vd1 (option du compilateur C++)"
  - "champs vtordisp"
ms.assetid: 93258964-14d7-4b1c-9cbc-d6f4d74eab69
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /vd (D&#233;sactiver les d&#233;placements de construction)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
/vdn  
```  
  
## Arguments  
 `0`  
 Supprime le membre de déplacement de constructeur\/destructeur vtordisp.  Choisissez cette option uniquement si vous êtes certain que tous les constructeurs et destructeurs de classe appellent virtuellement les fonctions virtuelles.  
  
 `1`  
 Active la création de membres de déplacement de constructeur\/destructeur vtordisp masqués.  Il s'agit de l'option par défaut.  
  
 `2`  
 Permet d'utiliser l'[dynamic\_cast, opérateur](../../cpp/dynamic-cast-operator.md) sur un objet en cours de construction.  Par exemple, un dynamic\_cast provenant d'une classe de base virtuelle vers une classe dérivée.  
  
 **\/vd2** ajoute un champ vtordisp lorsque vous utilisez une base virtuelle avec des fonctions virtuelles.  L'option **\/vd1** devrait être suffisante.  Le cas le plus fréquent d'utilisation de **\/vd2**, c'est lorsque la seule fonction virtuelle contenue dans votre base virtuelle est un destructeur.  
  
## Notes  
 Ces options s'appliquent uniquement au code C\+\+ qui utilise des bases virtuelles :  
  
 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] implémente la prise en charge du déplacement de construction C\+\+ quand l'héritage virtuel est utilisé.  Les déplacements de construction résolvent le problème qui survient quand une fonction virtuelle, déclarée dans une base virtuelle et substituée dans une classe dérivée, est appelée à partir d'un constructeur pendant la construction d'une autre classe dérivée.  
  
 Le problème est que la fonction virtuelle peut recevoir un pointeur `this` incorrect à cause de différences existant entre les déplacements vers les bases virtuelles d'une classe et les déplacements vers les classes dérivées.  La solution fournit un ajustement de déplacement de construction unique, appelé champ vtordisp, pour chaque base virtuelle d'une classe.  
  
 Par défaut, les champs vtordisp sont introduits chaque fois que le code définit des constructeurs et destructeurs définis par l'utilisateur et qu'il substitue également les fonctions virtuelles des bases virtuelles.  
  
 Ces options affectent l'ensemble des fichiers source.  Utilisez [vtordisp](../../preprocessor/vtordisp.md) de façon à supprimer,puis à réactiver les champs vtordisp classe par classe.  
  
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