---
title: "/Zm (Sp&#233;cifier la limite d&#39;allocation m&#233;moire d&#39;en-t&#234;te pr&#233;compil&#233;) | Microsoft Docs"
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
  - "/zm"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers .pch, limite d'allocation de mémoire"
  - "/Zm (option du compilateur C++)"
  - "compilateur cl.exe, limite d'allocation de mémoire"
  - "allocation de mémoire, limite d'allocation de mémoire (option du compilateur)"
  - "fichiers PCH, limite d'allocation de mémoire"
  - "fichiers d'en-tête précompilés, limite d'allocation de mémoire"
  - "spécifier la limite d'allocation de mémoire de l'en-tête précompilé (option du compilateur)"
  - "Zm (option du compilateur C++)"
  - "-Zm (option du compilateur C++)"
ms.assetid: 94c77d5e-6672-46a7-92e0-3f69e277727d
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zm (Sp&#233;cifier la limite d&#39;allocation m&#233;moire d&#39;en-t&#234;te pr&#233;compil&#233;)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine la quantité de mémoire que le compilateur alloue pour construire des en\-têtes précompilés.  
  
## Syntaxe  
  
```  
/Zmfactor  
```  
  
## Arguments  
 `factor`  
 Facteur d'échelle qui détermine la quantité de mémoire que le compilateur utilise pour construire des en\-têtes précompilés.  
  
 L'argument `factor` est un pourcentage de la taille par défaut d'une mémoire tampon de travail définie par le compilateur.  La valeur par défaut de `factor` est 100 \(pour cent\), mais vous pouvez spécifier des quantités plus grandes ou plus petites.  
  
## Notes  
 Dans les versions antérieures de Visual C\+\+, le compilateur utilisait plusieurs tas discrets, chacun avec une limite finie.  Actuellement, le compilateur augmente dynamiquement les tas selon les besoins, jusqu'à ce que la limite de la taille totale des tas soit atteinte. Il requiert ensuite une mémoire tampon de taille fixe uniquement pour construire des en\-têtes précompilés.  Par conséquent, l'option de compilateur **\/Zm** est rarement nécessaire.  
  
 Si l'espace du tas est insuffisant pour le compilateur et si ce dernier émet le message d'erreur [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) lorsque vous utilisez l'option de compilateur **\/Zm**, cela peut signifier que vous avez réservé trop de mémoire.  Supprimez l'option **\/Zm**.  Si le compilateur émet le message d'erreur [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md), un message d'accompagnement [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) spécifie l'argument `factor` à utiliser lorsque vous recompilez à l'aide de l'option de compilateur **\/Zm**.  
  
 Le tableau suivant montre comment l'argument `factor` affecte la limite d'allocation de mémoire si vous supposez que la taille de la mémoire tampon de l'en\-tête précompilé par défaut est de 75 Mo.  
  
|Valeur de `factor`|Limite d'allocation de mémoire|  
|------------------------|------------------------------------|  
|10|7.5 Mo|  
|100|75 Mo|  
|200|150 Mo|  
|1000|750 Mo|  
|2000|1500 Mo|  
  
## Autres moyens de définir la limite d'allocation de mémoire  
  
#### Pour définir l'option de compilateur \/Zm dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Dans le volet de navigation, sélectionnez **Propriétés de configuration**, **C\/C\+\+**, **Ligne de commande**.  
  
3.  Entrez l'option de compilateur **\/Zm** dans la zone **Options supplémentaires**.  
  
#### Pour définir l'option de compilateur \/Zm par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)