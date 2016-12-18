---
title: "&#201;tat du VSPackage | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "état, VSPackages"
  - "VSPackages, gestion de l’état de l’application"
  - "persistance de l’état"
ms.assetid: 6056a9ea-e7a8-481c-9fc8-340229fa12d9
caps.latest.revision: 25
caps.handback.revision: 25
manager: "douge"
---
# &#201;tat du VSPackage
De nombreux facteurs déterminent l'ensemble de valeurs persistantes, ou l'état, d'une application de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] .  
  
-   Les projets ont des propriétés du projet et de configuration.  
  
-   les solutions ont des propriétés.  
  
-   Les paramètres utilisateur déterminent la taille et la position des fenêtres de document, les fenêtres Outil, ancrage l'état, et les raccourcis clavier.  
  
-   les applications peuvent avoir des options des ensembles de cet utilisateur.  
  
-   Les objets qu'une application crée peuvent avoir des propriétés de leur.  
  
 Voici quelques utilisations dont un état de l'application de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] peut être géré :  
  
-   Dans les pages de propriétés du projet et de solution.  
  
-   Par **Assistant paramètres d'importation et d'exportation**, qui permet à un utilisateur de déplacer des paramètres d'un ordinateur à un autre.  
  
-   Dans la boîte de dialogue d' **Options** , qui inclut des options liées aux applications.  
  
-   Dans la fenêtre de **Propriétés** , qui expose les propriétés des objets.  
  
-   Via l'automation.  Une application peut accéder à VSPackage propriétés et de l'objet exposés à automation.  
  
 En sous\-jacent à l'état de l'application sont divers mécanismes de persistance qui permettent l'état de l'application à stocker et être restauré.  
  
## Dans cette section  
 [Prise en charge de la persistance de l’état](../misc/support-for-state-persistence.md)  
 Répertorie les stratégies courantes pour stocker, restaurer, et réinitialiser l'état d'un VSPackage.  
  
 [Options et Pages d’Options](../Topic/Options%20and%20Options%20Pages.md)  
 Présente les pages options générales et personnalisées et explique comment les implémenter.  
  
 [Création d’une Page d’Options](../Topic/Creating%20an%20Options%20Page.md)  
 Explique comment créer deux pages options, une page simple et une page personnalisée.  
  
 [Prise en charge des catégories de paramètres](../misc/support-for-settings-categories.md)  
 Traite des paramètres utilisateur et comment ils sont créés et rendus persistants.  
  
 [Création d’une catégorie de paramètres](../Topic/Creating%20a%20Settings%20Category.md)  
 Explique comment créer une catégorie de paramètres de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] et l'utiliser pour enregistrer des valeurs à et pour restaurer des valeurs à partir d'un fichier de paramètres.  
  
 [Étendre les propriétés et la fenêtre Propriétés](../Topic/Extending%20Properties%20and%20the%20Property%20Window.md)  
 Explique comment afficher et de modifier la valeur d'un objet dans la fenêtre de **Propriétés** .  
  
 [Exposition de propriétés dans la fenêtre Propriétés](../Topic/Exposing%20Properties%20to%20the%20Properties%20Window.md)  
 Explique comment exposer des propriétés publiques d'un objet dans la fenêtre de **Propriétés** .  
  
 [Prise en charge des propriétés de Configuration et de projet](../Topic/Support%20for%20Project%20and%20Configuration%20Properties.md)  
 Explique comment consulter et modifier les propriétés de projet et de configuration.  
  
 [Obtention des propriétés de projet](../Topic/Getting%20Project%20Properties.md)  
 Vous guide à travers les étapes de créer un VSPackage managé qui affiche les propriétés de projet dans une fenêtre Outil.  
  
 [À l'aide de la banque de paramètres](../Topic/Using%20the%20Settings%20Store.md)  
 Explique le mécanisme de persistance du magasin de paramètres et son utilisation.  
  
## Rubriques connexes  
 [Packages VS](../Topic/VSPackages.md)  
 Fournit une orientation générale aux rubriques qui expliquent comment créer et utiliser les VSPackages.