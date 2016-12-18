---
title: "&#201;tapes de conception d&#39;un Assistant | Microsoft Docs"
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
  - "Assistants personnalisés, concevoir"
ms.assetid: dc22746b-99e3-4569-a8b4-b3d7cbabf8f2
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &#201;tapes de conception d&#39;un Assistant
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser un Assistant pour créer et configurer les fichiers de départ d'un projet courant.  Comme pour tout projet, la création d'un Assistant nécessite une certaine planification.  Les étapes ci\-dessous expliquent comment vous familiariser avec l'Assistant personnalisé Visual C\+\+ pour l'appliquer à vos projets.  
  
1.  Examinez les [exemples d'Assistant personnalisé](http://msdn.microsoft.com/fr-fr/6afa2143-062c-4a68-81ca-66cbf4b95261) fournis avec Visual Studio.  
  
2.  Mettez en place les fondations pour le type de projet que l'Assistant doit créer.  Comme pour toute construction d'application, ce processus peut nécessiter de nombreuses itérations différentes par de nombreuses personnes.  
  
3.  Créez votre projet avec l'[Assistant personnalisé](../ide/creating-a-custom-wizard.md) Visual C\+\+, et spécifiez les options d'interface utilisateur et de nombre de pages.  
  
    > [!NOTE]
    >  Si vous n'indiquez aucun paramètre d'interface utilisateur \(c'est\-à\-dire si vous désactivez **Interface utilisateur** dans [Paramètres de l'application, Assistant personnalisé](../ide/application-settings-custom-wizard.md) de l'Assistant personnalisé\), votre Assistant attribue la valeur WIZARD\_UI\=**FALSE** au paramètre personnalisé et crée des fichiers modèles de projet sans entrée utilisateur et sans fichier .htm.  Le résultat est que vous ne spécifiez pas de numéro de page.  Pour plus d'informations, consultez [le fichier .vsz \(contrôle de projet\)](../ide/dot-vsz-file-project-control.md).  
  
4.  [Examinez le projet de base](../ide/examining-the-basic-wizard-project.md) créé pour vous par l'Assistant personnalisé.  
  
5.  Si votre Assistant contient une interface utilisateur, exécutez\-le pour [en savoir plus sur le mécanisme de l'Assistant personnalisé](../ide/examining-the-mechanics-of-a-wizard.md).  
  
6.  [Personnalisez l'Assistant de base](../ide/customizing-your-wizard.md).  
  
7.  [Ajoutez de l'aide contextuelle](../ide/providing-context-sensitive-help.md).  
  
8.  [Assurez la gestion des erreurs](../ide/handling-errors-in-wizards.md) pour le code JScript et HTML.  
  
9. Générez et testez l'Assistant.  
  
10. Déboguez votre Assistant.  Pour plus d'informations, consultez [Débogage de scripts et d'applications Web](../Topic/Debugging%20Web%20Applications%20and%20Script.md).  
  
    > [!NOTE]
    >  Lors du débogage de JScript, le débogage en mode mixte avec du code natif est impossible.  
  
## Voir aussi  
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Assistant personnalisé](../ide/custom-wizard.md)   
 [Fichiers créés pour votre Assistant](../ide/files-created-for-your-wizard.md)