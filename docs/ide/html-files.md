---
title: "Fichiers HTML | Microsoft Docs"
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
  - "Assistants personnalisés, fichiers HTML"
  - "Assistants personnalisés, interface utilisateur"
  - "fichiers (C++), créés par l'Assistant personnalisé"
  - "pages HTML, interface de l'utilisateur pour les Assistants personnalisés"
  - "interface utilisateur pour les Assistants"
  - "Assistants (C++), interface de l'utilisateur pour les Assistants personnalisés"
ms.assetid: 3b6ed080-6560-418b-b908-d84d71bdf145
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fichiers HTML
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un Assistant peut contenir une interface utilisateur, c'est une interface HTML.  En plus du fichier Default.htm, un Assistant peut contenir un certain nombre de fichiers .htm, ce nombre pouvant être indiqué dans la zone **Nombre de pages** de l'[Assistant personnalisé](../ide/custom-wizard.md).  Chaque fichier .htm représente une page HTML de votre Assistant, et cette page HTML est accessible par les boutons `Next` et **Précédent**, onglets ou autre mise en forme spécifiée dans la conception de l'Assistant.  
  
 Le code HTML contient :  
  
-   la balise SYMBOL, qui identifie la valeur par défaut des options définies par l'utilisateur.  Les symboles sont écrits dans la table de symboles quand l'utilisateur clique sur **Terminer**, par exemple :  
  
```  
<SYMBOL NAME='HEADER_FILE' VALUE='MyHeader.h' TYPE=text></SYMBOL>  
```  
  
 Dans l'interface utilisateur de l'Assistant \(UI\), la zone de texte identifiée dans la table de symboles par « HEADER\_FILE » contient le texte par défaut « MyHeader.h ».  Vous pouvez modifier cette valeur dans l'interface utilisateur de l'Assistant, la valeur résultante est écrite dans la table de symboles du projet quand vous cliquez sur **Terminer**, par exemple :  
  
```  
<SYMBOL NAME='CHECKBOX1' TYPE=checkbox VALUE=false></SYMBOL>  
```  
  
 Dans l'interface utilisateur de l'Assistant, la case à cocher identifiée dans la table de symboles par « CHECKBOX1 » est désactivée par défaut.  Vous pouvez la sélectionner dans l'interface utilisateur HTML, la valeur résultante est écrite dans la table de symboles quand vous cliquez sur **Terminer**.  
  
 Chaque fichier .htm enregistre les sélections de l'utilisateur dans la table de symboles :  
  
-   une inclusion de [Common.js](../ide/customizing-cpp-wizards-with-common-jscript-functions.md), qui contient des fonctions JScript utiles et couramment utilisées, ainsi que Default.js ;  
  
-   des références aux images du projet à afficher dans le code HTML ;  
  
-   du texte HTML et des mises en forme personnalisant l'apparence de l'interface utilisateur de l'Assistant ;  
  
-   des fonctions JScript accédant au modèle objet d'Assistant Visual C\+\+ pour un comportement personnalisé dans l'Assistant.  Ces fonctions figurent dans la section de la page HTML intitulée \<SCRIPT LANGUAGE\='JSCRIPT'\>, comme le montre l'exemple suivant.  
  
    > [!NOTE]
    >  Pour accéder à l'Assistant et aux modèles objet d'environnement depuis HTML, ajoutez "window.external." à l'élément du modèle objet.  
  
    ```  
    function InitDocument(document)  
    {  
       setDirection();  
  
       if (window.external.FindSymbol('DOCUMENT_FIRST_LOAD'))  
       {  
          // This function sets the default symbols based   
          // on the values specified in the SYMBOL tags above  
          //  
          window.external.SetDefaults(document);  
       }  
  
       // Load the document and initialize the controls   
       // with the appropriate symbol values  
       //  
       window.external.Load(document);  
    }  
    ```  
  
 Voici un exemple d'Assistant Application console :  
  
```  
<SYMBOL NAME='WIZARD_DIALOG_TITLE' TYPE=text VALUE='Console Application Wizard'></SYMBOL>  
  
<SYMBOL NAME='EMPTY_PROJECT' TYPE=checkbox VALUE=false></SYMBOL>  
<SYMBOL NAME='SUPPORT_ATL' TYPE=checkbox VALUE=false></SYMBOL>  
<SYMBOL NAME='SUPPORT_MFC' TYPE=checkbox VALUE=false></SYMBOL>  
```  
  
## Voir aussi  
 [Fichiers créés pour votre Assistant](../ide/files-created-for-your-wizard.md)   
 [Assistant personnalisé](../ide/custom-wizard.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)