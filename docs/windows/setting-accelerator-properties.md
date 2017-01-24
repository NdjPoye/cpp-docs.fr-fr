---
title: "D&#233;finition des propri&#233;t&#233;s d&#39;un acc&#233;l&#233;rateur | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "propriétés d'accélérateur"
  - "Propriétés (C++), les propriétés d’un accélérateur"
  - "Type (propriété)"
  - "Key (propriété)"
  - "Modifier (propriété)"
ms.assetid: 0fce9156-3025-4e18-b034-e219a4c65812
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;finition des propri&#233;t&#233;s d&#39;un acc&#233;l&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans Visual C++ .NET, vous pouvez définir les propriétés d’un accélérateur dans la [fenêtre Propriétés](../Topic/Properties%20Window.md) à tout moment. Vous pouvez également utiliser l'Éditeur d'accélérateurs pour modifier les propriétés d'un accélérateur dans la table d'accélérateurs. Les modifications apportées à l'aide de la fenêtre Propriétés ou de l'Éditeur d'accélérateurs ont le même résultat : elles sont immédiatement répercutées dans la table d'accélérateurs.  
  
 Il existe trois propriétés pour chaque raccourci [ID](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/3487f185-de96-4b1d-87db-034a52223160/locales/en-US):  
  
-   Le [propriété modificateur](../windows/accelerator-modifier-property.md) définit des combinaisons de touches pour l’accélérateur de contrôle.  
  
    > [!NOTE]
    >  Dans la fenêtre Propriétés, cette propriété s'affiche sous forme de trois propriétés booléennes distinctes, qui peuvent être contrôlées indépendamment : Alt, Ctrl ou Maj.  
  
-   Le [propriété de clé](../windows/accelerator-key-property.md) définit la clé à utiliser comme accélérateur.  
  
-   Le [de la propriété Type](../windows/accelerator-type-property.md) détermine si la clé est interprétée comme virtuelle (VIRTKEY) ou ASCII/ANSI.  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour plus d’informations sur l’ajout manuel de fichiers de ressources aux projets managés, l’accès aux ressources, l’affichage de ressources statiques et l’assignation de chaînes de ressources à des propriétés, consultez [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## <a name="requirements"></a>Spécifications  
 Win32  
  
## <a name="see-also"></a>Voir aussi  
 [Touches accélérateur prédéfinies](../windows/predefined-accelerator-keys.md)   
 [Éditeurs de ressources](../mfc/resource-editors.md)   
 [Éditeur d’accélérateurs](../mfc/accelerator-editor.md)