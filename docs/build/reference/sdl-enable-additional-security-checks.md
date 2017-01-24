---
title: "/sdl (activer des contr&#244;les de s&#233;curit&#233; suppl&#233;mentaires) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.SDLCheck"
dev_langs: 
  - "C++"
ms.assetid: 3dcf86a0-3169-4240-9f29-e04a9f535826
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /sdl (activer des contr&#244;les de s&#233;curit&#233; suppl&#233;mentaires)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ajoute les vérifications SDL \(Security Development Lifecycle\) recommandées.  Ces vérifications incluent des avertissements supplémentaires relatifs à la sécurité en tant qu'erreurs, ainsi que des fonctionnalités de génération de code sécurisé supplémentaires.  
  
## Syntaxe  
  
```  
/sdl[-]  
```  
  
## Notes  
 **\/sdl** active un sur\-ensemble des vérifications de sécurité de base fourni par [\/GS](../../build/reference/gs-buffer-security-check.md) et remplace **\/GS\-**.  Par défaut, **\/sdl** est désactivé.  **\/sdl\-** désactive les vérifications de sécurité supplémentaires.  
  
## Vérifications au moment de la compilation  
 **\/sdl** active les avertissements suivants en tant qu'erreurs :  
  
|Avertissement activé par \/sdl|Commutateur de ligne de commande équivalent|Description|  
|------------------------------------|-------------------------------------------------|-----------------|  
|[C4146](../../error-messages/compiler-warnings/compiler-warning-level-2-c4146.md)|\/we4146|Un opérateur moins unaire a été appliqué à un type non signé, ce qui génère un résultat non signé.|  
|[C4308](../../error-messages/compiler-warnings/compiler-warning-level-2-c4308.md)|\/we4308|Une constante intégrale négative a été convertie en type non signé, générant éventuellement un résultat sans signification.|  
|[C4532](../../error-messages/compiler-warnings/compiler-warning-level-1-c4532.md)|\/we4532|L'utilisation des mots clés `continue`, `break` ou `goto` dans un bloc `__finally`\/`finally` a un comportement indéfini lors d'un arrêt anormal.|  
|[C4533](../../error-messages/compiler-warnings/compiler-warning-level-1-c4533.md)|\/we4533|Le code d'initialisation d'une variable ne sera pas exécuté.|  
|[C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md)|\/we4700|Utilisation d'une variable locale non initialisée.|  
|[C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)|\/we4703|Utilisation d'une variable de pointeur locale potentiellement non initialisée.|  
|[C4789](../../error-messages/compiler-warnings/compiler-warning-level-1-c4789.md)|\/we4789|Dépassement de mémoire tampon quand des fonctions CRT \(Runtime C\) spécifiques sont utilisées.|  
|[C4995](../../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)|\/we4995|Utilisation d'une fonction marquée avec pragma [deprecated](../../preprocessor/deprecated-c-cpp.md).|  
|[C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)|\/we4996|Utilisation d'une fonction marquée comme [deprecated](../../cpp/deprecated-cpp.md).|  
  
## Vérifications au moment de l'exécution  
 Quand **\/sdl** est activé, le compilateur génère du code pour effectuer ces vérifications au moment de l'exécution :  
  
-   Active le mode strict de détection de dépassement de mémoire tampon à l'exécution **\/GS**, équivalent à la compilation avec `#pragma strict_gs_check(push, on)`.  
  
-   Effectue un assainissement de pointeur limité.  Dans les expressions qui n'impliquent pas de déréférencements et dans les types qui n'ont aucun destructeur défini par l'utilisateur, les références de pointeur sont définies sur une adresse non valide après un appel à `delete`.  Cela contribue à empêcher la réutilisation de références périmées de pointeur.  
  
-   Effectue l'initialisation des membres de classe.  Initialise automatiquement tous les membres de classe à zéro lors de l'instanciation d'objet \(avant l'exécution du constructeur\).  Cela contribue à éviter l'utilisation de données non initialisées associées aux membres de classe que le constructeur n'initialise pas explicitement.  
  
## Notes  
 Pour plus d'informations, consultez [Avertissements, \/sdl et amélioration de la détection des variables non initialisées](http://go.microsoft.com/fwlink/p/?LinkId=331012).  
  
#### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Sélectionnez le dossier **C\/C\+\+**.  
  
3.  Dans la page **Général**, sélectionnez l'option à partir de la liste déroulante **Vérifications SDL**.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)