---
title: "Examen du m&#233;canisme d&#39;un Assistant | Microsoft Docs"
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
helpviewer_keywords: 
  - "Assistants personnalisés, projets de l'Assistant"
ms.assetid: 79917075-a843-40f6-abf8-64d98e5f6bdc
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Examen du m&#233;canisme d&#39;un Assistant
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il n'est pas nécessaire de compiler un projet d'Assistant pour que les utilisateurs s'en servent immédiatement.  Une fois que vous avez créé les éléments nécessaires, VSDIR dirige la boîte de dialogue `New Project` pour afficher l'icône d'Assistant et la boîte de dialogue `Add New Item` pour afficher le nom d'Assistant dans le menu contextuel.  Votre client peut lancer immédiatement l'Assistant en le sélectionnant.  
  
 Quand l'utilisateur lance l'Assistant, le shell d'environnement crée en même temps le moteur de l'Assistant et les requêtes de <xref:EnvDTE.IDTWizard>.  Il appelle ensuite <xref:EnvDTE.IDTWizard.Execute%2A> pour lancer l'Assistant.  
  
> [!NOTE]
>  Si l'Assistant n'a pas d'interface, le projet est créé avec les valeurs par défaut fournies, puis affiché dans l'Explorateur de solutions, avec la structure de nœuds fournie dans le fichier .vsz.  Le reste de cette rubrique suppose que l'Assistant a une interface utilisateur.  
  
 Si l'Assistant a une interface utilisateur, l'utilisateur peut accepter ou modifier les valeurs par défaut dans chaque contrôle de l'interface utilisateur HTML de l'Assistant.  Lorsque l'utilisateur navigue dans les pages de l'Assistant pour effectuer des modifications, des fonctions telles que <xref:Microsoft.VisualStudio.VsWizard.VCWizCtlClass.Navigate%2A> et <xref:Microsoft.VisualStudio.VsWizard.VCWizCtlClass.Next%2A> sont appelées dans la section Script du code HTML.  
  
 Chaque fois que l'utilisateur sélectionne des options dans l'Assistant, ces sélections sont capturées dans la table de symboles du contrôle de l'Assistant.  La table de symboles fait correspondre les identificateurs des contrôles dans la page HTML de l'Assistant pour assurer une correspondance biunivoque entre les sélections de l'utilisateur et la table de symboles.  
  
 Quand l'utilisateur clique sur **Terminer** dans l'interface de l'Assistant, la fonction JScript **OnFinish** est appelée à partir du script HTML.  
  
> [!NOTE]
>  Vous pouvez personnaliser **OnFinish** dans Default.js pour effectuer les tâches supplémentaires nécessaires.  
  
 Le moteur d'Assistant parcourt alors les fichiers modèles, les analyse et les restitue en tenant compte des choix de l'utilisateur.  Il copie les fichiers rendus dans le répertoire du projet et les ajoute au projet.  Le projet créé est chargé dans l'environnement Visual Studio, les nœuds et fichiers de ce projet sont affichés dans l'Explorateur de solutions.  
  
## Voir aussi  
 <xref:Microsoft.VisualStudio.VsWizard.VCWizCtl>   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Étapes de conception d'un Assistant](../ide/steps-to-designing-a-wizard.md)   
 [Personnalisation de votre Assistant](../ide/customizing-your-wizard.md)