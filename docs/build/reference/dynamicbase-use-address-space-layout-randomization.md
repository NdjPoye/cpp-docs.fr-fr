---
title: "/DYNAMICBASE (Utiliser la randomisation du format d&#39;espace d&#39;adresse) | Microsoft Docs"
ms.custom: ""
ms.date: "12/09/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.RandomizedBaseAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DYNAMICBASE (option de l'Éditeur de liens)"
  - "DYNAMICBASE (option de l'Éditeur de liens)"
  - "-DYNAMICBASE (option de l'Éditeur de liens)"
ms.assetid: 6c0ced8e-fe9c-4b63-b956-eb8a55fbceb2
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /DYNAMICBASE (Utiliser la randomisation du format d&#39;espace d&#39;adresse)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Indique s'il est nécessaire de générer une image exécutable pouvant être aléatoirement redéfinie au moment du chargement à l'aide de la fonctionnalité de randomisation du format d'espace d'adresse \(ASLR, Address Space Layout Randomization\) de [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)].  
  
## Syntaxe  
  
```  
/DYNAMICBASE[:NO]  
```  
  
## Notes  
 Par défaut, \/DYNAMICBASE est activé.  
  
 Cette option modifie l'en\-tête d'un fichier exécutable pour indiquer si l'application doit être aléatoirement redéfinie au moment du chargement.  
  
 La randomisation du format d'espace d'adresse est prise en charge sur [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)].  
  
### Pour définir cette option de l'éditeur de liens dans Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriétés** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Développez le nœud **Propriétés de configuration**.  
  
3.  Développez le nœud **Éditeur de liens**.  
  
4.  Sélectionnez la page de propriétés **Avancé**.  
  
5.  Modifiez la propriété **Adresse de base aléatoire**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RandomizedBaseAddress%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)