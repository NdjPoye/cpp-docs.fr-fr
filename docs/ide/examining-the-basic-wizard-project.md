---
title: "Examen du projet d&#39;Assistant de base | Microsoft Docs"
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
  - "Assistants personnalisés, fichiers créés"
  - "Assistants personnalisés, projets de l'Assistant"
ms.assetid: c6423e3c-ddb0-43e0-b8e5-9e3a98a7908c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Examen du projet d&#39;Assistant de base
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Après utilisation de l'[Assistant personnalisé](../ide/creating-a-custom-wizard.md) pour créer le projet de base, examinez les fichiers qu'il a créés pour vous.  
  
1.  Dans l'**Explorateur de solutions**, développez le projet pour examiner [les fichiers](../ide/files-created-for-your-wizard.md) que l'Assistant a créés pour ce projet.  
  
2.  Double\-cliquez sur Default.js pour ouvrir le [fichier JScript](../ide/jscript-file.md) du projet dans l'éditeur de code.  Ce fichier contient les fonctions JScript qui créent le projet quand l'utilisateur clique sur **Terminer** dans l'Assistant.  Passez en revue les fonctions et les commentaires TODO dans ce fichier.  
  
3.  Si votre projet comporte une interface utilisateur, consultez le contenu du dossier [Fichiers HTML](../ide/html-files.md) et remarquez qu'il contient le nombre de fichiers .htm spécifié dans la page [Paramètres de l'application](../ide/application-settings-custom-wizard.md) de l'Assistant personnalisé.  Double\-cliquez sur Default.htm pour ouvrir la page HTML principale du projet dans le [concepteur HTML](../Topic/HTML%20Designer.md).  Le code HTML peut être affiché en [Design View](../Topic/Design%20View1.md) ou en mode HTML, sous forme de balisage HTML [](http://msdn.microsoft.com/fr-fr/7bb90672-b36a-4cf9-9bbc-677c9b956318).  Passez au mode HTML et vérifiez la balise HTML.  Cliquez sur le bouton **Mode Script uniquement** \(en haut à droite de la fenêtre d'édition du mode HTML, à côté de la liste déroulante **Événements**\) pour examiner le code JScript du fichier .htm.  Par défaut, ce fichier contient les fonctions JScript qui initialisent et chargent l'Assistant, il fournit aussi un comportement par défaut pour l'interface **IVCWizCtrlUI**.  Consultez l'objet <xref:Microsoft.VisualStudio.VsWizard.VCWizCtl> de la coclasse pour plus d'informations.  
  
4.  Enregistrez et fermez votre projet d'Assistant.  
  
5.  Ouvrez la boîte de dialogue **Nouveau projet** de Visual Studio et trouvez l'icône de l'Assistant.  Double\-cliquez sur l'icône pour afficher l'Assistant.  Vous pouvez examiner les pages d'Assistant de base que l'Assistant personnalisé a créées pour vous.  Remarquez que la première page contient quelques contrôles HTML exemple ainsi que les boutons standard **Terminer**, **Annuler** et **Aide**.  
  
6.  Cliquez sur **Terminer** pour créer un nouveau projet par votre Assistant.  Par défaut, votre Assistant crée deux fichiers texte : ReadMe.txt et Sample.txt.  Ces fichiers décrivent le projet que votre Assistant vient de créer.  Fermez ce projet et rouvrez votre projet d'Assistant.  
  
7.  Consultez [Examen du mécanisme d'un Assistant](../ide/examining-the-mechanics-of-a-wizard.md) pour mieux comprendre comment l'environnement Visual Studio et le moteur d'Assistant Visual C\+\+ ont créé le projet que vous avez créé quand vous avez exécuté votre Assistant.  
  
 Vous êtes prêt à passer à la [personnalisation de votre Assistant](../ide/customizing-your-wizard.md).  
  
## Voir aussi  
 [Assistant personnalisé](../ide/custom-wizard.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Étapes de conception d'un Assistant](../ide/steps-to-designing-a-wizard.md)   
 [Fichiers créés pour votre Assistant](../ide/files-created-for-your-wizard.md)   
 [Fourniture de l'aide contextuelle](../ide/providing-context-sensitive-help.md)   
 [Personnalisation de votre Assistant](../ide/customizing-your-wizard.md)