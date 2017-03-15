---
title: "/PGD (Sp&#233;cifier la base de donn&#233;es pour les optimisations guid&#233;es par profil) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.ProfileGuidedDatabase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/PGD (option de l'éditeur de liens)"
  - "-PGD (option de l'éditeur de liens)"
ms.assetid: 9f312498-493b-461f-886f-92652257e443
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /PGD (Sp&#233;cifier la base de donn&#233;es pour les optimisations guid&#233;es par profil)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/PGD:`filename`  
  
## Notes  
 où :  
  
 `filename`  
 Spécifie le nom du fichier .pgd qui sera utilisé pour contenir les informations relatives au programme en cours d'exécution.  
  
## Notes  
 Lors de l'utilisation de [\/LTCG:PGINSTRUMENT](../../build/reference/ltcg-link-time-code-generation.md), employez \/PGD pour spécifier un nom et un emplacement autres que ceux par défaut pour le fichier .pgd.  Si vous ne spécifiez pas \/PGD, le nom du fichier .pgd sera identique à celui du fichier de sortie \(.exe ou .dll\) et sera créé dans le même répertoire que celui à partir duquel la liaison a été appelée.  
  
 Lors de l'utilisation de \/LTCG:PGOPTIMIZE, employez \/PGD pour spécifier le nom du fichier .pgd à utiliser pour créer l'image optimisée.  
  
 Pour plus d'informations, consultez [Optimisation guidée par profil](../../build/reference/profile-guided-optimizations.md).  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Développez le nœud **Propriétés de configuration**.  
  
3.  Développez le nœud **Éditeur de liens**.  
  
4.  Sélectionnez la page de propriétés **Optimisation**.  
  
5.  Modifiez la propriété **Base de données guidée par profil**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProfileGuidedDatabase%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)