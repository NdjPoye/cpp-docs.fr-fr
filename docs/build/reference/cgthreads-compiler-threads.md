---
title: "/CGTHREADS (threads du compilateur) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CGTHREADS (option de l'éditeur de liens)"
  - "CGTHREADS (option de l'éditeur de liens)"
  - "-CGTHREADS (option de l'éditeur de liens)"
ms.assetid: 4b52cfdb-3702-470b-9580-fabeb1417488
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /CGTHREADS (threads du compilateur)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit le nombre de threads de cl.exe à utiliser pour l'optimisation et la génération de code quand la génération de code durant l'édition de liens est spécifiée.  
  
## Syntaxe  
  
```  
/CGTHREADS:[1-8]  
```  
  
## Arguments  
 nombre  
 Nombre maximal de threads utilisables par cl.exe, dans la plage de 1 à 8.  
  
## Notes  
 L'option **\/CGTHREADS** spécifie le nombre maximal de threads que cl.exe utilise en parallèle pour les phases d'optimisation et de génération de code de la compilation, quand la génération de code durant l'édition de liens \([\/LTCG](../../build/reference/ltcg-link-time-code-generation.md)\) est spécifiée.  Par défaut, cl.exe utilise quatre threads, comme si **\/CGTHREADS:4** était spécifié.  Si un plus grand nombre de cœurs de processeur sont disponibles, une valeur `number` plus élevée peut améliorer les durées de génération.  
  
 Vous pouvez spécifier plusieurs niveaux de parallélisme pour une build.  Le commutateur **\/maxcpucount** de msbuild.exe spécifie le nombre de processus MSBuild qui peuvent être exécutés en parallèle.  L'indicateur du compilateur [\/MP \(Générer avec plusieurs processus\)](../../build/reference/mp-build-with-multiple-processes.md) spécifie le nombre de processus cl.exe qui compilent simultanément les fichiers sources.  L'option de compilateur [\/cgthreads](../../build/reference/cgthreads-code-generation-threads.md) spécifie le nombre de threads utilisés par chaque processus cl.exe.  Le processeur ne pouvant pas exécuter simultanément plus de threads qu'il n'y a de cœurs de processeur, il est inutile de spécifier simultanément des valeurs plus élevées pour toutes ces options et cela peut même être contre\-productif.  Pour plus d'informations sur la création de projets en parallèle, consultez [Building Multiple Projects in Parallel](../Topic/Building%20Multiple%20Projects%20in%20Parallel%20with%20MSBuild.md).  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, voir [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le dossier **Propriétés de configuration**, **Éditeur de liens**.  
  
3.  Sélectionnez la page de propriétés **Ligne de commande**.  
  
4.  Modifiez la propriété **Options supplémentaires** pour inclure **\/CGTHREADS:**`number`, où `number` est une valeur comprise entre 1 et 8, puis choisissez **OK**.  
  
### Pour définir cette option de l'éditeur de liens par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)   
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)