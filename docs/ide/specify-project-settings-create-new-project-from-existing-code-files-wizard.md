---
title: "Sp&#233;cifier les param&#232;tres du projet, Assistant Cr&#233;er un projet &#224; partir de fichiers de code existants | Microsoft Docs"
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
  - "vc.appwiz.importwiz.appsettings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistant Créer un projet à partir de fichiers de code existants, paramètres de projet"
ms.assetid: 9b8860c9-d35f-4f18-9565-2934d3d7f569
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Sp&#233;cifier les param&#232;tres du projet, Assistant Cr&#233;er un projet &#224; partir de fichiers de code existants
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez cette page de l'Assistant Créer un projet à partir de fichiers de code existants pour spécifier :  
  
-   L'environnement de génération pour le nouveau projet  
  
-   Les paramètres de génération correspondant à un type spécifique de nouveau projet à générer  
  
## Liste des tâches  
 [Comment : créer un projet C\+\+ à partir d'un code existant](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## Liste UIElement  
 **Utiliser Visual Studio**  
 Spécifie d'utiliser les outils de génération qui sont inclus dans Visual Studio pour générer le nouveau projet.  Cette option est activée par défaut.  
  
 **Type de projet**  
 Spécifie le type de projet que l'Assistant générera.  
  
 **Projet d'application Windows**  
 Indique que l'Assistant générera un projet pour une application Windows exécutable.  Cette option est disponible dans la zone de liste déroulante **Type de projet**.  
  
 **Projet d'application console**  
 Indique que l'Assistant générera un projet pour une application console.  Cette option est disponible dans la zone de liste déroulante **Type de projet**.  
  
 **Projet de bibliothèque de liens dynamiques \(DLL\)**  
 Indique que l'Assistant générera un projet pour une application de bibliothèque de liens dynamiques vide.  Cette option est disponible dans la zone de liste déroulante **Type de projet**.  
  
 **Projet de bibliothèque statique \(LIB\)**  
 Indique que l'Assistant générera un projet pour une application de bibliothèque statique.  Cette option est disponible dans la zone de liste déroulante **Type de projet**.  
  
 **Ajouter la prise en charge de ATL**  
 Ajoute la prise en charge de ATL au nouveau projet.  
  
 **Ajouter la prise en charge de MFC**  
 Ajoute la prise en charge de MFC au nouveau projet.  
  
 **Ajouter la prise en charge pour le Common Language Runtime**  
 Ajoute la prise en charge de la programmation CLR au nouveau projet.  
  
 **Common Language Runtime**  
 Spécifie que le nouveau projet soit conforme aux fonctionnalités CLR.  
  
 **Common Language Runtime \(ancienne syntaxe\)**  
 Spécifie le nouveau projet pour qu'il se conforme à la syntaxe des Extensions managées pour C\+\+, qui est la syntaxe de la programmation CLR avant Visual C\+\+ 2005.  
  
 **Utiliser un système de génération externe**  
 Spécifie d'utiliser des outils de génération qui ne sont pas inclus dans Visual Studio pour générer le nouveau projet.  Lorsque cette option est sélectionnée, vous pouvez spécifier des lignes de commande de génération dans les pages **Spécifier les paramètres de configuration Debug** et **Spécifier les paramètres de configuration Release**.  
  
> [!NOTE]
>  Lorsque l'option **Utiliser un système de génération externe** est activée, l'IDE ne génère pas le nouveau projet, et les options \/D, \/I, \/FI, \/AI ou \/FU ne sont donc pas requises pour la compilation.  Toutefois, ces options doivent être définies correctement pour que IntelliSense fonctionne correctement.  
  
## Voir aussi  
 [Spécifier les paramètres de configuration Debug, Assistant Créer un projet à partir de fichiers de code existants](../ide/specify-debug-configuration-settings.md)   
 [Spécifier les paramètres de configuration Release, Assistant Créer un projet à partir de fichiers de code existants](../ide/specify-release-configuration.md)