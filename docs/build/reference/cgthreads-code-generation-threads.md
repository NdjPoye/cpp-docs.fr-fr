---
title: "/cgthreads (threads de g&#233;n&#233;ration de code) | Microsoft Docs"
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
  - "/cgthreads"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/cgthreads (option du compilateur C++)"
  - "cgthreads"
  - "cgthreads (option du compilateur C++)"
  - "-cgthreads (option du compilateur C++)"
ms.assetid: 64bc768c-6caa-4baf-9dea-7cfa1ffb01c2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /cgthreads (threads de g&#233;n&#233;ration de code)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit le nombre de threads de cl.exe à utiliser pour l'optimisation et la génération de code.  
  
## Syntaxe  
  
```  
/cgthreads[1-8]  
```  
  
## Arguments  
 nombre  
 Nombre maximal de threads utilisables par cl.exe, dans la plage de 1 à 8.  
  
## Notes  
 L'option **\/cgthreads** spécifie le nombre maximal de threads que cl.exe utilise en parallèle pour les phases d'optimisation et de génération de code de la compilation.  Notez qu'aucun espace ne peut figurer entre **\/cgthreads** et l'argument `number`.  Par défaut, cl.exe utilise quatre threads, comme si **\/cgthreads4** était spécifié.  Si un plus grand nombre de cœurs de processeur sont disponibles, une valeur `number` plus élevée peut améliorer les durées de génération.  Cette option est particulièrement utile quand elle est associée à [\/GL \(Optimisation de l'ensemble du programme\)](../../build/reference/gl-whole-program-optimization.md).  
  
 Vous pouvez spécifier plusieurs niveaux de parallélisme pour une build.  Le commutateur **\/maxcpucount** de msbuild.exe spécifie le nombre de processus MSBuild qui peuvent être exécutés en parallèle.  L'indicateur du compilateur [\/MP \(Générer avec plusieurs processus\)](../../build/reference/mp-build-with-multiple-processes.md) spécifie le nombre de processus cl.exe qui compilent simultanément les fichiers sources.  L'option **\/cgthreads** spécifie le nombre de threads utilisés par chaque processus cl.exe.  Le processeur ne pouvant pas exécuter simultanément plus de threads qu'il n'y a de cœurs de processeur, il est inutile de spécifier simultanément des valeurs plus élevées pour toutes ces options et cela peut même être contre\-productif.  Pour plus d'informations sur la création de projets en parallèle, consultez [Building Multiple Projects in Parallel](../Topic/Building%20Multiple%20Projects%20in%20Parallel%20with%20MSBuild.md).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, voir [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le dossier **Propriétés de configuration**, **C\/C\+\+**.  
  
3.  Sélectionnez la page de propriétés **Ligne de commande**.  
  
4.  Modifiez la propriété **Options supplémentaires** pour inclure **\/cgthreads**`N`, où `N` est une valeur comprise entre 1 et 8, puis sélectionnez **OK**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)