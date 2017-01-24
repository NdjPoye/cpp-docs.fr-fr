---
title: "Personnalisation de votre Assistant | Microsoft Docs"
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
  - "Assistants personnalisés"
  - "Assistants personnalisés, créer dans des projets Visual C++"
ms.assetid: a3ff1c81-3eef-41e7-a6bc-2f98e4bf423f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Personnalisation de votre Assistant
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous devez envisager les tâches courantes ci\-dessous lors de la personnalisation de l'Assistant créé avec l'[Assistant personnalisé](../ide/application-settings-custom-wizard.md).  
  
-   Dans le fichier .vsz, spécifiez les paramètres personnalisés nécessaires au fonctionnement de votre Assistant.  Pour plus d'informations, consultez [le fichier .vsz \(contrôle de projet\)](../ide/dot-vsz-file-project-control.md) et [Symboles d'Assistant personnalisé prédéfinis](../ide/custom-parameters-in-the-wizard-dot-vsz-file.md).  
  
     Si votre Assistant doit être localisé dans plusieurs langues, ajoutez les paramètres de langue au fichier .vsz.  Pour plus d'informations, consultez [Localisation d'un Assistant dans plusieurs langues](../ide/localizing-a-wizard-to-multiple-languages.md).  
  
-   Personnalisez les [fichiers modèles](../ide/template-files.md) \(et [Templates.inf](../ide/templates-inf-file.md)\) pour spécifier les directives de sélection de l'utilisateur.  
  
-   Personnalisez le [fichier Default.js](../ide/jscript-file.md) pour spécifier les gestions supplémentaires spéciales de votre Assistant.  Vous pouvez écrire vos propres fonctions et utiliser celles qui sont fournies dans [Common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md).  
  
-   Concevez les icônes et autres images utilisées par votre interface utilisateur HTML.  
  
-   Concevez l'interface utilisateur HTML.  
  
-   Ajoutez à la table de symboles HTML les symboles correspondant aux boutons, contrôles, zones de texte et autres éléments utilisés par votre Assistant.  
  
     Voici un extrait du code HTML fourni par l'Assistant personnalisé :  
  
    ```  
    <SYMBOL NAME="WIZARD_DIALOG_TITLE" TYPE=text VALUE="MyCustomWiz">  
          </SYMBOL>  
    <SYMBOL NAME="SAMPLE_CHECKBOX" TYPE=checkbox VALUE=true>  
          </SYMBOL>  
    ```  
  
     Cet Assistant, nommé MyCustomWiz, affiche une case à cocher qui est activée par défaut.  
  
-   Dans la section `<SCRIPT LANGUAGE="JSCRIPT">` des fichiers HTML, ajoutez les appels aux fonctions JScript et accédez au modèle objet Visual Studio pour personnaliser le comportement de votre Assistant.  Vous devez appeler ces fonctions par `window.external`, comme suit :  
  
    ```  
    window.external.AddSymbol("MAIN_FRAME_DEFAULT_STYLES", true);  
    window.external.AddSymbol("MAIN_FRAME_STYLE_FLAGS", "");  
    ```  
  
    > [!NOTE]
    >  Les méthodes, les propriétés et les événements exposés via [Automation et extensibilité pour Visual Studio](../Topic/Automation%20and%20Extensibility%20for%20Visual%20Studio.md), le [modèle de code Visual C\+\+](http://msdn.microsoft.com/fr-fr/dd6452c2-1054-44a1-b0eb-639a94a1216b), le [modèle de projet](http://msdn.microsoft.com/fr-fr/06c1bbd9-4c79-4f97-ad6d-2b1dea8ecd1f) et le [modèle de l'Assistant](http://msdn.microsoft.com/fr-fr/159395ac-33c7-47bf-ad42-4e1435ddc758) vous permettent de gérer par programmation tous les aspects du projet d'Assistant, de sa création à sa génération, à la fois dans les fichiers JScript et dans les fichiers .htm.  
  
-   Si nécessaire, personnalisez le [fichier .vsdir](../Topic/Adding%20Wizards%20to%20the%20Add%20Item%20and%20New%20Project%20Dialog%20Boxes%20by%20Using%20.Vsdir%20Files.md), pour permettre la compréhension des informations sur le fichier .vsz et les autres modèles par le shell.  Par exemple, indiquez l'ID de ressource d'icône, les indicateurs, les noms localisés, etc.  
  
-   Créez les fichiers .htm et les fichiers modèles pour toutes les langues dans lesquelles votre Assistant doit être localisé.  Ajoutez\-les aux répertoires appropriés du projet.  
  
-   [Ajoutez de l'aide contextuelle](../ide/providing-context-sensitive-help.md) pour votre Assistant.  
  
## Voir aussi  
 [Assistant personnalisé](../ide/custom-wizard.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Étapes de conception d'un Assistant](../ide/steps-to-designing-a-wizard.md)   
 [Fichiers créés pour votre Assistant](../ide/files-created-for-your-wizard.md)   
 [Fourniture de l'aide contextuelle](../ide/providing-context-sensitive-help.md)   
 [Gestion des erreurs dans les Assistants](../ide/handling-errors-in-wizards.md)