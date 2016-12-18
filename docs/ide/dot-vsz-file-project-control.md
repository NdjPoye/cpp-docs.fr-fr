---
title: "Fichier&#160;.Vsz (contr&#244;le de projet) | Microsoft Docs"
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
  - "fichiers .vsz"
  - "Assistants personnalisés, .vsz (fichier)"
  - "Assistants personnalisés, fichiers de contrôle de projet"
  - "fichiers (C++), créés par l'Assistant personnalisé"
  - "fichiers .vsz"
ms.assetid: b8678fee-6795-46d1-9338-48b22d5e9207
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fichier&#160;.Vsz (contr&#244;le de projet)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le point de départ de chaque Assistant est le fichier .vsz.  Le fichier .vsz est un fichier texte qui détermine l'Assistant à appeler et les informations à passer à cet Assistant.  Le fichier contient un en\-tête de deux lignes, suivi de divers paramètres facultatifs à passer à l'Assistant.  Pour obtenir la liste des paramètres facultatifs, consultez [Symboles d'Assistant personnalisé prédéfinis](../ide/custom-parameters-in-the-wizard-dot-vsz-file.md).  
  
 L'exemple ci\-dessous présente l'en\-tête d'un fichier .vsz :  
  
```  
VSWIZARD 7.0  
Wizard=VsWizard.VsWizardEngine.10.0  
Param="WIZARD_NAME = My AppWizard"  
```  
  
-   La première ligne de l'en\-tête spécifie le numéro de version de format du fichier modèle.  Pour ce numéro, vous pouvez indiquer `6.0`, `7.0` ou `7.1`.  Aucun autre numéro n'est valide et l'utilisation de tout autre numéro entraînera une erreur "format non valide".  
  
-   La deuxième ligne attribue à la variable **Wizard** le ProgID de l'Assistant qui est co\-créé par Visual Studio.  Un ProgID est une représentation chaîne d'un CLSID, comme `VsWizard.VsWizardEngine.10.0`.  
  
     Si votre Assistant a une interface utilisateur, le ProgID spécifie automatiquement que l'Assistant implémente <xref:Microsoft.VisualStudio.VsWizard.IVCWizCtlUI>.  Par défaut, les méthodes de cette interface sont implémentées dans les [fichiers .htm](../ide/html-files.md) de votre projet.  Vous pouvez modifier le comportement de l'Assistant à l'aide des méthodes de cette interface dans les fichiers .htm.  Pour plus d'informations, consultez <xref:Microsoft.VisualStudio.VsWizard.VCWizCtl>, coclasse de <xref:Microsoft.VisualStudio.VsWizard.IVCWizCtlUI>.  
  
-   Après ces deux lignes apparaît une liste facultative de paramètres qui permettent au fichier .vsz de passer des paramètres personnalisés supplémentaires à l'Assistant.  Chaque valeur est passée sous forme d'un élément chaîne d'un tableau de variants dans la méthode <xref:Microsoft.VisualStudio.VsWizard.VsWizardClass.Execute%2A> du contrôle de l'Assistant.  Par défaut, un Assistant ayant une interface utilisateur produit les paramètres par défaut suivants :  
  
    ```  
    Param="START_PATH = <path to the wizard>"  
    Param="HTML_PATH = <path to the wizard's HTML file>"  
    Param="TEMPLATES_PATH = <path to the wizard's template file>"  
    Param="SCRIPT_PATH = <path to the wizard's script files>"  
    Param="IMAGES_PATH = <path to the wizard's images>"  
    ```  
  
     Si votre Assistant n'a pas d'interface utilisateur, il n'a pas de paramètre `IMAGES_PATH` et contient à la place les paramètres suivants :  
  
    ```  
    Param="WIZARD_UI = FALSE"  
    Param="SOURCE_FILTER = txt"  
    ```  
  
-   Le fichier .vsz peut contenir les paramètres suivants, qui spécifient les fonctions trouvées dans le fichier [Common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md) :  
  
    ```  
    Param="PREPROCESS_FUNCTION = CanAddATLClass"  
    Param="PREPROCESS_FUNCTION = CanAddMFCClass"  
    Param="PREPROCESS_FUNCTION = CanAddClass"  
    ```  
  
 Les fonctions [CanAddATLClass](../ide/canaddatlclass.md), [CanAddMFCClass](../ide/canaddmfcclass.md) et [CanAddClass](../ide/canaddclass.md) sont appelées par l'Assistant pour confirmer que le [Modèle de code Visual C\+\+](http://msdn.microsoft.com/fr-fr/dd6452c2-1054-44a1-b0eb-639a94a1216b) est disponible.  Si une de ces fonctions retourne **false**, l'Assistant n'est pas lancé.  
  
 Vous pouvez ajouter votre Assistant au volet Modèles de la boîte de dialogue **Nouveau projet** dans Visual Studio en plaçant le fichier .vsz dans le répertoire vcprojects.  Par défaut, l'Assistant personnalisé écrit le fichier .vsz dans ce répertoire.  
  
> [!NOTE]
>  Si vous supprimez les fichiers et répertoires de votre Assistant, vous devez aussi supprimer le fichier .vsz du projet, le fichier .vsdir et le fichier .ico du répertoire vcprojects.  
  
## Voir aussi  
 [Fichiers créés pour votre Assistant](../ide/files-created-for-your-wizard.md)   
 [Assistant personnalisé](../ide/custom-wizard.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Visual C\+\+ Wizard Model](http://msdn.microsoft.com/fr-fr/159395ac-33c7-47bf-ad42-4e1435ddc758)   
 [Ajout d'Assistants aux boîtes de dialogue Ajouter un élément et Nouveau projet à l'aide de fichiers .Vsdir](../Topic/Adding%20Wizards%20to%20the%20Add%20Item%20and%20New%20Project%20Dialog%20Boxes%20by%20Using%20.Vsdir%20Files.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)