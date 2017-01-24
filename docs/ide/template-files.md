---
title: "Fichiers mod&#232;les | Microsoft Docs"
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
  - "Assistants personnalisés, fichiers modèles"
  - "fichiers (C++), créés par l'Assistant personnalisé"
  - "modèles (C++), pour les Assistants"
ms.assetid: 48fae3d8-3a53-4f62-8010-144c5ffe334e
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fichiers mod&#232;les
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les modèles qui créent un Assistant sont une collection de fichiers texte qui contient certaines [directives simples](../ide/template-directives.md) analysées et rendues conformément aux entrées de l'utilisateur et ajoutées au projet initial.  Les informations permettant d'analyser les modèles sont obtenues par accès direct à la table de symboles des contrôles de l'Assistant.  
  
 L'exemple ci\-dessous est un fichier modèle très simple pour un Assistant demandant à l'utilisateur de sélectionner A ou B.  
  
## Exemple  
  
```  
This file has been created by My Custom wizard.  
You selected:  
[!if TYPE_A]  
Type A  
[!else]  
Type B  
[!endif]  
The name of this project is [!output PROJECT_NAME].root.cpp:  
```  
  
 Si l'utilisateur choisit Type B, le modèle ci\-dessus est rendu comme suit :  
  
  **Ce fichier a été créé par l'Assistant personnalisé.  Vous avez sélectionné :**  
**Type B**  
**Le nom de ce projet est MyApp8.**    
## Sortie  
  
```  
This file has been created by My Custom wizard.  
You selected:  
Type B  
The name of this project is MyApp8.  
```  
  
 **Remarque** La syntaxe ci\-dessus est nouvelle pour Visual C\+\+ .NET.  La syntaxe des versions précédentes de Visual C\+\+ n'est pas prise en charge dans Visual C\+\+. NET.  
  
## Voir aussi  
 [Fichiers créés pour votre Assistant](../ide/files-created-for-your-wizard.md)   
 [Assistant personnalisé](../ide/custom-wizard.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)   
 [Fichier Templates.inf](../ide/templates-inf-file.md)