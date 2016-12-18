---
title: "/Gs (contr&#244;ler les appels de contr&#244;le de pile) | Microsoft Docs"
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
  - "/GS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GS (option du compilateur C++)"
  - "désactiver les tests de pile"
  - "GS (option du compilateur C++)"
  - "-GS (option du compilateur C++)"
  - "appels de contrôle de pile"
  - "tests de pile"
  - "pile, tests de pile"
ms.assetid: 40daed7c-f942-4085-b872-01e12b37729e
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Gs (contr&#244;ler les appels de contr&#244;le de pile)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gère les tests de pile.  
  
## Syntaxe  
  
```  
/Gs[size]  
```  
  
## Arguments  
 `size`  
 \(Facultatif\) Nombre d'octets que les variables locales peuvent occuper avant qu'une sonde de pile soit lancée.  Si l'option **\/Gs** est spécifiée sans argument `size`, cela revient à spécifier **\/Gs0**,  
  
## Notes  
 Une sonde de pile est une séquence de code que le compilateur insère dans chaque appel de fonction.  Lorsqu'elle est lancée, une sonde de pile pénètre sans heurt dans la mémoire en fonction de l'espace requis pour stocker les variables locales de la fonction.  
  
 Si une fonction requiert plus de `size` octets d'espace de pile pour les variables locales, sa sonde de pile est démarrée.  Par défaut, le compilateur génère du code qui lance une sonde de pile quand une fonction requiert plus d'une page d'espace de pile.  Ceci équivaut à une option du compilateur **\/Gs4096** pour les plateformes x86, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] et ARM.  Cette valeur permet à une application et au gestionnaire de mémoire Windows d'augmenter la quantité de mémoire validée dynamiquement dans la pile du programme au moment de l'exécution.  
  
> [!NOTE]
>  La valeur par défaut de **\/Gs4096** permet à la pile du programme des applications pour Windows de croître correctement au moment de l'exécution.  Nous vous recommandons de ne pas modifier la valeur par défaut à moins que vous sachiez exactement pourquoi vous devez la changer.  
  
 Certains programmes \(par exemple, les pilotes de périphériques virtuels\) n'ont pas besoin de ce mécanisme de croissance de pile par défaut.  Dans ce cas, les sondes de pile ne sont pas nécessaires et vous pouvez arrêter le compilateur qui les génère en affectant à `size` une valeur supérieure à celle qu'aucune fonction exigera pour le stockage des variables locales.  Aucun espace n'est autorisé entre **\/Gs** et `size`.  
  
 **\/Gs0** active des sondes de pile pour chaque appel de fonction qui requiert le stockage des variables locales.  Cela peut avoir un impact négatif sur les performances.  
  
 Vous pouvez activer ou désactiver les sondes de pile en utilisant [check\_stack](../../preprocessor/check-stack.md).  **\/Gs** et le pragma `check_stack` n'ont aucun effet sur les routines de bibliothèque C standard. Ils affectent uniquement les fonctions que vous compilez.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, voir [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Sélectionnez le dossier **C\/C\+\+**.  
  
3.  Sélectionnez la page de propriétés **Ligne de commande**.  
  
4.  Tapez l'option de compilateur dans la zone **Options supplémentaires**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)