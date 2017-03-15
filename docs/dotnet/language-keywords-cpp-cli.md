---
title: "Mots cl&#233;s de langage (C++/CLI) | Microsoft Docs"
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
  - "mots clés (C++)"
ms.assetid: 021013b2-70ac-4df9-aa77-4af1c67a1a67
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Mots cl&#233;s de langage (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Plusieurs mots clés de langage ont été modifiés entre Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
 Dans la nouvelle syntaxe [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)], le trait de soulignement double est supprimé comme préfixe de tous les mots clés \(avec une exception : `__identifier` est conservé\).  Par exemple, une propriété se déclare à présent sous la forme `property`, et non `__property`.  
  
 Il y avait deux raisons majeures pour utiliser le préfixe de trait de soulignement double en Extensions managées :  
  
-   Il s'agit de la méthode conforme servant à fournir des extensions locales sous la norme ISO\-C\+\+.  Un des objectifs essentiels de la conception d'Extensions managées était ne pas introduire d'incompatibilités avec le langage standard, tel que de nouveaux mots clés ou jetons.  C'est en grande partie cette raison qui motivait le choix d'une syntaxe de pointeur pour déclarer des objets de types référence managés.  
  
-   Le trait de soulignement double, en dehors de sa dimension conforme, offre par ailleurs une garantie raisonnable de non\-invasion de la base de code existante des utilisateurs du langage.  C'était là le deuxième grand objectif de la conception d'Extensions managées.  
  
 En dépit de la suppression des traits de soulignement doubles, Microsoft maintient son engagement de conformité.  Cependant, la prise en charge du modèle d'objet dynamique du CLR représente un paradigme de programmation à la fois novateur et puissant.  La prise en charge de ce nouveau paradigme requiert ses propres jetons et mots clés de haut niveau.  Nous avons cherché à exprimer ce nouveau paradigme avec un maximum d'efficacité tout en l'intégrant et en prenant en charge le langage standard.  La nouvelle conception de la syntaxe représente un véritable progrès en matière de programmation de ces deux modèles d'objets disparates.  
  
 De même, nous avons à cœur de préserver la nature non invasive de ces nouveaux mots clés du langage.  Nous y sommes parvenus grâce à l'utilisation de mots clés contextuels et espacés.  Avant de nous pencher sur la nouvelle syntaxe du langage elle\-même, essayons de comprendre le sens de ces deux versions très particulières des mots clés.  
  
 Un mot clé contextuel a une signification spéciale dans des contextes de programme spécifiques.  Dans le programme général, par exemple, `sealed` est traité comme un identificateur ordinaire.  Toutefois, lorsqu'il survient dans la partie déclarative d'un type de classe de référence managé, il est traité comme un mot clé dans le contexte de cette déclaration de classe.  Cela réduit l'impact potentiellement invasif de l'introduction d'un nouveau mot clé dans le langage, ce qui nous semblait très important vis\-à\-vis des utilisateurs possédant déjà une base de code.  En même temps, cela permet aux utilisateurs des nouvelles fonctionnalités de tirer le meilleur bénéfice de cette fonctionnalité de langage supplémentaire – ce qui n'était pas possible avec les Extensions managées.  Pour obtenir un exemple de la façon dont `sealed` est utilisé, consultez [Déclaration d'un type de classe managée](../dotnet/declaration-of-a-managed-class-type.md).  
  
 Un mot clé espacé, tel que `value class`, est un cas particulier de mot clé contextuel.  Il apparie un mot clé existant et un modificateur contextuel, séparés par un espace.  La paire est traitée en tant qu'unité, plutôt que comme deux mots clés séparés.  
  
## Voir aussi  
 [Initiation à la migration de C\+\+\/CLI](../dotnet/cpp-cli-migration-primer.md)   
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)