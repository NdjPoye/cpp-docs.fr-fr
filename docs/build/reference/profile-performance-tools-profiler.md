---
title: "/PROFILE (Profileur des outils d&#39;analyse des performances) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.Profile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/PROFILE (option de l'éditeur de liens)"
  - "-PROFILE (option de l'éditeur de liens)"
ms.assetid: e676baa1-5063-47a3-a357-ba0d1f0d1699
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /PROFILE (Profileur des outils d&#39;analyse des performances)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Produit un fichier de sortie utilisable avec le profileur Outils d'analyse des performances.  
  
## Syntaxe  
  
```  
/PROFILE  
```  
  
## Notes  
 \/PROFILE implique les options de l'éditeur de liens suivantes :  
  
-   [\/OPT:REF](../../build/reference/opt-optimizations.md)  
  
-   \/OPT:NOICF  
  
-   [\/INCREMENTAL:NO](../../build/reference/incremental-link-incrementally.md)  
  
-   [\/FIXED:NO](../../build/reference/fixed-fixed-base-address.md)  
  
 \/PROFILE indique à l'éditeur de liens de générer une section de réadressage dans l'image de programme.  Une section de réadressage permet au profileur de transformer l'image de programme pour obtenir les données de profil.  
  
 **\/PROFILE** n'est disponible que dans les versions Entreprise \(développement en équipe\).  Pour plus d'informations sur PREfast, consultez [Vue d'ensemble de l'analyse du code C\/C\+\+](../Topic/Code%20Analysis%20for%20C-C++%20Overview.md).  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Développez le nœud **Propriétés de configuration**.  
  
3.  Développez le nœud **Éditeur de liens**.  
  
4.  Sélectionnez la page de propriétés **Avancé**.  
  
5.  Modifiez la propriété **Profil**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Profile%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)