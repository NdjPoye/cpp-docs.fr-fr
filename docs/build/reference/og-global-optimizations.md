---
title: "/Og (Optimisations globales) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.GlobalOptimizations"
  - "/og"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Og (option du compilateur C++)"
  - "allocation automatique de registres"
  - "élimination de sous-expressions communes"
  - "optimisations globales (option du compilateur C++)"
  - "structures de boucle, optimiser"
  - "Og (option du compilateur C++)"
  - "-Og (option du compilateur C++)"
ms.assetid: d10630cc-b9cf-4e97-bde3-8d7ee79e9435
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# /Og (Optimisations globales)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit des optimisations locales et globales, une allocation automatique de registres et l'optimisation des boucles.  Déconseillé.  
  
## Syntaxe  
  
```  
/Og  
```  
  
## Notes  
 Les propriétés suivantes sont disponibles :  
  
-   Élimination de sous\-expressions communes locales et globales  
  
     Dans cette optimisation, la valeur d'une sous\-expression commune est calculée une seule fois.  Dans l'exemple suivant, si les valeurs de `b` et de `c` ne changent pas entre les trois expressions, le compilateur peut assigner le calcul de  `b + c`  à une variable temporaire, et substituer la variable à `b + c` :  
  
    ```  
    a = b + c;  
    d = b + c;  
    e = b + c;  
    ```  
  
     Pour une optimisation de sous\-expressions communes locales, le compilateur examine de courtes sections de code pour y rechercher des sous\-expressions communes.  Pour une optimisation de sous\-expressions communes globales, le compilateur recherche les sous\-expressions communes dans des fonctions entières.  
  
-   Allocation automatique de registres  
  
     Cette optimisation permet au compilateur de stocker dans des registres les variables et les sous\-expressions fréquemment utilisées ; le mot clé `register` est ignoré.  
  
-   Optimisation des boucles  
  
     Cette optimisation supprime les sous\-expressions de type invariant dans le corps d'une boucle.  Une boucle optimale contient uniquement des expressions dont les valeurs changent lors de chaque exécution de la boucle.  Dans l'exemple suivant, l'expression  `x + y`  ne change pas dans le corps de la boucle :  
  
    ```  
    i = -100;  
    while( i < 0 ) {  
        i += x + y;  
    }  
    ```  
  
     Après l'optimisation, `x + y` est calculée une fois au lieu de l'être à chaque exécution de la boucle :  
  
    ```  
    i = -100;  
    t = x + y;  
    while( i < 0 ) {  
        i += t;  
    }  
    ```  
  
     L'optimisation de boucles est beaucoup plus efficace lorsque le compilateur peut prendre par défaut l'absence de crénelage, ce qui se définit à l'aide de [\_\_restrict](../../cpp/extension-restrict.md), [noalias](../../cpp/noalias.md) ou [restrict](../../cpp/restrict.md).  
  
    > [!NOTE]
    >  Vous pouvez activer ou désactiver l'optimisation globale fonction par fonction en utilisant le pragma `optimize`  avec l'option `g`.  
  
 **\/Og** active également l'optimisation de valeur de retour nommée, ce qui élimine le constructeur de copie et le destructeur d'une valeur de retour basée sur la pile.  Pour plus d'informations, consultez [\/O1, \/O2 \(Réduire la taille, augmenter la vitesse\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md).  
  
 Pour obtenir des informations connexes, consultez [\/Oi \(Générer des fonctions intrinsèques\)](../../build/reference/oi-generate-intrinsic-functions.md) et [\/Ox \(Optimisation complète\)](../../build/reference/ox-full-optimization.md).  
  
 L'option **\/Og** est déconseillée ; utilisez [\/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md) ou **\/O2**.  Pour plus d'informations, consultez [Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/fr-fr/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Spécifiez l'option du compilateur dans la zone **Options supplémentaires**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [\/O \(Optimiser le code\), options](../../build/reference/o-options-optimize-code.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)