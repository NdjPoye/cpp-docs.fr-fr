---
title: "/GUARD (activer les contr&#244;les de protection) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 72758e23-70ac-4616-94d7-d767477406d1
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# /GUARD (activer les contr&#244;les de protection)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie la prise en charge pour les contrôles de protection du flux de contrôle de l'image exécutable.  
  
## Syntaxe  
  
```  
/GUARD:{CF|NO}  
```  
  
## Notes  
 Quand \/GUARD:CF est spécifié, l'éditeur de liens modifie l'en\-tête d'un fichier .dll ou .exe pour indiquer la prise en charge des contrôles d'exécution de la protection du flux de contrôle \(CFG\).  L'éditeur de liens ajoute également les données d'adresse cible du flux de contrôle nécessaire dans l'en\-tête.  Par défaut, \/GUARD:CF est désactivé.  Il peut être désactivé explicitement en spécifiant \/GUARD:NO.  Pour que \/GUARD:CF soit activé, l'option [\/DYNAMICBASE \(Utiliser la randomisation du format d'espace d'adresse\)](../../build/reference/dynamicbase-use-address-space-layout-randomization.md) de l'éditeur de liens doit également être activée \(elle l'est par défaut\).  
  
 Quand le code source est compilé avec l'option [\/guard:cf](../../build/reference/guard-enable-control-flow-guard.md), le compilateur analyse le flux de contrôle en examinant tous les appels indirects pour les adresses cibles possibles.  Le compilateur insère le code pour vérifier que l'adresse cible d'une instruction d'appel indirect figure dans la liste des adresses cibles connues au moment de l'exécution.  Les systèmes d'exploitation qui prennent en charge la protection CFG arrêtent tout programme qui ne satisfait pas une vérification à l'exécution CFG.  Il est ainsi plus difficile pour un attaquant d'exécuter du code malveillant en recourant à une altération des données pour modifier une cible d'appel.  
  
 L'option \/GUARD:CF doit être spécifiée dans le compilateur et l'éditeur de liens pour créer des images exécutables avec protection CFG.  Le code qui est compilé, mais pas lié avec l'option \/GUARD:CF implique un coût de vérifications à l'exécution, mais n'active pas la protection CFG.  Quand l'option \/GUARD:CF est spécifiée dans la commande `cl` pour compiler et lier le code en une seule étape, le compilateur passe l'indicateur à l'éditeur de liens.  Si la propriété de **protection du flux de contrôle** est définie dans Visual Studio, l'option \/GUARD:CF est passée au compilateur et à l'éditeur de liens.  Si des fichiers objets ou des bibliothèques ont été compilés séparément, l'option doit être spécifiée explicitement dans la commande `link`.  
  
### Pour définir cette option d'éditeur de liens dans Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriétés** du projet.  Pour plus d'informations, voir [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Développez **Propriétés de configuration**, **Éditeur de liens**, **Ligne de commande**.  
  
3.  Dans **Options supplémentaires**, entrez `/GUARD:CF`.  
  
## Voir aussi  
 [\/guard \(Activer la protection du flux de contrôle\)](../../build/reference/guard-enable-control-flow-guard.md)   
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)