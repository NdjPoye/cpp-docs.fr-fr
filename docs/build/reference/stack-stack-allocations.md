---
title: "/STACK, allocations de la pile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.StackReserveSize"
  - "VC.Project.VCLinkerTool.StackCommitSize"
  - "/stack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "STACK, option de l’éditeur de liens"
  - "-STACK, option de l’éditeur de liens"
  - "allocation de mémoire, pile"
  - "/STACK, option de l’éditeur de liens"
  - "pile, définir la taille"
ms.assetid: 73283660-e4bd-47cc-b5ca-04c5d739034c
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# /STACK, allocations de la pile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/STACK:reserve[,commit]  
```  
  
## Notes  
 L'option \/STACK définit la taille de la pile en octets.  N'utilisez cette option que lorsque vous générez un fichier .exe.  
  
 La valeur `reserve` indique la taille totale de l'allocation de piles dans la mémoire virtuelle.  Pour les ordinateurs ARM, x86 et [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], la taille de la pile par défaut est égale à 1 Mo  
  
 L'argument `commit` est soumis à l'interprétation du système d'exploitation.  Sous Windows WindowsRT, il spécifie la quantité de mémoire physique à allouer dans chaque cas.  La mémoire virtuelle dédiée fait réserver de l'espace dans le fichier d'échange.  Une valeur de l'argument `commit` supérieure permet de gagner du temps quand l'application requiert davantage d'espace pour la pile, mais augmente les besoins en ressources mémoire et peut allonger la durée de la phase de démarrage.  Pour les ordinateurs ARM, x86 et [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], la valeur de validation par défaut est 4 Ko.  
  
 Spécifiez les valeurs `reserve` et `commit` en notation décimale ou de langage C.  
  
 Un autre moyen de définir la taille de la pile consiste à utiliser l'instruction [STACKSIZE](../../build/reference/stacksize.md) dans un fichier de définition de module \(.def\).  **STACKSIZE** substitue l'option Allocations de la pile \(\/STACK\) si les deux arguments sont spécifiés.  Vous pouvez modifier la taille de la pile une fois que le fichier .exe est généré à l'aide de l'outil [EDITBIN](../../build/reference/editbin-reference.md).  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le dossier **Éditeur de liens**.  
  
3.  Sélectionnez la page de propriétés **System**.  
  
4.  Modifiez une des propriétés suivantes :  
  
    -   **Taille de validation de pile**  
  
    -   **Taille de la réserve de piles**  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Consultez les propriétés <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackCommitSize%2A> et <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackReserveSize%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)